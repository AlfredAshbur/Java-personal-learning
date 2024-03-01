# 1. Java语法基础

1.一个源文件中最多只有一个public类，其他类个数不限

2.编译后每一个类都会生成一个对应的class文件

3.如果源文件中包含一个public类，则文件必须按照该类名命名

4.mian方法也可以写在非public类中，然后指定运行非public类，这样入口方法就是非public的main方法

5.java源文件以.java作为拓展名，源文件的基本组成部分是类（class）

6.java应用程序的执行入口是main方法

7.java严格区分大小写

8.每一条语句以分号结束

```java
public class firstJavaProg {
	public static main(String[] args){
		System.out.println("Hello Java");
	}
}
```



# 2.转义字符

1. \t制表位，实现对齐功能
2. \n换行符
3. \\一个\
4. \\"一个"
5. \\'一个'
6. \r一个回车

example：

```java
//changeChar转义字符
class changeChar {
  public static void main(String[] args) {
    System.out.println("show\tchangechar");
    System.out.println("show\nchangechar");
    System.out.println("show \"changechar\"");
    System.out.println("show \'changechar\'");
    System.out.println("show\rchangechar");  
    System.out.println("show \\changechar");  
    System.out.println("show\r\nchangechar");
  }
}

```

# 3.注释

1.单行注释

//

2.多行注释

/*  */ 不能嵌套

3.文档注释

/**

 *@...

 *@...

*/

注释可被JDK提供的javadoc解析，生成一套以网页形式体现该程序的说明文档，一般写在类

例：javadoc -d E://javaCode//temp -author -version javaDocComment.java

在index.html

```java
/**
 	* @author zkw
 	* @version 1.0
 */
public class javaDocComment{
	public static void main(String[] args){
		System.out.println("javaDocComment");
	}
}
```

# 4.Java代码规范

1.类，方法的注释要以javadoc的方式来写

2.非javadoc注释给维护者看，为什么这么写，如何修改，注意事项

3.tab缩进默认整体向右，shift+tab整体向左

4.运算符和等号两边习惯性加一个空格

5.源文件使用utf-8编码保存

6.行宽不要超过80字符

7.代码编写次行风格和行尾风格

# 5.Dos原理

cmd命令行工具向dos系统发送指令，dos系统接受指令，解析指令，执行指令。对windows系统进行相应操作。

相对路径：从当前目录开始定位形成的一个路径

绝对路径：从根目录开始定位形成的一个路径

常用dos命令：

1.dir查看当前目录下的内容

2.cd切换盘符   例：从D盘切换到C盘 cd /D C:

3.切换到当前盘的其他目录（相对路径，绝对路径）..\表示上一级目录

4.切换到上一级：cd ..

5.切换到根目录：cd \ 

注：到根目录下继续切换上一级不报错，路径不变

6.查看指定目录下的所有子级目录tree 路径:

7.清屏cls

8.退出dos exit

9.md创建目录

10.rd删除目录

11.copy拷贝文件

12.del删除文件

13.echo输入内容到文件

14.type输入空文件

15.move剪切

# 6.练习

## 6.1.输出Hello World

```java
public class printHelloWorld{
	public static void main(String[] args){
		System.out.println("Hello World");
	}
}
```

## 6.2.转义字符

```java
public class escapeCharacter{
    public static void main(String[] args){
         System.out.println("姓名：\n");
         System.out.println("性别：\n");
         System.out.println("年龄：\n");
         System.out.println("籍贯：\n");
    }
}
```

## 6.3.JDK、JRE、JVM之间的关系

JDK(Java SE Development Kit)，Java标准开发包，它提供了编译、运行Java程序所需的各种工具和资源，包括Java编译器、Java运行时环境，以及常用的Java类库等。

```
JDK = JRE + Java开发工具
```

JRE( Java Runtime Environment) 、Java运行环境，用于解释执行Java的字节码文件。普通用户而只需要安装 JRE（Java Runtime Environment）来运行 Java 程序。而程序开发者必须安装JDK来编译、调试程序。

```
JRE = JVM + 核心类库
```

JVM(Java Virtual Mechinal)，Java虚拟机，是JRE的一部分。它是整个java实现跨平台的最核心的部分，负责解释执行字节码文件，是可运行java字节码文件的虚拟计算机。所有平台的上的JVM向编译器提供相同的接口，而编译器只需要面向虚拟机，生成虚拟机能识别的代码，然后由虚拟机来解释执行。

