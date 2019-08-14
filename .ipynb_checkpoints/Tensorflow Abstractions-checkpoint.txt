Some abstractions include
1. Estimator API
2. Keras
3. TF Learn
4. TF-Slim
5. Layers

Most abstractions lie in the tf.contrib package

Best abstractions are
Estimators, Keras (Abstraction of tf and theano), Layers (Halfway on tf.contrib and rest on tf.layers)


1. Estimator API

tf.estimator.*
Contains DNNClassifier(), DNNRegressor() etc
Needs a feature column: tf.feature_column.numeric_column()
Then create a model: tf.estimator.DNNClassifier()
Then an input function: tf.estimator.inputs.numpy/pandas_input_fn(); eval input fn shouldnt be shuffled
Then train: tf.estimator.DNNClassifier.train()
Then predict: tf.estimator.DNNClassifier.predict()


2. Keras API

tf.contrib.keras
1. Make model object: tf.contrib.keras import models; model = models.Sequential()
2. Add the layers you want: tf.contrib.keras.layers; model.add(layers.Dense())
3. Compie the model: model.compile(optimizer, loss, metrics=[]) # all params in strings
4. model.fit()
5. model.predict() for softmax values / model.predict_classes() for class values