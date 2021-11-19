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
无
