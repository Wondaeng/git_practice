다양한 git merge 방법

## 3-way
저번 시간에 했던거:
branch 마다 신규 commit이 하나 이상 있는 경우,
새로운 commit을 생성하며 main branch로 merge 했었음

```
        C (coupon)
       /
A ─── B (main)
```

왜 이름으 3-way 인가?

A: 공통조상 (merge base)
B: 현재 브랜치 (HEAD -> main)
C: 합칠 브랜치 (coupon)

B와 C만 비교하면 어디가 변경이고 어디가 원래 같던 부분인지 모름

## Fast-forward
새로 만들어진 branch에만 새 commit이 있고, 기존의 main branch에는 commit이 없는 경우

그냥 main -> 새 브랜치의 포인터가 가르키고 있던 최신 커밋을 가르키게 함 (즉, 새 브랜치가 main 브랜치가 됨)

이게 싫은 경우: `git merge --no-ff 브랜치명` 으로 강제로 3-way merge 사용 가능

머지 완료된 branch(포인터)는 `git branch -d 브랜치명`으로 삭제 가능 (다만 커밋은 그대로 남아있고, orphan 커밋이 됨. 추후 gc에 의해 지워잠)

소문자 플래그 `-d`는 merge가 어딘가 완료된 branch만 삭제가능 (safe delete)
잘못 만든 브랜치를 (어디에도 merge하지 않고) 지우려면 `-D` 사용

## Rebase
브랜치의 시작점을 옮길 수 있음

```
        C1 ─── C2
       /
A ─── B1 ─── B2
```
-->
```
                C1 ─── C2
               /
A ─── B1 ─── B2
```
이 다음 fast-forward merge
```
A ─── B1 ─── B2 ─── C1 ─── C2
```

이유: 히스토리가 읽기 쉬워짐

단점: 기존 커밋을 다른 기준점에 다시 이어 붙여 적용하므로 conflict가 날 확률이 높음 

cf. merge를 하는 경우:
1. 중심 브랜치(머지 기준)로 이동
2. `git merge <새로운 브랜치명>`

반면, rebase는:
1. 새로운 브랜치로 이동
2. `git rebase <중심 브랜치명>`
3. 메인 브랜치로 이동
4. fast-forward merge

## Squash
Branch가 많아지면 3-way merge를 할수록 커밋 내역이 더러워짐 
github에서도 main의 commit 내역을 확인할때, 합쳐진 branch의 commit 내역이 보임 (선으로 연결되어있으면 다 보여줌)
--> 선을 끊으면 됨 (rebase나 squash)

squash and merge
`git merge --squash <새브랜치>`

새브랜치의 commit들을 다 합쳐서 하나의 커밋으로 만들고,
main branch에 새로운 커밋으로 붙여줌

* 협업 시에는 branching/merge 가이드를 따라야함