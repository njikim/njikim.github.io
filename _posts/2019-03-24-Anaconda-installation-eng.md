---
layout: post
title: "Setting Anaconda path and environment variables"
date: 2019-03-24
tags: [Python, Anaconda, Jupyter notebook]
category: Python
comments: true
share: true
---

## Anaconda installation
Before we start, you can install Anaconda based on your OS specification from this URL! <https://www.anaconda.com/distribution/> 
Note: you don't need to change anything while you are downloading. Just check/click everything as default!

## Setting Anaconda Path
1. If you set your path as default while downloading, you can see that it has downloaded under User folder/your user name folder.

2. if you go to C:/Users/(your username)/Anaconda3, you can check the file ' python.exe'.
Note: 'exe' means the User interface extension that makes it possible to bring up dos prompt on window.

3. Once you click the 'Start' button, type 'cmd' and open 'Command Prompt'.
Let's check the example below. Since the path setting of 'notepad.exe' is done already, it is possible to bring up notepad. However, we didn't yet set the setting of python yet. Therefore, you need to change the path to where it is dowloaded and run it. 

  <img src="https://user-images.githubusercontent.com/46670511/54874181-459c2f00-4e29-11e9-8f2f-01e2789a4ec9.PNG" width="500" />
	
	  By using command 'cd' and 'dir', go to the path where python is downloaded and run python.exe 
	
  <img src="https://user-images.githubusercontent.com/46670511/54874204-b93e3c00-4e29-11e9-8243-4f7ef4093dd3.PNG" width="500" />
  
    In order to make life easier, we are going to save two types of path.
    
4. Go to Control Panel -> System and Security -> System -> click 'Advanced system settings'.

  <img src="https://user-images.githubusercontent.com/46670511/54874212-ed196180-4e29-11e9-8663-50c3a9366cf0.png" width="500" /> 
  
  Next, click 'Environment Variables' and double click 'Path' under 'System variables'. 
  
  <img src="https://user-images.githubusercontent.com/46670511/54874221-10441100-4e2a-11e9-83e8-fe6c873a4c51.png" width="500" />
  <img src="https://user-images.githubusercontent.com/46670511/54874227-32d62a00-4e2a-11e9-8799-dce452886053.PNG" width="500" />
  
  Then, Add these three paths as the picture below. <br>  Note: do not change anything above!

  <img src="https://user-images.githubusercontent.com/46670511/54874233-4c777180-4e2a-11e9-8eaa-5976770a38d8.PNG" width="500" />
  	
	By setting the path, the programs under these path could be run anywhere! (Now you can run python under any path)
  The reason we are setting path of Script and Library/bin is because we are going to use lots of programs under these path.
  
		C:/Users/(본인 username)/Anaconda3
		C:/Users/(본인 username)/Anaconda3/Scripts
		C:/Users/(본인 username)/Anaconda3/Library/bin

	Example:
	Running conda.exe that is under /Anaconda3/Scripts gives me an error.
  
  <img src="https://user-images.githubusercontent.com/46670511/54874262-e2ab9780-4e2a-11e9-8241-661080dbf07f.PNG" width="500" />
  
  But! after setting the path, it runs well without an error in a same path.
  
  <img src="https://user-images.githubusercontent.com/46670511/54874265-f525d100-4e2a-11e9-956e-08361e17fc40.PNG" width="500" />


## Setting for Jupyter notebook 
Now you can finally use jupyter notebook as you have downloaded Anaconda. 
In order to run jupyter notebook and save the files from the path you want, setting the path and environment variables are must things to do!
I would like to run jupyter notebook and save all the files related to python study under C:/Python as a default path.
So let's get started!

1. Start -> Anaconda3 -> put the cursor on Jupyter notebook and click right button -> More -> Open file location 
  Click right button on Jupyter notebook -> Properties

  <img src="https://user-images.githubusercontent.com/46670511/54874356-1c7d9d80-4e2d-11e9-8595-401a7aca8202.png" width="500" />

2. Inside the red box 'USERPROFILE' variable contains all the information regarding path. By deleting "%USERPROFILE%/" this guy, we just deleted the default path.
  <img src ="https://user-images.githubusercontent.com/46670511/54874391-a62d6b00-4e2d-11e9-83e8-7c08ae500efb.png" width="500" />

3. Start -> Anaconda3 -> open Anaconda prompt  
  write the command 'Jupyter notebook –-generate-config' and observe that the file is created.
	
    <img src="https://user-images.githubusercontent.com/46670511/54874465-1dafca00-4e2f-11e9-9ac8-896c37b468a1.PNG" width="500" />

4. Open jupyter_notebook_config.py file using notepad++ and delete the comment below and write the path you want to run jupyter notebook as default.

	<img src="https://user-images.githubusercontent.com/46670511/54874491-aa5a8800-4e2f-11e9-8312-a50c37acc28b.PNG" width="500" />

5. Now, once you run jupyter notebook, it will run and save the files from the path you have set.

## JDK 설치 및 환경 변수 설정
파이썬에서 Machine Learning/Deep Learning 알고리즘을 사용하여 분석할 때 필요한 몇가지 프로그램들은 Java를 기반으로 개발되어 있습니다. 따라서 저러한 프로그램들을 실행시키기 위해 JDK 설치가 필요합니다.


### JDK 설치
JDK 설치는 <www.oracle.com> 에 접속하여 Java SE Download 를 클릭한 뒤, JavaSE 8버젼을 다운로드 합니다.
너무 최신 버전은 호환이 안 될 수도 있어서 8버전을 다운받는겁니다!
아래의 그림예시와 같이 JDK를 클릭 수, accept 버튼을 누른 뒤, 자신의 컴퓨터 사양에 맞는 파일을 다운로드 합니다.

<img src="https://user-images.githubusercontent.com/46670511/54252335-b91e8080-458d-11e9-9e0d-8dc7f36e8daf.png" width="500" />

<img src="https://user-images.githubusercontent.com/46670511/54252344-c3407f00-458d-11e9-983f-451798513b27.png" width="500" />


### JDK 환경변수 설정
나중에 설치될 프로그램한테 jdk가 깔려있다는 것을 명시하기 위해 환경변수 설정을 해야합니다.

1. 위와 같은 방식으로 제어판 -> 시스템 및 보안 -> 시스템 -> 고급시스템 설정 -> 환경변수 를 클릭합니다.

2. 시스템 변수의 새로 만들기를 클릭 후 변수 이름은 JAVA_HOME으로 지정하고 jdk가 설치된 path값을 지정해줍니다.
note: 변수이름은 꼭 JAVA_HOME으로 하세요!

	<img src="https://user-images.githubusercontent.com/46670511/54252934-259a7f00-4590-11e9-8871-a9e65608c7ed.png" width="500" />

---------------------

### 아나콘다 설치 및 위의 포스트와 같은 환경설정은 파이썬을 사용하여 분석을 시작하기 앞서 매우 매우 중요한 스텝이므로 소홀히 하지 맙시다! 





