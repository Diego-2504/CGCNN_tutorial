# Tutorial-for-CGCNN
In the following notebooks I describe the model from 
__[Crystal Graph Convolutional Neural Networks](https://arxiv.org/abs/1710.10324)__ 
by __[Tian Xie](https://github.com/txie-93)__ who was advised by __[ Prof. Jeffrey Grossman](https://dmse.mit.edu/people/jeffrey-c-grossman)__.


If you want to run the jupyter notebooks you should install Anaconda and run the following command line to create the appropriate environment:

```conda create -n cgcnn_tutorial python=3 scikit-learn networkx nglview jupyter pytorch-lightning ase pytorch torchvision pymatgen -c pytorch -c conda-forge```

To activate the environment:

```conda activate cgcnn```

The notebooks are sequenced, in the following order of appearance:
> 1. Crystal_graphs
> 2. Features
> 3. Load_data
> 4. Load_targets
> 5. Pl_model

## Notebooks overview

### 1. Crystal_graphs
This jupyter notebook includes most of the scripts that come in the repository, that's why I divided it into 3 parts:

> #### 1.1 Data analysis
> In this part of the notebook I explain the way they read the cif files from the crystals.
> Afterwards I give an exhaustive explanation of the construction of graphs from the crystal.

> #### 1.2 Batches
> In this part of the notebook I explain how to create the batches that 
> will be passed as input to the model.

> #### 1.3 Model
> In this part of the notebook I describe the convolutions in the graphs and then the model in general.
> Finally I perform a small training of material classification (whether it is metal or semiconductor) to test the model.


### 2. Features
In this jupyter notebook I explain which features are going to be attributed to the nodes and edges of the crystal > > graphs.

### 3. Load_data
In order to load the data and create the cif files, I use an interface to the Materials
Project with pymatgen called MPRester, in the jupyter notebook I explain how to use it.

### 4. Load targets
In the same way I explain how to use the interface to load the properties to be predicted from the model.

### 5. Pl_model
In this jupyter notebook I explain how Pytorch-Lightning can be used to facilitate the training code.
in order to train the model directly on gpu (for those who do not have gpu it is possible to change the model configuration to cpu). If you wish to visualize
the training with tensorboard, you should install the package first, run the training and then execute the following command line in the terminal:

```tensorboard -logdir CGCNN```

You can find the original code here __[CGCNN code](https://github.com/txie-93/cgcnn)__.
