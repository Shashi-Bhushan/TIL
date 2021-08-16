# Maven Dependency Conflict

First thing you should check is 
```shell
mvn dependency:tree -Dincludes=com.google.guava -Dverbose=true
```

This would give you any conflicts you might have in your resolved dependency tree. Check that the expected version of the dependency is being resolved. 
