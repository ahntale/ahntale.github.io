---
layout: single
title: "2025-09-25-Thursday image#3 ~"
author_profile: false
sidebar:
  nav: "docs"
typora-root-url: ../
categories: jekyll
tag: jekyll
---

- 서울 일정 소화중 짬이나서 서강대 스타벅스에서 강의를 들을 시간이 됐다. (2025-09-25-1:00PM)
- 책 '지브리의 철학', '지브리의 문학' , '위대한 게임의 시작 : 게임 시나리오 작법' 외 AI영상관련 책 3권을 대출했다.

- [x] ??) 로컬에선 이미지가 무리없이 첨부되어도 홈페이지 호스팅시 이미지가 깨지는데 경로문제같다. 빨리 블로그 정비해서 계획서상의 공부를 진행하고 싶다.(해결! : **local에 있는 폴더명(post제목)에 #이 들어가면 이미지 추가할때 경로 오류가 생긴다.)**

- [ ] ??)yaml에 대해 잘 모른다.

- [x] ??) logo는 잘 들어갔는데, author profile avatar는 깨진다.(해결)

**이미지 추가**

---

설정 >> 이미지 >> 사용자 정의 폴더로 이미지 복사 >> 경로 세팅 후 뒤에 `/${filename}`을 타이핑한다.

_test삼아 내 첫기타 성음크래프터 기타사진을 올린다._

_![2021-12-26 16.12.46](/images/2025-09-25-Thursday-image-3/2021-12-26-guitar.jpg)_

이미지를 추가한 후 경로 앞의 .. 을 제거한다. 제거하면 서버에는 제대로 반영이 되지만 typora에서는 깨져서 보이는 문제가 있다. 이를 보완하기 위해 >> YAML 말머리에 `typora-root-url: ../`을 추가한다.

**업데이트 내역 실시간 확인하기(로컬 환경 설정)**

---

매번 typora에서 수정하고 github로 push하고 확인하면 번거로워서 로컬에서 실시간으로 확인할 수 있도록 해보자.

minimal-mistake Quick start guide >> Installation >> Install dependencies 에서 아래의 사이트에 접속할 수 있다.

[Jekyll official documentation]: https://jekyllrb.com/docs/

OS에 맞는 Ruby를 설치해야 한다. (_2025-09-25 5:21PM_)

\*중간 내용 나중에 다시 remind.

모든 설치과정을 거쳐서

`bundle exec jekyll serve`를 cmd에 입력하면 로컬 서버를 열 수 있다.

**기억해야 할 것**

---

- \_posts의 폴더명에 #이 들어가면 이미지 경로문제가 생긴다.

  local 경로, 상대경로, YAML typora-root-url: ../ 문제없는데 git서버에서 안뜨길래 폴더명(블로그)
