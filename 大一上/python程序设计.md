



# 随记


























































目标：

# test















































# reason

































































# 拟合数据























# 材料

> python语言程序设计
>
> 孙海洋



## 熵

1.能一行代码搞定的，绝不写两行

2.思维定势一定会阻挡你的进步，阻止你成为真·大佬

### 0.1熵

1.如何用正则的模式来匹配字符串中所有的数字子串

2.如何抛出类型错误


    b=type(x)
    if b!=int:
        raise Exception('请输入整数')



### 0.2负熵

1.标识符不能以数字开头 eg：3a=

2.input默认输入的是字符串

3.库分为标准库和拓展库

4.用from____ import____后指定模块，再在调用其模块时，不需要再写库名.

5.6种类型：字符串、整型、浮点型、列表、元组、集合

6.8/3会保留小数

7.元组和列表的区别：元组不可增删改。

7.1：元组是常量，其元素不能增、删、改，只能查询

8.tup1=5，6，7，8 元组可以这样写，不推荐写法

9.元组和列表切片访问和运算

10.for in后面可以是集合、元组

11.range是一个对象，生成类型是元组

12.print默认值与值的间隔(sep=' ')为空格和第二次执行(end='\n')时换行

13.print('\n')的换行比print()的默认换行，行与行之间多了空格

14.函数定义时必须先非默认值参数，最后默认值参数

15.reduce函数默认加法起点为0，乘法起点为1

16.面向对象的三大特性：封装、继承、多态。封装：把数据和对数据的操作封装成类。继承：提升代码的复用率。可以是单继承，多继承(有两个父类)

17.java是单继承，但可以通过指针实现多继承。c++是但继承

18.类的变量：除self以外的。实例变量：有self的

19.一个类里面不一定用构造方法,系统会默认构造方法

20.'str' object is not callable
	说明有之前缓存的定义，需要重启编辑器

21.字符串起始边界“”

22.#转义字符 \n 换行  \t 水平制表符 end = '\t'（空8格）63

23.list()仅传入一个整体参数

24.ls可以混合输出

```python
ls = ['Hello',2021]
print(ls)
```

25.from 模块名 import 函数名

26.中文符号属于强类型错误，无法捕获

27.完全理解浮点运算目前只是有可能



### 0.3拟合数据

#### 一、终章

##### 第一次拟合

1. 步长为负值时，首项默认为最后一位的下标
2. 对列表排序的sort是函数，要加（）
3. 对列表排序之后不会显示，但对应下标的值已经改变
4. 倒序是reverse
5. 打印真正匹配的值用print变量名.group()
6. 跨度是span
7. 继承在初始化的首句是不变的
8. 继承核心语句是 父类名.方法（相同的参数）
9. 为什么单个元素的元组要加上逗号？
   因为tup1=（）的括号会被识别成（1+1）的括号
10. 分割时split
11. join后面要加()
12. 直接用模块.会显示模块名()
13. \d和[]最后匹配出的都是数值
14. findall寻找出的是列表
15. countine要实现在星阵图中抠出一个星，就要只能在countinue之前填充空格
16. 5个换行还需要考虑左对齐
17. 素数的标记符是在第一个for循环下定义的
18. 素数要先将flag置为零，再跳出for循环
19. 换行语句要放在flag判别语句中，防止多次换行
20. 求圆面积的时候要保留小数



##### 第二次拟合

1.取个位是 g%10 s位是先//

2.求素数时是从2开始取的

3.素数的循环时标识符语句是在第一个循环里判断

4.只有%d才能左对齐 所有格式是写在%里面的

5.格式控制打印两个值%（a,b）要用（)

6.from math import* 先写库名再import所有

7.是否在是in不是 is in

8.返回列表索引是.index

9.添加方法除了append还有extend

10.pop是删除索引，remove是删除值

11.三位取百位是先//再%

12.reduce不用再变成列表

13.私有变量self,__x

14.re.split分割出来的也是列表字符形式

















## 一、语法基础

> 字符串、序列、流程控制

### 1.字符串

```python
#输出5个相同的字符 ww
print(5*'ww')
#值之间默认空格和换行，设置间隔sep=''


#输入提示ww，并将其提取成任意数字串，查看其类型
a=eval(input("ww"))
type(a)


#用两种方法打印 it's book，再用原生串格式打印
print("it's book")
print('it\'s book')
print(r'it\'s book')

#用格式控制打印 对123456.123456保留三位小数并占19位
a=123456.123456
print('%19.3f'%a)#保留小数点后3位，%m.n3f 自动四舍五入 .0f整数


#用格式控制打印 使字符str前补充长度使总长度为7
a='str'
print('%7s'%a)


#用两种方式调用math库
from math import*
import math 


#调用datetime模块，查看当天日期
import datetime
print(datetime.date.today())


#打印 1%2
print('%d %% %d'%(1,2))


#计算字符串s中’o'出现了几次,用两种在下标3到9(有假尾巴)中寻找'or‘的下标
#不同：index未找到会报错而find会返回-1 同：都是返回第一个遇到的数的下标
s = 'hello,world.'  

s.count('o')
s.find('lo',3,9)
s.index('lo',3,9)
```



### 2.序列

```python
#输出列表[1,2,3,4,5]倒数第二个
ls=[1,2,3,4,5]

ls[-2]


#同上ls，以步长为2切片出2和4
#假尾巴 step=1
ls[1:5:2]


#对列表ls中的每一个数求和，和个数
sum(ls)
len(ls)

#同上ls，判断1、6是否在ls
if 1 in ls:
    print('在')
if 6 not in ls:
    print('不在')
    

#返回列表 'a','b','c','d'中a的索引
ls=['a','b','c','d']
ls.index('a')


#返回字符 abcdef 中f的索引
s='abcdef'
s.find('f')


#ls1=[2,3]  ls2=[1,2,3]  将ls2的值一个个添加到ls1的末尾
#>再用另一种方法在末尾添加一个数2
ls1=[2,3]
ls2=[1,2,3]
ls1.extend(ls2) #一个个添加到列表末尾，而append会直接把列表添加到末尾
ls1.append(2)
ls1


#将元组 (1，2，3) 转换成列表
a=list((1,2,3))#list只能接受一个参数
a


#删除列表ls1中的值4
ls1 = [7,4,6,8,6]

ls1.remove(4)
ls1

#用del删除从下标为4的的值
ls1 = [7,4,6,8,6]

del ls1[4]
ls1

#用索引的方法删除ls1下标0的3
ls1 = [7,4,6,8,6]

#弹出8这个值
ls1.pop(3)




```

#### 2.5元组

```python
##2.5.1元组创建
#创建元组tup=5,6,7,8,空元组tup1,只有一个元素5的元组tup2
tup=(5,6,7,8)
tup=()
tup=(5,)#因为创建元组可以不加(),加,以表示是元组 
tup


#将列表 1,2,3转换成元组
tup=tuple([1,2,3])
tup

##2.5.2元组的访问
##2.5.3元组运算符
#连接两个元组tup1=（1,2,3） tup2=（2,3,4）为新的元组tup
tup1=(1,2,3)
tup2=(2,3,4)
tup=tup1+tup2
tup


#将元组内的4变成3个，列表内的‘hello’变成3个
tup=(4,)*3
tup
ls=['hello']*3
ls


#将元组和数组4,'a'分别打印3次
a=(4,'a')*3
a
a=[4,'a']*3
a


#调用0到4的序列列表对象
a=range(5)
list(a)


#用元组生成器生成元组6，8，11，14
a=tuple(x*3+2 for x in range(1,5))
print(tuple(a))#把对象a以元组形式呈现
#或
a = tuple(i for i in range(5,15,3))
print(a)
```

### 3.流程控制

#### 3.1分支

```python
##3.1.1if分支
##3.1.2if-else分支

#判断水仙花数

def fun():
    for x in range(100,1000):
        x1=x%10
        x2=x//100
        x3=x//10%10
        if pow(x1,3)+pow(x2,3)+pow(x3,3)==x:
            print('{}是水仙花数'.format(x))
fun()

# 3.1.3if-elif-else多分支
```

#### 3.2循环

```python
##3.2.1while循环
#用while循环实现1+到100，同时赋值给s和i，循环执行完，打印 i的值
s,i=0,1
while i<=100:
    s+=i
    i+=1
else:
    print(i)
```

#### 3.3循环嵌套

```python
# 3.3.1星型阵
# 3.3.2数字阵
#打印4*5的矩阵，使用两种方法使其左对齐
for i in range(1,5):
    for j in range(1,6):
#         print('%d'%(i*j),end='\t')
        print('%-3d'%(i*j),end='')
    print()
#=>%就不是一个变量都要加（）

# 3.3.3九九乘法表
# 3.3.4format格式化
#用两种格式打印9*9口诀表
for i in range(1,10):
    for j in range(1,i+1):
#         print('%d*%d=%d'%(i,j,i*j),end='\t')
        print('{}*{}={}'.format(i,j,i*j),end='\t')
    print()
#print('%-3d') #%nd 默认右对齐（给3位，放最右边） -nd
```

#### 3.4流程控制

```python
# 3.4.1break
#打印5*5的星星，第二行最后两个空出来
for i in range(5):
    for j in range(5):
        if i==1 and j==3:
            break
        print('*',end=' ')
    print()
    
# 3.4.3continue
#打印5*5的星星，第4行第三个空出来
for i in range(5):
    for j in range(5):
        if i==3 and j==2:
            print(end='  ')
            continue
        print('*',end=' ')
    print()
    
```











## 四、函数

4.1函数的定义与调用

```python
# 4.1.1无参函数的定义和调用
# 4.1.2带参函数的定义和调用
#编写程序，输出斐波那契数列的前20项，1，1，2，3，5，8，13，……
def fun(ls,x):
    for i in range(2,x+1):
        ls.append(ls[i-1]+ls[i-2])
    print(ls)
    
ls=[1,1]
fun(ls,20)

# 4.1.3带返回值的函数定义和调用
#计算并返回矩形的面积,宽高小于0时返回-1
def area(w,h):
    if w<0 or h<0:
        print('参数错误')
        return -1
    return w*h
a=area(3,-4)
print(a)

# 4.1.4带默认参数的函数
#下列调用方式是否正确
def fun(name,age=17):
    print(name)
    print(age)
fun('张三')
fun('张三',19)
fun(age=19,name='李四')
#=>正确

# 4.1.5参数值可变的函数
#参数ls在函数内被修改，函数外ls的值是否变化

def fun(ls,x):
    for i in range(2,x+1):
        ls.append(ls[i-1]+ls[i-2])
    print('函数里面{}'.format(ls))
    
ls=[1,1]
fun(ls,20)
print('函数外面{}'.format(ls))

#=>变化


```

### 4.2函数的作用域

```python
#写出全局变量a的值，和局部变量a的值
a=2
def fun(a):
    a=3
    print('局部变量{}'.format(a))

fun(a)
print('全局变量{}'.format(a))
#全局2，局部3


#写出全局变量a的值，和局部变量a的值
a=2
def fun():
    global a
    a=10
    print('局部变量{}'.format(a))

fun()
print('全局变量{}'.format(a))
#全局10，局部10
```

4.3lambda函数

```python
#将下列函数转换成lanmbda函数
def add(a,b):
    return a+b
add(2,3)

#写出lanmbda函数
f=lambda a,b:a+b
f(2,3)
```

4.4python常见内置函数

```python
# 4.4.1map函数
#用map将列表 [1,2,3,4,5] 的每一个元素乘以2，并以列表输出

lab=lambda x:x**2
rst=map(lab,[1,2,3,4,5])
print(list(rst)) #包裹只能用数组或列表来呈现

# 4.4.2filter函数
#用filter筛选上述列表中的奇数和大于2的数

rst=filter(lambda x:x%2==1 and x>2,[1,2,3,4,5])
print(list(rst))

# 4.4.3 reduce函数 非内置函数
#对上述列表实现前一个数加后一个数的累加，并设置初始值(initial)为100

from functools import reduce
rst=reduce(lambda x,y:x + y,[1,2,3,4,5],100) #默认起点100开始加，再加后面的
print(rst)


#同上实现累乘，不设置c初始值

rst=reduce(lambda x,y:x * y,[1,2,3,4,5]) #默认起点1开始乘
print(rst)
```













## 五、面向对象

> 面向对象的三大特性：封装、继承、多态

### 5.1类和对象

```python
class Class:
    i=10
    def fun(self):
        print('hello')
#>
obj=Class()
obj.i
obj.fun()
```



### 5.2构造方法

```python
#>用构造方法计算圆的周长和面积,赋值20，保留3位
import math
class Cricle:
    def __init__(self,r):
        self.r=r
    def area(self):
        return self.r**2*math.pi
    def sepermetre(self):
        return self.r*2*math.pi
p=Cricle(20)
print('面积{:0.3f}'.format(p.area()))
print('周长{:0.3f}'.format(p.sepermetre()))

```



### 5.3类的变量和实例变量

