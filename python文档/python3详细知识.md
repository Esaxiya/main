
```
"一等对象":
满足条件：1.在运行时创建 2.能赋值给变量或数据结构中的元素 3.能作为参数传递给函数 4.能作为函数的返回结果   
[ 整数、字符串、字典、"所有函数" ]等都是一等对象
```
```
"什么是函数"
调用：直接使用、不需要类或对象进行调用
定义：定义在模块中、类体外
作用：数据处理
```
```
"什么是方法"
调用：不能直接使用、需要类或对象进行调用
定义：定义在类体中
作用：状态处理、状态(对象的属性、类的属性)
```
```
"实例方法"
实例方法、接受一个self参数、该参数指向类的实例.
实例方法、通过self参数可以自由地访问同一个对象的属性和其他方法.
实例方法、不仅可以修改对象的状态、还可以修改类的状态、通过self.__class__属性访问类本身.
实例方法、需要一个类的实例对象、并通过self访问实例.
```
```
"类的方法"
类的方法、用一个@classmethod装饰器标记.
类的方法、接受一个cls参数、该参数指向类本身、而不是实例.
类的方法、只能访问cls参数、因此无法修改实例对象.
类的方法、仍然可以修改适用于此类的所有实例的类状态.
类的方法、不需要类实例、无法访问实例、但他们可以通过cls访问类本身. 常用于定义备选构造方法
```
```
"静态方法"
静态方法、用@staticmethod装饰器标记.
静态方法、既不需要self也不需要cls参数.
静态方法、既不能修改对象状态也不能修改类状态.
静态方法、无法访问cls或self、它们像常规函数一样工作，但属于类的命名空间.
静态方法和类的方法通信并(在某种程度上)强制开发人员 关于类设计的意图、这可以带来维护益处.
将方法标记为静态方法不仅仅是一个方法不会修改类或实例状态的提示 - 这个限制也是由Python运行时强制执行的
```
```
"高阶函数"
参数包含函数、或返回值是函数 的函数就是高阶函数。
如内置高阶函数：map、filter、reduce
```
```
"匿名函数"
匿名函数就是没有名字的函数、lambda关键字用来创建匿名函数、
lambda函数只能是纯表达式、不能赋值、不能使用while、try等语句、在参数列表中最适合使用匿名函数
```
```
"钩子函数"
钩子函数也叫回调函数，是通过函数指针来实现的. 函数的指针可以指向不同的函数, 从而完成不同的功能.  函数指针往往被声明为全局变量. 实例方法见C语言代码😯
```
```
"序列类型"
序列类型 Sequence Types
有三种基本序列类型：list、tuple、range
专门用于处理二进制数据"binary data"和文本字符串"text strings"的附加序列类型
```
```
"序列操作"
大多数序列类型都支持下表中的操作，包括可变和不可变的序列类型。相同类型的序列也支持比较.
[in, not in,+, *, 切片, len(), min(), max(), index(), count()]
collections.abc.Sequence 使其更容易正确地执行自定义序列类型这些操作
序列可以迭代的原因是：iter()函数、解释器需要迭代对象x时、会自动调用iter(x)
"对序列使用+和*"
+ * 都不会修改原有对象、而是构建一个全新的序列
对序列增量赋值、+=、*=的表现取决于他们的第一个操作对象、+=背后的特殊方法__iadd__()就地加法、
a+=b 等价于 a=a+b、*=、-=、/= 等都和+=原理相同、只是对应的特殊方法不同
增量运算只能用于可变序列、增量运算后可变序列的ID没有变、新元素追加到序列上
对不可变序列进行重复拼接(*n)效率很低、每次都创建新对象、在将原对象复制到新对象里
```
```
"不可变序列类型"  
Immutable Sequence Types
不可变序列类型通常实现的唯一操作是对hash() 内置的支持.
不可变序列可以作为字典的键key;可以存储在set和frozenset实例中
tuple 就是不可变序列
```
```
"可变序列类型"  
Mutable Sequence Types
可变序列、不可以哈希、不可以作为字典的键key
"collections.abc.MutableSequence ABC" 更容易在自定义序列类型上正确实现这些操作.
```
```
"可散列数据类型"
可散列是指这个对象的生命周期中、它的散列值不变、而这个对象需要实现__hash__()方法
可散列的对象还有__eq__()方法、这样才可以和其键做比较、对象相等散列值必相同
原子不可变数据类型(str、bytes、数值类型)都是可散列类型、frozenset也是可散列类型
抽象基类的主要作用是和instanse一起判断某个数据是不是广义上的映射类型
```
```
"容器序列"
容器序列存放的是它们所包含的任意类型的对象的引用;
容器序列(存放引用)：可以存放不同类型的数据、如: "list"、"tuple"、"conllections.duque"
容器序列存放的是它们所包含的任意类型的对象的引用; 扁平序列存放的是数据本身的值、而不是引用
```
```
"扁平序列"
扁平序列存放的是数据本身的值、而不是引用、扁平序列其实就是一段连续的内存空间
扁平序列体积更小、速度更快、用起来更方便、但只能保存一些原子性的数据、数字、字符、字节
扁平序列(存放数据)：只能存放一种类型、如:"str"、"bytearray"、"memoryview"和"array.array" 、
```
```
"函数式编程"
函数式编程就是将问题分解为一组函数。
理想情况下、函数只接受输入并产生输出、并不影响内部状态
一个函数应该仅具有一个功能、复杂函数拆分为多个简单函数
每个函数都接收输入产生输出、每个函数的输出必须仅取决于其输入
完全没有副作用的函数称为纯函数
函数式编程可以被认为是面向对象编程的反面
函数式编程希望尽可能避免状态变化，并使用函数之间的数据流
对象是包含一些内部状态的小胶囊以及一组方法调用, 可以让您修改此状态, 程序包括进行正确的状态更改
```
```
"可变类型"
可变类型:   "内存中的数据可以被修改：列表、字典"
"不可变类型"
不可变类型: "内存中的数据不允许被修改：数字、字符串、元组"

```
```
"PEP8"
包和模块名称：模块应该有简短的全小写名称. 如果提高可读性, 可以在模块名称中使用下划线. Python包也应该有简短的全小写名称, 但不鼓励使用下划线.
类的名称：类名通常应使用CapWords大小约定.
类型变量名：类型变量的名称通常应使用CapWords, 而不是短名称：T, AnyStr, Num.
全局变量名称：与函数和变量名称相同规则、名称应为小写, 并根据需要用下划线分隔
函数和变量名称：函数名称应为小写, 并根据需要用下划线分隔, 以提高可读性. 变量名称遵循与函数名称相同的约定.
方法和方法参数：总是使用self作为实例方法的第一个参数. 总是使用cls作为类方法的第一个参数. 如果函数参数的名称与保留关键字冲突, 通常最好附加单个尾随下划线而不是使用缩写或拼写损坏
方法名称和实例变量：小写, 必要时用下划线分隔, 以提高可读性. 仅对非公共方法和实例变量使用一个前导下划线.
常量：常量通常在模块级别定义, 并以全部大写字母书写, 下划线分隔单词.
```
```
"python"
python 既是一门面向对象的高级编程语言,同时也是支持函数式编程的脚本语言.
python 简单、免费、开源、可移植、解释性语言、自动内存管理.
python 可扩展性强、和混合C语言、Java语言等编写. 还有丰富的第三方库.
python 中的函数都是一等对象: 1.在运行时创建 2.能赋值给变量 3.能作为参数传递给函数 4.能作为函数的返回结果.
```
```
"切片"
`list、tuple、str、`都支持切片操作、通过索引来进行切片[:]、[:-1]、[1:3]、[3:5]、[5:]、
为什么切片和区间会忽略最后一个元素？
"通常都以0作为起始下标"、 "在切片和区间不含最后一个元素"
(1)当只有一个位置信息时、我们可以快速看出切片和区间里有几个元素
(2)当起止位置信息都可见时、可以快速计数出切片和区间的长度
(3)可以利用下标将序列分割成不重叠的两部分
(4)多维切片和省略表示法( ... )
```
```
"函数属性"
__annoations__           dict      参数和返回值的注解
__call__       method-wrapper      实现()运算符、即可调用对象协议
__closure__             tuple      函数闭包、即自由变量的绑定(None)
__code__                 code      编译成字节码的函数元数据和函数定义体
__defaults__            tuple      全部形参的默认值
__get__        method-wrapper      实现只读扫描符协议
__globals__              dict      函数所在模块中的全局变量
__kwdefaults__           dict      仅限关键字形参参数的默认值
__name__                  str      函数的名称
__qualname__              str      函数的限定名称
```

