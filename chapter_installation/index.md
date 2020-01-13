# Installation
:label:`chap_installation`

In order to get you up and running for hands-on learning experience,
we need to set you up with an environment for running Python,
Jupyter notebooks, the relevant libraries,
and the code needed to run the book itself.

## Installing Miniconda

The simplest way to get going will be to install
[Miniconda](https://conda.io/en/latest/miniconda.html). The Python 3.x version
is recommended. You can skip the following steps if conda has already been installed.
Download the corresponding Miniconda sh file from the website
and then execute the installation from the command line
using `sh <FILENAME> -b`. For macOS users:

```bash
# The file name is subject to changes
sh Miniconda3-latest-MacOSX-x86_64.sh -b
```


For Linux users:

```bash
# The file name is subject to changes
sh Miniconda3-latest-Linux-x86_64.sh -b
```


Next, initialize the shell so we can run `conda` directly.

```bash
~/miniconda3/bin/conda init
```


Now close and re-open your current shell. You should be able to create a new
environment as following:

```bash
conda create --name d2l -y
```


## Downloading the D2L Notebooks

Next, we need to download the code of this book. You can use the
[link](https://github.com/ahmaurya/d2l-en/archive/master.zip) to download and unzip the code.
Alternatively, if you have `git` (otherwise run `sudo apt install git-all`) available:

```bash
git clone https://github.com/ahmaurya/d2l-en/
```


Now we will want to activate the `d2l` environment and install `pip`.
Enter `y` for the queries that follow this command.

```bash
conda activate d2l
conda install python=3.7 pip -y
```


## Installing TensorFlow and the `d2l` Package

Before installing TensorFlow, please first check
whether or not you have proper GPUs on your machine
(the GPUs that power the display on a standard laptop
do not count for our purposes).
That will be more than enough CPU horsepower to get you
through the first few chapters but you will want
to access GPUs before running larger models.

```bash
# Current stable release for CPU and GPU
pip install tensorflow
```


We also install the `d2l-tf` package that encapsulates frequently used
functions and classes in this book.

```bash
pip install d2l-tf
```


Once they are installed, we now open the Jupyter notebook by running:

```bash
jupyter notebook
```


At this point, you can open http://localhost:8888 (it usually opens automatically) in your Web browser. Then we can run the code for each section of the book.
Please always execute `conda activate d2l` to activate the runtime environment
before running the code of the book or updating TensorFlow or the `d2l` package.
To exit the environment, run `conda deactivate`.


## Upgrading to a New Version

Both this book and TensorFlow are keeping improving. Please check a new version from time to time.

1. The URL https://github.com/ahmaurya/d2l-en/ always points to the latest contents.
2. Please upgrade the `d2l-tf` package by `pip install d2l-tf --upgrade`.
3. For the unstable preview build released nightly, use `pip install -U tf-nightly`.


## GPU Support

:label:`subsec_gpu`

Since the 1.15 release, CPU and GPU support are included in a single TensorFlow package.

```bash
# Current stable release for CPU and GPU
pip install tensorflow
```

For releases 1.14 and older, TensorFlow had separate CPU and GPU packages. You can install them
with one of the following command:

```bash
pip install tensorflow==1.14      # CPU
pip install tensorflow-gpu==1.14  # GPU
```


TensorFlow can be upgraded by
`pip install -U --pre tensorflow`.
You can find all available TensorFlow versions via `pip search tensorflow`.


## Exercises

1. Download the code for the book and install the runtime environment.
