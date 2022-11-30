---
layout: post
title:  "구조체 기초(Structure)"
---
  1. 구조체  
    - 다양한 정보를 저장할 수 있는 맞춤형 데이터 타입을 만든다. 
    - 배열은 정보를 저장하기에 적합 x / 배열의 쓰임 조건 : 데이터 타입이 같고, 연관되 있는 정보여야 한다.    
    
  2.구조체 저장   
    (1)  
      - struct를 선언을 했다고 데이터가 저장되는 것은 x   
      - 구조체 변수 b를 선언해야 b 데이터 공간에 구조체 Sample 변수들을 저장할 수 있다.

      Struct Sample {  
        int var1;
        int var2;
        char var3;}  
       int main () {  
        int a;
        struct Sample b; }  
         
- 메모리 공간 상황  




  
    (2)   
      - 구조체 변수를 통해 값 저장 : 구조체 변수. 변수이름 = 값;   
      - - > '.'은 컴퓨터가 저장한다는 뜻으로 알아들음    
      - - <u>"구조체 변수 안에있는 변수 이름에 값을 저장한다."</u>

        Struct Sample {  
        int var1;
        int var2;
        char var3;};  
        int main () {  
        int a;
        struct Sample b;  
        b.var1 = 2;   
        b.var2 = 4;  
        b.var3 ="홍길동"}    
         
- 메모리 공간 상황  



   
    (3)  
      - struct 구조체이름 변수 선언과 저장 활용
  
       struct Point {  
        int x;  
        int y;};  
        int main () {  
        struct Point p1;
        struct Point p2;      
        p1.x = -17;  
        p1.y = 17;}  

- 메모리 공간 상황     
  
    - struct 구조체 값 저장 활용  
      
      struct Point p1 ={-17,17}; // 윗 저장과 똑같다.  
  
    (4) 예시 문제: 국영수 점수와 총점,평균,석차를 저장하는 구조체   
  
      struct Students {  
        /*int kor;
        int eng;
        int math;*/            // 데이터가 연관되어 있고,데이터 타입이 같으면 -> 배열
    
        int scores [3];
        int total;
        double avg  
        int rank; };  
        int main () {  
        struct Students s1;  
        s1.scores; 
        // <u>s1.scores[0] = 98; ...   s1.total =259;... 할 수도 있지만 최적화를 위해 대괄호 써도 된다</u>  
      
- 메모리 공간 상황   
  
  2.구조체 심화  
    (1) 구조체를 포함한 구조체   
  
      struct Score {  
          int kor;  
      int eng;  
      int math;}    
  
      struct Student {  
      struct Score score;  
      int total;  
      double avg;  
      int rank;};  
    
      int main () {  
      struct Student s1 = {{98,88,89},259,98,2};  
    
 - 배열처럼 구조체도 구조체 안에서 활용할 수 있다.  
 - 메모리 공간 상황은 (4) 와 같다.    
   
    (2) 문자열을 저장할 구조체  
     
         Struct Person {  
        char name[10];  
        int age;  
        char addr [255];};
       
        int main() {  
        struct Person p1;  
        strcpy_s(p1.name,7."홍길동");  
        p1.age =23;  
        strcpy_s(p1.addr,4,"용산");}  
      
- 문자열은 선언과 저장을 같이 할 수 없다. 문자열 저장은 <u>strcpy_s</u> 사용  
  
    (3) typedef 활용  
      - 아래코드 일때, Person 은 태그라고 하고, P 는 타입이름이라고 한다.  
      - 타입이름을 쓰면 struct 태그를 int main 에서 생략 할 수 있다. -> <u>익명구조체</u>
        
         typedef struct Point{  
        int x;  
        int y; }P;  
       
        int main () {
        P points [3] = {{1,2},{3,4,}{6,3}};  
     
         P points [3];
        P points [0].x = 1;  
        P points [0].y = 2;                     //네 개  저장법, P p1 매모리 공간 상황은 다르다 
       
        P points [3];
        P points [0] = {1,2};  }  
       
         P p1 ={-17,17};
      
- 저장법 모양은 달라도 할 수 있는 방법은 매우 많다.  
  
  (4) 구조체의 역참조  
    - 구조체 변수로 구조체 안에 들어있는 변수의 값을 나타낼 수 있다.  
        
          typedef struct Point{  
          int x;  
          int y; }P;   
          P p1 = {-17,17};  
          P * ptr= &p1;
          printf ("p1.x =%d/ p1.y =%d", p1.x,p1.y);  
          printf(""p1.x =%d/ p1.y =%d", ptr -> X, ptr -> y)   
        
  - 포인터 변수를 사용해서 구조체안에 있는 값을 구할 수 있다.

     
     
     
     



    
