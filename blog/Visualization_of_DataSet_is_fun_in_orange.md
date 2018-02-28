# Visualizing Data Set is fun using Orange

### Introduction:

Data has become powerful source of earning and predict future  and people will seek to utilize it even if they don’t know exactly how. Machine learning will become a usual part of programmer’s resume, data scientists will be as common as accountants. Now a days and for the next approximately two decades, we will continue to see a major need for machine learning and data science specialists to help apply machine learning technologies to application areas where they aren't applied today.

Now a day people prefer GUI based tools instead of more coding stuffs . Orange is one of the popular open source machine learning and data visualization tool for beginners. People who don’t know more about coding and willing to visualize pattern and other stuffs can easily work with Orange.

### Why Orange:

Orange is an open-source software package released under GPL  that powers Python scripts with its rich compilation of mining and machine learning algorithms for data pre-processing, classification, modelling, regression, clustering and other miscellaneous functions. 

Orange also comes with a visual programming environment and its workbench consists of tools for importing data, and dragging and dropping widgets and links to connect different widgets for completing the workflow.

Orange uses common Python open-source libraries for scientific computing, such as numpy, scipy and scikit-learn, while its graphical user interface operates within the cross-platform Qt framework. 
            

### Getting Started:

#### Download Orange 

=> Go to [https://orange.biolab.si](https://orange.biolab.si) and click on Download.

##### For Linux Users: 

###### Anaconda

If you are using python provided by Anaconda distribution, you are almost ready to go . If not, follow these steps to download Orange :

> conda config --add channels conda-forge

and run

> conda install orange3

> conda install -c defaults pyqt=5 qt

###### PIP

Orange can also be installed from the Python Package Index. You may need additional system packages provided by your distribution.

> pip install orange3

Run short code to verify you setup Orange successfully. Open your Python Terminal and run the following code :

```
>>> import Orange
>>> Orange.version.version
'3.2.dev0+8907f35'
>>>
```

**Note:**  If You find result shown above then you successfully setup Orange. In case you get error like this :

```
from Orange.data import _variable
ImportError: cannot import name '_variable'
```

**Kindly Follow These Steps :** [Install Orange From Source](https://github.com/biolab/orange3/wiki/Installation-on-OSX-Yosemite) 

Mac and Windows user can easy setup orange in their system step by step just follow official docs of Orange:

[Official docs for setup Orange](http://biolab.github.io/datafusion-installation-guide/)

After installation let's start working with Orange

### Visualization of Data Set in Orange:

A primary goal of data visualization is to communicate information clearly and efficiently via statistical graphics, plots and information graphics. 

> Main goal of data visualization is to communicate information clearly and effectively through graphical means. It doesn't mean that data visualization needs to look boring to be functional or extremely sophisticated to look beautiful. To convey ideas effectively, both aesthetic form and functionality need to go hand in hand, providing insights into a rather sparse and complex data set by communicating its key-aspects in a more intuitive way. Yet designers often fail to achieve a balance between form and function, creating gorgeous data visualizations which fail to serve their main purpose — to communicate information.”

                                                    -Friedman (2008) 

Open Orange on your system & create your own new Workflow named as test as shown in image below:



In this tutorial we are going to learn Visualization of Data Set in few steps as given below:

Step 1: Without data there is no existence of Machine Learning. So In our first step we import our data set in this tutorial I uses example data set available in Orange Directory.
We import zoo.tab data set in file widget:

[Image]

Step 2: In next step we need data tables to viewing our data set. For this we use Data Table widget.

[Image]

Step 3: This is the last step where we will understand our data, with the help of visualization. Orange make visualization pretty much easier. We just add one more widget and choose in which format we would like to visualize our data like Scatter Plot.

[Image]



