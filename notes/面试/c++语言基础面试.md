## 语言基础面试

## 1. 请简述 C 和 C++中的 struct 有什么区别？以及关于 C++ 中为什么要保留 struct 关键字说出你的思考.

C中struct是public的，而C++中struct等价与class,只是class中成员private

C++要兼容C语法，C++新的语言的推广不兼容C的话，让使用者学习代价大

## 2. C++11 中 const 与 constexpr 的区别

const只是代表不可改变的量，constexpr代表是常量

const编译期运行期，constexpr时编译期编译器在编译程序时可以顺带将其结果计算出来

还可以修饰函数，const函数返回值函数本身

## 3. 请尽可能多的说出你所知道的关于 C++ 中虚函数的相关知识

1. C++中实现多态的手段，父类指针调用子类方法，虚函数跟着对象走，普通跟着类走

2. 纯虚函数，具有纯虚函数的类是抽象类
3. 继承关系中父类的析构函数一定要设置为虚函数，先调用子类的析构函数，所以要把父类的析构函数设置为虚函数
4. 虚函数表中存储着每一个虚函数，根据着类进行分类，一个类一个虚函数表。
5. override关键字，虽然可有可无，但是让我们的实现更加严谨。
6. final结束相关成员方法虚函数的特性，final修饰的类不可以继承。
7. 虚函数表是如何知道this的

