# 一、基础
## （一）一些概念
1. **System.out.println( )**  
   A method that allows Java to output content to the Shell (screen).  
2. **System.out.println** 会在输出结束后添加平台相关的换行序列（如 Windows 的 `\r\n` 或 Unix 的 `\n`），用于结束当前行并换至下一行。  
3. **Syntax Error**  
   表示违反了 Java 的“语法”规则。  
4. **comment**  
   注释，单行注释 `//`，多行注释 `/* */`。  
5. **identify（变量）**  
   - 是无空格的连续字符序列，变量名中不能有空格。  
   - 可由大小写字母、数字或下划线 `_` 组成，首字符必须是字母或下划线。  
   - 区分大小写，如 `amount`、`Amount`、`AMOUNT` 是不同标识符。  
6. **value（值）**  
   - **integer（整数）**：`byte`、`short`、`long`、`int`。  
   - **float-point values（浮点值）**：`float`、`double`。  
   - **char**：表示单独字符（如 `'?'` `'7'`），实际当作数字处理，可定义 `tab` 和换行（如 `char c = '\n';`，注意单引号）。  
   - **String**（注意首字母大写 `S`）：表示字符串（如 `"Hello world!"`）。  
7. **最基本骨架**  
   ```java
   public class IntegerDivision {
       public static void main(String[] args) {
           // 实际操作，无 return，一般用于打印结果，返回值为 void
       }
   }
   ```  
8. **关键词**  
   `abstract`、`continue`、`for`、`new`、`switch`、`assert`、`default`、`goto`、`package`、`synchronized`、`boolean`、`do`、`if`、`private`、`this`、`break`、`double`、`implements`、`protected`、`throw`、`byte`、`else`、`import`、`public`、`throws`、`case`、`enum`、`instanceof`、`return`、`transient`、`catch`、`extends`、`int`、`short`、`try`、`char`、`final`、`interface`、`static`、`void`、`class`、`finally`、`long`、`strictfp`、`volatile`、`const`、`float`、`native`、`super`、`while`。  
9. **索引**  
   Java 中索引从 `0` 开始，范围是 `0` 到 `length - 1`，不允许 `-1`。  

## （二）数据结构
### 1. 数组（Array）  
- **特点**：  
  - 大小固定，不可改变。  
  - 可包含重复值。  
  - 一维数组打印：`Arrays.toString()`；二维数组打印：`Arrays.deepToString()`。  
- **格式**：  
  ```java
  int[] arr = new int[5]; // 初始化指定大小
  int[] arr = {1, 2, 3}; // 直接赋值
  ```  
### 2. 集合（Collection）  
- **特点**：大小可变，依赖具体集合类型（如 `ArrayList`、`HashSet` 等）。  
### 3. 数组列表（ArrayList）  
- **格式**：  
  ```java
  ArrayList<Integer> list = new ArrayList<>(); // Java 7+ 可省略右侧类型参数
  ```  
- **特点**：大小不固定，可包含重复值，支持索引访问。  
### 4. 哈希集合（HashSet）  
- **特点**：不包含重复值，无序集合，不保证元素顺序。  
### 5. 哈希映射（HashMap）  
- **特点**：存储键值对（key-value），不允许键重复，值可重复。  
- **格式**：  
  ```java
  HashMap<String, Integer> map = new HashMap<>();
  ```  

## （三）循环
1. **while 结构 / do while 循环**  
   - `while`：  
     ```java
     while (<expression>) {
         <statement(s)>
     }
     ```  
   - `do while`：  
     ```java
     do {
         <statement(s)>
     } while (<expression>);
     ```  
     `do while` 至少执行一次判断。  
2. **Iteration Variable**  
   每次循环执行时变化的变量，控制循环结束时机。  
3. **for 结构**  
   ```java
   for (<initialization>; <condition>; <increment/decrement>) {
       <statement(s)>
   }
   ```  
   **特殊 for 循环（增强型 for 循环）**：  
   ```java
   for (int number : numbers) {
       // 操作
   }
   ```  

