* [Install Java On Windows] (https://github.com/fggo/java-basic/blob/master/README.md#windows)
* [Install Java On Linux] (https://github.com/fggo/java-basic/blob/master/README.md#linux)
* [Download IDE] (https://github.com/fggo/java-basic/blob/master/README.md#ide)
* [First Program] (https://github.com/fggo/java-basic/blob/master/README.md#first-program)
* [Comment] (https://github.com/fggo/java-basic/blob/master/README.md#comment)
* [Variable] (https://github.com/fggo/java-basic/blob/master/README.md#variables)

# Windows
Donwload java SE JDK and edit PATH (Computer - property - Environmental Variable)

1. [Java SE] (http://www.oracle.com/technetwork/java/javase/downloads/index.html)
2. Add PATH (C:\Program Files\Java\jdk1.x.x\bin;)
```
JDK = JRE + Development/debugging tools
JRE = JVM + Java Packages Classes(like util, math, lang, awt,swing etc)+runtime libraries.
JVM = Class loader system + runtime data area + Execution Engine.
```
![alt tag](https://i.stack.imgur.com/AaveN.png)

# Linux
Install java using command line
```
java -version
javac -version
sudo apt-get install default-jdk
```

# IDE

* [Eclipse] (https://eclipse.org/downloads/)
* [NetBeans] (https://netbeans.org/downloads/)
* [Visual Code] (https://code.visualstudio.com/download)

# First program
```java
public class FirstProgram{
	public static void main(String[] args){
		System.out.println("Basic Java program.");
		System.out.println("Learning Java.");
	}
}
```

# Comment
```java
//line comment
/*block 
comment
allows
multi line*/
```

# Variables
<table>
  <tr>
    <td>Data Type</td>
    <td>Data</td>
    <td>Size(byte)</td>
    <td>Range</td>
  </tr>
  <tr>
    <td>boolean</td>
    <td>true or false</td>
    <td>1</td>
    <td>true, false</td>
  </tr>
  <tr>
    <td>char</td>
    <td>characters</td>
    <td>2</td>
    <td>unicode characters</td>
  </tr>
  <tr>
    <td>byte</td>
    <td rowspan="4">integer number</td>
    <td>1</td>
    <td>-128 ~ 127</td>
  </tr>
  <tr>
    <td>short</td>
    <td>2</td>
    <td>-32768 ~ 32768</td>
  </tr>
  <tr>
    <td>int</td>
    <td>4</td>
    <td>-2147483648 ~ 2147483647</td>
  </tr>
  <tr>
    <td>long</td>
    <td>8</td>
    <td>-9223....808 ~ 9223....807</td>
  </tr>
  <tr>
    <td>float</td>
    <td rowspan="2">real number</td>
    <td>4</td>
    <td>+-(1.40e-45 ~ 3.40e38)</td>
  </tr>
  <tr>
    <td>double</td>
    <td>8</td>
    <td>+-(4.94e-324 ~ 1.79e308)</td>
  </tr>
</table>

```java
//UnicodeChar.java
char ch1 = 'A';
char ch2 = '亀';
char ch3 = 0x3091;
char ch4 = 0x3092;
```

# Type Casting

```java
//SuffixConst.java
double e1 = 125;
float e2 = 7.125F;

long n1 = 1000000000L;
long n2 = 150;
System.out.println(e2);
System.out.println(n1);
```

* Implicit Conversion
```java
byte - short \ int - long - float -> double
       char  /

double n1 = 20; //ok (int -> double)
int n2 = 20.5; //error due to data loss (double -> int)
float n3 = 10; //ok (int -> float)
double n4 = 3.5f + 12; // ok (= 15.5f float -> double)
```

* Explicit Conversion
```java
int n = (int)3.15;

long n1 = 198221221L;
int n2 = (int)n1;

int n3 = 99;
long n4 = (long)n3;
```

# Operator
```java

basic op
+ add
- subtract
* multiply
/ divide
% modulo

compare
< > 
<= >= 
!= ==
&& || !

unary 
+ - 
int n1 = +2; 
int n2 = -n1;

incr decs
n++ ++n
n-- --n

bit op
1 & 1 == 1 
1 & 0 == 0
0 & 0 == 0
1 | 1 == 1
1 | 0 == 1
0 | 0 == 0
1 ^ 1 == 0
1 ^ 0 == 1
0 ^ 0 == 0
~0 == 1
~1 == 0
<< <<< 
>> >>>
2 << 3 == 16

type conv
7/3 == 2
7.0f/3.0f == 2.333...
(float)7/3 == 2.333...
```

# if else
```java
if(cond1) {
	/*code*/
} 
else if(cond2){
	/*code*/
}
else {
	/*code*/
}
```
## similar to if else
```java
/* returns n1 if n1 > n2, otherwise returns n2*/
int bigN = (n1 > n2) ? n1 : n2;
```

# switch break
```java
switch(n){
case 1: 
	/*code*/
	break;
case2:
case3:
	/*code*/
	break;
...
default: 
	/*code*/
	break;
}

```

# for while do while
```java
for(int i = 0; i< N; i++){/*code*/}
while(cond){/*code*/}
do{/*code*/} while(cond)
```

# continue break
```java
for(;;){
	/*code*/
	if(cond)
		continue;
}

while(true){
	/*code*/
	if(cond)
		break; /*break 'one' loop*/
}
```

# Recursion
```java
public static int toBinary(int dec){
	if (dec < 0)
		return -1;
	else if (dec == 0)
		return 0;
	else
		return dec % 2 + 10*toBinary(dec/2);
}
```

# class
```java
/*class declaration*/
class AAA{
/*member var*/
	int num;
/*constructor*/
	public AAA(){this.num = 0;}
/*member func*/
	public void add(int n){num += n;}
}
```

# Constructor

## Constuctor called only once
```java
class AAA{
	int num;
	static AAA inst = null;
	public static AAA createInst(){
		if (inst == null)
			inst = new AAA();
		return inst;
	}
	private AAA(){this.num = 0;}
	public void add(int n){num += n;}
}
```

# Ref val null
```java
AAA a = null; //init ref variable as null
```


# final keyword
```java
final int MAX_NUM = 10; // constant

```

# Class path

# Package

# Access control specifier 
<table>
	<tr>
		<td>ACS</td>
		<td>Class</td>
		<td>Package</td>
		<td>Inherited Class</td>
		<td>Others</td>
	</tr>
	<tr>
		<td>private</td>
		<td>&#9711;</td>
		<td>&#10005;</td>
		<td>&#10005;</td>
		<td>&#10005;</td>
	</tr>
	<tr>
		<td>default</td>
		<td>&#9711;</td>
		<td>&#9711;</td>
		<td>&#10005;</td>
		<td>&#10005;</td>
	</tr>
	<tr>
		<td>protected</td>
		<td>&#9711;</td>
		<td>&#9711;</td>	
		<td>&#9711;</td>
		<td>&#10005;</td>
	</tr>
	<tr>
		<td>public</td>
		<td>&#9711;</td>
		<td>&#9711;</td>
		<td>&#9711;</td>
		<td>&#9711;</td>
	</tr>
</table>

# Encapsulation
```java
class Budweiser{
	public void take(){System.out.println("Favorite American beer.");}
}

class Sapporo{
	public void take(){System.out.println("Japanese beer.");}
}

class Kirin{
	public void take(){System.out.println("Favorite beer.");}
}

class BeerPack{
	Budweiser bud;
	Sapporo sap;
	Kirin kir;
	
	public BeerPack(){
		bud = new Budweiser();
		sap = new Sapporo();
		kir = new Kirin();
	}
	
	public void take(){
		bud.take();
		sap.take();
		kir.take();
	}
}

class Worker{
	public void takeBeer(BeerPack pack){ pack.take();}
}

public class Encapsulation {
	public static void main(String[] args){
		Worker worker = new Worker();
		worker.takeBeer(new BeerPack());
	}
}
```

# static var
1. shared by all class instances
2. 'one' static variable can exist in memory
3. accesible from anywhere (declared as public)
   (class).var;
   (inst).var;
   func{var}
4. init when JVM creates class in memory
5. init not possible by constructor
6. init only once. (before constructor is called)
7. static var only accessible by static method
```java
static int n = 0;
```
 
 # static method 
```java
class A{
	public static void doNothin(){/*code*/}
}
class MainClass{
	public static void main(String[] args){
		A.doNothing();
	}
}
```

# Overloading

# String class

# StringBuilder StringBuffer

