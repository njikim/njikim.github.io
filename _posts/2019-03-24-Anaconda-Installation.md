---
layout: post
title: "Anaconda path and Environment Variables"
description: "Anaconda installation and setting the path and environment variables"
date: 2019-03-24
tags: [Python, Anaconda, Jupyter notebook]
category: Python
comments: true
share: true
---

## Anaconda Installation
Before we start, you need to install Anaconda program based on your OS specification. 
<https://www.anaconda.com/distribution/>
Note: you don't need to change anything while downloading the program. Just check/click everything as default!

## Setting Anaconda Path
1. Anaconda3 is nicely installed under C:/Users/(your username) folder unless you've change anything during the installation process.

2. Go to C:/Users/(your username)/Anaconda3, check the file 'python.exe' and make sure you did install Anaconda properly.
Note: 'exe' means the user interface extension that brings up dos prompt on window.

3. Click the 'Start' button, type 'cmd' and open 'Command Prompt'. 
Let's see the example below. It is possible to execute the notepad program from cmd since the path of 'notepad.exe' is set already. However, we didn't yet set the path of the python yet. 

	  <img src="https://user-images.githubusercontent.com/46670511/54874181-459c2f00-4e29-11e9-8f2f-01e2789a4ec9.PNG" width="500" />
	
	  Change the path to where the python is installed and run python.exe. 
	
	  <img src="https://user-images.githubusercontent.com/46670511/54874204-b93e3c00-4e29-11e9-8243-4f7ef4093dd3.PNG" width="500" />
  
    In order to make life easier, we are going to save two types of path.
    
4. Go to Control Panel -> System and Security -> System -> click 'Advanced system settings'.

	  <img src="https://user-images.githubusercontent.com/46670511/54874212-ed196180-4e29-11e9-8663-50c3a9366cf0.png" width="500" /> 
  
	  Next, click 'Environment Variables' and double click 'Path' under 'System variables'. 
  
	  <img src="https://user-images.githubusercontent.com/46670511/54874221-10441100-4e2a-11e9-83e8-fe6c873a4c51.png" width="500" />
	  <br>
	  <img src="https://user-images.githubusercontent.com/46670511/54874227-32d62a00-4e2a-11e9-8799-dce452886053.PNG" width="500" />
  
	  Then, Add these three paths as the picture below.  
	  Note: do not change anything above!

	  <img src="https://user-images.githubusercontent.com/46670511/54874233-4c777180-4e2a-11e9-8eaa-5976770a38d8.PNG" width="500" />
  	
	Now the programs under these paths can be run anywhere! (which means you can run python from any path) We are going to use lots of programs under Script and Library/bin in the near future. So it's useful to set these paths as well.
	
		C:/Users/(본인 username)/Anaconda3
		C:/Users/(본인 username)/Anaconda3/Scripts
		C:/Users/(본인 username)/Anaconda3/Library/bin

	Example:
	Running conda.exe that is under /Anaconda3/Scripts gives me an error.
  
	  <img src="https://user-images.githubusercontent.com/46670511/54874262-e2ab9780-4e2a-11e9-8241-661080dbf07f.PNG" width="500" />
  
	  After setting the path, it runs well without an error in a same path.
	  
	  <img src="https://user-images.githubusercontent.com/46670511/54874265-f525d100-4e2a-11e9-956e-08361e17fc40.PNG" width="500" />


## Setting Jupyter Notebook Path 
You are finally ready to use jupyter notebook as you have downloaded Anaconda. 
Setting the path and environment variables is a must thing to do here as well to run jupyter notebook and save the files from the path you want.
As an example, I would like to run jupyter notebook and save all the files related to python study under C:/Python from now on.
So let's get started with my example!

1. Start -> Anaconda3 -> put the cursor on Jupyter notebook and click right button -> More -> Open file location 
  Click right button on Jupyter notebook -> Properties

	  <img src="https://user-images.githubusercontent.com/46670511/54874356-1c7d9d80-4e2d-11e9-8595-401a7aca8202.png" width="500" />

2. 'USERPROFILE' variable inside the red box contains all the information regarding the path. By deleting "%USERPROFILE%/" this guy, we will delete the default path.

	  <img src ="https://user-images.githubusercontent.com/46670511/54874391-a62d6b00-4e2d-11e9-83e8-7c08ae500efb.png" width="500" />

3. Next, start -> Anaconda3 -> open Anaconda prompt  &
  write the command 'Jupyter notebook –-generate-config' and observe that the file is created under .jupyter/.
	
    <img src="https://user-images.githubusercontent.com/46670511/54874465-1dafca00-4e2f-11e9-9ac8-896c37b468a1.PNG" width="500" />

4. Open jupyter_notebook_config.py file with notepad++ and delete the comment below and write the default path you want to run jupyter notebook.

	<img src="https://user-images.githubusercontent.com/46670511/54874491-aa5a8800-4e2f-11e9-8312-a50c37acc28b.PNG" width="500" />

5. Once you run jupyter notebook (from any path), it will now run and save the files from the path you have set.

## JDK Installation & Setting the Environment Variables
Some of the Machine Learning/Deep Learning programs that we are going to use in Python is based on Java. Therefore, we better install JDK now to run those programs later.

### JDK Installation
Install JDK by clicking this URL <www.oracle.com> -> go to 'Java SE Download' and download 'JavaSE version 8'.
Since the latest version might not be compatible with some programs just download version 8 to be safe. 
After clicking JDK, accept the license agreement and download the file!

<img src="https://user-images.githubusercontent.com/46670511/54874585-a92a5a80-4e31-11e9-97da-dbca29238412.png" width="500" />

<img src="https://user-images.githubusercontent.com/46670511/54874626-6a48d480-4e32-11e9-8d93-5c373053abc5.png" width="500" />


### JDK Environment Variables
To inform the programs that we have installed JDK, we need to set the environment variables.

1. Like we did earlier, go to Control Panel -> System and Security -> System -> Advanced system Settings and click Environment Variables

2. Click 'New' under System Variables

4. Name the variable as 'JAVA_HOME'! (don't try to be creative and give another name) and set the path as where the JDK is installed.

	<img src="https://user-images.githubusercontent.com/46670511/54874720-3b336280-4e34-11e9-8621-ed680f1a4e73.PNG" width="500" />

---------------------

### Setting the path & environment variables are super important. So, don't forget to pay attention to this before even getting started with Python! 