```
"位置参数、关键字参数"
关键字参数不一定要又默认值、只要是放在*参数后面的参数都是关键字参数、def func(a, *, b): 参数b就是一个关键字参数、强制必须传入实参、
函数对象有个__defaults__属性、它的值是一个元组、里面保存着定位参数和关键字参数的默认值
仅限关键字参数的默认追在__kwdefaults__属性中、参数的名称在__code__属性中、它的值是一个code对象的引用、自身也有很多属性"
```
```
"装饰器"
装饰器可以把被装饰的函数替换成其他函数、装饰器是加载模块时立即执行、
装饰器在源代码中标记函数已增强函数的行为、装饰器本质是一个高阶函数、
装饰器只是语法糖、装饰器可以像常规函数那样调用、其参数是另一函数、
装饰器在被装饰函数定义之后立即运行、通常在导入时、
被装饰的函数只是在明确调用时运行、装饰器可以叠放、装饰器也可以带有参数
装饰器作用: "引入日志、函数执行时间的统计、执行函数的前预处理、执行函数后的清理功能、权限校验场景、缓存等"
```
```
"闭包"
闭包、指的是延伸了作用域的函数、其中包含函数定义体中引用、但是不在定义体中定义的非全局变量、
闭包的关键在于能访问定义体之外的非全局变量、通常闭包表现为函数内部定义的函数、
闭包是回调异步编程和函数式编程风格的基础、使用内部函数的代码几乎都要靠闭包才能正确运作、
一个函数的参数、内部定义的局部变量、内部定义的函数、和组成了闭包、
闭包是一种函数、会保留定义函数时存在的自由变量的绑定、
注意：只有嵌套在其他函数中的函数才可能需要处理不在全局作用域中的外部变量
```

