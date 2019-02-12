装饰器模式(Decorator)|代理模式(Proxy)|委托模式(Delegate) 

 > proxy与delegete语义（也即使用场景）的区别：
       proxy :译为代理， 被代理方（B）与代理方（A）的接口完全一致。 主要使用场景（语义）应该是：为简化编程（或无法操作B），不直接把请求交给被代理方（B），而把请求交给代码方（A），由代理方与被代理方进行通信，以完成请求。
       delegete : 译为委托，主要语义是：一件事情（或一个请求）对象本身不知道怎样处理，对象把请求交给其它对象来做。
  <br><br>原文：https://blog.csdn.net/jince007/article/details/40179339 

```java
    public class FifoCache implements Cache {
      private final Cache delegate;
      ...
    
      public FifoCache(Cache delegate) {
        this.delegate = delegate;
        ...
      }
      
      @Override
      public String getId() {
        return delegate.getId();
      }
    
      @Override
      public int getSize() {
        return delegate.getSize();
      }
      
      ...
    }
  
```