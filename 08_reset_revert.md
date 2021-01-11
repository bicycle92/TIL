# reset vs revert

## revert

```
$ git log --oneline
1f7fb86 (HEAD -> master) Add omit.txt and d.txt
8645fc8 Add c.txt
4bacb2d Complete
9b54031 Add a.txt
$ git revert 8645fc8
Removing c.txt
hint: Waiting for your editor to close the file..[master ba71fdc] Revert "Add c.txt"
 1 file changed, 0 insertions(+), 0 deletions(-)
 delete mode 100644 c.txt
$ git log --oneline
ba71fdc (HEAD -> master) Revert "Add c.txt"
1f7fb86 Add omit.txt and d.txt
8645fc8 Add c.txt
4bacb2d Complete
9b54031 Add a.txt
```

![12312312312312](C:%5CUsers%5C%EB%B0%B0%EA%B2%BD%EB%A5%9C%5CDesktop%5C12312312312312.png)

## reset

> 공개된 저장소에 push가 된 경우 주의할 것

```
$ git reset --hard 1f7fb86
HEAD is now at 1f7fb86 Add omit.txt and d.txt

$ git log --oneline
1f7fb86 (HEAD -> master) Add omit.txt and d.txt
8645fc8 Add c.txt
4bacb2d Complete
9b54031 Add a.txt
```

- 옵션
  - 기본(--mixed) : 변경사항을 SA에 보관
  - --soft : 변경사항 및 WD 내용까지 모두 보관
  - --hard : 모든 변경사항을 삭제 **주의**