1. git을 통한 원격 저장소 github 배우기

1-1.먼저 로컬 저장소에서 ruby와 jekyll을 다운받는다.

1-2.jekyll new . --force로 지킬과 연결한다.

2. 그 다음에 bundle exec jekyll serve 로 지킬을 활용한 블로그를 완성한다.

2-1.생성하게 되면 폴더에 생겨있는 많은 파일들 중에 "_config.yml" 파일의 타이틀 등을 수정한다.

2-2.그 다음 git status로 확인하고, git add, git commit, git push를 통해 github 원격 저장소에 지킬을 통해 다운받은 파일들을 저장한다.

3. 블로그가 생성되면 _posts 칸에 포스트를 생성한다.

###
layout : "형식"

title: "제목"

date: "날짜"

제목

글
###
3-1.이 형식으로 포스트를 작성하여 YYYY-mm-dd-"파일이름".md로 저장한다.

3-2.그 다음 git status로 확인하고, git add, git commit, git push를 통해 github 원격 저장소에 지킬을 통해 다운받은 파일들을 저장한다.

형식은 레이아웃과 타이틀 그리고 그 아래에 적힐 글로 구성된다. 글을 구성하고 나면 로컬저장소에서 push하여 원격저장소에 저장한다.

그렇게 하여 블로그를 만들어가는 것이다.
