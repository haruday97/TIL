# Inversion of Control
라이브러리에서 애플리케이션 흐름의 주도권이 개발자에게 있고, 프레임워크는 애플리케이션 흐름의 주도권이 프레임워크에 있다.  
여기서 말하는 애플리케이션 흐름의 주도권이 뒤바뀐 것을 바로 IoC라고 한다.  

<pre>
    <code>
    public class example {
    public static void main(String[] args){
        System.out.println("Hello World!");
        }
    }
    </code>
</pre>

일반적으로 위 코드를 실행하려면 main() 메서드가 있어야한다.  
위 코드의 실행순서는 main 메서드 호출 -> System 클래스의 static 멤버변수 out의 println()을 호출한다.  
이것이 애플리케이션의 일반적인 제어 흐름이다.

## 웹 애플리케이션에서의 IoC
