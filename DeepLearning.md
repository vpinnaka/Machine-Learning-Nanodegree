
# Deep Learning

### Neural networks in Keras
Sample neural network build with keras, input hidden layer has 32 nodes followed by activation, fully connected layer. Category Cross Entropy is defiend as loss function for the model with accuracy as metric. Total no. od training ephos is 1000.
```python
    import numpy as np
    from keras.models import Sequential
    from keras.layers.core import Dense, Activation
    # X has shape (num_rows, num_cols), where the training data are stored
    # as row vectors
    X = np.array([[0, 0], [0, 1], [1, 0], [1, 1]], dtype=np.float32)
    # y must have an output vector for each input vector
    y = np.array([[0], [0], [0], [1]], dtype=np.float32)
    # Create the Sequential model
    model = Sequential()
    # 1st Layer - Add an input layer of 32 nodes with the same input shape as
    # the training samples in X
    model.add(Dense(32, input_dim=X.shape[1]))
    # Add a softmax activation layer
    model.add(Activation('softmax'))
    # 2nd Layer - Add a fully connected output layer
    model.add(Dense(1))
    # Add a sigmoid activation layer
    model.add(Activation('sigmoid')
    # After building compile the model with the backend(tensolflow, thenano etc.)
    model.compile(loss="categorical_crossentropy", optimizer="adam", metrics = ["accuracy"])
    # Summary of the model
    model.summary()
    # training the model with no. of epochs and message level
    model.fit(X, y, nb_epoch=1000, verbose=0)
    # evalucate the model with accuarcy metric defiend in compile step
    model.evaluate()
```
