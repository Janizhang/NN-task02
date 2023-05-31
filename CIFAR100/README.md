## <div align="center">Introduction</div>
This project is about experimenting data augmentation methods, Cutout, Mixup and CutMix. 

## <div align="center">Dataset</div>
In this experiment, we choose CIFAR-100 dataset to experiment on. It contains 50,000 natural images in the training dataset while 10,000 for testing. Each of them is of size 32 x 32, categorized in one of the 100 classes.

## <div align="center">A Quick Start</div>
Here we offer a notebook to play around. In Colab we implement with PyTorch. The training is light as a simple illustration of how things work. Make sure to run the notebook in GPU environment!(Owing to my macOS, I use $mps$ in macOS as my GPU to run, so if you wanna run the code, please change the relative codes, thank you!)
  
## <div align="center">Training</div>
To start with, you need to get access to our files. You can try either

```bash
git clone https://github.com/Janizhang/NN-task02.git
cd NN-task02/CIFAR100
```
or download project as a zip and unzip it locally and turn to "CIFAR100" directory. 
 
 <br>
 
 <h2>PyTorch</h2>
 <h3>Dependencies </h3>
 
Python 3.x
 
1. pytorch + cuda
3. tensorboard == 2.9.0
4. tqdm
5. PIL
6. numpy 
 
 <h3>Configuration</h3>
 
 Open **configs.py** and configure the paths, CUDAs, training parameters, etc.
 
 <h3>Train</h3>
 
Run **train_torch.py**, or
 
 ```bash
python train_torch.py
 ```
 
## <div align="center">Testing</div>
We have prepared **test.py** for one to easily test a ResNet-18 model trained on 224 x 224 images on CIFAR-100! Just type in 

```bash
python test.py
 ```
 
or manually execute the file, and the program will ask for inputting the path to your model. Both **.pdparams** and **.pth** files are supported. Then, it will ask for the index of cuda to run your model on (the process will be omitted if no cuda is available). 
 
 Here we also offer my already-trained model for testing,
 
* [PyTorch Model](https://pan.baidu.com/s/1vAR7omUT1Z_CNc6jzEeR0Q)
extracting password: **xiqp**

 Lastly, wait for a few seconds to obtain the result! (Maybe a few minutes if CIFAR-100 dataset needs to be downloaded.)

 
## <div align="center">Data Preparation</div>

We place this part in the final because this is NOT a must-do. The program will automatically fetch the CIFAR-100 dataset if you do not have any.
 
However,  if you are struck with the automatic download of the CIFAR-100 dataset (i.e. bad network connection), or you want to use a already-existed CIFAR-100 file,  this part might be helpful. The dataset can be accessed elsewhere, for example at [CIFAR](http://www.cs.toronto.edu/~kriz/cifar-100-python.tar.gz).
 
Open the **configs.py** and customize the ``data_file``. If you are working with PyTorch, set `data_file` to the folder that contains **cifar-100-python.tar.gz**.
 
 Leave `data_file   = None` as default and for automatic downloads.