### （三）方法
### 1.方法分类定义
- **实例方法（Instance Method）**：依赖对象实例调用，可访问实例字段，需创建实例（使用 `new`）。  
  ```java
  public class MyClass {
      public void instanceMethod() {
          System.out.println("Instance method");
      }

      public static void main(String[] args) {
          MyClass obj = new MyClass();
          obj.instanceMethod(); // 通过实例调用
      }
  }
  ```  
- **静态方法（Static Method）**：使用 `static` 关键字，可通过类名直接调用，不依赖实例。  
  ```java
  public class MyClass {
      public static void staticMethod() {
          System.out.println("Static method");
      }

      public static void main(String[] args) {
          MyClass.staticMethod(); // 通过类名调用
      }
  }
  ```  
- **抽象方法（Abstract Method）**：在抽象类或接口中声明，无方法体，由子类实现。  
  ```java
  public abstract class MyAbstractClass {
      public abstract void abstractMethod(); // 抽象方法
  }

  public class MyClass extends MyAbstractClass {
      @Override
      public void abstractMethod() {
          System.out.println("Abstract method implemented");
      }

      public static void main(String[] args) {
          MyClass obj = new MyClass();
          obj.abstractMethod(); // 调用实现的方法
      }
  }
  ```
  
---
  
### 2.参数  
- **parameter（形式参数）**：类似管道，不定义具体数值。  
  ```java
  public void myMethod(int parameter) {
      System.out.println("Parameter: " + parameter);
  }
  ```  
- **argument（实参）**：实际传递的值。  
  ```java
  MyClass obj = new MyClass();
  obj.myMethod(10); // 10 是实参
  ```



### 3.输入读取  
- **读取（Scanner 类）**：  
  ```java
  import java.util.Scanner;

  public class MyClass {
      public static void main(String[] args) {
          Scanner scanner = new Scanner(System.in);
          System.out.print("Enter your name: ");
          String name = scanner.nextLine();
          System.out.println("Hello, " + name);
          scanner.close();
      }
  }
  ```
### 4.数组相关方法  
- **copyOf**：`Arrays.copyOf(object, from, to)`，新数组额外元素填充 `0`、空字符或空字符串。  
  ```java
  import java.util.Arrays;

  public class MyClass {
      public static void main(String[] args) {
          int[] originalArray = {1, 2, 3, 4, 5};
          int[] copiedArray = Arrays.copyOf(originalArray, 3); // 复制前 3 个元素
          System.out.println(Arrays.toString(copiedArray)); // 输出: [1, 2, 3]
      }
  }
  ```  
- **copyOfRange()**：复制原始数组特定位置内容。  
  ```java
  import java.util.Arrays;

  public class MyClass {
      public static void main(String[] args) {
          int[] originalArray = {1, 2, 3, 4, 5};
          int[] copiedArray = Arrays.copyOfRange(originalArray, 1, 4); // 复制索引 1 到 3 的元素
          System.out.println(Arrays.toString(copiedArray)); // 输出: [2, 3, 4]
      }
  }
  ```  
- **binarySearch()**：`Arrays.binarySearch(name, element)`，返回元素索引。  
  ```java
  import java.util.Arrays;

  public class MyClass {
      public static void main(String[] args) {
          int[] array = {2, 5, 8, 12, 16, 23, 38, 56, 72, 91};
          int index = Arrays.binarySearch(array, 23); // 查找 23
          System.out.println("Index of 23: " + index); // 输出: Index of 23: 5
      }
  }
  ```  


### 5.泛型方法
- **Generic Method（泛型方法）**：  
  ```java
  public class MyClass {
      public static <T> void printArray(T[] array) {
          for (T element : array) {
              System.out.print(element + " ");
          }
          System.out.println();
      }

      public static void main(String[] args) {
          Integer[] intArray = {1, 2, 3};
          String[] stringArray = {"Hello", "World"};
          printArray(intArray);   // 输出: 1 2 3
          printArray(stringArray); // 输出: Hello World
      }
  }
  ```  



