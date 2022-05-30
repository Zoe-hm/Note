#### 第一节 变量赋值

Var:可重新赋值      Val：不可重新赋值

Scala可以自动类型推断

插值表达式：定义字符串

```scala
Var/val 变量名 = s“${变量/表达式}字符串”
```

保存大段文本：”””    ”””三引号

惰性赋值：只有使用变量是才会 加载都内存中

```scala
lazy var 变量=表达式
```

小驼峰命名：zhangSanSan         大驼峰命名：Zhangsansan

scala中数据类型开头都是大写

类型转换：

​       自动类型转换：Byte,Short,Char->Int->Long->Float->Double

​       强制类型转换：

```scala
var/val  变量名：数据类型 = 具体的值.toXxx
比如：
        val s1: String = "100"
        val  a: Int       =s1.toInt
```

值类型数据转换String类型：

```scala
1.   var/val  变量名 : String = 值类型数据 + ""
2.   var/val  变量名 : String = 值类型数据 . toString
```

**键盘录入**：

```scala
//键盘录入
import scala.io.StdIn //导包
object Test {
  def main(args: Array[String]): Unit = {
    println("请输入一个字符串：")
    val str = StdIn.readLine()//接受字符串数据
    println("您录入的字符串内容为：" + str)
  }
}
```

```
请输入一个字符串：
love myself
您录入的字符串内容为：love myself

Process finished with exit code 0
```

#### 第二节 运算符

scala中没有++，--运算

**进制** 打开计算器快捷键（Win + R  :  Clac）

逢几进一就是几进制。

二进制中，例如0b`1`0001001的值是一个负数，0b`0`0101010的值就是一个正数

1byte(字节)=8bit(比特)

8421码：

二进制数据:      0    0    0    0    0    0    0    0

十进制数据：128  64   32  16   8   4    2     1

```
0b00001010  ->   8+2=10    //替换
21                 ->    16 + 4 + 1 = 0b0001 0101
```

整数的原码，反码，补码计算规则：

​                  1，正数的原码，反码，补码一样

​                  2，负数的反码：原码符号位不变，数值位按位取反

​                       负数的补码：反码＋1

```scala
import scala.io.StdIn
import scala.util.control.Breaks._
object Test {
  def main(args: Array[String]): Unit = {
    var uname = ""
    var pw = ""
    breakable{
      for(i <- 1 to 3){
        println("请录入您的账号：")
        uname = StdIn.readLine()
        println("请录入您的密码：")
        pw = StdIn.readLine()
        if(uname == "gyx" && pw == "43"){
          println("登陆成功，开始学习Scala！")
          break()
        }
        else{
          if(i == 3)
            println("账号已经被锁定，请与管理员联系！")
          else println("用户名或密码错误，请重新录入，您还有" + (3-i) + "次机会")
        }
      }
    }

  }
}
```

#### 第三节  方法

```scala
def 方法名（参数名：参数类型，参数名：参数类型）:[return type] = {
    //方法体
}
```

scala定义方法可以省略返回值的数据类型，但是定义递归方法如：factorial（阶乘）就不能省略。

惰性方法：(lazy不能修饰var)

```scala
def getSum(a:Int,b:Int) = a + b
lazy val sum = getSum(10,20)
```

方法参数不固定，可定义切变长参数：

```scala
def 方法名(参数名：参数类型*)：返回值类型 = {
    //方法体
}

def getsum(a:Int*) = a.sum
   val sum = getsum(1,2,3,4,5)
```

方法调用方式：

```scala
对象名.方法名（参数）
Math.abs(-1)   //绝对值，结果为1

//中缀调用法：
对象名 方法名 参数
Math abs -1
//1 + 1也是方法，操作即方法

//后缀调用法：
Math.abs{
    //表达式1
    //表达式2
}

//无括号调用法：如果方法没有参数，可以省略方法后面的括号
def sayHello() = println("hello, scala")//方法的返回值是Unit
//调用方法
sayHello

```

在scala中。如果方法的返回值类型是Unit类型，这样的方法称之为**过程**

**过程**的 = 号可以不写

```scala
def sayHello(){
    println("hello, scala")
}
//调用
sayHello
```

#### 第四节 函数

scala中函数是一个对象(变量)，函数不需要def定义，且不需要指定返回类型。

```scala
val 函数变量名 = (参数名: 参数类型, 参数名: 参数类型......) =>函数体
```

