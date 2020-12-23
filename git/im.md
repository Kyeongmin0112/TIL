# git - intermediate

## branch

### 브랜치 생성하기(git branch <name>)

origin의 변경사항을 파악하거나 협업이 필요하거나 코드 수정사항이 필요할 때 branch를 생성해 편하게 사용이 가능하다.

```
$ git branch <name> # name이라는 branch 생성
```



### 브랜치 확인하기(git branch)

branch를 생성 후에 제대로 생성이 되었는지 혹은 head가 어디 위치에 있는지 파악할 수 있는 명령어.

```
$ git branch  # 밑에 하위목록이 생성되며 브랜치 목록을 확인 가능
```



### 브랜치 옮기기(HEAD 움직이기)

head를 branch로 이동하기 위해 필요한 명령어.

```
$ git switch <name>  # name으로 이동
$ git checkout <name> # name으로 이동(위와 동일)
```

보통 branch를 만들고 바로 이동하기 때문에 아래와 같이 사용하는 경우가 많다.

```
$ git switch -c <name> # name을 생성하고 이동
$ git checkout -d <name> # name을 생성하고 이동
```



### 브랜치 합치기(git merge)

branch name에 있는 저장사항들을 master에 합치기 위한 명령어이다. master가 제일 상위 개념이고 나머지 branch들은 하위 개념이기 때문에 master가 다른 branch들을 흡수해야 한다. 또한, merge를 할 경우엔 한 갈래로 가기 때문에 자동적으로 commit이 된다.

```
$ git switch master  # branch가 아닌 master로 이동
$ git merge <name>    # <name>을 master가 흡수
```

branch가 master를 흡수하는 경우 큰 문제가 생길 수 있기 때문에 주의할 것.

branch들과 master의 관계를 보고 싶다면 아래의 명령어를 쓰도록 한다. 아래의 명령어를 쓸 경우, 대략적인 그래프로 파악할 수 있다.

```
$ git log --pretty=format:"%h %s" --graph
```



### 브랜치 삭제하기(git branch -d <name>)

branch를 master와 merge 후에는 branch를 지워야 한다.

```
$ git branch -d <name> # 이후 <name>을 지운다.
```



### 자료 받기(clone)

github에 있는 코드나 자료를 처음 받을 때 clone 명령어를 사용한다.

```
$ git clone <URL> # 처음 이용하는 사용자의 컴퓨터에 저장된 폴더와 자료를 다운 받을 수 있다.
```

아무것도 없다면 홈(cd ~)위치에서 clone을 사용한다.



### 추가

추후 프로젝트를 진행하면서 더이상 파일이 필요없을 때

```
$ touch .gitignore
```

위의 명령어를 이용하면 정보를 untrack 할 수 있다.

https://gitignore.io 사이트에 들어가면 사용하는 언어대로 untrack할 수 있다.