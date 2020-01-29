---
layout: post
title:  How to make Git Page by Jekyll(for Windows)
date:   2020-01-29 15:20:30 +0300
image:  05.jpg
tags:   Guide
---
이번에 git page를 만들어 보면서 정말 수십개의 홈페이지, 블로그 등을 찾아보았다. 
하지만 그 어느것도 하나부터 열까지 다 설명한 곳은 없었다. 

결국엔 그나마 잘 설명이 되어있는 블로그 2개와 Github 사이트까지 3개를 번갈아 보면서 만들었다. 

그래서 하나의 글만 보고 대부분의 문제를 해결할 수 있도록 설명서를 만들어보고 싶었다. 

아래의 방법을 통해서 만약 해결되지 않는 부분이 있다면, comment를 남겨 같이 고민할 수 있으면 좋을 것 같다.

***

### GitHub Repository 생성하기

먼저, Github 사이트에 자신의 아이디로 로그인해 들어가서 Repository를 생성해야 한다. 

![]({{site.baseurl}}/img/gb1.JPG)

위의 사진을 보면 우측 상단에 더하기 모양이 보인다. 여기서 New repository를 클릭한다.

![]({{site.baseurl}}/img/gb2.JPG)

먼저, Repository name을 적어주여야 하는데, 이때 양식은 [username].github.io 로 해야 한다.

그리고 username은 모두 소문자로 적어주는 것이 이후 문제가 생기지 않을 수 있다. 

(나의 경우는 처음에 대문자를 그대로 적어서 해보았는데 20분이 넘도록 페이지 생성이 되지 않았다.) 

즉, 사진의 예를 들어보자면, 나의 username은 YiSeongYeop이므로, Repository name은 yiseongyeop.github.io가 되는 것이다. 

나는 이미 같은 이름이 있어서 에러가 났다. 사진 속의 에러는 무시해도 된다.

이후, 맨 밑에 Initialize this repository with a README를 체크하고 나서 Create repository 버튼을 누르면 생성이 완료된다.

![]({{site.baseurl}}/img/gb3.JPG)

그러면 위의 사진과 같은 Repository가 생성될 것이다. 

Github는 두 가지 page가 있는데, 하나는 위의 사진처럼 그냥 클라우드와 같이 파일 공유를 위한 page이고, 나머지 하나는 Github 내장 Jekyll을 통해 보여지는 page이다.

후자의 경우는 주소창에 [username].github.io를 치면 나올 것이다.

(바로 적용되지 않으므로 안 보인다고 당황할 것 없이 몇 분 기다리면 된다!)

***

### Jekyll 설치

Jekyll을 설치하기 위해 Ruby를 설치해야 한다. 
Ruby 다운로드 사이트는 아래 하이퍼링크로 들어가면 나온다. 

추천 버전으로 깔아도 좋고 그냥 자신의 상황에 맞는 버전으로 하면 된다.

<a href="https://rubyinstaller.org/downloads/" target="_blank">Ruby 설치</a>

상세한 설치 과정은 생략하도록 하겠다. 참고로 나는 설치할 수 있는 모든 것들에 체크하여 설치를 전부 다 했다.

설치 중에 Path 지정 또는 확장자 관련 체크 박스가 있다면 체크를 무조건 해야 한다.

설치가 끝났다면, CMD에서 아래의 명령어를 이용해서 Ruby의 버전을 확인해본다. 설치가 되어있다면 아래처럼 뜰 것이다.

{% highlight base16.monokai.dark %}
>ruby -v

ruby 2.6.5p114 (2019-10-01 revision 67812) [x64-mingw32]
{% endhighlight %}

Ruby 설치 확인이 끝났다면 윈도우 검색창에 ruby 라고 검색해서 'Start Command Prompt with Ruby' 를 실행시키고, 아래의 명령어를 입력해서 Jekyll과 bundler 설치를 시작한다.

{% highlight base16.monokai.dark %}
>gem install jekyll bundler
{% endhighlight %}

이렇게 하면 Ruby와 Jekyll의 설치가 모두 끝나게 된다.

***

### GitHub Repository Cloning / Jekyll 생성 / Server 실행

아까 처음에 만들어 둔 Github Repository에 들어가서 보면, 오른쪽에 'Clone or download'라고 적힌 초록색 버튼이 있다. 클릭하면 URL이 보이는데, 이것을 복사한다.

![]({{site.baseurl}}/img/gb4.JPG)

CMD를 실행해서 아래의 명령어를 입력하여 local로 clone을 하고 나서 생성된 폴더로 이동한다.

{% highlight base16.monokai.dark %}
>git clone https://github.com/YiSeongYeop/yiseongyeop.github.io.git

>cd yiseongyeop.github.io
{% endhighlight %}

이곳에서 Jekyll을 생성한다.

{% highlight base16.monokai.dark %}
>jekyll new .
>bundle install
{% endhighlight %}

어떻게 생성되었는지 보고 싶다면 아래의 명령어를 입력하여 서버를 열고, 아래에 표기된 Server address를 통해 접속하여 사이트를 확인해본다.

{% highlight base16.monokai.dark %}
>bundle exec jekyll serve  #jekyll serve 해도 되지만 앞과 같이 하는 것이 오류를 방지하기에 좋다
{% endhighlight %}


이 아래부터는 테마를 적용할 때 가능한 여러 방법들을 나열해놓았다. 각자가 편한 방법으로 골라서 하면 될 것 같다.

### 1. 