```scala
val getsum = (a:Int,b:Int) => a + b
val sum = getsum(11,22)
得到结果可以打印出
println(sum)
```

**方法与函数：**

java中没有区别，scala中有区别：

> 方法运行时，加载到Jvm的方法区中
>
> 函数运行时，加载到Jvm的堆内存中

函数对象有方法。继承自FunctionN

[^在scala中，方法归属于函数]: 函数是对象，方法属于对象

**方法转换为函数**

```scala
val 变量名 = 方法名 _       //格式为：方法名 + 空格 + 下划线
```

```scala
def add(a:Int,b:Int) = a + b
val a = add _
val sum = a(11,22)
```

案例：

```scala
//打印nn乘法表
//用方法定义
import scala.io.StdIn
def printMT(n,Int) = {
    for(i<- 1 to n;j<- 1 to n){
        print(s"${i}*${j} = ${i*j}\t")
        if(i==j)
        println()
    }
}
//或者是
"""def printMT(n,Int) = for(i<- 1 to n;j<- 1 to n) print(s"${i}*${j} = ${i*j}" + (if(i==j "\r\n" else "\t")))"""

println("请输入一个整数：")
val num = StdIn.readInt
printMT(num)
```

```scala
//用函数写
val printMT = (n:Int) => {
    for(i<- 1 to n;j<- 1 to n){
        print(s"${i}*${j} = ${i*j}\t")
        if(i==j)
        println()
    }
}
println(5)
```

#### 第五节 类和对象

##### **面向对象：**

`是一种编程思想，它是基于面向过程的，强调以对象为基础完成各种操作。`

`思想特点：更符合人的思想习惯，把复杂的事情简单化，把程序员从执行者变成指挥者。`

`面向对象三大特征：封装，继承，多态。`

> **类：**（用**class**关键字创建）
>
> 类是属性和行为的集合，是一个抽象概念。属性(成员变量)，行为(成员方法)。
>
> **对象：**（用**new**关键字创建）
>
> 对象是类的具体体现，实现。
>
> 案例：演示类和对象的创建。

```scala
//测试类

//可先创建一个项目project,在src下可创建一个包package,并在包中新建一个object

//package XXXXXX
object XXXXxxxx{
    //main方法，作为程序的主入口，所有代码的执行都是从这里开始。
    def main(args: Array[String]): Unit = {
        //创建Person类型的对象
        val p = new Person()
        //打印对象。
        println(p)
    }
}
```

```scala
//Person实体类

//新建一个class

//package XXXXXX
class Person{
    
}
```

以上这俩个是一体的，也可以写在一起。

```scala
//package XXXXXX
object XXXXxxxx{
    
    //1,创建Person类
    class Person{}
    
    //2,定义main方法
    def main(args: Array[String]): Unit = {
        
        //3,创建Person类型的对象
        val p = new Person()
        //4,打印对象。
        println(p)
    }
}
```

`简写方式：`

`类是空的，没有成员，可以省略{ }      // class Person`

`如果构造器参数为空，可以省略( )     //val p = new Person`

##### **成员变量：属性**

案例：演示在类中如何定义成员变量

```scala
//package XXXXXX
object XXXxxx{
    //1,定义Person类
    class Person{
        //2,定义姓名和年龄字段
        //方式一：
        var name:String = ""
        //方法二： 类型推断
        var name = ""
        var age = 0
       
        //方法三：采用下划线来初始化成员变量值
        var name:String = _
    }
    
    //3,添加main方法
    def main(args:Array[String]):Unit = {
        //4,创建Person类型的对象
        val p = new Person
        //5,给对象成员变量赋值
        p.name = "张三"
        p.age = 23
        //6,打印属性值
        println(p.name,p.age)
    }
}
```

**简化初始化成员变量：使用下划线__**

[仅对var类型的成员变量可以使用下划线]()

1. String => null
2. Int => 0
3. Boolean => false
4. Double => 0.0
5. ......默认值

##### **成员方法：行为**

```scala
//scala中也是用def来定义成员方法的
def 方法名(参数1 : 数据类型 , 参数2 : 数据类型): [return type] = {
    //方法体
}
```

案例：创建一个Customer类，并调用printHello方法

```scala
object XXXxxx{
    class Customer{
        var name:String = _
        var sex = ""
        def printHello(msg:String) = println(msg)
    }
    def main(args:Array[String]):Unit = {
        val c = new Customer
        c.name = "张三"
        c.sex = "男"
        println(c.name,c.sex)
        //调用成员方法
        c.printHello("XXXXXX")
    }
}
```