```python
#>同上,类中定义一个类的变量i，将其变成实例变量用来计算上述area方法被调用的次数，再用两种方法快速调用2次area方法,第一次输出次，第二次输出3次
import math
class Cricle:
    i=0
    def __init__(self,r):
        self.r=r
        Cricle.i+=1
    def area(self):
        return self.r**2*math.pi
    def sepermetre(self):
        return self.r*2*math.pi
p=Cricle(20)
print('\n调用了{}次'.format(p.i))
print('面积{:0.3f}'.format(p.area()))
print('周长{:0.3f}'.format(p.sepermetre()))
Cricle(10)
p2=Cricle(12)
print('调用了{}次'.format(p.i))
       
       
#>类名Family，实例变量存款total=1000，自定义spend,earn,show三个方法分别输出张三花了100,张三余额900

class Family:
    total=1000
    def __init__(self,x):
        self.x=x
    def spend(self,a):
        print('{}花了{}'.format(self.x,a))
        Family.total-=a
    def earn(self,b):
        print('{}赚了{}'.format(self.x,b))
        Family.total+=b
    def show(self):
        print('{}余额{}'.format(self.x,Family.total))
p=Family('张三')
p.spend(100)
p.show()

```



### 5.4私有变量及其访问方式

```python
#>同上，在类Family中的x和total设为一个私有变量，用gerSc方法间接调用私有变量total，调用setsc间接修改新名字李四，再用show输出：李四余额900. 
#尝试一下直接调用__total属性（肯定报错）

class Family:
    __total=1000
    def __init__(self,x):
        self.__x=x
    def spend(self,a):
        print('{}花了{}'.format(self.__x,a))
        Family.__total-=a
    def earn(self,b):
        print('{}赚了{}'.format(self.__x,b))
        Family.__total+=b
    def show(self):
        print('{}余额{}'.format(self.__x,Family.__total))
    def getSc(self):
        return self.__total
    def setsc(self,newx):
        self.__x=newx
p=Family('张三')
# p.__total
p.spend(100)
p.show()
print('余额{}'.format(p.getSc()))
p.setsc('李四')
p.show()



```



### 5.5类的继承

```python

#>建一个和类Person相似的类Stu，继承父类Person中类的变量name和age，并在子类Stu中构造方法grade，最后给子类传参，用父对象的speak方法打印 姓名张三，年龄18，班级2
class Person:
    def __init__(self,name,age):
        self.name=name
        self.age=age
    def speak(self):
        print('姓名{}，年龄{},班级{}'.format(self.name,self.age,self.grade))
#>

class Stu(Person):
    def __init__(self,name,age,grade):
        Person.__init__(self,name,age) #也可以直接用super()函数调用
        self.grade=grade
p=Stu('张三',18,2)
p.speak()

#wrong:传承也加self
#=>1.继承父类的子类和父类共享所有实例变量和方法


#>在上述子类重写父类方法speak并调用,输出hi,I am 张三,my age is 18,my grade is 2
class Person:
    def __init__(self,name,age):
        self.name=name
        self.age=age
    def speak(self):
        print('姓名{},年龄{},班级{}'.format(self.name,self.age,self.grade))
class Stu(Person):
    def __init__(self,name,age,grade):
        Person.__init__(self,name,age)
        self.grade=grade
    def speak(self):
        super().speak()#覆盖speak，super.依旧可以调用父类的speak。也可以隐藏属性
        print('hi,I am {},my age is {},my grade is {}'.format(self.name,self.age,self.grade))
p=Stu('张三',18,2)
p.speak()

```



5.6运算符重载

```python
#>重载+，-，实现vect（1，2）+vect（2，4）=vect（3，6）的效果
class Verb:
    def __init__(self,x,y):
        self.x=x
        self.y=y
    def __str__(self): #对象的呈现形式
        return 'vect({},{})'.format(self.x,self.y)
    def __add__(self,other):
        return Verb(self.x+other.x,self.y+other.y)
    def __sub__(self,other):
        return Verb(self.x-other.x,self,y-other.y)
p1=Verb(1,2)
p2=Verb(2,4)
print('{}+{}={}'.format(p1,p2,p1+p2))
#=>1.重载+运算符时要先声明类名。other要声明变量，加法的输出形式依然会遵守str的定义 2.print最后少一个）会报错到最后一行

```





## 六、异常

### 9.1常见异常

```python

""" 
类型异常 
TypeError
值异常 
valueError
名字异常 s = c + 3
NameError
零异常 
ZeroDivisionError

文件打开异常  
FilenotfoundError

索引异常 
IndexError
属性错误
AttributeError

语法异常 a = 'hello’* 2 （中文的‘）
SyntaxError
缩进异常 
IndentationError
强类型错误是
IndentationError and SyntaxError

 """
```



### 9.2异常处理

```python
# 9.2.1try-except
# 9.2.2try-except-except
#>监视输入两个整数a.b相除以,当b为0或输入小数时捕获并打印错误，并一直执行下去，当条件满足一次时终止
while True:
    try:
        a=int(input('输入一个整数1：'))
        b=int(input('输入一个整数2：'))
        s=a/b
        print('值是:{}'.format(s))
        break
    except ZeroDivisionError as e:
        print(e)
    except ValueError as e:
        print(e)
        
#=>valueerror的V要大写

# 9.2.3try-except-else
# 9.2.4try-except-else-finally
#> 同上，实现第一次无报错时打印：'无任何异常，完美!'，无论是否报错都打印'继续加油'
while True:
    try:
        a=int(input('输入一个整数1：'))
        b=int(input('输入一个整数2：'))
        s=a/b
        print('值是:{}'.format(s))
        
    except ZeroDivisionError as e:
        print(e)
    except ValueError as e:
        print(e)
    else:
        print('无任何异常，完美！')
        break
    finally:
        print('继续加油！')

        
# 9.2.5raise主动抛出异常
#=>当sc<60,用raise自动抛出是错误并捕获输出'我不及格'

try:
    sc=50
    if sc<60:
        raise Exception('我不及格') 
except Exception as e:
    print(e)
    
    
```



### 9.3自定义异常

```python
#=>圆的半径为负值和0时报错:异常：半径{}为负值,并值输出面积

import math
class CricleException(Exception):
    def __init__(self,r):
        self.r=r
    def __str__(self):
        return '异常：半径{}为负值'.format(self.r)
class Cricle:
    def __init__(self,r):
        if r<0:
            raise CricleException(r)
        self.r=r
    def getArea(self):
        return math.pi*self.r**2
try:
    r=eval(input('输入半径:'))
    obj=Cricle(r)
    print('圆的面积：{:0.3f}'.format(obj.getArea()))
except CricleException as e:
    print(e)
    
#=>1.忘了print里的{}


#=>求三角形面积，当两边之和不大于第三边时报错{},{},{}不能构成三角形
#海伦公式求三角形面积；(t=a+b+c)/2 s=sqrt(t*(t-a)*(t-b)*(t-c))
import math
class TriangleException(Exception):
    def __init__(self,a,b,c):
        self.a=a
        self.b=b
        self.c=c
    def __str__(self):
        return '{},{},{}不能构成三角形'.format(self.a,self.b,self.c)
class Triangle:
    def __init__(self,a,b,c):
        if a+b<=c or a+c<=b or b+c<=a:
            raise TriangleException(a,b,c)
        self.a=a
        self.b=b
        self.c=c
    def getArea(self):
        t=(self.a+self.b+self.c)/2
        return math.sqrt(t*(t-self.a)*(t-self.b)*(t-self.c))
try:
    a=eval(input('输入边长1:'))
    b=eval(input('输入边长2:'))
    c=eval(input('输入边长3:'))
    obj=Triangle(a,b,c)
    print('三角形的面积：{:0.3f}'.format(obj.getArea()))
except TriangleException as e:
    print(e)



```



### 9.4断言

```python
#用断言判断函数参数sc是否为整型和浮点型，name是否为字符型，是则打印继续

def fun(sc,name):
    assert type(sc) is int or float
    assert type(name) is str
    print('继续')

fun(sc=10.1,name='张三')

```







## 七、数组

10.1 numpuy数组

```python
#生成一维数组[1.2.3.4.5]

import numpy as np
a=np.array([1,2,3,4,5]) #array可以生成一维数组
print(a) #呈现出来是list 类型是数组了 numpy.ndarray(n维数组)
print(type(a)) 


#从5开始，步长3，生成共5个数

a=np.arange(5,20,3) #numpy公司仿制的range 
print(a) #生成[ 5  8 11 14 17]
print(type(a))  #arange也可以生成一维数组


#生成一个2行5列的矩阵，保存一个数组里
#>数组1 [1,2,3,4,5]，数组2 [6,7,8,9,10]

a=np.array([[1,2,3,4,5],[6,7,8,9,10]]) 
print(a) 
print(type(a)) 


# 10.1.2 特殊数组
#生成1行6列的0的基本矩阵

np.zeros(6,)


#生成2个3行4列的0的基本矩阵

np.zeros((2,3,4))


#生成一个4行5列的1的剧本矩阵
np.ones((4,5))


#生成5*5的对角矩阵，对角为1,并将值设为整型，并打印
a=np.eye(5,dtype=int)
print(a)


# 10.1.3 数组的基本运算

#求数组a1,a2的内积和相乘
#>a1=np.array([[1,2],[3,4]])
#>a2=np.array([[5,6],[7,8]])
# print(np.dot(a1,a2))
np.matmul(a1,a2) 
```

### 10.2 切片与索引

```python
#写出下列值
ls=[1,2,3,4,5,6,7,8,9,10]
print(ls[1:8:2])

#=>2,4,6,8


#生成1到10的一维矩阵，切片输出倒数第一个

a6=np.arange(1,11) #呈现出来是list 类型是数组了 numpy.ndarray
# print(a6)

print(a6[-1])


#对上述a6，从值4开始倒序

print(a6[3::-1])


#用silce对象表示切片的值，切片从索引1到10的步长3的a6的值

s=slice(1,10,3) #下标耙子 是一个对象
print(a6[s])
```



### 10.3数组的常用方法

```python
# 10.3.1排序
#对一维数组 b=[5,3,9,4,1]按升序排序

#升序sort
b = np.array([5,3,9,4,1])
b.sort()
print(b)


#对上述按降序排序
b.sort()
b=b[::-1]
print(b)


#对字符串 “1123456” 按步长为2进行倒叙、

s='0123456789'
print(s[::-2])


# 10.3.2 常用统计方法
#对上述一维数组求中位数、算术平均值、最大、最小值、加权平均值、标准差、方差。

print(np.median(b)) 

print(np.max(b))

print(np.min(b))

print(np.min(b))

print(np.average(b))

print(np.std(b))

print(np.var(a))
```











## 八、数据可视化



### 简述

标记类型有哪些



<img src="https://typora-cos-1308485298.cos.ap-nanjing.myqcloud.com/40703f2cb18b3f51679b34e2499f8608.png" alt="1" style="zoom: 150%;" />、



2.颜色字符(color)有哪些

