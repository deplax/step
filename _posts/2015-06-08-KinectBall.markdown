---
layout:     post
title:      "KinectBall"
subtitle:   "[KINECT] [JAVA] [PROCESSING]"
date:       2015-06-08 12:00:00
author:     "SturdyEgg"
header-img: "img/post_kinectball/title.jpg"
---
 
 <!-- **[Github Link](https://github.com/deplax/)** -->

#Summary

|**Project name :** KinectBall
|**Language :** Processing Java
|**Type of project :** Personal project
|**Project duration :** 2 week
|**Source code :** <a href="https://github.com/deplax/T_kinect_ball" style="color:#3366FF; font-weight:bold">Github Link</a>

####Brief Description <br>
Kinect를 이용하여 가상의 공과 인터렉티브 할 수 있다. 가상의 공은 중력과, 바람이 설정되어 있으며 실루엣으로 공을 옮길 수 있다.

사실 이걸 하려던 것은 아니었고 원래 작성하던 프로젝트 코드가 mac의 사망과 함께 증발하여
http://www.creativeapplications.net/processing/kinect-physics-tutorial-for-processing/ 의 Tutorial코드를 작동가능하도록 수정하고 몇가지 기능을 추가하는데 그쳤다.

<br/>


#Description

NHN NEXT 4학기 HumanComputerInteraction 과목에서 Kinec프로젝트로 진행했던 내용이다. 원래 진행하던 Magic이라는 코드가 있었지만 맥의 사망과 함께 프로젝트 제출 12시간이 남은 시점에서 소멸되었다. 차선책으로 Kinect시연을 위해 이전에 봐두었던 듀토리얼을 현재 버젼에서 작동할 수 있도록 수정하고 몇가지 기능을 추가하여 시연에 사용하였다. 코드가 내 것이 아니기에 [Kinect를 컴퓨터에 연결하여 들어오는 센서 값을 받아 조작할 수 있다] 정도의 의미를 가지고 마무리되었다.

<br/><br/>


#Postmortem

####아쉬운 점
* 깃을 push하지 않음.
: 로컬에서 사용하던 Magic이라는 이름으로 시작했던 프로젝트를 맥의 사망으로 송두리째 잃어버리고 말았다. 한번이라도 push를 했다면 복구해서 시간내에 시연이 가능했을텐데 아쉬움이 많이 남는다.
* 빈약한 추가기능.
: 12시간을 남겨두고 프로젝트가 변경되어 Tutorial코드에 기능들을 추가하여 마무리 하는 것을 택했다. 하지만 실시간 스킨변경, 실시간 중력 및 바람 변경과 Depth값 수정 정도만 추가되었다. 조금 더 바지런히 했다면 바운스 기능까지는 구현하지 않았을까 아쉽다.


####잘된 점.
* 묵은 코드를 실행시킴.
: Tutorial코드는 2012년에 작성된 코드로 그대로 받아 실행시키니 전혀 실행이 불가능했다. 그저 코드상의 문제 뿐만 아니라 Kinect라이브러리 버젼과도 문제가 생겨 어떻게 실행되도록 할 수 있을까 여기저기 찔러보았다. 그래서 일부는 버젼을 낮추고 일부는 새 버젼으로 코딩하는 등의 과정을 거쳐 작동이 가능한 코드로 변경시켰다.

<br/><br/>


#Preview video
<iframe src="https://www.youtube.com/embed/7ZDN5_5TuTM" frameborder="0" allowfullscreen></iframe>

<br/><br/>


#Screenshot

<img src="{{ site.baseurl }}/img/post_kinectball/01.jpg" width="100%" style="text-align: center">