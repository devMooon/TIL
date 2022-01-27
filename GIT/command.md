커밋할 목록 보기
커밋한 목록 보기
git log에서 빠져나오기 :wq


cd ~ : 자신의 home 디렉토리로 이동.
mkdir [폴더명] : 디렉토리 생성.
cd [폴더명] : 디렉토리 안으로 이동.
ls -al : 디렉토리 내부의 모든 파일 리스트 보기. (숨김 파일도 다 보임)
pwd : 현재 디렉토리 경로 보기.
clear : cmd 초기화.
cp [원본파일] [복사후파일] : 원본파일을 새로운 이름으로 복사한다.


vim [파일명.확장자] : vim 프로그램에서 파일을 생성하고 편집한다.
i : vim 프로그램에서 입력모드로 전환.
esc : vim 프로그램에서 입력모드 해제.
:wq : vim 프로그램에서 저장하고 나가기.
cat [파일명.확장자] : 파일 내용 표시

​
git init : git 저장소 만들기 (현재 디렉토리에서 버전관리를 진행하겠다고 git에게 알림)
           .git 디렉토리가 생성된다.

​
git config --global user.name "자신의 닉네임"
git config --global user.email "자신의 이메일"    
: 버전에 포함될 정보를 설정. 이 설정은 ~/.gitconfig 파일에 저장되고 최초 1번만 설정해주면 된다.       
git config --global core.editor "vim" : vim 이 아니라 다른 에디터가 실행될때 vim 으로 설정한다.

git status : git 프로젝트 폴더의 상태 보기.
git add [파일] : 파일을 stage로 상태 전환.

git commit : stage에 올려진 파일을 커밋한다.
git commit -a : 파일을 stage에 올리고 커밋까지 한번에 처리한다.
git commit -am "메세지" : 파일을 stage에 올리고 커밋메세지까지 한번에 처리한다.
git commit --amend 
: 아직 push 하지 않은 상태의 마지막 커밋 메세지를 수정한다.
즉, 지금 커밋하려는 내용이 바로 직전 커밋하는 내용을 덮어쓰기 한다.


git log : 커밋한 로그를 보여준다.
git log -p : 로그에서 출력되는 버전 간 차이점을 출력한다.
git log [비교할 브랜치명1]..[비교할 브랜치명2] : 브랜치 간의 비교를 한다.
git log --branches --graph --decorate --oneline 
: 로그에 모든 브랜치를 표시하고, 그래프로 표시하고, 브랜치명을 표시하고, 한줄로 표시한다.
git log --reverse : 로그를 최신순이 아닌 오래된순으로 본다.


git diff : add 하기전과 add 한 후의 파일 내용을 비교한다.
git diff [버전id]..[버전id] : 버전 간의 차이점을 비교한다.
git diff [비교할 브랜치명1]..[비교할 브랜치명2] : 브랜치 간의 비교를 한다.


git reset --hard "버전id" : 버전id 로 돌아간다.
로컬의 커밋 내용을 모두 삭제하고 기록또한 삭제된다.
하지만, 원격 저장소에 푸쉬한 후에는 사용해봤자 의미가 없다.
업데이트가 뒤쳐진 상태로 변하게 될 뿐이다.
로컬에서 푸쉬 전 잘못된 커밋을 되돌리는 경우에만 사용해야 한다.

​
git reset --hard HEAD 
: 가장 최신 커밋상태로 이동하고 그 이후에 커밋되지 않은 작업중인 내용은 삭제된다.

​
git revert "버전id" : 커밋을 취소한 내용을 새로운 버전으로 만드는 명령.
지워진 버전의 기록이 계속 남는다.
원격 저장소에 푸쉬한 이후에도 그전 커밋 기록이 남고 새로운 버전으로 선언하기에
revert 명령어로 되돌아간 버전이 최신버전으로 인식되게 하며
다른 사용자로 하여금 업데이트를 받게 한다.

​
git branch : 브랜치 목록을 보여준다.
git branch [브랜치명] : 새로운 브랜치를 생성한다.
git branch -d [브랜치명] : 브랜치를 삭제한다.
git branch -D [브랜치명] : 병합하지 않은 브랜치를 강제 삭제한다.
git checkout [브랜치명] : 해당 브렌치로 전환한다.
git checkout -b [브랜치명] : 새로운 브랜치를 생성하고 전환한다.


git checkout [브랜치A] : 브랜치A 로 체크아웃 한다.
git merge [브랜치B] : 브랜치A로 브랜치B를 끌어와서 머지시킨다.

​
git stash : 현재 작업중인 파일을 stash save 한다. git add 된 파일들만 stash save 된다.
git stash save : 현재 작업중인 파일을 stash save 한다. git add 된 파일들만 stash save 된다.
git stash apply : stash save 된 파일을 다시 작업중인 상태로 전환한다.
git stash list : stash save 된 리스트를 보여준다. 위에 있는 것일수록 최근에 stash save 한 것이다.
git stash drop : stash save 된 리스트에서 가장 최신 목록을 삭제한다.
git stash pop : stash save 된 리스트에서 가장 최신 목록을 apply 하고, drop 한다.
​