##### **访问权限修饰符**

`在scala中,没有public关键字,任何没有被标为private或protected的成员都是公共的.`

Scala中的权限修饰符只有:private , private[this] , protected , 默认 ,这四种

```scala
object XXXxxx{
    class Person{
        //定义私有成员变量
        private var name:String = _
        private var age = 0
        
        //定义成员方法
        //获取姓名
        def getName() = name
        //设置姓名
        def setName(name : String) = this.name = name
        //获取年龄
        def getAge() = age
        //设置年龄
        def setAge(age : Int) = this.age = age
       
        //私有的,sayHello方法
        private def sayHello() = println("Hello,Scala")
    }
        
        
    def main(args:Array[String]):Unit = {
        //Person类的对象
        val p = new Person
        
        //成员变量赋值
        //p.name = "张三" 会报错,因为被private修饰的内容只能在本类中被直接访问.
        p.setName("张三")
        p.setAge(23)
        
        println(p.getName,p.Age)
        //调用成员方法
        //p.printHello("XXXXXX"),会报错.原因如上
        
    }
}
```

##### **类的构造器**(之前使用的都是默认构造器)

* [x] 主构造器

    ```scala
    class 类名(var/val 参数名:类型 = 默认值 , var/val 参数名:类型 = 默认值){
        //构造代码块
    }
    ```

    案例: 定义一个Person类,通过主构造器参数列表定义姓名和年龄,并设置默认值.

    ```scala
    object XXXxxx{
        //定义Person类型,在主构造器指定姓名,年龄
        class Person(val name: String = "张三",val age: Int = 23){
            
        }
        def main(args:Array[String]): Unit = {
            //创建空对象,并打印属性值
            val p1 = new Person()
            println(s"${p1.name},${p1.age}")
            //创建全参对象
            val p2 = new Person("李四",24)
            println(s"${p2.name},${p2.age}")
            //仅指定年龄创建对象
            val p3 = new Person(age = 30)
            println(s"${p3.name},${p3.age}")
        }
    }
    ```

    

* [x] 辅助构造器

除了定义主构造器外,还可以根据需要来定义辅助构造器

`1,定义辅助构造器与定义方法的一样,也使用def关键字定义`

`2,辅助构造器的默认名字都是this,且不能修改`

```scala
def this(参数名:类型 , 参数名:类型){
    //第一行必须要调用主构造器或者其他构造器
    //构造器代码
}
```

案例 : 

```scala
object XXXxxx{
    class Customer(val name: String, val address: String){
        
        //定义辅助构造器,接收一个数组类型的参数
        def this(arr:Array[String]){
            //访问主构造器
            this(arr(0),arr(1))   //调用本类的主构造器
            
        }
    }
    def main(args:Array[String]):Unit = {
        
        //val c = new Customer("李四","北京")   //通过主构造器创建对象
        //通过辅助构造器,创建Customer类的对象
        val c = new Customer(Array("张三","上海"))
        
        println(c.name,c.address)
    }
}
```

##### **单例变量**

* [x] 定义单例对象

Scala中没有java中static关键字, 定义类似的,要用到Scala中的单例对象(object)

单例对象表示全局仅有一个对象,也叫做孤立对象, 定义单例对象和定义类类似, 把class换成object

```scala
object 单例对象{ }
```

> 1,在object中定义的成员变量类似于java中的静态变量,在内存中都是由一个对象
>
> 2,在单例对象中,可以直接使用`单例对象名.`的形式调用成员.

案例 : 定义一个Dog单例对象,保存狗有几条腿

```scala
object XXXxxx{
    
    //定义一个单例对象Dog
    object Dog{
        //定义变量
        val leg_num = 4
    }
    
    def main(args:Array[String]):Unit = {
        //直接打印数量
        println(Dog.leg_num)   //直接访问
    }
}
```

* [x] 在单例对象中 定义方法

案例 : 设计一个单例对象,定义一个能够打印分割线(十五个减号)的方法

```scala
object XXXxxx{
    
    //定义单例对象PrintUtil
    object PrintUtil{
        //定义一个方法
        def printSpliter() = println("-" * 15)
    }
    
    def main(args:Array[String]) : Unit = {
        //调用单例对象的成员方法
        PrintUtil.printSpliter()
    }
}
```

