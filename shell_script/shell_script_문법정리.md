### Shell script 기초 문법정리
1.  그때그때 공부하는 문법들
    * <pre>> 와 >>의 차이</pre>
        * <pre> >는 뒤에 입력하는 파일을에 내용을 덮어쓴다. 
            (그 파일이 기존에 없었다면 새로 생성하여 저장)
        * <pre> >>는 내용을 덮어쓰는 것이 아니라 "추가"한다.
    * **echo vs printf**
        * echo는 자동개행(자동줄바꿈)하여 출력해준다.
        * printf는 자동개행 없이 출력한다.
        <pre>
    * **Hello world 출력하기**
        * step (i):
            ```bash
            $ touch hello.sh
            $ echo "hello world"
            ```
        * step (ii): 만든 .sh 파일 실행하기
            ```bash
            $ bash hello.sh
            ```
    <pre></pre>        
    * **Function(함수) 코드 작성하기**
        ```bash
        # 첫번째 방법(function을 선언하지 않는 작성방식)
        $ test_function_1() {
            echo "test"
        }

        # 두번째 방법(function명 앞에 function을 기입하는 작성방식)
        $ function test_function_2() {
            echo "test2"
        }

        # 함수 호출 방법
        test_function_1
        test_function_2
        ``` 
    <pre></pre>

    * **변수**
        * 변수사용방법? **=** 기호를 양 옆 공백없이 기입한다.
            ```bash
            # 전역변수 할당하기
            test_global_var="hello world"

            #지역변수 할당하기
            local test_local_var="hello world 2"
        * 위치매개변수
            * ```$0 ```: 현재 shell script 명
            * ```$#```: 매개 변수의 총 개수
        * 배열(Array Variable) (반드시 괄호 사용할 것)
            ```bash
            # 여러 개의 배열 값(요소) 지정
            array=("This" "is" "test" "array" "variable")

            # 요소추가
            array[5]="Fighting!!"

            # 요소 삭제
            unset array[4] #"variable"이라는 요소가 삭제될 것임.
            
            # 배열 출력 해보기
                # 1. 특정 요소만 출력하기 (ex. "test" "array"만)
                echo "${array[2]} ${array[3]}"
                # 2. 배열 전체요소 출력
                echo "${array[@]}"    
                # 3. 배열 요소 개수 출력
                echo "${#array[@]}"

            # array 전체 삭제를 하고 싶다면?
            unset array           
            ```
    * **반복문**
        ```bash
        # for문
        for word in "This" "is" "a" "script"; do
            echo ${word}
        done   
        
        # while문
        number=1
        while [ ${number} <= 5 ]; do
            echo ${number}
            number=$(( ${number}+1 ))
        done

        # until문: while문과는 대조적으로,  조건이 false일 때 실행된다.
        number_2=10
        until [ ${number_2} <= 5 ];do
            echo ${number_2}
            number_2=$(( ${number_2}-1 ))
        done

    * **조건문**
        ```bash
        word_1="practice"
        word_2="shell"
        word_3="script"
        # if, elif, else - fi
        if [ ${word_1} == ${word_2} ]; then
            echo "the same_1"
        elif [ ${word_1} == ${word_3} ]; then
            echo "the same_2"
        else
            echo "the same_3"
        fi
        ```

        ```bash
        # And문
        if [ ${string1} == ${string2} ] && [ ${string3} == ${string4} ]

        # Or문
        if [ ${string1} == ${string2} ] || [ ${string3} == ${string4} ]

        ```
