Line 1 

# Git 시작
```git init```

# Git 파일 추가
```git add <file_name>```

# Git 파일 커밋
```git commit -m <commit_message>```

### 왜 굳이 add와 commit, 두 단계로 나누어 놓았는가?

모든 파일을 항상 기록할 필요가 없기 때문 (e.g., static 이미지 파일). 필요에 따라 버전 기록에 포함시키고 싶은 파일만 선택해서 추가(add), 고른 파일들을 기록(commit)하는 것.  
  
이렇게 `git add`를 통해 커밋할 파일을 고르는 과정을 `staging`이라 하며, 해당 파일들이 놓이는 공간을 `staging area`라고 부름.  
  
`git commit`을 통해 staging 되었던 파일들은 `repository`로 옮겨짐.