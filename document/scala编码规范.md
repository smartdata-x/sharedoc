#Scala编码规范

##1.命名
1. `class`,`object`,`trait`名首字母大写	
2. 方法名,非静态变量名首字母小写
3. 以上均遵循驼峰命名法
4. 静态变量全部大写,单词用"_"隔开
5. `val`变量不允许用`var`声明
6. 命名必须有含义,非特殊情况不允许用汉语拼音
7. 长度在10个字符以内的变量名不允许用包含单词的缩写(`min`等常见缩写除外)
8. 非特殊情况不可以用'XX1','XX2'或'XXa','XXb'的格式命名变量


##2.注释
1. 创建`class`,`object`,`trait`时必须加上作者,创建日期,和说明信息
<br>
`/**`
<br>
`　* Created by yangshuai on 2016/4/26.`
<br>
`　* XX项目主流程类`
<br>
`　*/`
<br>
`object Scheduler {`

2. 方法必须有注释,且包含对该方法作用的说明(特别简单的类似get,set的方法可以不加注释)
<br>
`/**`
<br>
`　* 拼接url对应的json字符串`
<br>
`　* @param url 需要转换为messagr的url`
<br>
`　* @author yangshuai`
<br>
`　*/`
<br>
`  def getUrlJsonString(url: String): String = {`
3. 方法的注释中必须包含所有参数的说明(特别简单的类似get,set的方法可以不加)
<br>
   例子同上
4. 如果`class`,`object`,`trait`的作者和方法的作者不同,则方法的注释中必须包含`@author`属性
<br>
	例子同2. 
5. 针对`class`,`object`,`trait`和方法的注释必须使用如下形式的
<br>
`/**`
<br>
`　*`
<br>
`　*/`
6. 针对若干行代码的注释必须使用如下形式
<br>
`//`
7. `pull request`中如无特殊情况不可包含注释掉的代码,如有调试需要则应从当前分支checkout出一个新的分支,在新的分支中删掉不应提交的部分,然后用新的分支来创建`pull request`


##3.空格 
1. 类名前后必须有且只有一个空格(class, object, trait)
<br>
`class Text {`
<br>
`}`
<br>
2. 流程控制相关的关键字如`if`,`for`,`while`和左括号`(`之间必须有且只有一个空格
<br>
`if (`
<br>
3. 关键字`try`和`{`之间必须有且只有一个空格
<br>
`try {`
4. 方法的签名中冒号(`:`)前面不允许有空格,后面必须有且只有一个空格,逗号(`,`)后面必须有且只有一个空格,等号(`=`)前后各有且只有一个空格
<br>
`  def example(url: String, content: String): String = {`
5. 数组和元组中的元素之间或调用方法时如有多个参数,逗号(`,`)后面必须有且只有一个空格
<br>
`　(url, content)`
<br>
`　example(url, content)`


##4.空行
1. 流程控制相关的block的第一行代码之前与最后一行代码之后必须有且只有一个空行
<br>
`val number = 1`
<br>
`　(此处必须有一个空行)`
<br>
`if (number == 1) {`
<br>
`}`
<br>
`　(此处必须有一个空行)`
2. 如果**方法**或流程控制相关的block内部(大括号内)的代码行数大于2行,则第二行和倒数第二行必须为空行
<br>
`if (number == 1) {`
<br>
`　(此处必须有一个空行)`
<br>
`　val count == 2`
<br>
`　val max == 20`
<br>
`　val min == 2`
<br>
`　(此处必须有一个空行)`
<br>
`}`
<br>
3. 如果方法有返回值,则`return`对应的行上面必须有且只有一个空行,下面不留空行
<br>
`　val min == 2`
<br>
`　(此处必须有一个空行)`
<br>
`　return min`
<br>
`}`
4. 方法之间必须有且只有一个空行
5. `class`,`object`,`trait`的属性之间必须有且只有一个空行
<br>
`class People {`
<br>
`　(此处必须有一个空行)`
<br>
`　var name: String = ""`
<br>
`　(此处必须有一个空行)`
<br>
`　var weight: float = 0f`

##5 其他
1.`if`,`else`,`try`,`catch`等关键字与其对应的大括号必须在同一行且中间要有空格
<br>
`　} else {`

2.定义和调用无返回值的无参方法时必须加上`()`
