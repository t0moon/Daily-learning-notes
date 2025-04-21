# 一、基础
## （一）变量
1. 必须以字母或下划线字符开头。
2. 不能以数字开头。
3. 只能包含字母、数字和下划线字符。
4. 变量名称区分大小写。
5. 驼峰式：myValue
6. 蛇形：my_value
## （二）进制
对于二进制数，我们添加前缀 0b（数字 0 和字母 b）。 对于八进制数，我们添加前缀 0o（数字 0 和字母 o）。 对于十六进制数字，我们添加前缀 0x（数字 0 和字母 x）
## （三）转义字符
\	将 \ 放在行尾，反斜杠和换行符将被忽略。	print（“第 1 行 \line2 \line3”）

\\	输出反斜杠。	print（“\\”）

\'	输出单引号。	print（“\'”）

\"	输出双引号。	print（“\””）

\b	\b 代表退格键，并删除 \b 之前的字符。	print（“嗨\b 世界！”）

\n	\n 在每个 \n 后添加一行新行。	print（“第一行。\n第二行。\n第三行。”）
三个双引号或三个单引号来分配多行字符串，而无需使用换行符。

\t	\t 添加一个空格。	print（“你好\t 世界！”）
## （四）报错
1. syntax 语法错误： due to the order of operations.
2. TypeError类型错误: unsupported operand type(s) for +: 'int' and 'str'
3. IndexError: list index out of range
4. IndentationError: 缩进错误
## （五）列表
1. 列表有序列，索引index从0开始映射，可以通过索引来找到
2. 列表中元素类型不一定是同一类型，str、float等等都可以
3. 列表中的元素为另外一个列表时，称为nested
4. 列表可变
5. 列表运算
in + = 

切片:list[:3]，左包右不包
list[3:]右包
6. 方法和函数（method and function）
list.append(x),在列表的末尾增加x
list.insert(3，x)在索引3的位置插入x
list1.extend(list2),在列表1的末尾插入列表2
list.sort(),排序，如果是英文字符串，按照首字母，数字按照大小排序
list.pop(x),移除索引为x的元素
del list[x],删除索引内的元素
list.remove(x),删除列表中的元素x，这个x是指索引最小的x
max（） 函数（代表 maximum）返回列表（或其他数据收集类型）中的最大值。
min（） 函数（代表 minimum）返回列表（或其他数据收集类型）中的最小值。
len（） 函数（代表长度）返回列表（或其他数据收集类型）中的元素数。
sum（） 函数返回列表（或其他数据收集类型）中所有值的总和。
## （六）元组、集合
1. 集合（set）不允许重复。mySet = {“apple”，“pear”，“banana”}
2. 元组（tuple）:myTuple = （“苹果”，“梨”，“香蕉”）
当数据不随时间变化时。请记住，元组是完全不可更改的，这意味着在创建元组后，我们无法更改、添加或删除元素。
当数据是异构的（多样化）时，这意味着您在可迭代对象中可能没有相同类型的元素，例如将 name 作为一个元素，将 age 作为另一个元素。
对 Tuples 中的每个数据片段重复相同的代码时。
列表和元组是有序的，所以元素可以按索引位置找到。
不允许对元素进行任何更改。
3. 字典有键值对。
当您需要关联两个或多个数据时。
当您计算多个事物时，例如段落中使用的单词数或输入数字的次数。
当您跟踪您看到的多个事物时，按某些类别进行组织，例如出现的蓝色项目的数量或菜单上的开胃菜数量。
myDict = {'apple'： '红'， '梨'： '绿色'， '香蕉'： '黄色'}
eng2span = dict()
eng2span['one'] = 'uno'
print(eng2span)

结果：
{'one': 'uno'}    在字典中，左侧的是key，右侧是值
## （七）多维 Multiple Dimensions
一般计算到二维，也就是nested list。指的是，列表里边嵌列表
myList = [[9, 8], [7, 6], [5, 4], [3, 2]]
print(multiplesList[0][1])，
###0指的是第一个列表，1指的第一个列表中的第二个数字，最后输出8
multiplesList[0].append(6)
###指的是在第一个列表中，末尾增加6这个参数，但是一次只能传输一个参数（列表或者一个数值）

## （八）breakpoint和debug

# 二、类
## （一）method和attribute区别
在Python中，`attribute`（属性）和`method`（方法）有以下区别：

### 定义与本质
- **Attribute（属性）**：是对象的特征或数据成员 ，用于存储与对象状态相关的信息，本质上是变量。比如在定义一个`Person`类时：
```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
```
这里的`name`和`age`就是`Person`类实例的属性，用于描述人的姓名和年龄这些状态信息 。属性可以在对象创建时初始化，也能在对象生命周期内通过方法修改 。

- **Method（方法）**：是定义在类内部的函数，用于描述类的实例（对象）的行为，本质上是函数 。例如：
```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    def introduce(self):
        print(f"My name is {self.name}, and I'm {self.age} years old.")
```
`introduce` 就是`Person`类的一个方法，用于实现对象自我介绍的行为 。

