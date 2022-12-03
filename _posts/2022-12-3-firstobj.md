--- 
layout : post
title : "JV 객체기초"
---
1. 객체란  
 - 물리, 추상적으로 정의 가능하고 식별가능 한것  
- 객체지향 언어 들의 최소한의 프로그램 단위  
- 객체(틀, 주형)는 Class 이다.  
2. 객체 (class) 생성과 객체화 방법과 생성 위치
  - 생성    
```java  
  class 클래스명
  { 
    생성자 -> 초기화 
    변수
    메소드
  }  
```
 class를 만들면 값들이 메모리에 저장되기 떄문에 쓸 수 있다.  
      
- 객체화  
```java 
클래스 명 변수명 = new 클래스명 ();  
```  
<u>class 가 객체화 되어야 변수명을 main 에서 자유롭게 사용 가능하다.</u>  
- 생성위치  
   - main 안에 객체를 선언하면 안된다.  

3. 기본 예제  
 - 클래스 생성  
```java  
  class Car {
	
	String model ="페라리";   // 변수 구성요소
	String color ="red";
	
	
	public void drive() { // 메소드 구성요소
		System.out.println(model+"드라이브를 합니다.");}
		
	public void autopilot() {
		System.out.println(model+"자율주행을 합니다.");}    
 ```  

- 객체화  
```java  
public class MainClass02 {	
	public static void main(String[] args) {
	
		//생산자 초기화
	Car car1 = new Car(); 
    // 객체화 완료 -> 메모리 car 공간 생성 완료
	car1.model ="페라리";
	
	System.out.println("car1 모델명 :"+car1.model);
	System.out.println("car1색상:"+car1.color);  
      
    car1.drive();
    car1.autopilot();
      

```  

- 객체화 활용  
```java  
  Car car2 = new Car();
	car2.model = "테슬라";
	car2.color = "yellow";
	
	System.out.println("car2 모델명 :"+car2.model);
	System.out.println("car2색상:"+car2.color);  

    car2.drive();
	car2.autopilot();  
```  
car 2 클래쓰는 car1 타입이 같을 뿐 다른 객체 이다.  
  
* <u> 객체화를 할 떄는 모두 ()가 붙어야 하면 object를 상속받는다.</u>    
   
*  
  <u> 자바 내에서 객체로써 정의가 되면 다른 패키지 또는 클래쓰에서도 사용이 가능하다</u>  
      
* 객체 지향의 거의 모든 기능은 이미 만들어져 있기 떄문에 더욱 용이하다.