```
"递归"
递归是算法中核心的概念有三个特点,
1.调用自身 2.具有结束条件 3.代码规模逐渐减少
```
```
"global"
函数体中定义全局变量、使用global先声明变量、然后再给变量赋值使用
```
```
"nonlocal"
nonlocal 的作用是把变量标记为自由变量、如果给自由变量赋了新值、闭包中保存的绑定的新值
```
```
"变量"
变量就是对象的一个标签、先有对象、才将标签添加到对象上、而不是将对象装入变量
 先创建了对象、然后将对象赋值给变量、此时变量才被创建、变量必须赋值才有效、变量仅仅是对象的一个标签
```
```
"对象"
对象包含的三个基本要素 分别是：id(身份标识)、type(数据类型)、value(值)
对象的一旦创建、它的标识绝不会改变、可以将标识理解为内存地址、id()返回内存地址
对象是包含一些内部状态的小胶囊以及一组方法调用, 可以让您修改此状态, 程序包括进行正确的状态更改
```
```
"参数的默认值"
不要使用可变类型作为参数的默认值、函数的参数的默认值是在函数创建时赋值的而不是函数调用时,
所以需要特别注意、对象不会自动销毁、无法得到对象时、可能会被当作垃圾回收
```
```
"帮助"
help()、dir()
help('keywords')、help('modules')、help("modules json")、help("topics"))
help("os.path")、help("list")、help("str.find")、help("open")、help("builtins")
```
```
"形参、实参"
形参：定义函数时使用的变量
实参：调用函数时传递的对象
```
```
"函数内省"    
内省，有时也叫类型内省，是在运行时进行的一种对象检测机制。
我们可以通过内省来获取一个对象的所有信息，比如这个对象的类型，其中包含哪些属性等等
省：检查某些事物以确定它是什么、内省：自我检查、已确定自己是什么、有什么、函数对象又很多属性、__doc__、__call__、__class__、__init__、__new__、__str__等、函数使用__doc__属性存储赋予它的用户的属性
```
```
"==和is的区别"
 == 是比较运算符     == 比较的是对象的value       
     is 是身份运算符     is 比较的是对象的id
== 比较的是两个对象的值(对象中保存的数据); is 比较的是对象的标识、即对象的内存地址信息、
继承字object的__eq__()方法比较两个对象的ID、结果与is一样、而 a == b 是语法糖、等同于 a.__eq__(b)、
但是大多数内置类型使用更有意义的方式覆盖了__eq__()方法、会考虑对象属性的值
"变量和单例值比较应该使用is"、is 运算比==速度快、因为它不能重载、is运算符不调用特殊方法、直接比较两个整数ID
```
```
"函数返回值类型"
无返回值时   None
一个返回值   值的类型
多个返回值   元组类型
```
```
"上下文管理器"
with 语句会设置一个临时的上下文、交给上下文管理对象控制、并负责清理上下文、
with 还有很多用途、除了关闭文件之外、with 语句存在的目的简化 try / finally 模式、
"上下文管理对象存在的目的是管理 with 语句"、"迭代器存在的目的是为了管理 for 循环语句"、
上下文管理协议包含__enter__和__exit__两个方法、
with 语句开始运行时、会在上下文管理对象上调用__enter__方法、
with 语句开始结束时、会在上下文管理对象上调用__exit__方法、扮演finally子句
```
```
"可调用对象"
1.用户定义的函数、2.内置函数、3.内置方法、4.方法、5.类、6.类的实例、7.生成器函数、
通过内置callable()函数、判断对象是否可以调用
```
```
"del 语句"
del 语句删除的是名称、而不是对象、del 语句可能会导致对象被当作垃圾回收、
Cpython中、垃圾回收使用的主要算法是引用计数、正因为有引用、对象才会在内存中存在、当对象的引用归零、垃圾回收程序会销毁对象
```
```
"__slots__"
__slots__ 类的属性、目的节省空间、
通常各个实例中名为__dict__的字典里存储实例属性、为了使用底层的三列表提升访问速度、
字典会消耗大量内存、通过使用__slots__类属性、能够节省大量内存、让解释器在元组中存储实例属性、而不是字典、
python只会使用各个类中自己定义的__slots__属性、继承的没有效果、
定义__slots__的方式、名称为__slots__、值为属性字符串组成的元组、
__slots__ = ('__x', '__y')、__slots__属性的目的就是告诉解释器、这个类中的所有实例属性都在这了、缺点：不能动态添加属性了"
```
```
"__add__"
如果a有__add__方法、则进行a.__add__(b)运算、
否则检查b有没有__radd__方法、如果有、则调用b.__radd__(a)，否则返回Notimplemented
```
```
" __eq__ "
   __eq__ 定义了类的等号(==)行为、其他魔术方法原理类似
def __eq__(self, obj):
    return self.name == obj.name
```
```
"__xxx__"
__xxx__为系统定义的名称、普通变量不可以使用此方式命名
可变参数 *args 类型为 tuple 类型、关键字参数 **kwargs 为 dict 类型.
```
```
"局部变量、全局变量"
"局部变量" 是在 "函数内部" 定义的变量、只能在函数内部使用；
 函数执行结束后, 函数内部的局部变量, 会被系统回收；
 不同的函数, 可以定义相同的名字的局部变量, 但是 彼此之间 不会产生影响；
 局部变量一般临时 保存 函数内部需要使用的数据
"全局变量" 是在 "函数外部" 定义的变量、所有函数内部都可以使用这个变量
```