当使用Java编译器编译Java程序时，生成的是与平台无关的字节码，这些字节码只面向JVM。不同平台的JVM都是不同的，但它们都提供了相同的接口。JVM是Java程序跨平台的关键部分，只要为不同平台实现了相应的虚拟机，编译后的Java字节码就可以在该平台上运行。

**区别与联系：**

1. JDK 用于开发，JRE 用于运行java程序 ；如果只是运行Java程序，可以只安装JRE，无序安装JDK。
2. JDk包含JRE，JDK 和 JRE 中都包含 JVM。
3. JVM 是 java 编程语言的核心并且具有平台独立性。

## 6.4.环境变量PATH配置及其作用

作用：为了在dos的任意目录下使用java、javac命令。

配置：先配置JAVA_HOME = JDK安装主目录

​			编辑PATH环境变量，编辑下添加jdk->bin路径

## 6.5Java编写步骤

编写Java源代码 -> javac编译得到对应的.class文件(字节码文件) -> java运行（本质就是将.class文件加载到Jvm虚拟机上进行运行）

## 6.6易犯错误

6.6.1 编译或运行时找不到相关文件 -> 检查文件名和文件路径

6.6.2 主类名和文件名要一致

6.6.3 行尾加分号

6.6.4 拼写错误，原生方法的大小写

# 7.变量

变量是程序的基本组成单位

变量三要素：类型、变量名、值

原理：在内存中开辟一定的空间来保存变量的值

变量类型不同占用内存空间不同	ex：int占用4个字节，double占用8个字节

变量的声明：

example1.

```java
int a;
a = 10;
```

example2.

```java
int a = 10;
```

将10这个值赋给变量a

**变量必须先声明后使用**

内存中存储的数据可以在同一类型范围内不断变化

变量在同一作用域内不能重名

# 8.加号的使用

加号左右是数字做相加运算

加号左右是字符串做拼接运算

运算顺序从左到右

```java
System.out.println(100 + 80);	//180
System.out.println("100" + 80);	//10080
System.out.println(100 + 80 + "hello");	//180hello
System.out.println("hello" + 100 + 80);	//hello10080
```

# 9.数据类型

Java是强类型语言

java数据类型分为：基本数据类型 + 引用数据类型

基本数据类型 = 数值型 + 字符型 + 布尔型（数值型 = 整型 + 浮点型）

byte[1]	short[2]	int[4]	long[8]	float[4]	double[8]	char[2]	boolean[1]

引用数据类型 = 类 + 接口 + 数组

## 9.1.整型

```java
byte num1 = 1;
short num2 = 2;
int num3 = 3;
long num4 = 4;
```

存放范围：

byte：-128-127

short：-32768-32767

java各整数类型有固定的范围和字段长度，不受OS影响，以保证可移植性。

Java的整型常量默认为int型，声明long型常量需后加 "L" , "l"

```java
public class wholeType {
    public static void main(String[] args){
        int n1 = 1;
        long n2 = 2L;
    }
}
```

## 9.2.浮点类型

Java浮点类型可以表示小数

单精度浮点：float

双精度浮点：double

浮点数在计算机中的存储形式：浮点数 = 符号位 + 指数位 + 尾数位

尾数部分可能丢失，造成精度损失（小数都是近似值）。

浮点类型有固定的范围和字段长度，不受OS影响，以保证可移植性。

浮点型常量默认为double型，声明float型常量需要在末尾加 'F' , 'f'

```java
public class floatType {
    public static void main(String[] args){
        double n1 = 1;
        double n1 = 1F;
        float n2 = 2F;
    }
}
```

浮点型常量的两种表现形式：

十进制数ex：5.12	.512	512.0f	必须有小数点，第一个零可以省略

科学计数法：5.12e2（512.0）	5.12e-2

注：2.7  ！=  8.1/3	8.1/3为一个接近但不等于2.7的小数

**如果要对运算结果为小数的变量进行比较，不能直接用  ==。应该以两个小数的差值的绝对值，在某个精度范围内进行判断。**

