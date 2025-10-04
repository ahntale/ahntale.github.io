---
typora-root-url: ../
categories: jekyll
title: 2025-10-03 notice, redirect, image half, LaTex 문법
author_profile: false
sidebar:
  nav: "docs"
layout: single
tag: jekyll
toc: true
---

### 2025-10-03 notice, redirect, image half, LaTex 문법 ,etc

------

- minimal-mistake notice 설정:

  - minimal-mistake quick guiad에서 notice 명령어를 vscode에서 해당 post 원하는 문장뒤에 삽입하여 설정.

    `{: .notice--danger}`

  - 한 문장이 아니라 여러 문장을 notice 설정할 경우 `<div>`로 감싸준다.

    `<div class = "notice">`

    "본문 내용" # 본문내용에는 html태그 삽입가능.

    `</div>`

- Youtube link 삽입:

  - `(중괄호) % include video id="youtube video id" provider="youtube" %(중괄호)`

- category 변경시 자동 redirect from 세팅

  - _config.yml에서 `plugin`, `whitelist`에 `-jekyll-redirect-from` 을 추가하고 로컬 서버를 돌리면 에러가 뜬다. 

    vscode에서 minimal-mistakes-jekyll-gemspec 에서 다음의 코드를 추가한다.

    `spec.add_runtime_dependency "jekyll-redirect-from", "~> 0.1"`

    이후 다시 블로그 repo에서 로컬서버(`bundle exec jekyll serve`) 로 구동시켜보면 실행된다.

    

    post YAML 상단에 `categories:` 를 변경하면 이를 참조하는 다른 post도 변경되어 404error가 뜬다. YAML 말머리에

    ```
    redirect_from:
    	-/바꾼categories/포스트제목
    ```

    하면 redirection을 해준다.

- post에 이미지 삽입시 50% 축소 태그

  - _sass >> _utilities.scss 에서 다음의 코드를 추가한다.

    ```
    .img-width-half {
    
     width: 50%;
    
    }
    ```

    이후 추가한 이미지 코드 뒤에 다음의 코드를 추가한다.

    `{: .img-width-half}`

    이미지 가운데 정렬은 이미 정의되어 있으므로

    `.img-width-half` 뒤에 `.align-center`후 }로 닫아준다.

- LaTex 수식 문법을 지원하는 mathjax.html 적용

  - teddynote 강의에서 다운받은 html코드를 'mathjax-support.html' 이름의 html파일로 저장하여 _includes 아래에 넣어준다.

  - _includes >> head >> custom.html에서 아까 추가한 mathjax.html을 사용하겠다는 코드를 추가한다. 이떄 수학수식이 필요한 post에만 적용할 수 있도록 해당 post YAML에 변수를 하나 추가한다 `use_math: true`

    

    ```html
    <script type="text/x-mathjax-config">
        MathJax.Hub.Config({
            TeX: {
              equationNumbers: {
                autoNumber: "AMS"
              }
            },
            tex2jax: {
            inlineMath: [ ['$', '$'] ],
            displayMath: [ ['$$', '$$'] ],
            processEscapes: true,
          }
        });
        MathJax.Hub.Register.MessageHook("Math Processing Error",function (message) {
              alert("Math Processing Error: "+message[1]);
            });
        MathJax.Hub.Register.MessageHook("TeX Jax - parse error",function (message) {
              alert("Math Processing Error: "+message[1]);
            });
        </script>
    <script type="text/javascript" async src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML">
    </script>
    ```



​	custom.html에 다음의 Liquid문법을 추가한다

​	

```

{% if page.use_math %}
    {% include mathjax-support.html %}
{% endif %}}

```

​	그런데 typora 에서는 자체적으로 LaTex 문법을 지원하니 필요없어 보인다..





------

- [ ] github page enforce https check 불가 (클라우드플레어 custom domain)
- [ ] categories counting post 구현할 것.
- [ ] 프로젝트학기 학습 진도에 집중할 것.