**Final Validation accuracy for base network:**
    82.14

**Model definition:**

    # Define the model                          Receptive field  -  output shape
    
    model = Sequential()
    model.add(SeparableConv2D(48, 3, 3, border_mode='same', input_shape=(32, 32, 3))) --3x3 -- 32x32x48
    model.add(Activation('relu'))
    model.add(BatchNormalization())
    #model.add(Dropout(0.1))


    model.add(SeparableConv2D(48, 3, 3))  -- 5x5 -- 30x30x48
    model.add(Activation('relu'))
    model.add(BatchNormalization())
    #model.add(Dropout(0.1))


    model.add(MaxPooling2D(pool_size=(2, 2))) # 10x10 -- 15x15x48
    model.add(Dropout(0.2))

    model.add(SeparableConv2D(96, 3, 3)) -- 12x12   --- 13x13x96
    model.add(Activation('relu'))
    model.add(BatchNormalization())
    #model.add(Dropout(0.1))

    model.add(SeparableConv2D(96, 3, 3)) -- 14x14  -- 11x11x96
    model.add(Activation('relu'))
    model.add(BatchNormalization())
    #model.add(Dropout(0.1))

    model.add(MaxPooling2D(pool_size=(2, 2))) -- 28x28  -- 5x5x96
    model.add(Dropout(0.25))

    model.add(SeparableConv2D(192, 3, 3, border_mode='same'))  -- 30x30 --5x5x192
    model.add(Activation('relu'))
    model.add(BatchNormalization())



    model.add(SeparableConv2D(192, 3, 3)) --32x32 --3x3x192
    model.add(Activation('relu'))
    model.add(BatchNormalization())
    #model.add(Dropout(0.2))

    model.add(MaxPooling2D(pool_size=(2, 2))) --64x64 -- 1x1x192
    model.add(Dropout(0.25))

    model.add(SeparableConv2D(10, 1, 1)) --64x64 -- 1x1x10

    model.add(Activation('relu'))
    model.add(BatchNormalization())


    #model.add(Flatten())

    model.add(GlobalAveragePooling2D())
    model.add(Activation('softmax'))



    model.summary()
    # Compile the model
    model.compile(optimizer="adam", loss='categorical_crossentropy', metrics=['accuracy'])


out put channel size:
1x1 x10

output rece3ptive field :
64x64

**Logs:**

/usr/local/lib/python3.6/dist-packages/ipykernel_launcher.py:12: UserWarning: The semantics of the Keras 2 argument `steps_per_epoch` is not the same as the Keras 1 argument `samples_per_epoch`. `steps_per_epoch` is the number of batches to draw from the generator at each epoch. Basically steps_per_epoch = samples_per_epoch/batch_size. Similarly `nb_val_samples`->`validation_steps` and `val_samples`->`steps` arguments have changed. Update your method calls accordingly.
  if sys.path[0] == '':
/usr/local/lib/python3.6/dist-packages/ipykernel_launcher.py:12: UserWarning: Update your `fit_generator` call to the Keras 2 API: `fit_generator(<keras_pre..., validation_data=(array([[[..., verbose=1, steps_per_epoch=390, epochs=50)`
  if sys.path[0] == '':
