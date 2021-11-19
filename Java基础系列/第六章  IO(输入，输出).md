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
