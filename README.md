# 正则表达式30分钟入门教程

# 目录
1. [本文目标](README.md)
2. [如何使用本教程](README.md)
3. [正则表达式到底是什么东西?](README.md)
4. [入门](enterdoor.md)
5. [测试正则表达式](testRegularExp.md)
6. [元字符](README.md)
7. [字符转义](README.md)
8. [重复](README.md)
9. [字符类](README.md)
10. [分枝条件](README.md)
11. [反义](README.md)
12. [分组](README.md)
13. [后向引用](README.md)
14. [零宽断言](README.md)
15. [负向零宽断言](README.md)
16. [注释](README.md)
17. [贪婪与懒惰](README.md)
18. [处理选项](README.md)
19. [平衡组/递归匹配](README.md)
20. [还有些什么东西没提到](README.md)
21. [网上的资源及本文参考文献](README.md)

## 本文目标
> 30分钟内让你明白正则表达式是什么，并对它有一些基本的了解，让你可以在自己的程序或网页里使用它。

## 如何使用本教程

* 别被下面那些复杂的表达式吓倒，只要跟着我一步一步来，你会发现正则表达式其实并没有想像中的那么困难。当然，如果你看完了这篇教程之后，发现自己明白了很多，却又几乎什么都记不得，那也是很正常的——我认为，没接触过正则表达式的人在看完这篇教程后，能把提到过的语法记住80%以上的可能性为零。这里只是让你明白基本的原理，以后你还需要多练习，多使用，才能熟练掌握正则表达式。
* 除了作为入门教程之外，本文还试图成为可以在日常工作中使用的正则表达式语法参考手册。就作者本人的经历来说，这个目标还是完成得不错的——你看，我自己也没能把所有的东西记下来，不是吗？
* `清除格式` 文本格式约定：**专业术语** `元字符/语法格式 正则表达式` `正则表达式中的一部分(用于分析)` 对其进行匹配的源字符串 `对正则表达式或其中一部分的说明`
* `隐藏边注` 本文右边有一些注释，主要是用来提供一些相关信息，或者给没有程序员背景的读者解释一些基本概念，通常可以忽略。

## 正则表达式到底是什么东西？
> 字符是计算机软件处理文字时最基本的单位，可能是字母，数字，标点符号，空格，换行符，汉字等等。字符串是0个或更多个字符的序列。文本也就是文字，字符串。说某个字符串匹配某个正则表达式，通常是指这个字符串里有一部分（或几部分分别）能满足表达式给出的条件。

* 在编写处理字符串的程序或网页时，经常会有查找符合某些复杂规则的字符串的需要。正则表达式就是用于描述这些规则的工具。换句话说，正则表达式就是记录文本规则的代码。
* 很可能你使用过Windows/Dos下用于文件查找的通配符(wildcard)，也就是*和?。如果你想查找某个目录下的所有的Word文档的话，你会搜索*.doc。在这里，*会被解释成任意的字符串。和通配符类似，正则表达式也是用来进行文本匹配的工具，只不过比起通配符，它能更精确地描述你的需求——当然，代价就是更复杂——比如你可以编写一个正则表达式，用来查找所有以0开头，后面跟着2-3个数字，然后是一个连字号“-”，最后是7或8位数字的字符串(像010-12345678或0376-7654321)。
