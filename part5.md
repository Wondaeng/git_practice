# git restore

파일 하나를 최근 커밋 상태로 되돌리기:
`git restore <파일명>`

특정 커밋 시점으로 되돌리기:
`git restore --source <커밋ID> <파일명>`

특정 파일 스테이징 취소하기:
`git restore --staged <파일명>`


# git revert 
커밋 단위 복구
Git은 커밋을 삭제/조작하는 기능이 없음 (깃 자체가 기록을 위해 설계된 것으로, 커밋 삭제는 핵심 정신에 위배되는 행위임)

다만, 특정 커밋에서 작업했던 내역을 취소하는 커밋을 추가하는 것은 가능
(주의: B의 이전 상태로 돌아가는 것이 아닌, B에서 있었던 변화를 반대로 추가/제거 하는 것)

따라서, 이 작업 또한 conflict가 발생할 수 있음

`git revert <커밋ID>`
`git revert HEAD`

여러게도 입력 가능:

`git revert <커밋ID> <커밋ID> ...`

merge로 생성된 커밋도 취소가능

# git reset
특정 커밋이 생성된 시점으로 모든 것을 되돌림
`git reset --hard <커밋ID>`

**협업시엔 사용금지**

`--soft`: 변동사항 지우지 말고 staging 상태로 남아있음

`--mixed`: 변동사항 지우지 말고 unstage 상태로 남아있음