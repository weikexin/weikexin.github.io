# 源起
云鹤平台（EEPlat）已经有10余年了，应用于多个行业，数百个项目，得到了客户的积极评价。EEPlat的开源版本在Google Code 时代进行了积极的维护，频繁的更新和大量的文档。
但转移到Github后，由于种种原因，一直没有做很好的维护。现在，我们准备把EEPlat发展过程中的一些自己的想法，陆续形成文档，其中规模比较大的，组织成商业友好协议的开源项目。
EEPlat的最核心的技术是可直接执行的模型，在UI方面，我们实现的HMVC的框架也是一个比较大的创新。但是建模阶段一直没有特别好的方式，我们尝试过UML建模，表格式建模，基于FORM建模，均没有达到理想状态。。。直到2016年的下半年我们尝试通过思维导图进行建模，发现还是一个不错的注意。

# 思维导图驱动开发
 
 思维导图驱动开发（MMDD，Mind Map Driven Development）是以思维导图的形式进行组织模型和代码的开发方式。思维导图同时包含模型和实现（代码或配置），是可执行的。思维导图可以包含多个平台的不同实现。为了让思维导图更好得支持开发，我们做如下约定，一个典型的MMDD工程有两层
	 
	 * 第一层，工程主题，包含的概念：
	  
		* 工程 需要开发的工程名称或项目名称。
		* 模块  工程的业务模块，根据需要而进行的分类。
		* 业务对象  根据OO思想对真实业务的软件抽象。
	![MMDD First Layer](https://weikexin.github.io/images/MMDD1.jpg)
	 
	 * 第二层业务对象主题 ，包含的概念：

		* 业务对象 从第一层超链接进入的第二层，是第二层导图的主题。
		* 属性  OO的概念，表达的是业务对象的特征。
		* 服务（方法）  OO的概念表达的业务对象的行为。在MMDD中，每个公有方法都有一个独立的URL供外部访问。
		* 服务分类，推荐安装RESTFul的GET PUT POST DELETE 进行分类
		* 实现  具体的实现，可以是代码实现或是配置实现，具体实现代码或配置是通过超链接引入。
	![MMDD Second Layer](https://weikexin.github.io/images/MMDD2.jpg)

 
由于这些约定，这样的思维导图和概念图（Concept mapping）更接近。 
 
# 思维导图驱动测试

思维导图驱动测试（MMDT，Mind Map Driven TEST）是在MMDD基础上进行的测试方法，把导图中的实现部分换成测试用例。当进行测试时，未实现测试用例、测试通过、测试失败，在思维导图上都有不同的颜色表示。无论测试覆盖率，还是测试通过率，都可以被直观得表达出来。

# MMDD在EEPlat中的实现
    
最初MMDD是作为EEPlat建模的SHELL出现的，EEPlat在MMDD应用中有天然的优势，EEPlat是模型驱动的，是通过配置描述业务而非代码，用MMDD描述EEPlat非常清晰简单。


