aaaaaaaaaaaaaaa

`git diff`: staging에 들어간 파일들(index)과 현재 working directory의 파일들을 비교 (cf. HEAD)

```
[ Working Tree ]  →  [ Index (Staging Area) ]  →  [ Repository (HEAD) ]
```

```
diff --git a/part2.md b/part2.md
index 05b287f..95ccaa7 100644
--- a/part2.md
+++ b/part2.md
@@ -1 +1,4 @@
-aaaaaaaaaaaaaaa
\ No newline at end of file
+aaaaaaaaaaaaaaa
+
+```git diff```
+
```

근데 난 aaaa... 라인을 수정한 적이 없는데, 왜 수정했다고 나오지?
--> 뒤에 다른 라인들을 추가하는 과정에서 aaa... 라인에 엔터를 입력했기 때문에 다른 라인으로 인식 됨

그래서 터미널로 보기도 불편하고.. 이런저런 문제점 떄문에 `git diff`를 쌩으로 쓰는 경우는 잘 없음

`git difftool` vim으로 더 깔끔하게 보여줌
`git difftool <commit_id>` 

근데? 사실 이거도 잘 안씀. VS Code extension ㄱㄱ