```java
if(Math.abs(n1 - n2) < 0.0001){
    System.out.println("差值小于规定值，认为相等");
}
```

**注：直接查询得到的或者赋值的小数是可以判断相等的。**

## 9.3字符类型

单个字符用char进行定义，多个字符用string

char占用两个字节

```java
char ch1 = 'a';
char ch2 = '\t';
char ch3 = '张';
char ch4 = 97;
```

char类型可以进行运算

```java
System.out.println('a' + 10);	//107
```

存储：字符->码值->二进制->存储

显示：二进制->码值->字符->显示

ASCII：一个字节表示，一个128个字符，实际上一个字节可以表示256个字符，但是只用128个。

Unicode：编码使用两个字节表示字符，汉字和字母都统一占用两个字节，浪费空间。

utf-8：大小可变的编码，字母使用一个字节，汉字使用3个字节。

gbk：可以表示汉字，范围广，字母使用一个字节，汉字使用两个字节。

gb2312：可以表示汉字，但范围小于gbk。

big5码：（繁体汉字，香港，台湾）。

## 9.4布尔类型

布尔类型只可以取值为false和true，不可以为null。

布尔类型占用一个字节。

boolean一般用于逻辑计算，用于流程控制。

```java
bollean pass = true;
if (pass) {
	//body
} else {
	//body
}
```

**不可以用零或非零数代替false和true，不同于C语言。**

# 10.自动类型转换

当java程序在运算和赋值时，精度小的数据类型自动转换为精度大的数据类型。

数据类型按精度（容量）大小排列：char -> int -> long -> float -> double

​                                                          byte -> short -> int -> long -> float -> double

```java
int num1 = 'a';
double num2 = 80;
```

多种数据类型进行运算时，系统首先将所有操作数转换为精度最大的数据类型，然后再进行计算。

```java
int num1 = 10;
float num2 = num1 + 1.1;	//错误
float num2 = num1 + 1.1F;	//正确
double num2 = num1 + 1.1;	//正确
```

精度大的数据转换为精度小的数据时会报错，反之直接进行自动类型转换。

```java
int num1 = 1.1;		//错误
double num2 = 1;	//正确
```

byte、short、不会自动转换为char，char也不能自动转换为short和byte。

```java
byte num1 = 10;
char ch = num1;	//错误
```

当给byte赋值时，先判断该数是否在byte表示范围内，当用变量进行赋值时，先判断类型。

byte，short，char三者可以进行运算，在运算时先转换为int型。

```java
byte num1 = 1;
byte num3 = 3;
short num2 = 2;
short sum = num1 + num2;	//错误
int sum = num1 + num2;	//正确

byte num4 = num1 + num3	//错误，已经转换为int型
```

boolean类型不参与运算。

自动提升原则：表达式结果的类型自动转换为操作数中精度最大的类型。

# 11.强制类型转换

自动类型转换的逆过程，将容量大的数据转换为容量小的数据，使用时声明变量关键字加（），但是可能造成精度丢失或溢出。

```java
int num1 = (int)1.1;

int num2 = 100;
byte num3 = (byte)num2;

int num4 = 1000;
byte num5 = (byte)num4;	//溢出

int num6 = (int)10*1.5+1.5;		//错误，结果为double型
int num7 = (int)(10*1.5+1.5);	//正确
```

强制类型转换只针对最近的操作数有效。

char可以保存int的常量值，不能保存int的变量值，需要强制类型转换。

```java
char ch = 100;		//true
int num = 100;
char ch1 = num;		//false
char ch2 = (char)num;//true
```

# 12.String

基本数据类型转String类型：将基本数据类型的值加 " "

```java
int num1 = 1;
double num2 = 3;
float num3 = 2F;
boolean num4 = true;
String str1 = num1 + "";
String str2 = num2 + "";
String str3 = num3 + "";
String str4 = num4 + "";
```

String转基本数据类型：通过包装类调用parsexx方法

```java
int num1 = Integer.parseInt(str1);
double num2 = Double.parseDouble(str2);
float num3 = Float.parseFloat(str3);
long num4 = Long.parseLong(str4);
byte num5 = Byte.parseByte(str5);
boolean str = Boolean.parseBoolean("true");
```

将字符串转成字符时，只取字符串的第一个字符。

```java
System.out.println(str.charAt(0));
```

