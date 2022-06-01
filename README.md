## X - Gradio interface 📱

Discover Gradio, a tool to create interfaces for your artificial intelligence applications.

You will:
- Automatic download your dataset
- Save and load your weights of your model
- Display your accuracy and loss
- Create a Gradio interface
- Use different Gradio interfaces
- Share your app on the Gradio platform

## Workspace

For this workshop you will not use a jupyter notebook. You will create your own application.
You will follow this architecture to start and then you are free to change it to make your application grow.

```
Folder: gradio_app

├── my_app.py
│   dataset/
│   └── (Empty folder)
│   weights/
│   └── (Empty folder)
```

## Dataset (CHANGE THE DATASET AND ADD CLASSES)

In this workshop you will use the [MNIST dataset](https://www.kaggle.com/c/digit-recognizer).

## Step 0: Initialization

All the required information to install the workshop's dependencies are given in the [SETUP.md](./SETUP.md)

## Step 1: Class app

Create a class called `app` that will be the main class of your application.

In the class `app` you will add the following attributes:
- `model`: the model of your application
- `epoch`: the number of epochs
- `batch_size`: the batch size
- `learning_rate`: the learning rate
- `classes`: the list of classes

## Step 2: Add the dataset

- In your class app create an attribute `train_loader` and an attribute `test_loader` that will contain the dataset.
- In your class app you will create an attribute `classes` that will contain the classes of your dataset.
- Create a method called `add_dataset` that will return a dataloader.

The `add_dataset` method will receive a `dataset_name`, `dataset_path` and if you want a train set or test set.

## Step 2.5: Check if the dataset is already downloaded

In your method `add_dataset` you will check if the dataset is already downloaded.
If it is downloaded, check if the dataset is correct.

## Step 3: Create the model

Create a class called `model` that will contain the model of your application.

In your init method of the class `model` you will add the following attributes:
- `conv1`: the first convolutional layer
- `pool`: the pooling layer
- `conv2`: the second convolutional layer
- `linear1`: the first linear layer
- `linear2`: the second linear layer
- `linear3`: the third linear layer

Create a forward method that will receive the input of your model and use the model variables.

## Step 4: Implement the training

Create a method called `train` that will train your model.

In the method `train` you will:
- Create a loss function
- Create a optimizer
- Keep track of the loss and accuracy
- Create a loop to train the model

## Step 5: Display the loss and accuracy

Use Matplotlib for this step.

In one figure you will display the loss and accuracy of the training.


## Step 6: Save the weights

After your training, you will save the weights of your model in the `weights` folder.

## Step 7: Predict an image

Create a method named `predict_image` that will predict an image.
This method will receive an image and return the prediction.
The prediction is an element of the `classes` attribute.

## Step 8: Create the Gradio interface

Create a gradio interface with for inputs an image.

For this, you need a function called `execute_predict` (You will create this function in the next step) that will receive an image and return the prediction.

## Step 9: Take image, reformat it and predict it

In this step you will create a function called `execute_predict` that will receive an image and return the prediction.

In reality your image is a numpy array.

## Step 9.1: Reformat the image

You must create a function called `reformat_image` that will reformat the image.

For this function you must proceed as follows:
- Convert your numpy array to a tensor image
- Resize the image to 32x32 (Size of images in the dataset)
- Reformat your image with a composed transformation (A composition of a resize and a conversion to tensor)

## Step 9.2: Normalize the image

You must create a function called `normalize_image` that will normalize the image.

For normalize an image with a Normalize function you need to use the following parameters:
- Mean
- Std

To calculate the mean and std of the dataset you need to create a function with the following process:
- Create a variable called `channels_sum`, `channels_squared_sum` and `batch_num`
- Create a loop that will iterate over the dataset
  - Add to `channels_sum` the result of a function `mean` (the dimension for this is [0,2,3])
  - Add to `channels_squared_sum` the result of a function `mean` (the dimension for this is [0,2,3]), don't forget to square the data before sending it to the function `mean`
  - Add 1 to `batch_num`
- Set `mean` variable to the result of `channels_sum` divided by `batch_num`
- Set `std` variable to this equation: `std = sqrt(E[X^2] - (E[X])^2)`
- Return the mean and std

## Step 9.3: Execute the prediction

With the last step, you are a tensor image, you need to convert this to a float image.

Now you have all tools to predict an image.

Use your `predict` function for return the prediction.

## Step 10: Share your app on the Gradio platform

With Gradio you can share your application. This is integrated in the Gradio interface. Check the [Gradio documentation](https://docs.gradio.org/en/latest/).

Share your app with your friends and test it.

## Step 11: Keep smiling 😃

You have finished the workshop.

Don't forget to share your code on the Github Classroom repository.


## Writer

| [<img src="https://github.com/LayBraid.png?size=85" width=85><br><sub>Clément Loeuillet</sub>](https://github.com/laybraid) |
|:---------------------------------------------------------------------------------------------------------------------------:|

<h2 align=center>
Organization
</h2>
<br/>
<p align='center'>
    <a href="https://www.linkedin.com/company/pocinnovation/mycompany/">
        <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white">
    </a>
    <a href="https://www.instagram.com/pocinnovation/">
        <img src="https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white">
    </a>
    <a href="https://twitter.com/PoCInnovation">
        <img src="https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white">
    </a>
    <a href="https://discord.com/invite/Yqq2ADGDS7">
        <img src="https://img.shields.io/badge/Discord-7289DA?style=for-the-badge&logo=discord&logoColor=white">
    </a>
</p>
<p align=center>
    <a href="https://www.poc-innovation.fr/">
        <img src="https://img.shields.io/badge/WebSite-1a2b6d?style=for-the-badge&logo=GitHub Sponsors&logoColor=white">
    </a>
</p>

> :rocket: Don't hesitate to follow us on our different networks, and put a star 🌟 on `PoC's` repositories.