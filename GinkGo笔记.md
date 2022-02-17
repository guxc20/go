# GinkGo笔记
## 什么是ginkgo：
ginkgo是一个用go写的BDD(Behavior Driven Development)的测试框架，一般用于Go服务的 集成测试。
在BDD模式中，测试用例标题书写，非常注重表达，能清晰看到用例测试的业务场景


## Ginkgo安装
```
$ go get github.com/onsi/ginkgo/ginkgo
$ go get github.com/onsi/gomega/...
```

## Ginkgo常用模块
```
常用的10个：It、Context、Describe、BeforeEach、AfterEach、JustBeforeEach、BeforeSuite、AfterSuite、By、Fail
```

## It模块
```
It是测试例的基本单位，即It包含的代码就算一个测试用例
It可以理解维测试代码的最小单元
```

## Context和Describe 模块
```
Context和Describe的功能都是将一个或多个测试例归类
一个describe可以包含多个context，一个context可以包含多个IT模块
```

## BeforeEach模块
```
BeforeEach是每个测试例执行前执行该段代码
比如创建数据库连接就可以使用BeforeEach ，每个BeforeEach只在当前域内起作用。
执行顺序是同一层级的顺序执行，不同层级的从外层到里层以此执行。类似与 全局变量和局部变量的区别
```

## AfterEach模块

```
AfterEach是每个测试例执行后执行该段代码
比如销毁数据库连接，一般用于测试例执行完成后进行数据清理，也可以用于结果判断
```

## 常用命令
```
ginkgo bootstrap  创建测试关联文件
比如在boot文件目录上执行 ginkgo bootstrap 项目下会创建一个 books_suite_test.go文件

ginkgo generate <filename(s)> 生成测试代码模版
创建测试模版文件 ginkgo generate books 当前的包名字叫 books所以 创建出来的测试模版文件叫
books_test.go

执行测试代码
go test -v
ginkgo
```

## 参考文档
[ginkgo：初学者指南_feiger的专栏-CSDN博客_ginkgo](https://blog.csdn.net/textdemo123/article/details/105427837)
https://www.ginkgo.wiki/chapter1.html
