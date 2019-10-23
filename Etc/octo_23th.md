# Git 명령어

git init : git 생성
git branch branch_name : 브랜치 생성
git checkout branch_name : 브랜치 선택
git checkout -t remote_path/branch_name : 원격 브랜치 선택
git branch -d branch_name : 브랜치 삭제하기
git push remote_name ? delete branch_name : 원격 브랜치 삭제 ( git push origin ? delete gh-pages )
git branch -r : 원격 브랜치 목록보기
git branch -a : 로컬 브랜치 목록보기
git commit -m “커밋 내용” : 커밋 메시지 적기
git push romote_name branch_name : add하고 commit한 코드 git server에 보내기 (git push origin master)
git pull : git 서버의 현 브랜치에서 최신 내용 받아오기

git reset ? hard HEAD^ : commit한 이전 코드 취소하기
git reset ? soft HEAD^ : 코드는 살리고 commit만 취소하기
git reset ? merge : merge 취소하기
git reset ? hard HEAD && git pull : git 코드 강제로 모두 받아오기
git stash / git stash save “description” : 작업코드 임시저장
git stash pop : 마지막으로 임시저장한 작업코드 가져오기
git branch ? set-upstream-to=remote_path/branch_name : git pull no tracking info 에러해결