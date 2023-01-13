## Iris Prediction using FastAPI and Docker

This assessment is the machine learning engineer role for sourcefuse and uses models (KNN, Logistic Regression, SVM and Random Forest) trained on the iris dataset to make predictions using FastAPI and Docker. Thought this assessment uses Docker, it is possible to try it without Docker using the following command
```
uvicorn main:app --reload making
```
Make sure that the command prompt directory is set to the folder containing the `main.py` file.

## Building The Image(s)
In order to build the images make sure that the directory is set to the respective folders, i.e. `no-batch` and `with-batch`. Then use the following command to build the image
```
docker build iris:sourcefuse .
```

## Run the container
Once the image has been built next step is to run the image. This can be done using the following command :
```
docker run --rm -p 80:80 iris:sourcefuse
```
Once the container is running,  go to  [localhost:80](http://localhost:80) to see the if the server is working or not. If it is running a message will be displayed

## Making Server Requests
The `POST` method is used to make requests for predictions. Every request should contain the data that represents a wine in `JSON` format like below :

### For no-batch
```
{
  "sepal_length":12.6,
  "sepal_width":1.34,
  "petal_length":1.9,
  "petal_width":18.5
}
```
