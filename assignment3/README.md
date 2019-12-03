**Final Validation accuracy for base network:**
    82.75

**Model definition:**

    # Define the model         Receptive field  -  output shape
    model = Sequential()
    model.add(SeparableConv2D(32, 3, 3, border_mode='same', input_shape=(32, 32, 3)))  # 3x3 - 32x32x32
    model.add(BatchNormalization())
    model.add(Dropout(0.1))
    model.add(Activation('relu'))

    model.add(SeparableConv2D(32, 3, 3)) # 5x5 - 30x30x32
    model.add(BatchNormalization())
    model.add(Dropout(0.1))
    model.add(Activation('relu'))

    model.add(MaxPooling2D(pool_size=(2, 2))) # 10x10 -15x15x32
    model.add(Dropout(0.25))

    model.add(SeparableConv2D(64, 3, 3, border_mode='same')) #12x12 - 15x15x64
    model.add(BatchNormalization())
    model.add(Activation('relu'))


    model.add(SeparableConv2D(64, 3, 3)) #14x14 -13x13-64
    model.add(BatchNormalization())
    model.add(Dropout(0.2))
    model.add(Activation('relu'))

    model.add(SeparableConv2D(64, 3, 3)) #16x16 -11x11x64
    model.add(BatchNormalization())
    model.add(Dropout(0.1))
    model.add(Activation('relu'))

    model.add(SeparableConv2D(64, 3, 3))  #18x18 -9x9x64
    model.add(BatchNormalization())
    model.add(Dropout(0.1))
    model.add(Activation('relu'))


    model.add(SeparableConv2D(128, 3, 3, border_mode='same')) #20x20 -9x9x128
    model.add(BatchNormalization())
    model.add(Dropout(0.2))
    model.add(Activation('relu'))

    model.add(SeparableConv2D(128, 3, 3)) #22x22 -7x7x128
    model.add(BatchNormalization())
    model.add(Dropout(0.1))
    model.add(Activation('relu'))

    model.add(SeparableConv2D(128, 3, 3)) #24x24 -5x5x128
    model.add(BatchNormalization())
    model.add(Dropout(0.1))
    model.add(Activation('relu'))


    model.add(SeparableConv2D(10, 5, 5)) #28x28 -1x1x10
    model.add(BatchNormalization())

    model.add(Activation('relu'))

    #model.add(Flatten())

    model.add(GlobalAveragePooling2D())
    model.add(Activation('softmax'))


    model.summary()
    # Compile the model
    model.compile(optimizer='adam', loss='categorical_crossentropy', metrics=['accuracy'])


out put channel size:
1x1 x10

output rece3ptive field :
28x28

**Logs:**

