# Clouds-Segmentation-Project

**Project Description:**
The task is semantic segmentation of cloud satellite images. The dataset consists of IR & Visual Grayscale images of clouds
with their corresponding masks.
Each mask consists of 5 classes: Open clouds, Closed clouds, Disorganized clouds, Other clouds and Ocean (no clouds).
The main objective is to be able to separate between Open clouds, Closed clouds and no clouds - so eventually this task is a 3 class semantic segmentation task.
The available architectures are Pytorch's "DeepLabV3-ResNet101" and "Unet" and the number of output classes are 2/3/4/5.

**Directory structure:**
In order to run the available experiments in this project, one requires a specific directory structure:
The main directory must contain:
- All the python files (which can be found in 'python_files' in this repository)
- The data directory (which can be found in 'data' in this repository)
- A directory named 'weights' (will be explained shortly)
- A directory named 'results' (will be explained shortly)


**Running experiments:**
Running an experiment requires several arguments:
- Data directory: Using the directory structure described above, just enter 'data'
- Output directory: When the training process ends, the best model weights and metrics log file will be saved in this directory. If a non-existing directory path is passed, it will be created.
- Epochs: Number of training epochs. (default=50)
- Batch size: Number of batch size. (default=2)
- Number of classes: How many classes we wish to segment. Can be 2/3/4/5. (default=3)
- Using Unet: Are we using Unet architecture or not? Passed as 0 for False and 1 for True (default=False i.e using ResNet)
- Train all – Are we training the entire network or just the last layers? (default=True)

If we wish to run an experiment, we must pass a data directory in the specific structure describe above and an output directory. The rest of the arguments are optional and will take default values unless passed explicitly.

Example (using the command line from the project main directory):
```
python main.py data output --epochs 50 --batchsize 2 --num_classes 5 --using_unet 0 --train_all 1
```

After running this command the training process initiates, which during you will see loss and different metrics statistics.
When the training ends, 2 files named 'weights.pt' and 'log.csv' will appear in your output directory - move 'weights.pt' to your 'weights' directory.


