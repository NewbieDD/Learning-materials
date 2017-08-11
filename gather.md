# equals与hashcode间的关系 #

##### 1.public boolean equals(Object obj)，和hashcode（）方法是object对象中的方法。 #####


#####2.equals与hashcode间的关系是这样的：#####

1、如果两个对象相同（即用equals比较返回true），那么它们的hashCode值一定要相同；

2、如果两个对象的hashCode相同，它们并不一定相同(即用equals比较返回false) 
  
即：(1)当obj1.equals(obj2)为true时，obj1.hashCode() == obj2.hashCode()必须为true 

(2)当obj1.hashCode() == obj2.hashCode()为false时，obj1.equals(obj2)必须为false




#####3为啥重写equals?#####

如果不重写equals，那么比较的将是对象的引用是否指向同一块内存地址，重写之后目的是为了比较两个对象的value值是否相等。
特别指出利用equals比较八大包装对象（如int，float等）和String类（因为该类已重写了equals和hashcode方法）对象时，
默认比较的是值，在比较其它自定义对象时都是比较的引用地址

#####4.什么是hashcode?#####

hashcode是用于散列数据的快速存取，如利用HashSet/HashMap/Hashtable类来存储数据时，
都是根据存储对象的hashcode值来进行判断是否相同的。
由于为了提高程序的效率才实现了hashcode方法，先进行hashcode的比较，如果不同，
那没就不必在进行equals的比较了，这样就大大减少了equals比较的次数，这对比需要比较的数量很大的效率提高是很明显的，

