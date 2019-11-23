Explanation:
Overfit because 13k increased dropout
learning rate is too high to be trained in the lower number of epocs
batch size ideal at 128


Model
```

_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
conv2d_65 (Conv2D)           (None, 26, 26, 10)        90        
_________________________________________________________________
batch_normalization_49 (Batc (None, 26, 26, 10)        40        
_________________________________________________________________
conv2d_66 (Conv2D)           (None, 24, 24, 16)        1440      
_________________________________________________________________
batch_normalization_50 (Batc (None, 24, 24, 16)        64        
_________________________________________________________________
conv2d_67 (Conv2D)           (None, 22, 22, 16)        2304      
_________________________________________________________________
batch_normalization_51 (Batc (None, 22, 22, 16)        64        
_________________________________________________________________
dropout_17 (Dropout)         (None, 22, 22, 16)        0         
_________________________________________________________________
max_pooling2d_9 (MaxPooling2 (None, 11, 11, 16)        0         
_________________________________________________________________
conv2d_68 (Conv2D)           (None, 11, 11, 10)        160       
_________________________________________________________________
batch_normalization_52 (Batc (None, 11, 11, 10)        40        
_________________________________________________________________
conv2d_69 (Conv2D)           (None, 9, 9, 16)          1440      
_________________________________________________________________
batch_normalization_53 (Batc (None, 9, 9, 16)          64        
_________________________________________________________________
conv2d_70 (Conv2D)           (None, 7, 7, 16)          2304      
_________________________________________________________________
batch_normalization_54 (Batc (None, 7, 7, 16)          64        
_________________________________________________________________
dropout_18 (Dropout)         (None, 7, 7, 16)          0         
_________________________________________________________________
conv2d_71 (Conv2D)           (None, 7, 7, 10)          160       
_________________________________________________________________
conv2d_72 (Conv2D)           (None, 1, 1, 10)          4900      
_________________________________________________________________
flatten_9 (Flatten)          (None, 10)                0         
_________________________________________________________________
activation_9 (Activation)    (None, 10)                0         
=================================================================
Total params: 13,134
Trainable params: 12,966
Non-trainable params: 168
_________________________________________________________________
```

Epocs

```
Train on 60000 samples, validate on 10000 samples
Epoch 1/10

Epoch 00001: LearningRateScheduler setting learning rate to 0.0001.
60000/60000 [==============================] - 5s 91us/step - loss: 0.0077 - acc: 0.9974 - val_loss: 0.0196 - val_acc: 0.9939
Epoch 2/10

Epoch 00002: LearningRateScheduler setting learning rate to 7.5815e-05.
60000/60000 [==============================] - 5s 91us/step - loss: 0.0077 - acc: 0.9976 - val_loss: 0.0202 - val_acc: 0.9941
Epoch 3/10

Epoch 00003: LearningRateScheduler setting learning rate to 6.10501e-05.
60000/60000 [==============================] - 5s 92us/step - loss: 0.0078 - acc: 0.9976 - val_loss: 0.0201 - val_acc: 0.9940
Epoch 4/10

Epoch 00004: LearningRateScheduler setting learning rate to 5.10986e-05.
60000/60000 [==============================] - 5s 91us/step - loss: 0.0077 - acc: 0.9973 - val_loss: 0.0199 - val_acc: 0.9939
Epoch 5/10

Epoch 00005: LearningRateScheduler setting learning rate to 4.39367e-05.
60000/60000 [==============================] - 5s 91us/step - loss: 0.0072 - acc: 0.9976 - val_loss: 0.0196 - val_acc: 0.9938
Epoch 6/10

Epoch 00006: LearningRateScheduler setting learning rate to 3.85356e-05.
60000/60000 [==============================] - 6s 92us/step - loss: 0.0074 - acc: 0.9977 - val_loss: 0.0198 - val_acc: 0.9939
Epoch 7/10

Epoch 00007: LearningRateScheduler setting learning rate to 3.43171e-05.
60000/60000 [==============================] - 5s 91us/step - loss: 0.0069 - acc: 0.9977 - val_loss: 0.0198 - val_acc: 0.9940
Epoch 8/10

Epoch 00008: LearningRateScheduler setting learning rate to 3.0931e-05.
60000/60000 [==============================] - 5s 91us/step - loss: 0.0073 - acc: 0.9975 - val_loss: 0.0202 - val_acc: 0.9939
Epoch 9/10

Epoch 00009: LearningRateScheduler setting learning rate to 2.81532e-05.
60000/60000 [==============================] - 5s 90us/step - loss: 0.0070 - acc: 0.9978 - val_loss: 0.0199 - val_acc: 0.9943
Epoch 10/10

Epoch 00010: LearningRateScheduler setting learning rate to 2.58331e-05.
60000/60000 [==============================] - 5s 91us/step - loss: 0.0071 - acc: 0.9976 - val_loss: 0.0194 - val_acc: 0.9944
<keras.callbacks.History at 0x7f835042a940>
```

Accuracy
```
[0.019447231261333218, 0.9944]
```
