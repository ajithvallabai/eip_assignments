**Final Validation accuracy for base network:**
    82.14

**Model definition: Receptive field : Output shape**

    # Define the model                          Receptive field  -  output shape**
    
    # Define the model
    model = Sequential()
    model.add(SeparableConv2D(32, 3, 3, border_mode='same', input_shape=(32, 32, 3)))  RF -- 3x3  output --   32x32x32
    model.add(Activation('relu'))
    model.add(BatchNormalization())
    #model.add(Dropout(0.1))


    model.add(SeparableConv2D(64, 3, 3, border_mode='same'))  RF -- 5x5 output-32x32x64
    model.add(Activation('relu'))
    model.add(BatchNormalization())
    #model.add(Dropout(0.1))

    model.add(SeparableConv2D(128, 3, 3, border_mode='same'))  RF -- 7x7 output--32x32x128
    model.add(Activation('relu'))
    model.add(BatchNormalization())
    model.add(SeparableConv2D(128, 3, 3)) RF   -- 9x9  output-- 30x30x128
    model.add(Activation('relu'))
    model.add(BatchNormalization())

    model.add(AveragePooling2D(pool_size=(2, 2))) RF  -- 18x18 output--15x15x128
    model.add(Dropout(0.2))

    model.add(SeparableConv2D(32, 1, 1)) RF  --18x18 output --15x15x32
    model.add(Activation('relu'))
    model.add(BatchNormalization())


    #------
    model.add(SeparableConv2D(32, 3, 3, border_mode='same')) RF -- 20x20 output--15x15x32
    model.add(Activation('relu'))
    model.add(BatchNormalization())


    model.add(SeparableConv2D(64, 3, 3, border_mode='same')) RF  -- 22x22 output--15x15x64
    model.add(Activation('relu'))
    model.add(BatchNormalization())


    model.add(SeparableConv2D(128, 3, 3, border_mode='same')) RF -- 24x24
    output--15x15x128
    model.add(Activation('relu'))
    model.add(BatchNormalization())


    model.add(SeparableConv2D(128, 3, 3, border_mode='same')) RF -- 26x26 output--15x15x128
    model.add(Activation('relu'))
    model.add(BatchNormalization())


    model.add(AveragePooling2D(pool_size=(2, 2)))  RF -- 52x52 output--7x7x128
    model.add(Dropout(0.25))

    model.add(SeparableConv2D(32, 1, 1))  RF --52x52  output--7x7x32
    model.add(Activation('relu'))
    model.add(BatchNormalization())

    #--------

    model.add(SeparableConv2D(32, 3, 3, border_mode='same'))  RF --54x54 output--7x7x32
    model.add(Activation('relu'))
    model.add(BatchNormalization())

    model.add(SeparableConv2D(64, 3, 3, border_mode='same')) RF  --56x56 output--7x7x64
    model.add(Activation('relu'))
    model.add(BatchNormalization())


    model.add(SeparableConv2D(128, 3, 3, border_mode='same')) RF --58x58 output--7x7x128
    model.add(Activation('relu'))
    model.add(BatchNormalization())


    model.add(AveragePooling2D(pool_size=(2, 2)))   RF output-- 106x106 --3x3x128
    model.add(Dropout(0.25))

    model.add(SeparableConv2D(32, 1, 1)) RF  --106x106 output--3x3x32
    model.add(Activation('relu'))
    model.add(BatchNormalization())

    model.add(SeparableConv2D(64, 3, 3)) RF --108x108 output--1x1x64
    model.add(Activation('relu'))
    model.add(BatchNormalization())


    model.add(SeparableConv2D(10, 1, 1))  RF --108x108   output--1x1x10

    model.add(Activation('relu'))
    model.add(BatchNormalization())


    model.add(GlobalAveragePooling2D())
    model.add(Activation('softmax'))

    model.summary()
    # Compile the model
    model.compile(optimizer=sgd, loss='categorical_crossentropy', metrics=['accuracy'])


out put channel size:
1x1 x10

output rece3ptive field :
64x64

