
>Base Model Validation Accuracy : 82.76

>My Model Validation Accuracy : 83.53

>Model Code

```
def scheduler(epoch, lr):
  return round(0.01 * 1/(1 + 0.319 * epoch), 10)
model = Sequential()

model.add(SeparableConv2D(filters=64, kernel_size=3, strides=1, depth_multiplier=5, activation='relu', use_bias=False, input_shape=(32, 32, 3)))
model.add(BatchNormalization())
model.add(Dropout(0.2))
model.add(SeparableConv2D(filters=64, kernel_size=3, strides=1, depth_multiplier=4, activation='relu', use_bias=False))
model.add(BatchNormalization())
model.add(Dropout(0.2))
model.add(SeparableConv2D(filters=128, kernel_size=3, strides=2, depth_multiplier=3, activation='relu', use_bias=False))
model.add(BatchNormalization())
model.add(Dropout(0.2))
model.add(SeparableConv2D(filters=128, kernel_size=3, strides=1,depth_multiplier=2, activation='relu', use_bias=False))
model.add(BatchNormalization())
model.add(Dropout(0.2))
model.add(SeparableConv2D(filters=10, kernel_size=3, strides=2,depth_multiplier=1, activation='relu', use_bias=False))
model.add(BatchNormalization())
model.add(AveragePooling2D(5))
model.add(Flatten())
model.add(Softmax())
model.add(Activation('relu'))
# Compile the model
model.compile(optimizer=Adam(lr=0.003), loss='categorical_crossentropy', metrics=['accuracy'])

model.summary()
```
>Model Summary

```
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
separable_conv2d_128 (Separa (None, 30, 30, 64)        1095      
_________________________________________________________________
batch_normalization_116 (Bat (None, 30, 30, 64)        256       
_________________________________________________________________
dropout_96 (Dropout)         (None, 30, 30, 64)        0         
_________________________________________________________________
separable_conv2d_129 (Separa (None, 28, 28, 64)        18688     
_________________________________________________________________
batch_normalization_117 (Bat (None, 28, 28, 64)        256       
_________________________________________________________________
dropout_97 (Dropout)         (None, 28, 28, 64)        0         
_________________________________________________________________
separable_conv2d_130 (Separa (None, 13, 13, 128)       26304     
_________________________________________________________________
batch_normalization_118 (Bat (None, 13, 13, 128)       512       
_________________________________________________________________
dropout_98 (Dropout)         (None, 13, 13, 128)       0         
_________________________________________________________________
separable_conv2d_131 (Separa (None, 11, 11, 128)       35072     
_________________________________________________________________
batch_normalization_119 (Bat (None, 11, 11, 128)       512       
_________________________________________________________________
dropout_99 (Dropout)         (None, 11, 11, 128)       0         
_________________________________________________________________
separable_conv2d_132 (Separa (None, 5, 5, 10)          2432      
_________________________________________________________________
batch_normalization_120 (Bat (None, 5, 5, 10)          40        
_________________________________________________________________
average_pooling2d_10 (Averag (None, 1, 1, 10)          0         
_________________________________________________________________
flatten_20 (Flatten)         (None, 10)                0         
_________________________________________________________________
softmax_12 (Softmax)         (None, 10)                0         
_________________________________________________________________
activation_20 (Activation)   (None, 10)                0         
=================================================================
Total params: 85,167
Trainable params: 84,379
Non-trainable params: 788
_________________________________________________________________
```


>Epocs

