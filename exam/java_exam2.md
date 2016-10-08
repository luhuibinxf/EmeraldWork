# java测验2

## 填空题

### 1. Java源程序的文件名和类名要 ____。

### 2. Java程序的入口是main方法，它的参数是 ____。

### 3. 变量的3要素是变量名, ____和变量值。

### 4. 要使计算机能编译和解释Java，需安装 ____。

### 5. JVM具体是指 ____。

### 6. String 类是final的，这是为了让它不能被 ____。

### 7. Java中的基本数据类型有 ____种。

### 8. Java中八进制数以 ____开头。

### 9. Java是面向 ____的编程语言。

### 10. switch语句的最后一个分支使用关键字 ____。

## 代码阅读题

### 1. 指出以下代码有什么错误：

```
public class HelloAccp{
    public static main(String[] arguments){
        System.out.println("Hello world!")
    }
}

```

### 2. 下面代码的作用是交换数组的第一个元素和最后一个元素，改正其中的错误。

```
public class Test{
    public static void main(String[] args){
        int[] list = new int[]{4, 4, 5, 2, 7, 1};
        int temp; // 临时变量

        // 交换数组的第一个元素和最后一个元素
        list[0] = temp;
        temp = list[5];
        list[5] = list[0];
    }
}

```

### 3. 分析以下代码，写出运行结果。

```
int num = 90;
System.out.print(num ++);
double a = 89.5;
int b = (int)a + 10;
System.out.println(" "+b);

```

### 4. 根据运行结果补全代码

```
int num = 8;
int num2 = 12;
  int num3 = num ___ num2
System.out.println( num3);

```

运行结果是： 4。

### 5. 以下代码运行结果是什么？

```
class test  {
    public static void main (String[] args){
        int x = -1;
        System.out.println( (x >> 31) + (x >>> 31));
    }
}

```

### 6. 以下代码运行结果是什么？

```
class test  {
    public static void main (String[] args){
        int x = -1;
        System.out.println( (x << 31) + (x <<< 31));
    }
}

```

### 7. 以下代码输出是多少？

```
class test  {
    public static void main (String[] args){
        if (true || true && false) {
            System.out.println("branch one");
        } else {
            System.out.println("branch two");
        }
    }
}

```

### 8. 以下代码输出是多少？

```
class test  {
    public static void main (String[] args){
        int count = 0;
        for(int i = 0; i<100; i++){

            if(i == 10){
                continue;
            }

            count ++;
        }

        System.out.println(count);
    }
}

```

### 9. 以下代码输出是多少？

```
class test  {
    public static void main (String[] args){
        int count = 0;
        for(int i = 0; i<10; i++){
            if(i == 5) continue;
            for(int j = 0; j<10; j++){
                if(j == 5) break;
                count ++;
            }
        }

        System.out.println(count);
    }
}

```

### 10. 以下代码输出是多少？

```
class test  {
    public static void main (String[] args){
        int count = 0;
        label:
        for(int i = 0; i<10; i++){
            if(i == 5) continue;
            for(int j = 0; j<10; j++){
                if(j == 5) break label;
                count ++;
            }
        }

        System.out.println(count);
    }
}

```

## 问答题（10 x 3分）

### 1. 编写和运行Java程序的步骤是什么？每一步的结果是什么？在JDK中，Java语言的编译命令是什么，Java语言的执行命令是什么？

### 2. Java程序有哪些编码规范？

### 3. 你学过的数据类型有哪几种？分别写出一条定义该数据类型变量的语句。

### 4. 列出你学过的运算符类型，以及每种类型中具体包括哪些运算符。

### 5. 数据类型转换分哪两种？规则是什么？

### 6. 请说明switch语句中的表达式只能是什么数据类型的值。

### 7. JAVA中的注释分为哪几种，分别是什么。

### 8. &和&&的区别。

### 9. Java中的名称命名规范。

### 10. 请用简单的代码说明for循环的两种用法。