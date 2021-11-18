 

# 0.特殊语句

## 1.退出Java虚拟机

```java
System.exit(0); //JVM退出
```

## 2.为了让程序不再执行，给出return;

```java
return;
```



# 1.DOS命令。

### （WIN+R==CMD）



![](https://github.com/Continuers/Java/blob/main/picture/1.png)


# 2.配置环境变量

## 环境变量更改path路径为	D:\Java\JDK11\bin

# 3.hello world

-------------------------------------------------------------------------------------------------------




```java
public class helloworld
{
	public static void main(String[] args)
	{
		System.out.println("helloworld");
	}
}
```

## ==注意！  String和System开头都要大写，否则报错！==

```java
 //win+r → cmd → cd Java文件的路径 → Javac 文件名.java → java class类名
```


![](https://github.com/Continuers/Java/blob/main/picture/2.png)

--------------------------------------------------------------------------------------------------------------------

# 4.数据类型

 ![](https://github.com/Continuers/Java/blob/main/picture/3.png)

## 例题

```java
public class 变量 {
	public static void main(String[] args) {
    //定义byte类型变量
    byte b=10;
    System.out.println(b);
    //定义short类型变量
    short s=100;
    System.out.println(s);
    //定义int类型变量 
    int i=10000;
    System.out.println(i);
    //定义double类型变量
    double d=13.14;
    System.out.println(d);
    //定义char类型变量
    char c='c';
    System.out.println(c);
    //定义boolean类型变量
    boolean bb=true;
    System.out.println(bb);
    //定义long类型变量
    long l=1000000000L;
    System.out.println(l);
    //定义float类型变量
    float f=13.14F;
    System.out.println(f);
    }
}
```

# 5.变量

```java
public class 变量 {
	public static void main(String[] args) {
		int a=10;
		System.out.println(a);
		a=20;
		System.out.println(a);
	}
}
```

  

## 变量使用的注意事项


![](https://github.com/Continuers/Java/blob/main/picture/4.png)

![](https://github.com/Continuers/Java/blob/main/picture/5.png)


------------------------------------------------------------------------------------

# 6.类型转换

## 1.自动类型转换

![](https://github.com/Continuers/Java/blob/main/picture/6.png)

```java
public class 变量 {
	public static void main(String[] args) {
    //byte可以转化为short.int
    byte b=10;
    short a=b;
    int i=b;
    //但不能转化为char，会报错
    char c=b;
    System.out.println(c);
    }
}
```

## 2.强制类型转换（==可能会丢失精度==）

![](https://github.com/Continuers/Java/blob/main/picture/7.png)

```java
public class 变量 {

	public static void main(String[] args) {
	int k = (int)88.88;
	System.out.println(k);
	}
} 
```



---------------------------------------------------------------------------------------



# 7.运算符

## 1.关系运算符

```java
public class 变量 {
    public static void main(String[] args) {
        int i=20;	int j=20;	int k=10;
        System.out.println(i==j);
        System.out.println(i==k);
    }
} 
```

```java
/*运行结果为：
	True
	False
*/
```



## 2.逻辑运算符

```java
public class 变量 {
    public static void main(String[] args) {
        int i=1;	int j=2;	int k=3;
        //& 有false则false
        System.out.println((i>j)&(i>k));	//false	
        System.out.println((i<j)&(i>k));	//false	
        System.out.println((i>j)&(i<k));	//false	
        System.out.println((i<j)&(i<k));	//true	
        //| 有true则true	
        System.out.println((i>j)|(i>k));	//false	
        System.out.println((i<j)|(i>k));	//true	
        System.out.println((i>j)|(i<k));	//true	
        System.out.println((i<j)|(i<k));	//true	
        //^ 相同为false,不同为true	
        System.out.println((i>j)^(i>k));	//false	
        System.out.println((i<j)^(i>k));	//true	
        System.out.println((i>j)^(i<k));	//true	
        System.out.println((i<j)^(i<k));	//false	
        //!	
        System.out.println((i>j));    		//false	
        System.out.println(!(i>j));   		//true	
        System.out.println(!!(i>j));  		//false	
        System.out.println(!!!(i>j)); 		//true		
    }
} 
```

## 3.短路逻辑运算符

![](https://github.com/Continuers/Java/blob/main/picture/8.png)

## 4.三元运算符

 ==a>b?a:b==

```java
public static void main(String[] args) {
    //a>b?a:b	
    int a=10;	int b=20;
    //找出最大值	
    int max=a>b?a:b;	
    System.out.println("max:"+max);	
}
```

==俩只老虎==

```java
public static void main(String[] args) {
    int w1=180;
    int w2=200;    
    //判断老虎体重是否相同  
    a==b?true:false	
    boolean b=w1==w2?true:false;	
    System.out.println("b:"+b);	
}
```

```java
//结果为false
```

==三个和尚：比较三人身高输出最大值==

 

```java
public static void main(String[] args) {
    int h1=160;
    int h2=170;
    int h3=180;
    int temp=h1>h2?h1:h2;
    int max=temp>h3?temp:h3;
    System.out.println("max:"+max);	
}
```

## 5.位运算符

| 位运算符 | 名称         | 描述                                                         | 举例                              |
| -------- | ------------ | ------------------------------------------------------------ | --------------------------------- |
| &        | 按位与       | 如果相对应位都是 1，则结果为 1，否则为 0                     | （a＆b），得到 12，即 0000 1100   |
| 丨       | 按位或       | 如果相对应位都是 0，则结果为 0，否则为 1                     | （ a 丨 b ）得到 61，即 0011 1101 |
| ^        | 按位异或     | 如果相对应位值相同，则结果为 0，否则为 1                     | （a^b）得到 49，即 0011 0001      |
| ~        | 按位补       | 翻转操作数的每一位，即 0 变成 1，1 变成 0                    | （〜a）得到 -61，即 1100 0011     |
| <<       | 按位左移     | 左操作数按位左移右操作数指定的位数                           | a<<2 得到 240，即 1111 0000       |
| >>       | 按位右移     | 左操作数按位右移右操作数指定的位数                           | a>>2 得到 15 即 1111              |
| >>>      | 按位右移补零 | 左操作数的值按右操作数指定的位数右移，移动得到的空位以零填充 | a>>>2 得到 15 即 0000 1111        |

```java
public class BitOperation {
    public static void main(String args[]) {
        int a = 60;
        int b = 13;
        System.out.println("a & b = " + (a & b));//a & b = 12
        System.out.println("a | b = " + (a | b));//a | b = 61
        System.out.println("a ^ b = " + (a ^ b));//a ^ b = 49
        System.out.println("~a = " + (~a));//~a = -61
        System.out.println("a << 2 = " + (a << 2));//a << 2 = 240
        System.out.println("a >> 2 = " + (a >> 2));//a >> 2 = 15
        System.out.println("a >>> 2 = " + (a >>> 2));//a >>> 2 = 15
    }
}
```



# 8.数据输入

## 1.Scanner使用的基本步骤

![](https://github.com/Continuers/Java/blob/main/picture/9.png)



```java
package bianliang;
//导包
import java.util.Scanner;
public class 变量 {
    public static void main(String[] args) {
        //创建对象	
        Scanner sc = new Scanner(System.in);
        //可直接输入Scanner回车进行自动导包
        //接收数据	
        int x = sc.nextInt();	
        //输出数据	
        System.out.println("x:"+x);	
    }
} 
```

## 2.三个和尚升级版

```java
package bianliang;
//导包
import java.util.Scanner;
public class 变量 {
    public static void main(String[] args) {
        //创建对象	
        Scanner sc = new Scanner(System.in);	
        //接收数据	
        System.out.println("请输入第一个和尚的身高：");
        int h1 = sc.nextInt();
        System.out.println("请输入第二个和尚的身高：");
        int h2 = sc.nextInt();
        System.out.println("请输入第三个和尚的身高：");
        int h3 = sc.nextInt();
        int temp=h1>h2?h1:h2;
        int max=temp>h3?temp:h3;
        //输出数据	
        System.out.println("三个和尚中最高的身高是:"+max+"cm");
    }
} 
//运行结果为：
	请输入第一个和尚的身高：170
    请输入第二个和尚的身高：180
    请输入第三个和尚的身高：190
    三个和尚中最高的身高是:190cm
```

# 9.if…else语句

## 1.奇偶数判断

```java
package bianliang;
//导包
import java.util.Scanner;

public class 变量 {
    public static void main(String[] args) 	{
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入一个整数：");	
        int number=sc.nextInt();
        if(number%2==0){	
            System.out.println(number+"是偶数");	
        }else{	
            System.out.println(number+"是奇数");
        }	
    }
} 
```

## 2.if……else if……else

# 10.switch语句

## 1.星期数例子

```java
public static void main(String[] args) 	{
    Scanner sc = new Scanner(System.in);
    System.out.println("请输入星期数（1-7）：");
    int week=sc.nextInt();
    switch(week){
        case 1:
            System.out.println("星期一");
            break;
        case 2:			
            System.out.println("星期二");
            break;
        case 3:			
            System.out.println("星期三");
            break;
        case 4:	
            System.out.println("星期四");	
            break;	
        case 5:		
            System.out.println("星期五");	
            break;	
        case 6:		
            System.out.println("星期六");	
            break;		
        case 7:		
            System.out.println("星期日");	
            break;	
        default:	
            System.out.println("输入有误！");
            break;	
    }
}
```

## 2.春夏秋冬例子

```java
public static void main(String[] args) 	{
    
    Scanner sc = new Scanner(System.in);
    System.out.println("请输入当前月份：");
    int month=sc.nextInt();
    switch(month)		{
        case 1:
        case 2:
        case 12:
            System.out.println("冬季");
            break;	
        case 3:	
        case 4:	
        case 5:	
            System.out.println("春季");
            break;	
        case 6:	
        case 7:	
        case 8:	
            System.out.println("夏季");
            break;	
        case 9:	
        case 10:	
        case 11:	
            System.out.println("秋季");
            break;	
        default:
            System.out.println("输入有误！");
            //			break;		
    }
}
```

# 11.循环

## 1.for循环

### 1.1-100中偶数之和

```java
public static void main(String[] args) 	{
    int num=0;
    for(int i=1;i<=100;i++)	{
        if(i%2==0){	
            num+=i;	
        }	
    }		
    System.out.println("和为:"+num);
}
```

### 2.水仙花数

```java
public static void main(String[] args) 	{
    int x,i,y,z;
    for(i=100;i<=999;i++){
        x=i%10;		
        y=i/10%10;	
        z=i/100%10;	
        if(x*x*x+y*y*y+z*z*z==i){	
            System.out.println(i);
        }					
    }	
}
```

### 3.百鸡百钱

![](https://github.com/Continuers/Java/blob/main/picture/19.png)

```java
public static void main(String[] args) {
    for (int x=0;x<=20;x++){
        for (int y=0;y<=33;y++){ 
            int z=100-x-y;
            if(z%3==0&&5*x+3*y+z/3==100){ //z%3==0：鸡雏三值钱一，不单卖。 
                System.out.println(x+","+y+","+z); 
            }   
        }  
    }
}
```

==运行结果为：==

![](https://github.com/Continuers/Java/blob/main/picture/20.png)



## 2.while循环

```java
public static void main(String[] args) 	{
    int i=1;
    while(i<=10){
        System.out.println("helloworld");			
        i++;		
    }	
}
```



### 折叠珠峰

```java
//一张纸0.1毫米，问折叠几次可以超过珠峰高度？
```

```java
public static void main(String[] args) 	{
    double paper=0.1;
    int i=0,m=884886;
    while(paper<=m){ 
        paper*=2;   
        i++;        
    }		
    System.out.println("折叠"+i+"次");	
}
//24c
```

## 3.do…while循环

```java
public static void main(String[] args) 	{
    int i=1;
    do {
        System.out.println("helloworld");
        i++;		
    }while(i<=10);	
}
```

## 4.三种循环的区别

![](https://github.com/Continuers/Java/blob/main/picture/10.png)



# 12.Random随机数

![](https://github.com/Continuers/Java/blob/main/picture/11.png)

## 1.生成10个随机数

```java
package bianliang;
//导包
import java.util.Random;
public class 变量 {
    public static void main(String[] args) 	{
        //创建对象
        Random r = new Random();
        //循环生成10个随机数
        for(int i=0;i<10;i++){
            //获取随机数			
            int number =r.nextInt(10);
            System.out.println("number:"+number);	
        }		
        //获取一个1-100的随机数
        int x=r.nextInt(100)+1;
        System.out.println(x);
    }
} 
```

## 2.猜数字

```java
package bianliang;
//导包
import java.util.Random;
//随机数
import java.util.Scanner;
//输入
public class 变量 {
	public static void main(String[] args) 	{
        //创建对象
        Random r = new Random();
        //获取随机数		
        int number =r.nextInt(100)+1;
        while(true){
            Scanner sc=new Scanner(System.in);	
            System.out.println("请输入你要猜的数字：");
            int guess=sc.nextInt();		
            if(guess>number){
                System.out.println("你猜的数字"+guess+"大了");		
            }else if(guess<number){
                System.out.println("你猜的数字"+guess+"小了");
            }else{	
                System.out.println("恭喜你！猜对了！");	
                break;	
            }	
        }	
    }
} 
```

# 13.快捷键

## IDEA快捷键

### 1.快速生成语句

```java
//psvm 回车
```

```java
public static void main(String[] args) {    }
```



```java
//sout 回车
```

```java
System.out.printf("");
```



```java
//soutp
```

```java
System.out.println("helloworld.main");
```



```java
//print不换行
```

```java
System.out.print("hello");
```



```java
//println自动换行
```

```java
System.out.println("hello");
```

 

### 2.内容辅助键==Ctrl+Alt+space(内容提示代码补全==



### 3.注释

单行：选中代码==Ctrl+/== ( 再来一次就是取消）

多行：选中代码==Ctrl+Shift+/== 



### 4.格式化（整理代码）==Ctrl+Alt+L==



### 5.自动导包==alt+enter==

![](https://github.com/Continuers/Java/blob/main/picture/17.png)

==或者输入Scanner回车==

### 6.自动生成左边内容 ==Ctrl+Alt+V==

```java
sc.nextLine();
//Ctrl+Alt+V


String line = sc.nextLine();
```

![](https://github.com/Continuers/Java/blob/main/picture/44.png)

### 7.快速复制代码 ==Ctrl + D==



### 8.构造方法 ==Alt+insert==

### 步骤1

![](https://github.com/Continuers/Java/blob/main/picture/74.png)

 **选择Constructor构造方法**

![](https://github.com/Continuers/Java/blob/main/picture/76.png)

### 步骤2

![](https://github.com/Continuers/Java/blob/main/picture/77.png)

**重复一次后，点击第一个，按住 ==shift== 键全选 再次点击OK即可** 

### 步骤3

![](https://github.com/Continuers/Java/blob/main/picture/78.png)

**再重复一次后，点击第一个，按住 ==shift== 键全选 再次点击OK即可** 

### 9.自动更改命名 ==shift+f6==



### 10.定位到项目窗口 ==alt+1==



### 11.快速定位报错行 ==f2==



### 12.自动定位到要敲代码的地方 ==CTRL+shift+enter==



### 13.横，竖向切分==Ctrl+Shift+A==  输入 ==Split Down  or  Split Right==





---------------------

## Eclipse快捷键

### 1.==Ctrl+F11==运行程序

### 2.==F11==以调试模式运行程序

### 3.==F2== 重命名文件名，工程名

### 4.在当前行上插入一行：==Ctrl+Shift+Enter==

### 5.在当前行下插入一行： ==Shift+Enter==

### 6.重做(与撤销Ctrl+Z相反)==Ctrl+Y==

### 7.==Ctrl+Alt+↑==   复制当前行到上一行（复制增加）

### 8.==Ctrl+Alt+↓== 复制当前行到下一行（复制增加）

### 9.调试

| 调试         |                                      |
| :----------- | :----------------------------------- |
| F5           | 单步跳入                             |
| F6           | 单步跳过                             |
| F7           | 单步返回                             |
| F8           | 继续                                 |
| Ctrl+Shift+D | 显示变量的值                         |
| Ctrl+Shift+B | 在当前行设置或者去掉断点             |
| Ctrl+R       | 运行至行(超好用，可以节省好多的断点) |
|              |                                      |
|              |                                      |
|              |                                      |
|              |                                      |
|              |                                      |
|              |                                      |
|              |                                      |
|              |                                      |
|              |                                      |
|              |                                      |
|              |                                      |
|              |                                      |



==F6==    step over>>debug 下一个







# 14.数组

## 1.数组元素访问

```java
public static void main(String[] args) 	{
    int[] arr=new int[3];
    /*int 说明数组中元素类型是int类型	 []说明数组	 arr是数组名	 new为数组申请内存空间	 */	
    System.out.println(arr);
    System.out.println(arr[0]);	
    System.out.println(arr[1]);	
    System.out.println(arr[2]);	
    arr[0]=100;	
    arr[1]=200;	
    System.out.println(arr);	
    System.out.println(arr[0]);	
    System.out.println(arr[1]);		
    System.out.println(arr[2]);
}
```

## 2.多个数组指向相同内存图

```java
public static void main(String[] args) 	{
    int[] arr=new int[3];     
    /*int 说明数组中元素类型是 int 类型[]说明数组 arr 是数组名 new 为数组申请内存空间 */	
    arr[0]=100;	
    arr[1]=200;	
    arr[2]=300;		
    System.out.println(arr);
    System.out.println(arr[0]);
    System.out.println(arr[1]);	
    System.out.println(arr[2]);	
    int[] arr2=arr;		
    arr2[0]=111;		
    arr2[1]=222;	
    arr2[2]=333;	
    System.out.println(arr);
    System.out.println(arr[0]);
    System.out.println(arr2);	
    System.out.println(arr2[0]);
}
```

## 3.数组静态初始化

```java
public static void main(String[] args) 	{
    //定义数组		
    int[] arr= {1,2,3};	
    System.out.println(arr[0]);	
    System.out.println(arr[1]);	
    System.out.println(arr[2]);	
}
```

## 4.数组常见问题

```java
public static void main(String[] args) 	{
    int[] arr = new int[3];	
    //索引越界ArrayIndexOutOfBoundsExceptpackage io.itrs6;

import java.io.*;

/*
    需求:
        把E:\\itcast复制到 F盘目录下
 */
public class CopyFolderDemo2 {
    public static void main(String[] args) throws IOException {
        //①创建数据源 File对象,路径是E:\\itcast
        File srcFile = new File("D:\\java\\itcast");
        //②创建目的地File对象,路径是F:\\
        File destFile = new File("D:\\");

        //③写方法实现文件夹的复制,参数为数据源 File对象和目的地File对象
        copyFolder(srcFile, destFile);
    }

    //复制文件夹
    private static void copyFolder(File srcFile, File destFile) throws IOException {
        //④判断数据源File是否是目录
        if (srcFile.isDirectory()) {
            //A在目的地下创建和数据源 File名称一样的目录
            String srcFileName = srcFile.getName();
            File newFolder = new File(destFile, srcFileName);    //D:\\itcast
            if (!newFolder.exists()) {
                newFolder.mkdir();
            }

            //B:获取数据源 File下所有文件或者目录的 File数组
            File[] fileArray = srcFile.listFiles();

            //C:遍历该 File数组,得到每一个 File对象
            for (File file : fileArray) {
                //D:把该 File作为数据源 File对象,递归调用复制文件夹的方法
                copyFolder(file, newFolder);
            }
        } else {
            //说明是文件,直接复制,用字节流
            File newFile = new File(destFile, srcFile.getName());
            copyFile(srcFile, newFile);
        }
    }

    //字节缓冲流复制文件
    private static void copyFile(File srcFile, File destFile) throws IOException{
        BufferedInputStream bis = new BufferedInputStream(new FileInputStream(srcFile));
        BufferedOutputStream bos = new BufferedOutputStream(new FileOutputStream(destFile));

        byte[] bys = new byte[1024];
        int len;
        while ((len=bis.read(bys))!=-1){
            bos.write(bys,0,len);
        }
        bos.close();
        bis.close();
    }


}
n
    //System.out.println(arr[3]);   
    arr=null;
    System.out.println(arr[0]);	
    //空指针异常==把null赋值给数组	
    //NullPointerException	
}
```

## 5.遍历    arr.length

```java
public static void main(String[] args) 	{
    int[] arr = {11,22,33,44,55,66,77,88,99};	
    //使用通用的遍历格式	
    for(int i=0;i<arr.length;i++){	
        System.out.println(arr[i]);	
    }	
}
```

## 6.数组最大值

```java
public static void main(String[] args) 	{
    int[] arr= {12,65,78,98,45};
    int max = arr[0];	
    for(int x=1;x<arr.length;x++){	
        if(arr[x]>max){		
            max=arr[x];		
        }	
    }		
    System.out.println("max:"+max);
}
```

## 7.数组最小值

```java
public static void main(String[] args) 	{
    int[] arr= {12,65,78,98,45};
    int min = arr[0];	
    for(int x=1;x<arr.length;x++){	
        if(arr[x]<min){	
            min=arr[x];	
        }	
    }	
    System.out.println("min:"+min);
}
```

## 8.不死兔神

![](https://github.com/Continuers/Java/blob/main/picture/18.png)

```java
public static void main(String[] args) { 
    int[] arr = new int[20];  
    arr[0] = 1;  
    //第一个月一对  
    arr[1] = 1;  
    //第二个月一对   
    for (int x=2;x<arr.length;x++){  
        arr[x] = arr[x-2]+arr[x-1];   
    }  
    System.out.println("第二十个月兔子的对数是："+arr[19]);
}
```

## 9.数组元素求和

![](https://github.com/Continuers/Java/blob/main/picture/21.png)

```java
public static void main(String[] args) {
    int[] arr = {68,27,95,88,171,996,51,210}; 
    int sum = 0;  
    for(int x=0;x<arr.length;x++){  
        if (arr[x]%10!=7 && arr[x]/10%10!=7 && arr[x]%2==0){  
            sum += arr[x];        
        }  
    }  
    System.out.println("sum:"+sum);
}
```

## 10.数组内容相同

![](https://github.com/Continuers/Java/blob/main/picture/22.png)

```java
public static void main(String[] args) { 
    int [] arr={11,22,33,44,55};   
    int [] arr2={11,22,33,44,55}; 
    boolean flag = compare(arr,arr2);
    //flag为变量    compare为方法名即函数名   
    System.out.println(flag);
}
public static boolean compare(int[] arr,int[] arr2){
    if (arr.length!=arr2.length){ 
        return false;  
    }  
    for (int x=0;x<arr.length;x++){ 
        if(arr[x]!=arr2[x]){    
            return false;       
        }   
    }   
    return true;
}
```

## 11.数组查找
![](https://github.com/Continuers/Java/blob/main/picture/23.png)

```java
public static void main(String[] args) {  
    int[] arr = {19,28,37,46,50};   
    Scanner sc = new Scanner(System.in);  
    System.out.print("请输入套查找的数据：");
    int number = sc.nextInt();   
    //定义一个索引变量，初始值为-1
    int index = -1;   
    for(int x=0;x<arr.length;x++){  
        if (arr[x]==number){     
            index = x;       
            break;    
        }   
    }   
    System.out.println("index:"+index);
}
```

## 12.反转（数组逆序排列）

```java
public static void main(String[] args) { 
    int[] arr={19,28,37,46,50};   
    for (int start = 0,end=arr.length-1;start<=end;start++,end--){
        int temp = arr[start];     
        arr[start]=arr[end];      
        arr[end] = temp;   
    }  
    printArray(arr);
}
public static void printArray(int[] arr){
    System.out.print("[");  
    for (int x=0;x< arr.length;x++){ 
        if(x==arr.length-1){     
            System.out.print(arr[x]);    
        }       
        else  {   
            System.out.print(arr[x]+",");   
        }   
    }  
    System.out.println("]");
}
```

```java
//输出结果为：[50,46,37,28,19]
```

## 13.评委打分
![](https://github.com/Continuers/Java/blob/main/picture/24.png)

```java
public static void main(String[] args) {
    int[] arr = new int[6];
    //评委人数 
    Scanner sc = new Scanner(System.in); 
    System.out.println("请评委输入评分（0-100）");  
    for (int x=0;x<arr.length;x++)        { 
        System.out.print("请输入第"+(x+1)+"个评委的打分："); 
        arr[x] = sc.nextInt();      
    }      
    int max=getMax(arr);   
    int min=getMin(arr); 
    int sum=getSum(arr);   
    int avg=(sum-max-min)/(arr.length-2);   
    System.out.println("选手最终得分是："+avg);  
}   
public static int getMax(int[] arr)    {   
    int max=arr[0];   
    for(int x=1;x<arr.length;x++)        {    
        if (arr[x]>max)            {   
            max = arr[x];       
        }    
    }      
    return max;   
}   
public static int getMin(int[] arr)    {   
    int min=arr[0];   
    for (int x=1;x<arr.length;x++)        { 
        if(arr[x]<min)  {
            min=arr[x];        
        }    
    }      
    return min;    
}   
public static int getSum(int[] arr)    { 
    int sum=0;  
    for(int x=0;x<arr.length;x++)        { 
        sum+=arr[x];     
    }     
    return sum;    
}
```

## 14.输入5个数输出最大值

```java
public static void main(String[] args) {
    Scanner sc = new Scanner(System.in); 
    int[] arr = new int[5];     
    for (int i=0;i<arr.length;i++)        { 
        System.out.print("请输入第"+(i+1)+"个数:"); 
        arr[i] = sc.nextInt();      
    }      
    int max = arr[0];    
    for (int i=0;i<arr.length;i++)        { 
        if(max<arr[i])            {     
            max=arr[i];        
        }    
    }    
    System.out.println(max);  
}
```





# 15.方法(函数)

## 1.函数调用

方法的定义语法：

```java
访问修饰符 返回值类型 方法名(参数列表) {
    方法体
}
```

==在上面的语法说明中：==

1. **访问修饰符**：代表方法允许被访问的权限范围， 可以是 `public`、`protected`、`private` 或者省略（`default`） ，其中 `public` 表示该方法可以被其他任何代码调用。
2. **返回值类型**：方法返回值的类型，如果方法不返回任何值，则返回值类型指定为 `void` （代表无类型）；如果方法具有返回值，则需要指定返回值的类型，并且在方法体中使用 `return` 语句返回值。
3. **方法名**：是方法的名字，必须使用合法的标识符。
4. **参数列表**：是传递给方法的参数列表，参数可以有多个，多个参数间以逗号隔开，每个参数由参数类型和参数名组成，以空格隔开。当方法被调用时，传递值给参数。这个值被称为实参或变量。参数列表是指方法的参数类型、顺序和参数的个数。参数是可选的，方法可以不包含任何参数。
5. **方法体**：方法体包含具体的语句，定义该方法的功能。

==根据方法是否带参、是否带返回值，可将方法分为四类：==

- 无参无返回值方法
- 无参带返回值方法
- 带参无返回值方法
- 带参带返回值方法

### 1.例一

```java
public class 变量 {
    public static void main(String[] args) { /*调用oushu函数		oushu();*/}

    public static void oushu() {
        int number = 10;
        if (number % 2 == 0) {
            System.out.println(true);
        } else {
            System.out.println(false);
        }
    }
}
```

### 2.例二

```java
public class 变量 {
    public static void main(String[] args) {
        getMax();
    }

    public static void getMax() {
        int a = 10;
        int b = 20;
        if (a > b) {
            System.out.println(a);
        } else {
            System.out.println(b);
        }
    }
} 
```

## 2.带参函数

```java
public class 变量 {
    public static void main(String[] args) 	{
        //常量值的调用	
        isNumber(10);	
        //变量的调用	
        int number=10;	
        isNumber(number);	
    }	
    public static void isNumber(int number)	{
        if(number%2==0){	
            System.out.println(true);	
        }		
        else
        {	
            System.out.println(false);	
        }	
    }
} 
```

## 3.形参和实参

![](https://github.com/Continuers/Java/blob/main/picture/12.png)

```java
package com.itrs2;

public class 变量 {
    public static void main(String[] args) {
        //  Ⅰ 常量值的调用	
        //  getMax(10,20);		
        //  Ⅱ 变量的调用	
        int a = 10;
        int b = 20;
        getMax(a, b);
    }

    public static void getMax(int a, int b) {
        if (a > b) {
            System.out.println(a);
        } else {
            System.out.println(b);
        }
    }
}

```

## 4.带返回值函数

![](https://github.com/Continuers/Java/blob/main/picture/13.png)

```java
package com.itrs2;

public class 变量 {
    public static void main(String[] args) {
        boolean flag = isNumber(10);
        System.out.println(flag);
    }

    public static boolean isNumber(int number) {
        if (number % 2 = 0) {
            return true;
        } else {
            return false;
        }
    }
} 
```

```java
package com.itrs2;

public class 变量 {
    public static void main(String[] args) {
        //第一种方法		
        int result = getMax(10, 20);
        System.out.println(result);
        //第二种方法		
        System.out.println(getMax(10, 20));
    }

    public static int getMax(int a, int b) {
        if (a > b) {
            return a;
        } else {
            return b;
        }
    }
}

```

## 5.方法重载

### 1.

![](https://github.com/Continuers/Java/blob/main/picture/14.png)

```java
package com.itrs2;

public class 变量 {
    public static void main(String[] args) {
        //调用方法		
        // 多个方法在同一个类中	
        // 多个方法具有相同的方法名	
        // 多个方法的参数不相同，类型不同或者数量不同	
        int result = sum(10, 20);
        System.out.println(result);
        double result2 = sum(10.0, 20.0);
        System.out.println(result2);
        int result3 = sum(10, 20, 20);
        System.out.println(result3);
    }

    public static int sum(int a, int b) {
        return a + b;
    }

    public static double sum(double a, double b) {
        return a + b;
    }

    public static int sum(int a, int b, int c) {
        return a + b + c;
    }
}
```

![](https://github.com/Continuers/Java/blob/main/picture/15.png)

### 2.重载类型

```java
package com.itrs2;

public class 变量 {
    public static void main(String[] args) {
        //调用方法		
        System.out.println(compare(10, 20));					//int
        System.out.println(compare((byte) 10, (byte) 20));		//byte		
        System.out.println(compare((short) 10, (short) 20));	//short		
        System.out.println(compare(10L, 20L));					//long	
    }

    //int
    public static boolean compare(int a, int b) {
        System.out.println("int");
        return a == b;
    }

    //byte	
    public static boolean compare(byte a, byte b) {
        System.out.println("byte");
        return a == b;
    }

    //short	
    public static boolean compare(short a, short b) {
        System.out.println("short");
        return a == b;
    }

    //long	
    public static boolean compare(long a, long b) {
        System.out.println("long");
        return a == b;
    }
}
```

## 6.方法的参数传递

```java
package com.itheima;

public class helloworld {
    public static void main(String[] args) {
        int[] arr = {10, 20, 30};
        System.out.println("调用change方法前：" + arr[1]);
        change(arr);
        System.out.println("调用change方法后：" + arr[1]);
    }

    public static void change(int[] arr) {
        arr[1] = 200;
    }
}
```

## 7.数组遍历

```java
package com.itheima;

public class helloworld {
    public static void main(String[] args) {
        int[] arr = {11, 22, 33, 44, 55, 66, 77, 88, 99};
        printArray(arr);
    }

    public static void printArray(int[] arr) {
        System.out.print("[");
        for (int x = 0; x < arr.length; x++) {
            if (x == arr.length - 1) {
                System.out.print(arr[x]);
            } else {
                System.out.print(arr[x] + ", ");
            }
        }
        System.out.println("]");
    }
}
```

## 8.数组最大值

```java
package com.itheima;

public class helloworld {
    public static void main(String[] args) {
        int[] arr = {11, 44, 23, 55, 77, 99};
        int number = getMax(arr);
        System.out.println("number=" + number);
    }

    public static int getMax(int[] arr) {
        int max = arr[0];
        for (int x = 1; x < arr.length; x++) {
            if (arr[x] > max) {
                max = arr[x];
            }
        }
        return max;
    }
}
```

# 16.Debug

## 未

# 17.面向对象

![](https://github.com/Continuers/Java/blob/main/picture/25.png)

## 1.类和对象



![](https://github.com/Continuers/Java/blob/main/picture/26.png)

### 1.对象的使用

新建俩个类

![](https://github.com/Continuers/Java/blob/main/picture/27.png)

```java
package com.itheima;

public class Phone {
    //成员变量    
    String brand;
    int price;

    //成员方法    
    public void call() {
        System.out.println("打电话");
    }

    public void sendMessage() {
        System.out.println("发短信");
    }
}
```

```java
package com.itheima;

public class PhoneDemo {
    public static void main(String[] args) {
        //创建对象        
        Phone p = new Phone();
        //使用成员变量        
        System.out.println(p.brand);
        System.out.println(p.price);
        p.brand = "华为";
        p.price = 5999;
        System.out.println(p.brand);
        System.out.println(p.price);
        p.call();
        p.sendMessage();
    }
}
```

```java
/*运行结果为：null0华为5999打电话发短信*/
```

### 2.学生

```java
package com.itheima;

public class Student {    //成员变量    
    String name;    // null    
    int age;        // 0    
    // 成员方法即函数    

    public void study() {
        System.out.println("好好学习，天天向上");
    }

    public void doHomework() {
        System.out.println("键盘敲烂，月薪过万");
    }
}
```

```java
package com.itheima;

public class StudentDemo {
    public static void main(String[] args) {        //创建对象 
        Student s = new Student();        //使用对象    
        System.out.println(s.name + "," + s.age);
        s.name = "java";
        s.age = 20;
        System.out.println(s.name + "," + s.age);
        s.study();      //调用类Student中的方法    
        s.doHomework(); //调用类Student中的方法  
    }
}
```

```java
/*运行结果null,0java,20好好学习，天天向上键盘敲烂，月薪过万*/
```



## 2.对象内存图

### 1.单个对象

![](https://github.com/Continuers/Java/blob/main/picture/29.png)

### 2.多个对象

![](https://github.com/Continuers/Java/blob/main/picture/28.png)

```java
public class Student {    //成员变量    
    String name;    // null   
    int age;        // 0   

    //成员方法即函数   
    public void study() {
        System.out.println("好好学习，天天向上");
    }

    public void doHomework() {
        System.out.println("键盘敲烂，月薪过万");
    }
}
```

```java
public class StudentDemo2 {
    public static void main(String[] args) {        //创建第一个对象并使用    
        Student s1 = new Student();
        //        System.out.println(s1);     地址    
        s1.name = "c";
        s1.age = 30;
        System.out.println(s1.name + "," + s1.age);
        s1.study();
        s1.doHomework();        //创建第二个对象并使用     
        Student s2 = new Student();
        //System.out.println(s2);    
        s2.name = "mysql";
        s2.age = 23;
        System.out.println(s2.name + "," + s2.age);
        s2.study();
        s2.doHomework();
    }
}
```

```java
/*运行结果c,30好好学习，天天向上键盘敲烂，月薪过万mysql,23好好学习，天天向上键盘敲烂，月薪过万*/
```

### 3.多个对象指向相同

![](https://github.com/Continuers/Java/blob/main/picture/30.png)

```java
public class StudentDemo3 {
    public static void main(String[] args) {        //创建第一个对象并使用 
        Student s1 = new Student();  //设s1地址为001 
        s1.name = "c";
        s1.age = 30;
        System.out.println(s1.name + "," + s1.age);        //把第一个对象的地址赋值给第二个对象       
        Student s2 = s1;   //s2=s1 地址=001  同一个地址 
        s2.name = "mysql";
        s2.age = 23;
        System.out.println(s1.name + "," + s1.age);
        System.out.println(s2.name + "," + s2.age);
    }
}
```

```java
/*运行结果：    c,30    mysql,23    mysql,23*/
```

## 3.成员变量和局部变量

### 定义

![](https://github.com/Continuers/Java/blob/main/picture/31.png)

### 区别

![](https://github.com/Continuers/Java/blob/main/picture/32.png)

## 4.封装

### 1.  private  关键字

![](https://github.com/Continuers/Java/blob/main/picture/33.png)

```java
package com.itrs;

public class Student {    //成员变量
    String name;    // null    //使用private    
    private int age;        // 0    //提供get/set方法 

    public void setAge(int a) //设置成员变量的值 
    {
        if (a < 0 || a > 150) {
            System.out.println("年龄有误");
        } else {
            age = a;
        }
    }

    public int getAge() //获取成员变量的值   
    {
        return age;
    }    //成员方法 

    public void show() {
        System.out.println(name + "," + age);
    }
}
```

```java
package com.itrs;

public class StudentDemo {
    public static void main(String[] args) {        //创建对象  
        Student s = new Student();        //给成员变量赋值 
        s.name = "java";
        s.setAge(100);        //调用show方法      
        s.show();
    }
}
```

###  2. private 关键字的使用

```java
package com.itrs2;

public class Student {    //成员变量 
    private String name;
    private int age;    //get/set方法  

    public void setName(String n) {
        name = n;
    }

    public String getName() {
        return name;
    }

    public void setAge(int a) {
        age = a;
    }

    public int getAge() {
        return age;
    }

    public void show() {
        System.out.println(name + "," + age);
    }
}
```

```java
package com.itrs2;
/*    
    学生测试类
*/
public class StudentDemo {
    public static void main(String[] args) {
        Student s = new Student();        //使用set方法给成员变量赋值     
        s.setName("java");
        s.setAge(100);
        s.show();        //使用get方法获取成员变量的值     
        System.out.println(s.getName() + "_" + s.getAge());
        System.out.println(s.getName() + "," + s.getAge());
    }
}
```

```java
/*  运行结果：   
java,100  
java_100  
java,100
*/
```

### 3. this

![](https://github.com/Continuers/Java/blob/main/picture/34.png)

```java
package com.itrs2;

public class Student {    //成员变量 
    private String name;
    private int age;    //get/set方法
  /*public void setName(String n){ 
         name = n;   
    }*/  

    public void setName(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public int getAge() {
        return age;
    }

    public void show() {
        System.out.println(name + "," + age);
    }
}
```

```java
package com.itrs2;

/*    学生测试类*/public class StudentDemo {
    public static void main(String[] args) {
        Student s = new Student();        //使用set方法给成员变量赋值   
        s.setName("java");
        s.setAge(100);
        s.show();        //使用get方法获取成员变量的值    
        System.out.println(s.getName() + "_" + s.getAge());
        System.out.println(s.getName() + "," + s.getAge());
    }
}
/*		
    java,100
    java_100
    java,100
*/
```

### 4. this内存原理

![](https://github.com/Continuers/Java/blob/main/picture/35.png)

### 5.垃圾回收

```java
    /**		gc源码
     * Runs the garbage collector.
     * <p>
     * Calling the <code>gc</code> method suggests that the Java Virtual
     * Machine expend effort toward recycling unused objects in order to
     * make the memory they currently occupy available for quick reuse.
     * When control returns from the method call, the Java Virtual
     * Machine has made a best effort to reclaim space from all discarded
     * objects.
     * <p>
     * The call <code>System.gc()</code> is effectively equivalent to the
     * call:
     * <blockquote><pre>
     * Runtime.getRuntime().gc()
     * </pre></blockquote>
     *
     * @see     java.lang.Runtime#gc()
     */
    public static void gc() {
        Runtime.getRuntime().gc();
    }
```

```java
package com.itrs1;

public class Waste {
    int num;
    public void finalise(){
        System.out.println("回收垃圾中...");
    }
}

package com.itrs1;

public class WasteDemo {
    public static void main(String[] args) {
        Waste w1 = new Waste();
        w1=null;
        new Waste();
        new Waste();
        System.gc();		//垃圾回收	自动调用 finalise 方法
        for (int i=0;i<1000000000;i++);
    }
}
```

### 6.  封装

![](https://github.com/Continuers/Java/blob/main/picture/36.png)

## 5.构造方法

### 1.构造方法概述

![](https://github.com/Continuers/Java/blob/main/picture/37.png)

```java
package com.itrs3;

public class Student {
    private String name;
    private int age;    //构造方法 

    public Student() {
        System.out.println("无参构造方法");
    }

    public void show() {
        System.out.println(name + "," + age);
    }
}
```

```java
package com.itrs3;/*    测试类 */

public class StudentDemo {
    public static void main(String[] args) {        //创建对象       
        Student s = new Student();
        s.show();
    }
}
```

```java
/*运行结果：无参构造方法null,0*/
```

### 2.构造方法的注意事项

![](https://github.com/Continuers/Java/blob/main/picture/38.png)

```java
package com.itrs3;

public class Student {
    private String name;
    private int age;    //构造方法   

    public Student() {
    }

    public Student(String name) {
        this.name = name;
    }

    public Student(int age) {
        this.age = age;
    }

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public void show() {
        System.out.println(name + "," + age);
    }
}
```

```java
package com.itrs3;/*    测试类 */

public class StudentDemo {
    public static void main(String[] args) {        //创建对象     
        Student s1 = new Student();
        s1.show();          //null,0       
        //public Student(String name)     
        Student s2 = new Student("java");
        s2.show();          //java,0                
        // public Student(int age)      
        Student s3 = new Student(100);
        s3.show();          //null,100                
        // public Student(String name, int age)
        Student s4 = new Student("java", 100);
        s4.show();          //java,100   
    }
}
```

### 3.标准类制作

![](https://github.com/Continuers/Java/blob/main/picture/39.png)

```java
package com.itrs4;

public class Student {    //成员变量 
    private String name;
    private int age;    //构造方法   

    public Student() {
    }

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public int getAge() {
        return age;
    }

    public void show() {
        System.out.println(name + "," + age);
    }
}
```

```java
package com.itrs4;

public class StudentDemo {
    public static void main(String[] args) {        //无参构造方法创建对象后使用setXxx()赋值        
        Student s1 = new Student();
        s1.setName("java");
        s1.setAge(150);
        s1.show();          //java,150        //使用带参构造方法直接创建带有属性值的对象       
        Student s2 = new Student("python", 10);
        s2.show();          //python,10   
    }
}
```

# 18.字符串

## 1. API

### 1.API概述

![](https://github.com/Continuers/Java/blob/main/picture/40.png)

### 2.如何使用帮助文档

1. 右键打开该文档![](https://github.com/Continuers/Java/blob/main/picture/41.png)

2. 找到索引选项卡中的输入框![](https://github.com/Continuers/Java/blob/main/picture/42.png)
3. 输入Random
4. 看类在那个包下
5. 看类的描述信息
6. 看构造方法
7. 看成员方法

### 3.API使用练习

![](https://github.com/Continuers/Java/blob/main/picture/45.png)

```java
import java.util.Scanner;

public class ScannerDemo {
    public static void main(String[] args) {        //创建对象      
        Scanner sc = new Scanner(System.in);        //接收数据     
        System.out.print("请输入一个字符串数据：");      
        //String line = sc.nextLine();     
        String line = sc.nextLine();        //输出结果
        System.out.println("你输入的数据是：" + line);
    }
}
```



## 2. String

### 1.概述

![](https://github.com/Continuers/Java/blob/main/picture/46.png)

### 2.String构造方法

![](https://github.com/Continuers/Java/blob/main/picture/48.png)

```java
public class StringDemo
{
    public static void main(String[] args) {
//      public String():创建一个空白字符串对象,不含有任何内容
        String s1 = new String();
        System.out.println("s1:"+s1);
        //s1:

//      public String(char[] ch):根据字符数组的内容,来创建字符串对象
        char[] ch = {'a','b','c'};
        String s2 = new String(ch);
        System.out.println("s2:"+s2);
        //s2:abc

//      public String(byte[] byte):根据字符数组的内容,来创建字符串对象
        byte[] bys = {97,98,99};   //ASCII码
        String s3 = new String(bys);
        System.out.println("s3:"+s3);
        //s3:abc

//      String s = "abc";直接赋值的方法创建字符串对象,内容就是abc
        String s4 = "abc";
        System.out.println("s4:"+s4);
        //s4:abc
    }
}

//推荐使用直接赋值的方法得到字符串对象，即s4
```

### 3. String 对象的特点

![](https://github.com/Continuers/Java/blob/main/picture/49.png)

![](https://github.com/Continuers/Java/blob/main/picture/50.png)

![](https://github.com/Continuers/Java/blob/main/picture/51.png)

```java
public static void main(String [] args) {
       	//构造方法的方式得到对象
        char[] chs = {'a', 'b', 'c'};
        String s1 = new String(chs);
        String s2 = new String(chs);
        System.out.println(s1 == s2);   //false
        
        //直接赋值的方式得到对象
        String s3 = "abc";		//Stirng的特性，只要字符序列相同(顺序和大小)
        String s4 = "abc";		//JVM都只会建立一个String对象，故地址一致。
		
        System.out.println(s3 == s4);  //true
        //比较字符串对象地址是否相同
        System.out.println(s1 == s3);  //false
 }
```



### 4.字符串的比较

![](https://github.com/Continuers/Java/blob/main/picture/52.png)

==如果想忽略掉大小写关系，比如：java 和 Java 是一样的，那怎么办呢？可以调用 `equalsIgnoreCase()` 方法，其用法与 `equals()` 一致，不过它会忽视大小写。==

```java
public class StringDemo{
    public static void main(String [] args) {
        //构造方法的方式得到对象
        char[] chs = {'a', 'b', 'c'};
        String s1 = new String(chs);
        String s2 = new String(chs);

        //直接赋值的方式得到对象
        String s3 = "abc";
        String s4 = "abc";

        //比较字符串对象地址是否相同   ==地址
        System.out.println(s1 == s2);   //false
        System.out.println(s3 == s4);   //true
        System.out.println(s1 == s3);   //false
        System.out.println("----------------");

        //比较字符串内容是否相同   equals表示内容
        System.out.println(s1.equals(s2));  //true
        System.out.println(s1.equals(s3));  //true
        System.out.println(s3.equals(s4));  //true

    }
}
```

### 5.用户登录

```java
package com.itrs;

import java.util.Scanner;

public class StringDemo {
    public static void main(String[] args) {       
        //已知用户名和密码，定义俩个字符串表示即可 
        String username = "itrs";
        String password = "123456";       
        //用循环实现多次机会，次数明确，采用for循环实现    
        for (int i = 1; i <= 3; i++) {        
            //键盘录入用户名和密码，用Scanner实现        
            Scanner sc = new Scanner(System.in);
            System.out.print("请输入用户名：");
            String name = sc.nextLine();
            System.out.print("请输入密码：");
            String pwd = sc.nextLine();          
            //比较密码，给出相应的提示，字符串内容比较            
            // 用equals()方法实现      
            if (name.equals(username) && pwd.equals(password)) {
                System.out.println("登录成功");
                break;
            } else {
                if (3 - i == 0) {
                    System.out.println("你的账户被锁定，请与管理员联系");
                } else {
                    System.out.println("登录失败，你还有" + (3 - i) + "次机会");
                }
            }
        }
    }
}
```

### 6.遍历字符串

![](https://github.com/Continuers/Java/blob/main/picture/53.png)

```java
package com.itrs;

import java.util.Scanner;

public class StringTest {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("请输入一个字符串:");
        String line = sc.nextLine();    
        //输入sc.nextLine()  Ctrl+Alt+v        
        // 遍历字符串，首先要能够获取到字符串中的每一个字符 
        line.charAt(i)        
        /*for (int i=0;i<3;i++) { 
                   System.out.println(line.charAt(i)); 
                          }*/        
        //遍历字符串，其次要能够获取到字符串的长度 line.length()       
        for (int i = 0; i < line.length(); i++) {
            System.out.println(line.charAt(i));
        }
    }
}
```

### 7.统计字符次数

![](https://github.com/Continuers/Java/blob/main/picture/54.png)

```java
package com.itrs;

import java.util.Scanner;

public class StringTest2 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("请输入一个字符串：");
        String line = sc.nextLine();
        int bigCount = 0;
        int smallCount = 0;
        int numberCount = 0;
        int otherCount = 0;
        for (int i = 0; i < line.length(); i++) {
            char ch = line.charAt(i);
            if (ch >= 'A' && ch <= 'Z') {
                bigCount++;
            } else if (ch >= 'a' && ch <= 'z') {
                smallCount++;
            } else if (ch >= '0' && ch <= '9') {
                numberCount++;
            } else {
                otherCount++;
            }
        }
        System.out.println("大写字母有：" + bigCount + "个");
        System.out.println("小写字母有：" + smallCount + "个");
        System.out.println("数字有：" + numberCount + "个");
        System.out.println("其他字符有：" + otherCount + "个");
    }
}
```

```java
/*    
请输入一个字符串：itrs666GDPI!  
大写字母有：4个  
小写字母有：4个 
数字有：3个   
其他字符有：1个*/
```

### 8.拼接字符串

![](https://github.com/Continuers/Java/blob/main/picture/55.png)

```java
package com.itrs;

public class StringTest2 {
    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 4, 5, 6, 7, 8, 9};       
        //调用方法，用一个变量接收结果     
        String s = arrS(arr);
        System.out.println(s);
    }

    public static String arrS(int[] arr) {   
        //在方法中遍历数组，按照要求进行拼接     
        String s = "";
        s += "[";
        for (int i = 0; i < arr.length; i++) {
            if (i == arr.length - 1) {
                s += arr[i];
            } else {
                s += arr[i];
                s += ",";
            }
        }
        s += "]";
        return s;
    }
}
```

### 9.字符串反转

![](https://github.com/Continuers/Java/blob/main/picture/56.png)

```java
package com.itrs;

import java.util.Scanner;

public class StringTest2 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("请输入一个字符串：");
        String line = sc.nextLine();
        String s = reverse(line);
        System.out.print("反转结果为：");
        System.out.println(s);
    }    //定义一个方法，实现字符串反转   
    /*   
    *  返回值类型：String 
    *  参数：String s   
    */  

    public static String reverse(String s) {
        String ss = "";
        for (int i = s.length() - 1; i >= 0; i--) {
            ss += s.charAt(i);
        }
        return ss;
    }
}
```

### 10.通过帮助文档查看String中的方法

![](https://github.com/Continuers/Java/blob/main/picture/57.png)

## 3.StringBuilder

### 1.概述

![](https://github.com/Continuers/Java/blob/main/picture/58.png)

![](https://github.com/Continuers/Java/blob/main/picture/59.png)

![](https://github.com/Continuers/Java/blob/main/picture/60.png)

### 2.StringBuilder构造方法

![](https://github.com/Continuers/Java/blob/main/picture/61.png)

#### ==切记不能用StringBuilder关键字作为类名==

```java
package com.itrs;

public class StringB/*切记不能用Sting Builder关键字作类名*/ {
    public static void main(String[] args) {
        //public StringBuilder():创建一个空白可变字符串对象，不含有任何内容
        StringBuilder sb = new StringBuilder();
        System.out.println("sb:" + sb);     //sb:
        System.out.println("sb.length():" + sb.length());       //sb.length():0        
        // public StringBuilder(String str):根据字符串的内容，来创建可变字符串对象
        StringBuilder sb2 = new StringBuilder("hello");
        System.out.println("sb2:" + sb2);       //sb2:hello
        System.out.println("sb2.length():" + sb2.length());     //sb2.length():5
    }
}
```



### 3.StringBuilder 的添加 ==append== 和反转 ==reverse==

![](https://github.com/Continuers/Java/blob/main/picture/62.png)

```java
package com.itrs;

public class StringB/*切记不能用Sting Builder关键字作类名*/ {
    public static void main(String[] args) {
        StringBuilder sb = new StringBuilder();
        //        public StringBuilder append(任意类型)：添加数据，并返回对象本身
        //        StringBuilder sb2 = sb.append("hello");
        //        System.out.println("sb:"+sb);		// sb:hello
        //        System.out.println("sb2:"+sb2);	// sb2:hello
        //        System.out.println(sb == sb2);	// true
        //        sb.append("hello");
        //        sb.append("java");
        //        sb.append("sql");
        //        sb.append(100);
        //        System.out.println("sb:"+sb);		// sb:hellojavasql100
        // 链式编程
        sb.append("hello").append("java").append("sql").append(100);
        System.out.println("sb:" + sb);				//sb:hellojavasql100
        // public StringBuilder reverse(): 返回相反的字符序列
        sb.reverse();
        System.out.println("反转后为：" + sb);
        //反转后为：001lqsavajolleh
    }
}
```

### 4.StringBuilder 和 String 相互转换

![](https://github.com/Continuers/Java/blob/main/picture/63.png)

```java
package com.itrs;

public class StringB/*切记不能用Sting Builder关键字作类名*/ {
    public static void main(String[] args) {
        /*        
        //Ⅰ StringBuilder 转换为 String     
        StringBuilder sb = new StringBuilder();      
        sb.append("hello");	
        //错误做法：String s = sb;	  
        //public String toString():通过 toString()就可以实现把 StringBuilder 转换为 String      
        String s = sb.toString();    
        System.out.println(s);  //hello*/
        //Ⅱ  String 转换为 StringBuilder         
        String s = "hello";
        //        错误做法 StringBuilder sb = s;        
        // public StringBuilder(String s): 通过构造方法就可以实现把 String 转换为 StringBuilder      
        StringBuilder sb = new StringBuilder(s);
        System.out.println(sb);
    }
}
```

### 5.字符串拼接升级版

![](https://github.com/Continuers/Java/blob/main/picture/64.png)

```java
package com.itrs;

public class StringB/*切记不能用Sting Builder关键字作类名*/ {
    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 4, 5, 6, 7, 8, 9};      
        //调用方法，用一个变量接收结果     
        String s = arrS(arr);
        System.out.println(s);
    }

    public static String arrS(int[] arr) {     
        //在方法中遍历数组，按照要求进行拼接     
        StringBuilder sb = new StringBuilder();
        sb.append("[");
        for (int i = 0; i < arr.length; i++) {
            if (i == arr.length - 1) {
                sb.append(arr[i]);
            } else {
                sb.append(arr[i]).append(",");
            }
        }
        sb.append("]");      
        //将String Builder类型转换为String类型     
        String s = sb.toString();
        return s;
    }
}
```

### 6.字符串反转升级版

```java
package com.itrs;/*	黑马版（安全性，复用性高）*/

import java.util.Scanner;

public class StringB {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("请输入一个字符串：");
        String line = sc.nextLine();
        String s = myReverse(line);
        System.out.println("反转后为：" + s);
    }

    public static String myReverse(String s) {
        //在方法中用StringBuilder实现字符串的反转，并把结果转成String返回                
        // String---StringBuilder---reverse()---String               
        /* 
        StringBuilder sb = new StringBuilder(s);           
        sb.reverse();         
        String ss = sb.toString();     
        return ss;        
           */
        return new StringBuilder(s).reverse().toString();
    }
}
package com.itrs2;
        /*	itrs版*/
        import java.util.Scanner;

public class StringB {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("请输入你要反转的字符：");
        String s = sc.nextLine();
        StringBuilder sb = new StringBuilder(s);
        sb.reverse();
        System.out.println(sb);
    }
}
```

### 7.通过帮助文档查看 StringBuilder 中的方法

![](https://github.com/Continuers/Java/blob/main/picture/65.png)

# 19.集合基础

## 1.集合概述

![](https://github.com/Continuers/Java/blob/main/picture/66.png)

## 2. ArrayList构造方法和添加方法

```java
package com.itrs;

import java.util.ArrayList;

public class ArrayListDemo/*切记不能用Sting Builder关键字作类名*/ {
    public static void main(String[] args) {
        /*	public ArrayList(); 创建一个空的集合对象	*/
        //ArrayList<String> array = new ArrayList<>();   
        ArrayList<String> array = new ArrayList<String>();
        /*	public boolean add(E e): 将指定的元素追加到此集合的末尾	*/
        //System.out.println(array.add("hello"));   
        array.add("hello");
        array.add("world");
        array.add("java");
        //System.out.println("array:"+ array);
        //       运行结果: array:[hello, world, java]        
        /*	public void add(int index,E element): 在此集合中的指定位置插入指定的元素	*/
        //array.add(1,"javase");        
        // System.out.println("array:"+ array);
        //       运行结果: array:[hello, javase, world, java]        
        // array.add(3,"javaweb");
        //       运行结果: array:[hello, world, java, javaweb]   
        array.add(4, "JDK11");        /*	越界	*/
        //       运行结果:  IndexOutOfBoundsException
        System.out.println("array:" + array);
    }
}
```

## 3. ArrayList 集合常用方法

![](https://github.com/Continuers/Java/blob/main/picture/67.png)

```java
package com.itrs;

import java.util.ArrayList;

public class ArrayListDemo {
    public static void main(String[] args) {
        ArrayList<String> array = new ArrayList<>();
        array.add("hello");
        array.add("java");
        array.add("hi");
        array.add("javaweb");        
        /*public boolean remove(Object o): 删除指定元素，放回删除是否成功*/
        System.out.println(array.remove("hi"));        //true        
        // array:[hello, java, javaweb]        
        /*public E remove(int index): 删除指定索引处的元素，返回被删除是否成功*/      
        System.out.println(array.remove(0));            //hello        
        // array:[java, hi, javaweb]   
        System.out.println(array.remove(4));            
        //越界 IndexOutOfBoundsException        
        /*public E set(int index,E element): 修改指定索引处的元素，返回被修改的元素*/     
        System.out.println(array.set(2, "javaee"));    //hi        
        // array:[hello, java, javaee, javaweb] 
        System.out.println(array.set(4, "javaee"));        
        //越界 IndexOutOfBoundsException        
        /*public E get(int index): 返回指定索引处的元素*/     
        System.out.println(array.get(0));            //hello     
        System.out.println(array.get(1));                //java    
        System.out.println(array.get(2));                //hi       
        System.out.println(array.get(3));                //javaweb     
        System.out.println(array.get(4));            
        //越界 IndexOutOfBoundsException     
        /*public int size(): 返回集合中的元素的个数*/
        System.out.println(array.size());           //4        
        // 输出  
        System.out.println("array:" + array);
    }
}
```

## 4.存储字符串并遍历

![](https://github.com/Continuers/Java/blob/main/picture/68.png)

```java
package com.itrs;

import java.util.ArrayList;

public class ArrayListDemo {
    public static void main(String[] args) {
        ArrayList<String> array = new ArrayList<>();
        array.add("黑马");
        array.add("rs");
        array.add("win");
        /*遍历集合，首先要能够获取到集合中的每一个元素，这个通过gei(int index)方法实现*/
        System.out.println(array.get(0));
        //黑马
        /*遍历集合，其次要能够获取集合的长度，这个通过size()方法实现*/
        System.out.println(array.size());      //3
        /*遍历集合的通用格式*/
        for (int i = 0; i < array.size(); i++) {
            //黑马
            String s = array.get(i);      
            System.out.println(s);           //黑马 rs  win
        }
    }
}
```

## 5.存储学生对象并遍历

![](https://github.com/Continuers/Java/blob/main/picture/69.png)

```java
package com.itrs5;

public class Student {
    private String name;
    private int age;

    public Student() {
    }

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public void SetName(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public int getAge() {
        return age;
    }
}
```

```java
package com.itrs5;

import java.util.ArrayList;

public class ArrayListTest {
    public static void main(String[] args) {
        ArrayList<Student> array = new ArrayList<Student>();
        //创建学生对象 
        Student s1 = new Student("黄开开", 20);
        Student s2 = new Student("rs", 20);
        Student s3 = new Student("黑马", 100);
        //添加学生对象到集合中  
        array.add(s1);
        array.add(s2);
        array.add(s3);
        //遍历集合，采用通用遍历格式实现      
        for (int i = 0; i < array.size(); i++) {
            Student s = array.get(i);
            System.out.println(s.getName() + "," + s.getAge());
        }
    }
}
//黄开开,20//rs,20//黑马,100
```

## 6.存储学生对象并遍历升级版

![](https://github.com/Continuers/Java/blob/main/picture/70.png)

```java
package com.itrs5;

public class Student {
    private String name;
    private int age;

    public Student() {
    }

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public int getAge() {
        return age;
    }
}
```

```java
package com.itrs5;

import java.util.ArrayList;
import java.util.Scanner;

public class ArrayListTest {
    public static void main(String[] args) {
        ArrayList<Student> array = new ArrayList<Student>();        
        /*
        add(array);        
        add(array);        
        add(array);
        */
        Scanner sc = new Scanner(System.in);
        System.out.print("请输入录信息的人数：");
        int num = sc.nextInt();
        for (int j = 0; j < num; j++) {
            add(array);
        }
        for (int i = 0; i < array.size(); i++) {
            Student s = array.get(i);
            System.out.println(s.getName() + "," + s.getAge());
        }
    }

    public static void add(ArrayList<Student> array) {
        /*键盘录入学生对象所需要的数据*/
        Scanner sc = new Scanner(System.in);
        System.out.print("请输入名字：");
        String name = sc.nextLine();
        System.out.print("请输入年龄：");
        int age = sc.nextInt();
        //创建学生对象，把键盘录入的数据赋值给学生对象的成员变量
        Student s = new Student();
        s.setName(name);
        s.setAge(age);
        //往集合中添加学生对象
        array.add(s);
    }
}
```

```java
/*   
请输入录信息的人数：2 
请输入名字：hrs   
请输入年龄：20   
请输入名字：hxy 
请输入年龄：20  
hrs,20  
hxy,20
*/
```

# 20.学生管理系统

## 1.项目演示

![](https://github.com/Continuers/Java/blob/main/picture/71.png)

## 2.学生管理系统实现思路

![](https://github.com/Continuers/Java/blob/main/picture/72.png)

## 3.定义学生类



![](https://github.com/Continuers/Java/blob/main/picture/73.png)

```java
package com.itrs;/*    学生类 */

public class Student {    //学号  
    public String sid;    //姓名 
    public String name;    //年龄 
    public String age;    //居住地  
    public String address;

    public Student() {                    //ALT + Insert   
    }                                    //Constructor                            				
    // com.itrs.Student  

    public Student(String sid, String name, String age, String address) {
        this.sid = sid;                        //ALT + Insert      
        this.name = name;                    //Constructor  
        this.age = age;                        //Shift(all)  
        this.address = address;
    }

    public String getSid() {                 //ALT + Insert     
        return sid;                         //Getter and Setter    
    }                                     //Shift(all)  

    public void setSid(String sid) {
        this.sid = sid;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getAge() {
        return age;
    }

    public void setAge(String age) {
        this.age = age;
    }

    public String getAddress() {
        return address;
    }

    public void setAddress(String address) {
        this.address = address;
    }
}
```

## 4.主界面的代码编写

![](https://github.com/Continuers/Java/blob/main/picture/79.png)

```java
package com.itrs;

import java.util.Scanner;

public class StudentManager {
    public static void main(String[] args) {        
        //用循环完成再次回到主界面   
        while (true) {            //用输出语句完成主界面的编写           
            System.out.println("--------欢迎来到学生管理系统--------");
            System.out.println("1. 添加学生信息");
            System.out.println("2. 删除学生信息");
            System.out.println("3. 修改学生信息");
            System.out.println("4. 查看学生信息");
            System.out.println("5. 退出");
            System.out.print("请输入你的选择：");           
            //Scanner实现键盘录入数据    
            Scanner sc = new Scanner(System.in);
            String line = sc.nextLine();            
            //用switch语句完成操作的选择    
            switch (line) {
                case "1":
                    System.out.println("添加学生信息");
                    break;
                case "2":
                    System.out.println("删除学生信息");
                    break;
                case "3":
                    System.out.println("修改学生信息");
                    break;
                case "4":
                    System.out.println("查看学生信息");
                    break;
                case "5":
                    System.out.println("谢谢使用");
                    System.exit(0); //JVM退出     
            }
        }
    }
}
```

## 5.添加学生的代码编写

![](https://github.com/Continuers/Java/blob/main/picture/80.png)

```java
package com.itrs;

import java.util.Scanner;

public class StudentManager {
    public static void main(String[] args) {        
        //创建集合对象，用于存储学生数据   
        ArrayList<Student> array = new ArrayList<Student>();        
        //用循环完成再次回到主界面     
        while (true) {           
            //用输出语句完成主界面的编写         
            System.out.println("--------欢迎来到学生管理系统--------");
            System.out.println("1. 添加学生信息");
            System.out.println("2. 删除学生信息");
            System.out.println("3. 修改学生信息");
            System.out.println("4. 查看学生信息");
            System.out.println("5. 退出");
            System.out.print("请输入你的选择：");            
            //Scanner实现键盘录入数据  
            Scanner sc = new Scanner(System.in);
            String line = sc.nextLine();            
            //用switch语句完成操作的选择       
            switch (line) {
                case "1":
                    //System.out.println("添加学生信息");                  
                    addStudent(array);
                    break;
                case "2":
                    System.out.println("删除学生信息");
                    break;
                case "3":
                    System.out.println("修改学生信息");
                    break;
                case "4":
                    System.out.println("查看学生信息");
                    break;
                case "5":
                    System.out.println("谢谢使用");
                    System.exit(0); //JVM退出    
            }
        }
    }    //定义一个方法，用于添加学生信息  

    public static void addStudent(ArrayList<Student> array) {        
        //键盘录入学生对象所需要的数据，显示提示信息，提示要输入何种信息    
        Scanner sc = new Scanner(System.in);
        System.out.print("请输入学生学号：");
        String sid = sc.nextLine();
        System.out.print("请输入学生姓名：");
        String name = sc.nextLine();
        System.out.print("请输入学生年龄：");
        String age = sc.nextLine();
        System.out.print("请输入学生居住地：");
        String address = sc.nextLine();        
        //创建学生对象，把键盘录入的数据赋值给学生对象的成员变量   
        Student s = new Student();
        s.setSid(sid);
        s.setName(name);
        s.setAge(age);
        s.setAddress(address);        
        //将学生对象添加到集合中     
        array.add(s);        
        //给出添加成功提示   
        System.out.println("添加学生信息成功");
    }
}
```

## 6.查看学生的代码编写

![](https://github.com/Continuers/Java/blob/main/picture/81.png)

```java
	/*主函数调用查看学生信息方法*/  
case "4":           
findAllStudent(array);       
break;
-------------------------------------------------  
    //定义一个方法，用于查看学生信息  
public static void findAllStudent(ArrayList<Student> array) { 
    //显示表头信息      
        System.out.println("学号\t\t\t姓名\t\t年龄\t\t居住地");    
    /*将集合中数据取出按照对应格式显示学生信息，年龄显示补充“岁”*/     
    for (int i = 0; i < array.size(); i++) {  
        Student s = array.get(i);    
        System.out.println(s.getSid() + "\t\t" + s.getName() + "\t\t" + s.getAge() + "岁\t\t" + s.getAddress());        }
}
```

## 7.查看学生的代码编写升级版

```java
	/*主函数调用查看学生信息方法*/    
findAllStudent(array);
-----------------------------------------------------
    
    //定义一个方法，用于查看学生信息  
    public static void findAllStudent(ArrayList<Student> array) {
    //判断集合中是否又数据，如果没有显示提示信息       
    if (array.size()==0){        
        System.out.println("无信息，请先添加信息再查询");    
        //为了让程序不再执行，给出return; 
        return;      
    }       
    //显示表头信息    
    System.out.println("学号\t\t\t姓名\t\t年龄\t\t居住地");   
    /*将集合中数据取出按照对应格式显示学生信息，年龄显示补充“岁”*/     
    for (int i = 0; i < array.size(); i++) {       
        Student s = array.get(i);        
        System.out.println(s.getSid() + "\t\t\t" + s.getName() + "\t\t" + s.getAge() + "岁\t" + s.getAddress());        }  
}
```

## 8.删除学生的代码编写

![](https://github.com/Continuers/Java/blob/main/picture/82.png)

```java
	/*主函数调用删除学生信息方法*/
case "2":
deleteStudent(array);
break;
--------------------------------------------------------------------------------------------	
    //定义一个方法，用于删除学生信息    
    public static void deleteStudent(ArrayList<Student> array){
    Scanner sc = new Scanner(System.in);  
    System.out.print("请输入你要删除的学生的学号：");     
    String sid = sc.nextLine();      
    //遍历集合将对应学生对象从集合中删除     
    for (int i=0;i<array.size();i++){    
        Student s = array.get(i);     
        if (s.getSid().equals(sid)){   
            array.remove(i);          
            break;      
        }   
    }   
    //给出删除成功提示      
	System.out.println("删除学生信息成功");  
}
```

## 9.修改学生的代码的编写

![](https://github.com/Continuers/Java/blob/main/picture/83.png)

```java
	/*主函数调用修改学生信息方法*/
case "3": 
updateStudent(array); 
break;
----------------------------------------------------  
    //定义一个方法，用于修改学生信息 
    public static void updateStudent(ArrayList<Student> array){
    Scanner sc = new Scanner(System.in); 
    System.out.println("请输入你要修改的学生的学号：");  
    String sid = sc.nextLine();       
    System.out.println("请输入学生的新姓名：");     
    String name = sc.nextLine();    
    System.out.println("请输入学生的新年龄：");    
    String age = sc.nextLine();     
    System.out.println("请输入学生的新居住地：");   
    String address = sc.nextLine();   
    //创建学生对象                                      
    Student s = new Student();     
    s.setSid(sid);   
    s.setName(name);    
    s.setAge(age);    
    s.setAddress(address);    
    //遍历集合修改对应的学生信息                                      
    for (int i=0;i< array.size();i++){   
        Student student = array.get(i);    
        if (student.getSid().equals(sid)){  
            array.set(i,s);         
            break;        
        }   
    }        
    //给出修改成功提示                            
    System.out.println("修改学生信息成功");    }
```



## 10.解决删除/修改学生学号不存在问题

```java
//定义一个方法，用于删除学生信息 
public static void deleteStudent(ArrayList<Student> array){
    Scanner sc = new Scanner(System.in);
    System.out.print("请输入你要删除的学生的学号：");   
    String sid = sc.nextLine();      
    //在删除学生操作钱对学号是否存在进行判断    
    //如果不存在，显示提示信息   
    //如果存在，执行删除操作                                                  
    int index = -1;    
    for (int i=0;i<array.size();i++){ 
        Student s = array.get(i);   
        if (s.getSid().equals(sid)){   
            index = i;        
            break;     
        } 
    }     
    if (index==-1){ 
        System.out.println("该信息不存在，请重新输入");  
        return;    
    } else {  
        /*array.remove(index);  
        //给出删除成功提示 
        System.out.println("删除学生成功");*/   
        //遍历集合将对应学生对象从集合中删除       
                                                  
        for (int i=0;i<array.size();i++){    
            Student s = array.get(i);      
            if (s.getSid().equals(sid)){  
                array.remove(i);          
                break;            
            }     
        }           
        
        //给出删除成功提示                   
        System.out.println("删除学生信息成功");        }    }
```

```java
//定义一个方法，用于修改学生信息 
public static void updateStudent(ArrayList<Student> array){ 
    Scanner sc = new Scanner(System.in);    
    System.out.print("请输入你要修改的学生的学号："); 
    String sid = sc.nextLine();    
    //在修改学生操作钱对学号是否存在进行判断   
    //如果不存在，显示提示信息      
    //如果存在，执行修改操作   
    int index = -1;   
    for (int i=0;i<array.size();i++){  
        Student s = array.get(i);  
        if (s.getSid().equals(sid)){   
            index = i;       
            break;       
        }     
    }    
    if (index==-1){      
        System.out.println("该信息不存在，请重新输入");    
        return;    
    } else {   
        /*array.set(index);   
        //给出修改成功提示    
        System.out.println("修改学生信息成功");*/       
        System.out.print("请输入学生的新姓名：");   
        String name = sc.nextLine();       
        System.out.print("请输入学生的新年龄：");   
        String age = sc.nextLine();         
        System.out.print("请输入学生的新居住地：");    
        String address = sc.nextLine();        
    	//创建学生对象      
   	 	Student s = new Student();     
        s.setSid(sid);       
        s.setName(name);    
        s.setAge(age);       
        s.setAddress(address);         
    	//遍历集合修改对应的学生信息        
    	for (int i=0;i< array.size();i++){  
            Student student = array.get(i);  
            if (student.getSid().equals(sid)){  
                array.set(i,s);             
                break;         
            }          
        }      
    }       
    //给出修改成功提示   
    System.out.println("修改学生信息成功");    }
```

## 11.解决添加学生学号重复问题

![](https://github.com/Continuers/Java/blob/main/picture/84.png)

```java
//定义一个方法，判断学号是否被使用 
public static boolean isUsed(ArrayList<Student> array,String sid){   
    //如果与集合中的某一个学生学号相同，返回true;如果不相同，返回false    
    boolean flag = false;     
    for (int i=0;i<array.size();i++){       
        Student s = array.get(i);    
        if (s.getSid().equals(sid)){  
            flag = true;        
            break;        
        }       
    }    
    return flag;   
}
```

```java
//定义一个方法，用于添加学生信息 
public static void addStudent(ArrayList<Student> array) {  
    //键盘录入学生对象所需要的数据，显示提示信息，提示要输入何种信息  
    Scanner sc = new Scanner(System.in);     
    //为了让sid在while循环外面被访问到，我们就把他定义在了循环外   
    String sid;      
    //为了让程序能够回到这里，我们使用循环实现    
    while (true) {       
        System.out.print("请输入学生学号：");   
        sid = sc.nextLine();      
        /*调用isUsed函数*/       
        boolean flag = isUsed(array, sid);//若学号不同 flag=false   
        if (flag) {       
            System.out.println("你输入的学号已经被使用，请重新输入");   
        }else{      
            break;   
        }     
    }    
    System.out.print("请输入学生姓名：");     
    String name = sc.nextLine();     
    System.out.print("请输入学生年龄：");   
    String age = sc.nextLine();     
    System.out.print("请输入学生居住地：");    
    String address = sc.nextLine();    
    //创建学生对象，把键盘录入的数据赋值给学生对象的成员变量 
    Student s = new Student();    
    s.setSid(sid);   
    s.setName(name);    
    s.setAge(age);     
    s.setAddress(address); 
    //将学生对象添加到集合中   
    array.add(s);     
    //给出添加成功提示     
    System.out.println("添加学生信息成功");  
}
```

## 12.学生管理系统源码

```java
package com.itrs;

/*    学生类 */
public class Student {
    //学号  
    public String sid;
    //姓名  
    public String name;
    //年龄   
    public String age;
    //居住地  
    public String address;

    public Student() {
        //ALT + Insert    
    }

    //Constructor      
    //com.itrs.Student  
    public Student(String sid, String name, String age, String address) {
        this.sid = sid;
        this.name = name;
        this.age = age;
        this.address = address;
    }

    //ALT + Insert   
    //Constructor    
    //Shift(all)  
    public String getSid() {
        //ALT + Insert    
        return sid;
        //Getter and Setter  
    }

    //Shift(all)  
    public void setSid(String sid) {
        this.sid = sid;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getAge() {
        return age;
    }

    public void setAge(String age) {
        this.age = age;
    }

    public String getAddress() {
        return address;
    }

    public void setAddress(String address) {
        this.address = address;
    }
}
```

```java
package com.itrs;/*	测试类*/

import java.util.ArrayList;
import java.util.Scanner;

public class StudentManager {
    public static void main(String[] args) {
        //创建集合对象，用于存储学生数据   
        ArrayList<Student> array = new ArrayList<Student>();
        //用循环完成再次回到主界面     
        while (true) {
            //用输出语句完成主界面的编写    
            System.out.println("--------欢迎来到学生管理系统--------");
            System.out.println("1. 添加学生信息");
            System.out.println("2. 删除学生信息");
            System.out.println("3. 修改学生信息");
            System.out.println("4. 查看学生信息");
            System.out.println("5. 退出");
            System.out.print("请输入你的选择：");
            //Scanner实现键盘录入数据    
            Scanner sc = new Scanner(System.in);
            String line = sc.nextLine();
            //用switch语句完成操作的选择           
            switch (line) {
                case "1":
                    addStudent(array);
                    break;
                case "2":
                    deleteStudent(array);
                    break;
                case "3":
                    updateStudent(array);
                    break;
                case "4":
                    findAllStudent(array);
                    break;
                case "5":
                    System.out.println("谢谢使用");
                    System.exit(0); //JVM退出     
            }
        }
    }

    //定义一个方法，用于添加学生信息   
    public static void addStudent(ArrayList<Student> array) {
        //键盘录入学生对象所需要的数据，显示提示信息，提示要输入何种信息      
        Scanner sc = new Scanner(System.in);
        //为了让sid在while循环外面被访问到，我们就把他定义在了循环外    
        String sid;
        //为了让程序能够回到这里，我们使用循环实现     
        while (true) {
            System.out.print("请输入学生学号：");
            sid = sc.nextLine();
            boolean flag = isUsed(array, sid);
            if (flag) {
                System.out.println("你输入的学号已经被使用，请重新输入");
            } else {
                break;
            }
        }
        System.out.print("请输入学生姓名：");
        String name = sc.nextLine();
        System.out.print("请输入学生年龄：");
        String age = sc.nextLine();
        System.out.print("请输入学生居住地：");
        String address = sc.nextLine();
        //创建学生对象，把键盘录入的数据赋值给学生对象的成员变量      
        Student s = new Student();
        s.setSid(sid);
        s.setName(name);
        s.setAge(age);
        s.setAddress(address);
        //将学生对象添加到集合中       
        array.add(s);
        //给出添加成功提示    
        System.out.println("添加学生信息成功");
    }

    //定义一个方法，判断学号是否被使用 
    public static boolean isUsed(ArrayList<Student> array, String sid) {
        //如果与集合中的某一个学生学号相同，返回true;如果不相同，返回false    
        boolean flag = false;
        for (int i = 0; i < array.size(); i++) {
            Student s = array.get(i);
            if (s.getSid().equals(sid)) {
                flag = true;
                break;
            }
        }
        return flag;
    }

    //定义一个方法，用于查看学生信息  
    public static void findAllStudent(ArrayList<Student> array) {
        //判断集合中是否又数据，如果没有显示提示信息  
        if (array.size() == 0) {
            System.out.println("无信息，请先添加信息再查询");
            //为了让程序不再执行，给出return;       
            return;
        }
        //显示表头信息   
        System.out.println("学号\t\t\t姓名\t\t年龄\t\t居住地");
        /*将集合中数据取出按照对应格式显示学生信息，年龄显示补充“岁”*/
        for (int i = 0; i < array.size(); i++) {
            Student s = array.get(i);
            System.out.println(s.getSid() + "\t\t\t" + s.getName() + "\t" + s.getAge() + "岁\t" + s.getAddress());
        }
    }

    //定义一个方法，用于删除学生信息  
    public static void deleteStudent(ArrayList<Student> array) {
        Scanner sc = new Scanner(System.in);
        System.out.print("请输入你要删除的学生的学号：");
        String sid = sc.nextLine();
        //在删除学生操作钱对学号是否存在进行判断   
        //如果不存在，显示提示信息    
        //如果存在，执行删除操作     
        int index = -1;
        for (int i = 0; i < array.size(); i++) {
            Student s = array.get(i);
            if (s.getSid().equals(sid)) {
                index = i;
                break;
            }
        }
        if (index == -1) {
            System.out.println("该信息不存在，请重新输入");
            return;
        } else {          
            /*array.remove(index);    
            //给出删除成功提示     
            System.out.println("删除学生成功");*/
            //遍历集合将对应学生对象从集合中删除     
            for (int i = 0; i < array.size(); i++) {
                Student s = array.get(i);
                if (s.getSid().equals(sid)) {
                    array.remove(i);
                    break;
                }
            }
            //给出删除成功提示       
            System.out.println("删除学生信息成功");
        }
    }

    //定义一个方法，用于修改学生信息 
    public static void updateStudent(ArrayList<Student> array) {
        Scanner sc = new Scanner(System.in);
        System.out.print("请输入你要修改的学生的学号：");
        String sid = sc.nextLine();
        //在修改学生操作钱对学号是否存在进行判断        
        // 如果不存在，显示提示信息        
        // 如果存在，执行修改操作      
        int index = -1;
        for (int i = 0; i < array.size(); i++) {
            Student s = array.get(i);
            if (s.getSid().equals(sid)) {
                index = i;
                break;
            }
        }
        if (index == -1) {
            System.out.println("该信息不存在，请重新输入");
            return;
        } else {        
            /*array.set(index);      
              //给出修改成功提示            
              System.out.println("修改学生信息成功");*/
            System.out.print("请输入学生的新姓名：");
            String name = sc.nextLine();
            System.out.print("请输入学生的新年龄：");
            String age = sc.nextLine();
            System.out.print("请输入学生的新居住地：");
            String address = sc.nextLine();
            //创建学生对象      
            Student s = new Student();
            s.setSid(sid);
            s.setName(name);
            s.setAge(age);
            s.setAddress(address);
            //遍历集合修改对应的学生信息     
            for (int i = 0; i < array.size(); i++) {
                Student student = array.get(i);
                if (student.getSid().equals(sid)) {
                    array.set(i, s);
                    break;
                }
            }
        }
        //给出修改成功提示     
        System.out.println("修改学生信息成功");
    }
}
```





# 21.继承

## 1.概述

![](https://github.com/Continuers/Java/blob/main/picture/85.png)

![](https://github.com/Continuers/Java/blob/main/picture/86.png)

![](https://github.com/Continuers/Java/blob/main/picture/87.png)

```java
package com.itrs3;
/*	父类*/
public class Fu {  
    public void show(){   
        System.out.println("show方法被调用");  
    }
}
```

```java
package com.itrs3;
/*	子类*/
public class Zi extends Fu {
    public void method(){   
        System.out.println("method被调用"); 
    }
}
```

```java
package com.itrs3;
/*	测试类*/
public class Demo {
    public static void main(String[] args) { 
        Fu f = new Fu();    
        f.show();    //show方法被调用   
        Zi z = new Zi();    
        z.method();     //method被调用   
        /*public class Zi extends Fu */   
        /*子类继承了父类，子类可以有自己的方法，也有父类的方法*/ 
        z.show();      
//show方法被调用   
    }
}
```



## 2.继承的好处和弊端

![](https://github.com/Continuers/Java/blob/main/picture/88.png)



## 3.继承中变量的访问特点

![](https://github.com/Continuers/Java/blob/main/picture/89.png)

```java
package com.itrs3;
/*	父类*/
public class Fu {   
    //年龄  
    public int  age = 40;  
}
```

```java
package com.itrs3;
/*    子类*/
public class Zi extends Fu { 
    //身高 
    public int height = 175;  
    public int  age = 20;   
    public void show(){    
        int age = 19;    
        System.out.println(age);   
        //就近原则19--20--40   
        System.out.println(height);  
        //175  
        System.out.println(weight);   
        //报错  
    }
}
```

```java
package com.itrs3;
/*    测试类*/
public class Demo {   
    public static void main(String[] args) { 
        Zi z = new Zi(); 
        z.show();
    }
}
```



## 4.super

![](https://github.com/Continuers/Java/blob/main/picture/90.png)

```java
package com.itrs3;
/*    父类*/
public class Fu { 
    //年龄
    public int  age = 40;
}
```

```java
package com.itrs3;
/*    子类*/
public class Zi extends Fu {  
    public int  age = 20;  
    public void show(){  
        int age = 19;     
        System.out.println(age);  //19        
        //访问本类的成员变量age  
        System.out.println(this.age);   //20   
        //访问父类的成员变量age    
        System.out.println(super.age);  //40   
    }
}
```

```java
package com.itrs3;
/*    测试类*/
public class Demo { 
    public static void main(String[] args) {  
        //创建对象，调用方法  
        Zi z = new Zi();     
        z.show();   
    }
}
```



## 5.继承中构造方法的访问特点

![](https://github.com/Continuers/Java/blob/main/picture/91.png)

```java
package com.itrs3;
/*    父类*/
public class Fu { 
    public Fu(){    
        System.out.println("Fu中无参构造方法被调用");  
    }  
    public Fu(int age){
        System.out.println("Fu中带参构造方法被调用");
    }
}
```

```java
package com.itrs3;
/*    子类*/
public class Zi extends Fu { 
    public Zi(){    
        super(19);
        //父类中默认无参构造方法     
        System.out.println("Zi中无参构造方法被调用");  
    }    
    public Zi(int age){   
        super(20);   
        System.out.println("Zi中带参构造方法被调用");  
    }
}
```

```java
package com.itrs3;
/*    测试类*/
public class Demo { 
    public static void main(String[] args) {  
        //创建对象，调用方法     
        Zi z = new Zi();	
        //Fu中带参构造方法被调用	
        //Zi中无参构造方法被调用    
        Zi z2 = new Zi(20);		
    	//Fu中带参构造方法被调用	
        //Zi中带参构造方法被调用 
    }
}
```



## 6.继承中成员方法的访问特点

![](https://github.com/Continuers/Java/blob/main/picture/92.png)

```java
package com.itrs3;
/*    父类*/
public class Fu { 
    public void show(){   
        System.out.println("Fu中show()方法被调用"); 
    }
}
```

```java
package com.itrs3;
/*    子类*/
public class Zi extends Fu {
    public void method(){    
        System.out.println("Zi中method()方法调用"); 
    }  
    public void show(){  
        super.show();    
        System.out.println("Zi中show()方法被调用");   
    }
}
```

```java
package com.itrs3;
/*    测试类*/
public class Demo { 
    public static void main(String[] args) {   
        //创建对象，调用方法    
        Zi z = new Zi();      
        z.method();          // Zi中method()方法调用
        z.show();     		//  Fu中show()方法被调用
    }
}
```



## 7.super内存图

![](https://github.com/Continuers/Java/blob/main/picture/93.png)



## 8.方法重写

![](https://github.com/Continuers/Java/blob/main/picture/94.png)



```java
package com.itrs4;
/*    手机类*/
public class Phone { 
    public void call(String name){  
        System.out.println("给"+name+"打电话");  
    }
}
```

```java
package com.itrs4;
public class NewPhone extends Phone{  
    @Override	
    /*注解*/
    public void call(String name){      
        System.out.println("开启视频功能");    
        super.call(name);  
    }
}
```

```java
package com.itrs4;
/*     测试类*/
public class PhoneDemo {  
    public static void main(String[] args) {   
        Phone p = new Phone();       
        p.call("java");    
        System.out.println("---------");  
        NewPhone np = new NewPhone();     
        np.call("js");   
    }
}
```



## 9.方法重写注意事项

![](https://github.com/Continuers/Java/blob/main/picture/95.png)

```java
package com.itrs4;
public class Fu { 
    private void show(){   
        System.out.println("Fu中show()方法被调用"); 
    }  
    /*public访问权限比private高*/   
    /*public void method(){  
    System.out.println("Fu中method()方法被调用");
    }*/  
    void method(){   
        System.out.println("Fu中method()方法被调用");  
    }
}
```

```java
package com.itrs4;
public class Zi extends Fu { 
    /*   
    @Override  
    private void show(){  
    System.out.println("Zi中show()方法被调用"); 
    }//        报错    */  
    /*@Override   
    public void method(){  
    System.out.println("Zi中method()方法被调用"); 
    }*/    
    @Override   
    public void method(){
        //写不写public都可以，只要访问权限不比父类的低就行  
        System.out.println("Zi中method()方法被调用");
    }
}
```



## 10.java中继承的注意事项

![](https://github.com/Continuers/Java/blob/main/picture/96.png)

```java
package com.itrs2;
public class Granddad {  
    public void drink(){   
        System.out.println("爷爷爱喝酒");  
    }
}
```

```java
package com.itrs2;
public class Mother {  
    public void dance(){      
        System.out.println("妈妈爱跳舞");  
    }
}
```

```java
package com.itrs2;
public class Father extends Granddad {  
    public void smoke(){     
        System.out.println("爸爸爱抽烟");  
    }
}
```

```java
package com.itrs2;
/*    public class Son extends Father,Mother {  
//java中类只支持单继承，不支持多继承，故报错  
}*/
public class Son extends Father{}
```



## 11.老师和学生

![](https://github.com/Continuers/Java/blob/main/picture/97.png)

```java
package com.itrs6;
public class person { 
    private String name;   
    private int age;     
    //私有的   
    public person() { 
    }  
    public person(String name, int age) { 
        this.name = name;  
        this.age = age;
    }  
    
    public String getName() { 
        return name;   
    }   
    
    public void setName(String name) { 
        this.name = name;
    }  
    
    public int getAge() {   
        return age;   
    }  
    
    public void setAge(int age) {
        this.age = age;  
    }
}
```

```java
package com.itrs6;
public class Teacher extends person {   
    public Teacher(){}   
    public Teacher(String name,int age){  
        super(name, age); 
        //person中name,age 均为私有private  
    }                     
    //需定义无参和带参构造方法，否则报错 
    public void teach(){        System.out.println("用爱成就每一位学员");    }
}
```

```java
package com.itrs6;
public class Student extends person {   
    public Student(){}  
    public Student(String name,int age){  
        super(name, age);   
    }   
    public void study(){        System.out.println("越努力越幸运");    }
}
```

```java
package com.itrs6;
/*    测试类*/
public class personDemo { 
    public static void main(String[] args) {  
        Teacher t1 = new Teacher();    
        t1.setName("java");      
        t1.setAge(30);      
        System.out.println(t1.getName()+","+t1.getAge()); 
        
        t1.teach();     
        Teacher t2 = new Teacher("javaweb",33);   
        System.out.println(t2.getName()+","+t2.getAge()); 
        
        t2.teach();    
        Student s1 = new Student();   
        s1.setName("javaweb");  
        s1.setAge(40);     
        System.out.println(t1.getName()+","+t1.getAge());  
        
        s1.study();     
        Student s2 = new Student("springboot",20);     
        System.out.println(t2.getName()+","+t2.getAge()); 
        s2.study();    
    }
}
```



## 12.猫和狗

![](https://github.com/Continuers/Java/blob/main/picture/98.png)

![](https://github.com/Continuers/Java/blob/main/picture/99.png)

```java
package com.itrs7;
public class Animal {   
    private String name;   
    private int age;  
    public Animal() {    }  
    
    public Animal(String name, int age) {        this.name = name;        this.age = age;    } 
    
    public String getName() {        return name;    }  
    
    public void setName(String name) {        this.name = name;    }   
    
    public int getAge() {        return age;    } 
    
    public void setAge(int age) {        this.age = age;    }
}
```

```java
package com.itrs7;
public class Cat extends Animal {   
    public Cat() {    }  
    
    public Cat(String name, int age) {        super(name, age);    }
    
    public void catchMouse(){        System.out.println("猫抓老鼠");    }
}
```

```java
package com.itrs7;
public class Dog extends Animal {  
    public Dog() {    } 
    
    public Dog(String name, int age) {        super(name, age);    } 
    
    public void lookDoor(){        System.out.println("看门");    }
}
```

```java
package com.itrs7;
public class AnimalDemo { 
    public static void main(String[] args) {    
        Cat c1 = new Cat();    
        c1.setName("Tom");   
        c1.setAge(15);      
        System.out.println(c1.getName()+","+c1.getAge());   //Tom,15      
        c1.catchMouse();                                    //猫抓老鼠   
        
        Cat c2 = new Cat("Tom",10);   
        System.out.println(c2.getName()+","+c2.getAge());   //Tom,10     
        c2.catchMouse();                                    //猫抓老鼠   
        
        Dog d1 = new Dog();   
        d1.setName("Spike");     
        d1.setAge(20);      
        System.out.println(d1.getName()+","+d1.getAge());   //Spike,20   
        d1.lookDoor();                                      //看门     
        
        Dog d2 = new Dog("Tyke",5);     
        System.out.println(d2.getName()+","+d2.getAge());   //Tyke,5    
        d2.lookDoor();                                      //看门  
    }
}
```





# 22.修饰符

## 1.包

### 1.概述

#### 	==package==

#### 路径：D:\Java\IDEA\IntelliJ IDEA Educational Edition 2021.1.2\JavaSE_code\idea_test\src\com

![](https://github.com/Continuers/Java/blob/main/picture/100.png)

[黑马程序员全套Java教程_Java基础入门教程，零基础小白自学Java必备教程_哔哩哔哩_bilibili-P162](https://www.bilibili.com/video/BV18J411W7cE?p=162)



## 2.导包

### import

![](https://github.com/Continuers/Java/blob/main/picture/101.png)

```java
package com.itrs6;
/*	itrs6*/
public class Teacher extends person {   
    public Teacher(){} 
    public Teacher(String name,int age){    
        super(name, age);  
        //person中name,age 均为私有private   
    }                  
    //需定义无参和带参构造方法，否则报错   
    public void teach(){        System.out.println("用爱成就每一位学员");    }
}
```

```java
package com.itrs8;
/*	测试类*/
import com.itrs6.Teacher;

public class Demo {   
    public static void main(String[] args) {  
        /* 
        	com.itrs6.Teacher t = new com.itrs6.Teacher();  
             t.teach();          //用爱成就每一位学员  
        */       
        /*java.util.Scanner sc = new java.util.Scanner(System.in);*/   
        /* import com.itrs6.Teacher; */  
        Teacher t = new Teacher();     
        t.teach();        
        //用爱成就每一位学员    
    }
}
```

## 3.修饰符

### 1.修饰符的分类

权限修饰符

状态修饰符

### 2.权限修饰符

![](https://github.com/Continuers/Java/blob/main/picture/102.png)

```java
package com.itrs3;
/*    测试类*/
public class Demo {  
    public static void main(String[] args) { 
        Fu f = new Fu();     
        f.show2();    
        //默认     
        f.show3();  
        //protected  
        f.show4();    
        //public  
    }
}
```

```java
package com.itrs3;
/*    子类*/
public class Zi extends Fu {   
    public static void main(String[] args) {     
        Zi z = new Zi();      
        z.show2(); 
        //默认    
        z.show3();    
        //protected    
        z.show4();   
        //public 
    }
}
```

```java
package com.itrs3;
/*    父类*/
public class Fu { 
    private void show1(){   
        System.out.println("private");  
    }   
    void show2(){  
        System.out.println("默认");  
    }   
    protected void show3(){   
        System.out.println("protected");   
    }   
    public void show4(){  
        System.out.println("public");  
    }   
    public static void main(String[] args) {  
        Fu f = new Fu();   
        f.show1();   
        //private   
        f.show2();   
        //默认     
        f.show3(); 
        //protected  
        f.show4();   
        //public  
    }
}
```

```java
package com.itrs9;
/*	测试类	Fu*/
import com.itrs3.Fu;

public class Zi extends Fu { 
    public static void main(String[] args) { 
        Zi z = new Zi();  
        //位于不同包的子类,只能访问protected和public      
        z.show3();       //protected 
        z.show4();   //public  
    }
}
```

```java
package com.itrs9;
/*	测试类	Demo*/
import com.itrs3.Fu;

public class Demo {   
    public static void main(String[] args) {  
        Fu f = new Fu();   
        //Alt+Enter   
        f.show4();     
        //位于不同包的无关类  只能访问public 
    }
}
```

### 3.状态修饰符

1.  **final（最终态）**
2.  **static（静态）**



### 4. final

![](https://github.com/Continuers/Java/blob/main/picture/103.png)

```Java
package com.itrs9;
public class Demo { 
    public static void main(String[] args) { 
        Zi z = new Zi(); 
        z.method();  		 //java: 无法从最终com.itrs9.Fu进行继承   
        z.show();			
    } 
}
```

```java
package com.itrs9;
public class Zi extends Fu {  
    //报错，不能继承 
    public final int age = 20;   
    //final修饰变量：表明该变量是常量，不能再次被赋值 
    public void show(){
        //        age = 100;  
        System.out.println(age);  
    }  
    //    @Override
    //    public void method(){
    //        System.out.println("Zi method");
    //    }
}
```

```java
package com.itrs9;
/*public class Fu { 
    public final void method(){  
    //final修饰方法,表明该方法是最终方法，不能被重写   
    System.out.println("Fu method");  
}*/
public final class Fu {     
    //final修饰类：表明该类是最终类，不能被继承  
    public final void method(){  
        System.out.println("Fu method");  
    }
}
```



### 5. final 修饰局部变量

![](https://github.com/Continuers/Java/blob/main/picture/104.png)

```java
package com.itrs10;

public class Student {
    public int age = 20;
}
```

```java
package com.itrs10;

public class FinalDemo {
    public static void main(String[] args) {    
        //final修饰基本类型变量，值不能变    
        final int age = 20;
        //        age = 100;    报错   
        System.out.println(age);  
        //final修饰引用类型变量，内容可以变，地址不能变     
        final Student s = new Student();    //s是地址      
        s.age = 100;        //s.age是s的内容   
        System.out.println(s.age);   
    }
}
```



### 6. static

![](https://github.com/Continuers/Java/blob/main/picture/105.png)

```java
package com.itrs9;
public class Student {   
    public String name;   //姓名   
    public int age;      //年龄
    //    public String university;   		//大学
    public static String university;	//静态修饰    
    public void show(){     
        System.out.println(name + "," + age + "," + university);  
    }
}
```

```java
package com.itrs9;
/*测试类 */
public class StaticDemo {   
    public static void main(String[] args) {  
        Student.university = "GDPI";   
        Student s1 = new Student();      
        s1.name = "java";        
        s1.age = 19;
        //        s1.university = "GDPI";    
        s1.show();       
        Student s2 = new Student();      
        s2.name = "javase";      
        s2.age = 30;
        //        s2.university = "GDPI";   
        s2.show();    
    }
}
```



### 7. static 访问特点

![](https://github.com/Continuers/Java/blob/main/picture/106.png)

```java
package com.itrs8;
/*    static访问特点 */
public class Student {  
    //非静态成员变量   
    private String name = "java";  
    //静态成员变量  
    private static String university = "GDPI"; 
    //非静态成员方法
    public void show1(){}   
    //非静态成员方法  
    public void show2(){  
        System.out.println(name);    
        System.out.println(university);   
        show1();    
        show3();   
    }   
    //静态成员方法  
    public static void show3(){}  
    //静态成员方法 
    public static void show4(){
        //        System.out.println(name);   
        System.out.println(university);
        //        show1();    
        show3();   
    }
}
```



# 23. 多态



## 1. 概述

![](https://github.com/Continuers/Java/blob/main/picture/107.png)



## 2.多态中成员的访问特点

![](https://github.com/Continuers/Java/blob/main/picture/108.png)

```java
package com.itrs8;
public class Animal {   
    public int age = 40;  
    public void eat(){     
        System.out.println("动物吃东西");  
    }
}
```

```java
package com.itrs8;
public class Cat extends Animal {  
    public int age = 20;  
    public int weight = 10;
    @Override   
    public void eat() {   
        System.out.println("猫吃鱼");  
    }   
    public void playGame(){    
        System.out.println("猫捉老鼠");  
    }
}
```

```java
package com.itrs8;
public class AnimalDemo {  
    public static void main(String[] args) {  
        //有父类引用指向子类对象   
        Animal a = new Cat();   
        System.out.println(a.age);  //40
        //        System.out.println(a.weight);   
        a.eat();        //猫吃鱼
        //        a.playGame();   
    }
}
```



## 3.多态的好处和弊端

![](https://github.com/Continuers/Java/blob/main/picture/109.png)

```java
package com.itrs8;
public class Animal { 
    public void eat(){ 
        System.out.println("动物吃东西");  
    }
}
```

```java
package com.itrs8;
public class Dog extends Animal { 
    @Override  
    public void eat() {  
        System.out.println("狗吃骨头"); 
    }   
    public void lookDoor(){    
        System.out.println("狗看门"); 
    }
}
```

```java
package com.itrs8;
public class Cat extends Animal { 
    @Override 
    public void eat() {
        System.out.println("猫吃鱼"); 
    }
}
```

```java
package com.itrs8;
public class Pig extends Animal { 
    @Override    
    public void eat() {  
        System.out.println("猪拱白菜");
    }
}
```

```java
package com.itrs8;
/*    动物操作类 */
public class AnimalOperator {  
    /*public void useAnimal(Cat c){ 
    //Cat c = new Cat();  
    c.eat();    
    }   
    public void useAnimal(Dog d){  
    //Dog d = new Dog();   
    d.eat(); 
    }*/   
    public void useAnimal(Animal a){   
        //Animal a = new Cat(); 
        //Animal a = new Dog();  
        a.eat();
        //        a.lookDoor(); 
        //弊端：多态形式不能访问具体子类所特有的功能  
    }
}
```

```java
package com.itrs8;
/*    测试类 */
public class AnimalDemo {
    public static void main(String[] args) {   
        //创建动物操作类的对象，调用方法  
        AnimalOperator ao = new AnimalOperator();   
        Cat c = new Cat();    
        ao.useAnimal(c);     //猫吃鱼       
        Dog d = new Dog();   
        ao.useAnimal(d);    //狗吃骨头       
        Pig p = new Pig();  
        ao.useAnimal(p);	//猪拱白菜    
    }
}
```



## 4. 多态中的转型

```java
package com.itrs10;
public class Animal { 
    public void eat(){ 
        System.out.println("动物吃东西");  
    }
}
```

```java
package com.itrs10;
public class Cat extends Animal {   
    @Override 
    public void eat() { 
        System.out.println("猫吃鱼"); 
    }   
    public void playGame(){   
        System.out.println("猫捉老鼠");   
    }
}
```

```java
package com.itrs10;
/*       向上转型    从子到父	 父类引用指向子类对象
		向下转型 	从父到子	父类引用转为子类对象
*/
public class AnimalDemo {  
    public static void main(String[] args) { 
        //多态      
        Animal a = new Cat();  
        //向上转型    
        a.eat();
        //        a.playGame();  
        //编译看左边，Animal没有这个方法，故报错 
        /*//创建Cat类的对象    
        Cat c = new Cat();  
        c.eat();    
        c.playGame();*/  
        //向下转型，解决多态弊端    
        Cat c = (Cat) a;  
        //强转类型      
        c.eat();     
        c.playGame();  
    }
}
```



## 5.多态转型内存图解

🔗 https://www.bilibili.com/video/BV18J411W7cE?p=173

![](https://github.com/Continuers/Java/blob/main/picture/110.png)

```java
package com.itrs10;
public class Animal {   
    public void eat(){ 
        System.out.println("动物吃东西"); 
    }
}
```

```java
package com.itrs10;
public class Dog extends Animal {
    public void eat(){   
        System.out.println("狗吃骨头");  
    }
}
```

```java
package com.itrs10;
public class Cat extends Animal { 
    @Override 
    public void eat() { 
        System.out.println("猫吃鱼");   
    }  
    public void playGame(){ 
        System.out.println("猫捉老鼠");  
    }
}
```

```java
package com.itrs10;
/*    测试类 */
public class AnimalDemo { 
    public static void main(String[] args) { 
        //向上转型     
        Animal a = new Cat(); 
        //向上转型    
        a.eat();	
        //a.playGame();  
        //编译看左边，Animal没有这个方法，故报错    
        //向下转型       
        Cat c = (Cat) a;    
        c.eat();   
        c.playGame(); 
        //向上转型     
        a = new Dog();  
        a.eat();      
        //ClassCastException 类型转换异常
        Cat cc = (Cat) a;  
        //强转类型     
        cc.eat();      
        cc.playGame();  
    }
}
```



## 案例：猫和狗(多态)

![](https://github.com/Continuers/Java/blob/main/picture/111.png)

```java
package com.itrs;
public class Animal {  
    private String name;  
    private int age;   
    public Animal() {    } 
    public Animal(String name, int age) { 
        this.name = name;    
        this.age = age;  
    }  
    public String getName() {  
        return name;  
    }  
    public void setName(String name) {   
        this.name = name;  
    }  
    public int getAge() { 
        return age;  
    } 
    public void setAge(int age) {  
        this.age = age; 
    }    
    public void eat(){
        System.out.println("动物吃东西"); 
    }
}
```

```java
package com.itrs;
public class Cat extends Animal { 
    public Cat() {    } 
    public Cat(String name, int age) { 
        super(name, age);  
    } 
    @Override 
    public void eat() {    
        System.out.println("猫吃鱼"); 
    }
}
```

```java
package com.itrs;
public class Dog extends Animal {
    public Dog() {    }    
    public Dog(String name, int age) { 
        super(name, age);  
    }  
    @Override 
    public void eat() {   
        System.out.println("狗吃骨头");   
    }
}
```

```java
package com.itrs;

public class AnimalDemo {
    public static void main(String[] args) {
        //创建猫类对象进行测试
        Animal a = new Cat();
        a.setName("Tom");
        a.setAge(8);
        System.out.println(a.getName()+","+a.getAge());
        a.eat();

        a = new Cat("Tom",5);
        System.out.println(a.getName()+","+a.getAge());
        a.eat();
    }
}
```



# 24.抽象类



## 1.概述 abstract 抽象的

![](https://github.com/Continuers/Java/blob/main/picture/112.png)

```java
package com.itrs2;

public abstract class Animal {  //抽象类
    /*public void eat(){
        System.out.println("吃东西");
    }*/

    public abstract void eat(); //抽象方法
}
```



## 2.抽象类的特点 

![](https://github.com/Continuers/Java/blob/main/picture/113.png)

```java
package com.itrs2;
/*
    抽象类
 */
public abstract class Animal {  //抽象类
    //抽象方法
    public abstract void eat(); 

    public void sleep(){
        System.out.println("睡觉");
    }
}
```

```java
package com.itrs2;

public class Cat extends Animal { 
    @Override
    public void eat() { 
        System.out.println("猫吃鱼"); 
    }
}
```

```java
package com.itrs2;

public abstract class Dog extends Animal {
	
}
```

```java
package com.itrs2;
/*    测试类 */
public class AnimalDemo {
    public static void main(String[] args) { 
        Animal a = new Cat();     
        a.eat();    	//猫吃鱼
        a.sleep(); 		//睡觉
    }
}
```



## 3.抽象类的成员特点

![](https://github.com/Continuers/Java/blob/main/picture/114.png)

```java
package com.itrs3;

public abstract class Animal {
    private int age = 20;
    private final String city = "汕头";

    public Animal(){}

    public Animal(int age){
        this.age = age;
    }

    public void show(){
        age = 40;
        System.out.println(age);
//        city = "中山";
        System.out.println(city);
    }

    public abstract void eat();
}
```

```java
package com.itrs3;
public class Cat extends Animal {
    @Override
    public void eat() { 
        System.out.println("猫吃鱼");    
    }
}
```

```java
package com.itrs3;
public class AnimalDemo {
    public static void main(String[] args) {
        Animal a = new Cat(); 
        a.eat();      
        a.show();  
    }
}
```



## 案例：猫和狗

![](https://github.com/Continuers/Java/blob/main/picture/115.png)



```java
package com.itrs4;

public abstract class Animal {
    private String name;
    private int age;

    public Animal() {
    }

    public Animal(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public abstract void eat();
}
```

```java
package com.itrs4;
public class Cat extends Animal {  
    public Cat() {    }  
    
    public Cat(String name, int age) {   
        super(name, age);   
    }  
    @Override   
    public void eat() {  
        System.out.println("猫吃鱼");    
    }
}
```

```java
package com.itrs4;
public class Dog extends Animal { 
    public Dog() {    }   
    public Dog(String name, int age) { 
        super(name, age); 
    }   
    @Override 
    public void eat() {  
        System.out.println("狗吃骨头"); 
    }
}
```

```java
package com.itrs4;
/*    测试类 */
public class AnimalDemo {  
    public static void main(String[] args) {  
        //创建对象，按照多态的方式   
        Animal a = new Cat();    
        a.setName("Tom");     
        a.setAge(5);      
        System.out.println(a.getName()+","+a.getAge()); //Tom,5  
        a.eat();    //猫吃鱼   
        System.out.println("----------------------------------");    
        a = new Cat("Tom",6);   //Tom,6    
        System.out.println(a.getName()+","+a.getAge());  
        a.eat();        //猫吃鱼    
        //多态      
        a = new Dog();   
        a.eat();   //狗吃骨头   
    }
}
```



# 25. 接口



## 1. 接口概述

![](https://github.com/Continuers/Java/blob/main/picture/116.png)



## 2.接口的特点

![](https://github.com/Continuers/Java/blob/main/picture/117.png)

```java
package com.itrs11;

public class Cat implements Jumpping {  //类 实现 接口
    @Override
    public void jump() {
        System.out.println("猫可以跳高了");
    }
}
```

```java
package com.itrs11;
/*
    定义了一个接口
 */
public interface Jumpping {
    public abstract void jump();
}
```

```java
package com.itrs11;
public class JumppingDemo {  
    public static void main(String[] args) {
        //        Jumpping j = new Jumpping();  
        Jumpping j = new Cat();  
        j.jump();   
    }
}
```



## 3.接口的成员特点

![](https://github.com/Continuers/Java/blob/main/picture/118.png)

```java
package com.itrs11;
//public class InterImpI implements Inter {     等价于
public class InterImpI extends Object implements Inter{  
    public InterImpI(){     
        super();   
    }   
    @Override  
    public void method() {   
        System.out.println("method");  
    }   
    @Override
    public void show() {   
        System.out.println("show");  
    }
}
```

```java
package com.itrs11;

public interface Inter {
    public int num = 10;
    public final int num2 = 20;
//    public static final int num3 = 30;
    int num3 = 30;

//    public Inter(){}      接口里面不能有构造方法的

//    public void show(){}

    public abstract void method();      //接口里面的成员方法是抽象的
    void show();

}
```

```java
package com.itrs11;
public class InterfaceDemo {  
    public static void main(String[] args) {   
        Inter i= new InterImpI();    
        System.out.println(i.num);		//10    
        System.out.println(i.num2);		//20    
        System.out.println(Inter.num);	//10   
    }
}
```



## 案例：猫和狗

![](https://github.com/Continuers/Java/blob/main/picture/119.png)

```java
package com.itrs12;

public abstract class Animal {
    private String name;
    private int age;

    public Animal() {
    }

    public Animal(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
    public abstract void eat();
}
```

```java
package com.itrs12;

public class Cat extends Animal implements Jumpping {

    public Cat() {      //无参构造方法
    }

    public Cat(String name, int age) {
        super(name, age);       //带参构造方法
    }

    @Override
    public void eat() {
        System.out.println("猫吃鱼");
    }

    @Override
    public void jump() {
        System.out.println("猫可以跳高了");
    }
}
```

```java
package com.itrs12;

public class Dog extends Animal implements Jumpping {

    public Dog() {
    }

    public Dog(String name, int age) {
        super(name, age);
    }

    @Override
    public void eat() {
        System.out.println("狗吃肉");
    }

    @Override
    public void jump() {
        System.out.println("狗可以跳高了");
    }
}
```

```java
package com.itrs12;
/*
	接口
*/
public interface Jumpping {
    public abstract void jump();
}
```

```java
package com.itrs12;
/*
    测试类
 */
public class AnimalDemo {
    public static void main(String[] args) {
        Jumpping j = new Cat();
        j.jump();       //猫可以跳高了
        
        j = new Dog();
        j.jump();       //狗可以跳高了
        System.out.println("-----------------------------------");

        Animal a = new Cat();
        a.setName("Tom");
        a.setAge(5);
        System.out.println(a.getName()+","+a.getAge());     //Tom,5
        a.eat();        //猫吃鱼
//        a.jump();
        
        a = new Dog();
        a.setName("Spike");
        a.setAge(10);
        System.out.println(a.getName()+","+a.getAge());     //Spike,10
        a.eat();        //狗吃肉
        System.out.println("-----------------------------------");

        a = new Cat("Tom",6);
        System.out.println(a.getName()+","+a.getAge());     //Tom,6
        a.eat();        //猫吃鱼
        
        a = new Dog("Spike",9);
        System.out.println(a.getName()+","+a.getAge());     //Spike,9
        a.eat();        //狗吃肉
        System.out.println("-----------------------------------");

        Cat c = new Cat();
        c.setName("Tom");
        c.setAge(7);
        System.out.println(c.getName()+","+c.getAge());     //Tom,7
        c.eat();        //猫吃鱼
        c.jump();       //猫可以跳高了
        
        c = new Cat();
        c.setName("Spike");
        c.setAge(8);
        System.out.println(c.getName()+","+c.getAge());     //Spike,8
        c.eat();        //猫吃鱼
        c.jump();       //猫可以跳高了

    }
}
```



## 4.类和接口的关系

![](https://github.com/Continuers/Java/blob/main/picture/120.png)

```java
package com.itrs;

public interface Inter1 {
}
```

```java
package com.itrs;

public interface Inter2 {
}
```

```java
package com.itrs;

public interface Inter3 extends Inter1,Inter2{
}
```

```java
package com.itrs;

public class InterImpI extends Object implements Inter1,Inter2,Inter3 {

}
```



## 5.抽象类和接口的区别

![](https://github.com/Continuers/Java/blob/main/picture/121.png)

![](https://github.com/Continuers/Java/blob/main/picture/122.png)

![](https://github.com/Continuers/Java/blob/main/picture/123.png)



## 案例：运动员和教练

![](https://github.com/Continuers/Java/blob/main/picture/124.png)

![](https://github.com/Continuers/Java/blob/main/picture/125.png)

```java
package com.itrs13;
/*
    说英语的接口
 */
public interface SpeakEnglish {
    public abstract void speak();
}
```

```java
package com.itrs13;
/*
    抽象人类
 */
public abstract class Person {
    private String name;
    private int age;

    public Person() {
    }

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public abstract void eat();
}
```

```java
package com.itrs13;
/*
    抽象运动员类
 */
public abstract class Player extends Person {
    public Player() {
    }

    public Player(String name, int age) {
        super(name, age);
    }

    public abstract void study();
}
```

```java
package com.itrs13;
/*
    抽象教练类
 */
public abstract class Coach extends Person {
    public Coach() {
    }

    public Coach(String name, int age) {
        super(name, age);
    }

    public abstract void teach();
}
```

```java
package com.itrs13;
/*
    篮球运动员类
 */
public class BasketballPlayer extends Player{

    public BasketballPlayer() {
    }

    public BasketballPlayer(String name, int age) {
        super(name, age);
    }

    @Override
    public void study() {
        System.out.println("篮球运动员学习投篮");
    }

    @Override
    public void eat() {
        System.out.println("篮球运动员吃面条");
    }
}
```

```java
package com.itrs13;
/*
    篮球教练类
 */
public class BasketballCoach extends Coach{

    @Override
    public void teach() {
        System.out.println("篮球教练教投篮");
    }

    @Override
    public void eat() {
        System.out.println("篮球教练吃面条");
    }
}
```

```java
package com.itrs13;
/*
    乒乓球运动员类
 */
public class PingpongPlayer extends Player implements SpeakEnglish{

    public PingpongPlayer() {
    }

    public PingpongPlayer(String name, int age) {
        super(name, age);
    }

    @Override
    public void study() {
        System.out.println("乒乓球运动员学习发球");
    }

    @Override
    public void eat() {
        System.out.println("乒乓球运动员吃米饭");
    }

    @Override
    public void speak() {
        System.out.println("乒乓球运动员说英语");
    }
}
```

```java
package com.itrs13;
/*
    乒乓球教练类
 */
public class pingpongCoach extends Coach implements SpeakEnglish{

    public pingpongCoach() {
    }

    public pingpongCoach(String name, int age) {
        super(name, age);
    }

    @Override
    public void teach() {
        System.out.println("乒乓球教练教发球");
    }

    @Override
    public void eat() {
        System.out.println("乒乓球教练吃米饭");
    }

    @Override
    public void speak() {
        System.out.println("乒乓球教练说英语");
    }
}
```

```java
package com.itrs13;
/*
    测试类
 */
public class PersonDemo {
    public static void main(String[] args) {
        //创建对象
        PingpongPlayer ppp = new PingpongPlayer();
        ppp.setName("张继科");
        ppp.setAge(30);
        System.out.println(ppp.getName()+","+ppp.getAge());     //张继科,30
        ppp.eat();                                              //乒乓球运动员吃米饭
        ppp.study();                                            //乒乓球运动员学习发球
        ppp.speak();                                            //乒乓球运动员说英语
        System.out.println();

        BasketballPlayer bp = new BasketballPlayer();
        bp.setName("姚明");
        bp.setAge(35);
        System.out.println(bp.getName()+","+bp.getAge());       //姚明,35
        bp.eat();                                               //篮球运动员吃面条
        bp.study();                                             //篮球运动员学习投篮

    }
}
```



# 26. 形参和返回值



## 1.类名作为形参和返回值

![](https://github.com/Continuers/Java/blob/main/picture/126.png)

```java
package com.itrs;

public class Cat {
    public void eat(){
        System.out.println("猫吃鱼");
    }
}
```

```java
package com.itrs;

public class CatOperator {
    public void useCat(Cat c){  //Cat c = new Cat();
        c.eat();
    }

    public Cat getCat(){
        Cat c = new Cat();
        return c;
    }
}
```

```java
package com.itrs;

public class CatDemo {
    public static void main(String[] args) {
        CatOperator co = new CatOperator();
        Cat c = new Cat();
        co.useCat(c);			//猫吃鱼

        Cat c2 = co.getCat();
        c2.eat();				//猫吃鱼
    }
}
```

## 2.抽象类名作为形参和返回值

![](https://github.com/Continuers/Java/blob/main/picture/127.png)

```java
package com.itrs1;
public abstract class Animal {
    public abstract void eat();
}
```

```java
package com.itrs1;
public class AnimalOperator {
    public void useAnimal(Animal a){
        a.eat();
    }

    public Animal getAnimal(){
        Animal a = new Cat();
        return a;
    }
}
```

```java
package com.itrs1;
public class Cat extends Animal{
    @Override
    public void eat() {
        System.out.println("猫吃鱼");
    }
}
```

```java
package com.itrs1;
/*
    测试类
 */
public class AnimalDemo {
    public static void main(String[] args) {
        //创建操作类对象，并调用方法
        AnimalOperator ao = new AnimalOperator();
        Animal a = new Cat();
        ao.useAnimal(a);

        Animal a2 = ao.getAnimal(); //new Cat()
        a2.eat();
    }
}
```



## 3.接口名作为形参喝返回值

![](https://github.com/Continuers/Java/blob/main/picture/128.png)

```java
package com.itrs2;
/*接口*/
public interface Jumpping {

    void jump();
}
```

```java
package com.itrs2;

public class JumppingOperator {

    public void useJumpping(Jumpping j){
        j.jump();
    }

    public Jumpping getJumpping(){
        Jumpping j = new Cat();
        return j;
    }
}
```

```java
package com.itrs2;

public class Cat implements Jumpping {
    @Override
    public void jump() {
        System.out.println("猫跳高");
    }
}
```

```java
package com.itrs2;
/*
*   测试类
*/
public class JumppingDemo {
    public static void main(String[] args) {
        JumppingOperator jo = new JumppingOperator();
        Jumpping j = new Cat();
        jo.useJumpping(j);      //猫跳高

        Jumpping j2 = jo.getJumpping();
        j2.jump();              //猫跳高
    }
}
```



# 27.内部类

## 1.内部类概述



![](https://github.com/Continuers/Java/blob/main/picture/129.png)



```java
package com.itrs2;

public class Outer {

    private int num = 10;   //私有

    /*  内部类   */
    public class Inner{
        public void show(){
            System.out.println(num);
        }
    }

    public void method(){
//        show();
        Inner i = new Inner();
        i.show();
    }
}
```



## 2.成员内部类



![](https://github.com/Continuers/Java/blob/main/picture/130.png)



```java
package com.itrs3;

public class Outer {

    private int num = 10;

    /*public class Inner{
        public void show(){
            System.out.println(num);
        }
    }*/

    /*私有化*/
    private class Inner{
        public void show(){
            System.out.println(num);
        }
    }

    public void method(){
        Inner i = new Inner();
        i.show();
    }

}
```

```java
package com.itrs3;

public class InnerDemo {

    public static void main(String[] args) {

        /*//public class Inner{}
        Outer.Inner oi = new Outer().new Inner();
        oi.show();*/

        /*间接调用Inner方法*/
        Outer o = new Outer();
        o.method();		//10
    }
}
```



## 3.局部内部类



![](https://github.com/Continuers/Java/blob/main/picture/131.png)



```java
package com.itrs4;

public class Outer {

    private int num = 20;

    public void method(){
        int num2 = 19;
        class  Inner{
            public void show(){
                System.out.println(num);
                System.out.println(num2);
            }
        }

        Inner i = new Inner();
        i.show();
    }
}
```

```java
package com.itrs4;
/*
    测试类
*/
public class OuterDemo {
    public static void main(String[] args) {
        Outer o = new Outer();
        o.method();     //20
                        //19
    }
}
```



## 4.匿名内部类



![](https://github.com/Continuers/Java/blob/main/picture/132.png)



```java
package com.itrs5;
/*  接口    */
public interface Inter {
    void show();
}
```

```java
package com.itrs5;

public class Outer {

    public void method(){
        /*      //对象
        new Inter(){
            @Override
            public void show() {
                System.out.println("匿名内部类");
            }
        };
        */

        /*对象调用show方法*/
        /*
        new Inter(){
            @Override
            public void show() {
                System.out.println("匿名内部类");
            }
        }.show();

        new Inter(){
            @Override
            public void show() {
                System.out.println("匿名内部类");
            }
        }.show();
        */

        /*	多次调用	*/
        Inter i = new Inter(){
            @Override
            public void show() {
                System.out.println("匿名内部类");
            }
        };

        i.show();
        i.show();
        i.show();

        /*for (int j=0;j<10;j++){
            i.show();
        }*/
    }
}
```

```java
package com.itrs5;
/*  测试类  */
public class OuterDemo {
    public static void main(String[] args) {
        Outer o = new Outer();
        o.method();     //匿名内部类     匿名内部类      匿名内部类
    }
}
```



## 5.匿名内部类在开发中的使用



![](https://github.com/Continuers/Java/blob/main/picture/133.png)



```java
package com.itrs5;

public class Cat implements Jumping{
    @Override
    public void jump() {
        System.out.println("猫跳高");
    }
}
```

```java
package com.itrs5;

public class Dog implements Jumping{
    @Override
    public void jump() {
        System.out.println("狗可以跳高了");
    }
}
```

```java
package com.itrs5;
/*
    跳高接口
 */
public interface Jumping {
    void jump();
}
```

```java
package com.itrs5;
/*
    接口操作类，里面有一个方法，方法的参数是接口名
 */
public class JumpingOperator {
    public void method(Jumping j){
        j.jump();
    }
}
```

```java
package com.itrs5;
/*
    测试类
 */
public class JumpingDemo {
    public static void main(String[] args) {
        JumpingOperator jo = new JumpingOperator();
        Jumping j = new Cat();
        jo.method(j);				//猫跳高

        Jumping j2 = new Dog();
        jo.method(j2);				//狗可以跳高了
        
        System.out.println("-----------");

        jo.method(new Jumping() {
            @Override
            public void jump() {
                System.out.println("猫飞了");
            }
        });

        jo.method(new Jumping() {
            @Override
            public void jump() {
                System.out.println("狗也飞了");
            }
        });
    }
}
```



# 28.常用API

![](https://github.com/Continuers/Java/blob/main/picture/134.png)

## 1.Math



### 1.Math类概述

![](https://github.com/Continuers/Java/blob/main/picture/135.png)

### 2.Math类的常用方法

![](https://github.com/Continuers/Java/blob/main/picture/136.png)



```java
package com.itrs3;

public class MathDemo {
    public static void main(String[] args) {
        //public static int abs(int a): 返回参数的绝对值
        System.out.println(Math.abs(88));   //88
        System.out.println(Math.abs(-88));  //88
        System.out.println("----------");

        //public static double ceil( double a): 返回大于或等于参数的最小 double值,等于一个整数
        System.out.println(Math.ceil(12.34));   //13.0
        System.out.println(Math.ceil(13.14));   //14.0
        System.out.println("----------");

        //public static double floor( double a): 返回小于或等于参数的最大 double值,等于一个整数
        System.out.println(Math.floor(12.34));  //12.0
        System.out.println(Math.floor(13.14));  //13.0
        System.out.println("-----------");

        //public static int round( float a):按照四舍五入返回最接近参数的int
        System.out.println(Math.round(12.34F)); //12
        System.out.println(Math.round(13.14F)); //13
        System.out.println("-----------");

        //public static int max( int a, int b):返回两个int值中的较大值
        System.out.println(Math.max(66,88));    //88
        System.out.println("----------");

        //public static int min( int a,  int b):返回两个int值中的较小值(自学)
        System.out.println(Math.min(66,88));    //66
        System.out.println("----------");

        //public static double pow( double a, double b):返回 a 的 b 次幂的值
        System.out.println(Math.pow(2.0,3.0));  //8.0
        System.out.println("----------");

        //public static double random(): 返回值为 double的正值,[0.0,1.0)   注: 取不到 1.0
//        System.out.println(Math.random());    //随机生成0到1的小数  如：0.89383565140668
        System.out.println((int)(Math.random()*100));   //扩大100倍并强转为int类型
        System.out.println((int)(Math.random()*100)+1); //  {可取到100}

    }
}
```

## 2.System



### 1.System类的概述



![](https://github.com/Continuers/Java/blob/main/picture/138.png)

### 2.System类的常用方法



![](https://github.com/Continuers/Java/blob/main/picture/137.png)



```java
package com.itrs4;
/*
    System类的常用方法
 */
public class SystemDemo {
    public static void main(String[] args) {
        /*
        System.out.println("start");
        *//* public static void exit(int status):终止当前运行的 Java 虚拟机，非零表示异常终止 *//*
        System.exit(0);
        System.out.println("end");
         */

        /* public static long currentTimeMillis(): 返回当前时间(以毫秒为单位) */
//        System.out.println(System.currentTimeMillis());

//        System.out.println(System.currentTimeMillis()*1.0/1000/60/60/24/365+"年");

        /* 输出运行时间(以毫秒为单位) */
        long start = System.currentTimeMillis();
        for (int i = 0; i < 10000; i++) {
            System.out.println(i);
        }
        long end = System.currentTimeMillis();
        System.out.println("共耗时：" + (end - start) + "毫秒");


    }
}
```



## 3. Object



### 1.Object 类的概述

![](https://github.com/Continuers/Java/blob/main/picture/139.png)

### 2.Object类的常用方法

![](https://github.com/Continuers/Java/blob/main/picture/140.png)

#### 1.Object类中的toString()方法

```java
package com.itrs4;

public class Student {
    private String name;
    private int age;

    public Student() {
    }

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    /* ALT + Insert = toString() */
    @Override
    public String toString() {
        return "Student{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }
}
```

```java
package com.itrs4;
/*
    Object 是类层次结构的根，每个类都可以将 Object 作为超类。所有类都直接或间接的继承自该类

    看方法的源码，选中方法，按下 Ctrl+B   或者选中方法右键 GoTo GoTo

    建议所有子类重写此方法
    如何重写呢？ 自动生成即可   ALT + Insert = toString()
 */
public class ObjectDemo {
    public static void main(String[] args) {
        Student s = new Student();
        s.setName("java");
        s.setAge(20);
        System.out.println(s);  //com.itrs4.Student@49e4cb85
        System.out.println(s.toString());   //com.itrs4.Student@49e4cb85
        /* 重写后为：Student{name='java', age=20} */

        //	源码
        /*
        public void println(Object x) {
            String s = String.valueOf(x);
            synchronized (this) {
                print(s);
                newLine();
            }
        }

        public static String valueOf(Object obj) {  //obj = x;
            return (obj == null) ? "null" : obj.toString();
        }

        public String toString() {
            return getClass().getName() + "@" + Integer.toHexString(hashCode());
        }
         */

    }
}
```

#### 2.Object类中的equals()方法

```java
package com.itrs3;

public class Student {
    private String name;
    private int age;

    public Student() {
    }

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    /*  equals重写方法
     Alt + Insert -- equals() and hashCode()
     Template:IntelliJ Default
     Next -- Next -- Next -- Finish
     删除 hashCode()重写模板
     */

    @Override
    public boolean equals(Object o) {
        /*
            this ---- s1
            o    ---- s2
         */
        //比较地址是否相同，如果相同，直接返回true
        if (this == o) return true;

        //判断参数是否为null || 判断俩个对象是否来自同一个类
        if (o == null || getClass() != o.getClass()) return false;

        //向下转型
        Student student = (Student) o;  //student = s2;

        //比较年龄是否相同
        if (age != student.age) return false;

        //比较姓名内容是否相同
        return name != null ? name.equals(student.name) : student.name == null;
    }
}
```

```java
package com.itrs3;
/*
    测试类
    public boolean equals (Object obj): 指示一些其他对象是否等于此
 */
public class ObjectDemo {
    public static void main(String[] args) {
        Student s1 = new Student();
        s1.setName("java");
        s1.setAge(20);

        Student s2 = new Student();
        s2.setName("java");
        s2.setAge(20);

        //需求： 比较俩个对象的内容是否相同
//        System.out.println(s1 == s2);   		//false  俩个都是地址值
//        System.out.println(s1.equals(s2));  	//false
        /*
        public boolean equals(Object obj) {
            //this ---- s1
            //obj  ---- s2
            return (this == obj);
        }
         */

        /* 重写equals方法后 */
        System.out.println(s1.equals(s2));     //true

    }
}
```



## 4.Arrays

### 1.冒泡排序

![](https://github.com/Continuers/Java/blob/main/picture/141.png)

```java
package com.itrs6;

public class ArrayDemo {
    public static void main(String[] args) {
        //定义一个数组
        int[] arr = {24, 69, 15, 95, 100, 80, 57, 13};
        System.out.println("排序前：" + arrayToString(arr));

        for (int j = 0; j < arr.length - 1; j++) {
            for (int i = 0; i < arr.length - 1; i++) {
                if (arr[i] > arr[i + 1]) {
                    int temp = arr[i];
                    arr[i] = arr[i + 1];
                    arr[i + 1] = temp;
                }
            }
        }
        System.out.println("排序后：" + arrayToString(arr));
    }

    //把数组中的元素按照指定的规则组成一个字符串：[元素1，元素2]
    public static String arrayToString(int[] arr) {
        StringBuilder sb = new StringBuilder();
        sb.append("[");
        for (int i = 0; i < arr.length; i++) {
            if (i == arr.length - 1) {
                sb.append(arr[i]);
            } else {
                sb.append(arr[i]).append(",");
            }
        }
        sb.append("]");
        String s = sb.toString();
        return s;
    }
}
```

### 2.Arrays类的概述和常用方法

![](https://github.com/Continuers/Java/blob/main/picture/142.png)

```java
package com.itrs6;

import java.util.Arrays;
/*
    Arrays 类包含用于操作数组的各种方法

    public static String toString (int[] a): 	返回指定数组的内容的字符串表示形式
    public static void sort (int[] a): 			按照数字顺序排列指定的数组
 */
public class ArraysDemo {
    public static void main(String[] args) {
        //定义一个数组
        int[] arr = {24,69,87,95,48,66,88,99,19};

        System.out.println("排序前："+ Arrays.toString(arr));
        //排序前：[24, 69, 87, 95, 48, 66, 88, 99, 19]
        
        Arrays.sort(arr);

        System.out.println("排序后："+ Arrays.toString(arr));
        //排序后：[19, 24, 48, 66, 69, 87, 88, 95, 99]
    }
}

```



## 5.基本类型包装类



### 1.基本类型包装类概述

![](https://github.com/Continuers/Java/blob/main/picture/143.png)

```java
package com.itrs6;
/*
	基本类型包装类
*/
public class IntegerDemo {
    public static void main(String[] args) {
        //需求 ： 判断一个数据是否在 int 范围内？
        //public static final int MIN_VALUE
        System.out.println(Integer.MIN_VALUE);
        //public static final int MAX_VALUE
        System.out.println(Integer.MAX_VALUE);

    }
}
```

### 2.Integer 类的概述和使用

![](https://github.com/Continuers/Java/blob/main/picture/144.png)

```java
package com.itrs7;

public class IntegerDemo {
    public static void main(String[] args) {
        /*
        //  构造方法：      （已过时）

        //public Integer(int value): 根据 int 值创建 Integer 对象(过时)
        Integer i1 = new Integer(100);
        System.out.println(i1);

        //public Integer(String s): 根据 String 值创建 Integer 对象(过时)
        Integer i2 = new Integer(100);
//        Integer i2 = new Integer("abc");    //NumberFormatException
        System.out.println(i2);
        */

        //静态方法获取对象：  （推荐）

        //public static Integer valueOf (int i): 返回表示指定的 int 值的 Integer 实例
        Integer i1 = Integer.valueOf(100);
        System.out.println(i1);

        //public static Integer valueOf (String s): 返回一个保存指定值的 Integer 对象 String
        Integer i2 = Integer.valueOf("100");
        System.out.println(i2);

    }
}
```



### 3. int 和 String 的相互转换

![](https://github.com/Continuers/Java/blob/main/picture/145.png)

```java
package com.itrs8;

public class IntegerDemo {
    public static void main(String[] args) {
        // int -----> String
        int number = 100;
        //方式1
        String s1 = ""+number;
        System.out.println(s1);
        
        //方式2
        //public static String valueOf (int i)
        String s2 = String.valueOf(number);
        System.out.println(s2);
        System.out.println();

        //String ------> int
        String s = "100";
        //方式1
        //String --- Integer --- int
        Integer i = Integer.valueOf(s);
        //public int intValue()
        int x = i.intValue();
        System.out.println(x);

        //方式2
        //public static int parseInt (String s)
        int y = Integer.parseInt(s);
        System.out.println(y);
    }
}
```



### 案例

🔗 https://www.bilibili.com/video/BV18J411W7cE?p=204

![](https://github.com/Continuers/Java/blob/main/picture/146.png)

```java
package com.itrs8;

import java.util.Arrays;

public class IntegerTest {
    public static void main(String[] args) {
        //定义一个字符串
        String s = "91 28 46 88 99 66";

        //把字符串中的数字数据存储到一个 int 类型的数组中
        String[] strArray = s.split(" ");
//        for (int i = 0;i<strArray.length;i++){
//            System.out.println(strArray[i]);
//        }

        //定义一个 int 数组，把 String[] 数组中的每一个元素存储到 int 数组中
        int[] arr = new int[strArray.length];
        for (int i = 0;i<arr.length;i++){
            arr[i] = Integer.parseInt(strArray[i]);
        }
//        for (int i = 0;i<arr.length;i++){
//            System.out.println(arr[i]);
//        }

        //对 int 数组进行排序
        Arrays.sort(arr);

        //把排序后的 int 数组中的元素进行拼接得到一个字符串，这里拼接采用 StringBuilder 来实现
        StringBuilder sb = new StringBuilder();
        for (int i=0;i<arr.length;i++){
            if (i == arr.length-1){
                sb.append(arr[i]);
            }else {
                sb.append(arr[i]).append(" ");
            }
        }
        String result = sb.toString();

        //输出结果
        System.out.println("result:"+result);
        //result:28 46 66 88 91 99
    }
}
```

 

### 4.自动装箱和拆箱



![](https://github.com/Continuers/Java/blob/main/picture/147.png)

==开发中一定要做判断==

```java
package com.itrs9;

public class IntegerDemo {
    public static void main(String[] args) {
        //装箱，把基本数据类型转换为对应的包装类类型
        Integer i = Integer.valueOf(100);   //装箱
        Integer ii = 100;           //自动装箱

        //拆箱，把包装类类型转换为对应的基本数据类型
//        ii = ii.intValue() + 200;     //拆箱
        ii += 200;          //自动拆箱,自动装箱
        System.out.println(ii);

        Integer iii = null;
        if (iii!=null){
            iii += 300;
        }
    }
}
```



## 6.日期类



### 1.Date 类概述和构造方法

![](https://github.com/Continuers/Java/blob/main/picture/148.png)

```java
package com.itrs9;

import java.util.Date;

public class DateDemo {
    public static void main(String[] args) {
        //public Date(): 分配一个 Date 对象，并初始化，以便它代表它被分配的时间，精确到毫秒
        Date d1 = new Date();
        System.out.println(d1);     //Sun Aug 22 21:59:57 CST 2021

        //public Date(long date): 分配一个 Date 对象，并将其初始化为表示从标准基准时间起指定的毫秒数
        long date = 1000*60*60;
        Date d2 = new Date(date);
        System.out.println(d2);     //Thu Jan 01 09:00:00 CST 1970
    }
}
```



### 2.Date 类的常用方法

![](https://github.com/Continuers/Java/blob/main/picture/149.png)

```java
package com.itrs9;

import java.util.Date;

public class DateDemo2 {
    public static void main(String[] args) {
        //创建日期对象
        Date d = new Date();

        //public long getTime(): 获取的是日期对象从1970年1月1日 00:00:00到现在的毫秒值
//        System.out.println(d.getTime());
//        System.out.println(d.getTime()*1.0/1000/60/60/24/365+"年");  

        //public void setTime(long time): 设置时间，给的是毫秒值
        long time = System.currentTimeMillis();
        d.setTime(time);
        System.out.println(d);      //Sun Aug 22 22:14:36 CST 2021
    }
}
```



### 3.SimpleDateFormat 类概述

![](https://github.com/Continuers/Java/blob/main/picture/150.png)



### 4.SimpleDateFormat 的构造方法

![](https://github.com/Continuers/Java/blob/main/picture/151.png)



### 5.SimpleDateFormat 格式化和解析日期

![](https://github.com/Continuers/Java/blob/main/picture/152.png)

```java
package com.itrs9;

import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;

/*
    构造方法:
        public Simpledateformat():构造一个 Simpledate Format,使用默认模式和日期格式
        public Simpledate Format( String pattern):构造一个 Simpledateformat使用给定的模式和默认的日期格式

    格式化: 从Date到 String
        public final string format( Date date):将日期格式化成日期/时间字符串

    解析: 从 String到
        public Date parse (String source):从给定字符串的开始解析文本以生成日期
 */

public class SimpleDateFormatDemo {
    public static void main(String[] args) throws ParseException {
        //格式化:从 Date 到 string
        Date d = new Date();
//        SimpleDateFormat sdf = new SimpleDateFormat();
        SimpleDateFormat sdf = new SimpleDateFormat("yyyy年MM月dd日 HH:mm:ss");
        String s = sdf.format(d);
        System.out.println(s);      //2021年08月22日 22:32:43
        System.out.println();

        //从 String 到 Date
        String ss = "2021-08-22 22:32:43";
        //ParseException
        SimpleDateFormat sdf2 = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");
        Date dd = sdf2.parse(ss);
        System.out.println(dd);     //Sun Aug 22 22:32:43 CST 2021
    }
}
```



### 案例：日期工具类



![](https://github.com/Continuers/Java/blob/main/picture/153.png)



```java
package com.itrs8;

import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;

/*
    工具类

    构造方法私有
    成员方法静态
 */
public class DateUtils {
    private DateUtils() {}

    /*
        把日期转为指定格式的字符串
        返回值类型: String
        参数: Date date, String format
    */

    public static String dateToString(Date date, String format){
        SimpleDateFormat sdf = new SimpleDateFormat(format);
        String s = sdf.format(date);
        return s;
    }

    /*
        把字符串解析为指定格式的日期
        返回值类型:Date
        参数; String s, String format
     */
    public static Date stringToDate(String s,String format) throws ParseException {
        SimpleDateFormat sdf = new SimpleDateFormat(format);
        Date d = sdf.parse(s);
        return d;
    }


}
```

```java
package com.itrs8;

import java.text.ParseException;
import java.util.Date;

public class DateDemo {
    public static void main(String[] args) throws ParseException {
        //创建日期对象
        Date d = new Date();

        String s1 = DateUtils.dateToString(d, "yyyy年MM月dd日 HH:mm:ss");
        System.out.println(s1);     //2021年08月22日 23:02:44

        String s2 = DateUtils.dateToString(d, "yyyy年MM月dd日");
        System.out.println(s2);     //2021年08月22日

        String s3 = DateUtils.dateToString(d, "HH:mm:ss");;
        System.out.println(s3);     //23:02:44
        System.out.println();

        String s = "2021-08-22 23:00:12";
        Date dd = DateUtils.stringToDate(s, "yyyy-MM-dd HH:mm:ss");
        System.out.println(dd);     //Sun Aug 22 23:00:12 CST 2021

    }
}
```



### 6.Calendar 类概述

![](https://github.com/Continuers/Java/blob/main/picture/154.png)

```Java
package com.itrs7;

import java.util.Calendar;

/*
    Calendar为某一时刻和一组日历字段之间的转换提供了一些方法,并为操作日历字段提供了一些方法

    Calendar提供了一个类方法 getinstance 用于获取 Calendar对象,其日历字段已使用当前日期和时间初始化
        Calendar rightnow = Calendar. getinstanceo:
 */
public class CalendarDemo {
    public static void main(String[] args) {
        //获取对象
        Calendar c = Calendar.getInstance();    //多态的形式
//        System.out.println(c);

        //public int get (int field)
        int year = c.get(Calendar.YEAR);
        int month = c.get(Calendar.MONDAY) + 1;
        int date = c.get(Calendar.DATE);
        System.out.println(year+"年"+month+"月"+date+"日");        //2021年8月23日
    }
}
```



### 7.Calendar 的常用方法

![](https://github.com/Continuers/Java/blob/main/picture/155.png)

```java
package com.itrs8;

import java.util.Calendar;

/*
    public abstract void add( int field, int amount):根据日历的规则,将指定的时间量添加或减去绐定的日历字段
    public final void set( int year, int month, int date):设置当前日历的年月日
*/
public class CalendarDemo {
    public static void main(String[] args) {
        //获取日历类对象
        Calendar c = Calendar.getInstance();

        //public int get (int field)：返回给定日历字段的值
//        int year = c.get(Calendar.YEAR);
//        int month = c.get(Calendar.MONDAY) + 1;
//        int date = c.get(Calendar.DATE);
//        System.out.println(year+"年"+month+"月"+date+"日");        //2021年8月23日

        //public abstract void add( int field, int amount):根据日历的规则,将指定的时间量添加或减去绐定的日历字段
        //需求1： 3年前的今天
//        c.add(Calendar.YEAR,-3);
        
//        int year = c.get(Calendar.YEAR);
//        int month = c.get(Calendar.MONDAY) + 1;
//        int date = c.get(Calendar.DATE);
//        System.out.println(year+"年"+month+"月"+date+"日");        //2018年8月23日

        //需求2： 10年后的5天前
//        c.add(Calendar.YEAR,10);
//        c.add(Calendar.DATE,-5);
        
//        int year = c.get(Calendar.YEAR);
//        int month = c.get(Calendar.MONDAY) + 1;
//        int date = c.get(Calendar.DATE);
//        System.out.println(year+"年"+month+"月"+date+"日");        //2031年8月18日

        //public final void set( int year, int month, int date):设置当前日历的年月日
        c.set(2048,10,1);
        int year = c.get(Calendar.YEAR);
        int month = c.get(Calendar.MONDAY) + 1;
        int date = c.get(Calendar.DATE);
        System.out.println(year+"年"+month+"月"+date+"日");        //2048年11月1日
    }
}
```



### 案例：二月天

![](https://github.com/Continuers/Java/blob/main/picture/156.png)

```java
package com.itrs9;

import java.util.Calendar;
import java.util.Scanner;

/*
    需求:
        获取任意一年的二月有多少天
    思路:
        1:键盘录入任意的年份
        2:设置日历对象的年、月、日
            年:来自于键盘录入
            月:设置为3月,月份是从0开始的,所以设置的值是2
            日:设置为1日
        3:3月1日往前推一天,就是2月的最后一天
        4:获取这一天输出即可
 */
public class CalendarTest {
    public static void main(String[] args) {
        //键盘录入任意的年份
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入年份：");
        int year = sc.nextInt();

        //设置日历对象的年、月、日
        Calendar c = Calendar.getInstance();
        c.set(year,2,1);

        //3月1日往前推一天,就是2月的最后一天
        c.add(Calendar.DATE,-1);

        //获取这一天输出即可
        int date = c.get(Calendar.DATE);

        System.out.println(year+"年份的2月有"+date+"天");
    }
}
```



# 29. 异常



## 1.异常概述

![](https://github.com/Continuers/Java/blob/main/picture/157.png)



## 2.JVM 的默认处理方案

![](https://github.com/Continuers/Java/blob/main/picture/158.png)

```java
package com.itrs10;
/*
    JVM 的默认处理方案
 */
public class ExceptionDemo {
    public static void main(String[] args) {
        System.out.println("开始");
        method();
        System.out.println("结束");
    }

    public static void method(){
        int[] arr = {1,2,3};
        System.out.println(arr[3]);
    }
}
/*
    开始
    Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: Index 3 out of bounds for length 3
        at com.itrs10.ExceptionDemo.method(ExceptionDemo.java:14)
        at com.itrs10.ExceptionDemo.main(ExceptionDemo.java:8)
 */
```



## 3.异常处理



## 4.异常处理之 try...catch...

![](https://github.com/Continuers/Java/blob/main/picture/159.png)

```java
package com.itrs10;

public class ExceptionDemo {
    public static void main(String[] args) {
        System.out.println("开始");
        method();
        System.out.println("结束");
    }

    public static void method(){
        try {
            int[] arr = {1, 2, 3};
            System.out.println(arr[3]);
        } catch (ArrayIndexOutOfBoundsException e){
            e.printStackTrace();
        }
    }
}
/*
    开始
    结束
    java.lang.ArrayIndexOutOfBoundsException: Index 3 out of bounds for length 3
        at com.itrs10.ExceptionDemo.method(ExceptionDemo.java:13)
        at com.itrs10.ExceptionDemo.main(ExceptionDemo.java:6)
 */
```



## 5.Throwable 的成员方法

![](https://github.com/Continuers/Java/blob/main/picture/160.png)

```java
package com.itrs10;

public class ExceptionDemo {
    public static void main(String[] args) {
        System.out.println("开始");
        method();
        System.out.println("结束");
    }

    public static void method(){
        try {
            int[] arr = {1, 2, 3};
            System.out.println(arr[3]); //new ArrayIndexOutOfBoundsException("xxx");
        } catch (ArrayIndexOutOfBoundsException e){
//            e.printStackTrace();

            /*public String getmessage():返回此 throwable的详细消息字符串*/
//            System.out.println(e.getMessage());
            //Index 3 out of bounds for length 3

            /*public String tostring():返回此可抛出的简短描述*/
//            System.out.println(e.toString());
            //java.lang.ArrayIndexOutOfBoundsException: Index 3 out of bounds for length 3

            /*public void printstacktrace():把异常的错误信息输出在控制台*/
            e.printStackTrace();
        }
    }
}

/*
    public class Throwable {
            private String detailMessage;

            public Throwable(String message){
                detailMessage = message;
            }

            public String getMessage() {
                return detailMessage;
            }
    }
 */
```



## 6.编译时异常和运行时异常的区别

![](https://github.com/Continuers/Java/blob/main/picture/161.png)

```java
package com.itrs10;

import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;

/*
    Java中的异常被分为两大类:
    编译时异常和运行时异常,也被称为受检异常和非受检异常
    所有的 RuntimeException类及其子类的实例被称为运行时异常,其他的异常都是编译时异常

    编译时异常:必须显示处理,否则程序就会发生错误,无法通过编译
    运行时异常:无需显示处理,也可以和编译时异常一样处理
 */
public class ExceptionDemo2 {
    public static void main(String[] args) {
//        method();
        method2();
    }

    //编译时异常
    public static void method2(){
        try {
            String s = "2048-08-08";
            SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd");
            Date d = sdf.parse(s);
            System.out.println(d);
        } catch (ParseException e){
            e.printStackTrace();
        }
    }


    //运行时异常
    public static void method(){
        try {
            int[] arr = {1, 2, 3};
            System.out.println(arr[3]);     //ArrayIndexOutOfBoundsException
        } catch (ArrayIndexOutOfBoundsException e){
            e.printStackTrace();
        }

    }
}
```



## 7.异常处理之 throws

![](https://github.com/Continuers/Java/blob/main/picture/162.png)

```java
package com.itrs10;

import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;

/*
    throws异常类名;
    这个格式是跟在方法的括号后面的
 */
public class ExceptionDemo3 {
    public static void main(String[] args) {
        System.out.println("开始");
//        method();
        try {
            method2();      //Alt+Enter Surround with try/catch
        } catch (ParseException e) {
            e.printStackTrace();
        }
        System.out.println("结束");
    }

    //编译时异常
    public static void method2() throws ParseException {    //Alt+Enter Add exception to method signature
            String s = "2048-08-08";
            SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd");
            Date d = sdf.parse(s);
            System.out.println(d);
    }


    //运行时异常
    public static void method() throws ArrayIndexOutOfBoundsException{
            int[] arr = {1, 2, 3};
            System.out.println(arr[3]);
    }
}
```



## 8.自定义异常

![](https://github.com/Continuers/Java/blob/main/picture/163.png)

```java
package com.itrs11;

public class ScoreException extends Exception{

    public ScoreException(){}

    public ScoreException(String message){
        super(message);
    }
}
```

```java
package com.itrs11;

public class Teacher {
    public void checkScore(int score) throws ScoreException{
        if (score<0||score>100){
//            throw new ScoreException();
            throw new ScoreException("输入分数有误");
        } else {
            System.out.println("分数正常");
        }
    }
}
```

```java
package com.itrs11;

import java.util.Scanner;

public class TeacherTest {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入分数");
        int score = sc.nextInt();

        Teacher t = new Teacher();
        try {
            t.checkScore(score);
        } catch (ScoreException e) {
            e.printStackTrace();
        }
    }
}
```



## 9.throws 和 throw 的区别

![](https://github.com/Continuers/Java/blob/main/picture/164.png)





# 30.集合进阶

![](https://github.com/Continuers/Java/blob/main/picture/165.png)



## 1.Collection



### 1.集合知识回顾

![](https://github.com/Continuers/Java/blob/main/picture/166.png)



### 2.集合类体系结构

![](https://github.com/Continuers/Java/blob/main/picture/167.png)



### 3.Collection  集合的概述和使用

![](https://github.com/Continuers/Java/blob/main/picture/168.png)

```java
package com.itrs;

import java.util.ArrayList;
import java.util.Collection;

/*
    创建 Collection集合的对象
    多态的方式
    Arraylist()
 */
public class ConllectionDemo {
    public static void main(String[] args) {
        //创建 Collection集合的对象
        Collection<String> c = new ArrayList<String>();

        //添加元素： boolean add (E e)
        c.add("hello");
        c.add("world");
        c.add("java");

        //输出集合对象
        System.out.println(c);      //[hello, world, java]
    }

}
```



### 4.Collection 集合常用方法

![](https://github.com/Continuers/Java/blob/main/picture/169.png)

```java
package com.itrs;

import java.util.ArrayList;
import java.util.Collection;

/*
    Collection集合常用方法:
        boolean add(E e):添加元素
        boolean remove(Object o):从集合中移除指定的元素
        void clear():清空集合中的元素
        boolean contains( Object o):判断集合中是否存在指定的元素
        boolean isempty():判断集合是否为空
        int size():集合的长度,也就是集合中元素的个数

    Alt+7    打开一个窗口，能够看到类的所有信息
 */
public class ConllectionDemo2 {
    public static void main(String[] args) {
        //创建集合对象
        Collection<String> c = new ArrayList<String>();
        //boolean add(E e):添加元素
//        System.out.println(c.add("hello"));
//        System.out.println(c.add("world"));
//        System.out.println(c.add("world"));
        c.add("hello");
        c.add("world");
        c.add("java");

        //boolean remove(Object o):从集合中移除指定的元素
//        System.out.println(c.remove("world"));
//        System.out.println(c.remove("javaee"));

        //void clear():清空集合中的元素
//        c.clear();

        //boolean contains( Object o):判断集合中是否存在指定的元素
//        System.out.println(c.contains("world"));
//        System.out.println(c.contains("javaee"));

        //boolean isempty():判断集合是否为空
//        System.out.println(c.isEmpty());

        //int size():集合的长度,也就是集合中元素的个数
        System.out.println(c.size());

        //输出集合对象
        System.out.println(c);
    }
}
```



### 5.Collection 集合的遍历

![](https://github.com/Continuers/Java/blob/main/picture/170.png)



```java
package com.itrs;

import java.util.ArrayList;
import java.util.Collection;
import java.util.Iterator;

/*
    Iterator:迭代器,集合的专用遍历方式
        Iterator<E> iterator():返回此集合中元素的选代器,通过集合的 iterator()方法得到
        迭代器是通过集合的 iterator()方法得到的,所以我们说它是依赖于集合而存在的
    Iterator 中的常用方法
        E next():返回选代中的下ー个元素
        boolean hasnext():如果迭代具有更多元素,则返回 true
 */
public class ConllectionDemo3 {
    public static void main(String[] args) {
        //创建集合对象
        Collection<String> c = new ArrayList<String>();

        //添加元素
        c.add("hello");
        c.add("world");
        c.add("java");

        //Iterator<E> iterator():返回此集合中元素的选代器,通过集合的 iterator()方法得到
        Iterator<String> it = c.iterator();
        /*
            public Iterator<E> iterator() {
                return new Itr();
            }

            private class Itr implements Iterator<E> {
                ...
            }
         */

        //E next():返回选代中的下ー个元素
        /*
        System.out.println(it.next());
        System.out.println(it.next());
        System.out.println(it.next());
        System.out.println(it.next());  //NoSuchElementException:表示被请求的元素不存在
        */

        //boolean hasnext():如果迭代具有更多元素,则返回 true
        /*if (it.hasNext()){
            System.out.println(it.next());
        }
        if (it.hasNext()){
            System.out.println(it.next());
        }
        if (it.hasNext()){
            System.out.println(it.next());
        }
        if (it.hasNext()){
            System.out.println(it.next());
        }*/

        //用while循环改进判断
        while (it.hasNext()){
//            System.out.println(it.next());
            String s = it.next();
            System.out.println(s);
        }
    }
}
```



### 6.集合的使用步骤

![](https://github.com/Continuers/Java/blob/main/picture/171.png)

![](https://github.com/Continuers/Java/blob/main/picture/172.png)



### 案例：Collection集合存储学生对象并遍历

![](https://github.com/Continuers/Java/blob/main/picture/173.png)

```java
package com.itrs2;

public class Student {
    private String name;
    private int age;

    public Student() {
    }

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}
```

```java
package com.itrs2;

import java.util.ArrayList;
import java.util.Collection;
import java.util.Iterator;

/*
    需求:
        创建一个存储学生对象的集合,存储3个学生对象,使用程序实现在控制台遍历该集合
    思路:
        1.定义学生类
        2:创建 Collection集合对象
        3:创建学生对象
        4:把学生添加到集合
        5:遍历集合(迭代器方式)
*/
public class CollectionDemo {
    public static void main(String[] args) {
        //创建 Collection集合对象
        Collection<Student> c = new ArrayList<Student>();

        //创建学生对象
        Student s1 = new Student("java", 30);
        Student s2 = new Student("javaee",20);
        Student s3 = new Student("java",25);

        //把学生添加到集合
        c.add(s1);
        c.add(s2);
        c.add(s3);

        //遍历集合(迭代器方式)
        Iterator<Student> it = c.iterator();
        while (it.hasNext()) {
            Student s = it.next();
            System.out.println(s.getName() + "," + s.getAge());
        }
    }
}
```



## 2.List

### 1.List 集合概述和特点

![](https://github.com/Continuers/Java/blob/main/picture/174.png)



```java
package com.itrs;

import java.util.ArrayList;
import java.util.Iterator;
import java.util.List;

/*
    List集合特点
        有序,存储和取出的元素顺序一致
        可重复: 存储的元素可以重复
 */
public class ListDemo {
    public static void main(String[] args) {
        //创建集合对象
        List<String> list = new ArrayList<>();

        //添加元素
        list.add("hello");
        list.add("world");
        list.add("java");
        list.add("javase");

        //输出集合对象
//        System.out.println(list);

        //迭代器的方式遍历
        Iterator<String> it = list.iterator();
        while(it.hasNext()){
            String s = it.next();
            System.out.println(s);
        }
    }
}
```



### 2.List 集合特有方法

![](https://github.com/Continuers/Java/blob/main/picture/178.png)

```java
package com.itrs;

import java.util.ArrayList;
import java.util.List;

/*
    List集合特有方法:
        void add( int index, E element):在此集合中的指定位置插入指定的元素
        E remove( int index):删除指定索引处的元素,返回被删除的元素
        E set( int index, E element):修改指定索引处的元素,返回被修改的元素
        E get( int index):返回指定索引处的元素
 */
public class ListDemo2 {
    public static void main(String[] args) {
        //创建集合对象
        List<String> list = new ArrayList<String>();

        //添加元素
        list.add("hello");
        list.add("world");
        list.add("java");

        //void add( int index, E element):在此集合中的指定位置插入指定的元素
//        list.add(1,"javaee");

        //E remove( int index):删除指定索引处的元素,返回被删除的元素
//        System.out.println(list.remove(1));

        //E set( int index, E element):修改指定索引处的元素,返回被修改的元素
//        System.out.println(list.set(1,"javaee"));

        //E get( int index):返回指定索引处的元素
//        System.out.println(list.get(1));

        //输出集合对象
//        System.out.println(list);

        //遍历集合
//        System.out.println(list.get(0));
//        System.out.println(list.get(1));
//        System.out.println(list.get(2));

        //用 for 循环改进遍历
        for (int i=0;i<list.size();i++){
            String s = list.get(i);
            System.out.println(s);
        }
    }
}
```



### 案例：List 集合存储学生对象并遍历

![](https://github.com/Continuers/Java/blob/main/picture/179.png)

```java
package com.itrs3;

public class Student {
    private String name;
    private int age;

    public Student() {
    }

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}
```

```java
package com.itrs3;

import java.util.ArrayList;
import java.util.Iterator;
import java.util.List;

/*
    需求:
        创建一个存储学生对象的集合,存储3个学生对象,使用程序实现在控制台遍历该集合
    思路:
        1:定义学生类
        2:创建 List 集合对象
        3:创建学生对象
        4:把学生添加到集合
        5:遍历集合(迭代器方式,for循环方式)
 */
public class ListDemo {
    public static void main(String[] args) {
        //创建List集合对象
        List<Student> list = new ArrayList<>();

        //创建学生对象
        Student s1 = new Student("张杰",35);
        Student s2 = new Student("谢娜",34);
        Student s3 = new Student("迪丽热巴",30);

        //把学生添加到集合
        list.add(s1);
        list.add(s2);
        list.add(s3);

        //遍历集合(迭代器方式,for循环方式)
        //迭代器方式
        Iterator<Student> it = list.iterator();
        while (it.hasNext()){
            Student s = it.next();
            System.out.println(s.getName()+","+s.getAge());
        }
        System.out.println();

        //for 循环方式
        for (int i=0;i<list.size();i++){
            Student s = list.get(i);
            System.out.println(s.getName()+","+s.getAge());
        }
    }
}
```



### 3.并发修改异常

![](https://github.com/Continuers/Java/blob/main/picture/180.png)

```java
package com.itrs4;

import java.util.ArrayList;
import java.util.Iterator;
import java.util.List;

/*
    需求:
        我有一个集合:List<string> List = new Arraylist< string>()
        里面有三个元素:List.add(" hello");tist.ad(" world");ist.ad("java");
        遍历集合,得到每一个元素,看有没有" world"这个元素,如果有,我就添加一个" gavage"元素,请写代码实现

        ConcurrentModificationException:当不允许这样的修改时,可以通过检测到对象的并发修改的方法来抛出此异

 */
public class ListDemo {
    public static void main(String[] args) {
        //创建List集合对象
        List<String> list = new ArrayList<String>();

        //添加到集合
        list.add("hello");
        list.add("world");
        list.add("java");

        //遍历集合,得到每一个元素,看有没有" world"这个元素,如果有,我就添加一个" gavage"元素,请写代码实现
//        Iterator<String> it = list.iterator();
//        while (it.hasNext()){
//            String s = it.next();
//            if (s.equals("world")){
//                list.add("javaee");
//            }
//        }                                 //ConcurrentModificationException

        for (int i=0;i<list.size();i++){
            String s = list.get(i);
            if (s.equals("world")){
                list.add("javaee");
            }
        }

        //输出集合对象
        System.out.println(list);
    }
}
```

```java
/*并发修改异常的源码分析*/

public interface List<E>{
    Iterator<E> iterator();
    boolean add(E e);
}
public abstract class AbstractList<E>{
    protected int modCount = 0;
}

public class ArrayList<E> extends AbstractList<E> implements List<E> {

    public E get(int index) {
        Objects.checkIndex(index, size);
        return elementData(index);
    }

    public boolean add(E e) {
        modCount++;
        add(e, elementData, size);
        return true;
    }

    public Iterator<E> iterator() {
        return new Itr();
    }

    private class Itr implements Iterator<E> {
        int expectedModCount = modCount;
        /*
            modCount:实际修改集合的次数
            expectedModCount:预期修改集合的次数
        */


        public E next() {
            checkForComodification();
            int i = cursor;
            if (i >= size)
                throw new NoSuchElementException();
            Object[] elementData = ArrayList.this.elementData;
            if (i >= elementData.length)
                throw new ConcurrentModificationException();
            cursor = i + 1;
            return (E) elementData[lastRet = i];
        }

        final void checkForComodification() {
            if (modCount != expectedModCount)
                throw new ConcurrentModificationException();
        }
    }
}
```



### 4.Listlterator

![](https://github.com/Continuers/Java/blob/main/picture/181.png)

```java
package com.itrs2;

import java.util.ArrayList;
import java.util.List;
import java.util.ListIterator;

/*
    Listiterator:列表迭代器
        通过List集合的 Listiterator()方法得到,所以说它是List集合特有的迭代器
        用于允许程序员沿任一方向遍历列表的列表的迭代器,在迭代期间修改列表,并获取列表中迭代器的当前位置

    Listiterator中的常用方法
        E next():返回迭代中的下一个元素
        boolean hasnext():如果迭代具有更多元素,则返回true
        E previous():返回列表中的上一个元素
        boolean hasprevious():如果此列表迭代器在相反方向遍历列表时具有更多元素,则返回true
        void add(Ee):将指定的元素插入列表
 */
public class ListIteratorDemo {
    public static void main(String[] args) {
        //创建集合对象
        List<String> list = new ArrayList<>();

        //添加元素
        list.add("hello");
        list.add("world");
        list.add("java");

        //通过List集合的 Listiterator()方法得到
//        ListIterator<String> lit = list.listIterator();
//        while (lit.hasNext()){
//            String s = lit.next();
//            System.out.println(s);      //hello  world  java
//        }
//
//        System.out.println("-------");
//
//        while (lit.hasPrevious()){
//            String s = lit.previous();
//            System.out.println(s);      //java  world  hello
//        }

        //获取列表迭代器
        ListIterator<String> lit = list.listIterator();
        while (lit.hasNext()){
            String s = lit.next();
            if (s.equals("world")){
                lit.add("javaee");
            }
        }

        System.out.println(list);
    }
}
```

```java
/*ListIterator源码分析*/

public interface List<E>{
    Iterator<E> iterator();
    ListIterator<E> listIterator();
}
public abstract class AbstractList<E>{
    protected int modCount = 0;
}

public class ArrayList<E> extends AbstractList<E> implements List<E> {
    public Iterator<E> iterator() {
        return new Itr();
    }

    private class Itr implements Iterator<E> {
        ...
    }

    public ListIterator<E> listIterator() {
        return new ListItr(0);
    }

    private class ListItr extends Itr implements ListIterator<E> {
        public void add(E e) {
            checkForComodification();

            try {
                int i = cursor;
                ArrayList.this.add(i, e);
                cursor = i + 1;
                lastRet = -1;
                expectedModCount = modCount;
            } catch (IndexOutOfBoundsException ex) {
                throw new ConcurrentModificationException();
            }
        }
    }
}
```



### 5.增强 for 循环

![](https://github.com/Continuers/Java/blob/main/picture/182.png)

```java
package com.itrs4;

import java.util.ArrayList;
import java.util.List;

/*
    增强for:简化数组和 Collection集合的遍历
        实现 Iterable接口的类允许其对象成为增强型for语句的目标
        它是JDK5之后出现的,其内部原理是一个 Iteraton迭代器
    格式:
        for(元素数据类型变量名:数组或者 Collection集合){
            //在此处使用变量即可,该变量就是元素
        }
 */
public class ForDemo {
    public static void main(String[] args) {
        int[] arr = {1,2,3,4,5};
        for (int i : arr){
            System.out.println(i);
        }
        System.out.println();

        String[] strArray = {"hello","world","java"};
        for (String s : strArray){
            System.out.println(s);
        }
        System.out.println();

        List<String> list = new ArrayList<String>();
        list.add("hello");
        list.add("world");
        list.add("java");

        for (String s : list){
            System.out.println(s);
        }
        System.out.println();

        //内部原理是一个 Iteraton迭代器
        /*for (String s : list){
            if (s.equals("world")){
                list.add("javaee");    //ConcurrentModificationException
            }
        }*/
    }
}
```



### 案例：List 集合存储学生对象用三种方式遍历

![](https://github.com/Continuers/Java/blob/main/picture/183.png)

```java
package com.itrs5;

public class Student {
    private String name;
    private int age;

    public Student() {
    }

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}
```

```java
package com.itrs5;

import java.util.ArrayList;
import java.util.Iterator;
import java.util.List;

/*
    需求：
        创建一个存储学生对象的集合,存储3个学生对象,使用程序实现在控制台遍历该集合
    思路:
        1:定义学生类
        2:创建List集合对象
        3:创建学生对象
        4:把学生添加到集合
        5:遍历集合
            迭代器:集合特有的遍历方式
            普通for:带有索引的遍历方式
            增强for:最方便的遍历方式
 */
public class ListDemo {
    public static void main(String[] args) {
        //创建List集合对象
        List<Student> list = new ArrayList<>();

        //创建学生对象
        Student s1 = new Student("java",30);
        Student s2 = new Student("javaee",15);
        Student s3 = new Student("javase",20);

        //把学生添加到集合
        list.add(s1);
        list.add(s2);
        list.add(s3);

        //迭代器:集合特有的遍历方式
        Iterator<Student> it = list.iterator();
        while(it.hasNext()){
            Student s = it.next();
            System.out.println(s.getName()+","+s.getAge());
        }
        System.out.println();

        //普通for:带有索引的遍历方式
        for (int i=0;i<list.size();i++){
            Student s = list.get(i);
            System.out.println(s.getName()+","+s.getAge());
        }
        System.out.println();

        //增强for:最方便的遍历方式
        for (Student s : list){
            System.out.println(s.getName()+","+s.getAge());
        }
    }
}
```



### 6.数据结构

![](https://github.com/Continuers/Java/blob/main/picture/186.png)

### 7.常见数据结构之栈

![](https://github.com/Continuers/Java/blob/main/picture/184.png)

### 8.常见数据结构之队列

![](https://github.com/Continuers/Java/blob/main/picture/185.png)



### 9.常见数据结构之数组

![](https://github.com/Continuers/Java/blob/main/picture/187.png)

### 10.常见数据结构之链表

![](https://github.com/Continuers/Java/blob/main/picture/188.png)

![](https://github.com/Continuers/Java/blob/main/picture/189.png)

![](https://github.com/Continuers/Java/blob/main/picture/190.png)

![](https://github.com/Continuers/Java/blob/main/picture/191.png)

![](https://github.com/Continuers/Java/blob/main/picture/192.png)

![](https://github.com/Continuers/Java/blob/main/picture/193.png)



### 11.List 集合子类特点

![](https://github.com/Continuers/Java/blob/main/picture/194.png)

```java
package com.itrs6;

import java.util.ArrayList;
import java.util.LinkedList;

/*
    List集合常用子类: Arraylist, Linkedlist
        Arraylist:底层数据结构是数组,查询快,增刪幔
        Linkedlist:底层数据结构是链表,查询慢,增删快
    练习：
        分别使用 Arraylist和 linkedlist完成存储字符串并遍历
 */
public class ListDemo {
    public static void main(String[] args) {
        //创建集合对象
        ArrayList<String> array = new ArrayList<String>();

        array.add("hello");
        array.add("world");
        array.add("java");

        //遍历
        for (String s : array){
            System.out.println(s);
        }
        System.out.println();

        LinkedList<String> linkedList = new LinkedList<String>();

        linkedList.add("hello");
        linkedList.add("world");
        linkedList.add("java");

        for (String s : linkedList){
            System.out.println(s);
        }


    }
}
```



### 案例：ArrayList 集合存储学生对象用三种方法遍历



![](https://github.com/Continuers/Java/blob/main/picture/195.png)

```java
package com.itrs6;

public class Student {
    private String name;
    private int age;

    public Student() {
    }

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}
```

```java
package com.itrs6;

import java.util.ArrayList;
import java.util.Iterator;

/*
    需求:
        创建一个存储学生对象的集合,存储3个学生对象,使用程序实现在控制台遍历该集合
    思路:
        1:定义学生类
        2:创建 Arraylist集合对象
        3:创建学生对象
        4:把学生添加到集合
        5:遍历集合
            迭代器:集合特有的遍历方式
            普通for:带有索引的遍历方式
            增强for:最方便的遍历方式
 */
public class ArrayListDemo {
    public static void main(String[] args) {
        //创建ArrayList 集合对象
        ArrayList<Student> array = new ArrayList<>();

        //创建学生对象
        Student s1 = new Student("java", 30);
        Student s2 = new Student("javaee", 35);
        Student s3 = new Student("javase", 20);

        //把学生添加到集合
        array.add(s1);
        array.add(s2);
        array.add(s3);

        //迭代器:集合特有的遍历方式
        Iterator<Student> it = array.iterator();
        while (it.hasNext()) {
            Student s = it.next();
            System.out.println(s.getName() + "," + s.getAge());
        }
        System.out.println();

        //普通for:带有索引的遍历方式
        for (int i = 0; i < array.size(); i++) {
            Student s = array.get(i);
            System.out.println(s.getName() + "," + s.getAge());
        }
        System.out.println();

        //增强for:最方便的遍历方式
        for (Student s : array) {
            System.out.println(s.getName() + "," + s.getAge());
        }
    }
}
```



### 12.LinkedList 集合的特有功能

![](https://github.com/Continuers/Java/blob/main/picture/196.png)

```java
package com.itrs7;

import java.util.LinkedList;

/*
    Linkedlist集合的特有功能:
        public void addfirst(Ee):在该列表开头插入指定的元素
        public void addlast(Ee):将指定的元素追加到此列表的末尾

        public E getfirst():返回此列表中的第一个元素
        public E getlast():返回此列表中的最后一个元素

        public E removefirst():从此列表中删除并返回第一个元素
        public E removelast():从此列表中删除并返回最后一个元素
 */
public class LinkedListDemo {
    public static void main(String[] args) {
        //创建集合对象
        LinkedList<String> linkedList = new LinkedList<String>();

        linkedList.add("hello");
        linkedList.add("world");
        linkedList.add("java");

//        public void addfirst(Ee):在该列表开头插入指定的元素
//        public void addlast(Ee):将指定的元素追加到此列表的末尾
//        linkedList.addFirst("javase");      //[javase, hello, world, java]
//        linkedList.addLast("javaee");       //[hello, world, java, javaee]

//        public E getfirst():返回此列表中的第一个元素
//        public E getlast():返回此列表中的最后一个元素
//        System.out.println(linkedList.getFirst());  //hello
//        System.out.println(linkedList.getLast());   //java

//        public E removefirst():从此列表中删除并返回第一个元素
//        public E removelast():从此列表中删除并返回最后一个元素
        System.out.println(linkedList.removeFirst());
        System.out.println(linkedList.removeLast());

        System.out.println(linkedList);

    }
}
```



## 3.Set

### 1.Set 集合概述和特点

![](https://github.com/Continuers/Java/blob/main/picture/197.png)

```java
package cn.itrs;

import java.util.HashSet;
import java.util.Set;

/*
    set集合特点
    不包含重复元素的集合
    没有带索引的方法,所以不能使用普通for循环遍历

    HashSet : 对集合的迭代顺序不作任何保证
 */
public class SetDemo {
    public static void main(String[] args) {
        //创建集合对象
        Set<String> set = new HashSet<String>();

        //添加元素
        set.add("hello");
        set.add("world");
        set.add("java");
        //不包含重复元素的集合
        set.add("world");

        //遍历
        for (String s:set){
            System.out.println(s);
        }
    }
}
```

### 2.哈希值

![](https://github.com/Continuers/Java/blob/main/picture/198.png)

```java
package cn.itrs;

public class Student {
    private String name;
    private int age;

    public Student() {
    }

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}
```

```java
package cn.itrs;

/*
    哈希值:
        是JDk根据对象的地址或者字符串或者数字算出来的int类型的数值

    0bject类中有一个方法可以获取对象的哈希值
        public int hashcode():返回对象的哈希码值
 */
public class HashDemo {
    public static void main(String[] args) {
        //创建学生对象
        Student s1 = new Student("java",30);

        //同一个对象多次调用hashCode()方法返回的哈希值是相同的
        System.out.println(s1.hashCode());  //1239731077
        System.out.println(s1.hashCode());  //1239731077
        System.out.println();

        Student s2 = new Student("java",30);

        //默认情况下,不同对象的哈希值是不相同的
        //通过方法重写，可以实现不同对象的哈希值是相同的
        System.out.println(s2.hashCode());  //557041912
        System.out.println();

        System.out.println("hello".hashCode()); //99162322
        System.out.println("world".hashCode()); //113318802
        System.out.println("java".hashCode());  //3254818

        System.out.println("world".hashCode()); //113318802
        System.out.println();

        System.out.println("北斗".hashCode());
        System.out.println("东风".hashCode());

    }
}
```



### 3.HashSet 集合概述和特点

```java
package cn.itrs;

import java.util.HashSet;

/*
    HashSet集合特点
        1:底层数据结构是哈希表
        2:对集合的迭代顺序不作任何保证,也就是说不保证存储和取出的元素顺序一致
        3:没有带索引的方法,所以不能使用普通 for循环遍历
        4:由于是 Set 集合,所以是不包含重复元素的集合
 */
public class HashSetDemo {
    public static void main(String[] args) {
        //创建集合对象
        HashSet<String> hs = new HashSet<String>();

        //添加元素
        hs.add("hello");
        hs.add("world");
        hs.add("java");

        hs.add("world");

        //遍历
        for (String s : hs){
            System.out.println(s);
        }
    }
}
```



### 4.HashSet 集合保证元素唯一性源码分析

![](https://github.com/Continuers/Java/blob/main/picture/199.png)

```java
//创建集合对象
HashSet<String> hs = new HashSet<String>();

//添加元素
hs.add("hello");
hs.add("world");
hs.add("java");
----------------------------------------------------------

public boolean add(E e) {
    return map.put(e, PRESENT)==null;
}

static final int hash(Object key) {
    int h;
    return (key == null) ? 0 : (h = key.hashCode()) ^ (h >>> 16);
}

public V put(K key, V value) {
    return putVal(hash(key), key, value, false, true);
}

//hash值和元素的hashCode()方法相关
final V putVal(int hash, K key, V value, boolean onlyIfAbsent,
               boolean evict) {
    Node<K,V>[] tab; Node<K,V> p; int n, i;

    //如果哈希表未初始化，就对其进行初始化
    if ((tab = table) == null || (n = tab.length) == 0)
        n = (tab = resize()).length;

    //根据对象的哈希值计算对象的存储位置，如果该位置没用元素，就存储元素
    if ((p = tab[i = (n - 1) & hash]) == null)
        tab[i] = newNode(hash, key, value, null);
    else {
        Node<K,V> e; K k;
        /*
            存入的元素和以前的元素比较哈希值
                如果哈希值不同，会继续向下执行，把元素添加到集合
                如果哈希值相同，会调用对象的equals()方法比较
                    如果返回false，会继续向下执行，把元素添加到集合
                    如果返回true，说明元素重复，不存储
        */
        if (p.hash == hash &&
            ((k = p.key) == key || (key != null && key.equals(k))))
            e = p;
        else if (p instanceof TreeNode)
            e = ((TreeNode<K,V>)p).putTreeVal(this, tab, hash, key, value);
        else {
            for (int binCount = 0; ; ++binCount) {
                if ((e = p.next) == null) {
                    p.next = newNode(hash, key, value, null);
                    if (binCount >= TREEIFY_THRESHOLD - 1) // -1 for 1st
                        treeifyBin(tab, hash);
                    break;
                }
                if (e.hash == hash &&
                    ((k = e.key) == key || (key != null && key.equals(k))))
                    break;
                p = e;
            }
        }
        if (e != null) { // existing mapping for key
            V oldValue = e.value;
            if (!onlyIfAbsent || oldValue == null)
                e.value = value;
            afterNodeAccess(e);
            return oldValue;
        }
    }
    ++modCount;
    if (++size > threshold)
        resize();
    afterNodeInsertion(evict);
    return null;
}
```

```java
package cn.itrs;

import java.util.HashSet;

/*
    HashSet集合特点
        1:底层数据结构是哈希表
        2:对集合的迭代顺序不作任何保证,也就是说不保证存储和取出的元素顺序一致
        3:没有带索引的方法,所以不能使用普通 for循环遍历
        4:由于是 Set 集合,所以是不包含重复元素的集合
 */
public class HashSetDemo {
    public static void main(String[] args) {
        //创建集合对象
        HashSet<String> hs = new HashSet<String>();

        //添加元素
        hs.add("hello");
        hs.add("world");
        hs.add("java");

        hs.add("world");

        //遍历
        for (String s : hs){
            System.out.println(s);
        }
    }
}
```



### 5.常用数据结构值哈希表

![](https://github.com/Continuers/Java/blob/main/picture/200.png)



### 案例：HashSet 集合存储学生对象并遍历


![](https://github.com/Continuers/Java/blob/main/picture/201.png)

```java
package cn.itrs;

public class Student {
    private String name;
    private int age;

    public Student() {
    }

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;

        Student student = (Student) o;

        if (age != student.age) return false;
        return name != null ? name.equals(student.name) : student.name == null;
    }

    @Override
    public int hashCode() {
        int result = name != null ? name.hashCode() : 0;
        result = 31 * result + age;
        return result;
    }
}
```

```java
package cn.itrs;

import java.util.HashSet;

/*
    需求:
        创建一个存储学生对象的集合,存储3个学生对象,使用程序实现在控制台遍历该集合
        要求:学生对象的成员变量值相同,我们就认为是同一个对象
    思路：
        1:定义学生类
        2:创建 Hashset集合对象
        3:创建学生对象
        4:把学生添加到集合
        5:遍历集合(增强for)
 */
public class HashSetDemo2 {
    public static void main(String[] args) {
        //创建 Hashset集合对象
        HashSet<Student> hs = new HashSet<Student>();

        //创建学生对象
        Student s1 = new Student("java",30);
        Student s2 = new Student("javaee",40);
        Student s3 = new Student("javase",20);

        Student s4 = new Student("javase",20);

        //把学生添加到集合
        hs.add(s1);
        hs.add(s2);
        hs.add(s3);
        hs.add(s4);

        //遍历集合(增强for)
        for (Student s : hs){
            System.out.println(s.getName()+","+s.getAge());
        }
    }
}
```

### 6.LinkedHashSet集合概述和特点


![](https://github.com/Continuers/Java/blob/main/picture/202.png)

```java
package cn.itrs;

import java.util.LinkedHashSet;

/*
    Linkedhashset集合特点
        1:哈希表和链表实现的Set接口,具有可预测的迭代次序
        2:由链表保证元素有序,也就是说元素的存储和取出顺序是一致的
        3:由哈希表保证元素唯一,也就是说没有重复的元素
 */
public class LinkedHashSetDemo {
    public static void main(String[] args) {
      //创建集合对象
        LinkedHashSet<String> linkedHashSet = new LinkedHashSet<String>();

        //添加元素
        linkedHashSet.add("hello");
        linkedHashSet.add("world");
        linkedHashSet.add("java");

        linkedHashSet.add("world");

        //遍历集合
        for (String s : linkedHashSet){
            System.out.println(s);
        }
    }
}
```



### 7.TreeSet 集合概述和特点

![](https://github.com/Continuers/Java/blob/main/picture/203.png)

```java
package cn.itrs;

import java.util.TreeSet;
/*
    Treeset集合特点
        1:元素有序,这里的顺序不是指存储和取岀的顺序,而是按照一定的规则进行排序,具体排序方式取决于构造方法
            Treeset():根据其元素的自然排序进行排序
            Treeset( Comparator comparator):根据指定的比较器进行排序
        2:没有带索引的方法,所以不能使用普通fo循环遍历
        3:由于是set集合,所以不包含重复元素的集合
 */
public class TreeSetDemo {
    public static void main(String[] args) {
        TreeSet<Integer> ts = new TreeSet<Integer>();

        ts.add(10);
        ts.add(40);
        ts.add(50);
        ts.add(30);
        ts.add(20);

        ts.add(30);

        //遍历集合
        for (Integer i : ts) {
            System.out.println(i);    //10  20  30  40  50
        }
    }
}
```



### 8.自然排序 Comparable 的使用

![](https://github.com/Continuers/Java/blob/main/picture/204.png)

```java
package cn.itrs;

public class Student implements Comparable<Student> {
    private String name;
    private int age;

    public Student() {
    }

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    @Override
    public int compareTo(Student s) {
//        return 0;
//        return 1;     //升序
//        return -1;      //降序

        //按照年龄从小到大排序
        int num = this.age - s.age;  //升序
//        int num = s.age - this.age;  //降序
        int num2 = num == 0?this.name.compareTo(s.name):num;
        return num2;
    }
}
```

```java
package cn.itrs;

import java.util.TreeSet;

/*
    存储学生对象并遍历,创建集合使用无参构造方法
    要求:按照年龄从小到大排序,年齡相同时,按照姓名的字母顺序排序
 */
public class TreeSetDemo2 {
    public static void main(String[] args) {
        TreeSet<Student> ts = new TreeSet<Student>();

        Student s1 = new Student("java",10);
        Student s2 = new Student("javaee",20);
        Student s3 = new Student("javase",30);
        Student s4 = new Student("javaweb",40);

        Student s5 = new Student("spring",40);
        Student s6 = new Student("spring",40);

        ts.add(s1);
        ts.add(s2);
        ts.add(s3);
        ts.add(s4);
        ts.add(s5);
        ts.add(s6);

        for (Student s : ts){
            System.out.println(s.getName()+","+s.getAge());
        }


    }
}
```



```java
/*
    java,10
    javaee,20
    javase,30
    javaweb,40
    spring,40
*/
```



### 9.比较器排序 Comparator 的使用

![](https://github.com/Continuers/Java/blob/main/picture/205.png)

```java
package com.itrs8;

public class Student {
    private String name;
    private int age;

    public Student() {
    }

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}
```

```java
package com.itrs8;

import java.util.Comparator;
import java.util.TreeSet;

/*
    存储学生对象并遍历,创建 Treeset集合使用带参构造方法
    要求:按照年龄从小到大排序,年龄相同时,按照姓名的字母顺序排序
 */
public class TreeSetDemo {
    public static void main(String[] args) {
        TreeSet<Student> ts = new TreeSet<Student>(new Comparator<Student>() {
            @Override
            public int compare(Student s1, Student s2) {
                //this.age - s.age
                //s1,s2
                int num = s1.getAge() - s2.getAge();
                int num2 = num == 0?s1.getName().compareTo(s2.getName()):num;
                return num2;
            }
        });

        Student s1 = new Student("java",10);
        Student s2 = new Student("javaee",20);
        Student s3 = new Student("javase",30);
        Student s4 = new Student("javaweb",40);

        Student s5 = new Student("spring",40);
        Student s6 = new Student("spring",40);

        ts.add(s1);
        ts.add(s2);
        ts.add(s3);
        ts.add(s4);
        ts.add(s5);
        ts.add(s6);

        for (Student s : ts){
            System.out.println(s.getName()+","+s.getAge());
        }

    }

}
```



### 案例：成绩排序

![](https://github.com/Continuers/Java/blob/main/picture/206.png)

```java
package com.itrs9;

public class Student {
    private String name;
    private int chinese;
    private int math;

    public Student() {
    }

    public Student(String name, int chinese, int math) {
        this.name = name;
        this.chinese = chinese;
        this.math = math;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getChinese() {
        return chinese;
    }

    public void setChinese(int chinese) {
        this.chinese = chinese;
    }

    public int getMath() {
        return math;
    }

    public void setMath(int math) {
        this.math = math;
    }

    public int getSum(){
        return this.chinese+this.math;
    }
}
```

```java
package com.itrs9;

import java.util.Comparator;
import java.util.TreeSet;

/*
    需求:
        用 TreeSet集合存储多个学生信息(姓名,语文成绩,数学成绩),并遍历该集合
        要求:按照总分从高到低出现
    思路:
        ①定义学生类
        ②创建 Treeset集合对象,通过比较器排序进行排序
        ③创建学生对象
        ④把学生对象添加到集合
        ⑤遍历集合
 */
public class TreeSetDemo {
    public static void main(String[] args) {
        //创建 Treeset集合对象,通过比较器排序进行排序
        TreeSet<Student> ts = new TreeSet<Student>(new Comparator<Student>() {
            @Override
            public int compare(Student s1, Student s2) {
//                int num = (s2.getChinese() + s2.getMath()) - (s1.getChinese() + s1.getMath());
                //主要条件
                int num = s2.getSum() - s1.getSum();
                //次要条件
                int num2 = num == 0 ? s1.getChinese() - s2.getChinese() : num;
                int num3 = num2 == 0 ? s1.getName().compareTo(s2.getName()) : num2;
                return num3;
            }
        });

        //创建学生对象
        Student s1 = new Student("java", 100, 98);
        Student s2 = new Student("javaweb", 99, 97);
        Student s3 = new Student("javase", 95, 96);
        Student s4 = new Student("javaee", 90, 99);
        Student s5 = new Student("springboot", 99, 98);

        Student s6 = new Student("springcloud", 98, 99);
        Student s7 = new Student("spring", 98, 99);

        //把学生对象添加到集合
        ts.add(s1);
        ts.add(s2);
        ts.add(s3);
        ts.add(s4);
        ts.add(s5);
        ts.add(s6);
        ts.add(s7);

        //遍历集合
        for (Student s : ts) {
            System.out.println(s.getName() + "：" + s.getChinese() + "+" + s.getMath() + "=" + s.getSum());
        }
    }
}

/*
	java：100+98=198
    spring：98+99=197
    springcloud：98+99=197
    springboot：99+98=197
    javaweb：99+97=196
    javase：95+96=191
    javaee：90+99=189
*/
```



### 案例：不重复的随机数

![](https://github.com/Continuers/Java/blob/main/picture/207.png)

```java
package com.itrs9;

import java.util.HashSet;
import java.util.Random;
import java.util.Set;
import java.util.TreeSet;

/*
    需求：
        編写一个程序,获取 10 个 1-20 之间的随机数,要求随机数不能重复,并在控制台输出
    思路:
        1:创建Set集合对象
        2:创建随机数对象
        3:判断集合的长度是不是小于10
            是:产生一个随机数,添加到集合
            回到3继续
        4:遍历集合
 */
public class SetDemo {
    public static void main(String[] args) {
        //创建Set集合对象
//        Set<Integer> set = new HashSet<Integer>();    //无序
        Set<Integer> set = new TreeSet<Integer>();      //顺序

        //创建随机数对象
        Random r = new Random();

        //判断集合的长度是不是小于10
        while (set.size()<10){
            //产生一个随机数,添加到集合
            int number = r.nextInt(20)+1;
            set.add(number);
        }

        //遍历集合
        for (Integer i : set){
            System.out.println(i);
        }
    }
}
```



## 4.泛型

### 1.泛型概述

![](https://github.com/Continuers/Java/blob/main/picture/208.png)

```java
package com.itrs10;

import java.util.ArrayList;
import java.util.Collection;
import java.util.Iterator;

/*
    需求： Collection 集合存储字符串并遍历
 */
public class GenericDemo {
    public static void main(String[] args) {
        //创建集合对象
//        Collection c = new ArrayList();
        Collection<String> c = new ArrayList<String>();

        //添加元素
        c.add("hello");
        c.add("java");
        c.add("world");

//        c.add(100);

        //遍历集合
//        Iterator it = c.iterator();
        Iterator<String> it = c.iterator();
        while (it.hasNext()){
//            Object obj = it.next();
//            System.out.println(obj);
//            String s = (String)it.next();
            String s = it.next();
            System.out.println(s);
        }
    }
}
```



### 2.泛型类

```java
package cn.itrs2;

public class Student {
    private String name;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }
}
```

```java
package cn.itrs2;

public class Teacher {
    private Integer age;

    public Integer getAge() {
        return age;
    }

    public void setAge(Integer age) {
        this.age = age;
    }
}
```

```java
package cn.itrs2;
/*
    泛型类
 */
public class Generic<T> {
    private T t;

    public T getT() {
        return t;
    }

    public void setT(T t) {
        this.t = t;
    }
}
```

```java
package cn.itrs2;

/*
    测试类
 */
public class GenericDemo {
    public static void main(String[] args) {
        Student s = new Student();
        s.setName("java");
        System.out.println(s.getName());

        Teacher t = new Teacher();
        t.setAge(30);
//        t.setAge("30");
        System.out.println(t.getAge());
        System.out.println();

        Generic<String> g1 = new Generic<String>();
        g1.setT("javase");
        System.out.println(g1.getT());

        Generic<Integer> g2 = new Generic<Integer>();
        g2.setT(20);
        System.out.println(g2.getT());

        Generic<Boolean> g3 = new Generic<Boolean>();
        g3.setT(true);
        System.out.println(g3.getT());

    }
}
```

### 3.泛型方法

```java
package cn.itrs3;
/*
public class Generic {
    public void show(String s){
        System.out.println(s);
    }
    public void show(Integer i){
        System.out.println(i);
    }
    public void show(Boolean b){
        System.out.println(b);
    }
}
*/

//泛型类改进
//public class Generic<T> {
//    public void show(T t){
//        System.out.println(t);
//    }
//}

//泛型方法改进
public class Generic{
    public <T> void show(T t){
        System.out.println(t);
    }
}
```

```java
package cn.itrs3;

/*
    测试类
 */
public class GenericDemo {
    public static void main(String[] args) {
//        Generic g = new Generic();
//        g.show("java");
//        g.show(true);
//        g.show(100);

//        Generic<String> g1 = new Generic<String>();
//        g1.show("java");
//
//        Generic<Integer> g2 = new Generic<Integer>();
//        g2.show(100);
//
//        Generic<Boolean> g3 = new Generic<Boolean>();
//        g3.show(true);

        //泛型方法的使用
        Generic g = new Generic();
        g.show("java");
        g.show(100);
        g.show(true);
        g.show(3.14);
    }
}
```



### 4.泛型接口

![](https://github.com/Continuers/Java/blob/main/picture/209.png)

```java
package cn.itrs4;
/*
    接口
 */
public interface Generic<T> {
    void show(T t);
}
```

```java
package cn.itrs4;

public class GenericImpl<T> implements Generic<T> {
    @Override
    public void show(T t) {
        System.out.println(t);
    }
}
```

```java
package cn.itrs4;

/*
    测试类
 */
public class GenericDemo {
    public static void main(String[] args) {
        Generic<String> g1 = new GenericImpl<>();
        g1.show("spring");

        Generic<Integer> g2 = new GenericImpl<Integer>();
            g2.show(100);
    }
}
```



### 5.类型通配符

![](https://github.com/Continuers/Java/blob/main/picture/210.png)

```java
package cn.itrs5;

import java.util.ArrayList;
import java.util.List;

/*
    类型通配符:<?>
        List<?>:表示元素类型未知的 List,它的元素可以匹配任何的类型
        这种带通配符的 List 仅表示它是各种泛型 List 的父类,并不能把元素添加到其中

    类型通配符上限:<? extends类型>
        List<? extends Number>:它表示的类型是 Numbel或者其子类型

    类型通配符下限:<? super类型>
        List<? super Number>:它表示的类型是 Number或者其父类型
 */
public class DenericDemo {
    public static void main(String[] args) {
       //类型通配符:<?>
        List<?> list1 = new ArrayList<Object>();
        List<?> list2 = new ArrayList<Number>();
        List<?> list3 = new ArrayList<Integer>();
        System.out.println();

        //类型通配符上限:<? extends类型>
//        List<? extends Number> list4 = new ArrayList<Object>();
        List<? extends Number> list5 = new ArrayList<Number>();
        List<? extends Number> list6 = new ArrayList<Integer>();
        System.out.println();

        //类型通配符下限:<? super类型>
        List<? super Number> list7 = new ArrayList<Object>();
        List<? super Number> list8 = new ArrayList<Number>();
//        List<? super Number> list9 = new ArrayList<Integer>();
    }
}
```



### 6.可变参数

![](https://github.com/Continuers/Java/blob/main/picture/211.png)

```java
package cn.itrs5;

public class ArgsDemo {
    public static void main(String[] args) {
        System.out.println(sum(10, 20));
        System.out.println(sum(10, 20, 30));
        System.out.println(sum(10, 20, 30, 40));

        System.out.println(sum(10, 20, 30, 40, 50));
        System.out.println(sum(10, 20, 30, 40, 50, 60));
        System.out.println(sum(10, 20, 30, 40, 50, 60, 70));
    }

//    public static int sum(int b,int... a) {
//        return 0;
//    }
    
    public static int sum(int... a) {
//        return 0;
        int sum = 0;
        for (int i : a) {
            sum += i;
        }
        return sum;
    }

//    public static int sum(int a, int b) {
//        return a + b;
//    }
//
//    public static int sum(int a, int b, int c) {
//        return a + b + c;
//    }
//
//    public static int sum(int a, int b, int c, int d) {
//        return a + b + c + d;
//    }
}
```



### 7.可变参数的使用

![](https://github.com/Continuers/Java/blob/main/picture/212.png)

```java
package cn.itrs5;

import java.sql.ClientInfoStatus;
import java.util.Arrays;
import java.util.List;
import java.util.Set;

/*
    Arrays 工具类中有一个静态方法：
        public static <T> List<T> asList (T... a): 返回由指定数组支持的固定大小的列表

    List接口中有一个静态方法：
        public static <E> List<E> of (E... elements): 返回包含任意数量元素的不可变列表

    Set 接口中有一个静态方法：
        public static <E> Set<E> of (E... elements): 返回一个包含任意数量元素的不可变集合
 */
public class ArgsDemo2 {
    public static void main(String[] args) {
        /*//public static <T> List<T> asList (T... a): 返回由指定数组支持的固定大小的列表
        List<String> list = Arrays.asList("hello", "java", "world");
//        list.add("javaee");     //UnsupportedOperationException
//        list.remove("world");   //UnsupportedOperationException
        list.set(1,"javaee");     //[hello, javaee, world]

        System.out.println(list);*/

        //public static <E> List<E> of (E... elements): 返回包含任意数量元素的不可变列表
/*        List<String> list = List.of("hello", "world", "java");
//        list.add("javaee");     //UnsupportedOperationException
//        list.remove("world");   //UnsupportedOperationException
//        list.set(1,"javaee");     ////UnsupportedOperationException

        System.out.println(list);*/

        //public static <E> Set<E> of (E... elements): 返回一个包含任意数量元素的不可变集合
//        Set<String> set = Set.of("hello", "java", "world","world"); //IllegalArgumentException
        Set<String> set = Set.of("hello", "java", "world");

//        set.add("javaee");      //UnsupportedOperationException
//        set.remove("world"); //UnsupportedOperationException
        
        System.out.println(set);
    }
}
```



## 5.Map

### 1.Map 集合概述和使用

![](https://github.com/Continuers/Java/blob/main/picture/213.png)

```java
package cn.itrs5;

import java.util.HashMap;
import java.util.Map;

/*
    Map集合概述
        Interface Map<K,V>  K:键的类型;  v:值的类型
        将键映射到值的对象;不能包含重复的键;每个键可以映射到最多一个值

    创建Map集合的对象
        多态的方式
        具体的实现类 HashMap
 */
public class MapDemo {
    public static void main(String[] args) {
        //创建集合对象
        Map<String,String> map = new HashMap<String,String>();

        //V put (K key, V value) 将指定的值与该映射中的指定键相关联
        map.put("itrs001","java");
        map.put("itrs002","javaee");
        map.put("itrs003","javase");
        map.put("itrs003","javaweb");
        //{itrs003=javaweb, itrs002=javaee, itrs001=java}

        //输出集合对象
        System.out.println(map);
    }
}
```



### 2.Map 集合的基本功能

![](https://github.com/Continuers/Java/blob/main/picture/214.png)

```java
package cn.itrs5;

import java.util.HashMap;
import java.util.Map;

/*
    Map集合的基本功能:
        V put(K key, V value):添加元素
        V remove( Object key):根据键删除键值对元素
        void clear():移除所有的键值对元素
        boolean containskey( Object key):判断集合是否包含指定的键
        boolean containsvalue( Object value):判断集合是否包含指定的值
        boolean isempty():判断集合是否为空
        int size():集合的长度,也就是集合中键值对的个数
 */
public class MapDemo2 {
    public static void main(String[] args) {
        //创建集合对象
        Map<String,String> map = new HashMap<String,String>();

        //V put(K key, V value):添加元素
        map.put("杨过","小龙女");
        map.put("郭靖","黄蓉");

        //V remove( Object key):根据键删除键值对元素
//        System.out.println(map.remove("郭靖"));
//        System.out.println(map.remove("郭襄"));

        //void clear():移除所有的键值对元素
//        map.clear();

        //boolean containskey( Object key):判断集合是否包含指定的键
//        System.out.println(map.containsKey("郭靖"));
//        System.out.println(map.containsKey("郭襄"));

        //boolean containsvalue( Object value):判断集合是否包含指定的值
//        System.out.println(map.containsValue("黄蓉"));    //V true    K false
//        System.out.println(map.containsValue("郭襄"));

        //boolean isEmpty():判断集合是否为空
//        System.out.println(map.isEmpty());

        //int size():集合的长度,也就是集合中键值对的个数
        System.out.println(map.size());

        //输出集合对象
        System.out.println(map);

    }
}
```



### 3.Map集合的获取功能

![](https://github.com/Continuers/Java/blob/main/picture/215.png)

```java
package cn.itrs5;

import java.util.Collection;
import java.util.HashMap;
import java.util.Map;
import java.util.Set;

/*
    Map集合的获取功能:
    V get( Object key):根据键获取值
    Set<K> keyset():获取所有键的集合
    Collection<V> values():获取所有值的集合
 */
public class MapDemo3 {
    public static void main(String[] args) {
        //创建集合对象
        Map<String,String> map = new HashMap<String,String>();

        //添加元素
        map.put("杨过","小龙女");
        map.put("郭靖","黄蓉");

        //V get( Object key):根据键获取值
//        System.out.println(map.get("杨过"));  //小龙女
//        System.out.println(map.get("郭襄"));  //null

        //Set<K> keySet():获取所有键的集合
//        Set<String> keySet = map.keySet();
//        for (String key : keySet){
//            System.out.println(key);      //杨过    郭靖
//        }

        /* Collection<V> values():获取所有值的集合 */
        Collection<String> values = map.values();
        for (String value : values){
            System.out.println(value);    //小龙女   黄蓉
        }

    }
}
```



### 4.Map集合的遍历①

![](https://github.com/Continuers/Java/blob/main/picture/216.png)

```java
package cn.itrs5;

import java.util.HashMap;
import java.util.Map;
import java.util.Set;

/*
    Map集合的遍历(方式 1):
        1:获取所有键的集合。用 keyset()方法实现
        2:遍历键的集合,获取到每一个键。用增强for实现
        3:根据键去找值。用get( Object key)方法实现
 */
public class MapDemo4 {
    public static void main(String[] args) {
        //创建集合对象
        Map<String,String> map = new HashMap<String, String>();

        //添加元素
        map.put("杨过","小龙女");
        map.put("郭靖","黄蓉");

        //获取所有键的集合。用 keyset()方法实现
        Set<String> keySet = map.keySet();
        //遍历键的集合,获取到每一个键。用增强 for实现
        for (String key : keySet){
            //根据键去找值。用get( Object key)方法实现
            String value = map.get(key);
            System.out.println(key+","+value);
        }
    }
}
```

### 5.Map 集合的遍历②

![](https://github.com/Continuers/Java/blob/main/picture/217.png)

```java
package cn.itrs5;

import java.util.HashMap;
import java.util.Map;
import java.util.Set;

/*
    Map集合的遍历(方式2)
        1:获取所有键值对对象的集合
            Set<Map. Entry<K,V>> entrySet():获取所有键值对对象的集合
        2:遍历键值对对象的集合,得到每一个键值对对象
            用增强for实现,得到每一个Map. Entry
        3:根据键值对对象获取键和值
            用 getkey()得到键
            用 getvalue()得到值
 */
public class MapDemo5 {
    public static void main(String[] args) {
        //创建集合对象
        Map<String, String> map = new HashMap<String, String>();

        //添加元素
        map.put("杨过", "小龙女");
        map.put("郭靖", "黄蓉");

        //获取所有键值对对象的集合
        Set<Map.Entry<String, String>> entrySet = map.entrySet();
        //遍历键值对对象的集合,得到每一个键值对对象
        for (Map.Entry<String, String> me : entrySet) {
            //根据键值对对象获取键和值
            String key = me.getKey();
            String value = me.getValue();
            System.out.println(key + "," + value);
        }
    }
}
```



### 案例：HashMap 集合存储学生对象并遍历

![](https://github.com/Continuers/Java/blob/main/picture/218.png)

```java
package cn.itrs6;

import java.util.HashMap;
import java.util.Map;
import java.util.Set;

/*
    需求：
        创建一个 Hashmap集合,键是学号( String),值是学生对象( Student)。存储三个键值对元素,并遍历
    思路：
        1:定义学生类
        2:创建 HashMap集合对象
        3:创建学生对象
        4:把学生添加到集合
        5:遍历集合
            方式1:键找值
            方式2:键值对对象找键和值
 */
public class HashMapDemo {
    public static void main(String[] args) {
        //创建 HashMap集合对象
        HashMap<String, Student> hm = new HashMap<String, Student>();

        //创建学生对象
        Student s1 = new Student("java", 100);
        Student s2 = new Student("javaweb", 99);
        Student s3 = new Student("javaee", 98);

        //把学生添加到集合
        hm.put("itrs001", s1);
        hm.put("itrs002", s2);
        hm.put("itrs003", s3);

        //方式1:键找值
        Set<String> keySet = hm.keySet();
        for (String key : keySet) {
            Student value = hm.get(key);
            System.out.println(key + "," + value.getName() + "," + value.getAge());
        }
        System.out.println();
        //方式2:键值对对象找键和值
        Set<Map.Entry<String, Student>> entrySet = hm.entrySet();
        for (Map.Entry<String, Student> me : entrySet) {
            String key = me.getKey();
            Student value = me.getValue();
            System.out.println(key + "," + value.getName() + "," + value.getAge());
        }
    }
}
```

### 案例：HashMap 集合存储学生对象并遍历2

![](https://github.com/Continuers/Java/blob/main/picture/219.png)

```java
package cn.itrs7;

public class Student {
    private String name;
    private int age;

    public Student() {
    }

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;

        Student student = (Student) o;

        if (age != student.age) return false;
        return name != null ? name.equals(student.name) : student.name == null;
    }

    @Override
    public int hashCode() {
        int result = name != null ? name.hashCode() : 0;
        result = 31 * result + age;
        return result;
    }
}
```

```java
package cn.itrs7;

import java.util.HashMap;
import java.util.Set;

/*
    需求：
        创建一个 Hashmap.集合,键是学生对象( Student),值是居住地( String)。存储多个键值对元素,并遍历。
        要求保证键的唯一性:如果学生对象的成员变量值相同,我们就认为是同一个对象
    思路：
        1:定义学生类
        2:创建 Hashmap集合对象
        3:创建学生对象
        4:把学生添加到集合
        5:遍历集合
        6:在学生类中重写两个方法
            hashcode()
            equals()
 */
public class HashMapDemo {
    public static void main(String[] args) {
        //创建HashMap集合对象
        HashMap<Student,String> hm = new HashMap<Student,String>();

        //创建学生对象
        Student s1 = new Student("java", 100);
        Student s2 = new Student("javaweb", 99);
        Student s3 = new Student("javaee", 98);
        Student s4 = new Student("javaee", 98);

        //把学生添加到集合
        hm.put( s1,"广州");
        hm.put( s2,"上海");
        hm.put( s3,"北京");
        hm.put( s4,"深圳");

        //遍历集合
        Set<Student> keySet = hm.keySet();
        for (Student key : keySet){
            String value = hm.get(key);
            System.out.println(key.getName()+","+key.getAge()+","+value);
        }
    }
}
```



### 案例：ArrayList 集合存储 HashMap 元素并遍历

![](https://github.com/Continuers/Java/blob/main/picture/220.png)

```java
package cn.itrs7;

import java.util.ArrayList;
import java.util.HashMap;
import java.util.Set;

/*
    需求：
        创建一个 Arraylist集合,存储三个元素,每一个元素都是 Hashmap,每一个 Hashmap的键和值都是 String,并遍历
    思路:
        1:创建 Arraylist集合
        2:创建 Hashmap集合,并添加键值对元素
        3:把 Hashmap作为元素添加到 Arraylist集合
        4:遍历 Arraylist集合

    给出如下的数据：
        第一个 Hashmap集合的元素
            孙策    大乔
            周瑜    小乔
        第二个 Hashmap集合的元素
            郭靖    黄蓉
            杨过    小龙女
        第三个 Hashmap集合的元素
            令狐冲  任盈盈
            林平之  岳灵珊
 */
public class ArrayListIncludeHashMapDemo {
    public static void main(String[] args) {
        //创建ArrayList集合
        ArrayList<HashMap<String, String>> array = new ArrayList<HashMap<String, String>>();

        //创建HashMap集合，并添加键值对元素
        HashMap<String, String> hm1 = new HashMap<String, String>();
        hm1.put("孙策", "大乔");
        hm1.put("周瑜","小乔");
        //把 Hashmap作为元素添加到 Arraylist集合
        array.add(hm1);

        //创建HashMap集合，并添加键值对元素
        HashMap<String, String> hm2 = new HashMap<String, String>();
        hm2.put("郭靖","黄蓉");
        hm2.put("杨过","小龙女");
        //把 Hashmap作为元素添加到 Arraylist集合
        array.add(hm2);

        //创建HashMap集合，并添加键值对元素
        HashMap<String, String> hm3 = new HashMap<String, String>();
        hm3.put("令狐冲","任盈盈");
        hm3.put("林平之","岳灵珊");
        //把 Hashmap作为元素添加到 Arraylist集合
        array.add(hm3);

        //遍历 Arraylist集合
        for (HashMap<String, String> hm : array){
            Set<String> keySet = hm.keySet();
            for (String key : keySet){
                String value = hm.get(key);
                System.out.println(key+","+value);
            }
        }

    }
}
```



### 案例：HashMap 集合存储 ArrayList 元素并遍历

![](https://github.com/Continuers/Java/blob/main/picture/221.png)

```java
package cn.itrs7;

import javax.swing.*;
import java.util.ArrayList;
import java.util.HashMap;
import java.util.Set;

/*
    需求:
        创建一个 HashMap集合,存储三个键值对元素,每一个键值对元素的键是 String,值是 Arraylist,每一个 Arraylist的元素是 String,并遍历
    思路:
        1:创建 HashMap集合
        2:创建 Arraylist集合,并添加元素
        3:把 Arraylist作为元素添加到 HashMap集合
        4:遍历 HashMap集合

    给出如下的数据:
        第一个 Arraylist集合的元素:(三国演义)
            诸葛亮 赵云
        第二个 Arraylist集合的元素:(西游记)
            唐僧 孙悟空
        第三个 Array ist集合的元素:(水浒传)
            武松 鲁智深
 */
public class HashMapIncludeArrayListDemo {
    public static void main(String[] args) {
        //创建 HashMap集合
        HashMap<String, ArrayList<String>> hm = new HashMap<String, ArrayList<String>>();

        //创建 Arraylist集合,并添加元素
        ArrayList<String> sgyy = new ArrayList<String>();
        sgyy.add("诸葛亮");
        sgyy.add("赵云");
        //把 Arraylist作为元素添加到 HashMap集合
        hm.put("三国演义", sgyy);

        //创建 Arraylist集合,并添加元素
        ArrayList<String> xyj = new ArrayList<String>();
        xyj.add("唐僧");
        xyj.add("孙悟空");
        //把 Arraylist作为元素添加到 HashMap集合
        hm.put("西游记", xyj);

        //创建 Arraylist集合,并添加元素
        ArrayList<String> shz = new ArrayList<String>();
        shz.add("武松");
        shz.add("鲁智深");
        //把 Arraylist作为元素添加到 HashMap集合
        hm.put("水浒传", shz);

        //遍历 HashMap集合
        Set<String> keySet = hm.keySet();
        for (String key : keySet) {
            System.out.println(key);
            ArrayList<String> value = hm.get(key);
            for (String s : value) {
                System.out.println("\t" + s);
            }
        }
    }
}
```



### 案例：统计字符串中每个字符出现的次数

![](https://github.com/Continuers/Java/blob/main/picture/222.png)

![](https://github.com/Continuers/Java/blob/main/picture/223.png)

```java
package cn.itrs8;

import java.util.HashMap;
import java.util.Scanner;
import java.util.Set;
import java.util.TreeMap;

/*
    1:键盘录入一个字符串
    2:创建 ashman集合,键是 Character,值是 Integer
    3:遍历字符串,得到每一个字符
    4:拿得到的每一个字符作为键到 Hashmap集合中去找对应的值,看其返回值
        如果返回值是nuLL:说明该字符在 Hashmap集合中不存在,就把该字符作为键,1作为值存储
        如果返回值不是nuLL符在 Hashmap集合中存在,把该值加1,然后重新存储该字符和对应的值
    5:遍历 Hashmap集合,得到键和值,按照要求进行拼接
    6:输出结果
 */
public class HashMapDemo {
    public static void main(String[] args) {
        //键盘录入一个字符串
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入一个字符串：");
        String line = sc.nextLine();

        //创建 Hashman集合,键是 Character,值是 Integer
//        HashMap<Character,Integer> hm = new HashMap<Character,Integer>();
        TreeMap<Character, Integer> hm = new TreeMap<Character, Integer>();

        //遍历字符串,得到每一个字符
        for (int i = 0; i < line.length(); i++) {
            char key = line.charAt(i);

            //拿得到的每一个字符作为键到 Hashmap集合中去找对应的值,看其返回值
            Integer value = hm.get(key);

            if (value == null) {
                //如果返回值是nuLL:说明该字符在 Hashmap集合中不存在,就把该字符作为键,1作为值存储
                hm.put(key, 1);
            } else {
                //如果返回值不是nuLL符在 Hashmap集合中存在,把该值加1,然后重新存储该字符和对应的值
                value++;
                hm.put(key, value);
            }
        }
        //遍历 Hashmap集合,得到键和值,按照要求进行拼接
        StringBuilder sb = new StringBuilder();

        Set<Character> keySet = hm.keySet();
        for (Character key : keySet) {
            Integer value = hm.get(key);
            sb.append(key).append("(").append(value).append(")");
        }

        String result = sb.toString();

        //输出结果
        System.out.println(result);
        //请输入一个字符串：
        //asdwaswasredsradwdsda
        //a(5)d(5)e(1)r(2)s(5)w(3)
    }
}
```



## 6.Collections

### 1.Collections 概述和使用

![](https://github.com/Continuers/Java/blob/main/picture/224.png)

```java
package cn.itrs8;

import java.util.ArrayList;
import java.util.Collection;
import java.util.Collections;
import java.util.List;

/*
    Collections类的概述
        是针对集合操作的工具类

    Collections类的常用方法
        public static< T extends Comparable<? super T>> void sort(List<T>List):将指定的列表按升序排序
        public static void reverse(List<?>tist):反转指定列表中元素的顺序
        public static void shuffle(List<?>List):使用默认的随机源随机排列指定的列表
 */
public class CollectionsDemo {
    public static void main(String[] args) {
        List<Integer> list = new ArrayList<Integer>();

        list.add(30);
        list.add(20);
        list.add(50);
        list.add(10);
        list.add(40);

        //public static< T extends Comparable<? super T>> void sort(List<T>List):将指定的列表按升序排序
//        Collections.sort(list);

        //public static void reverse(List<?>tist):反转指定列表中元素的顺序
//        Collections.reverse(list);

        //public static void shuffle(List<?>List):使用默认的随机源随机排列指定的列表
        Collections.shuffle(list);

        System.out.println(list);
    }
}
```

### 案例：ArrayList存储学生对象并排序

![](https://github.com/Continuers/Java/blob/main/picture/225.png)

```java
package cn.itrs8;

public class Student {
    private String name;
    private int age;

    public Student() {}

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}
```

```java
package cn.itrs8;

import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
/*
    需求：
        Arraylist存储学生对象,使用 Collections对 Arraylist进行排序
        要求:按照年龄从小到大排序,年龄相同时,按照姓名的字母顺序排序
 */
public class CollectionsDemo2 {
    public static void main(String[] args) {
        ArrayList<Student> array = new ArrayList<Student>();

        Student s1 = new Student("java", 100);
        Student s2 = new Student("javaweb", 99);
        Student s3 = new Student("javaee", 98);
        Student s4 = new Student("javase",97);

        array.add(s1);
        array.add(s2);
        array.add(s3);
        array.add(s4);

        //使用Collections对ArrayList集合排序
        //sort (List<T> list, Comparator<? super T> c)
        Collections.sort(array, new Comparator<Student>() {
            @Override
            public int compare(Student s1, Student s2) {
                int num = s1.getAge()- s2.getAge();
                int num2 = num ==0?s1.getName().compareTo(s2.getName()):num;
                return num2;
            }
        });

        //遍历集合
        for (Student s:array){
            System.out.println(s.getName()+","+s.getAge());
        }
    }
}
```



### 案例：模拟斗地主

![](https://github.com/Continuers/Java/blob/main/picture/226.png)

```java
package cn.itrs9;

import java.util.ArrayList;
import java.util.Collections;

/*
    需求
        通过程序实现斗地王过程中的洗牌,发牌和看牌
    思路
        1:创建一个牌盒,也就是定义一个集合对象,用 Arraylist集合实现
        2:任牌盒里面装牌
        3:洗牌,也就是把牌打撤,用 Collections的 shuffle()方法实现
        4:发牌,也就是遍历集合,给三个玩家发牌
        5:看牌,也就是三个玩家分别历自己的牌
 */
public class PokerDemo {
    public static void main(String[] args) {
        //创建一个牌盒,也就是定义一个集合对象,用 Arraylist集合实现
        ArrayList<String> array = new ArrayList<String>();

        //任牌盒里面装牌
        /*
            ♦2，3，4，...k,A
            ♣2...
            ♥2...
            ♠2...
            大小王
         */
        //定义花色数组
        String[] colors = {"♦", "♣", "♥", "♠"};
        //定义点数数组
        String[] numbers = {"2", "3", "4", "5", "6", "7", "8", "9", "10", "J", "Q", "K", "A"};
        for (String color : colors) {
            for (String number : numbers) {
                array.add(color + number);
            }
        }
        array.add("小王");
        array.add("大王");

        //洗牌,也就是把牌打撤,用 Collections的 shuffle()方法实现
        Collections.shuffle(array);

//        System.out.println(array);

        //发牌,也就是遍历集合,给三个玩家发牌
        ArrayList<String> iArray = new ArrayList<String>();
        ArrayList<String> mhtArray = new ArrayList<String>();
        ArrayList<String> myArray = new ArrayList<String>();
        ArrayList<String> dpArray = new ArrayList<String>();

        for (int i = 0; i < array.size(); i++) {
            String poker = array.get(i);

            if (i >= array.size() - 3) {
                dpArray.add(poker);
            } else if (i % 3 == 0) {
                iArray.add(poker);
            } else if (i % 3 == 1) {
                mhtArray.add(poker);
            } else if (i % 3 == 2) {
                myArray.add(poker);
            }
        }

        //看牌,也就是三个玩家分别历自己的牌
        lookPoker("我",iArray);
        lookPoker("马化腾",mhtArray);
        lookPoker("马云",myArray);
        lookPoker("底牌",dpArray);

    }

    //看牌的方法
    public static void lookPoker(String name,ArrayList<String> array){
        System.out.println(name+"的牌是：");
        for (String poker : array){
            System.out.print(poker+" ");
        }
        System.out.println();
    }
}
```



### 案例：模拟斗地主升级版

![](https://github.com/Continuers/Java/blob/main/picture/227.png)

![](https://github.com/Continuers/Java/blob/main/picture/228.png)

```java
package cn.itrs9;

import java.util.ArrayList;
import java.util.Collections;
import java.util.HashMap;
import java.util.TreeSet;

/*
    需求:
        通过程序实现斗地主过程中的洗牌,发牌和看牌。要求:对牌进行排序
    思路
        1:创建 Hashmap,键是编号,值是牌
        2:创建 Arraylist,存储编号
        3:创建花色数组和点数数组
        4:从开始往 Hashmap里面存储编号,并存储对应的牌。同时往 Arraylist里面存储编号
        5:洗牌(冼的是编号),用 Collections的 shuffle()方法实现
        6:发牌(发的也是编号,为了保证编号是排序的,创建 Treeset集合接收)
        7:定义方法看牌(遍历 Treeset集合,获取编号,到 Hashmap集合找对应的牌
        8:调用看牌方法
 */
public class PokerDemo2 {
    public static void main(String[] args) {
        //创建 Hashmap,键是编号,值是牌
        HashMap<Integer, String> hm = new HashMap<Integer, String>();

        //创建 Arraylist,存储编号
        ArrayList<Integer> array = new ArrayList<Integer>();

        //创建花色数组和点数数组
        String[] colors = {"♦", "♣", "♥", "♠"};
        String[] numbers = {"3", "4", "5", "6", "7", "8", "9", "10", "J", "Q", "K", "A", "2"};

        //从开始往 Hashmap里面存储编号,并存储对应的牌。同时往 Arraylist里面存储编号
        int index = 0;

        for (String number : numbers) {
            for (String color : colors) {
                hm.put(index, color + number);
                array.add(index);
                index++;
            }
        }
        hm.put(index, "小王");
        array.add(index);
        index++;
        hm.put(index, "大王");
        array.add(index);

        //洗牌(冼的是编号),用 Collections的 shuffle()方法实现
        Collections.shuffle(array);

        //发牌(发的也是编号,为了保证编号是排序的,创建 Treeset集合接收)
        TreeSet<Integer> iSet = new TreeSet<Integer>();
        TreeSet<Integer> mhtSet = new TreeSet<Integer>();
        TreeSet<Integer> mySet = new TreeSet<Integer>();
        TreeSet<Integer> dpSet = new TreeSet<Integer>();

        for (int i = 0; i < array.size(); i++) {
            int x = array.get(i);
            if (i >= array.size() - 3) {
                dpSet.add(x);
            } else if (i % 3 == 0) {
                iSet.add(x);
            } else if (i % 3 == 1) {
                mhtSet.add(x);
            } else if (i % 3 == 2) {
                mySet.add(x);
            }
        }

        //调用看牌方法
        lookPoker("我",iSet,hm);
        lookPoker("马化腾",mhtSet,hm);
        lookPoker("马云",mySet,hm);
        lookPoker("底牌",dpSet,hm);
    }

    //定义方法看牌(遍历 Treeset集合,获取编号,到 Hashmap集合找对应的牌
    public static void lookPoker(String name,TreeSet<Integer> ts, HashMap<Integer,String> hm){
        System.out.println(name+"的牌是：");
        for (Integer key : ts){
            String poker = hm.get(key);
            System.out.print(poker+" ");
        }
        System.out.println();
    }
}
```

# 31.IO流

## 1.File

### 1.File 类概述和构造方法

![](https://github.com/Continuers/Java/blob/main/picture/229.png)

```java
package io.itrs1;

import java.io.File;

/*
    FiLe:文件和目录路径名的抽象表示
        1:文件和目录是可以通过FiLe封装成对象的
        2:对于Fie而言,其封装的并不是一个真正存在的文件,仅仅是一个路径名而已。它可以是存在的,也可以是不存在的。
            将来是要通过具体的操作把这个路径的内容转换为具体存在的

    构造方法:
        FiLe( String pathname):通过将给定的路径名字符串转换为抽象路径名来创建新的 File实例。
        FiLe( String parent, String child):从父路径名字符串和子路径名字符串创建新的 File实例。
        File( File parent, String child):从父抽象路径名和子路径名字符串创建新的 File实例。
 */
public class FileDemo {
    public static void main(String[] args) {
        //FiLe( String pathname):通过将给定的路径名字符串转换为抽象路径名来创建新的 File实例。
        File f1 = new File("D:\\java\\java.txt");
        System.out.println(f1);     //D:\java\java.txt

        //FiLe( String parent, String child):从父路径名字符串和子路径名字符串创建新的 File实例。
        File f2 = new File("D:\\java","java.txt");
        System.out.println(f2);     //D:\java\java.txt

        //File( File parent, String child):从父抽象路径名和子路径名字符串创建新的 File实例。
        File f3 = new File("D:\\java");
        File f4 = new File(f3,"java.txt");
        System.out.println(f4);     //D:\java\java.txt

    }
}
```

### 2.File 类创建功能

![](https://github.com/Continuers/Java/blob/main/picture/230.png)

```java
package io.itrs1;

import java.io.File;
import java.io.IOException;
/*
    FiLe类创建功能
        public boolean createNewFile():当具有该名称的文件不存在时,创建一个由该抽象路径名命名的新空文件
            如果文件不存在，就创建文件，并返回true
            如果文件存在，就不创建文件，并返回false

        public boolean mkdir():创建由此抽象路径名命名的目录
            如果目录不存在，就创建目录，并返回true
            如果目录存在，就不创建目录，并返回false

        public boolean mkdirs():创建由此抽象路径名命名的目录,包括任何必需但不存在的父目录
            如果目录不存在，就创建目录，并返回true
            如果目录存在，就不创建目录，并返回false
 */
public class FileDemo2 {
    public static void main(String[] args) throws IOException {
        //需求1:我要在 D:\\java 目录下创建一个文件java.txt
        File f1 = new File("D:\\java\\java.txt");
        System.out.println(f1.createNewFile());
        System.out.println();

        //需求2,我要在 D:\\java 目录下创建一个目录 JavaSE
        File f2 = new File("D:\\java\\JavaSE");
        System.out.println(f2.mkdir());
        System.out.println();

        // 需求3:我要在 D:\\java 目录下创建一个多级目录 JavaWeb\\HTML
        File f3 = new File("D:\\java\\JavaWeb\\HTML");
//        System.out.println(f3.mkdir());
        System.out.println(f3.mkdirs());
        System.out.println();

        // 需求4:我要在 D:\\java 目录下创建一个文件 Javase.txt
        File f4 = new File("D:\\java\\javase.txt");
//        System.out.println(f4.mkdir());       //创建了个名为 Javase.txt 的文件夹
        System.out.println(f4.createNewFile());
    }
}
```



### 3.File 类删除功能

![](https://github.com/Continuers/Java/blob/main/picture/231.png)

```java
package io.itrs1;

import java.io.File;
import java.io.IOException;

public class FileDemo3 {
    public static void main(String[] args) throws IOException {
//        File f1 = new File("D:\\java\\java.txt");
        //需求1：在当前模块目录下创建java.txt文件
        File f1 = new File("myCollection\\java.txt");
//        System.out.println(f1.createNewFile());

        //需求2：删除当前模块目录下创建java.txt文件
//        System.out.println(f1.delete());
        System.out.println();

        //需求3：在当前模块目录下创建 itcast 目录
        File f2 = new File("myCollection\\itcast");
//        System.out.println(f2.mkdir());

        //需求4：删除当前模块目录下的 itcast 目录
//        System.out.println(f2.delete());
        System.out.println();

        //需求5：在当前模块目录下创建一个目录 itcast，然后在该目录下创建一个文件java.txt
        File f3 = new File("myCollection\\itcast");
//        System.out.println(f3.mkdir());
        File f4 = new File("myCollection\\itcast\\java.txt");
//        System.out.println(f4.createNewFile());

        //需求6：删除当前模块下的目录 itcast
        System.out.println(f4.delete());
        System.out.println(f3.delete());

    }
}
```



### 4.File 类判断和获取功能

![](https://github.com/Continuers/Java/blob/main/picture/232.png)

```java
package io.itrs1;

import java.io.File;

public class FileDemo4 {
    public static void main(String[] args) {
        File f = new File("D:\\java\\java.txt");

//        public boolean isDirectory(),测试此抽象路径名表示的 File是否为目录
//        public boolean isFile():测试此抽象路径名表示的 File 是否为文件
//        public boolean exists():测试此抽象路径名表示的 File是否存在
        System.out.println(f.isDirectory());
        System.out.println(f.isFile());
        System.out.println(f.exists());

//        public String getAbsolutePath(),返回此抽象路径名的绝对路径名字符串
//        public String getPath():将此抽象路径名转换为路径名字符串
//        public String getName(),返国由此抽象路径名表示的文件或目录的名称
        System.out.println(f.getAbsolutePath());
        System.out.println(f.getPath());
        System.out.println(f.getName());
        System.out.println();

//        public String[] list()返回此抽象路径名表示的目录中的文件和目录的名称字符串数组
//        public File[] ListFiles(),返回此抽象路径名表示的目录中的文件和目录的 File对象数组
        File f2 = new File("D:\\java");

        String[] strArray = f2.list();
        for (String str : strArray){
            System.out.println(str);
        }
        System.out.println();

        File[] fileArray = f2.listFiles();
        for (File file : fileArray){
//            System.out.println(file);
//            System.out.println(file.getName());
            if (file.isFile()){
                System.out.println(file.getName());
            }
        }
    }
}
```

### 5.递归

![](https://github.com/Continuers/Java/blob/main/picture/233.png)

```java
package io.itrs2;

/*
    递归概述:
        以编程的角度来看,递归指的是方法定义中调用方法本身的现象
 */
public class DiGuiDemo {
    public static void main(String[] args) {
        //回顾不死神兔可题,求第20个月兔子的对数
        //每个月的免子对数:1,1,2,3,5,8,...
        int[] arr = new int [20];

        arr[0] = 1;
        arr[1] = 1;

        for (int i= 2;i< arr.length;i++){
            arr[i] = arr[i-1]+arr[i-2];
        }
        System.out.println(arr[19]);
        System.out.println(f(20));
    }
    /*
        递归解决问题,首先就是要定义一个方法
            定义一个方法 f(n):表示第 n 个月的兔子对数
            那么,第 n-1个月的兔子对数该如何表示呢?f(n-1)
            同理,第 n-2个月的兔子对数该如何表示呢?f(n-2)
     */
    public static int f(int n){
        if (n==1||n==2) {
            return 1;
        }else {
            return f(n - 1) + f(n - 2);
        }
    }




}
```

### 案例：递归求阶乘

![](https://github.com/Continuers/Java/blob/main/picture/234.png)

```java
package io.itrs2;

public class DiGuiDemo2 {
    public static void main(String[] args) {
        int result = jc(5);
        System.out.println("阶乘是："+result);
    }

    //定义一个方法,用于递归求阶乘,参数为一个int类型的变量
    public static int jc(int n){
        //在方法内部判断该变量的值是否是1
        if (n==1){
            //是:返回1
            return 1;
        }else {
            //不是:返回n*(n-1)!
            return n*jc(n-1);
        }
    }
}
```

### 案例：遍历目录

![](https://github.com/Continuers/Java/blob/main/picture/235.png)

```java
package io.itrs2;

import java.io.File;

/*
    根据给定的路径创建一个File对象
    定义一个方法,用于获取给定目录下的所有内容,参数为第1步创建的File对象
    获取给定的File目录下所有的文件或者目录的File数组
    遍历该File数组,得到每一个File对象
    判断该File对象是否是目录
        是:递归调用
        不是:获取绝对路径输出在控制台
    调用方法
 */
public class DiGuiDemo3 {
    public static void main(String[] args) {
        //根据给定的路径创建一个File对象
        File srcFile = new File("D:\\java");

        getAllFilePath(srcFile);
    }
    //定义一个方法,用于获取给定目录下的所有内容,参数为第1步创建的File对象
    public static void getAllFilePath(File srcFile){
        File[] fileArray = srcFile.listFiles();
        //遍历该File数组,得到每一个File对象
        if (fileArray != null){
            for (File file:fileArray){
                //判断该File对象是否是目录
                if (file.isDirectory()){
                    //是:递归调用
                    getAllFilePath(file);
                }else {
                    //不是:获取绝对路径输出在控制台
                    System.out.println(file.getAbsolutePath());
                }
            }
        }
    }
}
```



## 2.字节流

### 1.IO流概述和分类

![](https://github.com/Continuers/Java/blob/main/picture/236.png)

![](https://github.com/Continuers/Java/blob/main/picture/237.png)

![](https://github.com/Continuers/Java/blob/main/picture/238.png)



### 2.字节流写数据

![](https://github.com/Continuers/Java/blob/main/picture/239.png)

```java
package io.itrs3;

import java.io.FileOutputStream;
import java.io.IOException;

/*
    Fileoutputstream:文件输出流用于将数据写入FiLe
        Fileoutputstream( String name):创建文件输出流以指定的名称写入文件
 */
public class FileOutputStreamDemo {
    public static void main(String[] args) throws IOException {
        //Fileoutputstream( String name):创建文件输出流以指定的名称写入文件
        FileOutputStream fos = new FileOutputStream("myCollection\\fos.txt");

        /*
            做了三件事情:
                A:调用系统功能创建了文件
                B:创建了字节输出流对象
                C:让字节输出流对象指向创建好的文件
         */

        //void write (int b):将指定的字节写入此文件输出流
        fos.write(97);

        //最后都要释放资源
        //void close():关闭此文件输出流并释放与此流相关联的任何系统资源。
        fos.close();
    }
}
```



### 3.字节流写数据的3种方式

![](https://github.com/Continuers/Java/blob/main/picture/240.png)

```java
package io.itrs3;

import java.io.FileOutputStream;
import java.io.IOException;

/*
    构造方法:
        Fileoutputstream( String name):创建文件输出流以指定的名称写入文件
        Fileoutputstream( File file):创建文件输出流以写入由指定的FiLe对象表示的文件

    写数据的三种方式:
        void write(int b):将指定的字节写入此文件输出流
        一次写一个字节数据

        void write( byte[] b):将 b.Length字节从指定的字节数组写入此文件输出流
        一次写一个字节数组数据

        void write( byte[] b, int off, int Len):将Len字节从指定的字节数组开始,从偏移量of∫开始写入此文件输岀流
        一次写一个字节数组的部分数据
 */
public class FileOutputStreamDemo2 {
    public static void main(String[] args) throws IOException {
        //Fileoutputstream( String name):创建文件输出流以指定的名称写入文件
        FileOutputStream fos = new FileOutputStream("myCollection\\fos.txt");
        //new File(name)
//        FileOutputStream fos = new FileOutputStream(new File("myCollection\\fos.txt"));

        //Fileoutputstream( File file):创建文件输出流以写入由指定的FiLe对象表示的文件
//        File file = new File("myCollection\\fos.txt");
//        FileOutputStream fos2 = new FileOutputStream(file);
//        FileOutputStream fos2 = new FileOutputStream(new File("myCollection\\fos.txt"));

        //void write(int b):将指定的字节写入此文件输出流
//        fos.write(97);
//        fos.write(98);
//        fos.write(99);
//        fos.write(100);
//        fos.write(101);

        //void write( byte[] b):将 b.Length字节从指定的字节数组写入此文件输出流
//        byte[] bys = {97,98,99,100,101};
        //byte[] getBytes (): 返回字符串对应的字节数组
        byte[] bys = "abcde".getBytes();
//        fos.write(bys);

        //void write( byte[] b, int off, int Len):将Len字节从指定的字节数组开始,从偏移量of∫开始写入此文件输岀流
//        fos.write(bys,0,bys.length);
        fos.write(bys,1,3);     //bcd

        //释放资源
        fos.close();
    }
}
```



### 4.字节流写数据的两个小问题

![](https://github.com/Continuers/Java/blob/main/picture/241.png)

```java
package io.itrs3;

import java.io.FileOutputStream;
import java.io.IOException;

public class FileOutputStreamDemo3 {
    public static void main(String[] args) throws IOException {
        //创建字节流输出流对象
//        FileOutputStream fos = new FileOutputStream("myCollection\\fos.txt");
        
        FileOutputStream fos = new FileOutputStream("myCollection\\fos.txt",true);

        //写数据
        for (int i = 0;i<10;i++){
            fos.write("hello".getBytes());
            fos.write("\n".getBytes());
        }

        //释放资源
        fos.close();
    }
}
```

### 5.字节流写数据异常处理

![](https://github.com/Continuers/Java/blob/main/picture/242.png)

```java
package io.itrs3;

import java.io.FileOutputStream;
import java.io.IOException;

public class FileOutputStreamDemo4 {
    public static void main(String[] args) {
        FileOutputStream fos = null;
        try {
            fos = new FileOutputStream("D:\\java\\fos.txt");
            fos.write("hello".getBytes());
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (fos != null) {
                try {
                    fos.close();
                } catch (IOException e) {
                    e.printStackTrace();
                }
            }
        }
    }
}
```

### 6.字节流读数据(一次读一个字节数据)

![](https://github.com/Continuers/Java/blob/main/picture/243.png)

```java
package io.itrs3;

import java.io.FileInputStream;
import java.io.IOException;

public class FileInputStreamDemo1 {
    public static void main(String[] args) throws IOException {
        //创建字节输入流对象
        //FileInputStream(String name)
        FileInputStream fis = new FileInputStream("myCollection\\fos.txt");

        //调用字节输入流对象的读数据方法
        //int read(): 从该输入流读取一个字节的数据
/*

        //第一次读取数据
        int by = fis.read();
        System.out.println(by);
        System.out.println((char) by);

        //第二次读取数据
        by = fis.read();
        System.out.println(by);
        System.out.println((char) by);

        //再多读取俩次
        by = fis.read();
        System.out.println(by);
        by = fis.read();
        System.out.println(by);

        //如果达到文件的末尾， -1
*/
        /*
        int by = fis.read();
        while (by != -1){
            System.out.print((char) by);
            by = fis.read();
        }
*/
        //优化上面的程序
        int by;
        /*
            fis.read():读数据
            by = fis.read(): 把读取到的数据赋值给by
            by != -1:判断读取到的数据是否是-1
         */
        while ((by = fis.read()) != -1){
            System.out.print((char) by);
        }

        //释放资源
        fis.close();

    }
}
```

![](https://github.com/Continuers/Java/blob/main/picture/246.png)

```java
package io.itrs3;

import java.io.FileInputStream;
import java.io.IOException;

public class FileInputStreamDemo2 {
    public static void main(String[] args) throws IOException {
        FileInputStream fis = new FileInputStream("myCollection\\fos.txt");

        //调用字节输入流对象的读数据方法
        //int read(byte[] b):从该输入流读取最多 b.Length个字节的数据到一个字节数组
        /*
        byte[] bys= new byte[5];

        //第一次读取数据
        int len = fis.read(bys);
        System.out.println(len);
        //String (byte[] bytes)
//        System.out.println(new String(bys));
        System.out.println(new String(bys,0,len));

        //第二次读取数据
        len = fis.read(bys);
        System.out.println(len);
//        System.out.println(new String(bys));
        System.out.println(new String(bys,0,len));

        //第三次读取数据
        len = fis.read(bys);
        System.out.println(len);
        System.out.println(new String(bys,0,len));

        //再多读取两次
        len = fis.read(bys);
        System.out.println(len);
        len = fis.read(bys);
        System.out.println(len);
        */
        /*
            hello
            world

            第一次：hello
            第二次：\nworl
            第三次：d\norl
         */

        byte[] bys = new byte[1024];    //1024及其整数倍
        int len;
        while ((len = fis.read(bys)) != -1) {
            System.out.println(new String(bys, 0, len));
        }

        //释放资源
        fis.close();

    }
}
```



### 案例：复制文本文件

![](https://github.com/Continuers/Java/blob/main/picture/244.png)

![](https://github.com/Continuers/Java/blob/main/picture/245.png)

```java
package io.itrs3;

import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;

public class CopyTxtDemo {
    public static void main(String[] args) throws IOException {
        //根据数据源创建字节输入流对象
        FileInputStream fis = new FileInputStream("D:\\java\\java.txt");
        //根据目的地创建字节输出流对象
        FileOutputStream fos = new FileOutputStream("myCollection\\java.txt");

        //读写数据，复制文本文件(一次读取一个字节，一次写入一个字节)
        int by;
        while ((by=fis.read()) != -1)/*by=fis.read()这里一定要记得加个括号*/ {
            fos.write(by);
        }

        //释放资源
        fos.close();
        fis.close();
    }
}
```



### 案例： 复制图片

![](https://github.com/Continuers/Java/blob/main/picture/247.png)

```java
package io.itrs3;

import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;

/*
    1:根据数据源创建字节输入流对象
    2:根据目的地创建字节输出流对象
    3:读写数据,复制图片(一次读取一个字节数组,一次写入一个字节数组
    4:释放资源
 */
public class CopyJpgDemo {
    public static void main(String[] args) throws IOException {
        //根据数据源创建字节输入流对象
        FileInputStream fis = new FileInputStream("D:\\java\\fl.jpg");	//被复制图片的路径
        //根据目的地创建字节输出流对象
        FileOutputStream fos = new FileOutputStream("myCollection\\fl.jpg"); //复制到当前目录的路径

        //读写数据,复制图片(一次读取一个字节数组,一次写入一个字节数组)
        byte[] bys = new byte[1024];
        int len;
        while((len = fis.read(bys))!=-1){
            fos.write(bys,0,len);
        }
        
        //释放资源
        fis.close();
        fos.close();
    }
}
```



### 7.字节缓冲流

![](https://github.com/Continuers/Java/blob/main/picture/248.png)

```java
package io.itrs4;

import java.io.BufferedInputStream;
import java.io.FileInputStream;
import java.io.IOException;

/*
    字节缓冲流:
        Bufferoutputstream
        Bufferedinputstream

    构造方法:
        字节缓冲输出流: Bufferedoutputstream( OutputStream out)
        字节缓冲输入流: Bufferedinputstream( InputStream in)
 */
public class BufferStreamDemo {
    public static void main(String[] args) throws IOException {
        //字节缓冲输出流: Bufferedoutputstream( OutputStream out)
//        FileOutputStream fos = new FileOutputStream("myCollection\\bos.txt");
//        BufferedOutputStream bos = new BufferedOutputStream(fos);
        /*
        BufferedOutputStream bos = new BufferedOutputStream(new FileOutputStream("myCollection\\bos.txt"));
        //写数据
        bos.write("hello\r\n".getBytes());
        bos.write("world\r\n".getBytes());

        //释放资源
        bos.close();
        */

        //字节缓冲输入流: Bufferedinputstream( InputStream in)
        try (BufferedInputStream bis = new BufferedInputStream(new FileInputStream("myCollection\\bos.txt"))) {

            //一次读取一个字节数据
//            int by;
//            while ((by = bis.read()) != -1) {
//                System.out.print((char) by);
//            }

            //一次读取一个字节数组数据
            byte[] bys = new byte[1024];
            int len;
            while ((len = bis.read(bys))!=-1){
                System.out.print(new String(bys,0,len));
            }

            //释放资源
            bis.close();
        }

    }
}
```



### 案例：复制视频

![](https://github.com/Continuers/Java/blob/main/picture/249.png)

```java
package io.itrs4;

import java.io.*;

/*
    四种方式实现复制视频,并记录每种方式复制视频的时间
        1:基本字节流一次读写一个字节         //共耗时：45333毫秒
        2:基本字节流一次读写一个字节数组      //共耗时：64毫秒
        3:字节缓冲流一次读写一个字节         //共耗时：74毫秒
        4:字节缓冲流一次读写一个字节数组      //共耗时：18毫秒
 */
public class CopyAviDemo {
    public static void main(String[] args) throws IOException {
        //记录开始时间
        long startTime = System.currentTimeMillis();

        //复制视频
//        method1();
//        method2();
//        method3();
        method4();


        //记录结束时间
        long endTime = System.currentTimeMillis();
        System.out.println("共耗时："+(endTime-startTime)+"毫秒");

    }

    //1.基本字节流一次读写一个字节
    public static void method1() throws IOException {
        FileInputStream fis = new FileInputStream("D:\\java\\zj.avi");
        FileOutputStream fos = new FileOutputStream("myCollection\\zj.avi");

        int by;
        while ((by = fis.read())!=-1){
            fos.write(by);
        }

        fos.close();
        fis.close();
    }

    //2.基本字节流一次读写一个字节数组
    public static void method2() throws IOException {
        FileInputStream fis = new FileInputStream("D:\\java\\zj.avi");
        FileOutputStream fos = new FileOutputStream("myCollection\\zj.avi");

        byte[] bys = new byte[1024];
        int len;
        while ((len = fis.read(bys))!=-1){
            fos.write(bys,0,len);
        }

        fos.close();
        fis.close();
    }

    //3.字节缓冲流一次读写一个字节
    public static void method3() throws IOException{
        BufferedInputStream bis = new BufferedInputStream(new FileInputStream("D:\\java\\zj.avi"));
        BufferedOutputStream bos = new BufferedOutputStream(new FileOutputStream("myCollection\\zj.avi"));

        int by;
        while ((by = bis.read())!=-1){
            bos.write(by);
        }
        bos.close();
        bis.close();
    }

    //4.字节缓冲流一次读写一个字节数组
    public static void method4() throws IOException{
        BufferedInputStream bis = new BufferedInputStream(new FileInputStream("D:\\java\\zj.avi"));
        BufferedOutputStream bos = new BufferedOutputStream(new FileOutputStream("myCollection\\zj.avi"));

        byte[] bys = new byte[1024];
        int len;
        while ((len = bis.read(bys))!=-1){
            bos.write(bys,0,len);
        }

        bos.close();
        bis.close();
    }
}
```



## 3.字符流

### 1.为什么会出现字符流

![](https://github.com/Continuers/Java/blob/main/picture/250.png)

```java
package io.itrs4;

import java.io.IOException;
import java.util.Arrays;

/*
    一个汉字存储：
        如果是GBK编码，占用2个字节
        如果是UTF-8编码，占用3个字节
 */
public class FileInputStreamDemo {
    public static void main(String[] args) throws IOException {
        /*
        FileInputStream fis = new FileInputStream("myCollection\\a.txt");

        int by;
        while ((by = fis.read())!=-1){
            System.out.print((char) by);
        }

        fis.close();
        */

//        String s = "abc";       //[97, 98, 99]
        String s = "中国";        //[-28, -72, -83, -27, -101, -67]

//        byte[] bys = s.getBytes();
//        byte[] bys = s.getBytes("UTF-8");   //[-28, -72, -83, -27, -101, -67]
        byte[] bys = s.getBytes("GBK");   //[-42, -48, -71, -6]

        System.out.println(Arrays.toString(bys));
    }
}
```



### 2.编码表

![](https://github.com/Continuers/Java/blob/main/picture/251.png)

注：win 10 系统自带计算器有程序员选项

![](https://github.com/Continuers/Java/blob/main/picture/252.png)

![](https://github.com/Continuers/Java/blob/main/picture/253.png)

![](https://github.com/Continuers/Java/blob/main/picture/254.png)

![](https://github.com/Continuers/Java/blob/main/picture/255.png)



### 3.字符串中的编码解码问题

![](https://github.com/Continuers/Java/blob/main/picture/256.png)

```java
package io.itrs4;

import java.io.UnsupportedEncodingException;
import java.util.Arrays;

/*
    编码：
        byte[] getbytes():使用平台的默认字符集将该 String编码为一系列字节,将结果存储到新的字节数组中
        byte[] getbytes( String charsetname):使用指定的字符集将该 String编码为一系列字节,将结果存储到新的字节数组中
    解码：
        String(byte[ bytes):通过使用平台的默认宇符集解码指定的字节数组来构造新的 string
        string( byte[] bytes, String charsetname):通过指定的字符集解码指定的字节数组来构造新的 String
 */
public class StringDemo {
    public static void main(String[] args) throws UnsupportedEncodingException {
        //定义一个字符串
        String s = "中国";

        //byte[] getbytes():使用平台的默认字符集将该 String编码为一系列字节,将结果存储到新的字节数组中
//        byte[] bys = s.getBytes();      //[-28, -72, -83, -27, -101, -67]
        //byte[] getbytes( String charsetname):使用指定的字符集将该 String编码为一系列字节,将结果存储到新的字节数组中
//        byte[] bys = s.getBytes("UTF-8");   //[-28, -72, -83, -27, -101, -67]
        byte[] bys = s.getBytes("GBK");   //[-42, -48, -71, -6]

        System.out.println(Arrays.toString(bys));

        //String(byte[ bytes):通过使用平台的默认宇符集解码指定的字节数组来构造新的 string
//        String ss = new String(bys);

        //string( byte[] bytes, String charsetname):通过指定的字符集解码指定的字节数组来构造新的 String
//        String ss = new String(bys,"UTF-8");
        String ss = new String(bys,"GBK");
        System.out.println(ss);
    }
}
```



### 4.字符流中的编码解码问题

![](https://github.com/Continuers/Java/blob/main/picture/257.png)

```java
package io.itrs4;

import java.io.*;

/*
    Inputstreamreader:是从字节流到字符流的桥梁
        它读取字节,并使用指定的编码将其解码为字符
        它使用的字符集可以由名称指定,也可以被明确指定,或者可以接受平台的默认字符集

    Outputstreamwriter:是从字符流到字节流的桥粱
        是从字符流到字节流的桥粱,使用指定的编码将写入的字符编码为字节
        它使用的字符集可以由名称指定,也可以被明确指定,或者可以接受平台的默认字符集
 */
public class ConversionStreamDemo {
    public static void main(String[] args) throws IOException {
//        OutputStreamwriter( Outputstream out)创建一个使用默认字符编码的 Outputstreamlriter。
//        Outputstreamwriter( Outputstream out, String charsetname)创建一个使用命名字符集的 Outputstreamwriter。
//        FileOutputStream fos = new FileOutputStream("myCollection\\osw.txt");
//        OutputStreamWriter osw = new OutputStreamWriter(fos);
//        OutputStreamWriter osw = new OutputStreamWriter(new FileOutputStream("myCollection\\osw.txt"));
//        OutputStreamWriter osw = new OutputStreamWriter(new FileOutputStream("myCollection\\osw.txt"),"UTF-8");
        OutputStreamWriter osw = new OutputStreamWriter(new FileOutputStream("myCollection\\osw.txt"), "GBK");
        osw.write("中国");
        osw.close();

//        InputStreamreader( Inputstream in)创建一个使用默认宇符集的 Inputstreamreader
//        InputStreamreader( Inputstream in, String charsetname)创建一个使用命名宇符集的 Inputstreamreader
//        InputStreamReader isr = new InputStreamReader(new FileInputStream("myCollection\\osw.txt"));
        InputStreamReader isr = new InputStreamReader(new FileInputStream("myCollection\\osw.txt"), "GBK");

        //一次读取一个字符数据
        int ch;
        while ((ch = isr.read()) != -1) {
            System.out.print((char) ch);
        }
        isr.close();

    }
}
```



### 5.字符流写数据的5种方式

![](https://github.com/Continuers/Java/blob/main/picture/258.png)

![](https://github.com/Continuers/Java/blob/main/picture/259.png)

```java
package io.itrs4;

import java.io.FileOutputStream;
import java.io.IOException;
import java.io.OutputStreamWriter;

public class OutputStreamWriterDemo {
    public static void main(String[] args) throws IOException {
        //Outputstreamwriter( Output stream out):创建一个使用默认字符编码的 Outputstreamwriter
        OutputStreamWriter osw = new OutputStreamWriter(new FileOutputStream("myCollection\\osw.txt"));

        //void write(intc):写一个字符
//        osw.write(97);
//        //void flush(): 刷新流
//        osw.flush();
//        osw.write(98);
//        osw.flush();
//        osw.write(99);

        //void write(char[)cbuf):写入一个字符数组
        char[] chs = {'a','b','c','d'};
//        osw.write(chs);

        //void write( chart cbuf, int off, int Len):写入字符数组的一部分
//        osw.write(chs,0,chs.length);
//        osw.write(chs,1,3);     //bcd

        //void write( String str):写一个字符串
//        osw.write("abcde");

        //void write( String str, int off, int Len):写一个字符串的一部分
//        osw.write("abcde",0,"abcde".length());
        osw.write("abcde",1,3);     //bcd

        //释放资源1
        osw.close();
//        osw.write(100);
    }
}
```

### 6.字符流读数据的2种方式

![](https://github.com/Continuers/Java/blob/main/picture/260.png)

```java
package io.itrs4;

import java.io.FileInputStream;
import java.io.IOException;
import java.io.InputStreamReader;

public class InputStreamReaderDemo {
    public static void main(String[] args) throws IOException {
        InputStreamReader isr = new InputStreamReader(new FileInputStream("myCollection\\osw.txt"));
//        InputStreamReader isr = new InputStreamReader(new FileInputStream("myCollection\\要复制的文件路径"));

        //int read (): 一次读一个字符数据
        /*
        int ch;
        while ((ch = isr.read())!=-1){
            System.out.print((char) ch);
        }
        */

        //int read(char[] cbuf): 一次读一个字符数组数据
        char[] chs = new char[1024];
        int len;
        while ((len = isr.read(chs))!=-1){
            System.out.println(new String(chs,0,len));
        }

        isr.close();
    }
}
```

### 案例：复制Java文件

![](https://github.com/Continuers/Java/blob/main/picture/261.png)

```java
package io.itrs4;

import java.io.*;

/*
    需求:
        把模块目录下的 Conversionstreamdemo,java复制到模块目录下的copy.java
 */
public class CopyJavaDemo {
    public static void main(String[] args) throws IOException {
        //根据数据源创建字符输入流对象
        InputStreamReader isr = new InputStreamReader(new FileInputStream("myCollection\\ConversionStreamDemo.java"));
        //根据目的地创建字符输出流对象
        OutputStreamWriter osw = new OutputStreamWriter(new FileOutputStream("myCollection\\Copy.java"));

        //读写数据,复制文件
        //一次读写一个字符数据
        /*
        int ch;
        while ((ch=isr.read())!=-1){
            osw.write(ch);
        }
        */
        //一次读写一个字符数组数据
        char[] chs = new char[1024];
        int len;
        while ((len = isr.read(chs))!=-1){
            osw.write(chs,0,len);
        }

        osw.close();
        isr.close();
    }
}
```



### 案例：复制Java文件(改进版)

![](https://github.com/Continuers/Java/blob/main/picture/262.png)

![](https://github.com/Continuers/Java/blob/main/picture/263.png)

```java
package io.itrs4;

import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;

public class CopyJavaDemo2 {
    public static void main(String[] args) throws IOException {
        //根据数据源创建字符输入流对象
        FileReader fr = new FileReader("myCollection\\ConversionStreamDemo.java");
        //根据目的地创建字符输出流对象
        FileWriter fw = new FileWriter("myCollection\\Copy.java");

        //读写数据,复制文件
        /*
        int ch;
        while ((ch=fr.read())!=-1){
            fw.write(ch);
        }
        */

        char[] chs = new char[1024];
        int len;
        while ((len=fr.read(chs))!=-1){
            fw.write(chs,0,len);
        }

        //释放资源
        fw.close();
        fr.close();
    }
}
```



### 7.字符缓冲流

![](https://github.com/Continuers/Java/blob/main/picture/264.png)

```java
package io.itrs4;

import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

/*
    字符缓冲流
        Bufferedwriter:将文本写入字符输出流,缓中字符,以提供单个字符,数组和字符串的高效写入,可以指定缓冲区大小,或者可以接受默认大小。默认值足够大,可用于大多数用途
        Buffered reader:从字符输λ流渎取文本,缓中字符,以提供字符,数组和行的高效读取,可以指定缓冲区大小,或者可以使用默认大小。默认值足够大,可用于大多数用途

    构造方法:
        BufferedWriter(Writer out)
        BufferedReader(Reader in)
 */
public class BufferedStreamDemo {
    public static void main(String[] args) throws IOException {
        //BufferedWriter(Writer out)
//        FileWriter fw = new FileWriter("myCollection\\bw.txt");
//        BufferedWriter bw = new BufferedWriter(fw);
//        BufferedWriter bw = new BufferedWriter(new FileWriter("myCollection\\bw.txt"));
//        bw.write("hello\n");
//        bw.write("world\n");
//        bw.close();

        //BufferedReader(Reader in)
        BufferedReader br = new BufferedReader(new FileReader("myCollection\\bw.txt"));

        //一次读一个字符数据
        /*
        int ch;
        while ((ch=br.read())!=-1){
            System.out.print((char) ch);
        }
        */
        //一次读取一个字符数组数据
        char[] chs = new char[1024];
        int len;
        while ((len = br.read(chs))!=-1){
            System.out.print(new String(chs,0,len));
        }
    }
}
```



### 案例：复制Java文件(字符缓冲流改进版)

![](https://github.com/Continuers/Java/blob/main/picture/265.png)

```java
package io.itrs4;

import java.io.*;

/*
    需求:
        把模块目录下的" Conversion Demo. java"复制到模块目录下的" Copy.java
 */
public class CopyJavaDemo3 {
    public static void main(String[] args) throws IOException {
        //①根据数据源创建字符缓冲输入流对象
        BufferedReader br = new BufferedReader(new FileReader("myCollection\\ConversionStreamDemo.java"));
        //②根据目的地创建字符缓冲输出流对象
        BufferedWriter bw = new BufferedWriter(new FileWriter("myCollection\\Copy.java"));

        //③读写数据,复制文件
        //一次读取一个字符数据
        /*
        int ch;
        while ((ch=br.read())!=-1){
            bw.write(ch);
        }
        */
        //一次读写一个字符数组数据
        char[] chs = new char[1024];
        int len;
        while ((len=br.read(chs))!=-1){
            bw.write(chs,0,len);
        }

        //④释放资源
        bw.close();
        br.close();
    }
}
```



### 8.字符缓冲流特有功能

![](https://github.com/Continuers/Java/blob/main/picture/266.png)

```java
package io.itrs4;

import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

/*
    Bufferedwriter
        void newline():写一行行分隔符,行分隔符字符串由系统属性定义

    BufferedReader
        public String readline0:读一行文字。
            结果包含行的内容的字符串,不包括任何行终止字符,如果流的结尾已经到达,则为null
 */
public class BufferdStreamDemo2 {
    public static void main(String[] args) throws IOException {
        /*
        //创建字符缓冲输出流
        BufferedWriter bw = new BufferedWriter(new FileWriter("myCollection\\bw.txt"));

        for (int i =0;i<10;i++){
            bw.write("hello"+i);
//            bw.write("\n");
            bw.newLine();       //换行
            bw.flush();
        }

        bw.close();
        */

        //创建字符缓冲输入流
        BufferedReader br = new BufferedReader(new FileReader("myCollection\\bw.txt"));

        //readline():读一行文字。不读取换行符号
        /*
        //第一次读取数据
        String line = br.readLine();
        System.out.println(line);

        //第二次读取数据
        line = br.readLine();
        System.out.println(line);

        line = br.readLine();
        System.out.println(line);
        */

        String line;
        while ((line=br.readLine())!=null){
            System.out.println(line);
        }
        br.close();

    }
}
```



### 案例：复制Java文件(字符缓冲流特有功能改进版)

![](https://github.com/Continuers/Java/blob/main/picture/267.png)

```java
package io.itrs4;

import java.io.*;

/*
    需求:
        把模块目录下的" ConversionStreamDemo.java”复制到模块目录下的" Copy. java
 */
public class CopyJavaDemo4 {
    public static void main(String[] args) throws IOException {
        //根据数据源创建字符缓冲输入流对象
        BufferedReader br = new BufferedReader(new FileReader("myCollection\\ConversionStreamDemo.java"));
        //根据目的地创建字符缓冲输出流对象
        BufferedWriter bw = new BufferedWriter(new FileWriter("myCollection\\Copy.java"));

        //读写数据,复制文件
        //使用字符缓冲流特有功能实现
        String line;
        while ((line= br.readLine())!=null){
            bw.write(line);
            bw.newLine();
            bw.flush();
        }

        //④释放资源
        bw.close();
        br.close();

    }
}
```

### 9.IO流小结

![](https://github.com/Continuers/Java/blob/main/picture/268.png)

![](https://github.com/Continuers/Java/blob/main/picture/269.png)



### 案例：集合到文件

![](https://github.com/Continuers/Java/blob/main/picture/270.png)

```java
package io.itrs4;

import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;
import java.util.ArrayList;

/*
    需求:
        把 Arraylist集合中的字符串数据写入到本文件。要求:每一个字符串元素作为文件中的行数据
 */
public class ArrayListToTxtDemo {
    public static void main(String[] args) throws IOException {
        //①创建 Arraylist集合
        ArrayList<String> array = new ArrayList<String>();

        //②往集合中存储字符串元素
        array.add("hello");
        array.add("world");
        array.add("java");

        //③创建字符缓冲输出流对象
        BufferedWriter bw = new BufferedWriter(new FileWriter("myCollection\\array.txt"));

        //④遍历集合,得到每一个字符串数据
        for (String s : array){
            //⑤调用字符缓冲输出流对象的方法写数据
            bw.write(s);
            bw.newLine();
            bw.flush();
        }

        //⑥释放资源
        bw.close();
    }
}
```



### 案例：文件到集合

![](https://github.com/Continuers/Java/blob/main/picture/271.png)

```java
package io.itrs4;

import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;
import java.util.ArrayList;

/*
    需求:
        把文本文件中的数据读取到集合中,并遍历集合。要求:文件中每-行数据是一个集合元素
 */
public class TxtToArrayListDemo {
    public static void main(String[] args) throws IOException {
        //①创建字符缓冲输入流刈象
        BufferedReader br = new BufferedReader(new FileReader("myCollection\\array.txt"));

        //②创建 Arraylist集合对象
        ArrayList<String> array = new ArrayList<String>();

        //③调用字符缓冲输入流对象的方法读数据
        String line;
        while ((line=br.readLine())!=null){
            //④把读取到的字符串数据存储到集合中
            array.add(line);
        }

        //⑤释放资源
        br.close();

        //⑥遍历集合
        for (String s : array){
            System.out.println(s);
        }
    }
}
```



### 案例：点名器

![](https://github.com/Continuers/Java/blob/main/picture/272.png)

```java
package io.itrs4;

import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;
import java.util.ArrayList;
import java.util.Random;

/*
    需求:
        我有一个文件里面存储了班级同学的姓名,每一个姓名占一行,要求通过程序实现随机点名器
        names.txt文件中存放名单
 */
public class CallNameDemo {
    public static void main(String[] args) throws IOException {
        //①创建字符缓冲输入流对象
        BufferedReader br = new BufferedReader(new FileReader("myCollection\\names.txt"));

        //②创建 Arraylist集合对象
        ArrayList<String> array = new ArrayList<String>();

        //③调用字符缓冲输入流对象的方法读数据
        String line;
        while ((line= br.readLine())!=null){
            //④把读取到的字符串数据存储到集合中
            array.add(line);
        }

        //⑤释放资源
        br.close();

        //⑥使用 Random产生一个随机数,随机数的范围在:[O,集合的长度)
        Random r = new Random();
        int index = r.nextInt(array.size());

        //⑦把第6步产生的随机数作为索引到 Arraylist堞集合中获取值
        String name = array.get(index);

        //⑧把第7步得到的数据输出在控制台
        System.out.println("幸运者是："+name);
    }
}
```



### 案例：集合到文件(改进版)

![](https://github.com/Continuers/Java/blob/main/picture/273.png)

```java
package io.itrs5;

public class Student {
    private String sid;
    private String name;
    private int age;
    private String address;

    public Student() {
    }

    public Student(String sid, String name, int age, String address) {
        this.sid = sid;
        this.name = name;
        this.age = age;
        this.address = address;
    }

    public String getSid() {
        return sid;
    }

    public void setSid(String sid) {
        this.sid = sid;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public String getAddress() {
        return address;
    }

    public void setAddress(String address) {
        this.address = address;
    }
}
```

```java
package io.itrs5;

import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;
import java.util.ArrayList;

/*
    需求:
        把 Arraylist集合中的学生数据写入到文本文件。要求:每一个学生对象的数据作为文件中的行数据
        格式:学号姓名年龄,居住地举例: thelma001,林青霞30西安
 */
public class ArrayListToFileDemo {
    public static void main(String[] args) throws IOException {
        //②创建 Arraylist集合
        ArrayList<Student> array = new ArrayList<Student>();

        //③创建学生对象
        Student s1 = new Student("itrs001", "马化腾", 40, "深圳");
        Student s2 = new Student("itrs002", "马云", 50, "杭州");
        Student s3 = new Student("itrs003", "雷军", 45, "中国");

        //④把学生对象添加到集合中
        array.add(s1);
        array.add(s2);
        array.add(s3);

        //⑤创建字符缓冲输出流对象
        BufferedWriter bw = new BufferedWriter(new FileWriter("myCollection\\Students.txt"));

        //⑥遍历集合,得到每一个学生对象
        for (Student s : array) {
            //⑦把学生对象的数据拼接成指定格式的字符串
            StringBuilder sb = new StringBuilder();
            sb.append(s.getSid()).append(",").append(s.getName()).append(",").append(s.getAge()).append(",").append(s.getAddress());

            //⑧调用字符缓冲输出流对象的方法写数据
            bw.write(sb.toString());
            bw.newLine();
            bw.flush();
        }

        //⑨释放资源
        bw.close();
    }
}
```



### 案例：文件到集合(改进版)

![](https://github.com/Continuers/Java/blob/main/picture/274.png)

```java
package io.itrs5;

import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;
import java.util.ArrayList;

/*
    需求:把文本文件中的数据读取到集合中,并遍历集合。
        要求:文件中每一行数据是一个学生对象的成员变量值
        举例: itheima001,林青霞,30,西安
 */
public class FileToArrayListDemo {
    public static void main(String[] args) throws IOException {
        //②创建字符缓冲输入流对象
        BufferedReader br = new BufferedReader(new FileReader("myCollection\\Students.txt"));

        //③创建 Arraylist集合对象
        ArrayList<Student> array = new ArrayList<Student>();

        //④调用字符缓冲输入流对象的方法读数据
        String line;
        while ((line=br.readLine())!=null){
            //⑤把读取到的字符串数据用split()进行分割,得到个字符串数组
            String[] strArray = line.split(",");

            //⑥创建学生对象
            Student s = new Student();
            //⑦把字符串数组中的每一个元素取出来对应的赋值给学生对象的成员变量值
            s.setSid(strArray[0]);
            s.setName(strArray[1]);
            s.setAge(Integer.parseInt(strArray[2]));
            s.setAddress(strArray[3]);

            //⑧把学生对象添加到集合
            array.add(s);
        }
        //⑨释放资源
        br.close();

        //⑩遍历集合
        for (Student s : array){
            System.out.println(s.getSid()+","+s.getName()+","+s.getAge()+","+s.getAddress());
        }
    }
}
```



### 案例：集合到文件(数据排序改进版)

![](https://github.com/Continuers/Java/blob/main/picture/275.png)

```java
package io.itrs6;

public class Student {
    private String name;
    private int chinese;
    private int math;
    private int english;

    public Student() {
    }

    public Student(String name, int chinese, int math, int english) {
        this.name = name;
        this.chinese = chinese;
        this.math = math;
        this.english = english;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getChinese() {
        return chinese;
    }

    public void setChinese(int chinese) {
        this.chinese = chinese;
    }

    public int getMath() {
        return math;
    }

    public void setMath(int math) {
        this.math = math;
    }

    public int getEnglish() {
        return english;
    }

    public void setEnglish(int english) {
        this.english = english;
    }

    public int getSum() {
        return this.chinese + this.math + this.english;
    }
}
```

```java
package io.itrs6;

import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;
import java.util.Comparator;
import java.util.Scanner;
import java.util.TreeSet;

/*
    需求:键盘录入5个学生信息(姓名,语文成绩,数学成绩,英语成绩)。要求按照成绩总分从高到低写入文本文件
        格式:姓名，语文成绩，数学成绩，英语成绩
 */
public class TreeSetToFileDemo {
    public static void main(String[] args) throws IOException {
        //②创建 Treeset集合,通过比较器排序进行排序
        TreeSet<Student> ts = new TreeSet<Student>(new Comparator<Student>() {
            @Override
            public int compare(Student s1, Student s2) {
                //按照成绩总分从高到低
                int num = s2.getSum()-s1.getSum();
                //次要条件
                int num2 = num == 0?s1.getChinese()-s2.getChinese():num;
                int num3 = num2==0? s1.getMath()-s2.getMath():num2;
                int num4 = num3==0? s1.getName().compareTo(s2.getName()):num3;
                return num4;
            }
        });

        //③键盘录入学生数据
        for (int i = 0;i<5;i++){
            Scanner sc = new Scanner(System.in);
            System.out.println("请录入第"+(i+1)+"个学生信息");
            System.out.print("姓名：");
            String name = sc.nextLine();
            System.out.print("语文成绩：");
            int chinese = sc.nextInt();
            System.out.print("数学成绩：");
            int math = sc.nextInt();
            System.out.print("英语成绩：");
            int english = sc.nextInt();

            //④创建学生对象,把键盘录入的数据对应赋值给学生对象的成员变量
            Student s = new Student();
            s.setName(name);
            s.setChinese(chinese);
            s.setMath(math);
            s.setEnglish(english);

            //⑤把学生对象添加到 Treeset集合
            ts.add(s);
        }

        //⑥创建字符缓冲输出流对象
        BufferedWriter bw = new BufferedWriter(new FileWriter("myCollection\\ts.txt"));

        //⑦遍历集合,得到每一个学生对象
        for (Student s : ts){
            //⑧把学生对象的数据拼接成指定格式的字符串
            StringBuilder sb = new StringBuilder();
            sb.append(s.getName()).append(",").append(s.getChinese()).append(",").append(s.getMath()).append(",").append(s.getEnglish()).append(",").append(s.getSum());

            //⑨调用字符缓冲输出流对象的方法写数据
            bw.write(sb.toString());
            bw.newLine();
            bw.flush();
        }
        //⑩释放资源
        bw.close();
    }
}
```



### 案例：复制单级文件夹

![](https://github.com/Continuers/Java/blob/main/picture/276.png)

```java
package io.itrs6;

import java.io.*;

/*
    需求:
        把E:\\itcast"这个文件夹复制到模块目录下
        由于文件不仅仅是文本文等文件,所以采用字节流复制文件
 */
public class CopyFolderDemo {
    public static void main(String[] args) throws IOException {
        //①创建数据源目录 File对象,路径是E:\\itcast
        File srcFolder = new File("D:\\java\\itcast");

        //②获取数据源目录 File对象的名称(itcast)
        String srcFolderName = srcFolder.getName();

        //③创建目的地目录 File对象,路径名是模块名+itcast组成 ( myCharstream\\itcast)
        File destFolder = new File("myCollection",srcFolderName);

        //④判断目的地目录对应的 File是否存在,如果不存在,就创建
        if (!destFolder.exists()){
            destFolder.mkdir();
        }

        //⑤获取数据源目录下所有文件的File数组
        File[] listFiles = srcFolder.listFiles();

        //⑥遍历 File数组,得到每一个File对象,该File对象,其实就是数据源文件
        for (File srcFile : listFiles){
            //数据源文件:E:\\itcast\\mn. jpg
            //⑦获取数据源文件Fie对象的名称( mn. Jpg)
            String srcFileName = srcFile.getName();
            //⑧创建目的地文件Fie对象,路径名是目的地目录+ mn. jpg组成( mycharstreamllitcast\\mn. jpg)
            File destFile = new File(destFolder,srcFileName);
            //⑨复制文件
            copyFile(srcFile,destFile);
        }
    }

    private static void copyFile(File srcFile, File destFile) throws IOException {
        BufferedInputStream bis = new BufferedInputStream(new FileInputStream(srcFile));
        BufferedOutputStream bos = new BufferedOutputStream(new FileOutputStream(destFile));

        byte[] bys = new byte[1024];
        int len;
        while ((len=bis.read(bys))!=-1){
            bos.write(bys,0,len);
        }

        bos.close();
        bis.close();
    }
}
```



### 案例：复制多级文件夹(懵)

![](https://github.com/Continuers/Java/blob/main/picture/277.png)

```java
package io.itrs6;

import java.io.*;

/*
    需求:
        把E:\\itcast复制到 F盘目录下
 */
public class CopyFolderDemo2 {
    public static void main(String[] args) throws IOException {
        //①创建数据源 File对象,路径是E:\\itcast
        File srcFile = new File("D:\\java\\itcast");
        //②创建目的地File对象,路径是F:\\
        File destFile = new File("D:\\");

        //③写方法实现文件夹的复制,参数为数据源 File对象和目的地File对象
        copyFolder(srcFile, destFile);
    }

    //复制文件夹
    private static void copyFolder(File srcFile, File destFile) throws IOException {
        //④判断数据源File是否是目录
        if (srcFile.isDirectory()) {
            //A在目的地下创建和数据源 File名称一样的目录
            String srcFileName = srcFile.getName();
            File newFolder = new File(destFile, srcFileName);    //D:\\itcast
            if (!newFolder.exists()) {
                newFolder.mkdir();
            }

            //B:获取数据源 File下所有文件或者目录的 File数组
            File[] fileArray = srcFile.listFiles();

            //C:遍历该 File数组,得到每一个 File对象
            for (File file : fileArray) {
                //D:把该 File作为数据源 File对象,递归调用复制文件夹的方法
                copyFolder(file, newFolder);
            }
        } else {
            //说明是文件,直接复制,用字节流
            File newFile = new File(destFile, srcFile.getName());
            copyFile(srcFile, newFile);
        }
    }

    //字节缓冲流复制文件
    private static void copyFile(File srcFile, File destFile) throws IOException{
        BufferedInputStream bis = new BufferedInputStream(new FileInputStream(srcFile));
        BufferedOutputStream bos = new BufferedOutputStream(new FileOutputStream(destFile));

        byte[] bys = new byte[1024];
        int len;
        while ((len=bis.read(bys))!=-1){
            bos.write(bys,0,len);
        }
        bos.close();
        bis.close();
    }
}
```



### 10.复制文件的异常处理

![](https://github.com/Continuers/Java/blob/main/picture/278.png)

```java
package io.itrs6;

import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;

public class CopyFileDemo {
    public static void main(String[] args) {

    }

    //JDK9后的改进方案
    private static void method4() throws IOException{
        FileReader fr = new FileReader("fr.txt");
        FileWriter fw = new FileWriter("fw.txt");
        try(fr;fw) {
            char[] chs = new char[1024];
            int len;
            while ((len=fr.read())!=-1){
                fw.write(chs,0,len);
            }
        } catch (IOException e){
            e.printStackTrace();
        }
    }

    //JDk7后的改进方案
    private static void method3() {
        try(FileReader fr = new FileReader("fr.txt");
            FileWriter fw = new FileWriter("fw.txt");) {
            char[] chs = new char[1024];
            int len;
            while ((len=fr.read())!=-1){
                fw.write(chs,0,len);
            }
        } catch (IOException e){
            e.printStackTrace();
        }
    }

    //try...catch...finally
    private static void method2(){
        FileReader fr = null;
        FileWriter fw = null;
        try {
            fr = new FileReader("fr.txt");
            fw = new FileWriter("fw.txt");

            char[] chs = new char[1024];
            int len;
            while ((len=fr.read())!=-1){
                fw.write(chs,0,len);
            }
        } catch (IOException e){
            e.printStackTrace();
        } finally {
            if (fw != null) {
                try {
                    fw.close();
                } catch (IOException e) {
                    e.printStackTrace();
                }
            }
            if (fr != null) {
                try {
                    fr.close();
                } catch (IOException e) {
                    e.printStackTrace();
                }
            }
        }
    }

    //抛出处理
    private static void method() throws IOException {
        FileReader fr = new FileReader("fr.txt");
        FileWriter fw = new FileWriter("fw.txt");

        char[] chs = new char[1024];
        int len;
        while ((len=fr.read())!=-1){
            fw.write(chs,0,len);
        }
        fw.close();
        fr.close();
    }
}
```



## 4.特殊操作流

### 1.标准输入输出流

![](https://github.com/Continuers/Java/blob/main/picture/279.png)

```java
package io.itrs7;

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;

/*
    public static final Inputstream in:标准输入流。通常该流对应于键盘输入或由主机环境或用户指定的另一个输入源
 */
public class SystemInDemo {
    public static void main(String[] args) throws IOException {
        //public static final Inputstream in:标准输入流。
//        InputStream is = System.in;

//        int by;
//        while ((by = is.read())!=-1){
//            System.out.print((char) by);
//        }

        //如何把字节流转换为字符流？用转换流
//        InputStreamReader isr = new InputStreamReader(is);
        //使用字符流能不能够实现一次读取一行数据呢？可以
        //但是，一次读取一行数据的方法是字符缓冲输入流的特有方法
//        BufferedReader br = new BufferedReader(isr);

        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));

        System.out.print("请输入一个字符串：");
        String line = br.readLine();
        System.out.println("你输入的字符串是："+line);

        System.out.print("请输入一个整数：");
        int i = Integer.parseInt(br.readLine());
        System.out.println("你输入的整数是："+i);

        //Java提供了一个类供我们使用
//        Scanner sc = new Scanner(System.in);

    }
}
```

![](https://github.com/Continuers/Java/blob/main/picture/280.png)

```java
package io.itrs7;

import java.io.PrintStream;

/*
    public static final Printstream out:标准输岀流。通常该流对应于显示输岀或由主机环境或用户指定的另一个输出目标
 */
public class SystemOutDemo {
    public static void main(String[] args) {
        //public static final Printstream out:标准输岀流。
        PrintStream ps = System.out;

        //能够方便地打印各种数据值
//        ps.print("hello");
//        ps.print(100);

//        ps.println("hello");
//        ps.println(100);

        //System.out的本质是一个字节输出流
        System.out.println("hello");
        System.out.println(100);

        System.out.println();
//        System.out.print();
    }
}
```

### 2.打印流

![](https://github.com/Continuers/Java/blob/main/picture/281.png)

```java
package io.itrs7;

import java.io.IOException;
import java.io.PrintStream;

/*
    打印流的特点
        只负责输出数据,不负责读取数据
        有自己的特有方法
    字节打印流
        Printstream( String filename):使用指定的文件名创建新的打印流
 */
public class PrintStreamDemo {
    public static void main(String[] args) throws IOException {
        //Printstream( String filename):使用指定的文件名创建新的打印流
        PrintStream ps = new PrintStream("myCollection\\ps.txt");

        //写数据
        //字节输出流有的方法
//        ps.write(97);

        //使用特有方法写数据
//        ps.print(97);
//        ps.println();
//        ps.print(98);
//        ps.println(97);
//        ps.println(98);
        
        ps.close();
    }
}
```

![](https://github.com/Continuers/Java/blob/main/picture/282.png)

```java
package io.itrs7;

import java.io.FileWriter;
import java.io.IOException;
import java.io.PrintWriter;

/*
    字符打印流的构造方法:
        Printwriter( String filename):使用指定的文件名创建一个新的 Printwriter,而不需要自动执行行刷新

        Printwriter( riter out, boolean autoflush):创建一个新的 Printwriter
            out:字符输出流
            outoFlush:一个布尔值,如果为真,则 println, printf,或 format方法将刷新输岀緩冲区
 */
public class PrintWriterDemo {
    public static void main(String[] args) throws IOException {
        //Printwriter( String filename):使用指定的文件名创建一个新的 Printwriter,而不需要自动执行行刷新
//        PrintWriter pw = new PrintWriter("myCollection\\pw.txt");

//        pw.write("hello");
//        pw.write("\n");
//        pw.flush();
//        pw.write("world");
//        pw.write("\n");
//        pw.flush();

//        pw.println("hello");
//        pw.flush();
//        pw.println("world");
//        pw.flush();

        //Printwriter( riter out, boolean autoflush):创建一个新的 Printwriter
        PrintWriter pw = new PrintWriter(new FileWriter("myCollection\\pw.txt"),true);
//        PrintWriter pw = new PrintWriter(new FileWriter("myCollection\\pw.txt"),false);

        pw.println("hello");
        pw.println("world");

        pw.close();
    }
}
```

### 案例：复制Java文件(打印流改进版)

![](https://github.com/Continuers/Java/blob/main/picture/283.png)

```java
package io.itrs7;

import java.io.*;

/*
    需求:
        把模块目录下的 PrintStreamDemo.java复制到模块目录下的 Copy.java

    思路：
        ①根据数据源创建字符输入流对象
        ②根据目的地创建字符输出流对象
        ③读写数据,复制文件
        ④释放资源
 */
public class CopyJavaDemo {
    public static void main(String[] args) throws IOException {
        /*
        //①根据数据源创建字符输入流对象
        BufferedReader br = new BufferedReader(new FileReader("myCollection\\PrintStreamDemo.java"));
        //②根据目的地创建字符输出流对象
        BufferedWriter bw = new BufferedWriter(new FileWriter("myCollection\\Copy.java"));

        //③读写数据,复制文件
        String line;
        while ((line=br.readLine())!=null){
            bw.write(line);
            bw.newLine();
            bw.flush();
        }

        bw.close();
        br.close();
        */

        //①根据数据源创建字符输入流对象
        BufferedReader br = new BufferedReader(new FileReader("myCollection\\PrintStreamDemo.java"));
        //②根据目的地创建字符输出流对象
        PrintWriter pw = new PrintWriter(new FileWriter("myCollection\\\\Copy.java"),true);

        //③读写数据,复制文件
        String line;
        while ((line=br.readLine())!=null){
            pw.println(line);
        }

        pw.close();
        br.close();
    }
}
```

### 3.对象序列化流

#### 1.序列化

![](https://github.com/Continuers/Java/blob/main/picture/284.png)

```java
package io.itrs7;

import java.io.Serializable;

public class Student implements Serializable {
    private String name;
    private int age;

    public Student() {
    }

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}
```

```java
package io.itrs7;

import java.io.FileOutputStream;
import java.io.IOException;
import java.io.ObjectOutputStream;

/*
    对象序列化流
        构造方法
            Objectoutputstream( Output stream out):创建一个写入指定的 Outputstream的 Objectoutputstream

        序列化对象的方法
            void writeobject( Object obj):将指定的对象写入 Objectoutputstream

    Not serializableexception:抛出一个实例需要一个 Serializable接口。序列化运行时或实例的类可能会抛出此异常

    类的序列化由实现java.io, Serializable接口的类启用。不实现此接口的类将不会使任何状态序列化或反序列化
 */
public class ObjectOutputStreamDemo {
    public static void main(String[] args) throws IOException {
        //Objectoutputstream( Output stream out):创建一个写入指定的 Outputstream的 Objectoutputstream
        ObjectOutputStream oos = new ObjectOutputStream(new FileOutputStream("myCollection\\oos.txt"));

        //创建对象
        Student s = new Student("java",30);

        //void writeobject( Object obj):将指定的对象写入 Objectoutputstream
        oos.writeObject(s);

        oos.close();
    }
}
```

#### 2.反序列化

![](https://github.com/Continuers/Java/blob/main/picture/285.png)

```java
package io.itrs7;

import java.io.FileInputStream;
import java.io.IOException;
import java.io.ObjectInputStream;

/*
    构造方法
        Objectinputstream( Inputstream in),创建从指定的 Inputstream读取的 Objectinputstrear

    反序列化对象的方法
        Object readobject()从 Objectinputstream读取一个对象
 */
public class ObjectInputStreamDemo {
    public static void main(String[] args) throws IOException, ClassNotFoundException {
        //Objectinputstream( Inputstream in),创建从指定的 Inputstream读取的 Objectinputstrear
        ObjectInputStream ois = new ObjectInputStream(new FileInputStream("myCollection\\oos.txt"));

        //Object readobject()从 Objectinputstream读取一个对象
        Object obj = ois.readObject();

        Student s = (Student) obj;
        System.out.println(s.getName()+","+s.getAge());

        ois.close();
    }
}
```

#### 3.对象序列化流

![](https://github.com/Continuers/Java/blob/main/picture/286.png)

```java
package io.itrs7;

import java.io.Serializable;

public class Student implements Serializable {
    private String name;
//    private int age;
    private transient int age;

    public Student() {
    }

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}
```

```java
package io.itrs7;

import java.io.*;

/*
    用对象序列化流序列化了一个对象后,假如我们修改了对象所属的类文件,读取数据会不会出问题呢?
        java.io.Invalidclassexception:
            当序列化运行时检测到类中的以下问题之一时抛出。
                类的串行版本与从流中读取的类描述符的类型不匹配
                该类包含未知的数据类型
                该类没有可访问的无参数构造函数
        com. itheima 03 Student, Local class incompatible
        stream classdesc serialversionuid =-3743788623620386195
        Local class serialversionuid247282599948908173

    如果出问题了,如何解决呢?
        给对象所属的类加一个值: private static final Long serialversionuid=42L;
    如果一个对象中的某个成员变量的值不想被序列化,又该如何实现呢?
        private transient int age
 */
public class ObjectStreamDemo {
    public static void main(String[] args) throws IOException,ClassNotFoundException {
//        write();
        read();
    }

    //反序列化
    private static void read ( ) throws IOException, ClassNotFoundException{
        ObjectInputStream ois = new ObjectInputStream(new FileInputStream("myCollection\\oos.txt"));
        Object obj = ois.readObject();
        Student s = (Student) obj;
        System.out.println(s.getName()+","+s.getAge());
        ois.close();
    }

    //序列化
    private static void write() throws IOException{
        ObjectOutputStream oos = new ObjectOutputStream(new FileOutputStream("myCollection\\oos.txt"));
        Student s = new Student("java",30);
        oos.writeObject(s);
        oos.close();
    }
}
```



### 4.Properties

#### 1.概述

![](https://github.com/Continuers/Java/blob/main/picture/287.png)

```java
package io.itrs8;

import java.util.Properties;
import java.util.Set;

/*
    Properties作为Map集合的使用
 */
public class PropertiesDemo {
    public static void main(String[] args) {
        //创建集合对象
        Properties prop = new Properties();

        //存储元素
        prop.put("itrs001","黑马");
        prop.put("itrs002","播妞");
        prop.put("itrs003","程序员");

        //遍历集合
        Set<Object> keySet = prop.keySet();
        for (Object key : keySet){
            Object value = prop.get(key);
            System.out.println(key+","+value);
        }
    }
}
```

#### 2.Properties作为集合的特有方法

![](https://github.com/Continuers/Java/blob/main/picture/288.png)

```java
package io.itrs8;

import java.util.Properties;
import java.util.Set;

/*
    Properties作为集合的特有方法方法名说明
        Object setproperty(String key, String value)设置集合的键和值,都是 String类型,底层调用 Hashtable方法put
        String getproperty(String key)使用此属性列表中指定的键搜索属性
        Set< String stringPropertyNames():从该属性列表中返回一个不可修改的键集,其中键及其对应的
 */
public class ProPertiesDemo2 {
    public static void main(String[] args) {
        //创建集合对象
        Properties prop = new Properties();

        //Object setproperty(String key, String value)设置集合的键和值,都是 String类型,底层调用 Hashtable方法put
        prop.setProperty("itrs001","黑马");
        /*
            Object setProperty(String key, String value) {
                return put(key, value);
            }
            Object put(Object key, Object value) {
                return map.put(key, value);
            }
         */
        prop.setProperty("itrs002","播妞");
        prop.setProperty("itrs003","程序员");

        //String getproperty(String key)使用此属性列表中指定的键搜索属性
//        System.out.println(prop.getProperty("itrs001"));    //黑马
//        System.out.println(prop.getProperty("itrs0011"));   //null

//        System.out.println(prop);   //{itrs003=程序员, itrs002=播妞, itrs001=黑马}

        //Set< String stringPropertyNames():从该属性列表中返回一个不可修改的键集,其中键及其对应的
        Set<String> names = prop.stringPropertyNames();
        for (String key : names){
//            System.out.println(key);
            String value = prop.getProperty(key);
            System.out.println(key + ","+value);
        }
    }
}
```

#### 3.Properties和IO流结合的方法

![](https://github.com/Continuers/Java/blob/main/picture/290.png)

```java
package io.itrs8;

import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;
import java.util.Properties;

/*
    Properties和IO流结合的方法:
        void Load(Reader reader)
            从输入字符流读取属性列表(键和元素对)

         void store(Writer writer, String comments):
            将此属性列表(键和元素对)写入此 Properties表中,以适合使用toad( Reader)方法的格式写入输出字符流
 */
public class PropertiesDemo3 {
    public static void main(String[] args) throws IOException {
        //把集合中的数据保存到文件
//        myStore();
        //把文件中的数据加载到集合
        myLoad();

    }

    private static void myLoad() throws IOException {
        Properties prop = new Properties();

        //void Load(Reader reader)
        FileReader fr = new FileReader("myCollection\\fw.txt");
        prop.load(fr);
        fr.close();

        System.out.println(prop);

    }

    private static void myStore() throws IOException {
        Properties prop = new Properties();

        prop.setProperty("itrs001","黑马");
        prop.setProperty("itrs002","播妞");
        prop.setProperty("itrs003","程序员");

        //void store(Writer writer, String comments):
        FileWriter fw = new FileWriter("myCollection\\fw.txt");
        prop.store(fw,null);
        fw.close();
    }
}
```

## 案例：游戏次数

![](https://github.com/Continuers/Java/blob/main/picture/291.png)

```java
package io.itrs8;

import java.util.Random;
import java.util.Scanner;

public class GuessNumber {
    private GuessNumber(){
    }

    public static void start(){
        //要完成猜数字的游戏，首先需要有一个要猜的数字，使用随机数生成该数字，范围1到100
        Random r = new Random();
        int number = r.nextInt(100)+1;

        while (true){
            //使用程序实现猜数字，每次均要输入猜测的数字值，需要使用键盘录入实现
            Scanner sc = new Scanner(System.in);

            System.out.print("请输入你要猜的数字：");
            int guessNumber = sc.nextInt();

            //比较输入的数字和系统产生的数据，需要使用分支语句
            if (guessNumber>number){
                System.out.println("你猜的数字"+guessNumber+"大了");
            } else if(guessNumber<number){
                System.out.println("你猜的数字"+guessNumber+"小了");
            } else {
                System.out.println("恭喜你猜中了！");
                break;
            }
        }
    }
}
```

```java
package io.itrs8;

import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;
import java.util.Properties;

/*
    需求:请写程序实现猜数字小游戏只能试玩3次,如果还想玩,提示:游戏试玩已结束,想玩请充值(ww. toast.cn)
    思路:
        1:写一个游戏类,里面有一个猜数字的小游戏
        2:写一个测试类,测试类中有main方法,main()方法中按照下面步骤完成
            A:从文件中读取数据到 Properties集合,用Load()方法实现
                文件已经存在:game.txt
                里面有一个数据值: count=0
            B:通过 Properties集合获取到玩游戏的次数
            C:判断次数是否到到3次了
                如果到了,给出提示:游戏试玩已结束,想玩请充值
                如果不到3次:
                    玩游戏
                    次数+1,重新写回文件,用 Properties的 store()方法实现
 */
public class PropertiesTest {
    public static void main(String[] args) throws IOException {
        //从文件中读取数据到 Properties集合,用Load()方法实现
        Properties prop = new Properties();

        FileReader fr = new FileReader("myCollection\\game.txt");
        prop.load(fr);
        fr.close();

        //通过 Properties集合获取到玩游戏的次数
        String count = prop.getProperty("count");
        int number = Integer.parseInt(count);

        //判断次数是否到到3次了
        if (number>=3){
            //如果到了,给出提示:游戏试玩已结束,想玩请充值
            System.out.println("游戏试玩已结束,想玩请充值");
        } else {
            //玩游戏
            GuessNumber.start();

            //次数+1,重新写回文件,用 Properties的 store()方法实现
            number++;
            prop.setProperty("count",String.valueOf(number));
            FileWriter fw = new FileWriter("myCollection\\game.txt");
            prop.store(fw,null);
            fw.close();
        }
    }
}
```

```java
/*game.txt*/
#Sun Sep 05 17:40:52 CST 2021
count=3
```



# 32.多线程



## 1.实现多线程

### 1.进程

![](https://github.com/Continuers/Java/blob/main/picture/292.png)

### 2.线程

![](https://github.com/Continuers/Java/blob/main/picture/293.png)

### 3.多线程的实现方式

![](https://github.com/Continuers/Java/blob/main/picture/294.png)

```java
package com.itrs1;

public class MyThread extends Thread{
    @Override
    public void run() {
        for (int i=0;i<100;i++){
            System.out.println(i);
        }
    }
}
```

```java
package com.itrs1;

/*
    方式1:继承 Thread类
        1:定义一个类 Mythread继承 Thread类
        2:在 My Thread类中重写run()方法
        3:创建MyThread类的对象
        4:启动线程
 */
public class MyThreadDemo {
    public static void main(String[] args) {
        MyThread my1 = new MyThread();
        MyThread my2 = new MyThread();

//        my1.run();
//        my2.run();

        // void start()导致此线程开始执行;Jave虛拟机调用此线程的run方法
        my1.start();
        my2.start();
    }
}
```

### 4.设置和获取线程名称

![](https://github.com/Continuers/Java/blob/main/picture/295.png)

```java
package com.itrs1;

public class MyThread extends Thread{

    public MyThread(){}

    public MyThread(String name){
        super(name);
    }

    @Override
    public void run() {
        for (int i=0;i<100;i++){
            System.out.println(getName()+":"+i);
        }
    }
}

/*
    private String name;

    public Thread() {
        this(null, null, "Thread-" + nextThreadNum(), 0);
    }

    public Thread(String name) {
        this(null, null, name, 0);
    }

    public Thread(ThreadGroup group, Runnable target, String name,
                  long stackSize) {
        this(group, target, name, stackSize, null, true);
    }

    private Thread(ThreadGroup g, Runnable target, String name,
                   long stackSize, AccessControlContext acc,
                   boolean inheritThreadLocals) {
        this.name = name;
    }

    public final synchronized void setName(String name) {
        this.name = name;
    }

    public final String getName() {
        return name;
    }

    private static int threadInitNumber;    //0.1.2
    private static synchronized int nextThreadNum() {
        return threadInitNumber++;  //0.1.....
    }
 */
```

```java
package com.itrs1;

/*
    Thread类中获取和设置线程名称的方法
        void setname( String name):将此线程的名称更改为等于参数name
        String getname():返回此线程的名称
 */
public class MyThreadDemo {
    public static void main(String[] args) {
        /*
        MyThread my1 = new MyThread();
        MyThread my2 = new MyThread();

        //void setname( String name):将此线程的名称更改为等于参数name
        my1.setName("高铁");
        my2.setName("飞机");
        */

        //Thread (String name)
//        MyThread my1 = new MyThread("高铁");
//        MyThread my2 = new MyThread("飞机");
//
//        my1.start();
//        my2.start();

        // static Thread currentThread()返回对当前正在执行的线程对象的引用
        System.out.println(Thread.currentThread().getName());
    }
}
```

### 5.线程调度

![](https://github.com/Continuers/Java/blob/main/picture/296.png)

```java
package com.itrs1;

public class ThreadPriority extends Thread{

    @Override
    public void run() {
        for (int i=0;i<100;i++){
            System.out.println(getName()+":"+i);
        }
    }
}
```

```java
package com.itrs1;

/*
    Thread类中设置和获取线程优先级的方法
        public final void setpriority( int newpriority):更改此线程的优先级
        public final int getpriority():返回此线程的优先级
 */
public class ThreadPriorityDemo {
    public static void main(String[] args) {
        ThreadPriority tp1 = new ThreadPriority();
        ThreadPriority tp2 = new ThreadPriority();
        ThreadPriority tp3 = new ThreadPriority();

        tp1.setName("高铁");
        tp2.setName("飞机");
        tp3.setName("汽车");

        //public final int getpriority():返回此线程的优先级
//        System.out.println(tp1.getPriority());  //5
//        System.out.println(tp2.getPriority());  //5
//        System.out.println(tp3.getPriority());  //5

        //public final void setpriority( int newpriority):更改此线程的优先级
//        tp1.setPriority(10000);
//        System.out.println(Thread.MAX_PRIORITY);    //10
//        System.out.println(Thread.MIN_PRIORITY);    //1
//        System.out.println(Thread.NORM_PRIORITY);   //5

        //设置正确的优先级      仅仅表示几率
        tp1.setPriority(5);
        tp2.setPriority(10);
        tp3.setPriority(1);

        tp1.start();
        tp2.start();
        tp3.start();
    }
}
```

### 6.线程控制

![](https://github.com/Continuers/Java/blob/main/picture/297.png)

```java
package com.itrs2;

public class ThreadSleep extends Thread{
    @Override
    public void run() {
        for (int i=0;i<100;i++){
            System.out.println(getName()+":"+i);
            try {
                Thread.sleep(1000);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
}
```

```java
package com.itrs2;
/*
    static void sleep( Long millis):使当前正在执行的线程停留(暂停执行)指定的毫秒数
 */
public class ThreadSleepDemo {
    public static void main(String[] args) {
        ThreadSleep tp1 = new ThreadSleep();
        ThreadSleep tp2 = new ThreadSleep();
        ThreadSleep tp3 = new ThreadSleep();

        tp1.setName("高铁");
        tp2.setName("飞机");
        tp3.setName("汽车");

        tp1.start();
        tp2.start();
        tp3.start();
    }
}
```



```java
package com.itrs2;

public class ThreadJoin extends Thread{
    @Override
    public void run() {
        for (int i=0;i<100;i++){
            System.out.println(getName()+":"+i);
        }
    }
}
```

```java
package com.itrs2;
/*
    void join(): 等待这个线程死亡
 */
public class ThreadJoinDemo {
    public static void main(String[] args) {
        ThreadJoin tj1 = new ThreadJoin();
        ThreadJoin tj2 = new ThreadJoin();
        ThreadJoin tj3 = new ThreadJoin();

        tj1.setName("黑马");
        tj2.setName("播妞");
        tj3.setName("程序员");

        tj1.start();
        try {
            tj1.join();
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
        tj2.start();
        tj3.start();
    }
}
```



```java
package com.itrs2;

public class ThreadDaemon extends Thread{
    @Override
    public void run() {
        for (int i=0;i<100;i++){
            System.out.println(getName()+":"+i);
        }
    }
}
```

```java
package com.itrs2;
/*
    void setDaemon( boolean on):将此线程标记为守护线程,当运行的线程都是守护线程时,Java虛拟机将退岀
 */
public class ThreadDaemonDemo {
    public static void main(String[] args) {
        ThreadDaemon td1 = new ThreadDaemon();
        ThreadDaemon td2 = new ThreadDaemon();

        td1.setName("关羽");
        td2.setName("张飞");

        //设置主线程为刘备
        Thread.currentThread().setName("刘备");

        //设置守护线程
        td1.setDaemon(true);
        td2.setDaemon(true);

        td1.start();
        td2.start();

        for (int i=0;i<10;i++){
            System.out.println(Thread.currentThread().getName()+":"+i);
        }

    }
}
```

### 7.线程生命周期

![](https://github.com/Continuers/Java/blob/main/picture/298.png)

### 8.多线程的实现方式

![](https://github.com/Continuers/Java/blob/main/picture/299.png)

```java
package com.itrs3;

public class MyRunnable implements Runnable{
    @Override
    public void run() {
        for (int i=0;i<100;i++){
            System.out.println(Thread.currentThread().getName()+":"+i);
        }
    }
}
```

```java
package com.itrs3;
/*
    方式2:实现 Runnable接口
        1:定义一个类 Myrunnable实现 Runnable接口
        2:在 Myrunnable类中重写run()方法
        3:创建 Myrunnable类的对象
        4:创建 Thread类的对象,把 Myrunnable对象作为构造方法的参数
        5:启动线程
 */
public class MyRunnableDemo {
    public static void main(String[] args) {
        //3:创建 Myrunnable类的对象
        MyRunnable my = new MyRunnable();

        //4:创建 Thread类的对象,把 Myrunnable对象作为构造方法的参数
        //Thread(Runnable target)
//        Thread t1 = new Thread(my);
//        Thread t2 = new Thread(my);

        //Thread(Runnable target,String name)
        Thread t1 = new Thread(my,"高铁");
        Thread t2 = new Thread(my,"飞机");

        //5:启动线程
        t1.start();
        t2.start();
    }
}
```

## 2.线程同步

### 案例：卖票

![](https://github.com/Continuers/Java/blob/main/picture/300.png)

```java
package com.itrs3;

//①定义一个类 Sellick实现 Runnable接口,里面定义一个成员变量: private int tickets=100
public class SellTicket implements Runnable{
    private int tickets = 0;

    //②在 Sellticket类中重写run()方法实现卖票,代码步骤如下

    @Override
    public void run() {
        //A:判断票数大于0,就卖票,并告知是哪个窗口卖的
        //B:卖了票之后,总票数要减1
        //C:票没有了,也可能有人来问,所以这里用死循环让卖票的动作一直执行

        while (true){
            if (tickets<100){
                System.out.println(Thread.currentThread().getName()+"正在出售第"+tickets+"张票");
                tickets++;
            }
        }
    }
}
```

```java
package com.itrs3;
/*
    需求:
        某电影院目前正在上映国产大片,共有100张票,而它有3个窗口卖票,请设计一个程序模拟该电影院卖票
    思路:
        ①定义一个类 Sellick实现 Runnable接口,里面定义一个成员变量: private int tickets=100
        ②在 Sellticket类中重写run()方法实现卖票,代码步骤如下
            A:判断票数大于0,就卖票,并告知是哪个窗口卖的
            B:卖了票之后,总票数要减1
            C:票没有了,也可能有人来问,所以这里用死循环让卖票的动作一直执行
        ③定义一个测试类 Sellticketdemo,里面有main方法,代码步骤如下
            A:创建 Sellticket类的对象
            B:创建三个 Thread类的对象,把 Sellicke对象作为构造方法的参数,并给出对应的窗囗名称
            C:启动线程
 */
public class SellTicketDemo {
    public static void main(String[] args) {
        //A:创建 Sellticket类的对象
        SellTicket st = new SellTicket();

        //B:创建三个 Thread类的对象,把 Sellicke对象作为构造方法的参数,并给出对应的窗囗名称
        Thread t1 = new Thread(st,"窗口1");
        Thread t2 = new Thread(st,"窗口2");
        Thread t3 = new Thread(st,"窗口3");

        //C:启动线程
        t1.start();
        t2.start();
        t3.start();
    }
}
```

### 1.卖票案例的思考

![](https://github.com/Continuers/Java/blob/main/picture/301.png)

```java
package com.itrs3;

//①定义一个类 Sellick实现 Runnable接口,里面定义一个成员变量: private int tickets=100
public class SellTicket implements Runnable {
    private int tickets = 100;

    //②在 Sellticket类中重写run()方法实现卖票,代码步骤如下

    @Override
    public void run() {
        //A:判断票数大于0,就卖票,并告知是哪个窗口卖的
        //B:卖了票之后,总票数要减1
        //C:票没有了,也可能有人来问,所以这里用死循环让卖票的动作一直执行

        //相同票出现多次
        /*
        while (true){
            //tickets = 100;
            //t1,t2,t3
            //假设t1线程抢到CPU的执行权
            if (tickets>0){
                //通过sleep()方法来模拟出票时间
                try {
                    Thread.sleep(100);
                    //t1线程休息100毫秒
                    //t2线程抢到CPU的执行权，t2线程就开始执行,执行到这里的时候，t2线程休息100毫秒
                    //t3线程抢到CPU的执行权，t3线程就开始执行，执行到这里的时候，t3线程休息100毫秒
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
                //假设线程按照顺序醒过来
                //t1抢到CPU的执行权，在控制台输出，窗口1正在出售第100张票
                System.out.println(Thread.currentThread().getName()+"正在出售第"+tickets+"张票");
                //t2抢到CPU的执行权，在控制台输出，窗口2正在出售第100张票
                //t3抢到CPU的执行权，在控制台输出，窗口3正在出售第100张票
                tickets--;
                //如果这三个线程还是按照顺序来，这里就执行了3次--的操作，最终票就变成了97
            }
        }
        */

        //出现了负数的票
        while (true) {
            //tickets = 1;
            //t1,t2,t3
            //假设t1线程抢到CPU的执行权
            if (tickets > 0) {
                //通过sleep()方法来模拟出票时间
                try {
                    Thread.sleep(100);
                    //t1线程休息100毫秒
                    //t2线程抢到CPU的执行权，t2线程就开始执行,执行到这里的时候，t2线程休息100毫秒
                    //t3线程抢到CPU的执行权，t3线程就开始执行，执行到这里的时候，t3线程休息100毫秒
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
                //假设线程按照顺序醒过来
                //t1抢到CPU的执行权，在控制台输出，窗口1正在出售第1张票
                //假设t1继续拥有CPU的执行权，就会执行tickets--;操作，tickets=0;
                //t2抢到CPU的执行权，在控制台输出，窗口2正在出售第0张票
                //假设t2继续拥有CPU的执行权，就会执行tickets--;操作，tickets=-1;
                //t3抢到CPU的执行权，在控制台输出，窗口3正在出售第-1张票
                //假设t3继续拥有CPU的执行权，就会执行tickets--;操作，tickets=-2;


                System.out.println(Thread.currentThread().getName() + "正在出售第" + tickets + "张票");
                tickets--;
            }
        }
    }
}
```

```java
package com.itrs3;

public class SellTicketDemo {
    public static void main(String[] args) {
        //A:创建 Sellticket类的对象
        SellTicket st = new SellTicket();

        //B:创建三个 Thread类的对象,把 Sellicke对象作为构造方法的参数,并给出对应的窗囗名称
        Thread t1 = new Thread(st,"窗口1");
        Thread t2 = new Thread(st,"窗口2");
        Thread t3 = new Thread(st,"窗口3");

        //C:启动线程
        t1.start();
        t2.start();
        t3.start();
    }
}
```

### 2.卖票案例数据安全问题的解决

![](https://github.com/Continuers/Java/blob/main/picture/302.png)

![](https://github.com/Continuers/Java/blob/main/picture/303.png)

```java
package com.itrs4;

public class SellTicket implements Runnable {
    private int tickets = 100;
    private Object obj = new Object();

    @Override
    public void run() {
        while (true) {
            //tickets = 100;
            //t1,t2,t3
            //假设t1抢到了CPU的执行权
            //假设t2抢到了CPU的执行权

            synchronized (obj) {
                //t1进来后，就会把该代码给锁起来
                if (tickets > 0) {
                    try {
                        Thread.sleep(100);
                        //t1休息100毫秒
                    } catch (InterruptedException e) {
                        e.printStackTrace();
                    }
                    //窗口1正在出售第100张票
                    System.out.println(Thread.currentThread().getName() + "正在出售第" + tickets + "张票");
                    tickets--;  //tickets = 99;
                }
            }
            //t1出来了，这段代码的锁就被释放了
        }
    }
}
```

```java
package com.itrs4;

public class SellTicketDemo {
    public static void main(String[] args) {
        SellTicket st = new SellTicket();

        Thread t1 = new Thread(st,"窗口1");
        Thread t2 = new Thread(st,"窗口2");
        Thread t3 = new Thread(st,"窗口3");

        t1.start();
        t2.start();
        t3.start();
    }
}
```

### 4.同步方法

![](https://github.com/Continuers/Java/blob/main/picture/304.png)

```java
package com.itrs5;

public class SellTicket implements Runnable {
//    private int tickets = 100;
    private static int tickets = 100;
    private Object obj = new Object();
    private int x = 0;

    @Override
    public void run() {
        while (true) {
            if(x%2==0) {
//                synchronized (obj) {
//                synchronized (this) {
                synchronized (SellTicket.class) {
                    if (tickets > 0) {
                        try {
                            Thread.sleep(100);
                        } catch (InterruptedException e) {
                            e.printStackTrace();
                        }
                        System.out.println(Thread.currentThread().getName() + "正在出售第" + tickets + "张票");
                        tickets--;
                    }
                }
            } else {
                /*
                synchronized (obj) {

                    if (tickets > 0) {
                        try {
                            Thread.sleep(100);
                        } catch (InterruptedException e) {
                            e.printStackTrace();
                        }
                        System.out.println(Thread.currentThread().getName() + "正在出售第" + tickets + "张票");
                        tickets--;
                    }
                }
                */
                sellTicket();
            }
            x++;
        }
    }

    /*
    private void sellTicket() {
        synchronized (obj) {
            if (tickets > 0) {
                try {
                    Thread.sleep(100);
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
                System.out.println(Thread.currentThread().getName() + "正在出售第" + tickets + "张票");
                tickets--;
            }
        }
    }
    */

    /*
    private synchronized void sellTicket() {
        if (tickets > 0) {
            try {
                Thread.sleep(100);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            System.out.println(Thread.currentThread().getName() + "正在出售第" + tickets + "张票");
            tickets--;
        }
    }
    */

    private static synchronized void sellTicket() {
        if (tickets > 0) {
            try {
                Thread.sleep(100);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            System.out.println(Thread.currentThread().getName() + "正在出售第" + tickets + "张票");
            tickets--;
        }
    }
}
```

```java
package com.itrs5;

public class SellTicketDemo {
    public static void main(String[] args) {
        SellTicket st = new SellTicket();

        Thread t1 = new Thread(st,"窗口1");
        Thread t2 = new Thread(st,"窗口2");
        Thread t3 = new Thread(st,"窗口3");

        t1.start();
        t2.start();
        t3.start();
    }
}
```

### 5.线程安全的类

![](https://github.com/Continuers/Java/blob/main/picture/305.png)

```java
package com.itrs3;

import java.util.*;

/*
    线程安全的类
        StringBuffer
        Vector
        Hashtable
 */
public class ThreadDemo  {
    public static void main(String[] args) {
        StringBuffer sb = new StringBuffer();
        StringBuilder sb2 = new StringBuilder();

        Vector<String> v = new Vector<String>();
        ArrayList<String> array = new ArrayList<String>();

        Hashtable<String,String> ht = new Hashtable<String, String>();
        HashMap<String,String> hm = new HashMap<String,String>();

        // static<T> List<T> synchronizedlist( List<T>tist)返回由指定列表支持的同步(线程安全)列表
        List<String> list = Collections.synchronizedList(new ArrayList<String>());
    }
}
```

### 6.Lock锁

![](https://github.com/Continuers/Java/blob/main/picture/306.png)

```java
package com.itrs6;

import java.util.concurrent.locks.Lock;
import java.util.concurrent.locks.ReentrantLock;

/*
    Lock中提供了获得锁和释放锁的方法
        void lock():获得锁
        void unlock():释放锁

    Lock是接囗不能直接实例化,这里采用它的实现类 Reentrantlock来实例化
        Reentrantlock():创建一个 Reentrantlock的实例
 */
public class SellTicket implements Runnable {
    private int tickets = 100;
    private Lock lock = new ReentrantLock();

    @Override
    public void run() {
        while (true) {
            try{
                lock.lock();
                if (tickets > 0) {
                    try {
                        Thread.sleep(100);
                    } catch (InterruptedException e) {
                        e.printStackTrace();
                    }
                    System.out.println(Thread.currentThread().getName() + "正在出售第" + tickets + "张票");
                    tickets--;
                }
            }finally {
                lock.unlock();
            }
        }
    }
}
```

```java
package com.itrs6;

public class SellTicketDemo {
    public static void main(String[] args) {
        SellTicket st = new SellTicket();

        Thread t1 = new Thread(st, "窗口1");
        Thread t2 = new Thread(st, "窗口2");
        Thread t3 = new Thread(st, "窗口3");

        t1.start();
        t2.start();
        t3.start();
    }
}
```

## 3.生产者消费者

### 1.生产者消费者模式概述

![](https://github.com/Continuers/Java/blob/main/picture/307.png)

![](https://github.com/Continuers/Java/blob/main/picture/308.png)

### 2.生产者消费者案例

![](https://github.com/Continuers/Java/blob/main/picture/309.png)

```java
package com.itrs4;

public class Producer implements Runnable{
    private Box b;

    public Producer(Box b) {
        this.b = b;
    }

    @Override
    public void run() {
        for (int i=1;i<=5;i++){
            b.put(i);
        }
    }
}
```

```java
package com.itrs4;

public class Customer implements Runnable{
    private Box b;

    public Customer(Box b) {
        this.b = b;
    }

    @Override
    public void run() {
        while (true){
            b.get();
        }
    }
}
```

```java
package com.itrs4;

public class Box {
    //定义一个成员变量，表示第x瓶奶
    private int milk;
    //定义一个成员变量，表示奶箱的状态
    private boolean state = false;

    //提供存储牛奶和获取牛奶的操作
    public synchronized void put(int milk){
        //如果有牛奶，等待消费
        if (state){
            try {
                wait();
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }

        //如果没有牛奶，就生产牛奶
        this.milk = milk;
        System.out.println("送奶工将第"+this.milk+"奶瓶放入奶箱");

        //生产完毕之后，修改奶箱状态
        state = true;

        //唤醒其他等待的线程
        notifyAll();
    }

    public synchronized void get(){
        //如果没有牛奶,等待生产
        if (!state){
            try {
                wait();
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }

        //如果有牛奶，就消费牛奶
        System.out.println("用户拿到第"+this.milk+"瓶奶");

        //消费完毕之后，修改奶箱状态
        state = false;

        //唤醒其他等待的线程
        notifyAll();
    }
}
```

```java
package com.itrs4;
/*
    生产者消费者案例中包含的类
        1:奶箱类(Box)定义一个成员变量,表示第x瓶奶,提供存储牛奶和获取牛奶的操作
        2:生产者类( Producer):实现 Runnable接口,重写run()方法,调用存储牛奶的操作
        3:消费者类(Customer):实现 Runnable接口,重写run()方法,调用获取牛奶的操作
        4:测试类( Boxdemo):里面有main方法,main方法中的代码步骤如下
            A:创建奶箱对象,这是共享数据区域
            B:创建生产者对象,把奶箱对象作为构造方法参数传递,因为在这个类中要调用存储牛奶的操作
            C:创建消费者对象,把奶箱对象作为构造方法参数传递,因为在这个类中要调用获取牛奶的操作
            D:创建2个线程对象,分别把生产者对象和消费者对象作为构造方法参数传递
            E:启动线程
 */
public class BoxDemo {
    public static void main(String[] args) {
        //A:创建奶箱对象,这是共享数据区域
        Box b = new Box();

        //B:创建生产者对象,把奶箱对象作为构造方法参数传递,因为在这个类中要调用存储牛奶的操作
        Producer p = new Producer(b);
        //C:创建消费者对象,把奶箱对象作为构造方法参数传递,因为在这个类中要调用获取牛奶的操作
        Customer c = new Customer(b);

        //D:创建2个线程对象,分别把生产者对象和消费者对象作为构造方法参数传递
        Thread t1 = new Thread(p);
        Thread t2 = new Thread(c);

        //E:启动线程
        t1.start();
        t2.start();

    }
}
```





# 33.网络编程

## 1.网络编程入门

### 1.网络编程概述

![](https://github.com/Continuers/Java/blob/main/picture/310.png)

### 2.网络编程三要素

![](https://github.com/Continuers/Java/blob/main/picture/311.png)

### 3.IP地址

![](https://github.com/Continuers/Java/blob/main/picture/312.png)

![](https://github.com/Continuers/Java/blob/main/picture/313.png)

### 4.InetAddress 的使用

![](https://github.com/Continuers/Java/blob/main/picture/314.png)

```java
package cn.itrs1;

import java.net.InetAddress;
import java.net.UnknownHostException;

/*
    Inetaddress
        此类表示 Internet协议(IP)地址

    public static InetAddress getByName( String host):确定主机名称的IP地址。主机名称可以是机器名称,也可以是IP地址
    public String getHostName():获取此IP地址的主机名
    public String getHostAddress():返回文本显示中的IP地址字符串
 */
public class InetAddressDemo {
    public static void main(String[] args) throws UnknownHostException {
        //public static InetAddress getByName( String host):确定主机名称的IP地址。主机名称可以是机器名称,也可以是IP地址
//        InetAddress address = InetAddress.getByName("DESKTOP-PA1NJH7");
        InetAddress address = InetAddress.getByName("172.21.122.115");

        //public String getHostName():获取此IP地址的主机名
        String name = address.getHostName();

        //public String getHostAddress():返回文本显示中的IP地址字符串
        String ip = address.getHostAddress();

        System.out.println("主机名："+name);
        System.out.println("IP地址："+ip);
    }
}
```

### 5.端口

![](https://github.com/Continuers/Java/blob/main/picture/315.png)

### 6.协议

![](https://github.com/Continuers/Java/blob/main/picture/316.png)

![](https://github.com/Continuers/Java/blob/main/picture/317.png)



## 2.UDP通信程序

### 1.UDP通信原理

![](https://github.com/Continuers/Java/blob/main/picture/318.png)

### 2.UDP发送数据

![](https://github.com/Continuers/Java/blob/main/picture/319.png)

```java
package cn.itrs1;

import java.io.IOException;
import java.net.DatagramPacket;
import java.net.DatagramSocket;
import java.net.InetAddress;

/*
    UDP发送数据的步骤
        1:创建发送端的 Socket对象( Datagramsocket)
        2:创建数据,并把数据打包
        3:调用 Datagramsocket对象的方法发送数据
        4:关闭发送端
 */
public class SendDemo {
    public static void main(String[] args) throws IOException {
        //1:创建发送端的 Socket对象( Datagramsocket)
        /* Datagramsocket()构造数据报套接字并将其排定到本地主机上的任何可用端口 */
        DatagramSocket ds = new DatagramSocket();

        //2:创建数据,并把数据打包
        /* Datagrampacket (byte[] buf, int Length, Inetaddress address, int port)
           构造一个数据包,发送长度为 Length的数据包到指定主机上的指定端口号 */
        byte[] bys = "hello,udp".getBytes();
//        int length = bys.length;
//        InetAddress address = InetAddress.getByName("172.21.122.115");    //IP 地址
//        int port = 10086;     //端口号
//        DatagramPacket dp = new DatagramPacket(bys,length,address,port);
        DatagramPacket dp = new DatagramPacket(bys,bys.length,InetAddress.getByName("172.21.122.115"),10086);

        //3:调用 Datagramsocket对象的方法发送数据
        /* void send (DatagramPacket p) 从此套接字发送数据报包 */
        ds.send(dp);

        //4:关闭发送端
        /* void close() 关闭此数据报套接字 */
        ds.close();
    }
}
```

### 3.UDP接收数据

![](https://github.com/Continuers/Java/blob/main/picture/320.png)

```java
package cn.itrs1;
/*
	发送端
*/
import java.io.IOException;
import java.net.DatagramPacket;
import java.net.DatagramSocket;
import java.net.InetAddress;

/*
    UDP发送数据的步骤
        1:创建发送端的 Socket对象( Datagramsocket)
        2:创建数据,并把数据打包
        3:调用 Datagramsocket对象的方法发送数据
        4:关闭发送端
 */
public class SendDemo {
    public static void main(String[] args) throws IOException {
        //1:创建发送端的 Socket对象( Datagramsocket)
        /* Datagramsocket()构造数据报套接字并将其排定到本地主机上的任何可用端口 */
        DatagramSocket ds = new DatagramSocket();

        //2:创建数据,并把数据打包
        /* Datagrampacket (byte[] buf, int Length, Inetaddress address, int port)
           构造一个数据包,发送长度为 Length的数据包到指定主机上的指定端口号 */
        byte[] bys = "hello,udp,我来了".getBytes();
//        int length = bys.length;
//        InetAddress address = InetAddress.getByName("172.21.122.115");    //IP 地址
//        int port = 10086;     //端口号
//        DatagramPacket dp = new DatagramPacket(bys,length,address,port);
        DatagramPacket dp = new DatagramPacket(bys,bys.length,InetAddress.getByName("172.21.122.115"),10086);

        //3:调用 Datagramsocket对象的方法发送数据
        /* void send (DatagramPacket p) 从此套接字发送数据报包 */
        ds.send(dp);

        //4:关闭发送端
        /* void close() 关闭此数据报套接字 */
        ds.close();
    }
}
```

```java
package cn.itrs1;
/*
	接收端
*/
import java.io.IOException;
import java.net.DatagramPacket;
import java.net.DatagramSocket;
import java.net.SocketException;

/*
    UDP接收数据的步骤
        1:创建接收端的 Socket对象( Datagramsocket)
        2:创建一个数据包,用于接收数据
        3:调用 DatagramSocket对象的方法接收数据
        4:解析数据包,并把数据在控制台显示
        5:关闭接收端
 */
public class ReceiveDemo {
    public static void main(String[] args) throws IOException {
        //1:创建接收端的 Socket对象( Datagramsocket)
        /* Datagramsocket(int port)构造数据报套接字并将其绑定到本地主机上的指定端口 */
        DatagramSocket ds = new DatagramSocket(10086);

        //2:创建一个数据包,用于接收数据
        /* Datagrampacket( byte[ buf, int Length)构造一个 Datagrampacket用于接收长度为 Length数据包 */
        byte[] bys = new byte[1024];
        DatagramPacket dp = new DatagramPacket(bys,bys.length);

        //3:调用 DatagramSocket对象的方法接收数据
        ds.receive(dp);

        //4:解析数据包,并把数据在控制台显示
        /* byte[] getData() 返回数据缓冲区 */
//        byte[] datas = dp.getData();
        /* int getlength()返回要发送的数据的长度或接收到的数据的长度 */
//        int len = dp.getLength();
//        String dataString = new String(datas,0,len);
//        System.out.println("数据是："+dataString);
        System.out.println("数据是："+new String(dp.getData(),0,dp.getLength()));

        //5:关闭接收端
        ds.close();
    }
}
```

==先运行接收端，再发送端，后关闭发送端运行窗口==



### 4.UDP通信程序练习

![](https://github.com/Continuers/Java/blob/main/picture/321.png)

```java
package cn.itrs2;
//发送端
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.net.DatagramPacket;
import java.net.DatagramSocket;
import java.net.InetAddress;
import java.net.SocketException;

/*
    UDP发送数据
        数据来自于键盘录入,直到输入的数据是886,发送数据结束
 */
public class SendDemo {
    public static void main(String[] args) throws IOException {
        //创建发送端的 Socket对象(Datagramsocket)
        DatagramSocket ds = new DatagramSocket();

        //自己封装键盘录入数据
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        String line;
        while ((line = br.readLine())!=null){
            //输入的数据是886，发送数据结束
            if ("886".equals(line)){
                break;
            }

            // 创建数据,并把数据打包
            byte[] bys = line.getBytes(); 
            DatagramPacket dp = new DatagramPacket(bys,bys.length, InetAddress.getByName("172.21.122.115"),12345);

            //调用 DatagramSocket对象的方法发送数据
            ds.send(dp);
        }

        // 关闭发送端
        ds.close();
    }
}
```

```java
package cn.itrs2;
//接收端
import java.io.IOException;
import java.net.DatagramPacket;
import java.net.DatagramSocket;
import java.net.SocketException;

/*
    UDP接收数据:
        因为接收端不知道发送端什么时候停止发送,故采用死循环接收
 */
public class ReceiveDemo {
    public static void main(String[] args) throws IOException {
        // 创建接收端的 Socket对象( Datagramsocket)
        DatagramSocket ds = new DatagramSocket(12345);

        while (true) {
            // 创建一个数据包,用于接收数据
            byte[] bys = new byte[1024];
            DatagramPacket dp = new DatagramPacket(bys, bys.length);

            // 调用 Datagramsocket对象的方法接收数据
            ds.receive(dp);

            // 解析数据包,并把数据在控制台显示
            System.out.println("数据是：" + new String(dp.getData(), 0, dp.getLength()));
        }

        // 关闭接收端
//        ds.close();
    }
}
```



## 3.TCP通信程序

### 1.TCP通信原理

![](https://github.com/Continuers/Java/blob/main/picture/322.png)

![](https://github.com/Continuers/Java/blob/main/picture/323.png)

### 2.TCP发送数据

![](https://github.com/Continuers/Java/blob/main/picture/324.png)

```java
package cn.itrs1;

import java.io.IOException;
import java.io.OutputStream;
import java.net.InetAddress;
import java.net.Socket;
import java.util.SortedMap;

/*
    TCP发送数据的步骤
        1:创建客户端的 Socket对象( Socket)
        2:获取输出流,写数据
        3:释放资源
 */
public class ClientDemo {
    public static void main(String[] args) throws IOException {
        //1:创建客户端的 Socket对象( Socket)
        /* Socket(Inetaddress address, int port)创建流套接字并将其连接到指定IP地址的指定端口号 */
//        Socket s = new Socket(InetAddress.getByName("172.21.122.115"),10000);
        /* Socket(String host, int port)创建流套接字并将其连接到指定主机上的指定端口号 */
        Socket s = new Socket("172.21.122.115",10000);

        //2:获取输出流,写数据
        /* OutputStream getOutputStream()返回此套接字的输出流 */
        OutputStream os = s.getOutputStream();
        os.write("hello,tcp,我来了".getBytes());

        //3:释放资源
        s.close();

    }
}
```

 

### 3.TCP接收数据

![](https://github.com/Continuers/Java/blob/main/picture/325.png)

```java
package cn.itrs1;

import java.io.IOException;
import java.io.OutputStream;
import java.net.InetAddress;
import java.net.Socket;
import java.util.SortedMap;

/*
    TCP发送数据的步骤
        1:创建客户端的 Socket对象( Socket)
        2:获取输出流,写数据
        3:释放资源
 */
public class ClientDemo {
    public static void main(String[] args) throws IOException {
        //1:创建客户端的 Socket对象( Socket)
        /* Socket(Inetaddress address, int port)创建流套接字并将其连接到指定IP地址的指定端口号 */
//        Socket s = new Socket(InetAddress.getByName("172.21.122.115"),10000);
        /* Socket(String host, int port)创建流套接字并将其连接到指定主机上的指定端口号 */
        Socket s = new Socket("172.21.122.115",10086);

        //2:获取输出流,写数据
        /* OutputStream getOutputStream()返回此套接字的输出流 */
        OutputStream os = s.getOutputStream();
        os.write("hello,tcp,我来了".getBytes());

        //3:释放资源
        s.close();
    }
}
```

```java
package cn.itrs1;

import java.io.IOException;
import java.io.InputStream;
import java.net.ServerSocket;
import java.net.Socket;

/*
    TCP接收数据的步骤
        1:创建服务器端的 Socket对象( Serversocket)
        2:获取输入流,读数据,并把数据显示在控制台
        3:释放资源
 */
public class ServerDemo {
    public static void main(String[] args) throws IOException {
        //1:创建服务器端的 Socket对象( Serversocket)
        /*  ServerSoket (int port) 创建绑定到指定端口的服务器套接字 */
        ServerSocket ss = new ServerSocket(10086);

        /* Socket accept() 侦听要连接到此套接字并接受它 */
        Socket s = ss.accept();

        //2:获取输入流,读数据,并把数据显示在控制台
        InputStream is = s.getInputStream();
        byte[] bys = new byte[1024];
        int len = is.read(bys);
        String data = new String(bys,0,len);
        System.out.println("数据是："+data);

        //3:释放资源
        s.close();
        ss.close();
    }
}
```



### 4.TCP 通信程序练习

#### ①

![](https://github.com/Continuers/Java/blob/main/picture/326.png)

```java
package cn.itrs2;

import java.io.IOException;
import java.io.InputStream;
import java.io.OutputStream;
import java.net.ServerSocket;
import java.net.Socket;

/*
    服务器：接收数据，给出反馈
 */
public class ServerDemo {
    public static void main(String[] args) throws IOException {
        // 创建服务器端的 Socket对象( Serversocket)
        ServerSocket ss = new ServerSocket(10086);

        // 监听客户端连接,返回一个 Socket对象
        Socket s = ss.accept();

        // 获取输入流,读数据,并把数据显示在控制台
        InputStream is = s.getInputStream();
        byte[] bys = new byte[1024];
        int len = is.read(bys);
        String data = new String(bys,0,len);
        System.out.println("服务器："+data);

        //给出反馈
        OutputStream os = s.getOutputStream();
        os.write("数据已收到".getBytes());

        // 释放资源
        ss.close();

        //服务器：hello,tcp,我来了
    }
}
```

```java
package cn.itrs2;

import java.io.IOException;
import java.io.InputStream;
import java.io.OutputStream;
import java.net.Socket;

/*
    客户端：发送数据，接收服务器反馈
 */
public class ClientDemo {
    public static void main(String[] args) throws IOException {
        //创建客户端的 Socket 对象(Socket)
        Socket s = new Socket("172.21.122.115",10086);

        //获取输出流，写数据
        OutputStream os = s.getOutputStream();
        os.write("hello,tcp,我来了".getBytes());

        //接收服务器反馈
        InputStream is = s.getInputStream();
        byte[] bys = new byte[1024];
        int len = is.read(bys);
        String data = new String(bys,0,len);
        System.out.println("客户端："+data);

        //释放资源
        s.close();

        //客户端：数据已收到
    }
}
```

#### ②

![](https://github.com/Continuers/Java/blob/main/picture/327.png)

```java
package cn.itrs3;

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStream;
import java.io.InputStreamReader;
import java.net.ServerSocket;
import java.net.Socket;

/*
    服务器: 接收到的数据在控制台输出
 */
public class ServerDemo {
    public static void main(String[] args) throws IOException {
        //创建服务器 Socket 对象
        ServerSocket ss = new ServerSocket(10086);

        //监听客户端的连接，返回一个对应的Socket对象
        Socket s = ss.accept();

        //获取输入流对象
//        InputStream is = s.getInputStream();
//        InputStreamReader isr = new InputStreamReader(is);
//        BufferedReader br = new BufferedReader(isr);
        BufferedReader br = new BufferedReader(new InputStreamReader(s.getInputStream()));
        String line;
        while ((line=br.readLine())!=null){
            System.out.println(line);
        }
        //释放资源
        ss.close();
    }
}
```

```java
package cn.itrs3;

import java.io.*;
import java.net.Socket;

/*
    客户端：数据来自于键盘的录入，直到输入的数据是886，发送数据结束
 */
public class ClientDemo {
    public static void main(String[] args) throws IOException {
        //创建客户端 Socket 对象
        Socket s = new Socket("172.21.122.115",10086);

        // s数据来自于键盘录入，直到输入数据是886，发送数据结束
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        //封装输出流对象
        BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(s.getOutputStream()));
        String line;
        while ((line=br.readLine())!=null){
            if ("886".equals(line)){
                break;
            }

            //获取输出流对象
            bw.write(line);
            bw.newLine();
            bw.flush();
        }
        //释放资源
        s.close();
    }
}
```

#### ③

![](https://github.com/Continuers/Java/blob/main/picture/328.png)

```java
package cn.itrs4;

import java.io.*;
import java.net.ServerSocket;
import java.net.Socket;

/*
    服务器：接收到的数据写入文本文件
 */
public class ServerDemo {
    public static void main(String[] args) throws IOException {
        //创建服务器 Socket 对象
        ServerSocket ss = new ServerSocket(10088);

        //监听客户端连接，返回一个对应的 Socket对象
        Socket s = ss.accept();

        //接收数据
        BufferedReader br = new BufferedReader(new InputStreamReader(s.getInputStream()));
        //把数据写入文本文件
        BufferedWriter bw = new BufferedWriter(new FileWriter("myThread\\a.txt"));

        String line;
        while ((line=br.readLine())!=null){
            bw.write(line);
            bw.newLine();
            bw.flush();
        }

        //释放资源
        bw.close();
        ss.close();
    }
}
```

```java
package cn.itrs4;

import java.io.*;
import java.net.Socket;
/*
    客户端：数据来自于键盘录入，直到输入的数据是886，发送数据结束
 */
public class ClientDemo {
    public static void main(String[] args) throws IOException {
        //创建客户端 Socket 对象
        Socket s = new Socket("172.21.122.115",10088);

        // 数据来自于键盘录入，直到输入数据是886，发送数据结束
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        //封装输出流对象
        BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(s.getOutputStream()));
        String line;
        while ((line=br.readLine())!=null){
            if ("886".equals(line)){
                break;
            }
            //获取输出流对象
            bw.write(line);
            bw.newLine();
            bw.flush();
        }
        //释放资源
        s.close();
    }
}
```

#### ④

![](https://github.com/Continuers/Java/blob/main/picture/329.png)

```java
package cn.itrs5;

import java.io.*;
import java.net.ServerSocket;
import java.net.Socket;

public class ServerDemo {
    public static void main(String[] args) throws IOException {
        //创建服务器 Socket 对象
        ServerSocket ss = new ServerSocket(10086);

        //监听客户端连接，返回一个对应的 Socket对象
        Socket s = ss.accept();

        //接收数据
        BufferedReader br = new BufferedReader(new InputStreamReader(s.getInputStream()));
        //把数据写入文本文件
        BufferedWriter bw = new BufferedWriter(new FileWriter("myThread\\Copy.java"));

        String line;
        while ((line=br.readLine())!=null){
            bw.write(line);
            bw.newLine();
            bw.flush();
        }

        //释放资源
        bw.close();
        ss.close();
    }
}
```

```java
package cn.itrs5;

import java.io.*;
import java.net.Socket;

/*
    客户端：数据来自于文本文件
 */
public class ClientDemo {
    public static void main(String[] args) throws IOException {
        //创建客户端 Socket 对象
        Socket s = new Socket("172.21.116.196",10086);

        //封装文本文件的数据
        BufferedReader br = new BufferedReader(new FileReader("myThread\\InetAddressDemo.java"));
        //封装输出流写数据
        BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(s.getOutputStream()));

        String line;
        while((line=br.readLine())!=null){
            bw.write(line);
            bw.newLine();
            bw.flush();
        }
        //释放资源
        br.close();
        s.close();
    }
}
```

#### ⑤

![](https://github.com/Continuers/Java/blob/main/picture/330.png)

```java
package cn.itrs6;

import java.io.*;
import java.net.ServerSocket;
import java.net.Socket;

public class ServerDemo {
    public static void main(String[] args) throws IOException {
        //创建服务器 Socket 对象
        ServerSocket ss = new ServerSocket(10086);

        //监听客户端连接，返回一个对应的 Socket对象
        Socket s = ss.accept();

        //接收数据
        BufferedReader br = new BufferedReader(new InputStreamReader(s.getInputStream()));
        //把数据写入文本文件
        BufferedWriter bw = new BufferedWriter(new FileWriter("myThread\\Copy.java"));

        String line;
        while ((line=br.readLine())!=null){ //等待读取数据
//            if ("exit".equals(line)){
//                break;
//            }
            bw.write(line);
            bw.newLine();
            bw.flush();
        }

//        System.out.println("Server");

        //给出反馈
        BufferedWriter bwServer = new BufferedWriter(new OutputStreamWriter(s.getOutputStream()));
        bwServer.write("文件上传成功");
        bwServer.newLine();
        bwServer.flush();

        //释放资源
        bw.close();
        ss.close();
    }
}
```

```java
package cn.itrs6;

import java.io.*;
import java.net.Socket;
/*
    客户端：数据来自于文本文件,接收服务器反馈
 */
public class ClientDemo {
    public static void main(String[] args) throws IOException {
        //创建客户端 Socket 对象
        Socket s = new Socket("172.21.116.196",10086);

        //封装文本文件的数据
        BufferedReader br = new BufferedReader(new FileReader("myThread\\InetAddressDemo.java"));
        //封装输出流写数据
        BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(s.getOutputStream()));

        String line;
        while((line=br.readLine())!=null){
            bw.write(line);
            bw.newLine();
            bw.flush();
        }

//        System.out.println("Client");

        //自定义结束标记
//        bw.write("exit");
//        bw.newLine();
//        bw.flush();

        //public void shutdownOutput()
        s.shutdownOutput();     //表示输出结束

        //接收服务器的反馈
        BufferedReader brClient = new BufferedReader(new InputStreamReader(s.getInputStream()));
        String data = brClient.readLine();  //等待读取数据
        System.out.println("服务器的反馈："+data);

        //释放资源
        br.close();
        s.close();
    }
}
```

#### ⑥

![](https://github.com/Continuers/Java/blob/main/picture/331.png)

```java
package cn.itrs7;

import java.io.*;
import java.net.Socket;

public class ServerThread implements Runnable {
    private Socket s;
    public ServerThread(Socket s) {
        this.s = s;
    }

    @Override
    public void run() {
        try {
            //接收数据写到文本文件
            BufferedReader br = new BufferedReader(new InputStreamReader(s.getInputStream()));
//            BufferedWriter bw = new BufferedWriter(new FileWriter("myTread\\Copy.java"));
            //解决名称冲突问题
            int count = 0;
            File file  = new File("myThread\\Copy["+count+"].java");
            while (file.exists()){
                count++;
                file  = new File("myThread\\Copy["+count+"].java");
            }
            BufferedWriter bw = new BufferedWriter(new FileWriter(file));

            String line;
            while ((line = br.readLine())!=null){
                bw.write(line);
                bw.newLine();
                bw.flush();
            }

            //给出反馈
            BufferedWriter bwServer = new BufferedWriter(new OutputStreamWriter(s.getOutputStream()));
            bwServer.write("文件上传成功");
            bwServer.newLine();
            bwServer.flush();

            //释放资源
            s.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

```java
package cn.itrs7;

import java.io.IOException;
import java.net.ServerSocket;
import java.net.Socket;

/*
    服务器：接收到的数据写入文本文件，给出反馈，代码用线程进行封装，为每一个客户端开启一个线程
 */
public class ServerDemo {
    public static void main(String[] args) throws IOException {
        //创建服务器 Socket 对象
        ServerSocket ss = new ServerSocket(10086);

        while(true) {
            //监听客户端连接，返回一个对应的 Socket 对象
            Socket s = ss.accept();
            //为每一个客户端开启一个线程
            new Thread(new ServerThread(s)).start();
        }
//        ss.close();
    }
}
```

```java
package cn.itrs7;

import java.io.*;
import java.net.Socket;

public class ClientDemo {
    public static void main(String[] args) throws IOException {
        //创建客户端 Socket 对象
        Socket s = new Socket("172.21.116.196",10086);

        //封装文本文件的数据
        BufferedReader br = new BufferedReader(new FileReader("myThread\\InetAddressDemo.java"));
        //封装输出流写数据
        BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(s.getOutputStream()));

        String line;
        while((line=br.readLine())!=null){
            bw.write(line);
            bw.newLine();
            bw.flush();
        }

//        System.out.println("Client");

        //自定义结束标记
//        bw.write("exit");
//        bw.newLine();
//        bw.flush();

        //public void shutdownOutput()
        s.shutdownOutput();     //表示输出结束

        //接收服务器的反馈
        BufferedReader brClient = new BufferedReader(new InputStreamReader(s.getInputStream()));
        String data = brClient.readLine();  //等待读取数据
        System.out.println("服务器的反馈："+data);

        //释放资源
        br.close();
        s.close();
    }
}
```



# 34.Lambda 表达式

## 1.函数式编程思想概述

![](https://github.com/Continuers/Java/blob/main/picture/332.png)

## 2.体验 Lambda 表达式

![](https://github.com/Continuers/Java/blob/main/picture/333.png)

```java
//package edu.itrs1;
//
//public class MyRunnable implements Runnable{
//    @Override
//    public void run() {
//        System.out.println("多线程程序启动了");
//    }
//}
```

```java
package edu.itrs1;
/*
    需求：启动一个线程，在控制台输出一句话，多线程程序启动了
 */
public class LambdaDemo {
    public static void main(String[] args) {
        //实现类的方式实现需求
//        MyRunnable my = new MyRunnable();
//        Thread t = new Thread(my);
//        t.start();

        //匿名内部类的方式改进
//        new Thread(new Runnable() {
//            @Override
//            public void run() {
//                System.out.println("多线程程序启动了");
//            }
//        }).start();

        //Lambda表达式的方式改进
        new Thread(()->{
            System.out.println("多线程程序启动了");
        }).start();


    }
}
```

## 3.Lambda 表达式的标准格式

![](https://github.com/Continuers/Java/blob/main/picture/334.png)

![](https://github.com/Continuers/Java/blob/main/picture/335.png)

## 4.Lambda 表达式的练习

### Ⅰ

![](https://github.com/Continuers/Java/blob/main/picture/336.png)

```java
package edu.itrs2;

public interface Eatable {
    void eat();
}
```

```java
package edu.itrs2;

public class EatableImpl implements Eatable{
    @Override
    public void eat() {
        System.out.println("越努力，越幸运");
    }
}
```

```java
package edu.itrs2;

public class EatableDemo {
    public static void main(String[] args) {
        //在主方法中调用useEatable方法
        Eatable e = new EatableImpl();
        useEatable(e);

        //匿名内部类
        useEatable(new Eatable() {
            @Override
            public void eat() {
                System.out.println("越努力，越幸运");
            }
        });

        //Lambda表达式
        useEatable(()->{
            System.out.println("越努力，越幸运");
        });
    }

    private static void useEatable(Eatable e){
        e.eat();
    }
}
```

### Ⅱ

![](https://github.com/Continuers/Java/blob/main/picture/337.png)

```java
package edu.itrs3;

public interface Flyable {
    void fly(String s);
}
```

```java
package edu.itrs3;

public class FlyableDemo {
    public static void main(String[] args) {
        //在主方法中调用 useFlyable 方法
        //匿名内部类
        useFlyable(new Flyable() {
            @Override
            public void fly(String s) {
                System.out.println(s);
                System.out.println("越努力，越幸运");
            }
        });
        System.out.println();

        //lambda
        useFlyable((String s)->{
            System.out.println(s);
            System.out.println("越努力，越幸运");
        });
    }

    private static void useFlyable(Flyable f){
        f.fly("加油");
    }
}
```

### Ⅲ

![](https://github.com/Continuers/Java/blob/main/picture/338.png)

```java
package edu.itrs4;

public interface Addable {
    int add(int x, int y);
}
```

```java
package edu.itrs4;

public class AddableDemo {
    public static void main(String[] args) {
        //
        useAddable((int x, int y) -> {
            return x + y;
//            return x-y;
        });
    }

    private static void useAddable(Addable a) {
        int sum = a.add(10, 20);
        System.out.println(sum);
    }
}
```

## 5.Lambda表达式的省略模式

![](https://github.com/Continuers/Java/blob/main/picture/339.png)

```java
package edu.itrs5;

public interface Addable {
    int add(int x, int y);
}
```

```java
package edu.itrs5;

public interface Flyable {
    void fly(String s);
}
```

```java
package edu.itrs5;

/*
    Lambda 表达式的省略模式
 */
public class LambdaDemo {
    public static void main(String[] args) {
//        useAddable((int x,int y)->{
//            return x+y;
//        });
        //参数的类型可以省略
//        useAddable((x, y) -> {
//            return x + y;
//        });
        //但是有多个参数的情况下，不能只省略一个
//        useAddable((x,int y)->{
//            return x+y;
//        });

//        useFlyable((String s) -> {
//            System.out.println(s);
//        });

//        useFlyable((s) -> {
//            System.out.println(s);
//        });
        //如果参数有且仅有一个，那么小括号可以省略
//        useFlyable(s -> {
//            System.out.println(s);
//        });

        //如果代码块的语句只有一条，可以省略大括号和分号
//        useFlyable(s -> System.out.println(s));

        //如果代码块的语句只有一条，可以省略大括号和分号。
        //如果有return，return也要省略掉
        useAddable((x, y) -> x + y);
    }

    private static void useFlyable(Flyable f) {
        f.fly("越努力，越幸运");
    }

    private static void useAddable(Addable a) {
        int sum = a.add(10, 20);
        System.out.println(sum);
    }
}
```

## 6.Lambda 表达式的注意事项

![](https://github.com/Continuers/Java/blob/main/picture/340.png)

```java
package edu.itrs6;

public interface Inter {
    void show();

//    void method();
}
```

```java
package edu.itrs6;
/*
    Lambda表达式的注意事项
 */
public class LambdaDemo {
    public static void main(String[] args) {
//        useInter(()->{
//            System.out.println("越努力，越幸运");
//        });

        /* 使用Lambda必须要有接口，并且要求接口有且仅有一个抽象方法 */
        useInter(()-> System.out.println("越努力，越幸运"));

        /* 必须有上下文环境，才能推导出Lambda对应的接口 */
//        new Thread(new Runnable() {
//            @Override
//            public void run() {
//                System.out.println("匿名内部类");
//            }
//        }).start();

//        Runnable r = () -> System.out.println("Lambda表达式");
//        new Thread(r).start();

        new Thread(() -> System.out.println("Lambda表达式")).start();

    }

    private static void useInter(Inter i){
        i.show();
    }
}
```



## 7.Lambda表达式和匿名内部类的区别

![](https://github.com/Continuers/Java/blob/main/picture/341.png)

```java
package edu.itrs7;

public interface Inter {
    void show();
//    void show2();
}
```

```java
package edu.itrs7;

public abstract class Animal {
    public abstract void method();
}
```

```java
package edu.itrs7;

public class Student {
    public void study(){
        System.out.println("越努力，越幸运");
    }
}
```

```java
package edu.itrs7;
/*
    Lambda表达式和匿名内部类的区别
 */
public class LambdaDemo {
    public static void main(String[] args) {
        //匿名内部类
        /*
        useInter(new Inter() {
            @Override
            public void show() {
                System.out.println("接口");
            }
        });

        useAnimal(new Animal() {
            @Override
            public void method() {
                System.out.println("抽象类");
            }
        });

        useStudent(new Student(){
            @Override
            public void study() {
                System.out.println("具体类");
            }
        });
        */

        useInter(new Inter() {
            @Override
            public void show() {
                System.out.println("接口");
            }
        });

        //
//        useInter(()-> System.out.println("接口"));      //√
//        useAnimal(()-> System.out.println("抽象类"));    //×
//        useStudent(()-> System.out.println("具体类"));   //×

        /*
        useInter(new Inter() {
            @Override
            public void show() {
                System.out.println("show");
            }

            @Override
            public void show2() {
                System.out.println("show2");
            }       //不输出
        });
        */
    }

    private static void useStudent(Student s){
        s.study();
    }

    private static void useAnimal(Animal a){
        a.method();
    }

    private static void useInter(Inter i){
        i.show();
    }
}
```

# 35.接口组成更新

## 1.接口组成更新概述

![](https://github.com/Continuers/Java/blob/main/picture/342.png)

## 2.接口中默认方法

![](https://github.com/Continuers/Java/blob/main/picture/343.png)

```java
package edu.itrs8;
/* 接口类 */
public interface MyInterface {
    void show1();

    void show2();

//    void show3();

//    public default void show3(){
//        System.out.println("show3");
//    }

    default void show3(){
        System.out.println("show3");
    }
}
```

```java
package edu.itrs8;
/* 接口类 */
public interface MyinterfaceSon extends MyInterface{
//    void show3();
}
```

```java
package edu.itrs8;

/*
    需求:
        1:定义一个接口 Myinterface,里面有两个抽象方法:
            void show1();
            void show2();
        2:定义口的两个实现类:
            MyInterfaceImplOne
            MyInterfaceImplTwo
        3:定义测试类:
            MyinterfaceDemo
            在主方法中,按照多态的方式创建对家并使用
 */
public class MyinterfaceDemo {
    public static void main(String[] args) {
        //按照多态的方式创建对家并使用
        MyInterface my = new MyInterfaceImplOne();
        my.show1();
        my.show2();
        my.show3();
    }
}
```

```java
package edu.itrs8;

public class MyInterfaceImplOne implements MyInterface {
    @Override
    public void show1() {
        System.out.println("One show1");
    }

    @Override
    public void show2() {
        System.out.println("One show2");
    }

    @Override
    public void show3() {
        System.out.println("One show3");
    }
}
```

```java
package edu.itrs8;

public class MyInterfaceImplTwo implements MyInterface{
    @Override
    public void show1() {
        System.out.println("Two show1");
    }

    @Override
    public void show2() {
        System.out.println("Two show2");
    }
}
```



## 3.接口中静态方法

![](https://github.com/Continuers/Java/blob/main/picture/344.png)

```java
package edu.itrs9;

public interface Inter {
    void show();
    default void method(){
        System.out.println("Inter 中的默认方法执行");
    }

//    public static void test(){
//        System.out.println("Inter 中的静态方法执行");
//    }

    static void test(){
        System.out.println("Inter 中的静态方法执行");
    }
}
```

```java
package edu.itrs9;

public interface Flyable {
    public static void test(){
        System.out.println("Flyable 中的静态方法执行");
    }
}
```

```java
package edu.itrs9;

public class InterImpI implements Inter,Flyable{
    @Override
    public void show() {
        System.out.println("show 方法执行");
    }
}
```

```java
package edu.itrs9;
/*
    需求:
        1:定义一个接口 Inter,里面有三个方法:一个是抽象方法,一个是默认方法,一个是静态方法
            void show();
            default void method(){}
            public static void test(){}
        2:定义接口的一个实现类:
            Interimpl
        3:定义测试类:
            InterDeme
            在主方法中,按照多态的方式创建对象并使用
 */
public class InterDemo {
    public static void main(String[] args) {
        //按照多态的方式创建对象并使用
        Inter i = new InterImpI();
        i.show();
        i.method();
//        i.test();

        Inter.test();
//        InterImpI/test();
        Flyable.test();
    }
}
```



## 4.接口中私有方法

![](https://github.com/Continuers/Java/blob/main/picture/345.png)



```java
package edu.itrs10;

public class InterImpl implements Inter{
}
```

```java
package edu.itrs10;

public interface Inter {
    default void show1(){
        System.out.println("show1开始执行");
//        System.out.println("初级工程师");
//        System.out.println("中级工程师");
//        System.out.println("高级工程师");
//        show();
        method();
        System.out.println("show1结束执行");
    }
    default void show2(){
        System.out.println("show2开始执行");
//        show();
        method();
        System.out.println("show2结束执行");
    }

    private void show(){
        System.out.println("初级工程师");
        System.out.println("中级工程师");
        System.out.println("高级工程师");
    }

    static void method1(){
        System.out.println("method1开始执行");
//        System.out.println("初级工程师");
//        System.out.println("中级工程师");
//        System.out.println("高级工程师");
//        show();   静态方法帮你调用静态方法
        method();
        System.out.println("method1结束执行");
    }
    static void method2(){
        System.out.println("method2开始执行");
//        System.out.println("初级工程师");
//        System.out.println("中级工程师");
//        System.out.println("高级工程师");
        method();
        System.out.println("method2结束执行");
    }

    private static void method(){
        System.out.println("初级工程师");
        System.out.println("中级工程师");
        System.out.println("高级工程师");
    }
}
```

```java
package edu.itrs10;
/*
    需定：
        1.定义一个接口 Inter,里面有四个方法:二个默认方法,二个静态方法
            default void show1(){}
            default void show2(){}
            static void method1(){}
            static void method2(){}
        2:定义接口的一个实现类:
            Interimpl
        3:定义测试类
            InterDemo
            在主方法中,按照多态的方式创建对象并使用
 */
public class InterDemo {
    public static void main(String[] args) {
        //按照多态的方式创建对象并使用
        Inter i = new InterImpl();
        i.show1();
        System.out.println("-----------");
        i.show2();
        System.out.println("-----------");

        Inter.method1();
        System.out.println("-----------");
        Inter.method2();

    }
}
```



# 36.方法引用

## 1.体验方法引用

![](https://github.com/Continuers/Java/blob/main/picture/346.png)

```java
package gov.itrs1;

public interface Printable {
    void printString(String s);
}
```

```java
package gov.itrs1;
/*
    需求
        1:定义一个接口( Printable):里面定义一个抽象方法: void printstring( String s)
        2.定义一个测试类( PrintableDemo),在测试类中提供两个方法
        一个方法是: useprintable( Printable p)
        一个方法是主方法,在主方法中调用 useprintable方法
 */
public class PrintableDemo {
    public static void main(String[] args) {
        //在主方法中调用 useprintable方法

//        usePrintable((String s)->{
//            System.out.println(s);
//        });

        /* 优化 */
        usePrintable(s -> System.out.println(s));

//        System.out.println("越努力，越幸运");

        /* 方法引用符:    :: */
        usePrintable(System.out::println);

        /* 可推导的就是可省略的 */

    }

    private static void usePrintable(Printable p){
        p.printString("越努力，越幸运");
    }
}
```



## 2.方法引用符	::

![](https://github.com/Continuers/Java/blob/main/picture/347.png)

```java
package gov.itrs2;

public interface Printable {
    void printInt(int i);
}
```

```java
package gov.itrs2;
/*
    需求:
        1:定义一个接口(Printable):里面定义一个抽象方法: void printint(int i);
        2:定义一个测试类(Printabledemo),在测试类中提供两个方法
            一个方法是: usePrintable(Printable p)
            一个方法是主方法,在主方法中调用 usePrintable方法
 */
public class PrintableDemo {
    public static void main(String[] args) {
        //在主方法中调用 usePrintable方法
        usePrintable(i-> System.out.println(i));

        /* 方法引用 */
        usePrintable(System.out::println);
    }

    private static void usePrintable(Printable p){
        p.printInt(666);
    }
}
```



## 3.Lambda 表达式支持的方法引用

![](https://github.com/Continuers/Java/blob/main/picture/348.png)

## 4.引用类方法

![](https://github.com/Continuers/Java/blob/main/picture/349.png)

```java
package gov.itrs3;

public interface Converter {
    int convert(String s);
}
```

```java
package gov.itrs3;

/*
    练习:
        定义一个接口(Converter),里面定义一个抽象方法
            int convert(String s);
        定义一个测试类(Converterdemo),在测试类中提供两个方法
            一个方法是: useConverter(Converter c)
            一个方法是主方法,在主方法中调用 useConverter方法
 */
public class ConverterDemo {
    public static void main(String[] args) {
        //在主方法中调用 useConverter方法

//        useConverter((String s)->{
//            return Integer.parseInt(s);
//        });

        /* 优化 */
        useConverter(s->Integer.parseInt(s));

        //引用类方法
        useConverter(Integer::parseInt);

        //Lambda 表达式被类方法替代的时候，它的形式参数全部传递给静态方法作为参数
    }

    private static void useConverter(Converter c){
        int number = c.convert("666");
        System.out.println(number);
    }
}
```

## 5.引用对象的实例方法

![](https://github.com/Continuers/Java/blob/main/picture/350.png)

```java
package gov.itrs4;

public interface Printer {
    void printUpperCase(String s);
}
```

```java
package gov.itrs4;

public class PrintString {
    //把字符串参数变成大写的数据,然后在控制台输出
    public void printUpper(String s){
        String result = s.toUpperCase();
        System.out.println(result);
    }
}
```

```java
package gov.itrs4;
/*
    练习
        1.定义一个类(PrintString),里面定义一个方法
            public void printuppert(String s):把字符串参数变成大写的数据,然后在控制台输出
        2.定义一个接口(Printer),里面定义一个抽象方法
            void printUpperCase(String s)
        3.定义一个测试类( Printerdemo),在测试类中提供两个方法
            一个方法是: usePrinter(Printer p)
            一个方法是主方法,在主方法中调用 usePrinter方法
 */
public class PrinterDemo {
    public static void main(String[] args) {
        //在主方法中调用 usePrinter方法

//        usePrinter((String s)->{
////            String result = s.toUpperCase();
////            System.out.println(result);
//            System.out.println(s.toUpperCase());
//        });

        //Lambda 表达式实现
        usePrinter(s-> System.out.println(s.toUpperCase()));

        //引用对象的实例方法
        PrintString ps = new PrintString();
        usePrinter(ps::printUpper);

        //Lambda 表达式被对象的实例方法替代的时候，它的形式参数全部传递给该方法作为参数
    }

    private static void usePrinter(Printer p){
        p.printUpperCase("HelloWorld");
    }
}
```

## 6.引用类的实例方法

![](https://github.com/Continuers/Java/blob/main/picture/351.png)

```java
package gov.itrs5;
/* 接口 */
public interface MyString {
    String mySubString (String s, int x, int y);
}
```

```java
package gov.itrs5;
/*
    1.定义一个接口(MyString),里面定义一个抽象方法
        String mySubString (String s, int x, int y);
    2.定义一个测试类(MyStringDemo),在测试类中提供两个方法
        一个方法是: useMyString(MyString my)
    一个方法是主方法,在主方法中调用 useMyString方法
 */
public class MyStringDemo {
    public static void main(String[] args) {
        //在主方法中调用 useMyString方法

//        useMyString((String s,int x,int y)->{
//            return s.substring(x,y);
//        });

        /*  优化 */
        useMyString((s,x,y)->s.substring(x,y));

        //引用类的实例方法
        useMyString(String::substring);

        //Lambda 表达式被类的实例方法替代的时候
        //第一个参数作为调用者
        //后面的参数全部传递给该方法作为参数
    }

    private static void useMyString(MyString my){
        String s = my.mySubString("Helloworld",2,5);
        System.out.println(s);
    }
}
```

## 7.引用构造器

![](https://github.com/Continuers/Java/blob/main/picture/352.png)

```java
package gov.itrs6;

public interface StudentBuilder {
    Student build(String name, int age);
}
```

```java
package gov.itrs6;

public class Student {
    private String name;
    private int age;

    public Student() {
    }

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}
```

```java
package gov.itrs6;
/*
    练习
        定义一个类(Student),里面有两个成员变量(name,age)
            并提供无参构造方法和带参构造方法,以及成员变量对应的 get和 set方法
        定义一个接口(StudentBuilder),里面定义一个抽象方法
            Student build(String name, int age);
        定义一个测试类( Student Demo),在测试类中提供两个方法
            一个方法是: useStudentBuilder(StudentBuilder s)
            一个方法是主方法,在主方法中调用 useStudentBuilder方法
 */
public class StudentDemo {
    public static void main(String[] args) {
        //在主方法中调用 useStudentBuilder方法

        /*
        useStudentBuilder((String name,int age)->{
//            Student s = new Student(name,age);
//            return s;
            return new Student(name,age);
        });
        */

//        useStudentBuilder((name,age)->new Student(name,age));

        //引用构造器
        useStudentBuilder(Student::new);

        //Lambda 表达式被构造器替代的时候，它的形式参数全部传递给构造器作为参数

    }
    private static void useStudentBuilder(StudentBuilder sb){
        Student s = sb.build("java",11);
        System.out.println(s.getName()+","+s.getAge());
    }
}
```



# 37.函数式接口

## 1.函数式接口概述

![](https://github.com/Continuers/Java/blob/main/picture/353.png)

```java
package mil.itrs1;
/* 函数式接口 */

@FunctionalInterface
public interface MyInterface {
    void show();

//    void method();    //函数式接口有且仅有一个抽象方法
}
```

```java
package mil.itrs1;
/*
    函数式接口：有且仅有一个抽象方法的接口
 */
public class MyInterfaceDemo {
    public static void main(String[] args) {
        MyInterface my = () -> System.out.println("函数式接口");
        my.show();
    }
}
```

## 2.函数式接口作为方法的参数

![](https://github.com/Continuers/Java/blob/main/picture/354.png)

```java
package mil.itrs1;
/*
    定义一个类(RunnableDemo),在类中提供两个方法
        一个方法是: startThread(Runnable r)
            方法参数 Runnable是一个函数式接口
        一个方法是主方法,在主方法中调用 startThread方法
 */
public class RunnableDemo {
    public static void main(String[] args) {
        //在主方法中调用 startThread方法

        //匿名内部类的方式
        startThread(new Runnable() {
            @Override
            public void run() {
                System.out.println(Thread.currentThread().getName()+"线程启动了");
            }
        });

        //Lambda 表达式
        startThread(()-> System.out.println(Thread.currentThread().getName()+"线程启动了"));
    }

    private static void startThread(Runnable r){
//        Thread t = new Thread(r);
//        t.start();
        new Thread(r).start();
    }
}
```

## 3.函数式接口作为方法的返回值

![](https://github.com/Continuers/Java/blob/main/picture/355.png)

```java
package mil.itrs2;

import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;

/*
    定义一个类(ComparatorDemo),在类中提供两个方法
        一个方法是: Comparator<String> getcomparator()
            方法返回值 Comparator是一个函数式接口
        一个方法是主方法,在主方法中调用 getComparator方法
 */
public class ComparatorDemo {
    public static void main(String[] args) {
        //构造使用场景

        //定义集合，存储字符串元素
        ArrayList<String> array = new ArrayList<String>();

        array.add("aaaa");
        array.add("bbb");
        array.add("cc");
        array.add("d");

        System.out.println("排序前："+array);

//        Collections.sort(array);
        Collections.sort(array,getComparator());

        System.out.println("按照长度排序后："+array);

    }

    private static Comparator<String> getComparator(){
        //匿名内部类的方式实现
//        Comparator<String> comp = new Comparator<String>() {
//            @Override
//            public int compare(String s1, String s2) {
//                return s1.length()-s2.length();
//            }
//        };
//        return comp

//        return new Comparator<String>() {
//            @Override
//            public int compare(String s1, String s2) {
//                return s1.length() - s2.length();
//            }
//        };

//        return (String s1,String s2)->{
//            return s1.length()-s2.length();
//        };

        return (s1,s2)-> s1.length()-s2.length();
    }
}
```

## 4.常用的函数式接口

![](https://github.com/Continuers/Java/blob/main/picture/356.png)

## 5.Supplier 接口

![](https://github.com/Continuers/Java/blob/main/picture/357.png)

```java
package mil.itrs2;

import java.util.function.Supplier;

/*
    Supplier<T>:包含一个无参的方法
        T get():获得结果
        该方法不需要参数,它会按照某种实现逻辑(由 Lambda表达式实现)返回一个数据
        Supplier<T>接口也被称为生产型接口,如果我们指定了接口的泛型是什么类型,那么接口中的 get方法就会生产什么类型的数据供我们使用
 */
public class SupplierDemo {
    public static void main(String[] args) {
//        String s = getString(()->{
//            return "广东";
//        });

        String s = getString(()->"广东");

        System.out.println(s);

        Integer i = getInteger(()-> 11);
        System.out.println(i);
    }

    //定义一个方法，返回一个字符串数据
    private static Integer getInteger(Supplier<Integer> sup){
        return sup.get();
    }

    //定义一个方法，返回一个字符串数据
    private static String getString(Supplier<String> sup){
        return sup.get();
    }
}
```

### 练习

![](https://github.com/Continuers/Java/blob/main/picture/358.png)

```java
package mil.itrs2;

import java.util.function.Supplier;

/*
    练习
        定义一个类(SupplierTest,在类中提供两个方法
            一个方法是: int getMax(Supplier<Integer> sup)
                用于返回个int数组中的最大值
            一个方法是主方法,在主方法中调用 getMax方法
 */
public class SupplierTest {
    public static void main(String[] args) {
        //定义一个 int 数组
        int[] arr = {19,50,90,58,43};

        int maxValue = getMax(()->{
           int max = arr[0];

           for (int i=1;i<arr.length;i++){
               if (arr[i]>max){
                   max = arr[i];
               }
           }
           return max;
        });
        System.out.println(maxValue);
    }

    //返回个int数组中的最大值
    private static int getMax(Supplier<Integer> sup){
        return sup.get();
    }
}
```

## 6.Consumer 接口

![](https://github.com/Continuers/Java/blob/main/picture/359.png)

```java
package mil.itrs3;

import java.util.function.Consumer;

/*
    Consumer<T>:包含两个方法
        void accept(T t):对给定的参数执行此操作
        default Consumer<T> and Then( Consumer after):
            返回个组合的 Consumer,依次执行此操作,然后执行 after操作
        Consumer<T>接口也被称为消费型接口,它消费的数据的数据类型由泛型指定
 */
public class ConsumerDemo {
    public static void main(String[] args) {
//        operatorString("广东",(String s)->{
//            System.out.println(s);
//        });

        operatorString("广东",s-> System.out.println(s));
//        operatorString("广东",System.out::println);

//        operatorString("广东",s->{
//            System.out.println(new StringBuilder(s).reverse().toString());
//        });

        operatorString("广东",s-> System.out.println(new StringBuilder(s).reverse().toString()));
        System.out.println("-----------------------");

        operatorString("广东理工职业学院",s-> System.out.println(s),s-> System.out.println(new StringBuilder(s).reverse().toString()));
    }

    //定义一个方法，用不同的方式消费同一个字符串数据俩次
    private static void operatorString(String name, Consumer<String> con1, Consumer<String> con2){
//        con1.accept(name);
//        con2.accept(name);
        con1.andThen(con2).accept(name);
    }


    //定义一个方法，消费一个字符串数据
    private static void operatorString(String name, Consumer<String> con){
        con.accept(name);
    }
}
```

### 练习

![](https://github.com/Continuers/Java/blob/main/picture/360.png)

```Java
package mil.itrs3;

import java.util.function.Consumer;

/*
    String[] strArray={"姓名,年龄","姓名,年龄","姓名,年龄"};
    字符串数组中有多条信息,请按照格式:“姓名:XX年龄:XX"的格式将信息打印出来
    要求
        把打印姓名的动作作为第一个 Consumer接口的 Lambda实例
        把打印年龄的动作作为第二个 Consumer接口的 Lambda实例
        将两个 Consumer接口按照顺序组合到一起使用
 */
public class ConsumerTest {
    public static void main(String[] args) {
        String[] strArray = {"黑马,66", "播妞,99", "itrs,20"};

        /*
        printInfo(strArray, (String str) -> {
            String name = str.split(",")[0];
            System.out.print("姓名:" + name);
        }, (String str) -> {
            int age = Integer.parseInt(str.split(",")[1]);
            System.out.println(",年龄:" + age);
        });
        */

        printInfo(strArray,str-> System.out.print("姓名："+str.split(",")[0]),str -> System.out.println(",年龄:"+Integer.parseInt(str.split(",")[1])));

    }

    private static void printInfo(String[] strArray, Consumer<String> con1, Consumer<String> con2) {
        for (String str : strArray) {
            con1.andThen(con2).accept(str);
        }
    }
}
```

## 7.Predicate 接口

![](https://github.com/Continuers/Java/blob/main/picture/361.png)

```java
package mil.itrs4;

import java.util.function.Predicate;

/*
    Predicate<T>:常用的四个方法
        boolean test(T t)。对给定的参数进行判断(判断辺辑由 Lambda表达式实现),返回一个布尔值
        default Predicate<r> negate():返回一个遷辑的否定,对应還辑非
        Predicate<T>接口通常用于判断参数是否满足指定的条件
 */
public class PredicateDemo01 {
    public static void main(String[] args) {
        /*boolean b1 = checkString("hello",(String s)->{
           return s.length()>8;
        });*/

        boolean b1 = checkString("hello", s -> s.length() > 8);
        System.out.println(b1);

        boolean b2 = checkString("helloworld", s -> s.length() > 8);
        System.out.println(b2);
    }

    //判断给定的字符串是否满足要求
    private static boolean checkString(String s, Predicate<String> pre) {
//        return pre.test(s);
//        return !pre.test(s);
        return pre.negate().test(s);
    }
    /*
        源码：
        default Predicate<T> negate() {
            return (t) -> !test(t);
        }
     */
}
```

```java
package mil.itrs4;

import java.util.function.Predicate;

/*
    Predicate<T>
        default Predicate<T> and ( Predicate other):返回一个组合判断,对应短路与
        default Predicate<T> or ( Predicate other):返回一个组合判断,对应短路或
 */
public class PredicateDemo02 {
    public static void main(String[] args) {
        boolean b1 = checkString("hello", s -> s.length() > 8);
        System.out.println(b1);
        boolean b2 = checkString("helloworld", s -> s.length() > 8);
        System.out.println(b2);

        boolean b3 = checkString("hello", s -> s.length() > 8, s -> s.length() < 15);
        System.out.println(b3);

        boolean b4 = checkString("helloworld",s->s.length()>8,s->s.length()<15);
        System.out.println(b4);
    }

    //同一个字符串给岀两个不同的判断条件,最后把这两个判断的结果做逻辑与运算的结果作为最终的结果
    private static boolean checkString(String s, Predicate<String> pre1, Predicate<String> pre2) {
//        boolean b1 = pre1.test(s);
//        boolean b2 = pre2.test(s);
//        boolean b = b1 && b2;
//        return b;

//        return pre1.and(pre2).test(s);
        return pre1.or(pre2).test(s);
    }

    //判断给定的字符串是否满足要求
    private static boolean checkString(String s, Predicate<String> pre) {
        return pre.test(s);
    }

}
```

### 练习

![](https://github.com/Continuers/Java/blob/main/picture/362.png)

```java
package mil.itrs4;

import java.util.ArrayList;
import java.util.function.Predicate;

/*
    练习
    String[] strArray={"林青霞,30","柳岩,34"张曼玉,35,"貂蝉31","王祖贤33"};
    字符串数组中有多条信息,请通过 Predicate接口的拼装将符合要求的字符串筛选到集合 Arraylist中,并遍历 Arraylist集合
    要求：同时满足如下要求:
        1.姓名长度大于
        2;年龄大于33
    分析：
        1.有两个判断条件所以需要使用两个 Predicate接囗对条件进行判断
        2.必须同时满足两个条件所以可以使用and方法连接两个判断条件
 */
public class PredicateTest {
    public static void main(String[] args) {
        String[] strArray={"林青霞,30","柳岩,34","张曼玉,35","貂蝉,31","王祖贤,33"};

        ArrayList<String> array = myFilter(strArray,s->s.split(",")[0].length()>2,
                s->Integer.parseInt(s.split(",")[1])>33);

        for (String str:array){
            System.out.println(str);
        }

    }
    //通过 Predicate接口的拼装将符合要求的字符串筛选到集合 Arraylist中
    private static ArrayList<String> myFilter(String[] strArray, Predicate<String> pre1,Predicate<String> pre2){
        //定义一个集合
        ArrayList<String> array = new ArrayList<String>();

        //遍历数组
        for (String str : strArray){
            if (pre1.and(pre2).test(str)){
                array.add(str);
            }
        }
        return array;
    }
}
```



## 8.Function 接口

![](https://github.com/Continuers/Java/blob/main/picture/363.png)

```java
package mil.itrs5;

import java.util.function.Function;

/*
    Function<T,R>:常用的两个方法
        R aaply(T t):将此函数应用于给定的参数
        default<V> Function andthen( Function after):返回一个组合函数,首先将该函数应用于输入,然后将 after函数应用于结
        Function<T,R>接口通常用于对参数进行处理,转换(处理逻辑由 Lambda表达式实现),然后返回一个新的值
 */
public class FunctionDemo {
    public static void main(String[] args) {
//        convert("100",(String s)->{
//            return Integer.parseInt(s);
//        });

        convert("100",s->Integer.parseInt(s));
//        convert("100",Integer::parseInt);

        convert(100,i->String.valueOf(i+566));

        convert("100",s->Integer.parseInt(s),i->String.valueOf(i+566));
    }
    //定义一个方法,把一个字符串转换 int类型,在控制台输出
    private static void convert(String s, Function<String,Integer> fun){
//        Integer i = fun.apply(s);
        int i = fun.apply(s);
        System.out.println(i);
    }

    //定义一个方法,把一个 int类型的数据加上一个整数之后,转为字符串在控制台输出
    public static void convert(int i,Function<Integer,String> fun){
        String s = fun.apply(i);
        System.out.println(s);
    }

    //定义一个方法,把一个字符串转换 int类型,把int类型的数据加上一个整数之后,转为字符串在控制台输出
    private static void convert(String s,Function<String,Integer> fun1,Function<Integer,String> fun2){
//        Integer i = fun1.apply(s);
//        String ss = fun2.apply(i);
//        System.out.println(ss);

        String ss = fun1.andThen(fun2).apply(s);
        System.out.println(ss);
    }
}
```

### 练习

![](https://github.com/Continuers/Java/blob/main/picture/364.png)

```java
package mil.itrs5;

import java.util.function.Function;

/*
    Strings="林青霞,30";
    请按照我指定的要求进行操作
        1:将字符串截取得到数字年龄部分
        2:将上一步的年龄字符串转换成为 int类型的数据
        3:将上一步的 int数据加 70,得到个 int结果,在控制台输出
    请通过 Function接口来实现函数拼接
 */
public class FunctionTest {
    public static void main(String[] args) {
        String s = "彭于晏,30";

        /*
        convert(s, (String ss) -> {
            return s.split(",")[1];
        }, (String ss) -> {
            return Integer.parseInt(ss);
        }, (Integer i) -> {
            return i + 70;
        });
        */

//        convert(s, ss -> ss.split(",")[1], ss -> Integer.parseInt(ss), i -> i + 70);
        convert(s, ss -> ss.split(",")[1], Integer::parseInt, i -> i + 70);
    }

    public static void convert(String s, Function<String, String> fun1, Function<String, Integer> fun2, Function<Integer, Integer> fun3) {
//        Integer i = fun1.andThen(fun2).andThen(fun3).apply(s);
        int i = fun1.andThen(fun2).andThen(fun3).apply(s);
        System.out.println(i);
    }
}
```



# 38.Stream流

## 1.体验Stream流

![](https://github.com/Continuers/Java/blob/main/picture/365.png)

![](https://github.com/Continuers/Java/blob/main/picture/366.png)

```java
package com.itrs1;

import java.util.ArrayList;

/*
    需求:
        按照下面的要求完成集合的创建和遍历
            1.创建一个集合,存储多个字符串元素。
            2.把集合中所有以"张"开头的元素存储到一个新的集合
            3.把张"开头的集合中的长度为 3的元素存储到个新的集合。
            4.遍历上一步得到的集合
 */
public class StreamDemo {
    public static void main(String[] args) {
        //创建一个集合，存储多个字符串元素
        ArrayList<String> list = new ArrayList<String>();

        list.add("易烊千玺");
        list.add("彭于晏");
        list.add("张杰");
        list.add("张继科");

        //2.把集合中所有以"张"开头的元素存储到一个新的集合
        ArrayList<String> zhangList = new ArrayList<String>();

        for (String s : list){
            if (s.startsWith("张")){
                zhangList.add(s);
            }
        }

//        System.out.println(zhangList);

        //3.把张"开头的集合中的长度为 3的元素存储到个新的集合。
        ArrayList<String> threeList = new ArrayList<String>();

        for (String s : zhangList){
            if (s.length() == 3){
                threeList.add(s);
            }
        }

//        System.out.println(threeList);

        //4.遍历上一步得到的集合
        for (String s : threeList){
            System.out.println(s);
        }
        System.out.println("--------------");

        //Stream流来改进
//        list.stream().filter(s -> s.startsWith("张")).filter(s->s.length() == 3).forEach(s-> System.out.println(s));
        list.stream().filter(s -> s.startsWith("张")).filter(s->s.length() == 3).forEach(System.out::println);
    }
}
```



## 2.Stream流的生成方式

![](https://github.com/Continuers/Java/blob/main/picture/367.png)

### 1.Stream流的使用

![](https://github.com/Continuers/Java/blob/main/picture/368.png)

### 2.Stream流的常见生成方式

![](https://github.com/Continuers/Java/blob/main/picture/369.png)

```java
package com.itrs2;

import java.util.*;
import java.util.stream.Stream;

/*
    Stream流的常见生成方式
        1: Collection体系的集合可以使用默认方法 stream()生成流
            default Stream<E> stream()
        2:Map体系的集合间接的生成流
        3:数组可以通过 Stream接口的静态方法of(T.. values)生成流
 */
public class StreamDemo {
    public static void main(String[] args) {
        //1: Collection体系的集合可以使用默认方法 stream()生成流
        List<String> list = new ArrayList<String>();
        Stream<String> listStream = list.stream();

        Set<String> set = new HashSet<String>();
        Stream<String> setStream = set.stream();

        //2:Map体系的集合间接的生成流
        Map<String,Integer> map = new HashMap<String,Integer>();
        Stream<String> keyStream = map.keySet().stream();
        Stream<Integer> valueStream = map.values().stream();
        Stream<Map.Entry<String,Integer>> entryStream = map.entrySet().stream();

        //3:数组可以通过 Stream接口的静态方法of(T.. values)生成流
        String[] strArray = {"hello","world","java"};
        Stream<String> strArrayStream = Stream.of(strArray);
        Stream<String> strArrayStream2 = Stream.of("hello", "world", "java");
        Stream<Integer> intStream = Stream.of(10, 20, 30);
    }
}
```



## 3.Stream流的常见中间操作方法

