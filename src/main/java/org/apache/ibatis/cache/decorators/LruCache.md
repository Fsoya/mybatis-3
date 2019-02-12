LinkedHashMap 实现 LRU 

```java
    new LinkedHashMap<Object, Object>(size, .75F, true) {
          private static final long serialVersionUID = 4267176411845948333L;
    
          @Override
          protected boolean removeEldestEntry(Map.Entry<Object, Object> eldest) {
            boolean tooBig = size() > size;
            if (tooBig) {
              eldestKey = eldest.getKey();
            }
            return tooBig;
          }
        };
```