### 调用方式
- **Attribute（属性）**：通过对象名加属性名，使用点号`.`访问 。例如：
```python
person = Person("Alice", 30)
print(person.name)  # 访问属性
```
- **Method（方法）**：同样通过对象名加方法名，使用点号`.`调用，但方法调用时通常要加括号 `()` ，如果方法有参数还需传入对应参数 。比如：
```python
person = Person("Alice", 30)
person.introduce()  # 调用方法
```

### 功能作用
- **Attribute（属性）**：主要用于描述对象的状态 ，不同的属性值可区分不同对象个体 。如`Car`类中，`color`属性区分汽车颜色，`model`属性区分汽车型号 。
- **Method（方法）**：用于定义对象能执行的操作或行为 ，可操作属性来实现对象行为 。比如`Car`类的`start_engine`方法，可能会检查`fuel_level`属性判断能否启动发动机 。 

### 与对象的关系
- **Attribute（属性）**：是对象的组成部分，直接描述对象状态 。
- **Method（方法）**：紧密关联对象，是对象行为的具体实现。不同对象实例调用相同方法，执行结果可能因对象属性不同而有差异 。比如不同半径的圆形对象调用计算面积的方法，得到的面积值不同 。 

此外，从技术层面讲，方法其实也是一种特殊的属性，在类的定义中，方法作为可调用的属性存在于类的命名空间中 ，但在实际编程使用和概念理解上，二者有上述明显区别。 

-----

## （二）封装


在 Python 中，**封装的核心底层原因是类的属性默认具有「开放性」**——外部代码可直接读写属性，这可能导致数据混乱。封装通过限制直接访问，强制数据修改遵循业务规则，保护对象状态的完整性。以下从技术原理和实践场景展开分析：


### 一、问题根源：Python 属性的「开放性」
Python 中，类的属性默认是**公开的（public）**，外部代码可直接读写，缺乏天然的访问控制：
```python
class Person:
    def __init__(self, age):
        self.age = age  # 直接暴露属性，外部可自由修改

p = Person(25)
p.age = -5  # 非法数据被写入，破坏对象状态
```
### 底层风险
1. **数据不一致**：属性值可能违反业务规则（如年龄为负、薪资为 0）。  
2. **逻辑分散**：数据校验、日志等逻辑散落各处，难以维护。  
3. **状态不可控**：无法跟踪属性修改过程，调试困难。

#### 封装的本质
将「自由修改」转为「受控修改」：  
所有属性操作必须通过类定义的**接口（方法或 `@property`）**，并在接口中植入校验、日志等逻辑。


### 二、封装的核心动机：维护对象的「不变性」
每个对象都有「不变性约束」（Invariants），例如：  
- `Person` 的年龄必须 ≥ 0  
- `BankAccount` 的余额必须 ≥ 0  
- `Circle` 的半径必须 > 0  

#### 1. 强制校验：拒绝非法数据
```python
class Person:
    def __init__(self, age):
        self.set_age(age)  # 初始化时通过方法赋值，确保合法性

    def set_age(self, value):
        if value < 0:
            raise ValueError("年龄不能为负数")
        self._age = value  # 单下划线：约定「内部属性」，非强制私有

p = Person(-5)  # 初始化时即报错，避免非法对象诞生
```

#### 2. 统一逻辑：集中管理修改规则
所有属性修改必须通过方法，避免逻辑重复：  
```python
p.set_age(30)  # 合法修改  
p.set_age("25")  # 在方法中添加类型校验，拒绝非整数输入  
```

#### 3. 可追溯性：附加业务逻辑
通过方法封装，可植入日志、审计等额外逻辑：  
```python
def set_age(self, value):
    if self._age != value:  # 仅值变化时记录日志
        logger.info(f"年龄从 {self._age} 改为 {value}")
    # 执行校验逻辑...
```


### 三、封装的深层意义：隔离变化，保护接口
### 1. 内部实现与外部调用解耦
#### 不封装（直接暴露属性）：
```python
class Circle:
    def __init__(self, radius):
        self.radius = radius  # 外部直接访问
```  
若后续需求变更（如半径必须为浮点数且 > 0），所有调用处都需修改。

#### 封装后（通过 `@property`）：
```python
class Circle:
    @property
    def radius(self):
        return self._radius

    @radius.setter
    def radius(self, value):
        if value <= 0:
            raise ValueError("半径必须 > 0")
        self._radius = float(value)  # 内部实现变更，外部调用不变

c = Circle(5)
c.radius = 3.5  # 外部调用方式不变，内部自动处理校验和类型转换
```



# 三、读取写入文件
## Python文件操作笔记
### 1. 文件模式

在Python中，文件模式决定了如何访问文件。常见的文件模式包括：

