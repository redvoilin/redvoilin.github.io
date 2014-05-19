---
layout: post
title: "Ruby惯用法"
date: 2014-05-17 23:06:38 +0800
comments: true
categories: 
---

本篇集中写了一些ruby中惯用的方法

1、拟态方法

puts “hello world” 这是一段很简单的代码，一些刚接触ruby的人可能以为puts是ruby中的关键字，其实不然，puts是一个方法，只是我们一般使用时都会省略括号，如果把上面这段代码写全了，是这样的 puts("hello world")

下面来看一个其它的例子，其实对象属性，也是伪装过的方法
``` ruby 对象属性
class Person
  def name=(value)
    @name = value
  end

  def name
    @name
  end
end

p = Person.new
p.name = "ch"
p.name    # => "ch"
```
代码p.name="ch"的功能和代码p.name=("ch")是一样的，只是前者写起来更简洁，代码p.name也是一样的道理，省略了括号。像这个把一个方法调用伪装成另外一种东西，我们可以称之为拟态方法。随着深入学习ruby，可以发现类中的访问修饰符private()和protected()，类宏attr_reader()、attr_writer()和attr_accessor()也都是拟态方法

