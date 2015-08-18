---
layout:     post
title:      "SyncPlayer"
subtitle:   "[JAVA] [JAVAFX]"
date:       2015-07-23 12:00:00
author:     "SturdyEgg"
header-img: "img/post_syncplayer/title.jpg"
---
 
 <!-- **[Github Link](https://github.com/deplax/)** -->

#Summary

|**Project name :** SyncPlayer
|**Language :** Java
|**Type of project :** Personal project
|**Project duration :** 3 week
|**Source code :** <a href="https://github.com/deplax/S_MoviePlayer" style="color:#3366FF; font-weight:bold">Github Link</a>

####Brief Description <br>
n개의 동영상을 동기화 재생 할 수 있는 프로그램이다.

<br/>


#Description

맥프로에서 6개의 동영상을 동시에 재생할 수 있는 프로그램을 만들어 달라는 외주를 받았다. 비슷한 계열의 프로그램을 해본 적이 없었고 맥에서 돌아가는 프로그램을 어떻게 만들지 고민하다가 멀티 '플랫폼인 Java로 해보자' 하고 생각했다. 

요청사항은 각 영상의 싱크가 맞을 것, 6개의 화면에서 끊김 없이 재생이 가능할 것, 전체 화면이 가능할 것, 전체화면시 다른 어떤 것도 보이지 않을 것, 반복재생에도 싱크가 틀어지지 않을 것 등이 있었다. 가장 중요한 포인트는 Sync이었으며 자바로 동영상 플레이어 제작이 가능한지부터 확인하며 작업을 시작하였다.

<br/><br/>


#Postmortem

####어려웠던 점
* JavaFX는 하나의 전체화면만 허용한다.
: 거의 막바지에 이르러 이 사실을 알고 말았다. Java에서 제공하는 메서드를 이용했을 때 하나의 전체화면 만을 인정해 주었다. 내 접근이 틀렸다고 생각하고 여러 가지 방법을 시도해 보았으나 지원이 안 되는 문제는 방법이 없었다. 약속기한이 얼마 남지 않은 상황에서 프로그램 구조를 완전히 바꾸어야 하는 상황에 이르렀으나 Mac에서 기본으로 전체화면이 가능하여 우회할 수 있었다.

* JVM은 모든 OS가 같지 않다.
: Java를 너무 맹신한 탓이었을까? 처음 Java를 배울 당시 Java는 멀티플렛폼으로 같은 코드를 여러 개의 OS에서 작동하는 것을 장점으로 배웠다. 'JVM위에 올라가니 한번 작성하면 win, mac 다 되겠지?' 하지만 디테일한 부분은 OS에 따라 다르게 동작하였다. 창 크기의 계산 방식부터 동영상의 상태까지 다르게 작동하였고 결국 win을 배제한 체 프로그램을 작성하게 되었다.

* 동시에 멈추고 동시에 시작
: 싱크 문제를 심각하게 받아들이지 않았다. 하나의 메서드에서 처리하면 자연스레 싱크가 맞을 것이라 생각했지만 본질적인 싱크 문제를 해결하기 위해서는 JVM단의 thread프로그래밍이 필요하다고 판단되었다. 결국 하드웨어 퍼포먼스로 이 문제를 해결하였으며 보조 수단으로 하드코딩을 하게 되었다. 중간에 일시정지를 할 경우 다시 싱크를 재 정렬하며, 영상이 끝났을 때도 다시 재 정렬하여 싱크의 오차를 줄이도록 되어 있다.

* 영상비율과 중앙정렬
: 너무나도 간단할 것이랑 생각했던 문제가 후반에 발목을 잡았다. 창 크기에 대한 영상 크기변경은 bind를 사용하여 처리했는데 비율문제와 중앙정렬도 비슷한 방식으로 처리할 수 있을 것이라 생각했지만 높이와 너비를 받아서 적용하는 것이 쉽지 않았다. Github에서 다른 사람들 코드를 보던 중 구조 자체에 문제가 있다는 것을 알고 borderPane을 추가하여 정렬하였다.

####잘된 점.
* .app으로 배포.
: 개발당시에는 배포문제는 안중에도 없었다. 이클립스에서 Run을 누르면 잘 돌아갔기 때문이다. 프로그램 전달 몇 시간을 남겨두고 잔 버그를 수정하고 있었는데 그 때서야 배포해야 한다는 것을 알았다. 일단 .jar파일로는 만들 수 있었지만, 이렇게 주는 것은 뭔가 찜찜하였다. 다른 Mac os application처럼 아이콘도 있고 예쁘게 나오도록 하고 싶었다. app이 directory구조라는 것을 뒤늦게 알고 관련 파일과 아이콘을 넣어 .app으로 배포할 수 있었다.

<br/><br/>


#Preview video
<iframe src="https://www.youtube.com/embed/1vNGXyXSL4E" frameborder="0" allowfullscreen></iframe>

<br/><br/>


#Screenshot

<img src="{{ site.baseurl }}/img/post_syncplayer/01.jpg" width="100%" style="text-align: center">

<img src="{{ site.baseurl }}/img/post_syncplayer/02.jpg" width="100%" style="text-align: center">