```
"*args 与 **kwargs"
*args        数据类型元组     位置参数
**kwargs     数据类型字典     关键字参数  
*和**        表示可变参数      可以传递任意数量的参数
*和**        也可以在函数调用的时候使用, 称之为解包裹(unpacking)
*args   数据类型元组 位置参数
**kwargs 数据类型字典 关键字参数
```
```
"可迭代对象"
for语句在容器对象上调用iter()内置函数,可以获取迭代器对象、
如果对象实现了能返回迭代器的__iter__方法, 那么对象就是可迭代的、
python 从可迭代的对象中获取迭代器
序列都可以迭代、实现了__getitem__方法、参数索引从0开始的对象、也可以进行迭代
<可迭代对象一定不能是自身的迭代器>、也就是说、可迭代的对象必须实现__iter__方法、但不能实现__next__方法
```
```
"运算符"
1.算术运算符 2.比较运算符 3.赋值运算符 4.逻辑运算符 5.位运算符  6.成员运算符 7.身份运算符
```
```
"迭代器"
迭代器存在的目的是为了管理 for 循环语句、迭代器是表示数据流的带有位置状态的对象;
该对象调用next()函数返回容器中的下一个值、此对象一次返回一个元素的数、任何一个实现了_iter_方法和_next_方法的类对象，就是迭代器.
如果流中没有更多元素，则 __next__() 必须引发 StopIteration 异常.
内置iter()函数接受一个任意对象，并尝试返回一个迭代器，该迭代器将返回对象的内容或元素，如果该对象不支持迭代，则会引发TypeError，
迭代器、扫描内存中放不下的数据集时、产生了一种惰性获取数据的方式、迭代器模式、迭代器模式：一次获取一个数据项
标准的迭代器接口有两个方法：__next__和__iter__、__next__ 返回一个可用的元素、如果没有元素了、会抛出Stopiteration异常、
__iter__() 返回 self，以便在应该使用对象的地方使用迭代器、如 for 循环
```
```
"生成器"
生成器是只能遍历一次的、生成器是一类特殊的迭代器.
生成器函数: 使用 def 定义函数, 使用yield语句返回结果而不是return语句.
yield语句一次返回一个结果, 在每个结果中间, 挂起函数的状态, 以便下次从它离开的地方继续执行.
生成器是可以暂停和恢复的函数，返回可以迭代的对象。与列表不同，它们是懒惰的，因此只能在被询问时生成一个项目(items)。
因此，在处理大型数据集时，它们的内存效率更高.
请记住，当数据大小大于可用内存时，生成器表达式会大大加快。  
生成器非常适合读取大量大型文件，因为无论输入流的大小如何，它们一次只能生成一个数据块。
它们还可以通过将迭代过程分离为更小的组件来实现更清晰的代码.
生成器允许我们在需要时询问值，使我们的应用程序更高效，非常适合无限数据流。
它们还可用于从循环中重构处理，从而产生更清晰，分离的代码.
```
```
"生成器函数"
只要函数定义体中有yield关键字、该函数就是生成器函数、调用生成器函数、会返回一个生成器对象、
也就是说生成器函数就是一个工厂函数、生成器工厂函数、生成器函数都有个 yield 关键字、
生成器函数的定义体中通常都有循环、但不是必须条件、生成器函数返回一个生成器对象、
生成器就是迭代器、会生成传给yield关键字的表达式的值、生成器函数执行完毕会抛出一个StopIteration异常
```
```
"迭代器于生成器的区别"
迭代器用于从集合中取出元素、生成器用于"凭空"生成元素、
通常情况下可以视为一个概念、所有生成器都是迭代器、因为生成器完全实现了迭代器接口
```
```
"面向对象"
封装、继承、多态、封装了属性和方法的代码块。
```
```
"封装"
封装就是将相关细节隐藏、仅对外提供访问接口.
相关细节包括、属性、方法、实现方式、逻辑判断等。
类本身就是一个封装, 封装了属性和方法.
方法也是封装, 对一些业务逻辑的封装.
私有也是封装, 将一些方法和属性私有化, 对外提供可访问的接口.
```
```
"继承"
将共性的内容放在父类中, 子类只需要关注自己特有的内容, 共性的继承过来就行了.简化开发符合逻辑习惯, 利于扩展
```
```
"多态"
一个对象在不同的情况下显示不同的形态。
在python中因为是弱类型语言，对类型没有限定，所有python中不完全支持多态，但是多态的思想，python也是能体现的
```
```
"字典"
字典 class dict(object):
方法: ['clear', 'copy', 'fromkeys', 'get', 'pop', 'popitem', 'keys', 'values', 'items', 'setdefault', 'update', ]
字典是映射类型、是关联数组、是`键集合`到`值集合`的映射、字典表现为键值对、
value可以是任意类型对象、key必须是不可变类型对象、key唯一且不可变、元组可以充当键。
字典被广泛使用、模块的命名空间、实例的属性、函数的关键字、都使用到字典 、
内置函数都在`__buil__builtins__.__dict__`模块中、字典被高度优化、
散列表则是字典类型性能出众的根本原因、集合的实现也依赖散列表。
```
```
"元组"
class tuple(object):
方法:`count`、`index`
元组是不可变序列、存放的是数据的引用、可以存放任何类型的数据、通常用于存储异构元素(不同数据类型的元素)
元组不仅仅是不可变的列表、还包含len属性和元素位置
元组是对数据的记录、元组中的每个元素都存放着记录中一个字段的数据、外加字段位置、正是这个位置信息给数据赋予类意义。
"元组的相对不可变性"
元组和大多数python容器(列表、字典、集、等)一样、保存的都是对象的引用、
如果引用的元素是可变的、即使元组本身不可变、元素依然可变
元组的不可变性、是指元组数据结构的物理内容不可变(即引用不可变)、与引用的对象无关、
元组的值会随着引用的可变对象变化而变化、元组中不可变的是元素的引用
```
```
"列表"
class list(object):
列表是可变序列、存放的是数据的引用、可以存储任何类型的数据、通常用于存储同类型的数据、列表使用 [] 表示
方法：['append', 'clear', 'copy', 'count', 'extend','index', 'insert', 'pop', 'remove', 'reverse', 'sort']

```
```
"集合"
Set Types — set, frozenset
set对象是不同的可哈希对象的无序集合.
集合不支持索引、切片或其他类似序列的行为.
目前有两种内置集类型、set和 frozenset
由于它是可变的、因此它没有哈希值、不能用作字典键或另一组的元素.
该frozenset类型是不可变的和可散列的 - 其内容在创建后不能更改.
set常见用途包括成员资格测试、从序列中删除重复项、以及计算数学运算、如交集、并集、差异和对称差异.
```
```
class set(object):
['add','clear','copy','difference','difference_update',
'discard','update','intersection','intersection_update',
'isdisjoint','issubset','issuperset','pop','remove',
'symmetric_difference','symmetric_difference_update','union',]
```
```
class frozenset(object):
['copy','difference','intersection','union'
'isdisjoint','issubset','issuperset','symmetric_difference']
```

```
"数组"
array.array支持所有可变序列的操作、包括pop、insert、extend、
数组还提供从文件读取、存入文件的更快方法、.frombytes、.tofile、
数组背后存的不是float对象、而是数字的字节表示
```
```
"内存视图"
memoryview是一个内置类、能够让用户在不复制内容的情况下操作同一个数组的不同切片
```
```
"列表推导式"
List Comprehensions
允许您将该代码的三个主要方面表达为一行
•从中检索值的序列 •用于确定是否应包含值的表达式 •用于为新列表提供值的表达式
列表推导式是构建列表的快捷方式
filter和map合起来能做的事情、列表推导式也可以做、
列表推导式的唯一作用就是生成列表    [ i for i in range(10) ]
生成器表达式遵守迭代协议、可以逐个产生元素、而不是先建立一个列表
```
```
"生成器表达式"
generator expression
生成器表达式则可以用来创建任何类型的序列
python 会忽略[]、{}、()、中的换行、因此可以有多行列表、列表推导式、生成器表达式等
如果生成器表达式是一个函数调用过程中的"唯一参数",就不需要将其用括号围起来
生成器表达式是逐个产生元素
```
```
"字典推导"
还有集合推导式(后面出现)
字典推导可以从任何以键值作为元素的可迭代对象中构建出字典
字典推导式可以把一个装满元组的列表变为两个不同的字典
如果要生成其他类型的序列、就需要生成器表达式
```
```
"模块"
  模块对象具有一个秘密的只读属性[`__dict__`]
```

```
标准库中的装饰器
@property、@classmethod、@staticmethod
@functools.wraps 协助构建行为良好的装饰器
@functools.lru_cache() 实现了备忘的功能、把耗时的函数结果保存起来、避免传入相同的参数时重复计算
@functools.singledispatch 可以把整体方案拆分成多个模块、装饰的函数会变成泛函数、根据参数类型、以不同的方式执行相同操作的一组函数
```

