---
layout:     post
title:      "GoogleImageCrawl"
subtitle:   "[PYTHON] [SELENIUM]"
date:       2015-03-10 12:00:00
author:     "SturdyEgg"
header-img: "img/post_googleimagecrawl/title.jpg"
---
 
 <!-- **[Github Link](https://github.com/deplax/)** -->

#Summary

|**Project name :** GoogleImageCrawl
|**Language :** Python
|**Type of project :** Personal project
|**Project duration :** 2.5 week
|**Source code :** <a href="https://github.com/deplax/S_ImageCrawl" style="color:#3366FF; font-weight:bold">Github Link</a>

####Brief Description <br>
구글 이미지 검색으로 나오는 이미지의 썸내일이 아닌 원본을 모두 로컬에 저장하는 프로그램.

<br/>


#Description

여러 이미지 검색 사이트의 이미지들을 모아서 보여주는 엔진을 제작하고자 했다. 일단 Google과 Pinterest를 대상으로 지정하고 시작했다. 그저 "DOM 파싱을 통해 원본 이미지를 주소를 가져오면 끝이지" 하고 생각했지만 문제는 여러 부분에서 터졌다.

네트워크의 이해가 부족해 발생한 여러 가지 문제점을 하나하나 넘어 Google 이미지 검색에 출력되는 모든 이미지의 원본을 로컬 디렉터리에 저장하는 것에 성공하였다.

<br/><br/>


#Postmortem

####어려웠던 점

* user-agent
: 먼저 테스트를 위해 이미지 검색 후 HTML을 복사한 스트링으로 원본 이미지를 가져올 수 있는지 코드를 짜보았다. 별 문제없이 된다는 것을 확인하고 진행하는데 전혀 이미지 URL을 가져오지 못하였다. 다시 확인해 보니 내가 보고 있는 HTML과 python에서 가져온 HTML이 달랐다. 한참을 고민했다. "이게 다를 수 있나?" 브라우저나 버전에 따라 Google은 결과를 다르게 출력하는 것이었고 Header를 조작하여 지금 내가 보고 있는 환경과 같도록 맞춰줘야 했다.

* Ajax
: 이 문제는 프로젝트 중반에 발생하여 후반까지 나를 괴롭혔고 결국 크롤링 방식을 완전히 변경하게 만들었다. Google에서 이미지검색을 하면 일단 100개의 이미지만 가져온다. 그리고 스크롤이 내려감에 따라 100개씩 Ajax요청을 통해 추가적으로 로딩하게 되는데 이 요청에는 Hash값으로 추정되는 알 수 없는 값이 들어있다. 아마 크롤링 방지를 위해 있는 듯하다.(API를 이용하라는 것인 듯...) 요청을 따로 만들어 보내기도 하고 처음 보낸 요청에서 Hash값을 얻어 보내는 등 여러 가지를 시도했지만 원하는 결과를 얻지 못하였다. 그러던 중 헤드리스 브라우저를 알게 되어 속도는 다소 느리지만 Selenium을 사용하여 문제를 해결하였다.

####잘된 점.
* 원본을 가져온다.
: 어떻게 하면 원본을 가져올까 고민을 많이 했다. 대부분 CDN의 이미지이거나, 썸내일 이었기 때문에 원본을 쫒아가기로 했다. 하지만 Google의 경우 의외로 검색결과에 보이는 것은 썸내일이나 HTML에는 원본의 주소가 포함되어 있어 스트링을 잘라 쉽게 가져올 수 있었다. 다른 사이트는 요청에 요청을 보내 가져오는 방식을 취하였으나 Pinterest의 경우는 CDN에 있는 이미지를 크롤링 하는 수밖에 없었다. 원본이 있는 사이트의 위치만을 알려주기 때문이다.

* 처음 사용하는 파이썬
: 파이썬을 처음 사용해 보았다. 크롤링에 어떤 언어를 사용할까 고민하다 스크립트 언어라면 좋겠다는 생각이 들었기 때문에 JS와 Python에서 고르고 있었다. JS는 이전에 만난 적이 있기 때문에 Python을 한 번 사용해보자 하여 배우면서 코딩했다. 의외로 어렵지 않게 결과를 볼 수 있었고 새로운 방식의 언어이기에 흥미로웠다.

<br/><br/>


#Preview video
<iframe src="https://www.youtube.com/embed/dKWmSpWtsls" frameborder="0" allowfullscreen></iframe>

<br/><br/>


#Screenshot

<img src="{{ site.baseurl }}/img/post_googleimagecrawl/01.png" width="100%" style="text-align: center">