# /dev/null

/dev/null 파일은 항상 비어있으며, /dev/null에 전송된 데이터는 버려짐.

### 파일 설명자

리눅스 운영체제가 특정 파일에 접근할 때 사용되는 값을 의미

- 0 : 표준 입력
- 1 : 표준 출력
- 2 : 표준 오류 출력

```bash
# 표준 출력만 무시
$ echo Hello World

# 표준 오류 출력만 무시
$ script.sh 2> /dev/null

# 표준 출력과 표준 오류 출력 둘 다 무시
$ echo Hello World > /dev/null 2>&1
```

표준 출력과 표준 오류 출력 방향을 지정하여 파일로 저장 가능

```bash
$ echo Hello World 1> ok.txt

$ script.sh 2> fail.txt

$ echo Hello World 1> ok.txt 2> fail.txt

$ echo Hello World 1> /dev/null 2> fail.txt
```

# References

[ standard input-output-error ] https://www.ibm.com/docs/ko/aix/7.1?topic=redirection-standard-input-standard-output-standard-error-files
[ file descriptor ] https://bio-info.tistory.com/86