```
Epoch 1/50
97/97 [==============================] - 29s 302ms/step - loss: 1.0873 - acc: 0.6509 - val_loss: 1.1356 - val_acc: 0.6171
Epoch 2/50
97/97 [==============================] - 29s 299ms/step - loss: 0.9874 - acc: 0.6810 - val_loss: 1.1300 - val_acc: 0.6271
Epoch 3/50
97/97 [==============================] - 29s 299ms/step - loss: 0.9137 - acc: 0.7035 - val_loss: 0.9353 - val_acc: 0.6881
Epoch 4/50
97/97 [==============================] - 29s 300ms/step - loss: 0.8599 - acc: 0.7207 - val_loss: 0.8603 - val_acc: 0.7116
Epoch 5/50
97/97 [==============================] - 29s 296ms/step - loss: 0.8089 - acc: 0.7367 - val_loss: 0.8211 - val_acc: 0.7249
Epoch 6/50
97/97 [==============================] - 29s 298ms/step - loss: 0.7799 - acc: 0.7439 - val_loss: 0.9331 - val_acc: 0.6869
Epoch 7/50
97/97 [==============================] - 29s 299ms/step - loss: 0.7517 - acc: 0.7543 - val_loss: 0.7552 - val_acc: 0.7464
Epoch 8/50
97/97 [==============================] - 29s 299ms/step - loss: 0.7192 - acc: 0.7632 - val_loss: 0.8037 - val_acc: 0.7278
Epoch 9/50
97/97 [==============================] - 29s 298ms/step - loss: 0.6976 - acc: 0.7699 - val_loss: 0.7020 - val_acc: 0.7604
Epoch 10/50
97/97 [==============================] - 29s 299ms/step - loss: 0.6759 - acc: 0.7775 - val_loss: 0.7299 - val_acc: 0.7495
Epoch 11/50
97/97 [==============================] - 29s 297ms/step - loss: 0.6597 - acc: 0.7819 - val_loss: 0.7293 - val_acc: 0.7522
Epoch 12/50
97/97 [==============================] - 29s 297ms/step - loss: 0.6432 - acc: 0.7863 - val_loss: 0.7180 - val_acc: 0.7588
Epoch 13/50
97/97 [==============================] - 29s 294ms/step - loss: 0.6271 - acc: 0.7913 - val_loss: 0.6762 - val_acc: 0.7702
Epoch 14/50
97/97 [==============================] - 29s 295ms/step - loss: 0.6150 - acc: 0.7972 - val_loss: 0.7367 - val_acc: 0.7592
Epoch 15/50
97/97 [==============================] - 29s 296ms/step - loss: 0.6042 - acc: 0.7960 - val_loss: 0.6410 - val_acc: 0.7872
Epoch 16/50
97/97 [==============================] - 29s 300ms/step - loss: 0.5914 - acc: 0.8020 - val_loss: 0.5701 - val_acc: 0.8075
Epoch 17/50
97/97 [==============================] - 29s 300ms/step - loss: 0.5786 - acc: 0.8068 - val_loss: 0.6578 - val_acc: 0.7804
Epoch 18/50
97/97 [==============================] - 29s 297ms/step - loss: 0.5787 - acc: 0.8051 - val_loss: 0.6121 - val_acc: 0.7925
Epoch 19/50
97/97 [==============================] - 29s 296ms/step - loss: 0.5648 - acc: 0.8104 - val_loss: 0.5982 - val_acc: 0.7979
Epoch 20/50
97/97 [==============================] - 29s 296ms/step - loss: 0.5560 - acc: 0.8124 - val_loss: 0.5822 - val_acc: 0.8013
Epoch 21/50
97/97 [==============================] - 29s 297ms/step - loss: 0.5494 - acc: 0.8150 - val_loss: 0.5353 - val_acc: 0.8135
Epoch 22/50
97/97 [==============================] - 29s 296ms/step - loss: 0.5479 - acc: 0.8140 - val_loss: 0.5967 - val_acc: 0.7988
Epoch 23/50
97/97 [==============================] - 29s 297ms/step - loss: 0.5313 - acc: 0.8200 - val_loss: 0.5700 - val_acc: 0.8056
Epoch 24/50
97/97 [==============================] - 29s 295ms/step - loss: 0.5263 - acc: 0.8204 - val_loss: 0.6127 - val_acc: 0.7935
Epoch 25/50
97/97 [==============================] - 29s 298ms/step - loss: 0.5233 - acc: 0.8240 - val_loss: 0.6097 - val_acc: 0.8032
Epoch 26/50
97/97 [==============================] - 29s 294ms/step - loss: 0.5165 - acc: 0.8250 - val_loss: 0.6009 - val_acc: 0.8016
Epoch 27/50
97/97 [==============================] - 29s 295ms/step - loss: 0.5167 - acc: 0.8256 - val_loss: 0.6178 - val_acc: 0.7902
Epoch 28/50
97/97 [==============================] - 29s 298ms/step - loss: 0.5058 - acc: 0.8268 - val_loss: 0.6278 - val_acc: 0.7967
Epoch 29/50
97/97 [==============================] - 29s 298ms/step - loss: 0.5063 - acc: 0.8289 - val_loss: 0.6283 - val_acc: 0.7947
Epoch 30/50
97/97 [==============================] - 29s 296ms/step - loss: 0.4908 - acc: 0.8324 - val_loss: 0.5494 - val_acc: 0.8126
Epoch 31/50
97/97 [==============================] - 29s 294ms/step - loss: 0.4983 - acc: 0.8292 - val_loss: 0.6461 - val_acc: 0.7921
Epoch 32/50
97/97 [==============================] - 29s 296ms/step - loss: 0.4876 - acc: 0.8360 - val_loss: 0.5819 - val_acc: 0.8060
Epoch 33/50
97/97 [==============================] - 29s 294ms/step - loss: 0.4772 - acc: 0.8366 - val_loss: 0.5084 - val_acc: 0.8274
Epoch 34/50
97/97 [==============================] - 28s 293ms/step - loss: 0.4816 - acc: 0.8359 - val_loss: 0.6780 - val_acc: 0.7831
Epoch 35/50
97/97 [==============================] - 29s 296ms/step - loss: 0.4810 - acc: 0.8339 - val_loss: 0.5189 - val_acc: 0.8250
Epoch 36/50
97/97 [==============================] - 29s 297ms/step - loss: 0.4706 - acc: 0.8400 - val_loss: 0.5218 - val_acc: 0.8258
Epoch 37/50
97/97 [==============================] - 29s 295ms/step - loss: 0.4756 - acc: 0.8366 - val_loss: 0.5839 - val_acc: 0.8071
Epoch 38/50
97/97 [==============================] - 29s 297ms/step - loss: 0.4660 - acc: 0.8388 - val_loss: 0.5383 - val_acc: 0.8167
Epoch 39/50
97/97 [==============================] - 29s 297ms/step - loss: 0.4677 - acc: 0.8409 - val_loss: 0.6273 - val_acc: 0.7964
Epoch 40/50
97/97 [==============================] - 29s 295ms/step - loss: 0.4627 - acc: 0.8421 - val_loss: 0.5396 - val_acc: 0.8191
Epoch 41/50
97/97 [==============================] - 29s 299ms/step - loss: 0.4603 - acc: 0.8433 - val_loss: 0.5731 - val_acc: 0.8137
Epoch 42/50
97/97 [==============================] - 29s 296ms/step - loss: 0.4516 - acc: 0.8444 - val_loss: 0.5776 - val_acc: 0.8125
Epoch 43/50
97/97 [==============================] - 29s 295ms/step - loss: 0.4544 - acc: 0.8455 - val_loss: 0.6038 - val_acc: 0.8026
Epoch 44/50
97/97 [==============================] - 29s 296ms/step - loss: 0.4519 - acc: 0.8431 - val_loss: 0.5632 - val_acc: 0.8160
Epoch 45/50
97/97 [==============================] - 29s 296ms/step - loss: 0.4522 - acc: 0.8454 - val_loss: 0.5064 - val_acc: 0.8313
Epoch 46/50
97/97 [==============================] - 30s 305ms/step - loss: 0.4426 - acc: 0.8496 - val_loss: 0.5605 - val_acc: 0.8157
Epoch 47/50
97/97 [==============================] - 29s 300ms/step - loss: 0.4393 - acc: 0.8492 - val_loss: 0.5308 - val_acc: 0.8255
Epoch 48/50
97/97 [==============================] - 29s 296ms/step - loss: 0.4327 - acc: 0.8507 - val_loss: 0.5733 - val_acc: 0.8113
Epoch 49/50
97/97 [==============================] - 29s 299ms/step - loss: 0.4367 - acc: 0.8498 - val_loss: 0.4819 - val_acc: 0.8383
Epoch 50/50
97/97 [==============================] - 29s 296ms/step - loss: 0.4422 - acc: 0.8491 - val_loss: 0.4769 - val_acc: 0.8353
Model took 1441.45 seconds to train

Accuracy on test data is: 83.53
```

