# 依赖注入

### 什么是依赖注入？

在Class A中，会用到一个Class B的实例，则称A对B有一个依赖。例如类Human中会用到一个Father对象，就说Human对Father有一个依赖。

```java
public class Human {
    ...
    Father father;
    ...
    public Human() {
        father = new Father();
    }
}
```

当Human需要使用这个Father的时候，需要先获取到这个对象。最简单的方式是由Human自己来**主动获取**，例如使用Father的构造函数new一个出来。如果使用这种方式，Father就丧失了独立性，它无法在Human之外的地方使用（除非再new一次）。而Human其实只需要拿到Father对象去用就好了，不需要关注Father对象是怎么获得的。很明显，这种主动获取依赖的方式使得程序的模块化变得模糊，从而降低了灵活性。

因此程序很多时候需要**通过外部来获取对象**。

```java
public class Human {
    ...
    Father father;
    ...
    public Human(Father father) {
        this.father = father;
    }
}
```

上面代码中，Human把Father对象的初始化写入了构造方法中，外部在调用Human的构造方法的时候就初始化了Father对象。像这种情形，**无需自身关注，而通过外部来获取依赖，就称为依赖注入。**

### Java中的依赖注入

依赖注入的实现有多种途径，而在Java中，使用注解是最常用的。通过在字段的声明前添加@Inject注解进行标记，来实现依赖对象的自动注入。

```java
public class Human {
    ...
    @Inject Father father;
    ...
    public Human() {
    }
}
```

上面这段代码看起来很神奇：只是增加了一个注解，Father对象就能自动注入了？这个注入过程是怎么完成的？

实质上，如果你只是写了一个@Inject注解，Father并不会被自动注入。你还需要使用一个依赖注入框架，并进行简单的配置。现在Java语言中较流行的依赖注入框架有[Google Guice](https://github.com/google/guice)、[Spring](http://projects.spring.io/spring-framework/)等，而在Android上比较流行的有[RoboGuice](https://github.com/roboguice/roboguice)、[Dagger](http://square.github.io/dagger/)等。其中Dagger是我现在正在项目中使用的。如果感兴趣，你可以在[这篇文章](https://github.com/android-cn/android-open-project-analysis/tree/master/dagger)里面对依赖注入和Dagger了解到更多。