**进入主入口的两种方法:**

> 1 , 定义main方法
>
> 
>
> 2 , 继承App特质
>
> ​     创建一个object,继承来自App特质(Trait) , 然后将需要编写在main方法中的代码,写在object的构造方法体内.

```scala
object 单例对象名 extends App{
    //方法体
}
```

案例 : 通过继承App特质的方式,定义程序的主入口.

```scala
object XXXxxx extends App{
    println("Hello,Scala!")
}
```

##### **伴生对象**

`一个class和object具有同样的名字.这个calss称为伴生类,object称为伴生对象`

> 伴生对象必须要和伴生类一样的名字
>
> 伴生对象和伴生类在同一个scala源文件中
>
> 伴生对象和伴生类可以互相范围private属性

案例 : 编写Generals类 , toWar方法

​          打印: 武将拿着 ** 武器,上阵杀敌!

​          编写一个Generals伴生对象,定义私有变量,保存武器名称

​          调用Generals对象,调用toWar方法

```scala
object XXXxxx{
    
    //定义伴生类
    class Generals{   //里面都是非静态内容
        //定义toWar方法,表示打仗
        def toWar() : =println("武将拿着${Generals.armsName}武器,上阵杀敌!")
    }
    
    
    //定义伴生对象
    object Generals{   //里面都是静态内容  且 是单例对象
        //定义私有成员:武器
        private val armsName = "青龙偃月刀"
    }
    
    
    def main(args:Array[String]) : Unit = {
        //创建伴生类的对象
        val g = new Generals()
        //调用toWar方法
        g.toWar()
    }
}
```

##### **pirnvate[this]访问权限**

如果某个成员的权限设置为private[this]，表示只能在当前类中访问。伴生对象也不可以访问。

案例：定义一个Person类包含一个name字段，并用private[this]修饰

​           测试伴生对象是否能访问private[this]权限的成员

```scala
object XXXxxx{
    
    //定义Person伴生类，并定义一个name字段
    class Person(private[this] var name : String){
        
    }
    
    //定义Person伴生对象
    object Person{
        //定义一个printPerson方法，并打印Person对象属性值
        def printPerson(p : Person) = println(p.name)  //会报错
    }
    
    
    def main(args:Array[String]) : Unit = {
        
        //调用伴生对象的printPerson方法访问private[this]修饰的内容
        val p = new Person("张三")
        Person.printPerson(p)
    }
}
```

##### **apply方法**

在Scala中支持创建对象的时候，免new的写法，要通过伴生对象的apply来实现。

```scala
//定义apply方法
object 伴生对象名{
    def apply(参数名: 参数类型, 参数名: 参数类型...) = new 类(...)
}

//创建对象
val 对象名 = 伴生对象名(参数1, 参数2, ...)
```

案例：在伴生对象中定义apply方法，实现创建Person对象的免new操作。

```scala
object XXXxxx{
    
    class Person(var name: String = "", var age: Int = 0){}
    object Person{
        
        //定义apply方法
        def apply(name: String,age: Int) = new Person(name,age)
    }                                //apply()方法，Scala SDK会自动调用
    
    def main(args:Array[String]) : Unit = {
        val p = Person("张三"，23)   //并没有调用apply方法，因为如上
        println(p.name,p.age)
    }
}
```

**综合案例：**

```scala
import java.text.SimpleDateFormat
import java.utils.Date

object XXXxxx{
    
    
    
    //定义工具类DateUtils
    object DateUtils{
        //下面要用到一个SimpleDateFormat类型的对象，所以定义
        var sdf:SimpleFormat = null
        
        //定义data2String方法，用来将日期对象转换成其对应的字符串
        def data2String(data: Date, template: String) = {    //导入Date包
            sdf = new SimpleDateFormat(template)
            sdf.format(data)  //格式化方法format()
        }
        
        //定义string2Date方法，用来将字符串行式的日期转换成其对应的日期对象
        def string2Date(dataString: String, template: String) = {
            sdf = new SimpleDateFormat(template)
            sdf.parse(dataString)
        }
    }
    
    
    
    
    def main(args:Array[String]) : Unit = {
        //测试data2String方法
        println(DateUtils.data2String(new Date(),"HH:mm:ss"))
        //测试string2Date方法
        println(DateUtils.string2Date("1314年5月21日","yyyy年MM月dd日"))
    }
    
    
}
```





