### 6.自定义方法
- **自定义方法**：  
  ```java
  public class MyClass {
      static String sayHello(String name) {
          return "Hello, " + name;
      }

      public static void main(String[] args) {
          String message = sayHello("Alice");
          System.out.println(message); // 输出: Hello, Alice
      }
  }
  ```  
  局部变量在声明处到代码块结束范围内有效。  
- **Overload method（方法重载）**：方法签名（参数类型、数量、顺序）不同但方法名相同。  
  ```java
  public class MyClass {
      public int add(int a, int b) {
          return a + b;
      }

      public double add(double a, double b) {
          return a + b;
      }

      public static void main(String[] args) {
          MyClass obj = new MyClass();
          System.out.println(obj.add(2, 3));       // 输出: 5
          System.out.println(obj.add(2.5, 3.5));   // 输出: 6.0
      }
  }
  ```  
  

## （四）实例方法中的变量
- **局部变量和全局变量**：  
  - 局部变量：定义在方法内部，仅方法内有效。  
    ```java
    public class MyClass {
        public void myMethod() {
            int localVar = 10; // 局部变量
            System.out.println(localVar);
        }
    }
    ```  
  - 全局变量（成员变量）：定义在类中，整个类内有效，通常为私有属性。  
    ```java
    public class MyClass {
        private int globalVar; // 全局变量

        public void myMethod() {
            globalVar = 20;
            System.out.println(globalVar);
        }
    }
    ```  
## （五）实例中的对象传递  
- **方法 1：对象引用传递**  
  方法参数传递对象引用（地址）的副本，修改对象状态影响调用者。  
  ```java
  public class PeopleCounter {
      private int count = 0;

      public void increment() {
          count++;
      }

      public int getCount() {
          return count;
      }
  }

  public class Main {
      public static void countUsingParameter(PeopleCounter counter) {
          counter.increment(); // 操作同一个对象
      }

      public static void main(String[] args) {
          PeopleCounter pc = new PeopleCounter();
          System.out.println("Before: " + pc.getCount()); // 输出: Before: 0
          countUsingParameter(pc);
          System.out.println("After: " + pc.getCount());  // 输出: After: 1
      }
  }
  ```  
- **方法 2：从方法返回对象**  
  方法返回对象引用，调用者接收引用操作对象。  
  ```java
  public class PeopleCounter {
      private int count = 0;

      public void increment() {
          count++;
      }

      public int getCount() {
          return count;
      }
  }

  public class Main {
      public static PeopleCounter getPeopleCounter() {
          return new PeopleCounter();
      }

      public static void main(String[] args) {
          PeopleCounter counter = getPeopleCounter();
          counter.increment();
          System.out.println("Count: " + counter.getCount());  // 输出: Count: 1
      }
  }
  ```  
# 二、类  
## （一）概念  
- **属性（attribute）**：必须声明为 `private`，保证封装性，防止外部直接访问和修改。  
  ```java
  public class MyClass {
      private int myAttribute; // 私有属性
  }
  ```  
- **方法（method）**：通常声明为 `public`，提供对外访问接口。  
  ```java
  public class MyClass {
      public void myMethod() {
          // 方法体
      }
  }
  ```  
- **类名**：必须以大写字母开头，遵循 Java 命名规范。  
  ```java
  public class MyClass { // 类名以大写字母开头
  }
  ```  



### （二）封装
- **封装（Encapsulation）**  
  在Java中，通常将类的属性声明为 `private`，禁止外部直接访问。  
  通过提供 **get** 和 **set** 方法，允许外部安全地访问和修改这些私有属性，保证数据的完整性和安全性。  
  这也是面向对象设计中封装原则的重要体现。

#### （1）**访问器（Accessor）方法**：  
  - 普通属性：`getXxx()`。  
  - 布尔类型属性：`isXxx()`。  
  ```java
  public class MyClass {
      private int myValue;
      private boolean isValid;

      public int getMyValue() {
          return myValue;
      }

      public boolean isValid() {
          return isValid;
      }
  }
  ```  

#### （2）**修改器（Mutator）方法**：

