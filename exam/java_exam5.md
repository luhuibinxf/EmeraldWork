# Java 测试5

## 简答题（10 x 6分）

### 1. 什么是JVM？

### 2. Override和Overload分别指的是什么。

### 3. 什么是内部类和匿名类？

### 4. 在Java中如何强制垃圾收集？

### 5. 解释构造方法和普通方法的区别。

### 6. 什么是不可变的类，举例说明Java中不可变的类？

### 7. Java中实现了对数组做二分查找的类是？该类可以对String数组做二分查找吗，为什么？

### 8. 简述接口和抽象类的区别。

### 9. 为什么说Random类产生的随机数是伪随机数？

### 10. 什么是迪米特法则？

## 代码阅读题（5 x 4分）

### 1. 阅读以下代码：

```
public abstract class Shape {
    protected abstract void onDraw();
}

class Square extends Shape {
    @Override
    public void onDraw() {
        System.out.println("绘制了一个正方形！");
    }
}

class Round extends Shape {
    @Override
    private void onDraw() {
        System.out.println("绘制了一个圆形！");
    }
}

class Painter{
    public void draw(Shape shape){
        shape.onDraw();
    }
}

```

请问：@Override代表什么？以上两个用@Override注解的方法，有一个会报编译错误，是哪一个，为什么？Painter在调用draw方法时，只有在运行时才能知道绘制的形状具体是什么，这表现了面向对象的什么特征？

### 2. 面向接口编程中，一个重要而普遍的做法是用接口作为方法的参数，例如Java API中的Collections.sort()方法，该方法直接用到的接口有哪些？回到上一题中的代码，程序员经过进一步的业务分析，抽象出了以下接口：

```
interface Drawable{
    void onDraw();
}

```

请根据此接口修改上题中的代码，使得Painter类更符合面向接口编程的原则。

### 3. 以下三个类模拟了一个简单的文件系统

```
public abstract class FileSystemElement {
    private String path;

    public FileSystemElement(String path){
        this.path = path;
    }

    public String getPath(){
        return path;
    }

    public abstract List<FileSystemElement> listElements();
}

public class File extends FileSystemElement{
    public File(String path) {
        super(path);
    }

    public List<FileSystemElement> listElements(){
        return null;
    }
}

public class Directory extends FileSystemElement{
    private final List<FileSystemElement> elements = new ArrayList<>();

    public Directory(String path) {
        super(path);     
    }

    public List<FileSystemElement> listElements(){
        return elements;
    }
}

```

请用UML图表示这三个类之间的关系，并回答：文件和文件夹的关系适用于哪种设计模式？

### 4. 良好的方法命名能极大的提高代码可读性，例如下面的代码：

```
public class MathUtils {

    public static void main(String[] args){
        System.out.println(MathUtils.round(MathUtils.sqrt(4.2f)));
    }

    public static float sqrt(float x) {
        float xhalf = 0.5f * x;
        int i = Float.floatToIntBits(x);
        i = 0x5f3759df - (i >> 1);
        x = Float.intBitsToFloat(i);
        x = x * (1.5f - xhalf * x * x);
        return 1.0f / x;
    }

    public static int round(float num) {
        if (num > 0) {
            return (int) (num + 0.5f);
        } else {
            return (int) (num - 0.5f);
        }
    }
}

```

请问它的输出是什么？相比较Math.round(float f)，上面的round方法有什么缺陷？

### 5. 随意的命名是编程中最糟糕的习惯之一，阅读下面的代码

```
import java.util.Random;

public class DoSomething {

    public static void main(String[] args) {
        System.out.println(DoSomething.doItNow(10));
        System.out.println(DoSomething.doItNow(100));
        System.out.println(DoSomething.doItNow(1000));
    }

    public static int doItNow(int x) {
        int y = 0;
        Random o = new Random();
        float j = x / 2.0f;
        for (int i = 0; i < 1000; i++) {
            float k = o.nextFloat() * x - j;
            float z = o.nextFloat() * x - j;
            if (k * k + z * z <= j * j) {
                y++;
            }
        }
        return 4 * y / 1000;
    }

}

```

请判断它的输出是什么？你能将它改成可读性更高的代码吗？

## 综合题（2 x 10分）

### 1. Singleton模式：

- 什么是Singleton模式？举一个应用了单例模式的例子。
- 写一个单例模式的类，有getInstance方法。
- 请实现线程安全的单例模式。
- 请用double checked locking实现线程安全的单例模式。
- 如何防止通过反射实例化多个Singleton Class的对象？

### 2. 递归和迭代:

斐波那契数列是指这样一个数列： 0, 1, 1, 2, 3, 5, 8, 13, 21, 34 ... 从第三项开始，每一项都是前两项的和。现有一个Java方法public int fib(n)，来产生此数列。例如，fib(0) = 0, fib(1) = 1, fib(4) = 3;

- 请用递归来实现fib方法。
- 递归实现的空间复杂度为Θ(φ的n次方)，时间复杂度为Θ(n)，这是典型的对递归的滥用。请用迭代的方式实现fib方法，迭代实现的时间复杂度和空间复杂度为多少？
- Java 8支持Lambda表达式，可以真正在Java中实现尾递归。请用尾递归的方式改写第二步中的代码(无需考虑JVM是否做尾递归调用优化)。
- 有一种更优化的方法实现fib方法，其时间复杂度为Θ(log(n)),请用迭代的方式实现它。