```
内置iter函数作用?
  "检查对象是否实现了__iter__方法、如果实现了就调用获取一个迭代器、如果没有实现__iter__方法、但是实现了__getitem__方法、python会自己创建一个迭代器、如果还是失败、会抛出异常"
```
```
if __name__ == '__main__'是什么？
  "模块是对象、并且所有的模块都有一个内置属性 __name__"
  一个模块的 __name__ 的值取决于如何使用模块
  如果模块被导入: '模块__name__ 属性 的值通常为模块文件名'
  如果直接运行模块: '模块__name__属性 的值将是一个特别缺省 __main__'
```
```
"Mapping Types":    dict
"Set Types":        set、frozenset
"Sequence Types":   range、tuple、list
```
```
tuple()
    1.创建空元组 2.创建元组 3.将列表转换为元组 4.将range转换为元组
list()
    1.创建空列表 2.创建列表 3.将元组转换为列表 4.将range转换为列表
dict()
    1.创建空字典 2.创建字典
```
```
#字符串的相关内容
name='xin yue'; age = '15';  grade = '0525'
student0 =f"姓名: {name},年龄: {age},班级: {grade}"  # f-string来组合字符串
student2 = ("姓名: " 'xin yue' ",年龄: " '15' ",班级: " '0525')  # 元组方式()组合字符串
student3 = "姓名: "+"xin yue"+",年龄: "+"15"+",班级: "+"0525"  # 使用+方式
student4 = "".join(['姓名: ', 'xin yue', ',年龄: ', '15', ',班级: ', '0525'])   #  join()拼接组合字符串
student5 = "姓名: %s,年龄: %d,班级: %s" %('xin yue',15,'0525')  # 使用C语言格式%
student6 = "姓名: {},年龄: {},班级: {}".format('xin yue',15,'0525')
student7 = "姓名: {0},年龄: {1},班级: {2}".format('xin yue', 15, '0525')
student8 = "姓名: {name},年龄: {age},班级: {grade}".format(name='xin yue', age=15, grade='0525')
```

--------------------------------------------------------------------------------------------
```
"functools"
可调用对象的高阶函数和操作
高阶函数采用一个或更多个函数作为参数，并返回一个新的函数。

```
```
"operator"
标准运算符作为函数
包含一组与Python运算符相对应的函数。
这些函数通常在函数式代码中很有用，因为它们可以避免编写执行单个操作的简单函数。
```
```
"conllections"
泛映射类型
conllections.abc模块中有MultableMapping和Mapping两个抽象基类
MultableMapping---->Mapping--->Container
MultableMapping: __setitem__、__delitem__、clear、pop、popitem、setdefault、update
Mapping: __getitem__、__contains__、__eq__、__ne__、get、items、keys、values
Container: __contains__  &&  iterable:  __iter__  &&  Sized:  __len__

```
```
"itertools"
函数创建迭代器以实现高效循环
该itertools模块包含许多常用的迭代器以及组合多个迭代器的函数。
该模块的功能分为几大类
(1)基于现有迭代器创建新迭代器的函数。
(2)用于将迭代器元素视为函数参数的函数。
(3)用于选择迭代器输出部分的函数。
(4)用于对迭代器输出进行分组的函数。
(5)支持迭代器的数据类型。
```
```
"字典生成式实例"
code_list=[ (0,'未注册'), (1,"已注册"), (2,'未登陆'), (3,'已登陆')]
code_dict={ state:code for code, state  in code_list}
print(code_dict)
# {'未注册': 0, '已注册': 1, '未登陆': 2, '以登陆': 3}

```
```
"json"
json模块总是生成str对象、而不是字节对象. 因此、fp.write()必须支持str输入
import json
skipkeys=True           # True时如果dict的keys不是基本类型、则忽略、也不会发生异常
ensure_ascii=True       # 所有中文等非ASCII字符输出用``\ uXXXX``序列进行转义
ensure_ascii=False      # 所有中文等非ASCII字符都不转义、输出原始值
check_circular=False    # 将跳过对容器类型的循环引用检查、循环引用将导致"OverflowError"(或更糟)
allow_nan=False         # 严格遵守JSON规范、而不是使用JavaScript等价物 (``NaN``, ``Infinity``, ``-Infinity``).
indent=4                # index控制缩进、格式化输出的JSON数组元素和对象成员
separators=(',', ': ')  # 分隔符如果指定,应该使用元组(item_separator, key_separator) 、
encoding='utf-8'        # 只有python2中有此参数、python3中没有
default                 # 如果指定，则default应该是为无法以其他方式序列化的对象调用的函数
sort_keys=True          # 如果sort_keys为true（默认值：False），则字典的输出将按键排序。
```
```
"将对象(obj)序列化为到文件(fp)的JSON格式的流"
    json.dump(obj, fp, *, skipkeys=False, ensure_ascii=True, check_circular=True, allow_nan=True, cls=None, indent=None, separators=None, default=None, sort_keys=False, **kw)
"将obj序列化为JSON格式的str"
    json.dumps(obj, *, skipkeys=False, ensure_ascii=True, check_circular=True, allow_nan=True, cls=None, indent=None, separators=None, default=None, sort_keys=False, **kw)
"将包含JSON文档的文本文件或二进制文件fp反序列化为Python对象"
    json.load(fp, *, cls=None, object_hook=None, parse_float=None, parse_int=None, parse_constant=None, object_pairs_hook=None, **kw)
"将s(包含JSON文档的str、bytes或bytearray实例)反序列化为Python对象"
    json.loads(s, *, encoding=None, cls=None, object_hook=None, parse_float=None, parse_int=None, parse_constant=None, object_pairs_hook=None, **kw)
```
```
"defaultdict "
conllections.defaultdict可以优雅的解决、处理找不到键的一个选择
在用户创建defaultdict对象的时候就需要给他配置一个为找不到的键创建默认值的方法
具体来说、在实例化一个defaultdict的时候、需要给构造方法提供一个可调用对象、
这个可调用对象在__getitem__找不到键的时候调用、让__getitem__返回某种默认值
这一切的背后特殊方法是 __missing__
它会在defaultdict遇到找不到键的情况下调用 defaultdict里的default_factory方法
特殊方法__missing__
所有映射类型在处理找不到键的时候、都会牵扯到__missing__方法
```
```
"字典视图"
dictionary view
字典视图是 dict.keys(), dict.values(), and dict.items() 返回的对象、
可以转为列表类型list(dictview)
```
```
"范围"
class range(object):
作用: 产生并返回一个整数序列对象
方法: ['count', 'index']
```
```
"关键字函数"
key function、关键字函数是可调用的，它返回用于排序或排序的值、
Python中的许多工具接受关键函数来控制元素的排序或分组方式。They include
min(), max(), sorted(), list.sort(),
heapq.merge(), heapq.nsmallest(), heapq.nlargest(), and itertools.groupby().
```
```
"字典变种"
conllections.OrderedDict() 这个类型在添加键时会保持顺序、因此键的迭代次序总是一致的
conllections.ChainMap() 这个类型可以容纳数个不同的映射对象、查找操作时被当作一个整体
conllections.Counter() 这个类型会给键准备一个整数计数器、可以用来给散列对象计数
conllections.UserDict 这个类其实是把标准dict用纯python又实现来一遍、让用户继承使用
标准库里所有映射类型都是可变的
```
```
"通用函数"
generic function 通用函数 由多个函数组成的函数，为不同类型实现相同的操作。
调用期间应使用哪种实现由调度算法确定。
```