![2](https://typora-cos-1308485298.cos.ap-nanjing.myqcloud.com/8819825f7b44888ef659d94f38f2d7fd.png)



3.风格字符(linestyle)有哪些

![3](https://typora-cos-1308485298.cos.ap-nanjing.myqcloud.com/ef42598540d66d500afb6266f0beac4a.png)



### 11.1绘制简单折线图

```python
#绘制3条曲线y=x,y2=x**2,y3=x**3 颜色分别是红，绿，蓝 分别设置图例linear，sqaudratic，cubic x密度为：到2有500个点
import matplotlib.pyplot as plt
import numpy as np
x=np.linspace(0,2,500)
y=x
y2=x**2
y3=x**3
plt.plot(x,y,color='r',label='linear')
plt.plot(x,y2,color='b',label='sqaudratic')
plt.plot(x,y3,color='g',label='cubic')
plt.legend()
plt.show()


#绘制简单折线图(linspace) 用两种方式调用pyplot模块  y轴数据：money=[7,10,13,15,18]  标记类型星星
import matplotlib.pyplot as plt
#from matplotlib.pyplot as plt
money=[7,10,13,15,18]
plt.plot(money,marker='*')
plt.show()


#同上 试用两种中文字体
#添加x轴数据：fruit=['apple','orange','banana','pear','peach']  标记类型：矩阵  风格字符 点划线
#x轴标题 fruit(水果)  y轴标题 money(单价)  表标题 图1：fruit-money

plt.rcParams['font.family']='SimHei'
# plt.rcParams['font.sans-serif']='SimHei'
money=[7,10,13,15,18]
fruit=['apple','orange','banana','pear','peach']
plt.plot(fruit,money,marker='s',linestyle='-.')
plt.xlabel('fruit(水果) ')
plt.ylabel('money(单价)')
plt.title('fruit-money')
plt.show()

```



### 11.2 条形图

```python
#1.绘制条形图：根据折线图数据和标题。宽度0.3 红色

money=[7,10,13,15,18]
fruit=['apple','orange','banana','pear','peach']
plt.bar(fruit,money,width=0.3,color='r')
plt.xlabel('fruit(水果) ')
plt.ylabel('money(单价)')
plt.title('fruit-money')
plt.show()


#将上表改为直方图（使条形图转过来）

money=[7,10,13,15,18]
fruit=['apple','orange','banana','pear','peach']
plt.barh(fruit,money,height=0.3,color='r')
plt.xlabel('money(单价) ')
plt.ylabel('fruit(水果)')
plt.title('fruit-money')
plt.show()


#在1.的基础上添加水果单价的2021年对比数据 money_2021=[8,8,19,17,31]  对比数据添加在原数据右侧设为蓝色，添加图例2021和2020

money=[7,10,13,15,18]
money_2021=[8,8,19,17,31]  
fruit=['apple','orange','banana','pear','peach']
bar_width=0.3
index_2020=range(len(fruit))
index_2021=[x+bar_width for x in index_2020]
plt.bar(index_2020,money,width=bar_width,color='r',label='2020')
plt.bar(index_2021,money_2021,width=bar_width,color='b',label='2021')

#plt会让数据按宽度/2处开始出建模
plt.xticks([x+bar_width/2 for x in index_2020],fruit)
plt.xlabel('fruit(水果) ')
plt.ylabel('money(单价)')
plt.title('fruit-money')
plt.legend()
plt.show()

```



### 11.3一图绘制多条曲线

### 11.4 散点图

```python
#绘制散点图（scatter） 用np模块随机生成0-1内的10个数 分别赋值给x1,x2,x3,y1,y2,y3 x1-y1为红色，圆圈。x2-y2为绿，三角 x3-y3为蓝。星星

N=10
x1=np.random.rand(N)
y1=np.random.rand(N)
x2=np.random.rand(N) #生成10个数
y2=np.random.rand(N) 
x3=np.random.rand(N) 
y3=np.random.rand(N) 
plt.scatter(x1,y1,color='r',marker='o')
plt.scatter(x2,y2,color='g',marker='^')
plt.scatter(x3,y3,color='b',marker='*')
plt.show

```



### 11.5饼图

```python
#饼图
#>显示一个饼图，sleep占7/24，'eating'=2/24,'working'=2,'playing'=13，颜色:青、品红、红、蓝 ，小数：两位 ，阴影：有 ，使eating凸出3

slices=[7,2,2,13]
labels=['sleeping','eating','working','playing']
cols =['c','m','r','b']
plt.pie(slices,
        colors=cols,
        explode=[0,0.3,0,0],
        autopct='%.2f%%',
        labels=labels,
        shadow=True)
plt.show()
```

















## 九、数据处理

### 12.1 pandas数据处理

```python
## 12.1.1 Series系列
#用series来显示一维数组 'a','b','c','d' ，自定义序列 101,102,103,104 
#data不能为集合、二维元组、index可以是元组、列表、集合、数组

import pandas as pd
import numpy as np
d = np.array(['a','b','c','d'])
index=[101,102,103,104]
rst = pd.Series(data=d,index=index)
rst
#=>第一句是调用pandas模块


# 12.2.1 DataFrame
#1.用DataFrame在一行内一部创建字典 'Name':['Tom','Jack','Steve','Ricky'],'Age':[28,34,29,42] 和序列'rank1','rank2','rank3','rank4'，
#显示数据类型为浮点型
rst = pd.DataFrame(data={'Name':['Tom','Jack','Steve','Ricky'],'Age':[28,34,29,42] },index=['rank1','rank2','rank3','rank4'],dtype=float)
rst
#=>显示类型是dtype=


#同上，显示索引1到2行的数据，显示前两行，显示后两行
print(rst[1:3])
print(rst.head(2))
rst.tail(2)


#二维列表[95,92],[88,94]创建数据,序列'张三','李四'，字段名'语文','数学'，并显示
d=[[95,92],[88,94]]
index=['张三','李四']
columns=['语文','数学']
rst=pd.DataFrame(data=d,index=index,columns=columns)
rst
#=>是Frame 2.是colu


#2.同上，用字典和series公司一步创建上述矩阵(序列默认)，并赋值给d，并显示
#该创建方式不能添加序列,否则数据会显示乱码

d={'语文':pd.Series([95,88]),'数学':pd.Series([92,94])}
rst=pd.DataFrame(d)
rst
#=>是ies 2.Series要接()


#处理各字段名的最大值，处理语文的最大值
print(rst.max())
rst['语文'].max()


#同上，处理语文字段之和，处理所有字段的平均值，处理所有字段的标准差
print(rst['语文'].sum())
print(rst.mean())
rst.std()
#=>标准差是std


# 12.3.1 读取 excel
# 12.3.1 读取 csv
#创建一个同上2.的csv表格，取名 grade，并读取
#路径保存不能有中文,csv可以显示是乱码，不影响输出
rst=pd.read_csv(r'E:\static\grade.csv')
rst
#=>读取时read


#用条形图统计csv表中 语文 字段中的相同的数据分别出现了几次，宽度0.2
from matplotlib import pyplot as plt
rst['语文'].value_counts().plot(kind='bar',width=0.2)
#=>子公司叫matplotlib 2.公司叫pyplot 3.公司简写是plt 4.统计只要在处理后面加制表语句plot()就行 5.对csv表的处理用的是值_counts 6.值没有s


#读取E:\static目录下的test和train的csv文件，读取train文件的后5行
rst_train=pd.read_csv(r'E:\static\train.csv')
rst_test=pd.read_csv(r'E:\static\test.csv')
rst_train.tail(5)

#=>read_后面要跟文件类型 2.pd后面永远是.



#同上，分类统计两张表 Survived 字段 0出现的次数和 1出现的次数
print(rst_train['Survived'].value_counts())
rst_test['Survived'].value_counts()



#同上，调用matplotlib库中的axiss模块,用条形图统计train表的 survived 字段的个数，宽度0.2
#为x轴标题 Survived(0:遇难 1：幸存  ，y轴 Counts() ，字体设为fontsize=15
from matplotlib import pyplot as plt
plt.rcParams['font.family']='SimHei'
ax = rst_train['Survived'].value_counts().plot(kind='bar',width=0.2)
ax.set_xlabel('Survived(0:遇难 1：幸存',fontsize=15)
ax.set_ylabel('Counts()',fontsize=15)
plt.show()

#=>是aram 2.rcParmns后面是[] 2.xlabel后跟() 3.显示图表是plt.show()
```



```python
```



```python
```





```python
```















## 十、正则

### 13.1match匹配

```python
## 13.1match匹配
## 13.1.1 匹配字符串
## 13.1.2匹配数字
#匹配 7Hello Python 的 7Hello ,并打印内容和跨度
#用两种正则,在0到9中任意一个数字来匹配

import re
# rst=re.match('[0-9]Hello','7Hello Python')
rst=re.match('\dHello','7Hello Python')
print(rst.span())
print(rst.group())


#同1，用其中一种方法改为匹配0到9之间任意多个数字

rst=re.match('\d*Hello','7Hello Python')
print(rst.span())
print(rst.group())


#同上,但不能没有数字

rst=re.match('\d+Hello','7Hello Python')
print(rst.span())
print(rst.group())


#无视大小写,用hello的完成上述匹配
#>用两种方法

# rst=re.match('7[Hh]ello','7Hello Python')
rst=re.match('7hello','7Hello Python',re.I)
print(rst.span())
print(rst.group())


#匹配 0123456789hello 前7个数字

rst=re.match('\d{,7}','0123456789hello')
print(rst.span())
print(rst.group())
#=> *和{，7}同时表示数量，冲突了,所以只能用{}


#同上，添加代码，实现显示前3个数字

rst=re.match('\d{3,7}?','0123456789hello')
print(rst.span())
print(rst.group())


#同上，用？写出一个匹配三位数通用的正则表达式

rst=re.match('[1-9]?\d?\d?','0123456789hello')
print(rst.span())
print(rst.group())
#=>?的用处除了倒置另一项，还可以判断是与不是，相当与集合的属于


#同上显示前11个大写小写字母、数字和下划线
#用两种方法

# rst=re.match('[a-zA-Z0-9]{,11}','0123456789hello')
rst=re.match('\w{,11}','0123456789hello')
print(rst.span())
print(rst.group())

#匹配所有百位在6-9，个位在不能为4的二位数字,最后再单独判断100 列表 [58,87,92,95,61,49,100]

ls=[58,87,92,95,61,49,100]
for item in ls:
    rst=re.match('[6-9][1-35-9]|100',str(item))
    if rst:
        print(item)


#匹配8.0 同时匹配实数以1-9为开头，数字末尾
a=8.0
rst=re.match("^[1-9]?\.\d$",str(a))
print(rst.span())
print(rst.group())        


#构造对象patten，用其来匹配 1354602179@qq.com 7354602179@163.com 1354602179@126.com 三个邮箱，设置首字母在1-3内
#输出符合，不符合。

ls=['1354602179@qq.com','7354602179@163.com','1354602179@126.com']
patten=re.compile('^[1-3]\w{,20}@(qq|163|126)\.com')
for item in ls:
    rst=patten.match(str(item))
    if rst:
        print('{}符合'.format(item))
    else:
        print('{}不符合'.format(item))
#=>1.python的.用\.来表示 2.调用patten，patten就像一个对象.这个对立中包含着match 3.为了逻辑清晰，|要配合小括号，以表示块
```



### 13.3search



```python
#构造对象patten,用来扫描整个字符串，打印整个字符串并标记前两个数字子串
#字符串 Hello 123456789 Word_This is just a test 666 Test123  用两种方式打印整个字符串、字符串所有符合模式的子串，和第二个符合要求的子串

patten=re.compile('(\d+).*?(\d+).*')
rst=re.search(patten,'Hello 123456789 Word_This is just a test 666 Test123')
print(rst.group(0))
print(rst.groups())
print(rst.group(2))
#=> .表示可以匹配任何单个字符 2..*任何字符0个或多个  3.()?是返回，不是执行下面的模式 


#同上，匹配出形式为列表，并打印这个
rst=re.findall(patten,'Hello 123456789 Word_This is just a test 666 Test123')
for item in rst:
    if rst:
        print(item)

        
        
#运行下列程序，写出match、search、fiandall最本质的区别
rst=re.match('\d*','123456789 Word_This is just a test 666 Test123')
print(rst.group())

rst=re.search('\d+.*?','qqq123456789 Word_This is just a test 666 Test123')
print(rst.group())

rst=re.findall('\d+.*?','123456789 Word_This is just a test 666 Test123')
for item in rst:
    if rst:
        print(item)
#=>match:从字符串起始位置开始一个一个匹配 search：返回所有字符串中第一个匹配的 finall:返回字符串中所有匹配的子串      


phone='2004-959-599 # ndjwoqejw'
# num=re.sub(r' #.*','',phone) #替换成''
# print('电话号码：',num) 
#移除非数字符号
num=re.sub(r'\D','',phone) #大写是相反的意思
print('电话号码：',num) 



#用替换和移除非数字符号方法提取 2004-959-599 # ndjwoqejw 中的电话号码，并打印
phone='2004-959-599 # ndjwoqejw'
num=re.sub(r'#.*','',phone) #和后面的所有字符一起替换成''
print(num) 
num=re.sub(r'\D','',phone) #大写是相反的意思
print('电话号码：',num) 


#以-、#、空格来分割同上
re.split('-|#| ','2004-959-599 # ndjwoqejw')


#在搜索中设置无视大小写、多行匹配、原生串来匹配字符串 Cats are smarter \ than dogs 标记出字符串中的Cat和smarter
#如果搜索成功，打印符合模式的字符串、所有标记、标记1。否则返回“没找到”
#\是续航符
line = "Cats are smarter \
than dogs";
rst = re.search( r'(.*) are (.*?) .*', line, re.M|re.I)
if rst:
    print(rst.group())
    print(rst.groups())
    print(rst.groups(1))  
else:
    print('没找到')

```











## 十一、补充部分

### 11.1分割

```python
#对字符串 'hello world how are you' 以w为分割线，分割字符串

'hello world how are you'.split('w')


#同上以‘e’分割，每个字符后以…分割。

'...'.join('hello world how are you').split('e')
#分开以‘’分开
#谁分开，谁就消失
#slipt后面一定要加''
```



### 11.2增长字符

```python
#元组形式增长
def fun(x,y,*args):
    print(x,y,args)
fun(1,2,3,4,5)


#打包成字典格式
def fun(**kwargs):
    print(kwargs)
fun(a=1.2,b=3,c=3) #一个键只能对应一个值


def fun(arg,*args,**kwargs):
    print(arg,args,kwargs)
fun(1,2,3,5,67,a=1,b=1,c=3)
```



### 11.3文件

```python
#补2 打开文件
fp=open(r'D:\weww.txt','w') #w可写 w会打开后清空原来的内容，再写入
#upper变大写
str=input("in\n")
str=str.upper()
fp.write(str)
fp=open(r'D:\weww.txt','r')
print(fp.read())
fp.close

```



### 11.4 字典

```python
#>对字典d={'name':'张三','age':18,'sex':'M'} 进行增删改查，1.添加一个健值对sc:90：9； 2.删除sex健值对； 3.改写sc的值为100； 4.查询打印name键的值
#最后输出{'name':'张三'，'age'：18.'sc'：100}
""" 
d={'name':'张三','age':18,'sex':'M'}
d['sc']=90
del d['sex']
d['sc']=100
print(d['name'])
print(d)
 """
#=>1.健值对的健一直要加''


#取出 狼的值
townee = [
    {'海底王国':['小美人鱼''海之王''小美人鱼的祖母''五位姐姐'],'上层世界':['王子','邻国公主']},
    '丑小鸭','坚定的锡兵','睡美人','青蛙王子',
    [{'主角':'小红帽','配角1':'外婆','配角2':'猎人'},{'反面角色':'狼'}]
    ]
print(townee[5][1]['反面角色'])


```



11.5 练习题

```python
#编程实现微信发红包程序并验证，100元钱，随机发给15人，每人至少有1元（设每个红包为整数）


import random


def luck_money(total, num):
    tmp = num
    for i in range(num-1):       #循环num-1次，根据[0.01 ,total/num*2]的规则生成9个红包
        hb = round(random.uniform(0.01, total/num*2), 2)
        total = total - hb
        if total <= num*1:   # 为了保证每个人最少能拿到0.01元，则做一个判断，如果余额不足的情况，上一个红包的金额=余额-（剩余的人数*0.01），余下所有人拿到的都是0.01
            total = total + hb
            num -= 1
            hb = total - num*0.01
            yield round(hb, 2)
            for j in range(i+1, tmp):   #接着上面的循环，
                yield 0.01
            break                       #循环完后结束上次循环
        yield hb
        num -= 1
    else:                       #最后一个红包如果余额还有，所有余额给分给最后一个
        total = round(total, 2)
        yield total


g = luck_money(100, 15)
for i in g:
    print(i)
```













## 十二、项目



### 1.人狗大战

```python
#>实现1:函数用字典实现已知狗品种攻击力的调用，没有默认30，人大于等于18，攻击力40，小于则输出20.输出形式：狗_打了人_,人掉血_，剩余血量_
attack_vals={
    '泰迪':30,
    '藏獒':70,
    '哈士奇':40
}
"""
"""
def dog(name,breed):
    data={'name':name,
        'breed':breed,
        'life_val':100
        }
    if data['breed'] in attack_vals:
        data['attack_vals']=attack_vals[breed]
    else:
        data['breed']=20
    return data

def person(name,age):
    data={'name':name,
        'age':age,
        'life_val':100
    }
    if data['age']>=18:
        data['attack_vals']=40
    else: data['attack_vals']=20
    return data
d1=dog('小黄','哈士奇')
p1=person('张三',19)

def dog_beat(dog,person):
    person['life_val']-=dog['attack_vals']
    print('狗{}打了人{},人掉血{},剩余血量{}'.format(dog['name'],person['name'],dog['attack_vals'],person['life_val']))

def person_beat(dog,person):
    dog['life_val']-=person['attack_vals']
    print('人{}打了狗{},人掉血{},剩余血量{}'.format(person['name'],dog['name'],person['attack_vals'],dog['life_val']))

dog_beat(d1,p1)
person_beat(d1,p1)

#>实现2:函数嵌套
attack_vals={
    '泰迪':30,
    '藏獒':70,
    '哈士奇':40
}
def dog(name,breed):
    data={'name':name,
        'breed':breed,
        'life_val':100
        }
    if data['breed'] in attack_vals:
        data['attack_vals']=attack_vals[breed]
    else:
        data['breed']=20
    def dog_beat(person):
        person['life_val']-=data['attack_vals']
        print('狗{}打了人{},人掉血{},剩余血量{}'.format(data['name'],person['name'],data['attack_vals'],person['life_val']))
    data['dog_beat']=dog_beat
    return data
def person(name,age):
    data={'name':name,
        'age':age,
        'life_val':100
    }
    if data['age']>=18:
        data['attack_vals']=40
    else: data['attack_vals']=20
    def person_beat(dog):
        dog['life_val']-=data['attack_vals']
        print('人{}打了狗{},人掉血{},剩余血量{}'.format(data['name'],dog['name'],data['attack_vals'],dog['life_val']))
    data['person_beat']=person_beat
    return data
d1=dog('小黄','哈士奇')
p1=person('张三',19)
d1['dog_beat'](p1)
p1['person_beat'](d1)
#=>1.数的嵌套需要将嵌套的函数定义在元组里，再用d1['bite']来调用


#>实现3:面向对象

class Dog:
    def __init__(self,name,attack_vals,life_val):
        self.name=name
        self.attack_vals=attack_vals
        self.life_val=life_val
    def person(self,person_obj):
        self.life_val-=p1.attack_vals
        print('人{}打了狗{},狗掉血{},剩余血{}'.format(p1.name,self.name,p1.attack_vals,self.life_val))

class Person:
    def __init__(self,name,attack_vals,life_val):
        self.name=name
        self.attack_vals=attack_vals
        self.life_val=life_val
    def dog(self,dog_obj):
        self.life_val-=d1.attack_vals
        print('狗{}打了人{},人掉血{},剩余血{}'.format(d1.name,self.name,d1.attack_vals,self.life_val))
d1=Dog('小黄',40,100)
p1=Person('小明',40,100)
p1.dog(d1)
d1.person(p1)

#=>1.另一个类的实例变量只有通过像 p1.dog(d1)这样的调用才可以使用 2.实例变量都是调用来的

```



### 2.抓精灵

```python
# 抓精灵
import random
import time

monsters_pool = ['火柴鼠','瞌睡熊','板牙狸','博学企鹅','绅士企鹅',
                 '漂浮龟','皮皮','贪玩虎','黑客','蹦蹦','乌鸦',
                 '竹叶青','小青龙']
monsters_list = []
targets_list = []
bag = []
monster_flag = False

def put_into_bag(monster):
    if len(bag) < 2:
        bag.append(monster)
        print("--现在包里的小精灵是:",bag)
    else:
        print("--现在的包里的小精灵是:",bag)
        print("--你的目标是:",targets_list)
        index = int(input("--你的包满了，你要放弃的小精灵序号是:"))
        print("--你放弃了%s" % bag.pop(index))
        put_into_bag(monster)

def find_monster(step):
    global monster_flag
    if step % 3 == 0 or step % 5 == 0:
        monster_flag = True
        print("--你遇到一个小精灵")
    else:
        print("请继续寻找小精灵")
        monster_flag = False

def check_target():
    flag = 1
    for i in targets_list:
        if i not in bag:
            flag = 0
            break
    if flag == 1:
        print("--恭喜你完成了任务！")
    else:
        print("--很遗憾，你没有完成任务！")

if __name__ == '__main__': #下面的这一整块模块，仅我自己可见，其他人不可调用该模块
    for i in range(20):
        monsters_list.append(random.choice(monsters_pool)) #random.choice 随机选择一个列表中的某一项
    print("--野外有这些精灵:",monsters_list)
    for i in range(2):
        targets_list.append(random.choice(monsters_list))
    print("--你的【目标】是要抓住这些精灵:",targets_list)
    while True: #print'''呈现方式不变
        choice = input(''' 
        ---------------------
        请输入你的选择：
        w:向前走
        a:向左走
        s:向后走
        d:向右走
        c:抓小精灵
        t:检查背包/确认目标
        q:退出游戏\n''')
        if choice == "q":
            check_target()
            break
        elif choice =="t":
            print("--背包中有:",bag)
            print("--你的目标是:",targets_list)
        elif choice == "w":
            step = random.randint(10,50)
            print("--向前走了%i步" % step)
            find_monster(step)
        elif choice =="a":
            step = random.randint(10,50) # 随机选一个10到50（不知道是不是假尾巴：）的整数
            print("--向左走了%i步" % step)
            find_monster(step)
        elif choice == "s":
            step = random.randint(10,50)
            print("--向后走了%i步" % step)
            find_monster(step)
        elif choice == "d":
            step = random.randint(10,50)
            print("--向右走了%i步" % step)
            find_monster(step)
        elif choice == "c" and monster_flag: #monster_flag=
            monster_flag = False
            monster_hp = random.randint(70,100)
            our_ap = random.randint(70,120)
            print("--野生小精灵的生命值为: %d" % monster_hp)
            print("--你的战斗力为: %d " % our_ap)
            print("--你扔出了精灵球")
            index = random.randint(0, len(monsters_list)-1) #从零开始，包含尾巴，len是从1开始数的
            time.sleep(0.5)
            for i in range(3):
                print("精灵球晃了晃...")
                time.sleep(random.random()) #画面暂停几秒
            if abs(monster_hp - our_ap) <= 10:
                monster_caught = monsters_list.pop(index)
                print("--你抓住了【%s】" % monster_caught)
                put_into_bag(monster_caught)
            else:
                print("--很遗憾，你没有抓住【%s】" % monsters_list[index])
            
        elif choice == "c" and not monster_flag:
            print("--你还没遇到小精灵")
        else:
            print("--你输入了一个无效命令")

```

---







### 3.龟抓鱼

```python
#龟抓鱼
import random as r
import time
legal_x=[0,10]
legal_y=[0,10]

class Turtle:
    def __init__(self):
    #初始体力
        self.power=100
    #初始位置随机
        self.x=r.randint(legal_x[0],legal_x[1])
        self.y=r.randint(legal_y[0],legal_y[1])
    def move(self):
        new_x=self.x+r.choice([1,2,-1,-2])
        new_y=self.y+r.choice([1,2,-1,-2])
        
#检查移动后是否超出场景x轴边界
        if new_x<legal_x[0]:
            self.x=legal_x[0] + (legal_x[0] -new_x)
        elif new_x>legal_x[1]:
            self.x=legal_x[1] - (new_x - legal_x[1])
        else:
            self.x=new_x
#检查移动后是否超出场景y轴边界
        if new_y < legal_y[0]:
            self.y=legal_y[0]+(legal_y[0]-new_y)
        elif new_y>legal_y[1]:
            self.y=legal_y[1]-(new_y-legal_y[1])
        else:
            self.y=new_y
#体力消耗
        self.power-=1
#返回移动后的新位置
        return (self.x,self.y)

    def eat(self):
        self.power+=20
        if self.power>100:
            self.power=100
            
class Fish:
    def __init__(self,no):
        self.x=r.randint(legal_x[0],legal_x[1])
        self.y=r.randint(legal_y[0],legal_y[1])
        self.no=no
    def getNo(self):
        return self.no
     
    def move(self):
        # 随机计算方向并移动到新的位置（x,y）
        new_x=self.x+r.choice([1,-1])
        new_y=self.y+r.choice([1,-1])
        #检查移动后是否超出场景x轴边界
        if new_x<legal_x[0]:
            self.x=legal_x[0]+(legal_x[0]-new_x)
        elif new_x>legal_x[1]:
            self.x=legal_x[1]+(new_x-legal_x[1])
        else:
            self.x=new_x
#检查移动后是否超出场景y轴边界
        if new_y<legal_y[0]:
            self.y=legal_y[0]+(legal_y[0]-new_y)
        elif new_y>legal_y[1]:
            self.y=legal_y[1]+(new_y-legal_y[1])
        else:
            self.y=new_y
        return (self.x,self.y)
            
turtle=Turtle()
fish=[]
for i in range(10):
    new_fish=Fish(i+1)
    fish.append(new_fish)

while True:
    if len(fish)<=0:
        print('鱼儿都吃完了，游戏结束！')
        break
    if turtle.power <= 0:
        print('乌龟体力耗尽，挂掉了')
        break
        
    pos=turtle.move()
    
    for each_fish in fish:
        if each_fish.move() == pos:
        #鱼。。。被吃掉了
            turtle.eat()
            time.sleep(0.5)
            fish.remove(each_fish)
            print("鱼%d被吃掉了……" % each_fish.no)
```



### 4.学生管理系统

#### 4.1模型

```python
import student_manager

data = {}
def register():
    while True:
        teacher_name = input('请输入账号(3-6位):')
        if not 3 <= len(teacher_name) <=6:
            print('账号不符合要求，请重新输入！')
        else:
            break

    while True:
        password = input('请输入密码(6~12位):')
        if not 6 <= len(password) <=12:  
            print('密码不符合要求，请重新输入！')      
        else:
            break

    data[teacher_name] = password
    print(data)


def login():
    teacher_name = input('请输入老师账号：')
    if teacher_name not in data:
        print('登录失败！该账号没有注册！')
        return
    password = input('请输入密码：')
    if data[teacher_name] == password:
        student_manager.show_manager()
    else:
        print('密码错误，登陆失败！')




def start():
    try:
        with open('E:\python\student_manager\welcome.txt','r',encoding='utf8') as file:
            content = file.read()
            while True:
                operator = input(content+'\n请选择(1-3):')
                if operator == '1':
                    login()
                elif operator == '2':
                    register()
                elif operator == '3':
                    #break
                    #exit(0)
                    sys.exit(0)
                else:
                    print('输入有误！')
    except FileNotFoundError:
        print('文件未找到')


if __name__=='__main__':
    start()
```



```python
name = ''
def show_manager():
    try:
        with open('E:\python\student_manager\student_page.txt','r',encoding='utf8') as file1:
            content = file1.read() % name
            while True:
               input(content+'\n请选择(1-5):')
    except FileNotFoundError:
        print('文件未找到')
       
```

熵：

1.with 是什么	=>上下文管理器，文件、socket、数据库连接都可以自动 关闭，要求 后面的对象需要实_enter_和exit魔法方法

2.打开当前文件夹不是./是什么？=>vscode不需要./

4.json是什么

3.如何加密

5.如何写入数据库

6.以何种方式存储数据

7.如何如何写入json

8.如何读取json

4.2序列化与反序列化

> 序列化：讲数据从内存持久化保存到硬盘的过程
>
> 反序列化：讲数据从硬盘加载到内存的过程
>
>
> write时，只能写入字符串和二进制
>
> 将数据转换成为字符串：reper/str、使用json模块
>
> json 本质就是字符串，区别在于json里要是用双引号表示字符串
>
> '["zhangsan","lisi","jack","tony"]'
>
> 将数据转换成为二进制：使用pickle模块
> 
>
>
> json里将数据持久有两种方法：
>
> dumps:将数据转换成为json字符串，不会将数据保存到文件里
>
> dunp:将数据转化成为json字符串的同时写入到指定文件。
> loads:读取文件，把读取的内容加载成为python里的数据
>
> load:读取一个文件，并把文件里的json字符串加载成为一个对象



完整代码

#### file_manager.py

```python
base_dir = 'files'

def read_file(file_name):
    try:
        with open(base_dir + file_name,'r',encoding='utf8') as file:
            content = file.read()
            return content
    except FileNotFoundError:
        print('文件未找到')

def write_json(file_name,data):
     with open(base_dir + file_name,'w', encoding='utf8') as file:
        import json
        json.dump(data,file)

def read_json(file_name,default_data):
    try:
        with open(base_dir + file_name,'r',encoding='utf8') as file:
            import json
            return json.load(file)
    except FileNotFoundError:
        # print('文件未找到')
        return default_data
        

```





#### index.py

```python
import file_manager
import student_manager
import sys
import model


def register():
    # 读取文件，查看文件是否有数据，如果文件不存在，默认是一个字典   
    data = file_manager.read_json('\data.json',{})
    while True:
        teacher_name = input('请输入账号(3-6位):  ')
        if not 3 <= len(teacher_name) <=6:
            print('账号不符合要求，请重新输入!')
        else:
            break
    
    if teacher_name in data:
        print('注册失败!该账号已经注册过!')
        return
          
    while True:
        password = input('请输入密码(6~12位):')
        if not 6 <= len(password) <=12:  
            print('密码不符合要求，请重新输入!')      
        else:
            break

    # 用户名密码器都已经正确以后，创建teacher对象
    t = model.Teacher(teacher_name,password)
    # teacher[teacher_name] = password
    data[t.name] = t.password
    # data[teacher_name] = password
    # sql.write(t)
    file_manager.write_json('\data.json',data)

def login():
    data = file_manager.read_json('\data.json',{})
    teacher_name = input('请输入老师账号:')

    if teacher_name not in data:
        print('登录失败!该账号没有注册!')
        return
    password = input('请输入密码:')
    import tools
    if data[teacher_name] == tools.encrypt_password(password):
        student_manager.name = teacher_name
        student_manager.show_manager()
    else:
        print('密码错误，登陆失败!')

def start():
    file_manager.base_dir = 'files'
    content=file_manager.read_file('\welcome.txt') 
    while True:
            operator = input(content+'\n请选择(1-3):')
            if operator == '1':
                login()
            elif operator == '2':
                register()
            elif operator == '3':
                #break
                #exit(0)
                sys.exit(0)
            else:
                print('输入有误！')

#不能更改写入
""" 
def start():
    try:
        with open('E:\python\student_manager\welcome.txt','r',encoding='utf8') as file:
            content = file.read()
            while True:
                input(content)
    except FileNotFoundError:
        print('文件未找到')
  """

if __name__=='__main__':
    start()
```





#### model.py

```python

class Teacher():
    def __init__(self,name,password):
        import tools
        self.name = name
        self.password = tools.encrypt_password(password)

class Student():
    def __init__(self,s_id,name,age,gender,tel):
        self.s_id = s_id
        self.name = name
        self.age = age
        self.gender = gender
        self.tel = tel
```





student_manager.py

```python
import file_manager
import model

name = ''
num = 0

def add_student():
    x = file_manager.read_json('\\'+name + '.json',{})
    if not x:
        students = []

    else:
        students = x['all_student']
        global num
        num = int(x['num'])
    while True:
        s_name = input('请输入学生姓名(英文):')
        if not s_name.isalpha() :
            print('只能输入英文字母,请重新输入')
            continue
            
        s_age = input('请输入年龄:')
        if not s_age.isdigit() or not 0 <= int(s_age) <=150:
            print('只能输入的3位年龄,请重新输入')
            continue
        
        s_gender = input('请输入性别(man | female):')
        if not (s_gender == 'man' or s_gender =='female'):
            print('只能输入(man | female),请重新输入')
            continue

        s_tel = input('请输入11位的电话号码:')
        if not s_tel.isdigit() or not  len(s_tel) == 11 and 12:
            print('只能输入11位的电话号码,请重新输入')
            continue

        num += 1
        #字符串的zfill方法，在字符串的前面补0 rjust，ljust是加空格的
        s_id = 'stu_' + str(num).zfill(4)

        # 创建一个Student对象
        s = model.Student(s_id,s_name,s_age,s_gender,s_tel)

        students.append(s.__dict__)
        #拼接字典
        data = {'all_student': students,'num': str(num)}
        # print(data)
        file_manager.write_json('\\'+name + '.json',data)
        choice = input('添加成功！\n1.继续\n2.返回\n请选择(1-2):')

        if choice == '2':
            break

def show_student():
    key = value = ''
    x = input('1.查看所有学生\n2.根据姓名查找\n3.根据学号查找\n4.其他:返回\n请选择:')
    y = file_manager.read_json('\\'+name + '.json',{})
  
    # if not y:
    #     students = []
    # else:
    #     students = y['all_student']

    students = y.get('all_student',[])
    if not students:
        print('该老师还没有学员，请添加学员')
        return 

    # if x == '1': #查询所有
    #     for student in  students:
    #         print('学号:{s_id},姓名:{name},性别:{gender},年龄:{age},电话:{tel}'.format(**student))        

    # elif x == '2':
    #     s_name = input('请输入学员姓名:')
    #     # same_name_students = []
    #     # for student in students:
    #     #     if student['name'] == s_name:
    #     #         same_name_students.append(student)
    #     # filter结果是一个filter类，它是一个可迭代对象        
    #     same_name_students = filter(lambda s: s['name'] == s_name, students)
    #     if not same_name_students:
    #         print('未找到学员')
    #     for student in  same_name_students:
    #         print('学号:{s_id},姓名:{name},性别:{gender},年龄:{age},电话:{tel}'.format(**student))

    # elif x == '3':
    #     s_id == input('请输入学员姓名')
    #     same_id_students = filter(lambda s: s['s_id'] == s_id, students)
    #     if not same_id_students:
    #         print('未找到学员')
    #     for student in  same_id_students:
    #         print('学号:{s_id},姓名:{name},性别:{gender},年龄:{age},电话:{tel}'.format(**student))
    # else:
    #     pass
 

 
    # if x == '1':
    #     pass

    # elif x == '2':
    #     s_name = input('请输入学员姓名:')      
    #     students = filter(lambda s: s['name'] == s_name, students)
    # elif x == '3':
    #     s_id == input('请输入学员id')
    #     students = filter(lambda s: s['s_id'] == s_id, students)
    # else:
    #     pass
    # if not students:
    #     print('未找到学员')
    #     return
    
    # for student in students:
    #     print('学号:{s_id},姓名:{name},性别:{gender},年龄:{age},电话:{tel}'.format(**student))



 
    if x == '1':
        pass

    elif x == '2':
        value = input('请输入学员姓名:')      
        key = 'name'

    elif x == '3':
        value = input('请输入学生学号')
        key = 's_id'

    # elif x == '3':
    #     value == input('请输入学员id:')
    #     key = 's_id'
        
    else:
        print('输入1-4')
        return

    
    if x == '2'or x == '3':
        students = filter(lambda s:s.get(key,"") == value,students)
        
    if not students:
        print('未找到学员')
        return
    
    for student in students:
        print('学号:{s_id},姓名:{name},性别:{gender},年龄:{age},电话:{tel}'.format(**student))
        # print('学号:{s_id},姓名:{name},性别:{gender},年龄:{age},电话:{tel}'.format(**student))

def modify_student():

    y = file_manager.read_json('\\'+name + '.json',{})
    all_students = y.get('all_student',[])
    key = value = ''
    if not all_students:
        print('该老师还没有学员，请添加学员')
        return 

    choine = input('1.按姓名修改\n2.按学号修改\n其他:返回\n请选择')
    if choine == '1':
        key = 'name'
        value = input('请输入要修改的学生名字:')
    elif choine == '2':
        key = 's_id'
        value = input('请输入要修改的的学生学号')
    else:
        return


    students = list(filter(lambda s:s.get(key,{}) == value,all_students))
    # students = list(filter(lambda s:s.get(key,'') == value,all_students))

    if not students:
        print('没有找到对应的学生')
        return

    #在python里，只要函数能够分隔作用域
    for i, s in enumerate(students):
        print('{x} 学号:{s_id},姓名:{name},性别:{gender},年龄:{age},电话:{tel}'.format(x=i,**s))

    n  = input('请输入需要修改的学生的标号（0~{}),q-返回:'.format(i)) #有风险

    if not n.isdigit() or not 0 <= int(n) <=i:
        print('输入的内容不合法')
        return
    
    
    all_students.remove(students[int(n)])
    y['all_student'] = all_students
    file_manager.write_json('\\'+name+'.json',y)
    print('已删除，请输入新信息')


    y = file_manager.read_json('\\'+name + '.json',{})
    students = y['all_student']
    while True:
        s_name = input('请输入新的学生姓名:')
        s_age = input('请输入新的年龄:')
        s_gender = input('请输入新的性别:')
        s_tel = input('请输入新的电话号码:')

        global num
        num += 1
        #字符串的zfill方法，在字符串的前面补0 rjust，ljust是加空格的
        s_id = 'stu_' + str(num).zfill(4)

        # 创建一个Student对象
        s = model.Student(s_id,s_name,s_age,s_gender,s_tel)

        students.append(s.__dict__)
        #拼接字典
        data = {'all_student': students,'num': len(students)+2}
        # print(data)
        file_manager.write_json('\\'+name + '.json',data)
        choice = input('添加成功！\n1.继续\n2.返回\n请选择(1-2):')

        if choice == '2':
            break

def delect_student():
    y = file_manager.read_json('\\'+name + '.json',{})
    all_students = y.get('all_student',[])
    key = value = ''
    if not all_students:
        print('该老师还没有学员，请添加学员')
        return 



    choine = input('1.按姓名删\n2.按学号删\n其他:返回\n请选择(1-2)')
    if choine == '1':
        key = 'name'
        value = input('请输入要删除的学生名字:')
    elif choine == '2':
        key = 's_id'
        value = input('请输入要删除的学生学号')
    else:
        return

    students = list(filter(lambda s:s.get(key,[]) == value,all_students))
    # students = list(filter(lambda s:s.get(key,'') == value,all_students))

    if not students:
        print('没有找到对应的学生')
        return

    #在python里，只要函数能够分隔作用域
    for i, s in enumerate(students):
        print('{x} 学号:{s_id},姓名:{name},性别:{gender},年龄:{age},电话:{tel}'.format(x=i,**s))
    n  = input('请输入需要删除的学生的标号（0~{}),q-返回:'.format(i)) #有风险

    if not n.isdigit() or not 0 <= int(n) <=i:
        print('输入的内容不合法')
        return
    #将学生从all_students删除
    #all_students.pop(n)
    all_students.remove(students[int(n)])
    y['all_student'] = all_students
    file_manager.write_json('\\'+name+'.json',y)
    print('删除成功')

def show_manager():
    content = file_manager.read_file('\student_page.txt') % name
    while True:
        print(content)
        operator = input('请选择(1-5):')
        if operator == '1':
            add_student()
        elif operator == '2':
            show_student()
        elif operator == '3':
            modify_student()
        elif operator == '4':
            delect_student()
        elif operator == '5':
            break
        else:
            print('输入有误')
        

```







tool.py

```python
import hashlib


def encrypt_password(passwd,x='dfsdfhfhkdk'):
    h = hashlib.sha256()
    h.update(passwd.encode('utf8'))
    h.update(x.encode('utf8'))
    return h.hexdigest()


```























### 5.飞机大战


1.以C/S的界面完成；
2.实现功能：
2.1 玩家飞机可以左右方向移动以躲避子弹；
2.2 玩家飞机可以发射子弹；
2.3敌方飞机位于屏幕的顶部保持左右移动，并且随
机地向玩家飞机发射子弹；
3.实现方法：用PyCharm实现，安装PyCharm，
并添加
第三方模块pygame模块；搭建游戏界面。

```python

```

完整代码

#### game.py

```python
import pygame
import sys
from game_items import *
from game_music import *
from game_hud import *
import random

class Game():
    def __init__(self):
        self.main_window = pygame.display.set_mode(SCREEN_RECT.size)
        pygame.display.set_caption('飞机大战')
        self.is_game_over =  False
        self.is_game_pause =   False

        self.all_group = pygame.sprite.Group()
        self.enemies_group = pygame.sprite.Group()
        self.supplies_group = pygame.sprite.Group()

        self.all_group.add(Background(False),Background(True))

        #创建游戏控制面板
        self.hud_panel = HUDPanel(self.all_group)

        #创建英雄飞机精灵
        self.hero_sprite = Hero(self.all_group)
        self.hud_panel.show_bomb(self.hero_sprite.bomb_count)

        #初始化敌机
        self.create_enemies()

        """ #测试，让敌机静止显示
        for enemy in self.enemies_group.sprites():
            enemy.speed = 0
            enemy.rect.y += 400
        self.hero_sprite.speed = 1 """

        #初始化道具
        self.create_supply()

        #音乐播放器 
        # pygame.mixer.music.load('./res/sound/game_music.ogg')
        # pygame.mixer.music.play(-1)
        # hero_down_sound = pygame.mixer.Sound('./res/sound/me_down.wav')
        # hero_down_sound.play()


        self.player = MusicPlayer('game_music.ogg')        
        self.player.play_music()



    def reset_game(self):
        self.is_game_over = False
        self.is_game_pause = False

        # 重置面板
        self.hud_panel.reset_panel()

        # 重置英雄飞机位置
        self.hero_sprite.rect.midbottom = HERO_DEFAULT_MID_BOTTOM

        # 销毁所有的敌人飞机
        for enemy in self.enemies_group:
            enemy.kill()

        # 销毁所有的子弹
        for bullet in self.hero_sprite.bullets_group:
            bullet.kill()

        # 重新创建飞机
        self.create_enemies()

        # 初始化道具
        self.create_supply()
   
    def start(self):
        clock = pygame.time.Clock()
        # 动画帧数计数器
        frame_count = 0
        while True:
            # 判断英雄是否已经死亡
            self.is_game_over = self.hud_panel.lives_count == 0
            if self.event_handler():
                # 退出游戏之前要保存最好成绩
                self.hud_panel.save_best_score()
                return               
            if self.is_game_over:
                # print('游戏已经结束，按空格键重新开始……')
                self.hud_panel.panel_paused(True, self.all_group)

            elif self.is_game_pause:
                # print('游戏已经暂停，按空格键继续')
                self.hud_panel.panel_paused(False, self.all_group)
            else:
                self.hud_panel.panel_resume(self.all_group)
                # print('游戏进行中……')

                # 处理长按事件
                keys = pygame.key.get_pressed()  # get_pressed() 得到一个元组，每一个按键在元组里都有一个下标，对应下标值为 1 则说明按键被按下
                move_hor = keys[pygame.K_RIGHT] - keys[pygame.K_LEFT]  # 水平的移动基数
                move_ver = keys[pygame.K_DOWN] - keys[pygame.K_UP]  # 垂直的移动基数

                #检测碰撞
                self.check_collide()

                frame_count = (frame_count + 1) % FRAME_INTERVAL
                self.all_group.update(frame_count == 0, move_hor, move_ver)

            self.all_group.draw(self.main_window)

            pygame.display.update()
            clock.tick(60)
           
    def event_handler(self):
        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                return True
            if event.type == pygame.KEYDOWN and event.key == pygame.K_ESCAPE:
                return True
            if event.type == pygame.KEYDOWN and event.key == pygame.K_SPACE:
                if self.is_game_over:
                    self.reset_game()
                else:
                    self.is_game_pause = not self.is_game_pause
                    self.player.pause_music(self.is_game_pause)  # 切换背景音乐状态


            #必须在游戏结束也没暂停才能执行操作
            if not self.is_game_over and not self.is_game_pause:
                if event.type == pygame.KEYDOWN and event.key == pygame.K_b:
                    #释放有一颗炸弹，并修改炸弹数量
                    if self.hero_sprite.hp > 0 and self.hero_sprite.bomb_count > 0:
                        self.player.play_sound('use_bomb.wav')

                    score = self.hero_sprite.blowup(self.enemies_group)
                    self.hud_panel.show_bomb(self.hero_sprite.bomb_count)
                    if self.hud_panel.increase_score(score):
                        self.create_enemies()

                elif event.type == HERO_DEAD_EVENT:
                    # 玩家飞机死亡
                    self.hud_panel.lives_count -= 1
                    self.hud_panel.show_lives()

                    self.hud_panel.show_bomb(self.hero_sprite.bomb_count)

                elif event.type == HERO_POWER_OFF_EVENT:
                    # 无敌时间结束
                    self.hero_sprite.is_power = False
                    pygame.time.set_timer(HERO_POWER_OFF_EVENT, 0)  # 设置定时器延时为 0，可用取消定时器

                elif event.type == HERO_FIRE_EVENT:
                    # 英雄飞机发射子弹定时事件
                    self.player.play_sound('bullet.wav')
                    self.hero_sprite.fire(self.all_group)

                elif event.type == THROW_SUPPLY_EVENT:
                    # 随机抛出一个道具
                    self.player.play_sound('supply.wav')
                    supply = random.choice(self.supplies_group.sprites())
                    supply.throw_supply()

                elif event.type == BULLET_ENHANCED_OFF_EVENT:
                    # 玩家使用双排子弹的时间已经结束，需要恢复为单排的子弹
                    self.hero_sprite.bullets_kind = 0  # 恢复为单排子弹
                    pygame.time.set_timer(BULLET_ENHANCED_OFF_EVENT, 0)  # 取消定时
                





        return

    def create_enemies(self):
        """创建敌机"""
        count = len(self.enemies_group.sprites())
        groups = (self.all_group, self.enemies_group)

        # 根据不同的关卡创建不同数量的敌机
        if self.hud_panel.level == 1 and count == 0:
            # 关卡1
            for i in range(16):
                Enemy(0, 3, *groups)

        elif self.hud_panel.level == 2 and count == 16:
            # 关卡2
            for enemy in self.enemies_group.sprites():
                enemy.max_speed = 5

            for i in range(8):
                Enemy(0, 5 ,*groups)
            for i in range(2):
                Enemy(1, 1, *groups)

        elif self.hud_panel.level == 3 and count == 26:
            # 关卡3
            for enemy in self.enemies_group.sprites():
                enemy.max_speed = 7 if enemy.kind == 0 else 3

            for i in range(8):
                Enemy(0, 7, *groups)
            for i in range(2):
                Enemy(1, 3, *groups)
            for i in range(2):
                Enemy(2, 1, *groups)

    def check_collide(self):
        """检查是否有碰撞"""
        if not self.hero_sprite.is_power:  # 没有无敌才需要检查碰撞
            collide_enemies = pygame.sprite.spritecollide(self.hero_sprite, self.enemies_group,
                                                            False, pygame.sprite.collide_mask)

            collide_enemies = list(filter(lambda x: x.hp > 0, collide_enemies))
                                                                        
            # 撞毁玩家飞机
            if collide_enemies:
                self.player.play_sound(self.hero_sprite.wav_name)
                self.hero_sprite.hp = 0

            # 撞毁敌人飞机
            for enemy in collide_enemies:
                    enemy.hp = 0

             # 子弹和敌机的碰撞分析
            hit_enemies = pygame.sprite.groupcollide(self.enemies_group, self.hero_sprite.bullets_group,
                                       False, False, pygame.sprite.collide_mask)

            for enemy in hit_enemies:

                # 已经被摧毁的飞机不需要再处理
                if enemy.hp <= 0:
                    continue

                for bullet in hit_enemies[enemy]:
                    bullet.kill()  # 销毁子弹
                    enemy.hp -= bullet.damage  # 修改敌机生命值

                    if enemy.hp > 0:
                        continue  # 如果敌机没有被摧毁，则继续遍历下一颗子弹

                    # 当前这一颗子弹已经把敌机摧毁
                    if self.hud_panel.increase_score(enemy.value):
                        self.player.play_sound('upgrade.wav')
                        self.create_enemies()

                    # 这个飞机已经被摧毁，不需要再遍历下一颗子弹了
                    self.player.play_sound(enemy.wav_name)
                    break
        # 检查英雄飞机和道具的碰撞
        supplies = pygame.sprite.spritecollide(self.hero_sprite, self.supplies_group,
                                    False, pygame.sprite.collide_mask)
        if supplies:
            supply = supplies[0]
            self.player.play_sound(supply.wav_name)  # 根据道具类型播放捡道具的音效

            # 根据道具类型产生不同的行为
            if supply.kind == 0:
                self.hero_sprite.bomb_count += 1
                self.hud_panel.show_bomb(self.hero_sprite.bomb_count)

            else:
                self.hero_sprite.bullets_kind = 1  # 修改英雄子弹为双排子弹
                pygame.time.set_timer(BULLET_ENHANCED_OFF_EVENT, 20000)  # 20秒之后重新变为单排子弹

            # 移动道具到屏幕之下
            supply.rect.y = SCREEN_RECT.h

    def create_supply(self):
        """初始化两个道具，并开启投放道具的定时器"""
        Supply(0, self.all_group, self.supplies_group)
        Supply(1, self.all_group, self.supplies_group)

        pygame.time.set_timer(THROW_SUPPLY_EVENT, 30000)


if __name__ == '__main__':
    pygame.init()
    Game().start()
    pygame.quit()
```



#### game_items.py

```python
import pygame
import random

SCREEN_RECT = pygame.Rect(0,0,480,700)
FRAME_INTERVAL = 10                        # 逐帧动画间隔帧数

HERO_BOMB_COUNT = 3                        # 英雄默认炸弹数量
HERO_DEFAULT_MID_BOTTOM = (SCREEN_RECT.centerx,   # 英雄默认初始位置
                           SCREEN_RECT.bottom - 90)

HERO_DEAD_EVENT = pygame.USEREVENT              # 英雄牺牲事件
HERO_POWER_OFF_EVENT = pygame.USEREVENT + 1     # 取消英雄无敌事件
HERO_FIRE_EVENT = pygame.USEREVENT + 2          # 英雄发射子弹事件
THROW_SUPPLY_EVENT = pygame.USEREVENT + 3       # 投放道具事件
BULLET_ENHANCED_OFF_EVENT = pygame.USEREVENT + 4  # 关闭子弹增强事件


class GameSprite(pygame.sprite.Sprite):
    res_path = './res/images/'
    def __init__(self,image_name,speed,*group):
        super(GameSprite, self).__init__(*group)
        self.image = pygame.image.load(self.res_path + image_name)
        self.rect = self.image.get_rect()
        self.speed = speed
        # 生成遮罩属性，提高碰撞检测的执行效率
        self.mask = pygame.mask.from_surface(self.image)    

    def update(self,*args):
        self.rect.y += self.speed
    
class Background(GameSprite):
    def __init__(self, is_alt, *group):
        super(Background,self).__init__('background.png',1,*group)
        if is_alt:
            self.rect.y = - self.rect.h

    def update(self,*args):
        super(Background, self).update(*args)
        if self.rect.y > self.rect.h:
            self.rect.y = - self.rect.y
 
class StatusButton(GameSprite):
    def __init__(self, image_names, *groups):
        #image_name 接收一个元组， 元组的0下标必须时暂停的图片，1下标必须时运行的图片
        super(StatusButton, self).__init__(image_names[0], 0, *groups)

        #准备用于切换显示的两张图片
        self.images = [pygame.image.load(self.res_path+name) for name in image_names]
    
    def switch_status(self, is_pause):
        #根据是否暂停，切换要使用的图片对象
        self.image = self.images[1 if is_pause else 0]

'''标签精灵'''
class Label(pygame.sprite.Sprite):
    '''初始化标签精灵的数据'''
    font_path = './res/font/MarkerFelt.ttc'
    def __init__(self, text, size, color, *groups):
        super(Label,self).__init__(*groups)
        #创建字体对象
        self.font = pygame.font.Font(self.font_path, size)

        #字体颜色
        self.color = color

        #精灵属性
        self.image = self.font.render(text, True, self.color)
        self.rect = self.image.get_rect()

    '''更新显示的文本内容'''
    def set_text(self, text):
        self.image = self.font.render(text, True , self.color)
        self.rect = self.image.get_rect()

class Plane(GameSprite):
    """飞机精灵类"""

    def __init__(self, normal_names, speed, hp, value, wav_name, hurt_name, destroy_names, *groups):
        """飞机类的初始化"""
        super(Plane, self).__init__(normal_names[0], speed, *groups)

        #  飞机基本属性
        self.hp = hp  # 当前生命值
        self.max_hp = hp  # 初始生命值
        self.value = value   # 分值
        self.wav_name = wav_name  # 音效名

        # 飞机要显示的图片
        self.normal_images = [pygame.image.load(self.res_path+name) for name in normal_names]  # 正常状态图像列表
        self.normal_index = 0  # 正常状态图像索引
        self.hurt_image = pygame.image.load(self.res_path + hurt_name)  # 受伤图像
        self.destroy_images = [pygame.image.load(self.res_path+name) for name in destroy_names]  # 摧毁状态图像列表
        self.destroy_index = 0  # 摧毁状态索引

    def reset_plane(self):
        """重置飞机"""
        self.hp = self.max_hp

        self.normal_index = 0
        self.destroy_index = 0

        self.image = self.normal_images[0]

    def update(self, *args):
        """更新状态，准备下一次要显示的内容"""
        # 判断是否要更新
        if not args[0]:
            return

        if self.hp == self.max_hp:
            # 切换要显示的图片
            self.image = self.normal_images[self.normal_index]

            # 计算下一次显示的索引
            count = len(self.normal_images)
            self.normal_index = (self.normal_index + 1) % count

        elif self.hp > 0:
            # 受伤
            self.image = self.hurt_image

        else:
            # 死亡
            if self.destroy_index < len(self.destroy_images):
                self.image = self.destroy_images[self.destroy_index]

                self.destroy_index += 1
            else:
                self.reset_plane()
    
class Enemy(Plane):
    """敌人飞机"""

    def __init__(self, kind, max_speed, *groups):
        """初始化敌人飞机"""
        self.kind = kind
        self.max_speed = max_speed

        if kind == 0:
            # 小敌机
            super(Enemy, self).__init__(
                ['enemy1.png'], 1, 1, 1000, 'enemy1_down.wav', 'enemy1.png',
                ['enemy1_down%d.png' % i for i in range(1,5)],
                *groups
            )
        elif kind == 1:
            # 中敌机
            super(Enemy, self).__init__(
                ['enemy2.png'], 1, 6, 6000, 'enemy2_down.wav', 'enemy2_hit.png',
                ['enemy2_down%d.png' % i for i in range(1,5)],
                *groups
            )
        elif kind == 2:
            # 大敌机
            super(Enemy, self).__init__(
                ['enemy3_n1.png', 'enemy3_n2.png'], 1, 15, 15000, 'enemy3_down.wav', 'enemy3_hit.png',
                ['enemy3_down%d.png' % i for i in range(1,7)],
                *groups
            )

        # 初始化飞机时，要让飞机随机的选择一个位置显示
        self.reset_plane()

    def reset_plane(self):
        """重置敌人飞机"""
        super(Enemy, self).reset_plane()

        # 敌人飞机的数据重置
        x = random.randint(0, SCREEN_RECT.w - self.rect.w)
        y = random.randint(0, SCREEN_RECT.h - self.rect.h) - SCREEN_RECT.h

        self.rect.topleft = (x, y)  

        # 重置飞机的飞行速度
        self.speed = random.randint(1, self.max_speed)

    def update(self, *args):
        """更新飞机的位置信息"""
        super(Enemy, self).update(*args)

        # 根据血量判断是否还要移动
        if self.hp > 0:
            self.rect.y += self.speed

        # 如果移动后已经到了屏幕之外，则需要重置飞机
        if self.rect.y >= SCREEN_RECT.h:
            self.reset_plane()

class Hero(Plane):
    """英雄飞机"""
    def __init__(self, *groups):
        """初始化英雄飞机"""
        self.is_power = False  # 是否无敌
        self.bomb_count = HERO_BOMB_COUNT  # 炸弹数量
        self.bullets_kind = 0  # 子弹类型
        self.bullets_group = pygame.sprite.Group()  # 子弹精灵组

        super(Hero, self).__init__(('me1.png', 'me2.png'),
                            5, 1, 0, 'me_down.wav', 'me1.png',
                            ['me_destroy_%d.png' % x for x in range(1, 5)],
                            *groups)            
        self.rect.midbottom = HERO_DEFAULT_MID_BOTTOM  # 创建好飞机之后要设置飞机位置为屏幕底部中间

        pygame.time.set_timer(HERO_FIRE_EVENT, 200)  # 创建玩家飞机之后每0.2秒激活一次发射子弹事件

    def update(self, *args):
        """
        args的 0 号下标说明了是否要更新下一帧动画，1 号说明玩家飞机水平方向移动基数，2 号说明玩家飞机垂直方向的移动基数
        """
        super(Hero, self).update(*args)

        if len(args) != 3 or self.hp <= 0:
            return

        # 屏幕边缘的位置修正
        self.rect.x += args[1] * self.speed
        self.rect.x = 0 if self.rect.x < 0 else self.rect.x
        if self.rect.right > SCREEN_RECT.right:
            self.rect.right = SCREEN_RECT.right

        self.rect.y += args[2] * self.speed
        self.rect.y = 0 if self.rect.y < 0 else self.rect.y
        if self.rect.bottom > SCREEN_RECT.bottom:
            self.rect.bottom = SCREEN_RECT.bottom

    def blowup(self, enemies_group):
        """炸毁所有敌机,并返回得到的总分值"""
        # 判断是否能够发起引爆
        if self.bomb_count <= 0 or self.hp <= 0:
            return 0

        # 引爆所有敌机，累计得分
        self.bomb_count -= 1
        score = 0
        count = 0

        for enemy in enemies_group.sprites():
            if enemy.rect.bottom > 0:
                score += enemy.value
                enemy.hp = 0
                count += 1

        print('炸毁了 %d 架敌机，获取得分 %d' % (count, score))

        return score

    def reset_plane(self):
        """重置玩家飞机数据"""
        super(Hero, self).reset_plane()

        self.is_power = True
        self.bomb_count = HERO_BOMB_COUNT
        self.bullets_kind = 0

        # 发布事件,让游戏主逻辑更新界面
        pygame.event.post(pygame.event.Event(HERO_DEAD_EVENT))
       
        # 发布定时事件
        pygame.time.set_timer(HERO_POWER_OFF_EVENT, 3000)    

    def fire(self, display_group):
        """英雄飞机发射一轮新的子弹"""
        # 准备子弹要显示到的组
        groups = (display_group, self.bullets_group)

        # 创建新子弹并定位
        for i in range(3):
            bullet1 = Bullet(self.bullets_kind, *groups)
            y = self.rect.y - i*15

            if self.bullets_kind == 0:
                bullet1.rect.midbottom = (self.rect.centerx, y)
            else:
                bullet1.rect.midbottom = (self.rect.centerx - 20 , y)

                bullet2 = Bullet(self.bullets_kind, *groups)
                bullet2.rect.midbottom = (self.rect.centerx + 20, y)

class Bullet(GameSprite):
    """子弹类"""

    def __init__(self, kind, *group):
        """初始化子弹数据"""
        image_name = 'bullet1.png' if kind == 0 else 'bullet2.png'
        super(Bullet, self).__init__(image_name, -12, *group)

        self.damage = 1  # 杀伤力

    def update(self, *args):
        """更新子弹的数据"""
        super(Bullet, self).update(*args)

        # 飞出屏幕之外则需要销毁子弹
        if self.rect.bottom < 0:
            self.kill()

class Supply(GameSprite):
    """道具精灵"""

    def __init__(self, kind, *group):
        """初始化道具属性"""
        image_name = 'bomb_supply.png' if kind == 0 else 'bullet_supply.png'
        super(Supply, self).__init__(image_name, 5, *group)

        self.kind = kind  # 道具类型
        self.wav_name = 'get_bomb.wav' if kind == 0 else 'get_bullet.wav'  # 道具的音效

        self.rect.y = SCREEN_RECT.h  # 道具的初始位置

    def update(self, *args):
        """修改道具位置"""
        if self.rect.y > SCREEN_RECT.h:  # 如果已经移动到屏幕之外则不需要继续移动
            return

        super(Supply, self).update(*args)

    def throw_supply(self):
        """投放道具"""
        self.rect.bottom = 0 # 移动道具到窗口的顶部
        self.rect.x = random.randint(0, SCREEN_RECT.w - self.rect.w)


```



#### game_music.py

```python
"""游戏音乐控制模块"""
import pygame
import os

class MusicPlayer(object):
    """音乐播放器类"""

    res_path = './res/sound/'

    def __init__(self, music_file):
        """初始化音乐播放器"""
        # 加载背景音乐
        pygame.mixer.music.load(self.res_path + music_file)
        pygame.mixer.music.set_volume(0.2)

        # 初始化音效的字典
        self.sound_dict = {}

        files = os.listdir(self.res_path)
        for file in files:
            if file == music_file:  # 背景音乐不需要处理
                continue

            sound = pygame.mixer.Sound(self.res_path + file)
            self.sound_dict[file] = sound

    @staticmethod
    def play_music():
        """播放背景音乐"""
        pygame.mixer.music.play(-1)

    @staticmethod
    def pause_music(is_pause):
        """根据暂停状态决定是否要播放背景音乐"""
        if is_pause:
            pygame.mixer.music.pause()
        else:
            pygame.mixer.music.unpause()

    def play_sound(self, wav_name):
        """根据文件名，播放音效"""
        self.sound_dict[wav_name].play()

```



#### game_hub.py

```python
'''游戏控制面板/提示信息模块'''
import pygame
from game_items import *

'''所有面板精灵的控制类'''
class HUDPanel():
    margin = 10     # 间距
    white = (255, 255, 255)
    gray = (64, 64, 64)
    reward_score = 100000                       # 奖励分值
    level2_score = 10000                        # 级别 2 分值
    level3_score = 50000                        # 级别 3 分值
    record_filename = "record.txt"  # 最好成绩文件名

    def __init__(self, display_group):
        #基本数据
        self.score = 0  #游戏得分
        self.lives_count = 3    # 生命技数
        self.level = 1  # 游戏级别
        self.best_score = 0     #最好成绩

        #图像精灵

        #状态精灵
        self.status_sprite = StatusButton(('pause.png', 'resume.png'), display_group)
        self.status_sprite.rect.topleft = (self.margin,self.margin)

        #炸弹精灵
        self.bomb_sprite = GameSprite('bomb.png', 0, display_group)
        self.bomb_sprite.rect.x = self.margin
        self.bomb_sprite.rect.bottom = SCREEN_RECT.bottom - self.margin 

        #得分标签
        self.score_label = Label('%d'%self.score, 32, self.gray, display_group)
        self.score_label.rect.midleft = (self.status_sprite.rect.right + self.margin,
                                       self.status_sprite.rect.centery)
  
        #炸弹计数标签
        self.bomb_label = Label('X 3', 32, self.gray, display_group)
        self.bomb_label.rect.midleft = (self.bomb_sprite.rect.right + self.margin,
                                       self.bomb_sprite.rect.centery)
  
        #生命计数标签
        self.lives_label = Label('X %d'%self.lives_count, 32, self.gray, display_group)
        self.lives_label.rect.midright = (SCREEN_RECT.right - self.margin,
                                         self.bomb_sprite.rect.centery)
        #生命精灵
        self.live_sprite = GameSprite('life.png', 0, display_group)
        self.live_sprite.rect.right = self.lives_label.rect.x - self.margin
        self.live_sprite.rect.bottom = SCREEN_RECT.bottom - self.margin

        #最好成绩标签
        self.best_label = Label('Best:%d'%self.best_score, 36, self.white)
        self.best_label.rect.center =   SCREEN_RECT.center

        #状态标签
        self.status_label = Label('Game Pause!', 48, self.white)
        self.status_label.rect.midbottom = (self.best_label.rect.centerx,
                                            self.best_label.rect.y - 2*self.margin)

        #提示标签
        self.tip_label = Label('Press spacebar to continue.', 22, self.white)
        self.tip_label.rect.midtop = (self.best_label.rect.centerx,
                                    self.best_label.rect.bottom + 8*self.margin)

        # #剧情精灵
        # self.plot_1 = Label('8岁，看着自己空中盘旋的纸飞机，你心中无比的向往……',10,self.white)
        # self.plot_1.rect.center = SCREEN_RECT.center - 5*self.margin

        # 从文件里加载最好成绩
        self.load_best_score()
        print('初始化控制面板，当前最好得分是:', self.best_score)

    '''修改炸弹数量为X count'''
    def show_bomb(self,count):
        self.bomb_label.set_text('X %d'%count)
        self.bomb_label.rect.midleft = (self.bomb_sprite.rect.right + self.margin,
                                       self.bomb_sprite.rect.centery)

    '''修改最新的生命计数为 x live_count''' 
    def show_lives(self):
        self.lives_label.set_text('X %d' % self.lives_count)

        #修正生命计数精灵的位置
        self.lives_label.rect.midright = (SCREEN_RECT.right - self.margin,
                                         self.bomb_sprite.rect.centery)


        #修正生命精灵的位置
        #我们重算的是文本，而不是精灵
        self.live_sprite.rect.right = self.lives_label.rect.x - self.margin

    def increase_score(self, enemy_score):
        """增加得分，注意同时要处理增加生命、关卡升级、更新最好成绩"""

        # 计算最新得分
        score = self.score + enemy_score

        # 判断是否增加生命
        if score // self.reward_score != self.score // self.reward_score:
            self.lives_count += 1
            self.show_lives()

        self.score = score

        # 更新最好成绩
        self.best_score = score if score > self.best_score else self.best_score

        # 计算最新关卡等级
        if score < self.level2_score:
            level = 1
        elif score < self.level3_score:
            level = 2
        else:
            level = 3

        is_upgrade = level != self.level
        self.level = level

        # 更新得分精灵显示内容
        self.score_label.set_text('%d' % score)
        self.score_label.rect.midleft = (self.status_sprite.rect.right + self.margin,
                                         self.status_sprite.rect.centery)

        # 返回是否升级给游戏主逻辑
        return is_upgrade   

    def save_best_score(self):
        """保存当前最好得分到文件里"""
        file = open(self.record_filename, 'w')
        file.write('%d' % self.best_score)
        file.close()

    def load_best_score(self):
        """从文件里重新加载最好得分"""
        try:
            # 读取文件内容
            file = open(self.record_filename, 'r')
            content = file.read()
            file.close()

            # 转换内容为数字
            self.best_score = int(content)
        except (FileNotFoundError, ValueError):
            print('读取最高得分文件，发生异常')

    def panel_paused(self, is_game_over, display_group):
        """游戏停止，显示提示信息。is_game_over 为 True则说明游戏结束，为 False 则说明是游戏暂停"""
        # 判断是否已经显示了提示信息
        if display_group.has(self.best_label, self.status_label, self.tip_label):
            return

        # 根据游戏状态生成提示文本
        status = 'Game Over!' if is_game_over else 'Game Paused!'
        tip = 'Press spacebar to '
        tip += 'play again.' if is_game_over else 'continue.'

        # 修改标签精灵的文本内容
        self.best_label.set_text('Best:%d' % self.best_score)
        self.status_label.set_text(status)
        self.tip_label.set_text(tip)

        # 修正标签精灵的位置
        self.best_label.rect.center = SCREEN_RECT.center
        self.status_label.rect.midbottom = (self.best_label.rect.centerx,
                                            self.best_label.rect.y - 2*self.margin)
        self.tip_label.rect.midtop = (self.best_label.rect.centerx,
                                      self.best_label.rect.bottom + 8*self.margin)

        # 把标签精灵添加到精灵组
        display_group.add(self.best_label, self.status_label, self.tip_label)

        # 修改状态按钮
        self.status_sprite.switch_status(True)

    def panel_resume(self, display_group):
        """取消停止状态，隐藏提示信息"""
        display_group.remove(self.best_label, self.status_label, self.tip_label)

        self.status_sprite.switch_status(False)

    def reset_panel(self):
        """重置面板数据"""
        # 重置数据
        self.score = 0
        self.lives_count = 3

        # 重置精灵数据
        self.increase_score(0)
        self.show_bomb(3)
        self.show_lives()

```



## 十三、终章



### 谨记

1. 缩进

2. 注意冒号

3. 两项之间默认以空格间隔


4. global
5. 函数内的a和函数外的a不一样
6. end默认换行
7. Lambal 必会和 可以用列表呈现也可以是元组
8. 还是要看：正则





### 填空题

> 15*1



```python
##1.切片与逆序
#写出下列值
ls=[1,2,3,4,5,6,7,8,9,10]
ls[1:8:2]
>>>[2, 4, 6, 8]

#对上述ls切片，从4开始之前的数倒序
>>>ls[3::-1]

#升序排序
>>>ls.sort()

#降序排序
>>>ls.sort(reverse = True)



##2.写出输出的值
s = 'Hello, li lie'
s[-9:-3:2]
>>>'0 i'


#输入8
x=input('输入值')
x
>>> '8'


print(2021,12,29,sep='-')
>>>2021-12-29


print(2*'5')
>>> '55'


a= input('输入值：')
a +=2
print('a={}'.format(a))
>>> 报错


print('2021' + '1')
>>>'20211'


eval('2+3')
>>>5


print(1,2,end='  ')
>>>1 2


s = 'hello,world'
'or' in s
>>> True


a=[1, 3]
b=[5, 7]
a+b
>>>[1, 3, 5, 7]


[sc for sc  in [98,77,51] if sc<52]
>>>[51]


t = ('s', '2')
t[1] = '23'
print(t)
>>>报错


a = (1,2,3)
a*2
>>>(1, 2, 3, 1, 2, 3)


'-'.join(['2021','12','29'])
>>>'2021-12-29'


a=1
print('a=',a)
>>>a= 1


[i for i in range(1,4,2)]
>>>[1, 3]



##3.正则
#匹配 77Hello Python 的 77Hello ,并打印内容和跨度
import re
rst = re.match('77Hello','77Hello Python 的 7Hello')
print(rst.span())
print(rst.group())

#用两种正则,匹配首次遇到的0到9中任意一个数字来匹配
rst = re.match('[0-9]','77Hello Python 的 7Hello')
rst = re.match('\d','77Hello Python 的 7Hello')
print(rst.group())

#同1，用其中一种方法改为匹配首次遇到0到9之间任意多个数字
rst = re.match('\d*','77Hello Python 的 7Hello')
print(rst.group())

#同1，用其中一种方法改为匹配首次遇到0到9至少一个数字
rst = re.match('\d+','77Hello Python 的 7Hello')
print(rst.group())


##4.继承
#建一个和类Person相似的类Stu，继承父类Person中类的变量name和age，
#>和一个新的实例变量grade，最后给子类传参，用父对象的speak方法打印 
#>姓名张三，年龄18，班级2

class Person:
    def __init__(self,name,age):
        self.name=name
        self.age=age
    def speak(self):
        print('姓名{}，年龄{},班级{}'.format(self.name,self.age,self.grade))
#>>>
class Stu(Person):
    def __init__(self,name,age,grade):
        Person.__init__(self,name,age)
        self.grade = grade
p = Stu('张三',18,2)
p.speak()



#>同上,重写speak方法为speak并调用,同上输出和输出hprint('hi,I am {},my age is {},my grade is {}'.format(self.name,self.age,self.grade))

class Person:
    def __init__(self,name,age):
        self.name=name
        self.age=age
    def speak(self):
        print('姓名{}，年龄{},班级{}'.format(self.name,self.age,self.grade))
#>>>
class Stu(Person):
    def __init__(self,name,age,grade):
        Person.__init__(self,name,age)
        self.grade = grade
    def speak(self):
        super().speak()
        print('hi,I am {},my age is {},my grade is {}'.format(self.name,self.age,self.grade))
p = Stu('张三',18,2)
p.speak()



##5.其他
#[1,2,3]转成元组
tuple([1, 2, 3])

#创建元组tup值为5,6,7,8,空元组tup1,只有一个元素5的元组tup2
tup = (5,6,7,8)
tup1=()
tup2=(5,)

#对字符串 'hello world how are you' 以w为分割线，分割字符串
'hello world how are you'.split('w')

#同上,再对每个字符后以…分割
'…'.join('hello world how are you').split('w')

```

















### 选择题

> 15*2



1. 标识符的命名规则：第一个字符不能是数字

2. 幂次方：2**3或pow(2,3)

3. ```python
   #调用datetime模块，查看当天日期
   #>>>import datetime
   print(datetime.date.today())
   ```

   











### 判断

> 10*2

1. 类的继承可以继承多个父类

2. 两个列表值可以直接加

3. 单双引号的区别（有双无双，有单无单）

4. 访问类的变量 类名访问更好，也可以通过对象名

5. 实例变量只能在类内使用，在类外只能通过对象名.实例变量名，而不能通过类名.实例变量名来访问

6. 不能给元组赋值，不能增删改

7. 字符串的起始边界不能这样写

   ```python
   'It's a book'
   ```


8. 少了一个：

   ```python
   if (x < y) print(x)
   ```

9. 这句话的语法结构是否正确：正确

   ```python
   while True: pass
   ```

   



### 程序分析

> 5*3



#### 1.分支结构

```python
a,b,c = 1,2,3
if a<b:
    if b>0:
        if c>0:
            c +=1
        c +=2
print('c = %d' % c)      
>>> c = 6


a = 1
for i in range(10):
    if i == 7:
        continue
    a +=3
else:
    a +=4
print(a)
>>>32


for n in range(1, 50):
    if n % 3 != 0 and n % 5 ==0:
        print(n,end=' ')
>>>5 10 20 25 35 40 45 50

```





#### 2.函数调用

```python
a = 5
def change():
    global a
    a = 8
    print('a=',a)
change()
print('a=',a)
>>> a= 8
	a= 8
    
    
    
def f(n):
    n = n * 2
    print('n=',n)
n = 4
f(n)
print('n=', n )
>>>n= 8
   n= 4
```







#### 3.星阵图

```python
# 3.4.1break
#打印5*5的星星，第二行最后两个空出来

for i in range(5):
    for j in range(5):
        if i == 1 and j ==3:
            break
        print('*',end=' ')
    print()
    
    
# 3.4.3continue
#打印5*5的星星，第4行第三个空出来

for i in range(5):
    for j in range(5):
        if i == 3 and j == 2:
            print(end = '  ')
            continue
        print('*',end=' ')
    print()
    
```







#### 4.Lamdba

```python
#用map将列表 [1,2,3,4,5] 的每一个元素乘求平方，并以列表输出
rst = map(lambda x:x**2, [1, 2, 3, 4, 5])
print(list(rst))
>>>[1, 4, 9, 16, 25]


#用filter筛选上述列表中的奇数以及大于2的数
rst = filter(lambda x:x>2 and x%2 == 1, [1, 2, 3, 4, 5])
print(list(rst))
>>>[3, 5]
```







#### 5.正则

```python
import re
ls = [87,59,97,73,55,66,100]
for i in ls:
    rst = re.match('[6-9][0-9]',str(i))
    if rst:
        print(i,end=' ')
>>>87 97 73 66


r=re.findall('\d+', 'python = 99, c++ = 78, jajva =55')
print(r)
>>>['99', '78', '55']

```





### 大题

> 5*6

#### 1.鸡兔同笼

```python
#编写函数，实现鸡兔同笼子：35个头，94只脚，问多少只鸡和兔

m=35
n=94
for i in range(1,m+1):
    for j in range(1,m+1):
        if i + j == m and i*2 + j*4 == n:
            print('有{}只鸡，{}只兔'.format(i, j))

```



#### 2.零件

```python
#有一堆100多个的零件，若三个三个数，剩二个；若五个五个数，剩三个；若七个七个数，剩五个。请你编一个程序计算出这堆零件至少是多少个？

n=100
while True:
    if n%3 == 2 and n%5 == 3 and n%7 == 5:
        print(n)
        break
    else:
        n += 1
```



#### 2.水仙花数

```python
#编写函数，实现打印100-1000以内的所有水仙花数，一个三位数的各位数字的立方和等于其本身，例如153

for i in range(100,1000):
    g = i%10
    s = i//10%10
    b = i//100
    if pow(g, 3)+pow(s, 3)+pow(b, 3) == i:
        print(i)
```





#### 3.素数

```python
#求出100以内的素数，每5个换行

count = 0
for i in range(2, 101):
    flag = 1
    for j in range(2, i):
        if i%j == 0:
            flag = 0
            break      
    if flag == 1:
        print('%-3d'%i,end = ' ')
        count += 1
        if count%5 == 0:
            print()
```







#### 4.学生类

```python
#学生类 每个学生三门成绩、最高、最低、平均分
class Stu:
    def __init__(self,a,b,c):
        self.a = a
        self.b = b
        self.c = c
    def max_graden(self):
        return max(self.a, self.b, self.c)
    def min_graden(self):
        return min(self.a, self.b, self.c)  
    def avg_graden(self):
        return (self.a+self.b+ self.c)/3
p = Stu(123,321,32)
print('最高分，最低分，分别是',p.max_graden(), p.min_graden(), p.avg_graden())
```







#### 5.异常

5.1#=>求三角形面积，当两边之和不大于第三边时报错{},{},{}不能构成三角形

```python
#=>求三角形面积，当两边之和不大于第三边时报错{},{},{}不能构成三角形
#海伦公式求三角形面积；(t=a+b+c)/2 s=sqrt(t*(t-a)*(t-b)*(t-c))

import math
class TriangleException(Exception):
    def __init__(self,a,b,c):
        self.a=a
        self.b=b
        self.c=c
    def __str__(self):
        return '{},{},{}不能构成三角形'.format(self.a,self.b,self.c)
class Triangle:
    def __init__(self,a,b,c):
        if a+b<=c or a+c<=b or b+c<=a:
            raise TriangleException(a,b,c)
        self.a=a
        self.b=b
        self.c=c
    def getArea(self):
        t=(self.a+self.b+self.c)/2
        return math.sqrt(t*(t-self.a)*(t-self.b)*(t-self.c))
try:
    a=eval(input('输入边长1:'))
    b=eval(input('输入边长2:'))
    c=eval(input('输入边长3:'))
    obj=Triangle(a,b,c)
    print('三角形的面积：{:0.3f}'.format(obj.getArea()))
except TriangleException as e:
    print(e)



```



5.2圆的半径为负值和0时报错:异常：半径{}为负值,并值输出面积

```python
#=>圆的半径为负值和0时报错:异常：半径{}为负值,并值输出面积

import math
class CricleException(Exception):
    def __init__(self,r):
        self.r=r
    def __str__(self):
        return '异常：半径{}为负值'.format(self.r)
class Cricle:
    def __init__(self,r):
        if r<0:
            raise CricleException(r)
        self.r=r
    def getArea(self):
        return math.pi*self.r**2
try:
    r=eval(input('输入半径:'))
    obj=Cricle(r)
    print('圆的面积：{:0.3f}'.format(obj.getArea()))
except CricleException as e:
    print(e)
```







#### 6.不一定

##### 1.一元二次方程

```python
#为二次方程式ax2+bx+c=0设计一个名Equation的类，这个类包括：1.代表三个系数的成员变量a、b、c。2.一个参数为a、b、c的构造方法。
#>3.一个名为getDiscriminant()的方法返回判别式的值。 4.一个名为getRoot1()和getRoot2()的方法返回等式的两个根：如果判别式为负，这些方法返回0。

from math import *
class Equation:
    def __init__(self,a, b, c):
        self.a = a
        self.b = b
        self.c = c
        self.delta=sqrt(self.b*self.b-4*self.a*self.c)
        
    def getDiscriminant(self):
        return self.delta
            
    def getRoot1(self):
        x1=(-self.b+self.delta)/2/self.a
        return x1
            
    def getRoot2(self):
        x2=(-self.b-self.delta)/(2*self.a)
        return x2  

a=float( input("请输入 a:") )
b=float( input("请输入 b:") )
c=float( input("请输入 c:") )
p = Equation(a,b,c)

print("判别式和两个实根的值分别为:",p.getDiscriminant(),p.getRoot1(),p.getRoot2())
```



##### 3.斐波那契

```python
#编写程序，输出斐波那契数列的前20项，1，1，2，3，5，8，13，……
def fun(ls,x):
    for i in range(2,x+1):
        ls.append(ls[i-1]+ls[i-2])
    print(ls)
    
ls=[1,1]
fun(ls,20)
```



##### 4.鸡兔同笼第二种写法

```python
#编写函数，实现鸡兔同笼子：35个头，94只脚，问多少只鸡和兔
def fun():
    for x in range(1,36):
        if x*2+(35-x)*4==94:
            print('有{}只鸡，{}只兔'.format(x,35-x))
```







# 材料2

> Python入门到精通
>
> 千锋教育

## 进程与线程





