Epoch 1/50
390/390 [==============================] - 31s 79ms/step - loss: 1.9315 - acc: 0.3077 - val_loss: 2.0321 - val_acc: 0.3246
Epoch 2/50
390/390 [==============================] - 26s 67ms/step - loss: 1.5090 - acc: 0.4814 - val_loss: 1.6726 - val_acc: 0.4311
Epoch 3/50
390/390 [==============================] - 26s 67ms/step - loss: 1.3216 - acc: 0.5493 - val_loss: 1.2824 - val_acc: 0.5597
Epoch 4/50
390/390 [==============================] - 26s 67ms/step - loss: 1.1992 - acc: 0.5917 - val_loss: 1.3940 - val_acc: 0.5218
Epoch 5/50
390/390 [==============================] - 26s 67ms/step - loss: 1.1040 - acc: 0.6238 - val_loss: 1.1445 - val_acc: 0.6102
Epoch 6/50
390/390 [==============================] - 26s 67ms/step - loss: 1.0227 - acc: 0.6495 - val_loss: 1.2429 - val_acc: 0.5790
Epoch 7/50
390/390 [==============================] - 26s 67ms/step - loss: 0.9579 - acc: 0.6734 - val_loss: 1.2386 - val_acc: 0.5849
Epoch 8/50
390/390 [==============================] - 26s 67ms/step - loss: 0.9006 - acc: 0.6924 - val_loss: 1.0398 - val_acc: 0.6545
Epoch 9/50
390/390 [==============================] - 26s 67ms/step - loss: 0.8642 - acc: 0.7044 - val_loss: 0.8587 - val_acc: 0.7060
Epoch 10/50
390/390 [==============================] - 26s 67ms/step - loss: 0.8288 - acc: 0.7157 - val_loss: 0.9085 - val_acc: 0.6918
Epoch 11/50
390/390 [==============================] - 26s 67ms/step - loss: 0.7986 - acc: 0.7255 - val_loss: 0.8406 - val_acc: 0.7155
Epoch 12/50
390/390 [==============================] - 26s 67ms/step - loss: 0.7702 - acc: 0.7381 - val_loss: 1.0454 - val_acc: 0.6475
Epoch 13/50
390/390 [==============================] - 26s 67ms/step - loss: 0.7500 - acc: 0.7431 - val_loss: 0.7313 - val_acc: 0.7502
Epoch 14/50
390/390 [==============================] - 26s 67ms/step - loss: 0.7214 - acc: 0.7530 - val_loss: 0.8585 - val_acc: 0.7117
Epoch 15/50
390/390 [==============================] - 26s 67ms/step - loss: 0.7097 - acc: 0.7548 - val_loss: 0.8372 - val_acc: 0.7163
Epoch 16/50
390/390 [==============================] - 26s 67ms/step - loss: 0.6913 - acc: 0.7625 - val_loss: 0.9236 - val_acc: 0.6929
Epoch 17/50
390/390 [==============================] - 26s 67ms/step - loss: 0.6739 - acc: 0.7675 - val_loss: 0.7084 - val_acc: 0.7583
Epoch 18/50
390/390 [==============================] - 26s 67ms/step - loss: 0.6606 - acc: 0.7723 - val_loss: 0.7546 - val_acc: 0.7454
Epoch 19/50
390/390 [==============================] - 26s 67ms/step - loss: 0.6456 - acc: 0.7776 - val_loss: 0.7727 - val_acc: 0.7481
Epoch 20/50
390/390 [==============================] - 26s 66ms/step - loss: 0.6312 - acc: 0.7834 - val_loss: 0.7195 - val_acc: 0.7646
Epoch 21/50
390/390 [==============================] - 26s 67ms/step - loss: 0.6275 - acc: 0.7821 - val_loss: 0.7272 - val_acc: 0.7533
Epoch 22/50
390/390 [==============================] - 26s 67ms/step - loss: 0.6172 - acc: 0.7874 - val_loss: 0.6983 - val_acc: 0.7606
Epoch 23/50
390/390 [==============================] - 26s 67ms/step - loss: 0.6036 - acc: 0.7923 - val_loss: 0.8803 - val_acc: 0.7057
Epoch 24/50
390/390 [==============================] - 26s 67ms/step - loss: 0.5973 - acc: 0.7940 - val_loss: 0.6813 - val_acc: 0.7688
Epoch 25/50
390/390 [==============================] - 26s 67ms/step - loss: 0.5908 - acc: 0.7963 - val_loss: 0.7543 - val_acc: 0.7467
Epoch 26/50
390/390 [==============================] - 26s 67ms/step - loss: 0.5803 - acc: 0.7970 - val_loss: 0.7536 - val_acc: 0.7441
Epoch 27/50
390/390 [==============================] - 26s 67ms/step - loss: 0.5683 - acc: 0.8031 - val_loss: 0.7744 - val_acc: 0.7489
Epoch 28/50
390/390 [==============================] - 26s 67ms/step - loss: 0.5680 - acc: 0.8015 - val_loss: 0.6353 - val_acc: 0.7869
Epoch 29/50
390/390 [==============================] - 26s 67ms/step - loss: 0.5558 - acc: 0.8058 - val_loss: 0.6710 - val_acc: 0.7844
Epoch 30/50
390/390 [==============================] - 26s 67ms/step - loss: 0.5512 - acc: 0.8072 - val_loss: 0.7507 - val_acc: 0.7512
Epoch 31/50
390/390 [==============================] - 26s 67ms/step - loss: 0.5473 - acc: 0.8081 - val_loss: 0.7041 - val_acc: 0.7657
Epoch 32/50
390/390 [==============================] - 26s 67ms/step - loss: 0.5381 - acc: 0.8145 - val_loss: 0.8052 - val_acc: 0.7412
Epoch 33/50
390/390 [==============================] - 26s 67ms/step - loss: 0.5302 - acc: 0.8171 - val_loss: 0.7120 - val_acc: 0.7673
Epoch 34/50
390/390 [==============================] - 26s 67ms/step - loss: 0.5270 - acc: 0.8162 - val_loss: 0.6545 - val_acc: 0.7821
Epoch 35/50
390/390 [==============================] - 26s 67ms/step - loss: 0.5222 - acc: 0.8167 - val_loss: 0.6951 - val_acc: 0.7754
Epoch 36/50
390/390 [==============================] - 26s 67ms/step - loss: 0.5179 - acc: 0.8201 - val_loss: 0.7593 - val_acc: 0.7549
Epoch 37/50
390/390 [==============================] - 26s 67ms/step - loss: 0.5108 - acc: 0.8218 - val_loss: 0.6571 - val_acc: 0.7863
Epoch 38/50
390/390 [==============================] - 26s 67ms/step - loss: 0.5097 - acc: 0.8202 - val_loss: 0.8007 - val_acc: 0.7481
Epoch 39/50
390/390 [==============================] - 26s 67ms/step - loss: 0.5009 - acc: 0.8250 - val_loss: 0.6657 - val_acc: 0.7797
Epoch 40/50
390/390 [==============================] - 26s 67ms/step - loss: 0.4982 - acc: 0.8259 - val_loss: 0.6545 - val_acc: 0.7824
Epoch 41/50
390/390 [==============================] - 26s 67ms/step - loss: 0.4928 - acc: 0.8290 - val_loss: 0.6727 - val_acc: 0.7814
Epoch 42/50
390/390 [==============================] - 26s 67ms/step - loss: 0.4928 - acc: 0.8282 - val_loss: 0.7056 - val_acc: 0.7674
Epoch 43/50
390/390 [==============================] - 26s 67ms/step - loss: 0.4899 - acc: 0.8275 - val_loss: 0.6667 - val_acc: 0.7798
Epoch 44/50
390/390 [==============================] - 26s 67ms/step - loss: 0.4781 - acc: 0.8327 - val_loss: 0.7086 - val_acc: 0.7669
Epoch 45/50
390/390 [==============================] - 26s 67ms/step - loss: 0.4830 - acc: 0.8301 - val_loss: 0.6802 - val_acc: 0.7799
Epoch 46/50
390/390 [==============================] - 26s 67ms/step - loss: 0.4730 - acc: 0.8336 - val_loss: 0.6839 - val_acc: 0.7771
Epoch 47/50
390/390 [==============================] - 26s 67ms/step - loss: 0.4714 - acc: 0.8359 - val_loss: 0.6799 - val_acc: 0.7740
Epoch 48/50
390/390 [==============================] - 26s 67ms/step - loss: 0.4652 - acc: 0.8369 - val_loss: 0.7190 - val_acc: 0.7691
Epoch 49/50
390/390 [==============================] - 26s 67ms/step - loss: 0.4643 - acc: 0.8368 - val_loss: 0.6435 - val_acc: 0.7871
Epoch 50/50
390/390 [==============================] - 26s 67ms/step - loss: 0.4622 - acc: 0.8373 - val_loss: 0.6926 - val_acc: 0.7793
Model took 1310.89 seconds to train



