```
拆包
unpacking
for 循环可以分别提取元组里的元素、也叫拆包、
拆包时、可以将不关注的元素赋值给_占位符
拆包让元组可以完美的被当作记录来使用。
拆包可以应用到任何可迭代对象上、如果元素数量与变量不一致可以使用*参数忽略多余的元素
```





















```
list.sort方法、内置函数sorted
list.sort方法会就地排序列表、不会把原列表复制一份、所以返回值为None、
如果一个函数或方法对对象进行的是就地改掉、它就应该返回None、python惯例、random.shuffle函数也遵守这个惯例
内置sorted方法、会新建一个列表作为返回值、可以接受任何形式的可迭代对象作为参数
内置sorted方法不管传入的参数是什么类型的始终返回一个列表
list.sort 和sorted 都有两个可选参数
"reverse":  reverse=True 时、被排序的序列中元素会以降序输出、反之亦然
"key":  key是一个函数作为参数、这个函数会被用在序列里的每个元素上
如对字符串进行排序sorted("Python Method",key=str.lower)
很多内置方法和标准库中的方法都支持key参数、itertools.groupby()、heapq.nlargest()
bisect 来管理以排序的序列
bisect模块包含两个主要函数、后续研究
```
```
变量查找规则
当我们使用一个变量时, 会优先在当前作用域中寻找该变量, 如果有则使用;
如果没有则继续去上一级作用域中寻找, 如果有则使用;
如果依然没有则继续去上一级作用寻找, 依次类推, 直到找到全局作用域, 依然没有找到的话, 则会抛出异常;
```
```
"全局作用域"
在全局都有效, 全局作用域在程序执行时创建, 在程序执行结束时销毁;
所有函数以外的区域都是全局作用域;
在全局作用域中定义的变量, 都属于全局变量, 全局变量可以在程序的任意位置被访问;
```
```
"函数作用域"
函数作用域在函数调用时创建, 在调用结束时销毁, 函数每调用一次就会产生一个新的函数作用域;
在函数作用域中定义的变量, 都是局部变量, 只能在函数内部被访问;
在函数中为变量赋值时, 默认都是为局部变量赋值;
如果需要在函数内部修改全局变量, 则需要使用global关键字来 声明 使用全局变量。
```
```
"requests"
请求参数:  
['method', 'url', 'params', 'data', 'json','headers', 'cookies', 'files', 'auth',
'timeout', 'allow_redirects','proxies', 'verify', 'stream', 'cert']
请求方法:  
['REQUEST','GET','POST','PUT','HEAD','DELETE','PATCH']
响应方法:  
"close()、encoding、json()、`raise_for_status`()"
响应属性:  
"apparent_encoding、content、cookies、elapsed、encoding、headers、history、
is_permanent_redirect、is_redirect、iter_content、iter_lines、links、next、ok、
raw、reason、status_code、text、url"
```

