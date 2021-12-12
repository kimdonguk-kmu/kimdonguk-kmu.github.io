
1. git을 통한 원격 저장소 github 배우기

1-1. 먼저 index.html을 vi 에디터를 통해 작성한다.

1-2. git add index.html를 통해 커밋할 파일에 index.html을 추가한다, git commit -m "comment"를 통해 커밋 코멘트를 작성하고 커밋을 해주며 , git push를 통해 git의 원격 저장소에 그 결과를 푸시하여 저장한다.

1-3.이 활동을 하면 github가 자동적으로 <username>.github.io 주소에 index.html에 적힌 문구들을 띄워주는 창을 생성하게 된다.

1-4.이런 git과 github의 특성을 활용해 블로글 작성하려면, 먼저 로컬 저장소에서 ruby와 jekyll을 다운받는다.

1-5. 터미널에서 jekyll new . --force로 새로운 지킬 블로그를 생성한다.

---

2. 그 다음에 bundle exec jekyll serve 로 지킬을 활용한 블로그를 연결한다.

2-1.생성하게 되면 폴더에 많은 폴더가 생기게 된다.

2-1-1. Gemfile, Gemfile.lock, 404.html, about.markdown, index.markdown, 과 _posts 파일에 들어있는 예시 포스트가 생성된다.

2-1-2. 생겨있는 많은 파일들 중에 "_config.yml" 파일의 타이틀 등을 수정한다.

2-2.그 다음 git status로 확인하고, git add, git commit, git push를 통해 github 원격 저장소에 지킬을 통해 다운받은 파일들을 저장한다.
  
2-3. 그렇게 하면 메인 화면에 타이틀이나 자신이 수정한 다른 것들이 바뀌어있는 모습을 볼 수 있다.

---
  
3. 블로그가 생성되면 _posts 칸에 포스트를 생성한다.

layout: post

title: "제목"

subtitle: "소제목"

date: 날짜

background: '그림 파일' (이것은 추후에 설명할 블로그 테마와도 관련있음)

제목

<p> 글 </p>
  

3-1.이 형식으로 포스트를 작성하여 YYYY-mm-dd-"파일이름".md로 저장한다.

3-2.그 다음 git status로 확인하고, git add, git commit, git push를 통해 github 원격 저장소에 지킬을 통해 다운받은 파일들을 저장한다.

형식은 레이아웃과 타이틀 그리고 그 아래에 적힐 글로 구성된다. 글을 구성하고 나면 로컬저장소에서 push하여 원격저장소에 저장한다.

그렇게 하여 블로그를 만들어가는 것이다.
  
---

4. 테마 적용하기

4-1. 적용하고 싶은 테마를 찾는다. 이 블로그는 Clean Blog 테마를 적용하였다.

4-2. 적용하고 싶은 테마를 만든 사람의 깃허브 주소로 가서 fork를 통해 불러온다.

4-3. fork한 깃허브 주소의 이름을 <username>.github.io로 바꾼다.

4-4. 포스트를 fork한 테마에 맞추어 다시 작성하면 된다.
  
4-4-1. 내가 찾은 블로그는 post의 형식이 md가 아닌 html이다.

4-4-2. 따라서 html 형식에 맞는 글자 크기를 조절하기 위해서 html의 글자 크기를 조절하는 방법을 찾게 되었다.
  
~1.기본적으로 글자의 크기는 h1 ~ h6까지로 조절할 수 있다.
  
~2. h1이 가장 크고 h6이 가장 작다. 또한 이것들은 markdown형식의 글에서 #의 개수를 담당한다고 생각하면 된다.

~3.그것을 통하여 원하는 크기의 글자로 포스트를 작성할 수 있다.
  
~4.글의 한 문장이 끝나게 되면 h1과 같은 형식으로 글의 마지막에 작성한다.

~5.그렇게 하면 한 문장이 완성된다.
  
