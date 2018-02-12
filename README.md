# 52ABP.CodeGenerator
52ABP的代码生成器，反馈收集问题和文档信息。
## 前言

但是这个月好歹抽空做了一些事情，嗯。就是一直说的ABP 的新版本代码生成器，之前的代码生成器大家说不支持.NET CORE。
现在这个版本终于支持了。
也算是兑现了承诺。
> ABP Code Generator 是基于ABP（ASP.NET Boilerplate）框架制作的代码生成器，可以用于大家在日常开发过程中节约时间，把更多的精力放于业务逻辑的处理中。 

> 欢迎您使用 ABP Code Generator ，重新开发的代码生成器，[支持.net framework和.net](http://xn--framework-yw9o.net/) core 双版本。
开发代码生成器的初衷是为了让大家专注于业务开发，而基础设施的地方，由代码生成器实现，节约大家的实现。实现提高效率、共赢的局面。 欢迎到：[https://github.com/52ABP/52ABP.CodeGenerator](https://github.com/52ABP/52ABP.CodeGenerator) 提供您的脑洞，如果合理的我会实现哦~


# 说正事

在群里已经内测了一周多的时间，也算稳定了，终于可以做成教程出来见人了。
#### 支持 Visual Studio 2015 和 Visual Studio 2017 哦
## 下载方式：
首先打开Visual Studio 的工具- 拓展和更新 菜单栏，见下图：
![菜单栏.png](http://upload-images.jianshu.io/upload_images/1979022-9e9af10a566e0b3c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
然后选择 **“联机”**菜单栏 ，再在右侧 搜索"ABP"，
![image.png](http://upload-images.jianshu.io/upload_images/1979022-53a6a30af23e4d6d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
我们可以看到有4个工具。
我们都简单说明下：
ABP Code Generator 是之前开发的，用的是基架体系可以参考文章：http://t.cn/RRMQQhS
![ABP Code Generator.png](http://upload-images.jianshu.io/upload_images/1979022-eedee2ec9463687d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

ABP Code Power Tools 是目前支持.Net Framework 和.NET Core的代码生成器。
![image.png](http://upload-images.jianshu.io/upload_images/1979022-39b2a8f1c1ffb1b7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
也是接下来会持续进行更新的项目之一。

后面的ABPHelper 是国外的一个人开发的，大家有兴趣也可以使用。
最后的ASP.NET Zero Power Tools是ABP官方推出的代码生成器，功能强大，唯一的问题就是要**给钱**。

# 如何使用
只要是ABP的项目无论是Core还是Framework 版本都可以。
打开解决方案，选择Core层。
![image.png](http://upload-images.jianshu.io/upload_images/1979022-8d29b2684ea52597.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
我们选择“Book”的实体文件，
```
using Abp.Domain.Entities;

using System;
using System.Collections.Generic;
using System.ComponentModel.DataAnnotations;
using System.IO;
using System.Linq;
using System.Text;

namespace SmartToken.Persons
{
  public  class Book:Entity<long>
    {
       
        [Required]
        [MaxLength(32)]
        public virtual string Name { get; set; }

        [Required]
        [MaxLength(32)]
        public virtual string Surname { get; set; }

        [MaxLength(255)]
        public virtual string EmailAddress { get; set; }
    }
}
```
在实体文件"Book"上右键点击
![右键.png](http://upload-images.jianshu.io/upload_images/1979022-2ff312fa3c86b67d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
展开对话框
![基本信息配置.png](http://upload-images.jianshu.io/upload_images/1979022-0bd77cd646bee086.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 说下重点，如果是刚刚生成器的ABP空项目，请选择“第一次使用代码生成器”，它会帮助您生成相关的基类代码。

>另外选择你的项目版本比如是.NET Core 和.Net Framework  

然后点击确定
![Dto信息](http://upload-images.jianshu.io/upload_images/1979022-8bec982f44295d23.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
选择要生成的字段信息。点击确定即可。
以下是生成的文件信息：

![Core层.png](http://upload-images.jianshu.io/upload_images/1979022-b1907fd6b1079d37.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![Application层.png](http://upload-images.jianshu.io/upload_images/1979022-7d2821eec448df6d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

生成了领域层和应用层的相关代码，涉及的功能有：
领域层初始化、AutoMapper自动注入、表的增删改查、批量删除、单数据修改等功能。
基本上来说和上一个版本的代码生成器差不多。

但是功能还不够。
所以我们要说接下来的事情了

 

# 路线图
 - 生成ReadMe手册
- 完善基础设施层的代码
- 完善bug
- 针对视图层增加代码段。

另外欢迎到：https://github.com/52ABP/52ABP.CodeGenerator
欢迎 Star ，然后提出您的想法和意见。

# 现在的成绩
目前 版本还是1.0 后续做更多的迭代。请大家耐心等待。

意外的小惊喜就是今天居然上了最常用榜单有点意外。难道大家都去过年了吗？
![image.png](http://upload-images.jianshu.io/upload_images/1979022-a22cd2db19e701e4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 交流QQ群：104390185



最后祝大家：
大家新年快乐。
##  -*About Me-*

![image](http://upload-images.jianshu.io/upload_images/1979022-9e2bbb5c0bca57f2?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)




![image](http://upload-images.jianshu.io/upload_images/1979022-bd2643389761d9ef?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