```
特殊方法
special method、特殊方法、隐式调用的方法、方法的名称以双下划线开头和结尾.
特殊方法用于支持: 迭代、集合类、属性访问、运算符重载、函数和方法的调用、对象创建和销毁、字符串表示、字符串格式化、上下文管理
```
```
====================================================================
"特殊方法 "
存在是用来被解释器调用的、通常我们不会使用它
my_object.__len__() 这种写法、尽管这么写是正确的但不推荐使用
而应该使用 len(my_object) 这种写法
特殊方法的调用是隐式的
for i in x: 这个语句的背后用的是iter(x) 方法、而iter(x)函数背后则是x.__iter__()方法
前提条件是这个方法在x中被实现了
通过使用内置方法len、iter、str等来使用特殊方法是最好的选择
====================================================================
```
```
"特殊方法一览"
可调用模拟   __call__
上下文管理   __enter__、__exit__
属性描述符   __get__、__set__、__delete__
迭代枚举     __iter__、__reversed__ 、__next__
实例创建和销毁 __new__、__init__、__del__
类相关服务    __prepare__、__instancecheck__、__subclasscheck__
字符串/字节序列表示形式 __repr__、__str__、__format__、__bytes__
集合模拟     __len__、__getitem__、__setitem__、__delitem__、__contain__
属性管理     __getattr__、__setattr__、__delattr__、__dir__、__getattribute__
数值转换     __abs__、__bool__、__complex__、__int__、__float__、__hash__、__index__
====================================================================
```
```
一元运算符
__neg__、__pos__、__abs__、    negative、positive、absolute
比较运算符
 __lt__、__le__、__eq__、      less than、less equal、equal
__gt__、__ge__、__ne__、    greter than、greter equal、inequality
算术运算符
__truediv__、__floordiv__、   / 、//
__add__、__sub__、__mul__    addition、subtraction、multiplication
__mod__、__divmod__、__pow__、__round__    %、divmod()、**、round()
反向运算符
__radd__、__rsub__、__rmul__、__rtruediv__、__rfloordiv__、__rmod__、__rdivmod__、__rpow__、
增量赋值运算符
__iadd__、__isub__、__imul__、__itruediv__、__ifloordiv__、__rmod__、__rpow__
位运算符
__invert__ ~、__lshift__ <<、__rshift__ >>、__and__ &、__or__ |、__xor__ ^

反向位运算符
 、__rlshift__ 、__rrshift__ 、__rand__ 、__ror__ 、__rxor__

增量赋值位运算符
 、__ilshift__ 、__irshift__ 、__iand__ 、__ior__ 、__ixor__
 当交互两个数的位置时、就会调用反向运算符
通过特殊方法、自定义数据类型可以表现的和内置类型一样、从而写出更好的代码
====================================================
```
```
class __generator(object):           # 表示生成器函数类型的模拟类
class __asyncgenerator(object):      # 表示异步生成器函数类型的模拟类
class __function(object):            # 表示函数类型的模拟类
class __method(object):              # 表示方法类型的模拟类
class __coroutine(object):           # 代表协程类型的模拟类
class __namedtuple(tuple):           # 命名元组的模拟基类
class __loader__(object):            # 内置模块的元路径导入
====================================================
```
```
class object:   # 最基本的类型
class int(object):
class str(object):
class bool(int):
class float(object):
class bytearray(object):
class bytes(object):
class complex(object):
==================================================
```
```
class range(object):    # 内置range类
class list(object):     # 内置可变序列
class tuple(object):    # 内置不可变序列。
class set(object):      # 无序的独特元素集合。
class dict(object):     # 字典
class map(object):      # 创建一个迭代器, 能够返回一个 map 的 obj
=================================================
```
```
class memoryview(object):   # 创建一个新memoryview对象引用给定对象的
class slice(object):        # 创建切片对象
class reversed(object):     # 在给定序列值上返回反向迭代器
class enumerate(object):    # 返回一个枚举对象
class filter(object):       # 过滤器对象
class frozenset(object):    # 构建一个不可变的无序的独特元素集合
================================================
```
```
class property(object):      # 提供了可读可写可删除的属性操作
class staticmethod(object):  # 将函数转换为静态方法。
class classmethod(object):   # 将函数转换为类方法
================================================
```
```
class super(object):            #
class zip(object):
class type(object):
=================================================
```
```
class BaseException(object): # 所有异常的公共基类
class Exception(BaseException): # 所有非退出异常的公共基类
class GeneratorExit(BaseException): # 生成器退出
class SystemExit(BaseException):
class StopAsyncIteration(Exception): # 从iterator.__anext__()发出结束信息
class StopIteration(Exception):          # 从iterator.__next__() 发出结束信号
class Warning(Exception):
================================================
```
```
class object:
__setattr__、__getattribute__、__delattr__
__eq__、__ne__、__ge__、__gt__、__le__、__lt__
__format__、__init__、__new__、__sizeof__、__hash__、__subclasshook__、
__repr__、__str__、__dir__、__reduce_ex__、__reduce__、__init_subclass__
属性
__class__ = None
__dict__ = {}
__doc__ = ''
__module__ = ''
================================================
```
```
def __format__(self, *args, **kwargs):
    """ Return a formatted version of the string as described by format_spec. """
@staticmethod
def __new__(*args, **kwargs):
    """ Create and return a new object.  See help(type) for accurate signature. """
def __init__(self, value='', encoding=None, errors='strict'):
=================================================
```
```
def __add__(self, *args, **kwargs):  """ Return self+value. """
def __mod__(self, *args, **kwargs):  """ Return self%value. """
def __mul__(self, *args, **kwargs):  """ Return self*value. """
def __rmod__(self, *args, **kwargs): """ Return value%self. """
def __rmul__(self, *args, **kwargs): """ Return value*self. """
def __eq__(self, *args, **kwargs):   """ Return self==value. """
def __ge__(self, *args, **kwargs):   """ Return self>=value. """
def __gt__(self, *args, **kwargs):   """ Return self>value. """
def __le__(self, *args, **kwargs):   """ Return self<=value. """
def __lt__(self, *args, **kwargs):   """ Return self<value. """
def __ne__(self, *args, **kwargs):   """ Return self!=value. """
==================================================
```
```
def __repr__(self, *args, **kwargs):         """ Return repr(self). """
def __str__(self, *args, **kwargs):          """ Return str(self). """
def __getitem__(self, *args, **kwargs):      """ Return self[key]. """
def __contains__(self, *args, **kwargs):     """ Return key in self. """
def __getattribute__(self, *args, **kwargs): """ Return getattr(self, name). """
def __getnewargs__(self, *args, **kwargs):
=================================================
```
```
def __hash__(self, *args, **kwargs):    """ Return hash(self). """
def __iter__(self, *args, **kwargs):    """ Implement iter(self). """
def __len__(self, *args, **kwargs):     """ Return len(self). """
def __sizeof__(self, *args, **kwargs):  " Return the size of the string in memory, in bytes. "
======================================================
```
```
"功能编程模块" [ itertools、functools、functools ]
"itertools模块" - 创建迭代器函数、用于高效循环
"functools模块" - 可调用对象的高阶函数和操作
"operator模块" - 标准运算符作为函数
```
```
无限迭代器：itertools模块、 [ count()、cycle()、repeat() ]
```
```
itertools.count(start=0,step=1) "创建一个无限迭代器，返回以数字start开头的均匀间隔值"  for i in count(0,2): print(i)  # count(start=0,step=1)、count()、count(9)、count(0,2)
itertools.cycle(iterable) "使迭代器返回迭代中的元素并保存每个元素的副本"  for i in cycle("ABCD"): print(i)  # cycle("1234")、cycle("01")
itertools.repeat(object[, times]) "创建一个一遍又一遍地返回对象的迭代器、除非指定了times参数、否则无限期运行"  for i in repeat("A",10): print(i)  # repeat("A")、repeat("A",100)、repeat("hello world")
```
```
itertools.accumulate(iterable[, func]) 创建一个迭代器, 返回累积的总和 accumulate([1,2,3,4,5]) --> 1 3 6 10 15
itertools.chain(*iterables) "用于将连续序列作为单一序列处理" chain('ABC', 'DEF') --> A B C D E F
itertools.chain.from_iterable(iterable)  替代构造函数[`chain()`]获取来自懒惰计算的单个可迭代参数的链式输 chain.from_iterable(['ABC', 'DEF']) --> A B C D E F
itertools.compress(data, selectors)  创建一个迭代器，用于过滤数据中的元素，只返回那些在选择器中具有相应元素且评估为True的元素  compress('ABCDEF', [1,0,1,0,1,1]) --> A C E F
itertools.dropwhile(predicate, iterable) "只要条件成立、就删除元素、一旦不成立就返回后面的所有数据" for i in dropwhile(lambda x: x<5,[1,4,,8,4,2,1]):
itertools.groupby(iterable, key=None)  "创建一个从迭代中返回连续键和组的迭代器。关键是计算每个元素的键值的函数"  k=[k for k, g in groupby('AAAABBBCCDAABBB')]---[A B C D A B]、[list(g) for k, g in groupby('AAAABBBCCD')] --> AAAA BBB CC D
itertools.filterfalse(predicate, iterable)  创建一个迭代器,用于过滤来自iterable的元素,只返回predicate=False时的元素False. filterfalse(lambda x: x%2, range(10)) --> 0 2 4 6 8
```
```
python3 "dict默认是有序的"、即按添加顺序排序的
```
```
collections — 容器类型  具有: 函数[ namedtuple ]、类[ ChainMap、Counter、OrderedDict、defaultdict、deque、UserDict、UserList、UserString]
```
```
dict  创建字典: [ dict(),dict(mapping), dict(iterable), dict(**kwargs)]
dict 方法："[ items(), keys(), values() ]"、"[update(), copy(), clear()]", [pop(k,d=None),popitem()]、"[ get(*args, **kwargs), setdefault(*args, **kwargs), fromkeys(*args, **kwargs) ]"
dict 方法:  pop(self, k, d=None)  删除指定的键并返回相应的值、如果指定了d的值、在未找到指定键时、返回该值
dict 方法:  popitem()  "移除字典最后一项、并返回移除项的(2-tuple)2元组表示 (key,value) "
dict 方法：[ __contains__、__delitem__、__getattribute__、__getitem__、__setitem__、__sizeof__、__repr__、__iter__、__len__、__init__、__new__、__lt__、__le__、__eq__、__ne__、__ge__、__gt__ ]
```
```
dict属性：__hash__ = None
```
```
"OrderedDict": dict的子类、记住插入顺序的字典、支持全部的dict方法、
OrderedDict([('a', 'A'), ('b', 'B'), ('c', 'C'), ('d', 'D')])
OrderedDict 特有的方法：popitem(last=True)  移除字典最后一项、"如果last=True，则以LIFO顺序返回对，如果last=False，则以FIFO顺序返回."
OrderedDict 特有的方法：move_to_end( key, last=True)  "将现有元素移动到末尾(如果last为false,则开头)."
```
```
"defaultdict": dict的子类、调用工厂函数来提供缺失值、、
```
```
"Counter": dict的子类、用于计算可哈希对象的字典的子类、有时叫一个pag或multiset、元素存储为字典键及其计数存储为字典值.
c = Counter('abcdeabcdabcaba') 、c.most_common(3)  、sorted(c)、c.clear()
Counter方法：most_common(n=None), elements(), subtract([iterable-or-mapping]), fromkeys(iterable), update([iterable-or-mapping])
```
```
"ChainMap": 将多个 dict或map 组合在一起创建单个可更新视图、"底层映射存储在列表中"、该list是公开的, 可以使用maps属性访问或更新、查找会连续搜索基础映射直到找到密钥、"写入\更新\删除 仅在第一个上运行映射".
class ChainMap(_collections_abc.MutableMapping):
ChainMap 方法：[ pop()、popitem() ]、[ " new_child(m=None) " ]、[copy()、clear()、get(key, default=None)、fromkeys(cls, iterable, *args) ]
ChainMap 方法：[__setitem__、__delitem__、__getitem__、__len__、__iter__、__contains__、__bool__、__repr__、__init__、__missing__、]
```
```
ChainMap 属性: " maps、parents "
```
```
"namedtuple": 是collections模块的一个函数、用于创建命名元组子类的工厂函数、返回带有命名字段的元组的新子类、
def namedtuple(typename, field_names, *, rename=False, defaults=None, module=None):
"创建命名元组": request = namedtuple(typename="request", field_names="method url headers data")
"nametuple对象赋值": req = request('GET', 'http://www.baidu.com', 'None', '数据')
"nametuple按名称获取字段的属性": print(req.method, req.url, req.headers, req.data)  # GET http://www.baidu.com None 数据
"nametuple支持解包": method,url,headers,data = req
"nametuple转换为OrderedDict字典 _asdict()方法":  print(req._asdict())   # OrderedDict([('method', 'GET'), ('url', 'http://www.baidu.com'), ('headers', 'None'), ('data', '数据')])
"nametuple修改命名字段的值 _replace()方法": print(req._replace(method='POST'))  # request(method='POST', url='http://www.baidu.com', headers='None', data='数据')
```
```
"deque": 类似于list的容器, 两端都有快速附加和弹出
"deque属性": maxlen  双端队列的大小、如果为None则无界
"deque方法": [ append(x)、appendleft(x)、extend(iterable)、extendleft(iterable) ]、"[ pop()、popleft()、remove(value)、reverse()、rotate(n=1) ]"、[ index(x)、insert(i, x)、clear()、copy()、count(x) ]
```
```
"UserDict": 包装字典对象以便于字典子类化、"事实上是对内建字典类型的 Python 封装"、可继承的字典类、
"UserList": 包装列表对象以便于列表子类化
"UserString": 包装字符串对象以便于字符串子类化
```

