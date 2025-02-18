---
title: "[블로그] 한줄코딩 포스팅 적기전.. (스크립트 활용해보자 🔔)"
author: "널두"
date: 2021-10-14 14:27:52 +0900
categories: [블로그]
tags: [블로그, 스크립트]
pin: true
---

## 블로그 적기 전..
한줄코딩 블로그를 사용하기 전에 알아야할 것은 2가지를 알면 포스팅을 편리하게
적을 수 있다.

*🌱 markdown 사용법*

*🌱 script 사용법*

*2 가지의 포인트*를 알아보도록 하자.

### 🌱 markdown 사용법
jekyll 블로그에서 사용하고 있는 markdown은 *kramdown*이다.

마크다운 마다 문법이 약간씩 차이가 있는데, 마크다운 문법이 궁금할 경우 구글에 *kramdown 사용법*을 검색해보자.

좀 더 자세한 사용법은 [발가락님의 포스팅 작성법](https://blog.hanjulcoding.com/posts/markdown/)을 참고하자:)

사실, 귀찮아서 링크도 클릭하지 않는 닝겐들에게 사용법 몇 가지를 적어본다.

1. "\#"을 잘 활용할 것.
  - "\#" 의 개수에 따라 "H"테크의 크기라고 알면 된다.
  - 즉, "\#" -> "H1", "\#\#"-> "H2", "\#\#\#"-> "H3"
  - 위의 말을 봐도 무슨말인지 모르면, 검색하자..

2. 코드 작성 방법
  - 코드를 작성하기 위해서는 "\`\`" 백쿼터를 사용하면된다.
  - 작성법은 아래의 사진을 참고하자.

  - 위와 같이 작성할 경우 아래와 같은 결과를 나타낼 수 있다.
  ```js
    console.log(Hello hanjul coding!);
  ```

3. 강조
  - \* 강조 \* <- 강조하는 방법
  - 너무 많은 강조를 하면 안되고, 특정 문자에 대해 강조할 것을 추천한다.

4. 링크
  - \[\]\(\) <- 링크 거는 방법
  - 링크는 예시를 보면 쉽다.
    - \[naver 들어가자\](https://www.naver.com) 과 같이 적게 되면 아래의 결과를 도출 할 수 있다.
    - [naver 들어가자](https://www.naver.com)

5. 사진추가
  - 사진을 추가하기 위해서는 사진을 블로그 내 "hanjulcoding.github.io/assets/img/" 이미지 폴더에 사진을 넣어야한다.
    - 보통 해당 커뮤니티에서는 "날짜기준" 으로 사진을 관리하는 듯하니, 룰을 따르도록 하자.
      (로마에 왔으면 로마의 법을 따르라!)

  - 문법
  - 이미지 추가가 완료됐다면, 아래의 문법을 따라 만들면 된다.
  - 링크 거는 방법에 "!" 만 추가하면 된다.
  - !\[\]\(\) <- 사진 사용하는 바업
  - !\[thumnail\]\(/assets/img/20210911/haha.jpg\) 와 같이 사용하면 되고, 아래와 같이 나올 것이다.
	- ![image desc](/assets/img/20210911/haha.jpg)

  - 사진 크기 조절은 어떻게 해요?
    - \{:height :100px, width :100px\} 이라는 방법이 있는데.. 이것도 구글 검색해서 알아보면 바로나온다.
 
사실 위에 방법들만 알아도, 마크다운 블로그 내용 적는데 큰 문제가 없다. 더 필요한 부분들은 찾아서 읽어보자!

### 🌱 스크립트 사용법

일단 스크립트를 왜 사용해야할까요?

```console
---
title: 제목
author: 작성자
date: 2021-03-17 17:54:48 +0900 (리눅스 명령어 date '+%Y-%m-%d %H:%M:%S %z' 을 실행하면 시간이 나옵니다.)
categories: [카테고리]
tags: [태그]
(카테고리, 태그는 자동으로 생성됩니다.
pin: true
---
```

포스팅을 하기 위해서는 파일을 만들고, 해당 값을 복사하고, 시간을 따로
구해야한다.. 😭 너무 귀찮아서 스크립트로 만들어서 편하게 해당 작업을 하고자 한다.

스크립트의 이름은 "\_post" 폴더 내 "mkdown"이다.

해당 스크립트는 단순하게 동작한다. 파일하나 만들고, jekyll에서 동작할 수 있는
파일명을 만들고, 위의 복사해야되는 자동으로 문자들을 삽입해준다.

됐고, 사용방법을 보자. (스크립트 분석은 필요 없다. 사용방법만 알면됨..)

*🙋 어떻게 사용하나요?*

```sh
# filename은 본인이 원하는 파일명을 적으면 됨.
# 예시로, filename이라는 파일을 만들어보자:)
> ./mkdown filename
```

위와 같이, 명령어를 실행하면 아래와 같은 filename이라는 파일이 생성된다.

![test1](/assets/img/20211014/test1.png)

여기서 보면, filename이라는 파일이 생성된 후 *"노란색"*으로 본인이 만든 파일명을
알 수 있다. 해당 파일 명으로 들어가면, 아래와 같이 필요한 부분들이 다 삽입되어져있는 것을 알
수 있다.

![test2](/assets/img/20211014/test2.png)

위와 같이, posting에 필요한 정보를 본인에 입맛에 고치면 된다.

*title* : 제목을 쓰는 곳. ("..") 내 제목을 쓰면 됨.

*author* : 자신의 이름을 곳. ("..") 자신의 닉네임을 쓰면 됨.

*date* : 자동으로 채워지지 건들지 않아도 됨.

*category* : 카테고리를 적는 곳. 보통 카테고리는 하나로 묶어서 사용함. 본인이
원하는대로 변경해서 사용하면 됨.

*tag* : tag를 적는 곳. 여기에는 다수의 tag를 적을 수 있는데, 다수개의 tag를 적을
때는 (,)를 적어서 여러개를 적으면 됨. 예를들어, [*tag1* , *tag2*] 와 같이
다수개의 tag를 적으면 된다.

모를 경우 다른 포스팅을 열어 참고해보자 :)

위의 과정이 완료됐다면,  위에서 배운 마크다운으로, 포스팅의 꿈을 펼치면 보도록
하자!!😀

*⛔ 스크립트 예외처리*

스크립트 내에서 두 가지 예외를 처리하고 있다.

예외처리로 발생한 에러는 *빨간색*으로 표기될 것이다.

*1. 파일명을 입력하지 않았을 경우*
- 파일명을 입력하지 않을 경우 아래와 같은 메세지를 보게 될 것이다.

![test3](/assets/img/20211014/test3.png)

*2. post내 중복된 이름이 존재할 경우*
- 동일한 날짜에 동일한 이름을 사용할 경우 *중복*으로 간주하고 예외로 처리했다.
- 아래와 같은 에러를 만나면 내가 동일한 포스팅을 또 만들었구나 생각하면 됨.

![test4](/assets/img/20211014/test4.png)