**Logs:**

    
    
    Epoch 1/50
    390/390 [==============================] - 49s 125ms/step - loss: 1.9345 - acc: 0.2961 - val_loss: 1.9253 - val_acc: 0.3285
    Epoch 2/50
    390/390 [==============================] - 29s 75ms/step - loss: 1.6588 - acc: 0.3989 - val_loss: 1.7126 - val_acc: 0.3887
    Epoch 3/50
    390/390 [==============================] - 29s 75ms/step - loss: 1.5402 - acc: 0.4439 - val_loss: 1.6375 - val_acc: 0.4311
    Epoch 4/50
    390/390 [==============================] - 29s 75ms/step - loss: 1.4559 - acc: 0.4751 - val_loss: 1.5847 - val_acc: 0.4466
    Epoch 5/50
    390/390 [==============================] - 29s 75ms/step - loss: 1.3784 - acc: 0.5035 - val_loss: 1.3659 - val_acc: 0.5184
    Epoch 6/50
    390/390 [==============================] - 29s 74ms/step - loss: 1.3034 - acc: 0.5343 - val_loss: 1.3036 - val_acc: 0.5375
    Epoch 7/50
    390/390 [==============================] - 29s 75ms/step - loss: 1.2257 - acc: 0.5631 - val_loss: 1.1809 - val_acc: 0.5841
    Epoch 8/50
    390/390 [==============================] - 29s 75ms/step - loss: 1.1577 - acc: 0.5895 - val_loss: 1.0649 - val_acc: 0.6222
    Epoch 9/50
    390/390 [==============================] - 30s 76ms/step - loss: 1.0978 - acc: 0.6101 - val_loss: 1.1099 - val_acc: 0.6071
    Epoch 10/50
    390/390 [==============================] - 29s 75ms/step - loss: 1.0452 - acc: 0.6314 - val_loss: 1.2462 - val_acc: 0.5787
    Epoch 11/50
    390/390 [==============================] - 29s 75ms/step - loss: 1.0077 - acc: 0.6442 - val_loss: 1.0818 - val_acc: 0.6241
    Epoch 12/50
    390/390 [==============================] - 29s 74ms/step - loss: 0.9692 - acc: 0.6561 - val_loss: 0.9912 - val_acc: 0.6560
    Epoch 13/50
    390/390 [==============================] - 29s 74ms/step - loss: 0.9383 - acc: 0.6690 - val_loss: 0.9689 - val_acc: 0.6669
    Epoch 14/50
    390/390 [==============================] - 29s 74ms/step - loss: 0.8997 - acc: 0.6823 - val_loss: 0.9322 - val_acc: 0.6760
    Epoch 15/50
    390/390 [==============================] - 29s 75ms/step - loss: 0.8708 - acc: 0.6943 - val_loss: 0.9099 - val_acc: 0.6846
    Epoch 16/50
    390/390 [==============================] - 29s 74ms/step - loss: 0.8469 - acc: 0.7015 - val_loss: 0.9091 - val_acc: 0.6873
    Epoch 17/50
    390/390 [==============================] - 29s 74ms/step - loss: 0.8195 - acc: 0.7133 - val_loss: 0.7710 - val_acc: 0.7313
    Epoch 18/50
    390/390 [==============================] - 29s 74ms/step - loss: 0.8025 - acc: 0.7174 - val_loss: 0.8344 - val_acc: 0.7077
    Epoch 19/50
    390/390 [==============================] - 28s 73ms/step - loss: 0.7774 - acc: 0.7278 - val_loss: 0.7906 - val_acc: 0.7260
    Epoch 20/50
    390/390 [==============================] - 29s 74ms/step - loss: 0.7606 - acc: 0.7338 - val_loss: 0.7898 - val_acc: 0.7297
    Epoch 21/50
    390/390 [==============================] - 29s 73ms/step - loss: 0.7356 - acc: 0.7435 - val_loss: 0.7275 - val_acc: 0.7482
    Epoch 22/50
    390/390 [==============================] - 29s 73ms/step - loss: 0.7273 - acc: 0.7456 - val_loss: 0.6681 - val_acc: 0.7669
    Epoch 23/50
    390/390 [==============================] - 29s 73ms/step - loss: 0.7044 - acc: 0.7535 - val_loss: 0.7182 - val_acc: 0.7561
    Epoch 24/50
    390/390 [==============================] - 28s 73ms/step - loss: 0.6923 - acc: 0.7579 - val_loss: 0.7037 - val_acc: 0.7608
    Epoch 25/50
    390/390 [==============================] - 29s 75ms/step - loss: 0.6780 - acc: 0.7644 - val_loss: 0.6777 - val_acc: 0.7620
    Epoch 26/50
    390/390 [==============================] - 29s 74ms/step - loss: 0.6614 - acc: 0.7678 - val_loss: 0.6681 - val_acc: 0.7769
    Epoch 27/50
    390/390 [==============================] - 29s 74ms/step - loss: 0.6586 - acc: 0.7709 - val_loss: 0.7212 - val_acc: 0.7543
    Epoch 28/50
    390/390 [==============================] - 29s 73ms/step - loss: 0.6414 - acc: 0.7778 - val_loss: 0.6646 - val_acc: 0.7759
    Epoch 29/50
    390/390 [==============================] - 29s 74ms/step - loss: 0.6310 - acc: 0.7792 - val_loss: 0.6118 - val_acc: 0.7891
    Epoch 30/50
    390/390 [==============================] - 29s 75ms/step - loss: 0.6211 - acc: 0.7838 - val_loss: 0.7647 - val_acc: 0.7469
    Epoch 31/50
    390/390 [==============================] - 29s 74ms/step - loss: 0.6189 - acc: 0.7854 - val_loss: 0.5865 - val_acc: 0.8009
    Epoch 32/50
    390/390 [==============================] - 29s 74ms/step - loss: 0.6012 - acc: 0.7933 - val_loss: 0.6556 - val_acc: 0.7789
    Epoch 33/50
    390/390 [==============================] - 29s 74ms/step - loss: 0.5987 - acc: 0.7915 - val_loss: 0.5830 - val_acc: 0.7989
    Epoch 34/50
    390/390 [==============================] - 29s 74ms/step - loss: 0.5883 - acc: 0.7950 - val_loss: 0.5846 - val_acc: 0.7961
    Epoch 35/50
    390/390 [==============================] - 29s 74ms/step - loss: 0.5775 - acc: 0.7991 - val_loss: 0.5792 - val_acc: 0.8055
    Epoch 36/50
    390/390 [==============================] - 29s 75ms/step - loss: 0.5762 - acc: 0.8001 - val_loss: 0.6453 - val_acc: 0.7825
    Epoch 37/50
    390/390 [==============================] - 29s 74ms/step - loss: 0.5686 - acc: 0.8007 - val_loss: 0.5410 - val_acc: 0.8158
    Epoch 38/50
    390/390 [==============================] - 29s 74ms/step - loss: 0.5520 - acc: 0.8086 - val_loss: 0.5603 - val_acc: 0.8081
    Epoch 39/50
    390/390 [==============================] - 29s 74ms/step - loss: 0.5527 - acc: 0.8091 - val_loss: 0.6905 - val_acc: 0.7697
    Epoch 40/50
    390/390 [==============================] - 29s 73ms/step - loss: 0.5484 - acc: 0.8097 - val_loss: 0.6598 - val_acc: 0.7790
    Epoch 41/50
    390/390 [==============================] - 29s 73ms/step - loss: 0.5398 - acc: 0.8114 - val_loss: 0.6341 - val_acc: 0.7865
    Epoch 42/50
    390/390 [==============================] - 29s 73ms/step - loss: 0.5357 - acc: 0.8151 - val_loss: 0.5477 - val_acc: 0.8166
    Epoch 43/50
    390/390 [==============================] - 29s 73ms/step - loss: 0.5305 - acc: 0.8168 - val_loss: 0.6230 - val_acc: 0.7898
    Epoch 44/50
    390/390 [==============================] - 29s 73ms/step - loss: 0.5263 - acc: 0.8175 - val_loss: 0.5302 - val_acc: 0.8244
    Epoch 45/50
    390/390 [==============================] - 29s 73ms/step - loss: 0.5138 - acc: 0.8211 - val_loss: 0.5517 - val_acc: 0.8153
    Epoch 46/50
    390/390 [==============================] - 28s 72ms/step - loss: 0.5122 - acc: 0.8215 - val_loss: 0.5561 - val_acc: 0.8124
    Epoch 47/50
    390/390 [==============================] - 29s 73ms/step - loss: 0.5096 - acc: 0.8249 - val_loss: 0.5104 - val_acc: 0.8300
    Epoch 48/50
    390/390 [==============================] - 29s 73ms/step - loss: 0.5023 - acc: 0.8272 - val_loss: 0.6437 - val_acc: 0.7917
    Epoch 49/50
    390/390 [==============================] - 28s 73ms/step - loss: 0.4948 - acc: 0.8290 - val_loss: 0.5037 - val_acc: 0.8308
    Epoch 50/50
    390/390 [==============================] - 29s 73ms/step - loss: 0.4907 - acc: 0.8293 - val_loss: 0.5081 - val_acc: 0.8310
    Model took 1463.28 seconds to train

    Accuracy on test data is: 83.10



























