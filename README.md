
Copenhagen 2018 Summer School QuantEcon Workshop
--------------------------------------------------

Instructors: John Stachurski and Natasha Watkins

Homepage: https://quantecon.org/copenhagen-summer-school-2018

[![Binder](https://mybinder.org/badge.svg)](https://mybinder.org/v2/gh/QuantEcon/Copenhagen_workshop_2018/master)


**Schedule**

* 9:00 - 10:30: Introduction to QuantEcon, Jupyter notebooks, and Python
* 10:45 - 12:15: Python for data handling, analysis, and visualisation, numerical techniques
* 12:15 - 13:15: Lunch
* 13:15 - 14:45: Intro to Numba
* 15:00 - 16:30: Dynamic programming applications with Numba and parallelization
* 16:45 - 18:15: Computer lab/office hours




### Links:

* [Anaconda](https://www.anaconda.com/)
* [AWS](https://aws.amazon.com/)
* [Accessing AWS via SSH](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstancesLinux.html)


### Notes on AWS


#### To get an instance running

1. Login to Amazon AWS Console 
2. Navigate to EC2 Service
3. Choose your region for setting up an instance
6. Create security key-pair for the region if you don't have one
4. Launch & Configure an instance and choose Ubuntu 64-bit
5. enable access through Port 8000 (in addition to Port 22 for ssh)
6. Choose security key you've set up

#### Connecting and set up 

Use `ssh -i /path/to/pem-key ubuntu@hostname`

Here `hostname` is your Public DNS, as shown in the instance information from AWS console

Now run `sudo apt-get update` so you can install things you might need using `apt-get`


#### Configure instance to run Jupyter

1. ssh into the running instance using IP from AWS Console
2. Install Anaconda using wget and the latest download link for python36
3. Run: jupyter notebook --generate-config
4. For Automatic Password Setup run: jupyter notebook password
5. Edit .jupyter/jupyter_notebook_config.py and set the following

```
# Set ip to '*' to bind on all interfaces (ips) for the public server
c.NotebookApp.ip = '*'
c.NotebookApp.open_browser = False
c.NotebookApp.port = 8000
```


