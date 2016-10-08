# Java测验4

## 填空题（10 x 2分）

### 1. 实现接口的 ____ 不必实现接口中定义的全部方法。

### 2. Java中没有返回值的方法叫做 ____ 方法。

### 3. Java中有一个处理日期的类Date，但此类已不推荐再使用，替代它的是 ____。

### 4. 包装类Integer和String类的相同点是，它们都是 ____。

### 5. 依赖倒转原则是指程序要依赖于____, 不要依赖于具体实现。

### 6. 获取系统当前时间的方法是 ____。

### 7. 类有两种重要关系has-a和is-a， ____ 是聚合， ____ 是泛化。

### 8. 方法的重写要求 ____ 相同。

### 9. 两个方法有相同的名称和参数，但返回值不同，是否是重载？ ____

### 10. final关键字修饰类表示类 ____。

## 代码阅读题（10 x 5分）

### 1. 阅读以下代码：

```
public class Man extends People{
    public void talk(String... words){
        for(String word : words){
            System.out.print(word + " ");
        }
    }

    public static void main(String[] args){
        new Man().talk("Hello", "World");
    }
}

class People{
    public void talk(){
        System.out.println("Nothing to say.");
    }
}

```

它的运行结果是什么？

### 2. 阅读以下代码：

```
public class Test {
    public static void main(String[] args) {
        Test test = null;
        if(test instanceof Test){
            System.out.println("A");
        } else {
            System.out.println("B");
        }
    }
}

```

它的运行结果是什么？

### 3. 阅读以下代码：

```
public class Test {
    public static void main(String[] args) {
        char strs[][] = new char[5][];
        for(int i=0; i<strs.length; i++){
            strs[i] = new char[i + 1];
            Arrays.fill(strs[i], 0, i + 1, '*');
        }

        for(int i=0; i< strs.length; i++){
            for(int j=0; j < strs[i].length; j++)
                System.out.print(strs[i][j]);
            System.out.println("");
        }
    }
}

```

它的运行结果是什么？

### 4. 阅读以下代码：

```
class test  {
    public static void main (String[] args){
        Animal animal = new Cat();
        animal.running();
    }
}

class Animal{
    public void running(){
        System.out.println("Animal is running!");
    }
}

class Cat extends Animal{
    public void running(String target){
        System.out.println("Cat is running to "+target);
    }

    public void running(){
        System.out.println("Cat is running.");
    }
}

```

它的运行结果是什么？

### 5. 阅读以下代码：

```
1.  public class Test {
2.      private int a = 0;
3.      public Test(int a){
4.          this.a = a;
5.      }   
6.      class InnerTest extends Test{
7.          public static int sValue = 3;
8.          InnerTest(){
9.              Test.a = sValue;
10.         }
11.     }
12. }

```

它有哪些错误？

### 6. 阅读以下代码：

```
public abstract class Test{
    abstract Test method();
}

class TestA extends Test{

    protected TestA method() {
        return null;
    } 

}

class TestB extends Test{

    private Test method() {
        return null;
    } 

}

class TestC extends Test{

    public Object method() {
        return null;
    } 

}

```

三个子类中哪一个是对的？

### 7. 阅读以下代码：

```
public class Test {

    public Test(){
        System.out.print("A");
    }

    public Test(String str){
        this();
        System.out.print(str);
    }

    static{
        System.out.print("B");
    }

    {
        System.out.print("C");
    }

    public void test(){
        System.out.print("D");
    }

    public static void main(String a[]){
        Test test = new Test("E");
        test.test();
    }
}

```

它的运行结果是什么？

### 8. 请补全横线上的代码片段，让这段代码运行后输出HelloWorld。

```
public class HelloWorld{
    public static void main(String []args){
        double a = ____;
        double b = ____;

        if( (a==b) || (a>b) || (a<b) ){
            // Do nothing.
        } else {
            System.out.print("HelloWorld");
        }
    }
}

```

### 9. 以下代码运行结果是什么？

```
public class test {

    private int i = j ;
    private int j = 10;
    public static void main(String[] args) {
        System.out.print(new test().i);

    }

}

```

### 10. 以下代码的运行结果是什么？

```
public class test {

    private int i = getJ() ;
    private int j = 10;

    private int getJ(){
        return j;
    }
    public static void main(String[] args) {
        System.out.print(new test().i);

    }

}

```

# 问答题（5 x 6分）

### 1. 哪些父类成员不能被子类直接访问。

### 2. 请详细描述抽象类和接口的异同。

### 3. 详述方法重载和方法重写的异同。

### 4. 什么是里氏替换原则？

### 5. 简述String， StringBuffer和StringBuilder的区别。