```
"1.内存管理"
一对象的引用计数机制,二垃圾回收机制,三内存池机制

一、对象的引用计数机制
Python内部使用引用计数，来保持追踪内存中的对象，所有对象都有引用计数。
引用计数增加的情况：
1，一个对象分配一个新名称
2，将其放入一个容器中（如列表、元组或字典）
引用计数减少的情况：
1，使用del语句对对象别名显示的销毁
2，引用超出作用域或被重新赋值
sys.getrefcount( )函数可以获得对象的当前引用计数
多数情况下，引用计数比你猜测得要大得多。对于不可变数据（如数字和字符串），解释器会在程序的不同部分共享内存，以便节约内存。
二、垃圾回收
1，当一个对象的引用计数归零时，它将被垃圾收集机制处理掉。
2，当两个对象a和b相互引用时，del语句可以减少a和b的引用计数，并销毁用于引用底层对象的名称。然而由于每个对象都包含一个对其他对象的应用，因此引用计数不会归零，对象也不会销毁。（从而导致内存泄露）。为解决这一问题，解释器会定期执行一个循环检测器，搜索不可访问对象的循环并删除它们。
三、内存池机制
Python提供了对内存的垃圾收集机制，但是它将不用的内存放到内存池而不是返回给操作系统。
1，Pymalloc机制。为了加速Python的执行效率，Python引入了一个内存池机制，用于管理对小块内存的申请和释放。
2，Python中所有小于256个字节的对象都使用pymalloc实现的分配器，而大的对象则使用系统的malloc。
3，对于Python对象，如整数，浮点数和List，都有其独立的私有内存池，对象间不共享他们的内存池。也就是说如果你分配又释放了大量的整数，用于缓存这些整数的内存就不能再分配给浮点数。


```







```
协程、抽象基类、可哈希、`__slots__`、MRO、鸭子类型、、
协程、coroutine、coroutine function
struct sequence、结构序列
context manager、上下文管理器
垃圾回收、引用计数、
可哈希、`__hash__()`、`__eq__()`
`__slots__`、通过预先声明空间实例属性和消除实例字典来节省内存、、
MRO、方法解析顺序、 method resolution order、
鸭子类型、duck - typing、编程风格、`hasattr()`
```