git init --bare remote : 작업은 할 수 없고 저장소로서의 기능만 하는 remote 폴더를 생성한다.
git init --bare project.git : bare repo라고 불리는 이 저장소에는 실제 작업되는 파일, 디렉토리가 저장되는 것이 아닌
변경사항, 이력등의 revision history의 정보들이 저장된다. 이를 통해 누가 어떤 변경사항이 있는지 확인한다.
bare repo는 공유하기 위한 목적으로 생성한다. 다수의 작업자, 프로젝트 참가자의 변경사항을 공통으로
관리하기 위한 저장소로 사용할 수 있다.
원격 저장소를 만들때는 무조건 --bare 옵션으로 디렉토리를 만든다고 생각하면 된다.

​
git remote add origin /home/git/remote
: /home/git/remote 의 경로를 origin 이라는 별명을 사용하고 원격저장소로 등록한다.
git remote add origin https://github.com/..../gifth.git
: remote 를 url로 연결시키고 origin 이라는 별명을 사용한다.
git remote -v : 현재 등록되어 있는 원격저장소를 보여준다.
git remote remove origin : origin 이라는 별명을 가진 원격저장소를 삭제한다.
git config --global push.default.simple : 원격 저장소의 push 방식을 simple 방식으로 사용하겠다는 설정.


git clone https://github.com/git/git.git .
: url의 git 프로젝트를 현재 디렉토리(.)에 clone 한다.
git clone https://github.com/git/git.git gitsrc
: url의 git 프로젝트를 gitsrc 라는 디렉토리를 만들어서 clone 한다.

​
git push : 원격저장소로 푸쉬한다.
git push --set-upstream origin master : 현재 브랜치에서 push 명령을 하면 자동으로 origin의 master 브랜치로 push 하겠다는 설정.
git push -u origin master 
: 현재 브랜치를 origin 의 master 브랜치로 푸쉬한다.
이때 -u 는 처음에 딱 한번만 사용하면 된다. 
현재 로컬저장소의 브랜치와 origin의 master 브랜치를 연결시켜서 다음부터는 git push 만 하면
자동으로 푸쉬가 되도록 하는 옵션이다.
git push --force : 강제로 푸쉬한다. 원격저장소의 내용을 덮어씌운다.

​
git pull : 원격저장소의 내용을 로컬저장소르 내려받는다.


요약
git init : git 생성하기
git clone git_path : 코드가져오기
git checkout branch_name : 브랜치 선택하기
git checkout -t remote_path/branch_name : 원격 브랜치 선택하기
git branch branch_name : 브랜치 생성하기
git branch -r : 원격 브랜치 목록보기
git branch -a : 로컬 브랜치 목록보기
git branch -m branch_name change_branch_name : 브랜치 이름 바꾸기
git branch -d branch_name : 브랜치 삭제하기
git push remote_name — delete branch_name : 원격 브랜치 삭제하기 ( git push origin — delete gh-pages )
git add file_path : 수정한 코드 선택하기 ( git add * )
git commit -m “commit_description” : 선택한 코드 설명 적기 ( git commit -m “내용”)
git push romote_name branch_name : add하고 commit한 코드 git server에 보내기 (git push origin master)
git pull : git서버에서 최신 코드 받아와 merge 하기
git fetch : git서버에서 최신 코드 받아오기
git reset — hard HEAD^ : commit한 이전 코드 취소하기
git reset — soft HEAD^ : 코드는 살리고 commit만 취소하기
git reset — merge : merge 취소하기
git reset — hard HEAD && git pull : git 코드 강제로 모두 받아오기
git config — global user.name “user_name ” : git 계정Name 변경하기
git config — global user.email “user_email” : git 계정Mail변경하기
git stash / git stash save “description” : 작업코드 임시저장하고 브랜치 바꾸기
git stash pop : 마지막으로 임시저장한 작업코드 가져오기
git branch — set-upstream-to=remote_path/branch_name : git pull no tracking info 에러해결



git reset // add 한 파일 취소
git reset — -merge // merge 한 코드 취소

git reset — soft HEAD^ //commit 코드 살리기
git reset — hard HEAD^ //commit하기 이전의 코드로 돌아가기

git reset — hard HEAD // HEAD를 기준으로 이전코드로 돌아갑니다.
git pull // git 서버에서 코드를 다시 받아옵니다.



## 느낀점
***
리눅스 명령어와 정말 비슷하다! 2021년 2학기 때 전공과목으로 리눅스를 배웠는데 
*"정말 이걸 어디에 쓸까.."* 라고 생각했다. 쓸데가 있구나 역시...