将String转成基本数据类型时要保证数据的有效性，比如可以把字符串123转成一个整数，但是不能把hello转成一个整数。

当格式不正确时，会抛出异常，导致程序终止。

# 13.运算符

## 13.1算术运算符

+、-、*、/、%、++、--

前++/--（++i、--i）：先自增/自减后使用

后++/--（i++、i--）：先自增/自减后赋值

```java
int num1 = 1;
num1 = num1++;
System.out.println(num1);	//1

int num2 = 1;
num2 = ++num2;
System.out.println(num2);	//2
```

## 13.2关系运算符（比较运算符）

关系运算符的运算结果都是boolean型，要么是true要么是false。

instanceof检查是否是类的对象

## 13.3逻辑运算符

用于连接多个关系表达式，最终结果也是boolean型

短路与（&&）：如果第一个条件为false，则第二个条件不会被判断，结果为false，效率高。

逻辑与（&）：不管第一个条件是否为false，第二个条件都会被判断，效率低。

短路或（||）：如果第一个条件为true，则第二个条件不会被判断，结果为true，效率高。

逻辑与（|）：不管第一个条件是否为true，第二个条件都会被判断，效率低。

逻辑异或 (^) :相同为false，不同为true

## 13.4赋值运算符

运算顺序从右向左

赋值运算符的左边只能是变量，右边可以是变量，常量，表达式。

**复合赋值运算符会进行类型转换。**

example:

```java
byte num1 = 1;
num1 += 2;	//等价于  num1 = (byte)(num1 + 2);
```

## 13.5三元运算符

语法：条件表达式 ？表达式1 ：表达式2；

条件表达式判断为true运行表达式1，条件表达式判断为false运行表达式2。

表达式1和表达式2要为可以赋值给接受变量的类型（或可以自动转换）

example：

```java
int num1 = 1;
int num2 = 2;
double num3 = num1 < num2 ? 1.0 : 2.0;
//或
int num4 = num1 < num2 ? (int)1.0 : (int)2.0;
```

## 13.6运算符优先级

|      | .     ()        {}      ;     ,  |
| ---- | -------------------------------- |
| R->L | ++     --     ~     !(data type) |
| L->R | *         /      %               |
| L->R | +       -                        |
| L->R | <<    >>    >>>    位移          |
| L->R | <    >    <=    >=    instanceof |
| L->R | ==      !=                       |
| L->R | &                                |
| L->R | ^                                |
| L->R | \|                               |
| L->R | &&                               |
| L->R | \|\|                             |
| L->R | ?  :                             |
| R->L | =       *=      /=     %=        |
|      | +=     -=     <<=     >>=        |
|      | >>>=      &=     ^=     \|=      |

从上到小优先级降低，单目运算和赋值运算的运算顺序是从右向左。

# 14.标识符的命名规则和规范

命名规则：

1.数字，字母，下划线（_），$

2.数字不能作为标识符的开头。

3.不可以使用关键字和保留字，但是可以包含关键字和保留字。

4.严格区分大小写，长度无限制。

5.标识符不能包含空格。

命名规范：

包名：多单词组成时，所有字母都小写。

类名，接口名：多单词组成时，所有单词首字母大写。（大驼峰）

变量名，方法名：驼峰命名法。

常量名：所有字母都大写，多单词时每个单词用下划线连接。

# 15.关键字，保留字

所有关键字的字母都是小写。

保留字：尚未使用，但之后版本可能会用。

命名标识符要避免使用保留字。

# 16.键盘输入语句

Scanner 扫描器（对象）

1.导入该类所在的包（java.util）

2.创建对象Scanner

3.调用里面的功能

```java
import java.util.Scanner;	//将java.util下的Scanner类导入到当前文件
public class input{
    public static void main(String[] args){
        //creat Scanner object example
        Scanner myScanner = new Scanner(System.in);
        //receive user inut
        System.out.println("Please input your name:");
        String name = myScanner.next();	//receive string
        System.out.println("Please input your age:");
        int age = myScanner.nextInt();	//receive int
        System.out.println("Please input your score:");
        double score = myScanner.nextDouble();	//receive double
    	System.out.println("user's information:");
        System.out.println("username=" + name 
            + " userage=" + age + " userscore=" + score);
    }
}
```



