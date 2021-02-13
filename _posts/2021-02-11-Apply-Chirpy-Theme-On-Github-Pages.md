---
comments: true
title: 깃헙 페이지에 Chirpy 테마 적용하기
date: 2021-02-11 23:50:30 +0900
categories: [ETC, Github Pages]
tags: [jekyll, theme]
---

# 깃헙 페이지에 Chirpy 테마 적용하기

깃헙 페이지에 Chirpy 테마를 적용하는 방법을 정리한 포스트입니다.

- [Chirpy](https://github.com/cotes2020/jekyll-theme-chirpy)
- [Chirpy Demo](https://chirpy.cotes.info/)

## 1.깃헙 페이지 생성

### 1-1.Repositories 탭에서 New 버튼 클릭

![https://user-images.githubusercontent.com/58318174/107635262-2cffc100-6cae-11eb-958d-c4b453421a1a.png](https://user-images.githubusercontent.com/58318174/107635262-2cffc100-6cae-11eb-958d-c4b453421a1a.png)

리파지토리 생성 버튼을 클릭합니다.

### 1-2.리파지토리 생성

![https://user-images.githubusercontent.com/58318174/107635264-2d985780-6cae-11eb-97b9-fe0b0191620c.png](https://user-images.githubusercontent.com/58318174/107635264-2d985780-6cae-11eb-97b9-fe0b0191620c.png)

- Repository name: **GithubId**.github.io
  - **GithubId**.github.io 로 설정하지 않으면 [https://dev-angelo.github.io/](https://dev-angelo.github.io/) 가 아닌 다른 주소에 깃헙 페이지가 생성되게 됩니다.
- Public / Private: Public 선택
  - 깃헙 무료 사용자일 경우에 깃헙 페이지는 public 리파지토리에서만 가능합니다.

설정 완료 후 Create repository 버튼을 클릭합니다.

### 1-3.Settings 탭에서 깃헙 페이지의 발행 확인

![https://user-images.githubusercontent.com/58318174/107635266-2d985780-6cae-11eb-8899-df66d9e56623.png](https://user-images.githubusercontent.com/58318174/107635266-2d985780-6cae-11eb-8899-df66d9e56623.png)

깃헙 페이지가 정상적으로 생성되었는지 `Your site is published at <https://GithubId.github.io/`> 문구를 확인합니다.

### 1-4.리파지토리 URL 복사

![https://user-images.githubusercontent.com/58318174/107635268-2e30ee00-6cae-11eb-8ff8-bb2b20d2acff.png](https://user-images.githubusercontent.com/58318174/107635268-2e30ee00-6cae-11eb-8ff8-bb2b20d2acff.png)

리파지토리 클론을 위해 URL을 복사합니다.

### 1-5.리파지토리 클론

![https://user-images.githubusercontent.com/58318174/107635269-2e30ee00-6cae-11eb-80d4-e0f9218f68f9.png](https://user-images.githubusercontent.com/58318174/107635269-2e30ee00-6cae-11eb-80d4-e0f9218f68f9.png)

새로 생성한 리파지토리를 클론합니다.

## 2.jekyll-theme-chirpy 업로드

### 2-1.압축파일 풀기

![https://user-images.githubusercontent.com/58318174/107635271-2ec98480-6cae-11eb-89d5-c0551d92e06e.png](https://user-images.githubusercontent.com/58318174/107635271-2ec98480-6cae-11eb-89d5-c0551d92e06e.png)

[https://github.com/cotes2020/jekyll-theme-chirpy/releases](https://github.com/cotes2020/jekyll-theme-chirpy/releases) 에서 다운받은 파일을 적절한 폴더에 압축을 풀어줍니다.

### 2-2.리파지토리에 업로드하기 위하여 jekyll-theme-chirpy 폴더 안의 내용을 복사

![https://user-images.githubusercontent.com/58318174/107635273-2ec98480-6cae-11eb-923c-e9f5dc871388.png](https://user-images.githubusercontent.com/58318174/107635273-2ec98480-6cae-11eb-923c-e9f5dc871388.png)

압축을 푼 폴더안의 내용을 전부 앞서 클론한 리파지토리 폴더에 복사합니다.

### 2-3.리파지토리 폴더/.github/workflows/pages-deploy.yml.hook 파일 수정

![https://user-images.githubusercontent.com/58318174/107635275-2f621b00-6cae-11eb-8b2d-ea412614db68.png](https://user-images.githubusercontent.com/58318174/107635275-2f621b00-6cae-11eb-8b2d-ea412614db68.png)

2020년 10월 이후에 생성한 리파지토리는 default 브랜치가 main으로 생성되므로 branches를 master -> **main** 으로 수정해야합니다.
그 이전에 생성하였던 리파지토리에 적용한다면 이 절차는 필요 없습니다.

### 2-4.HTML language tag 및 timezone 설정 변경

![https://user-images.githubusercontent.com/58318174/107635277-2f621b00-6cae-11eb-9a40-6483367f8088.png](https://user-images.githubusercontent.com/58318174/107635277-2f621b00-6cae-11eb-9a40-6483367f8088.png)

- lang: ko-KR
- timezone: Asia/Seoul

### 2-5.Init 쉘 스크립트 실행

![https://user-images.githubusercontent.com/58318174/107635278-2ffab180-6cae-11eb-917a-570973ba1790.png](https://user-images.githubusercontent.com/58318174/107635278-2ffab180-6cae-11eb-917a-570973ba1790.png)

불필요한 파일들을 제거하고 chirpy에 대한 파일들을 커밋하는 기능을 수행하는 쉘 스크립트를 실행합니다.
`[INFO] Initialization Successful!`이라는 문구가 출력되면 정상적으로 수행된것입니다.

## 3.Push 및 깃헙 액션 확인

### 3-1.Push

![https://user-images.githubusercontent.com/58318174/107635280-2ffab180-6cae-11eb-9c40-4eef11aae640.png](https://user-images.githubusercontent.com/58318174/107635280-2ffab180-6cae-11eb-9c40-4eef11aae640.png)

커밋된 내용을 main 브랜치로 푸시합니다.

### 3-2.Github Actions - workflows

![https://user-images.githubusercontent.com/58318174/107635248-296c3a00-6cae-11eb-9cf1-0a8e1f2c5e0a.png](https://user-images.githubusercontent.com/58318174/107635248-296c3a00-6cae-11eb-9cf1-0a8e1f2c5e0a.png)

`init.sh`파일을 실행하여 커밋된 메시지의 제목으로 생성된 workflow를 확인 가능합니다.

### 3-3.Github Actions - Summary

![https://user-images.githubusercontent.com/58318174/107635251-2a04d080-6cae-11eb-8a13-e1c8636d0e64.png](https://user-images.githubusercontent.com/58318174/107635251-2a04d080-6cae-11eb-8a13-e1c8636d0e64.png)

continuous-delivery를 클릭합니다.

### 3-4.Github Actions - Jobs

![https://user-images.githubusercontent.com/58318174/107635254-2a9d6700-6cae-11eb-8444-474651e1bf00.png](https://user-images.githubusercontent.com/58318174/107635254-2a9d6700-6cae-11eb-8444-474651e1bf00.png)

현재 진행중인 작업을 확인할 수 있습니다.

### 3-5.Github Actions - Complete job

![https://user-images.githubusercontent.com/58318174/107635255-2a9d6700-6cae-11eb-87f1-6252bd07fdfc.png](https://user-images.githubusercontent.com/58318174/107635255-2a9d6700-6cae-11eb-87f1-6252bd07fdfc.png)

마지막 단계까지 작업이 완료됨을 확인합니다.

### 3-6.새로 생성된 gh-pages 브랜치 확인

![https://user-images.githubusercontent.com/58318174/107635256-2b35fd80-6cae-11eb-987b-96dcbb046edc.png](https://user-images.githubusercontent.com/58318174/107635256-2b35fd80-6cae-11eb-987b-96dcbb046edc.png)

리파지토리의 `<> Code`탭에서 **gh-pages**브랜치가 생성된것을 확인할 수 있습니다.
다음 단계에서 이 브랜치를 해당 리파지토리의 Source로 설정해야합니다.

### 3-7.Settings 탭에서 Source 변경

![https://user-images.githubusercontent.com/58318174/107635257-2b35fd80-6cae-11eb-9915-da333065f8d4.png](https://user-images.githubusercontent.com/58318174/107635257-2b35fd80-6cae-11eb-9915-da333065f8d4.png)

gh-pages 브랜치는 깃헙 블로그를 위해 발행된 브랜치지만 직접적으로 gh-pages 브랜치를 수정하기보다는
main 브랜치에서 `클론한 리파지토리 폴더/_posts` 폴더에 포스트를 추가하여 푸시하고 다시 workflow 를 진행하여 gh-pages 를 발행하는 방법으로 진행됩니다.

## 4.발행된 깃헙 블로그 확인

### 4-1.Settings 탭에서 GitHub Pages 확인

![https://user-images.githubusercontent.com/58318174/107635258-2bce9400-6cae-11eb-88d7-3563dfbfa44c.png](https://user-images.githubusercontent.com/58318174/107635258-2bce9400-6cae-11eb-88d7-3563dfbfa44c.png)

`Your site is ready to be published at ~`문구를 확인합니다.

### 4-2.Chirpy 테마 적용 확인

![https://user-images.githubusercontent.com/58318174/107635259-2c672a80-6cae-11eb-90fd-a35455c66c05.png](https://user-images.githubusercontent.com/58318174/107635259-2c672a80-6cae-11eb-90fd-a35455c66c05.png)

![https://user-images.githubusercontent.com/58318174/107635261-2c672a80-6cae-11eb-852b-d20e3769e339.gif](https://user-images.githubusercontent.com/58318174/107635261-2c672a80-6cae-11eb-852b-d20e3769e339.gif)

**GithubId**.github.io 에 접속하여 테마가 정상적으로 적용된것을 확인할 수 있습니다.
