---
title: 자주쓰는 CLI명령어
date: 2017-07-17 14:55:23
categories: 
- ETC

tags:
- CLI
- 터미널
- CMD
thumbnail: https://tuhbm.github.io/images/bnr-etc.jpg
---
# cli 명령어

ls : 리스트출력

ls -l : 리스트 출력(사용권한,소유자,그룹,크기,날짜등 상세정보 출력)

ls [폴더명]/ : 입력한 폴더의 리스트 출력

cd [폴더명] : 입력한 폴더로 이동

cd ~ : Desktop 폴더로 이동
<!-- more -->
cd .. : 한단계 상위폴더로 이동

mkdir [폴더명] : 폴더 생성(띄어쓰기 하고 칠경우 여러개 생성 가능)

touch [파일명] : 입력한 파일생성(띄어쓰기 하고 칠경우 여러개 생성 가능)

mv [파일명] [폴더명/파일명] : 파일을 입력한 폴더로 이동

mv [파일명] [변경될파일명] : 현재파일을 입력한 파일명으로 변경

pwd : 현재 작업중인 폴더의 절대경로가 출력

vim [파일명] : 파일을 수정할수있다.(저장하고 나가려면 ESC키를 누른 후 :wq{Write Quit} 명령어 실행)

vimtutor : vim튜토리얼

cat [파일명] : 파일내용확인

cp [폴더명/파일명] [복제될파일명] - 폴더에 파일을 현재 폴더에 복제한다

cp -R [복제될폴더명] [복제된폴더명] - 파일을 복제한다(파일도 가능)

rm [파일명] : 해당 파일을 삭제(폴더불가능)(띄어쓰기 하고 칠경우 여러개 삭제 가능)(*.[파일종류]를 입력하면 해당 파일 종류 모두를 삭제한다)

rmdir [폴더명] : 폴더삭제(단, 빈폴더가아닐경우 삭제안됨)

rmdir —help : rmdir 삭제 도우미

rm -rf [폴더명] : 비어있지 않은 폴더 삭제

rm —help : re명령어 도우미


