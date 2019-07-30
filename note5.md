### 日期的基本操作
- let time = now Date();
- 获取当前客户端（本机电脑）本地的时间
- 这个时间用户是可以自己修改的，所以不能作为重要的参考依据
- 获取的结果不是字符串是对象数据类型的，属于日期对象（或者说是Date这个类的实例对象）typeof time；//=>‘object’
- 标准日期对象中提供了一下属性和方法，供我们操作日期信息
- 1.getFullYear: 获取年
- 2.getMonth: 获取月  结果是0~11代表第一月到十二月
- 3.getDate: 获取日 
- 4.getDay: 获取星期  结果是0~6代表周日到周六
- 5.getHours：获取小时
- 6.getMinutes: 获取分
- 7.getSeconds: 获取秒
- 8.getMilliseconds: 获取毫秒
- 9.getTime: 获取当前日期距离1970/1/1 00:00:00 这个日期之前的毫秒差
- 10.toLocaleDateString: 获取年月日（字符串）
- 11.toLocaleString:获取完成的日期字符串
- now Date()：除了获取本机时间，还可以把一个时间格式字符串转换为标准的时间格式
- 支持的格式 /  - （这种格式在IE不支持）

### DOM及其基础操作
- DOM: document boject model 文档对象模型，提供一些属性和方法供我们操作页面中的元素
- document.getElementByid() 指定在文档中，基于元素的ID或者这个元素对象
- [context].getEementsByTagName() 在指定上下文（容器）中，通过标签名获取一组元素集合
- document.getElementByName() 在整个文档中，通过标签的NAME属性值获取一组元素集合（在IE中只有表单元素的NAME才能识别，所以我们一般只应用于表单元素的处理）
- document.head / document.body / document.documentElement:获取页面中HEAD/BODY/HTML三个元素
- [context].querySelector([selector]) 在指定上下文中，通过选择器获取到指定的元素集合


####   js中的节点和描述节点之间关系的属性
- node:节点（页面中所有的东西都是节点）
- NodeList:(getElementsByBame/querySelector获取的都是节点集合)
- 元素节点（元素标签）
      - nodeType：节点类型(1)
      - nodeName ：大写的标签名
      - nodeValue：null
- 文本节点
      - nodeType：3
      - nodeName ：大写的标签名
      - nodeValue：null
- 注释节点
      - nodeType：8
      - nodeName ：大写的标签名
      - nodeValue：null
- 文档节点 docunent 
      - nodeType：9
      - nodeName ：大写的标签名
      - nodeValue：null
- 描述这些节点之家的属性
    - childNodes : 获取所有的子节点
    - chlidren ： 获取所有元素子节点（子元素标签）
    - firstChild ： 获取第一个子节点
    - lastChild ： 获取最后一个子节点
    - firstChild/lastChild ： 获取第一个和最后一个元素子节点（不兼容IE6~8）
- prviousSibling： 获取上一个哥哥节点
- nextSibling ： 获取下一个弟弟节点
- previousElementSibling / nextElementSibling :获取哥哥和弟弟元素节点（不兼容IE6~8）
### 在JS中动态增删改元素
- createElement 创建元素对象
- createTextNode 创建文本对象
- appendchild 把元素添加到容器的末尾
- nsertBefore  把元素添加到指定容器指定元素的前面
- cloneNode(true / false) 克隆元素或者节点
- renmoveChild 移除容器中的某个元素
- setAttribute / getAttribute / removeAttribute 设置获取移除元素的自定义属性信息（这种方式是把自定义属性放到元素结构上） 

#### GIT版本控制系统
- 版本控制系统：
- 1.记录历史版本信息（记录每一次修改的记录）
- 2.方便团队相互之间协助开发
### 常用的版本控制系统
- CVS / SVN ：集中式版本控制系统
- GIT ： 分布式版本控制系统 
### GIT工作原理
- 1.工作区：我们能看到的，并且用来写代码的区域
- 2.暂存区：临时存储用的 
- 3.历史区：生成历史版本
- （$git add -A(工作区到暂存区) / $git commit -m"(暂存区到历史区) / $git pull origin master(历史区到中央厂库)）
### GIT 的全局配置
- 第一次安装完成git后，我们在全局环境下配置基本信息：我是谁？
- git config -l
- clear :清屏
- $ git config -l 查看配置信息
- $ git config --global -l查看全局配置信息
### 创建仓库完成版本控制
- 创建本地git仓库
- $ giy  init :会生成一个隐藏文件夹“.git”（这个文件夹千万不要删，因为暂存区和历史区还有一些其他的信息都在这里，删了就不是一个完成的git仓库）
- 在本地编写完成代码后，把一些文件提交到暂存区
- 1.$ git add xxx ：把某一个文件或者文件夹提交到缓存区
- 2.$ add ./-A ba ：把所有仓库中所有最新修改的文件都提交到暂存区