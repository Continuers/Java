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

