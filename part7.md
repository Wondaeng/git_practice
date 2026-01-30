원격 저장소로 협업하기

`git clone 저장소주소.git`: 저장소 다운로드/클론

다른 팀원이 최근 git push를 했으면 나는 git push를 할 수가 없음..

무슨 소리냐? 원격 저장소에 이미 새로운 변화가 생겼으므로 내가 로컬과 이미 달라졌고, 로컬에서 만든 변경 사항을 push할 수 없음

먼저 `git pull`로 로컬 작업환경을 동기화 한 후에 `push`해야함
`git pull 원격저장소주소 브랜치명`

pull = fetch + merge(or rebase) --> 원격 커밋을 가져와서, 내 커밋과 합침

fetch를 통해 원격 브랜치를 내 로컬로 가져옴 (origin/main) 그리고 이 로컬 브랜치를 내 대상 브랜치와 merge하는 것