Epoch 1/50
390/390 [==============================] - 34s 87ms/step - loss: 1.8057 - acc: 0.3598 - val_loss: 1.6099 - val_acc: 0.4359
Epoch 2/50
390/390 [==============================] - 23s 60ms/step - loss: 1.4741 - acc: 0.4900 - val_loss: 1.2756 - val_acc: 0.5574
Epoch 3/50
390/390 [==============================] - 24s 61ms/step - loss: 1.3241 - acc: 0.5458 - val_loss: 1.1787 - val_acc: 0.5960
Epoch 4/50
390/390 [==============================] - 24s 61ms/step - loss: 1.2212 - acc: 0.5851 - val_loss: 1.1327 - val_acc: 0.6066
Epoch 5/50
390/390 [==============================] - 23s 60ms/step - loss: 1.1390 - acc: 0.6140 - val_loss: 1.0892 - val_acc: 0.6291
Epoch 6/50
390/390 [==============================] - 24s 60ms/step - loss: 1.0803 - acc: 0.6328 - val_loss: 0.9643 - val_acc: 0.6678
Epoch 7/50
390/390 [==============================] - 24s 61ms/step - loss: 1.0230 - acc: 0.6512 - val_loss: 1.0847 - val_acc: 0.6333
Epoch 8/50
390/390 [==============================] - 24s 60ms/step - loss: 0.9807 - acc: 0.6662 - val_loss: 0.9321 - val_acc: 0.6857
Epoch 9/50
390/390 [==============================] - 24s 60ms/step - loss: 0.9469 - acc: 0.6762 - val_loss: 0.8209 - val_acc: 0.7194
Epoch 10/50
390/390 [==============================] - 24s 60ms/step - loss: 0.9155 - acc: 0.6903 - val_loss: 0.8986 - val_acc: 0.6953
Epoch 11/50
390/390 [==============================] - 23s 60ms/step - loss: 0.8873 - acc: 0.6970 - val_loss: 0.7853 - val_acc: 0.7325
Epoch 12/50
390/390 [==============================] - 23s 60ms/step - loss: 0.8695 - acc: 0.6993 - val_loss: 0.7460 - val_acc: 0.7431
Epoch 13/50
390/390 [==============================] - 23s 59ms/step - loss: 0.8475 - acc: 0.7082 - val_loss: 0.7464 - val_acc: 0.7426
Epoch 14/50
390/390 [==============================] - 23s 60ms/step - loss: 0.8205 - acc: 0.7169 - val_loss: 0.8173 - val_acc: 0.7208
Epoch 15/50
390/390 [==============================] - 23s 59ms/step - loss: 0.8044 - acc: 0.7229 - val_loss: 0.7472 - val_acc: 0.7427
Epoch 16/50
390/390 [==============================] - 23s 60ms/step - loss: 0.7949 - acc: 0.7241 - val_loss: 0.7148 - val_acc: 0.7530
Epoch 17/50
390/390 [==============================] - 23s 60ms/step - loss: 0.7784 - acc: 0.7310 - val_loss: 0.6975 - val_acc: 0.7609
Epoch 18/50
390/390 [==============================] - 23s 59ms/step - loss: 0.7716 - acc: 0.7322 - val_loss: 0.7186 - val_acc: 0.7540
Epoch 19/50
390/390 [==============================] - 23s 59ms/step - loss: 0.7592 - acc: 0.7368 - val_loss: 0.7006 - val_acc: 0.7565
Epoch 20/50
390/390 [==============================] - 23s 59ms/step - loss: 0.7432 - acc: 0.7424 - val_loss: 0.6793 - val_acc: 0.7634
Epoch 21/50
390/390 [==============================] - 23s 59ms/step - loss: 0.7413 - acc: 0.7420 - val_loss: 0.6765 - val_acc: 0.7680
Epoch 22/50
390/390 [==============================] - 23s 60ms/step - loss: 0.7282 - acc: 0.7481 - val_loss: 0.6551 - val_acc: 0.7765
Epoch 23/50
390/390 [==============================] - 23s 59ms/step - loss: 0.7231 - acc: 0.7478 - val_loss: 0.6827 - val_acc: 0.7637
Epoch 24/50
390/390 [==============================] - 23s 60ms/step - loss: 0.7110 - acc: 0.7551 - val_loss: 0.6970 - val_acc: 0.7598
Epoch 25/50
390/390 [==============================] - 23s 60ms/step - loss: 0.7075 - acc: 0.7566 - val_loss: 0.6529 - val_acc: 0.7748
Epoch 26/50
390/390 [==============================] - 23s 60ms/step - loss: 0.7024 - acc: 0.7572 - val_loss: 0.7358 - val_acc: 0.7510
Epoch 27/50
390/390 [==============================] - 23s 59ms/step - loss: 0.6992 - acc: 0.7590 - val_loss: 0.6358 - val_acc: 0.7797
Epoch 28/50
390/390 [==============================] - 23s 60ms/step - loss: 0.6902 - acc: 0.7600 - val_loss: 0.6301 - val_acc: 0.7857
Epoch 29/50
390/390 [==============================] - 23s 59ms/step - loss: 0.6842 - acc: 0.7622 - val_loss: 0.6920 - val_acc: 0.7675
Epoch 30/50
390/390 [==============================] - 23s 59ms/step - loss: 0.6731 - acc: 0.7661 - val_loss: 0.6145 - val_acc: 0.7867
Epoch 31/50
390/390 [==============================] - 23s 60ms/step - loss: 0.6683 - acc: 0.7687 - val_loss: 0.6016 - val_acc: 0.7943
Epoch 32/50
390/390 [==============================] - 23s 59ms/step - loss: 0.6685 - acc: 0.7681 - val_loss: 0.6563 - val_acc: 0.7740
Epoch 33/50
390/390 [==============================] - 23s 59ms/step - loss: 0.6566 - acc: 0.7724 - val_loss: 0.7109 - val_acc: 0.7602
Epoch 34/50
390/390 [==============================] - 23s 59ms/step - loss: 0.6573 - acc: 0.7717 - val_loss: 0.6145 - val_acc: 0.7864
Epoch 35/50
390/390 [==============================] - 23s 60ms/step - loss: 0.6531 - acc: 0.7742 - val_loss: 0.5758 - val_acc: 0.8057
Epoch 36/50
390/390 [==============================] - 23s 59ms/step - loss: 0.6509 - acc: 0.7741 - val_loss: 0.6218 - val_acc: 0.7867
Epoch 37/50
390/390 [==============================] - 23s 59ms/step - loss: 0.6485 - acc: 0.7758 - val_loss: 0.5879 - val_acc: 0.7998
Epoch 38/50
390/390 [==============================] - 23s 60ms/step - loss: 0.6373 - acc: 0.7787 - val_loss: 0.6294 - val_acc: 0.7861
Epoch 39/50
390/390 [==============================] - 23s 59ms/step - loss: 0.6432 - acc: 0.7766 - val_loss: 0.6029 - val_acc: 0.7973
Epoch 40/50
390/390 [==============================] - 23s 59ms/step - loss: 0.6283 - acc: 0.7826 - val_loss: 0.5923 - val_acc: 0.7956
Epoch 41/50
390/390 [==============================] - 23s 60ms/step - loss: 0.6284 - acc: 0.7812 - val_loss: 0.5956 - val_acc: 0.7973
Epoch 42/50
390/390 [==============================] - 24s 60ms/step - loss: 0.6221 - acc: 0.7830 - val_loss: 0.5620 - val_acc: 0.8072
Epoch 43/50
390/390 [==============================] - 23s 59ms/step - loss: 0.6202 - acc: 0.7849 - val_loss: 0.5767 - val_acc: 0.8003
Epoch 44/50
390/390 [==============================] - 24s 60ms/step - loss: 0.6188 - acc: 0.7861 - val_loss: 0.5544 - val_acc: 0.8094
Epoch 45/50
390/390 [==============================] - 23s 60ms/step - loss: 0.6223 - acc: 0.7837 - val_loss: 0.5623 - val_acc: 0.8087
Epoch 46/50
390/390 [==============================] - 23s 59ms/step - loss: 0.6122 - acc: 0.7873 - val_loss: 0.5613 - val_acc: 0.8055
Epoch 47/50
390/390 [==============================] - 23s 58ms/step - loss: 0.6021 - acc: 0.7898 - val_loss: 0.5732 - val_acc: 0.8015
Epoch 48/50
390/390 [==============================] - 23s 59ms/step - loss: 0.6069 - acc: 0.7899 - val_loss: 0.5473 - val_acc: 0.8145
Epoch 49/50
390/390 [==============================] - 23s 59ms/step - loss: 0.6051 - acc: 0.7883 - val_loss: 0.5581 - val_acc: 0.8065
Epoch 50/50
390/390 [==============================] - 23s 58ms/step - loss: 0.5965 - acc: 0.7923 - val_loss: 0.5900 - val_acc: 0.7988
Model took 1173.17 seconds to train




























