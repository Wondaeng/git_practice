협업을 하거나 큰 변경점이 있는 작업을 할 때,
복사본을 만들어서 먼저 실행을 해보고 원본 파일에 반영하는게 안전.

이떄 사용 하는 것: Branch

e.g., 쇼핑몰 만드는 중
<랜딩 페이지>
<위젯>
<버튼>
등등...

쿠폰 기능을 추가하고 싶음
`git branch <이름>` --> 현재 HEAD가 가르키고 있는 커밋의 사본을 만듦 (정확히는 HEAD가 가르키는 커밋을 가르키는 포인터를 하나 더 만드는 것)

`git switch <이름>` --> HEAD가 <이름> 포인터를 가르키게 함

- main branch only feature 1
- main branch only feature 2

coupon 기능이 잘 동작해서, main branch에 이제 합치고 싶음
1. 병합의 기준이 되는 branch로 이동 (main)
2. `git merge <합칠 branch 명>
여기서 두가지 경우 발생:
- 각 브랜치에서 각각 다른 파일만 수정했을 때: merge 바로 끝
- 같은 파일의 같은 줄을 수정했을때: 충돌(conflict) 발생: 직접 해결해줘야함