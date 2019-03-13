---
layout: post
title: "Anaconda 설치 및 환경변수 설정"
description: "Anaconda & Jupyter notebook 환경변수 설정"
date: 2019-03-13
tags: [Python, Anaconda, Jupyter notebook]
category: Python
comments: true
share: true
---

## Anaconda 설치
아나콘다 설치는 <https://www.anaconda.com/distribution/> 에 들어가서 자신의 OS에 맞는 사양을 설치하면 됩니다.

## Anaconda 환경 설정
1. 아나콘다를 설치할 때 디폴트로 경로를 설정하면 Users 하위 폴더인 자신의 유저 폴더 안에 Anaconda3 폴더가 생성된 것을 확인할 수 있습니다.

2. C:/Users/(본인 username)/Anaconda3 로 들어가면 python.exe 파일이 확인 가능합니다. <br> note: 'exe는 window에서 도스창을 띄우는 확장자명 입니다. (마우스로 클릭해서 도스창이 뜨는 것이 가능하게 하는 user interface)

3. 시작 버튼을 누른 뒤, cmd를 입력하여 명령 프롬프트 창을 띄웁니다. 예를들어, 아래의 예시를 봅시다! <br> 제 컴퓨터에 설치 되어 있는 notepad.exe는 path 설정이 되어 있어 바로 실행이 가능하나, python은 path 설정이 되어있지 않아서 python이 설치된 경로를 직접 찾아가서 실행시켜야 합니다.
	![0312_1](https://user-images.githubusercontent.com/46670511/54249400-693abc00-4583-11e9-8715-ec06ec2cf0a1.png)
	
	간단한 cd/dir 명령어로 파이썬이 설치된 경로로 이동한 뒤, python.exe를 실행하면 실행되는 것을 확인할 수 있습니다. 
	이러한 불편함을 감소 시키기 위해 두개의 경로를 저장합니다.

4. Path 설정을 하기 위해서, 제어판 -> 시스템 및 보안 -> 시스템 -> 고급시스템 버튼을 눌러줍니다. 고급 아래 쪽 환경변수 버튼을 클릭해 주면, 본인 사용자 변수 와 시스템 변수 두가지 옵션이 뜹니다. 
시스템 변수 하위 새로만들기 버튼을 클릭 한 뒤, 변수값에 앞에 뭐라뭐라 써져있는 값들은 건들지 말고 세미콜론을 추가한 뒤, Anaconda3가 있는 Path값을 추가해줍니다.
	![0312_2](https://user-images.githubusercontent.com/46670511/54249538-dc443280-4583-11e9-9bd2-4d6316623ce2.png)
	
	이런 식으로 Path 설정을 하면, 추가한 경로 안의 시스템은 어디서든 실행이 가능합니다. (어느 경로에서나 파이썬 실행이 가능) 
	세개의 경로를 저장해야 합니다.
	Script와 Library/bin 폴더 안에 우리가 앞으로 사용할 다양한 프로그램이 존재하므로 얘도 path 설정을 해주는 것입니다.

```
C:/Users/(본인 username)/Anaconda3
C:/Users/(본인 username)/Anaconda3/Scripts
C:/Users/(본인 username)/Anaconda3/Library/bin
```

예시: 
Script 하위의 conda.exe를 C:/Users/(본인 username) 에서 실행하면 오류가 뜨는 걸 확인할 수 있습니다.

	![0312_3](https://user-images.githubusercontent.com/46670511/54249551-ed8d3f00-4583-11e9-89f3-05e74f943484.png)
	Path를 저장 후, 같은 위치에서 conda.exe를 실행하면 아래와 같이 잘 실행이 됩니다.

	![0312_4](https://user-images.githubusercontent.com/46670511/54249568-fa119780-4583-11e9-883c-5a36ddef3bc6.png)

## Jupyter notebook 환경 설정
Anaconda를 설치하였으니, jupyter notebook을 사용할 수 있습니다. jupyter notebook 또한 환경 설정을 하지 않으면, 원하지 않는 경로에서 jupyter notebook이 실행되고 저장이 됩니다. <br> 저는 앞으로 파이썬 공부할 내용을 저장할 폴더를 C:/njikim/pythonwork 로 생성하였고, 이폴더를 default로 jupyter notebook가 실행이 되고 저장이 되길 원합니다!!

1. 시작 -> Anaconda3 -> Jupyter notebook 마우스 올리고 오른쪽 버튼 -> '속성' 을 클릭합니다.
	![0312_5](https://user-images.githubusercontent.com/46670511/54249584-03026900-4584-11e9-8707-302249ae9dc3.png)


	![0312_6](https://user-images.githubusercontent.com/46670511/54249590-0d246780-4584-11e9-91fc-167b511b2d11.png)

2. 빨간 박스 안 USERPROFILE 이라는 변수 안에 경로 정보를 포함한 모든 정보가 담겨있습니다. "%USERPROFILE%/" 얘를 지워버립니다! 즉, 기본 경로를 지워버리는 겁니다.

3. 시작 -> Anaconda3 -> Anaconda prompt 창을 열고, <br> Jupyter notebook –generate-config 라는 명령어를 치면, 파일이 생성된 것을 확인할 수 있습니다.

	![0312_7](https://user-images.githubusercontent.com/46670511/54249598-157ca280-4584-11e9-8a5f-c49ba4694ca8.png)


4. jupyter_notebook_config.py 파일을 notepad++ 로 실행한 뒤, 저 부분의 주석을 지워주고 원하는 경로를 입력합니다.

	![0312_8](https://user-images.githubusercontent.com/46670511/54249602-1dd4dd80-4584-11e9-8453-24523af3d5a0.png)

5. 이제 jupyter notebook을 실행하면 지정한 경로에서 주피터 노트북이 실행되고, 그 경로에 파일이 저장됩니다.






