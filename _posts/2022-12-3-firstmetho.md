---
layout: post
title:  "JV- 메소드 기초"
---

1. Method  
  - 클래스 안에서 활동하는 명령문 (코드)의 집합으로 값이 아닌 기능의 역할을 한다.
  - 메소드는 반드시 클래스 내에서 선언, 호출 되어야 한다.
  
2. 메소드 선언, 호출 방법  
  - 선언 방법
  - <u>public static 리턴타입 메소드 명 (인자값) { 실행코드 return 값 ;}</u>  
  - 리턴값이 없는 타입은 void 다. 이 외 모든 타입은 리턴값이 있다.  
  - 선언했다고 기능하지 않는다. 호출을 해야 명령문을 실행한다.
    
  - 호출방법  
  - <u>메소드명 (리턴타입에 맞는 값);</u>  
    
3. 다양한 유형의 메소드   
 - 인자 x 리턴x   
 ```java  
 선언   
 public static void hello() {
		System.out.println("Hello, World");  
 호출  
 hello () ;  // 반환값 없기 때문에 괄호 값 들어갈 내용 없음  
 // 호출 될 때마다 Helo World 를 반환시킴
 ```    
- 인자 o 리턴x  
  ```java  
  선언
  public static void printName(String name) {   <U>// String은 참조형 문자열 변수이다!!</U>
		System.out.println("이름 :" +name);  
  호출  
  printName ("이지수");  
  //()에 값을 안넣어주면 -> 에러  
  // !!!! 인자가 있는 메소드는 무조건 데이터 타입에 맞는 값이 있는 호출을 해주어야 한다. !!!!
  ```  
    
- 인자 o 리턴o  
```java  
 선언
public static String getEvolution  (String mon){
	String eMon = "";
	 if(mon.equals("꼬부기")) {
		 // equals 는 = 과 같다. 문자열은 equals 를 쓰는게 좋다
		 eMon ="어니부기";}
	 //main 에서 "꼬부기"가 들어오면 eMon 이 어니부기가 되서 return 값은 어니부기
	 else if (mon.equals("어니북")) {
		 eMon ="거북왕";
     //main 에서 "어니부기"가 들어오면 eMon 이 거북왕이 되서 return 값은 거북왕
		 }
	 return eMon;   
   
 호출  
 String eMon = getEvolution("꼬부기");
		System.out.println(eMon);  
      
  // 호출에서 "꼬부기"가 들어오면 equals 로 참 , 거짓을 판별해서 eMon 에 어니부기 아니면 거북왕을 저장한다.   
     저장한 값을 return 이 main 으로 튕겨준다. 결국 출력되는 eMon 은 메소드에서 기능한 값이 출력된다.
 
 ```    
 **REVIEW**  
   - 변수의 생애 주기  
     변수의 범위 (라이프 사이클/ 생애주기)
-> 만들어지는 시점 : 변수를 선언하는 코드를 컴퓨터가 만났을 때
-> 사라지는 시점: 변수 선언이 속한 코드블록의 끝을 만났을 때  
  
   -  위 코드의 메소드 선언에서 IF 문장안에 eMon을 선언하면 안된다. -> 그 코드블럭 외에서 eMon 변수가 사용되면  
 인식이 안된다. 
     
- 오버로딩 : 인자 두개 이상  !! 매우 중요
  ```java  
  선언
  public static void printName(String name, int age) {
	System.out.println("이름:"+name);	
	System.out.println("나이:"+age);	}  
  호출  
  printName("이지수",22); 
  ```  
    
- 메소드의 전역변수 활용  
  - 인자 o 리턴x  
  ```java   
    선언
   public static void setName(String name) {
	MainClass01.name=name;    
    
   // 매개 name을 main 전역 변수에 저장하고 싶을 때  
   // 어떤 name 인지 정확히 표현해줄것 (MainClass01.name) 
  
   호출  
  setName("피카추");  
  System.out.println("전역변수 name :"+name);  
  
  // 피카추가 출력됨  
  ```    
  
 - 전역변수 값을 가져오는 메소드 인자 x 리턴 o   
  ```java  
   선언
  public static String getName() {	
	 return MainClass01.name;}    
   
  호출  
  String strName = getName();
 System.out.println("전역변수 name :"+strName);  
      
  // return 이 전역변수 name을 튕겨주면 저장할 공간이 필요함   
   strName 을 선언해야하는 이유
  <u>*메소드의 호출은 값으로 사용 할 수 없음</u>  
  ``` 
 
  


  
  
  
  
  
  
  
