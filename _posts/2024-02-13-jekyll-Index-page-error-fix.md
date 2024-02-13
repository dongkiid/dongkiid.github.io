---
title: Chirpy - 'layout home Index page' 에러 해결
date: 2024-02-12 19:20:00 +09:00
categories: [Blogging,블로그 관련]
tags: [jekyll, github, github.io, github-blog]
pin: true
---

### 어제 갓 만든 내 블로그에 벌써 오류가 났다!

<img width="320" alt="error-image" src="https://github.com/dongkiid/dongkiid.github.io/assets/113974911/73849b10-870d-4f7f-b2c1-c6fa3efa228c">

맥북에서 chrome으로 접속할땐 문제가 없었는데,  
사파리나 윈도우 chrome으로 접속하면 해당 에러가 발생하며 블로그가 보이지 않는 문제였다.

### 해결 방법

아래 링크를 참고하여 해당 에러를 해결했다.

[chirpy-repo-issue](https://github.com/cotes2020/jekyll-theme-chirpy/issues/628) <br>
[chirpy tutorial](https://chirpy.cotes.page/posts/getting-started/#deploy-by-using-github-actions)


해결 방법은 크게 2가지가 있었다.

해결 방법 1. gemfile.lock 파일의 platform에 x86_64-linux를 추가하는 것 <br>
    => 로컬에서 다음 명령어 실행: ```bundle lock --add-platform x86_64-linux``` <br>
    => gemfile.lock에 이미 리눅스 관련 플랫폼들 설정이 되어있던 상태이므로, 내 문제에는 해당하지 않는 해결책이었다.

**해결 방법 2. Repository Setting에서 Source Build and Deploy 설정을 Github Actions로 변경**

<img width="790" alt="image" src="https://github.com/dongkiid/dongkiid.github.io/assets/113974911/285ec310-b5a9-420d-902e-6160673e8f0c">
    => 기본 설정인 'Deploy from branch'으로 해둘 경우, "--- layout: home # Index page ---" 내용을 포함한 index.html을 잘못 렌더링한다는 내용이 이슈와 튜토리얼에 나와 있었다.<br>
    => 해당 설정을 수동으로 변경하여 오류 해결 완료! 

