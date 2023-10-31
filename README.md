# R_study
R program study

<1주차>
# R의 기본 연산 

## 기본 연산
       나머지 파이썬과 동일 -%% : 나눗셈의 나머지 
                            -^/**: 제곱
## 산술연산 함수 
        log/sqrt/max/min/abs/factorial/sin,cos,tan
        sample: 표본 자동 생성  
               - sample(5) : 다섯개의 임의의 수 
               - sample(1:10,3):1부터 10까지의 범위를 정해줌 + 해당 범위 중 3개의 값 랜덤

# 변수 

## 자료형
           숫자형/ 문자형(따음표 쓰기)/논리형(대문자 첫 글자로도 표현 가능 T/F)
           특수값
                   -NULL: 정의되어 있지 않음
                   -NA: 결측값(누락된 값) 
                   -NAN: 수학적으로 정의가 불가능한 값=> SEQ(-3): -3의 제곱근 수학적 정의 없음
                   -Inf/-Inf: 양/음의 무한대
## 자료형 이용 함수
                 class(): 유형 파악 
                 is. numeric/character/logical/null():판별,T/F로 값이 나옴

# 벡터

## 벡터의 이해
                 <-c(): "하나의 벡터에는 동일한 종류의 자료형이 저장되어있음"
                        (숫자형과 문자열이 같이 있을 경우=> 문자열로 바뀜)
## 벡터 만들기
                   1) 연속적인 숫자로 이루어진 벡터(:)
                           a<-c(1:100), a<-c(1:100,500:510) -,로 이어지는 숫자 이어갈 수 있음
                           -단, 하나의 이어지는 숫자 1:100은 c없이 그냥 표기 가능 
                   2) 일정한 간격의 숫자로 이루어진 벡터(seq)
                   -정석: a <-seq(from="어디서부터",to="어디까지",by="어떤 간격으로")
                     -from,to,by:생략 가능
                     - a <-seq(1,100,1ength.out=) 
                             :1부터 100까지 "length.out"에 입력된 값만큼의 간격으로 나눠달라
                                                                (소수점으로 나올 수 있음)
                 3) 반복되는 숫자로 이루어진 벡터(rep)
                   -a<-rep("반복대상","횟수")
                     -a <-rep(c("a","b"),times=10): ab의 묶음으로 10번
                            (따라서 총 20개의 값이 결과로 나옴)/times 생략 가능
                   -a <-rep(c("a","b"),each=10): a,b 각각을 10개씩 반복
                     -a <-rep(c("a","b"),length.out=): 이때 length.out은 total 거리를 의미함
## 벡터의 이해
                 1) 벡터의 원소 값에 이름 지정(names())
                 2) 벡터에서 원소 값 추출: 인덱스 이용 
                   -d[1]:파이썬과 달리 1부터 시작함. 
                     -d[-n]: n번째의 원소를 제외하고 나열.
                 3) 여러 개의 값을 한번에 추출하는 방법: 콜론(:),seq함수, 벡터 
                      -d[-c(3:5)]: 3~5번째 값은 제외하고 출력
                      -d[seq(1,5,2)]:1번째 5번째 값 중에서 2씩 뛰어넘으면서 (1,3,5번째 출력)
                      -d[c(1,3,5)]:1,3,5번째 값 출력                                      
                          
## 벡터에서 저장된 원소 값 변경 
               1) d[2]<-10: d라는 변수의 2번째 값을 10으로 변경
               2) d[c(1,4)]<-c(20,30): 1,4번째 원소를 20과 30으로 각각 변경 
## 벡터의 연산 
               1) 벡터와 벡터 연산하기 위해서는 두 벡터의 길이가 같아야한다.
               2) 여러 개의 벡터를 합쳐 새로운 벡터를 만들기 위해서 c()함수 사용
                 -a<-1:2/b<-c("a","b")/c<-c(a,b)=> 1,2,"a","b"
               3) sum/max,min/length/mean=평균/median=중앙값/var= 분산
                 /sd= 표준편차/sort=오름차순/range=범위/length=벡터에 값들의 개수  (길이)
                  -sort(a(매개변수 값),decreasing = FALSE(orF))/sort(a): a라는 변수 오름차순
                -sort(a,decreasing=TRUE(orT))/sort(a,TRUE): 내림차순                                                         
                4) 논리연산자: A|B:A또는 B 한쪽이라도 T면 T,A&B:모두 일때만 T


<2주차>
▶ 여러 종류의 자료가 섞인 것. 
# 리스트
## 리스트 vs 벡터
      1) 리스트: 서로 다른 자료형의 값들을 1차원 형태로 저장
      2) 벡터: 동일한 자료형의 값을 1차원 형태로 저장
## 리스트
      1) x <- list ( )의 형태
      2) 벡터와는 달리 [[1]] 대괄호가 두 개인 형식으로 나오게 됨
        - list 해당 ‘값’을 찾고 싶으면 [[ ]], 대괄호 두 개 적어야됨. 
      3) names( ) <- (  )하면 list의 각 값에 이름 정할 수 있음 
        -$(지정한 이름)을 하면 해당 값이 나옴
         -이름 정해주는 방법: 

        
         -리스트에서 값을 출력하는 방식:    


# 팩터
## 팩터 
     1) 문자형 데이터가 저장된 벡터의 일종
     2) 문자형 벡터를 만든 뒤 factor() 함수 이용 변환 
     3) LEVELS: 팩터에 저장된 값들을 요약해서 보여주는 것. 
        - 추가하고 싶을 때 다른 것들과 동일하게: x [(넣고싶은 순서)] <-‘   ’
        - level 안에 있는 값만이 추가될 수 있음. else error
     4) summary(factor 이름): 팩터 값을 요약해준다. 
       ex) A가 두 개 있다.

#### EXTRA
예시2) TRUE =1,FALSE=0 => 110보다 작은 값의 개수라고 하면 sum(d<110): True 개수 세면 됨
       d[[d<110]]: d의 벡터 중에서 110보다 작은 값이 나옴

# 매트릭스와 데이터프레임
## 1차원 데이터, 2차원 데이터
     
-내장된 함수 View(  ) 볼 수 있음

 # 매트릭스 
##  매트릭스
     1) x<-matrix( (데이터:무엇을 넣을건지), (행의 수), (열의 수) )
       -데이터와 행열의 양은 같아야. 
        -일반적으로 열의 방향으로 채워짐: matrix(  , nrow= , ncol= ) 
        -행의 방향으로 채우기 위해서: matirx(  , nrow= , ncol= , byrow= TRUE)
        - matrix(1:20,2)까지만 해도 열은 알아서 채워짐. 하지만 나눠떨어지지 않는 경우 error 
             (데이터 값 뒤에 무조건 행부터 넣을 필요 없지만 단, ncol 즉 열이라고 명시해줘야함.)
     2) 모든 셀에 저장되는 값은 ‘동일한 자료형’이여야
     3) 값 추출하고 싶다면 x[행, 열] 
       -x[1, ]은 첫 번째 행의 모든 값, x[ ,1]은 첫 번째 열의 모든 값
             (둘 다 비우는 경우는 x[ , ] but 그냥 x만 쳐도 됨.)
         -x[1, 2:4]: 1행의 값 중에서 2~4열에 있는 값
        -x[c(1,3), ]:1,3행에 있는 모든 값
      4) length(x): 칸의 개수/dim(x): 행과 열의 개수
                           -dim(x)[1]:행의 개수/ dim(x)[2]: 열의 개수
                              -or ncol(x)/nrow(x)
## 매트릭스 만들기 
     1) z<- cbind(x,y): 두 개의 벡터를 열의 방향으로 묶는다. 
     2) z<- rbind(x,y): 두 개의 벡터를 행의 방향으로 묶는다. 
      -cbind( , ,matrix( , , ,)): cbind된 것 옆에 matrix 붙이기(rbind는 아래로)
         (벡터 + 매트릭스/매트릭스 + 매트릭스)
## 매트릭스 행/열에 이름 지정
     1) rownames(x)<-c(   ): 행에 이름 지정 
     2) clonames(x)<- c(   ): 열에 이름 지정
     3) rownames(x):x 행의 이름/colnames(x):x 열의 이름
      -rownames(x)[2]: x행의 이름 중 두 번째 이름, x[‘a ’, ]: a행의 모든 값




<3주차>

# 데이터프레임 
## 데이터프레임
    1) 서로 다른 자료형의 값들이 저장됨
    2) x<- data.frame( )형태
    3) matrix와 동일한 형태로 행과 열의 이름 넣을 수 있음. 
      -x$English: 해당 행에 있는 값들이 나옴
    4) str(x): 데이터프레임의 정보를 알려주는 것
    5) matrix와 데이터프레임은 서로 변환이 가능하다.
      - b <- as.data.frame(a)/ c <- data.frame(a)
      - d <- as.matrix(b)
      - 단, 데이터프레임의 모든 값의 자료형이 동일해야 매트릭스 변환 가능
              (따라서, 일부만 변경 가능)
    6) matrix와 동일하게 cbind/rbind함수 사용
      -x$(x라는 데이터프레임에 지정되지 않은 것): cbind와 동일
    7) matrix와 값 추출 방식이 동일하다 

# 매트릭스와 데이터프레임
## 매트릭스와 데이터프레임 산술연산
    1) 숫자로 구성된 m/d 산술연산 가능
    2) 자료 상 동일 위치 값끼리 계산 
    3) 자료구조의 행과 열의 개수가 동일해야 함.
             (a*2: a값 변경되지 않음/ a<-a*2: a값이 변경됨)

## 매트릭스와 데이터프레임 함수
     dim()/nrow,dim()[1]/ncol(),dim()[2]/rownames()/ncolnames()/str()/class()
     /is.matrix(), is.data.frame()
     -head(): 데이터셋의 시작 부분의 일부 데이터 출력(1~6행)
             (처음 보는 데이터와 같은 것 어떻게 생겼는지 파악하기 위한 용도)
     -tail( ): 데이터셋의 끝 부분의 일부 데이터 출력(n-5~n행)
     -unique( ): 어떤 그룹을 자료에서 중복된 값 제거하여 출력
               (LEVEL이 나옴)
     -table( ): 자료에서 각 그룹별로 몇 개의 관측치가 존재하는지 출력
     -colSums(): 열별 합계/rowSums(): 행별 합계
     -colMeans(): 열별 평균 /rowMeans(): 행별 평균
     -t(): 행과 열의 방향 바꿈 = 전치 행렬
     -subset(): 전체 데이터에서 조건에 맞는 행들만 추출(데이터프레임에서만 사용 가능)
                  x<-subset( (데이터 추출 대상),(조건-2개 조건 &로 연결) )
      
  cf) x[ ,“A”]:데이터프레임으로 결과 나옴/ x$A: 벡터 형태로 결과



<4주차>
# 데이터의 입력과 출력
## 출력(화면)
   1) 원칙적으로 print 함수 쓰는 것이 맞지만 R에서 변수명으로도 값이 출력됨
    2) print(): 여러 개의 변수 값을 cat( )과 달리 쓰지 못한다. 
              -print(“가장 젊은 사람의 나이는”,{변수명},“이다.”) => error
               -자동 줄 바꿈이 이루어진다. 
    3) cat( ): 여러 개의 변수를 옆에 붙여쓸 때 쓰는 함수이다.
             -한 줄 띄우고 싶지 않은 경우에  
              -출력하고 싶은 것 cat 이용하여 동시에 출력하면 이어서 출력됨
              -줄 바꿈을 하고 싶다면 “\n” 뒤에 붙여주기
## 입력(화면)
    1) install.packages(‘svDialogs’)
       library(svDialogs)  => 패키지 설치 
     -> [변수명]<-dlgInput(    )$res=> “$res”
             -입력받은 것은 항상 문자로 받게 됨.  
               -$res 쳐야 그 값이 나오게 할 수 있음
## 입력(파일)
     1) getwd( ): 현재 작업하고 있는 파일의 위치를 나타냄
     2) setwd( ): 새로운 작업 형태로 저장. (작업 폴더 변경하기) 
               -원하는 곳 ctrl c,ctrl v, 역슬레쉬로 바꾸기
## 읽기/쓰기 (파일)
    ### csv 파일 읽기 
        1) (변수명) <-read.csv(‘자료명’, header=T)
             - header: 열 이름처럼 생긴 것 -> header 정보
             - header = F인 경우는 header이 없을 때 
             - 있는데 없다고 해버리면 하나의 데이터 값으로써 header 정보가 들어가게 됨

   
        2) View(head/tail(변수명)): 해당 데이터의 위/아래에서부터 5~6번째 줄만 보여줌
           class( ) 등 파일을 알아보는데 사용될 수 있음. 
      ### csv 파일 쓰기
          setwd( ): 작업 폴더 지정 후 
        1) write.csv(변수명, ‘파일 이름’): 해당 파일의 row에 데이터 값만큼 숫자가 써짐. 
        2) write.csv(변수명, ‘파일 이름’,row,names =F): row에 적힌 행 번호들이 사라짐. 
      ### 엑셀(.xls,xlsx) 파일 읽기
          패키지 설치(install,package).패키지 불러오기(library)
        1) 변수명<- read.xlsx(‘해당 파일’, fileEncoding = "CP949“ (파일 안에 한글 데이터 있는 경우), header= T(파일의 첫 번째 행은 데이터 값이 아닌 열 이름))
            -sep = ‘\t’: 데이터와 데이터 tab으로 떨어져있음.
      ### 엑셀 파일 쓰기
            library(파일 불러오기)
        1) write.xlsx(넣을 데이터 명,”파일 이름.xlsx“, row.names =F(행 번호 제외해라))
         
      ### txt 파일 읽기
           


 <5주차>
for/while


<6주차>



 