通常为 `set` 方法，修改私有属性值。  
  ```java
  public class MyClass {
      private int myValue;

      public void setMyValue(int myValue) {
          this.myValue = myValue;
      }
  }
  ```  
  
--- 

### （三）构建项目  
  - 第一步：定义类，明确属性和方法（含默认构造器、参数化构造器）。  
    ```java
    public class PeopleCounter {
        private long count = 0;

        // 默认无参构造器
        public PeopleCounter() {}

        // 参数化构造器
        public PeopleCounter(long count) {
            this.count = count;
        }

        // 计数加一方法
        public void anotherOne() {
            count++;
            System.out.println("So far " + count);
        }
    }
    ```  
  - 第二步：驱动类（Driver Class），含 `main()` 方法，调用方法。  
    ```java
    public class PeopleCounterProgram {
        public static void main(String[] args) {
            PeopleCounter pc = new PeopleCounter();
            pc.anotherOne();

            PeopleCounter pc2 = new PeopleCounter(10);
            pc2.anotherOne();
        }
    }
    ```  



# 三、关系  


## （一）继承  
- **概念**：  
  - `base class`（基类），`subclass`（子类）通过 `extends` 继承基类属性和方法，用 `super()` 调用基类。  
  - 子类含私有属性时，调用方法用 `@override` 声明。  
  ```java
  public class ChildClass extends BaseClass {
  }
  ```  
- **继承规则**：`super()` 必须写在方法体最前边。  

## （二）聚合与组成  
- **接口（interface）**  
  类通过 `implements` 实现接口，接口含抽象方法（无方法体）。实现类方法是否需 `return` 取决于接口方法声明的返回值类型（`void` 无需 `return`，非 `void` 必须有 `return`）。  
- **聚合（aggregation）**  
  整体与部分可独立存在，部分可属于多个整体。  
  ```java
  import java.util.ArrayList;

  // 定义饮品接口
  interface Beverage {
      double getPrice();
      String getDescription();
  }

  // 咖啡类实现接口
  class Coffee implements Beverage {
      private double price = 30.0;
      private String description = "Coffee";

      @Override
      public double getPrice() { return price; }
      @Override
      public String getDescription() { return description; }
  }

  // 茶类实现接口
  class Tea implements Beverage {
      private double price = 20.0;
      private String description = "Tea";

      @Override
      public double getPrice() { return price; }
      @Override
      public String getDescription() { return description; }
  }

  // 订单类，聚合饮品
  class DrinkOrder {
      private ArrayList<Beverage> order = new ArrayList<>();

      public void add(Beverage beverage) { order.add(beverage); }
      public double getTotalPrice() {
          double total = 0;
          for (Beverage b : order) total += b.getPrice();
          return total;
      }
      public ArrayList<Beverage> getOrder() { return order; }
  }

  // 测试
  public class Main {
      public static void main(String[] args) {
          DrinkOrder order = new DrinkOrder();
          Coffee coffee = new Coffee();
          Tea tea = new Tea();
          order.add(coffee);
          order.add(tea);

          for (Beverage b : order.getOrder()) {
              System.out.println(b.getDescription() + " - Price: " + b.getPrice());
          }
          System.out.println("Total price: " + order.getTotalPrice());
      }
  }
  ```  
- **组合（composition）**  
  整体与部分生命周期绑定，部分不能独立存在。  
  ```java
  class Engine {
      public Engine() { System.out.println("Engine created"); }
      public void start() { System.out.println("Engine started"); }
  }

  class Car {
      private Engine engine = new Engine(); // 组合关系，Car 创建时 Engine 也被创建

      public void start() {
          engine.start();
          System.out.println("Car started");
      }
  }

  public class Main {
      public static void main(String[] args) {
          Car car = new Car(); // 创建 Car 时 Engine 被创建
          car.start();
          // Car 销毁时，Engine 也随之销毁
      }
  }
  ```  

# 四、库  
## （一）基础  
1. **java.io**：传统的输入输出操作库，如文件读写、流操作等。  
2. **java.nio**：新的输入输出库，提供更高效的 I/O 操作，支持缓冲区、通道等特性。
