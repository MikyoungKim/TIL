#### 1. Git bash에서 Git 익히기
- 설치해야할 것
    - Git bash
    - Visual Studio Code
    - Github 홈페이지에서 회원가입 후 Repository 하나를 만든다.

---
- 실습
    * 1단계: Git bash를 연다.  
        ```
        mkdir [directory명] 
        cd [윗줄에서 만든 directory명]
        ```
        을 통해 directory를 하나 만들어준다.      

    * 2단계: Gibhub에서 자신이 만든 새로운 Repository를 클릭해보면 
 
        ```
        echo "# [Repo 이름]" >> README.md
        git init 
        git add README.md
        git commit -m "first commit"
        git remote add origin [현재 repository의 URL]
        git push -u origin master
        ```
        라는 코드가 보이는데 이를 git bash 창에 한 줄씩 그대로 복사+붙여넣기하여 실행한다.
---
- 코드 설명
    - 1단계 해설
        >**_mkdir [디렉토리명]_**: make directory의 줄임말로, 흔히 윈도우에서 오른쪽 마우스를 눌러 _새폴더_ 를 생성하는 것과 같은 행위이다.

      >**_cd [디렉토리명]_**: change directory의 줄임말로, 윈도우에서 폴더를 더블클릭하여 폴더 내부로 이동하는 것과 같은 행위이다.
    - 2단계 해설
        >**_echo " " >> README.md_**: " "안에 있는 내용을 README.md라는 file을 만들어 그 안에 출력(저장)하라.  

        >**_git init_**: '내가 지금 _mkdir_ 이라는 명령어를 통해 만든 directory를 git이라는 명령(github 홈페이지와 연동되어 명령을 통해 파일들을 업로드 할 수 있는 명령어들의 집합)을 가능하도록 설정할게!'라고 말해주는 코드이다.

        >**_git add README.md_**: '나 _README.md_ 라는 파일을 만들었어. 그래서 이제 github 웹 페이지에 올릴 준비상태를 갖춰줘!'라고 명령하는 행위이다.  

        >**_git commit -m "first commit"_**: 실제로 웹상에 올라가게 하는 명령어이다. _-m_ 은 일종의 옵션으로 " "이라는 간략한 메시지를 통해 메모를 남기겠다는 것이다.  

        >**_git remote add origin [현재 repository의 URL]_**: 'remote(원격) 저장소 즉, 내 github에 만들어놓은 어떤 repository를 임의의 _origin_ 이라는 이름으로 칭할건데, 여기에 현재 내 컴퓨터 directory를 연결시켜줘'라는 의미이다. (이는 사실, _git init_ 직후에 수행해도 무관하다.)  
        
        >**_git push origin master_**: '이제 진짜 내 github 웹에 보이도록 동기화!!'  

    
