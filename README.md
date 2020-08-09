# NeuralNetwork

## Background

### Purpose
This project was focused on taking an example dataset of charities that included a key fact along with a final evaluation that they were successful or not.  The objective of the challenge was then to apply machine learning and neural network models to predict the likelihood that a charity would be successful based on the input data.  Given the size of the provided dataset it could support either a supervised machine learning model or a neural network.  To evaluate this dataset, I chose a Random Forest model for the machine learning and a deep learning model for the neural network.

### Results
For the Random Forest model, it was necessary to evaluate how many estimators to use.  I evaluated a range from 50 to 350 at increments of 50.  After reviewing the results, it was determined that 100 estimators resulted in the best results with the fewest estimators.  Based on that number of estimators the accuracy score was 0.690379 or 69%.  While this is a reasonable result it is important to contrast this with the neural network model.

For the neural network, I have seen that for multiple inputs with limited linearity to the data it is important to use two hidden layers.  To start the process each layer was using the relu activation function.  The recommendation was to use two or three times the number of inputs for the first layer and a reduced number in the second hidden layer.  I tested many different options here and found that 1.5 X the number of inputs and 12 neurons for the second layer resulted in the best accuracy and loss.  I also increased the number of epochs to 100 and saw very little improvement after epoch 95.  Unfortunately, even after those adjustments the accuracy of the model was 71% which was not the target 75%.  Further refinements needed to be explored.

The next steps to increase the model's performance was to reduce the number of inputs.  I removed status, application type, and special considerations inputs from the evaluation based on the observation that there was not a lot of unique data being contributed from those inputs.  Reevaluating the Random Forest model resulted the accuracy going down slightly to 68.6%.  The neural network was not as negatively affected and still resulted in a 71% accuracy.

The last step I attempted was to change the activation function being applied to the neural network.  I tried several options including softmax, softplus, softsign.  I also tried different combinations on the first and second layer.  Based on that analysis that relu was consistently the best performer on the second layer and softmax on the first layer resulted in a very small improvement in accuracy. However, ultimately it kept the accuracy at 71%.

### Next Steps
Given enough time and because we have still not achieved the 75% accuracy objective it would be good to evaluate each type of machine learning model (such as SVM) and neural network combination to determine if we can achieve a better result with a different model.  The important thing to note is that there are numerous models and they all have their strengths and weaknesses.  Given the different types of inputs available in this dataset, it is hard to determine which model would be the best fit without taking a more comprehensive survey of the available models.



## Resources
- Data Source: charity_data.csv

- Software:  Python 3.7.7, Jupyter Notebook 6.0.3
    - Python Modules: numpy, pandas, sklearn, tensorflow