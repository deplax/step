---
layout:     post
title:      "PhotoCategorize"
subtitle:   "[PYTHON]"
date:       2015-02-10 12:00:00
author:     "SturdyEgg"
header-img: "img/post_photocategorize/title.jpg"
---
 
 <!-- **[Github Link](https://github.com/deplax/)** -->

#Summary

|**Project name :** PhotoCategorize
|**Language :** Python
|**Type of project :** Personal project
|**Project duration :** 6 hour
|**Source code :** <a href="https://github.com/deplax/P_PhotoCategorize" style="color:#3366FF; font-weight:bold">Github Link</a>

####Brief Description <br>
사진의 메타데이터를 읽어 날짜별로 폴더를 생성해 분류해 준다.

<br/>


#Description

사진을 상당히 어렸을 때 부터 디지털카메라를 이용해 촬영하였다. 5학년부터 촬영한 사진은 꼬박꼬박모아 4만장 정도 모였는데 사진들이 일관성있게 분류되지 않아 보기가 쉽지 않았고, 날짜별로 분류한다면 그나마 보기 편할 것 같았다. 그래서 일일이 날짜로 폴더를 만들고 복사를 하는데 양이 너무 많다. '아... 내가 이걸 왜 직접 하고 있지?' 프로그램을 짜기로 결정하고 가장 최근에 사용한 언어인 Python을 사용해 1차적으로 메타데이터를 읽고 메타데이터가 없을 경우 생성일을 읽어 폴더별로 분류해주는 프로그램을 제작하였다.

<br/><br/>


#Postmortem

####어려웠던 점
* 테스트
: 테스트를 하려면 샘플로 파일을 넣어두고 스크립트를 돌리면 파일이 실제로 이동해버린다. 한 번 테스트하면 다시 결과물 파일을 지우고 원본 위치에 파일을 복사해야 했다. Python은 unit테스트를 어떻게 할까 궁금해 하면서 일단 만들었다.

####잘된 점.
* 내가 원하는 것을 빠른 시간에 만들었다.
: 언어의 장점이라고 생각한다. 프로그램을 만들기 위한 준비시간이 거의 걸리지 않았고, 샘플코드 몇개를 수정하고 소규모로 테스트하여 빠른 시간에 결과를 볼 수 있었다. 내가 원하는 내용을 직접 만들어 사용하니 기분이 좋았다.

<br/><br/>


#Preview video
<iframe src="https://www.youtube.com/embed/TXnMEwWOsUM" frameborder="0" allowfullscreen></iframe>

<br/><br/>


#Screenshot

<img src="{{ site.baseurl }}/img/post_photocategorize/01.png" width="100%" style="text-align: center">