# java测验3

## 选择题

### 1. 下列不可作为java语言修饰符的是:

```
A) a1                   
B) $1                    
C) _1                   
D) 11

```

### 2. 整型数据类型中，需要内存空间最少的是:

```
A) short                
B) long                 
C) int                  
D) byte

```

### 3. double数据类型的默认值是多少？

```
A) 0                    
B) 0.0
C) null                  
D) 0.0d

```

### 4. 对于变量int val = 0b11010，System.out.println("" + val)输出是多少?（注：在Java7之后，可以用0b开头标识二进制数）

```
A) 26                   
B) 64
C) 28                   
D) 32

```

### 5. String is an ___ .

```
A) Class                 
B) Variable
C) Array                 
D) Data type

```

### 6. Which of these method of String class can be used to test to strings for equality?

```
A) isequal()              
B) isequals()
C) equal()                
D) equals()

```

### 7. 指出正确的表达式。

```
A) byte=128;               
B) Boolean=null;
C) long l=0xfffL;             
D) double=0.9239d;

```

### 8. System类在哪个包中?

```
A) java.util                 
B) java.lang
C) java.awt                 
D) java.io

```

### 9. 下面哪种注释方法能够支持javadoc命令:

```
A) /**...**/                   
B) /*...*/
C) //                       
D) /**...*/

```

### 10. 若a = 8，则表达式 a >>> 2 的值是多少？

```
A)1                       
B)4
C)3                       
D)2

```

## 填空题(10 x 2)

### 1. Java源程序的文件名要求和类名要____。

### 2. ____方法是Java程序的入口。

### 3. 为了使计算机具备编译和解释Java语言的能力，首先安装**。JRE 即**，JVM即____。

### 4. **是在程序运行过程中始终保持不变的量。其名称通常要**，其必须在声明的同时____。

### 5. Java是面向____的语言，它的一切内容都包含在 ____ 中。

### 6. 在Java中，二维数组中存储的一维数组长度是否可以不同？ ____ 。

### 7. Java中的变量有两种: ____和引用，前者共有 ____ 种。

### 8. Java中数组的长度是 ____ 的，数组的每一个元素通过 ____ 访问。

### 9. 循环结构有3种，分别是 ____ ，while和do-while。其中，while和do-while的区别是 ____ 循环块中的程序代码至少会执行一次。

### 10. 除了byte，short，char和int之外，switch语句还支持（	），在Java7之后，switch语句 ____ 使用字符串。

## 代码阅读题(5 x 4)

### 1. 以下代码有4处不合理之处，请将它们改正：

```
1.  public class TestMain {
2.      public static void Main(String arguments) {
3.          String helloWorld;
4.          System.out.print(helloWorld);
5.          return void;
6.      }
7.  }

```

### 2. 阅读以下代码，判断运行结果。

![img](http://i4.tietuku.cn/84cbfaa1a156dcb2.png)

### 3. 改正下面程序中的错误(共5处)：

```
1.   public class Test {
2.      public void main(String[] args) {
3.          boolean isValid = 0;
4.          int scores[5] = {65, 70, 69, 98, 86};
5.          if(isValid) then {
6.              System.out.println(scores[5]);
7.          } else {
8.              System.out.println("No Information");
9.          }
10.     }
11.  }
```

### 4. 略

### 5. 阅读以下代码，判断其输出结果。

```
public class Test {
    public static void main(String[] args) {
        int i, j, k;
        for(i = 1; i <= 7; i++){
            for(j = 1; j <= i; ++j)
                System.out.print(j);
            for(k = 7-i; k>=1; k--)
                System.out.print("*");
            System.out.println("");
        }
    }
}

```

## 简答题(5 x 4)

### 1. 编写和运行Java程序的步骤是什么？每一步的结果是什么？在JDK中，Java语言的编译命令是什么，Java语言的执行命令是什么？

### 2. 列出你学过的运算符类型，以及每种类型中具体包括哪些运算符。

### 3. 数据类型转换分哪两种？规则是什么？

### 4. 请说明&和&&的区别。

### 5. 字符串和字符数组相互转换的方法是什么？

## 综合题(2 x 10)

### 1. 为什么String在Java中是不可变的？

### 2. 对于存储密码而言，为什么使用char数组比使用String要好？



