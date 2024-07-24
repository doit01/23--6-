单一职责原则（Single Responsibility Principle，SRP）：一个类应该只有一个引起变化的原因。换句话说，一个类应该只有一个责任。因此，拒绝编写大而全的类。
    开放-封闭原则（Open-Closed Principle，OCP）：用抽象的方式规范代码结构，用具体实现的方式实现业务功能，并且抽象层是无法被修改

示例：假设有一个图形类Shape，现在需要添加一个新的图形类型。按照开放-封闭原则，应该通过创建新的子类来扩展Shape，而不是修改Shape类本身
    里氏替换原则（Liskov Substitution Principle，LSP）：就是指多态，即父类的方法可以通过多种不同的重写，被实现。此时，父类仅仅起到一个规范的作用。

示例：假设有一个Rectangle类和一个Square类，Square是Rectangle的子类。按照里氏替换原则，任何使用Rectangle的地方都可以替换成Square而不影响程序的正确性

    依赖倒置原则（Dependency Inversion Principle，DIP）：高层模块不应该依赖于低层模块，二者都应该依赖于抽象；抽象不应该依赖于具体实现细节，具体实现细节应该依赖于抽象。

    其实，我们的常用的MVC架构就用到这个原则，比如，UserController（高层）依赖UserService接口（抽象层），而不是直接调UserServiceImpl（底层）

    接口隔离原则（Interface Segregation Principle，ISP）：客户端不应该依赖于它不使用的接口。换句话说，所设计的接口的影响范围越小越好，设计得越精准越好。

示例：假设有一个Worker接口，其中包含了work和eat两个方法。但是有些工作者并不需要eat方法。按照接口隔离原则，应该将Worker接口拆分为多个接口，每个接口包含特定的方法

    合成复用原则（Composite Reuse Principle，CRP）：尽量使用合成/聚合，而不是继承来达到代码复用的目的。换句话说，应该优先使用对象组合而不是类继承来实现代码复用。

示例：假设有一个Person类，它需要具有name和address属性。按照合成复用原则，应该将name和address抽象为一个独立的类，然后Person类通过组合的方式来使用



设计模式
├── 创建型模式（Creational Patterns）：关注对象的创建过程。
│   ├── 单例模式（Singleton Pattern）：确保一个类只有一个实例，并提供全局访问点。
│   ├── 工厂方法模式（Factory Method Pattern）：定义一个用于创建对象的接口，但让子类决定实例化哪个类。
│   ├── 抽象工厂模式（Abstract Factory Pattern）：提供一个接口，用于创建相关或依赖对象的家族，而不需要指定具体类。
│   ├── 建造者模式（Builder Pattern）：将一个复杂对象的构建与其表示分离，使同样的构建过程可以创建不同的表示。
│   └── 原型模式（Prototype Pattern）：通过复制现有对象来创建新对象，而不是通过实例化新对象。
单例模式优点：

    资源节约：单例模式避免了多次实例化造成的资源浪费。
    全局访问点：通过单例模式提供的全局访问点，可以方便地在程序的任何地方访问该实例。

缺点：

    可能引起性能问题：在高并发情况下，单例模式的实现可能会成为性能瓶颈。
    可能引起线程安全问题：如果实现不当，单例模式可能会引起线程安全问题
    
├── 结构型模式（Structural Patterns）：处理类和对象的组合，用于构建更大的结构。
│   ├── 适配器模式（Adapter Pattern）：将一个类的接口转换成客户端希望的另一个接口。
│   ├── 装饰器模式（Decorator Pattern）：动态地将责任附加到对象上，扩展其功能。
│   ├── 代理模式（Proxy Pattern）：为其他对象提供一种代理以控制对这个对象的访问。
│   ├── 外观模式（Facade Pattern）：为复杂子系统提供一个简化的接口。
│   ├── 桥接模式（Bridge Pattern）：将抽象部分与实现部分分离，使它们可以独立地变化。
│   ├── 组合模式（Composite Pattern）：将对象组合成树形结构以表示部分-整体层次结构。
│   └── 享元模式（Flyweight Pattern）：通过共享尽可能多的相似对象来减少内存使用和提高性能。

└── 行为型模式（Behavioral Patterns）：关注对象之间的通信和交互。
    ├── 观察者模式（Observer Pattern）：定义对象间的一对多依赖关系，当一个对象改变状态时，它的所有依赖者都会收到通知并自动更新。
    ├── 状态模式（State Pattern）：允许对象在内部状态改变时改变它的行为。
    ├── 策略模式（Strategy Pattern）：定义一系列算法，封装每个算法，并使它们可以互换。
    ├── 模板方法模式（Template Method Pattern）：定义算法的框架，将一些步骤延迟到子类中实现。
    ├── 职责链模式（Chain of Responsibility Pattern）：为解决同一问题的一组对象提供解决方案，将这些对象串成一条链，并在该链上传递请求，直到有一个对象处理它。
    ├── 命令模式（Command Pattern）：将请求封装成一个对象，从而允许用不同的请求对客户进行参数化。
    ├── 访问者模式（Visitor Pattern）：在不改变元素类的前提下定义作用于这些元素的新操作。
    ├── 备忘录模式（Memento Pattern）：在不破坏封装的前提下，捕获并保存一个对象的内部状态，以便稍后恢复它。
    ├── 中介者模式（Mediator Pattern）：通过一个中介对象来封装一系列对象之间的交互。
    └── 解释器模式（Interpreter Pattern）：定义一个语言的文法，并定义一个解释器来解释该语言中的句子。
