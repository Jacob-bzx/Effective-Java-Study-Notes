## 主旨

用静态工厂替代构造函数


## 优点

1. Unlike constructors，static factory method have names.

   静态工厂有函数名，可以用来区分不同的函数。而构造方法没有函数名，只能通过方法的参数不同来进行区分。

2. They are not required to create a new object each time they're invoked.

   类就变得 instance-controlled。如单例，不可实例化的类等都是通过这种方式实现的。

3. They can return an object of any subtype of their return type.

   可满足面向接口编程的规范。
   
4. The returned type can vary from call to call as a function of the input parameters.

   书中举了一个 EnumSet 的例子，感觉不是很普遍。

5. The returned object need not exist when the class containing the method is written.

   书中举了一个 service provider framework 的例子。 

## 缺点

1. The classes without public or protected constructors cannot be subclassed.

2. They are hard for programmers to find.

    所以建议静态工厂采用好的名字。

   * ***from***——type-conversion
   * ***of***——aggregation
   * ***valueOf***——verbose alternative to ***from*** and ***of***
   * ***instance*** / ***getInstance***
   * ***create*** / ***newInstance***
   * ***get*[Type]**——The factory method is in a different class.
   * ***new*[Type]**——The factory method is in a different class.
   * ***type***——A concise way.

## 总结

多用静态工厂替代构造函数。