html형식을 사용해야 해서 살짝 당황했지만 다행히 글자 크기를 조절하는 법을 찾아서 무사히 끝마칠 수 있었다.

4-4-3 블로그의 post의 형식은 이러하다.  
---

layout: post

title: "제목"

subtitle: "소제목"

date: 날짜

background: '그림 파일' (이것은 추후에 설명할 블로그 테마와도 관련있음)

---
  
내가 찾은 블로그의 기본 형식을 이렇게 써져있었는데, 이것 중 background는 포스트 등의 배경화면을 설정해주는 문구이다.
  
이것을 통해서 배경화면을 설정하여 더 다채로운 포스트를 만들 수 있다.
  
---
  
5. 댓글기능 적용하기
  
5-1. 댓글기능을 적용하는 법은 일단 disqus에 가입하고, disqus의 절차에 따라 행동해준다.
 
5-1-1. 플랫폼을 선택하는 것에서는 jekyll을 사용하므로 그것을 선택해준다.
  
5-2. 모든 절차를 마치고 나면 _config.yml에 다음과 같은 코드를 작성한다.

comment:
  provider:         "disqus"
  disqus:
    shortname:      "kimdonguk-kmu"
  
5-3. 그 후 _layou/post.html에 들어간다.

5-3-1. disqus에 들어가 jekyll을 선택하면 나오는 Universal Code를 복사한다.
  
5-3-2. 다음과 같이 형식에 맞춰서 코드를 작성해준다.

{% if page.comments %}
<div id="disqus_thread"></div>
<script>
    /**
    *  RECOMMENDED CONFIGURATION VARIABLES: EDIT AND UNCOMMENT THE SECTION BELOW TO INSERT DYNAMIC VALUES FROM YOUR PLATFORM OR CMS.
    *  LEARN WHY DEFINING THESE VARIABLES IS IMPORTANT: https://disqus.com/admin/universalcode/#configuration-variables    */
    /*
    let Page_URL = "{{site.url}}{{page.url}}"
    let PAGE_IDENTIFIER = "{{page.url}}"
    var disqus_config = function () {
    this.page.url = PAGE_URL;  // Replace PAGE_URL with your page's canonical URL variable
    this.page.identifier = PAGE_IDENTIFIER; // Replace PAGE_IDENTIFIER with your page's unique identifier variable
    };
    */
    (function() { // DON'T EDIT BELOW THIS LINE
    var d = document, s = d.createElement('script');
    s.src = 'https://kimdonguk-kmu.disqus.com/embed.js';
    s.setAttribute('data-timestamp', +new Date());
    (d.head || d.body).appendChild(s);
    })();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>
{% endif %}
  
{% if page.comments %}와 {% endif %}는 if문과 같은 역할을 해준다. 이것을 작성하지 않으면 모든 포스트에 댓글 기능이 활성화된다.
  
<h2>Comments</h2> 코드를 통하여 큰 글씨로 댓글이라는 것을 표현하는 문구를 적어준다.
  
let Page_URL = "{{site.url}}{{page.url}}"
let PAGE_IDENTIFIER = "{{page.url}}"

위와 같은 문구를 적어 페이지의 댓글 기능을 활성화시켜줘야 한다.
  
그 다음 post의 형식을 적는 곳에서 아래와 같은 문구를 적어준다.
  
---

layout: post

title: "댓글 기능 적용"

subtitle: "Disqus를 통한 댓글 기능 활성화"

date: 2021-12-12 20:23:40 -0400

background: '/img/posts/05.jpg'

comments: true

---
  
위의 문구 중 comments: true를 통하여 이 포스트의 댓글을 활성화시켜준다.

저 코드를 적지 않으면 댓글이 활성화되지 않는다.
  
이 사실은 배운 것을 작성한 post와 나머지 post를 통해 확인할 수 있다.
  
이렇게 하면 댓글 기능이 활성화된다.

 
