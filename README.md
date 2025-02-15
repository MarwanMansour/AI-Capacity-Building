# AI-Capacity-Building
The AI capacity building project is a project that aims to develop a sandbox for students to use when they are developing their machine learning projects.

# Use cases:
1.	Accident Severity Classification: a machine learning project that labels the accident severity from 1- 4 (inclusive) and provides analysis of the data. Data format is a csv file
2.	Smart Cities Sentiment Analysis: an NLP project in which Arabic tweets discussing smart cities are classified either positive, negative, or neutral. Data format is a tsv file.
3.	Accident Detection: a computer vision project that performs image classification. The images are split into labeled folders, and a CNN is used to classify the input images.
# Additional files:
1.	A hands-on example of how to use MLFlow with TensorFlow
2.	A hands-on example of how to use MLFLow with PyTorch

# Tech Stack:
The covered libraries are: NumPy, pandas, matplotlib, scipy, sklearn, seaborn, TensorFlow, PyTorch, MLFlow, xgboost, nltk.

# Prerequisites:
-	Installation of docker desktop from https://www.docker.com/products/docker-desktop/
-	You can find docker images in the following link: https://hub.docker.com/u/aicapacitybuilding
-  Pull the images using the following commands: 
   - docker pull aicapacitybuilding/torch_env:1.0 --> for the torch image
   - docker pull aicapacitybuilding/tensorflow_env:1.0 --> for the tensorflow image
-  If you're building the docker image from this repository's Dockerfiles instead of pulling it from DockerHub, you can build the image using the following commands:
   -  For the image containing both tensorflow and pytorch: docker build -t ml_env:1.0 .
   -  For the image containing pytorch only: docker build -f torch.Dockerfile -t torch_env:1.0 .
   -  For the image containing tensorflow only: docker build -f tensorflow.Dockerfile -t tensorflow_env:1.0 .
-	Run the image:
docker container run -it -p 5000:5000 {imageID} <br /> 
or <br /> 
docker container run -it -p 5000:5000 container_name <br /> 
Example: docker container run -it -p 5000:5000 tensorflow_env:1.0


# Running the use cases

# Using MLFlow 
  To open MLFlow user interface and view the runs output (make sure your code uses mlflow and logs the parameters you want to see - US accidents doesn't use mlflow)
  1. Open a terminal in your project
  2. Execute:  mlflow ui --host 0.0.0.0
  3. In your browser open : http://0.0.0.0:5000  (mlflow uses port 5000 on the host)
  4. If your experiment has a name (example : experiment_name = "MNIST_Classification"), it will create a folder with the same name in mlflow ui, open that folder to view the runs
     
# Integrating with VSCode (Optional)
  1. Install VSCode from : https://code.visualstudio.com/Download
  2. Installation of 2 extensions in VSCode: Docker, and Remote – Containers
  
  ![Docker extension](Documentation/Pictures%20used%20in%20documentation/Fig4%20-%20Docker%20extension.png)
  ![remote - containers extension](Documentation/Pictures%20used%20in%20documentation/Fig5%20-%20Dev%20Containers%20extension.png)
   3. If you haven't run the image yet, in your vscode terminal execute: docker container run -p 5000:5000 ml_env:2.0
  
 4. In VSCode, go to the docker icon present in the left
  
  ![Icon](Documentation/Pictures%20used%20in%20documentation/Fig6%20-%20Docker%20Icon.png)
  
  5. Under containers -> choose the running container (ml_env:2.0) -> right click -> choose 'Attach Visual Studio Code'.
  6. A newly opened VSCode will appear, install Jupyter & Python extensions (press install in container)
  7. Press open folder
  8. You can either choose a usecase to run, or open root folder (folder containing all usecases) by just pressing ok
  9. You can now use VSCode to develop inside the container
  10. To run your code, open a terminal inside the example folder and type : python (python file name)

    Example : python mlflow_torch_example.py
  11. To open MLFlow user interface
       1. Right click on the usecase folder
       2. Choose open in integrated terminal 
       3. Execute MLFlow commands mentioned above