- **`'r'`**：只读模式（默认模式），用于读取文件内容。
- **`'w'`**：写入模式，会清空文件内容并写入新内容。如果文件不存在，则创建新文件。
- **`'a'`**：追加模式，会在文件末尾追加新内容。如果文件不存在，则创建新文件。
- **`'x'`**：创建模式，用于创建新文件。如果文件已存在，则会引发异常。
- **`'r+'`**：读写模式，允许读取和写入文件内容。
- **`'w+'`**：读写模式，会清空文件内容并允许读写。
- **`'a+'`**：读写模式，允许读取和在文件末尾追加内容。

### 2. 读取文件

#### 2.1 使用`read()`方法

- **功能**：一次性读取整个文件的内容，并将其作为一个字符串返回。
- **示例**：
  ```python
  with open('example.txt', 'r') as f:
      content = f.read()
      print(content)
  ```

#### 2.2 使用`readline()`方法

- **功能**：逐行读取文件内容，每次读取一行，并返回该行作为一个字符串。
- **示例**：
  ```python
  with open('example.txt', 'r') as f:
      line = f.readline()
      while line:
          print(line)
          line = f.readline()
  ```

#### 2.3 使用`readlines()`方法

- **功能**：将文件的所有行读取到一个列表中，每行作为列表的一个元素。
- **示例**：
  ```python
  with open('example.txt', 'r') as f:
      lines = f.readlines()
      for line in lines:
          print(line)
  ```

### 3. 写入文件

#### 3.1 使用`write()`方法

- **功能**：将字符串写入文件中。
- **示例**：
  ```python
  with open('example.txt', 'w') as f:
      f.write("Hello, World!")
  ```

#### 3.2 使用`writelines()`方法

- **功能**：将多行内容写入文件。
- **示例**：
  ```python
  lines = ["Line 1\n", "Line 2\n", "Line 3\n"]
  with open('example.txt', 'w') as f:
      f.writelines(lines)
  ```

### 4. 删除文件

在Python中，删除文件通常使用`os`模块的`remove()`函数。

- **示例**：
  ```python
  import os
  os.remove('example.txt')
  ```

### 5. CSV文件操作

#### 5.1 读取CSV文件

使用`csv.reader()`读取CSV文件。

```python
import csv
with open('example.csv', 'r') as f:
    reader = csv.reader(f)
    for row in reader:
        print(row)
```

#### 5.2 写入CSV文件

使用`csv.writer()`写入CSV文件。

```python
import csv
with open('example.csv', 'w') as f:
    writer = csv.writer(f)
    writer.writerow(["Name", "Age"])
    writer.writerow(["John", 30])
```

### 6. 文件关闭

- **手动关闭文件**：使用`close()`方法。
  ```python
  f = open('example.txt', 'r')
  # ...
  f.close()
  ```

- **使用`with`语句**：自动关闭文件。
  ```python
  with open('example.txt', 'r') as f:
      # ...
  ```

### 7. 异常处理

在文件操作中，应注意可能出现的异常，如文件不存在或权限不足。

```python
try:
    with open('example.txt', 'r') as f:
        # ...
except FileNotFoundError:
    print("File not found.")
except Exception as e:
    print(f"An error occurred: {e}")
```

### 8. CSV文件示例

以下是使用CSV文件进行员工信息管理的示例：

```python
import csv

def read_employees(filename):
    try:
        employees = []
        with open(filename, 'r') as f:
            reader = csv.reader(f)
            for row in reader:
                employees.append(row)
        return employees
    except FileNotFoundError:
        print("File not found.")
        return []

def write_employees(employees, filename):
    try:
        with open(filename, 'w') as f:
            writer = csv.writer(f)
            writer.writerows(employees)
    except Exception as e:
        print(f"An error occurred: {e}")

def add_employee(employees):
    empid = input("Enter the employee ID: ")
    name = input("Enter the employee name: ")
    employee = [empid, name]
    employees.append(employee)
    return employees

def delete_employee(employees, empid):
    for i, employee in enumerate(employees):
        if employee[0] == empid:
            employees.pop(i)
            return employees
    return employees

filename = "employees.csv"
employees = read_employees(filename)

while True:
    print("1. List Employees")
    print("2. Add Employee")
    print("3. Delete Employee")
    print("4. Exit")
    choice = input("Enter your choice: ")
    
    if choice == "1":
        for employee in employees:
            print(f"ID: {employee[0]}, Name: {employee[1]}")
    elif choice == "2":
        employees = add_employee(employees)
        write_employees(employees, filename)
    elif choice == "3":
        empid = input("Enter the employee ID to delete: ")
        employees = delete_employee(employees, empid)
        write_employees(employees, filename)
    elif choice == "4":
        break
    else:
        print("Invalid choice. Please try again.")
```

### 总结

- **文件模式**：根据需要选择合适的文件模式。
- **读写方法**：使用`read()`、`readline()`、`readlines()`和`write()`、`writelines()`方法。
- **异常处理**：注意可能出现的异常，并进行适当的处理。
- **CSV文件操作**：使用`csv`模块进行CSV文件的读写。

