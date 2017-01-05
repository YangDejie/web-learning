<h1>第**14**章 **XML**简介</h1>

# 14．1 XML语法与文档结构 ★

- XML是一种元标记语言
- 它与HTML等标记语言的区别:


- - XML提供了创建标记语言的准则。


- - - 作为元标记语言，XML不包含标记。
    - 使用XML设计一种标记语言时，必须要定义一个标记集合，标记集合中每个标记内容的意义要明确规定。


- - 使用XML的标记语言编写的文档称为XML文档。



1)示例：first.xml

```

<?xml version=”1.0”>
<cars>
	<producer> Honda </producer>
	<picture pic_name=”spring.jpg”/>
	<year> 2008 </year>
	<color> red </color>
</cars>
```

2)．XML声明

- XML文档以声明开始，在上面例子中，文档的声明部分就是文档的第一行。

​		` <?xml version=”1.0” encoding=”UTF-8”>`

- 一个XML文档可以包含三种不同类型的属性：版本、编码和独立。


- - 编码属性（encoding）指定XML文档使用的语言，一般在编码属性中指定XML文档所使用语言的字符集。
  - 独立属性（standalone）指定是否需要文档类型定义(DTD)，关于DTD的概念将会在后面介绍。

3)．XML的标记与属性

- 与HTML类似，也将标记及它们包含的信息叫做元素。
- 与HMTL不同的是，XML中所有的元素必须有开始标记和结束标记，否则格式就将出错。
- XML是一种元标记语言，


- - 因此XML本身并不定义任何的元素。
  - 标记及属性是由用户自己定义的，通常用来描述文档中的数据。
  - 在上例中，`<producer>`、`<color`>、`<year>`等标记都是用户自定义的。
  - 与HTML一样，标记的属性值必须是有引号的。


- 需要注意的是，XML中的标记中“<”与标记内容之间不能有空格，而“>”前是允许有空格的。
- XML中的注释语句与HTML的完全相同。

4)．XML的格式要求

①XML对大小写敏感

②XML标记必须有结束标记

- - 在XML中，通常单标记是不允许出现的。
  - 在上面的例子中可以看到一个特殊的标记`<picture>`，这个标记是没有结束标记的。在XML中，这样的标记叫做空标记。
  - 与HTML中单标记不同，XML中的空标记必须在”>”前加”/”表示标记结束。
  - `<picture pic_name=”spring.jpg”/>`

③XML文档必须有根标记

- 在HTML中，一个HTML文档会用<html>和</html>标记文档的开始和结束。在XML中同样要求用一对跟标记来标志文档的开始与结束。需要注意的是，XML声明部分并不是根标记的组成部分。在上面例子中，根标记是<car>和</car>。从该例子中可以看到，根标记必须出现在XML声明部分后，其他所有标记必须嵌套在根标记中。

④XML标记必须正确嵌套

- `<a><b><c>嵌套的例子</c></b></a>`
- `<a><b><c>嵌套的例子</a></b></c>`就会出现错误。

5)．XML的特殊字符

- 在XML中有5种字符属于特殊字符


- - 通过实体引用


- - - 左尖括号“<”    &lt
    - 右尖括号“>”   &gt
    - 与符号“&” &amp
    - 单引号“’”  &apos
    - 双引号“””  &quot


- - 2008年将在中国上市&lt;新款Focus三厢&gt;
  - 2008年将在中国上市<新款Focus三厢>


- 有一些经常用在数学公式中的特殊符号是无法从键盘输入到文档中的，比如希腊字母。
- 在XML中，解决这一问题的手段是使用字符引用。
- 通常，这些字符会在Unicode字符集中找到，需要记住这些特殊字符在Unicode字符集中的编号，然后进行引用。
- 引用的格式为“&#+编码”，


- - 比如“&#945”会被解析为希腊字母“α”。


- 如果编码采用十六进制，则引用格式为“&#x+编码”。
- ​

```
<special_char>

	α+ β=100

</special_char>

			将被解析为：α+β=100。 

```

# 14．2 文档类型定义 ★

对XML的数据结构进行限制有两种途径：

- 使用文档类型定义(Document Type Definition，DTD)
- XML架构(XML Schema)。

1)DTD

- DTD是一个一系列关于数据结构规则的集合，这些规则被称为声明。声明规定了一个将出现在文档中的标记的集合以及这些标记如何和在哪里出现。一个DTD可以为一个XML文档服务，也可以被一系列XML文档使用，因此它可以为团队开发提供良好的开发规范。
- DTD分为


- - 内嵌DTD


- - - 位于由它来描述语法规则的XML文档中，因此它只能约束它所在的XML文档；
    - <!DOCTYPE 根标记名称 [DTD内容]>


- - 外部DTD两种。


- - - 被单独存储为一个文件，因此可以为一组XML文档服务。

- 需要注意的是，浏览器的XML解析器只检查XML文件是否规范。当用浏览器打开一个被DTD约束的XML文档时，解析器只检查XML文档所关联的DTD文件是否有语法错误，并不检查XML文件是否遵守该DTD规定的约束条件。

2)．DTD中的元素

DTD中的元素用来约束关联XML文档中的标记。元素的声明格式为：

​		<!ELEMENT 标记名 标记的约束规则>

①约束标记中只包含文本数据

- 标记中只包含文本数据，实际上就说明了在标记中不能包含子标记。
- 其声明格式如下：

​		<!ELEMENT 标记名  (#PCDATA)>

```
<!ELEMENT SANTANA  (#PCDATA)>：

下面的SANTANA标记是符合约束条件的
<SANTANA> Santana is the most famous car in China </SANTANA> 
而下面的标记则是不符合条件的：
< SANTANA >
	<produce_place> 
		Shanghai 
	</produce_place>
	Santana is the most famous car in China 
</SANTANA>
```

②约束标记中的子标记

<!ELEMENT 标记名  (子标记列表)>

- 子标记列表可以约束标记的子标记有哪些、它们的排列顺序如何。而规定一个子标记重复出现的次数，可以通过为子标记的规范说明添加一个修饰符来实现。这些修饰符包括：


- - +：一次或多次重复
  - *：零次或多次重复
  - ?：零次或一次重复


- dtd_sample1.dtd

<!ELEMENT 汽车销售信息  (汽车种类*)>

<!ELEMENT 汽车种类  (名称，型号，(微型车|中级车|商务车)，价格，(优惠折扣))>

<!ELEMENT 微型车  (#PCDATA)>

<!ELEMENT 中级车  (#PCDATA)>

<!ELEMENT 商务车  (#PCDATA)>

<!ELEMENT 优惠折扣  (#PCDATA)>

```
xml_sample1.xml
<?xml version=”1.0” encoding=”UTF-8”>
<!DOCTYPE 汽车销售信息 SYSTEM  “dtd_sample1.dtd”>
<汽车销售信息>
	<汽车种类>
		<名称> 宝来 </名称>
		<型号> Bora 1.8T </型号>
		<中级车> 被誉为驾驶者之车 </中级车>
		<价格> RMB 18万 </价格>
		<优惠折扣> 9折 </优惠折扣>
	</汽车种类>
	<汽车种类>
		<名称> 途安 </名称>
		<型号> Turan 2.0 </型号>
		<商务车> 兼顾家用与商用 </商务车>
		<价格> RMB 17.5万 </价格>
		<优惠折扣> 92折 </优惠折扣>
	</汽车种类>
</汽车销售信息> 
```

③EMPTY与ANY

- 如果约束一个标记是空标记，或者是只包含空字符的非空标记，可以将标记的约束规则设置为EMPTY。

<!ELEMENT 召回条件 EMPTY>

- 而如果标记可以在字面上包含任何内容，可以将标记的约束规则设置为ANY。比如下面的两个例子：

<!ELEMENT 详细配置 ANY>

3)．DTD中的属性

- DTD中的属性是标记的属性，它可以为标记添加附加信息。
- 在DTD中，属性的声明与标记的声明是分开的。一个属性的声明必须包含下面的内容：属性对应的标记名称、属性名称和属性类型。属性是允许包含一个默认值的。
- 属性的声明格式如下：

<!ATTLIST 标记名称 属性名称 属性类型 [默认值]>

<!ATTLIST 标记名称 	

属性名称1 属性类型 [默认值1]属性名称2 属性类型 [默认值2]

…>

属性的默认值

- 具体值:若没有规定任何值，则使用该默认值
- \#FIXED 具体值: 所有该属性元素都使用这个值，不能改变
- \#IMPLIED:未给出默认值，元素的属性值可以没有(暗示）
- \#REQUIRED：未给出默认值，但元素的实例必须有属性值

属性的类型

- CDATA任意字符串，如果包含特殊字符，需要字符引用
- Enumerated枚举类型
- NMTOKEN由字母、数字、下划线和连字符构成的字符串
- NMTOKENS与NMTOKEN类似，但字符串间可以使用空格做间隔
- ID属性值有专用性。可以由字母、数字、下划线、连字符和点构成，但必须以字母或下划线开头
- IDREF用来判断标记之间的关联。通过定义IDREF类型，可以找到某个ID类型标记的后代标记
- IDREFS与IDREF类似，但可以约束某个属性的属性值是若干个其他ID属性的属性值的组合


- dtd_sample2.dtd

<!ELEMENT 客户信息 （姓名*）>

<!ELEMENT 姓名 （#PCDATA）>

<!ATTLIST 姓名 	电话 CDATA  #REQUIRED

联系地址 CDATA  #IMPLIED>

```
xml_sample2.xml
<?xml version=”1.0”>
<!DOCTYPE 客户信息 SYSTEM “dtd_sample2.dtd”>
<客户信息>
<姓名 电话=”139011000000” 联系地址=”山东大学”>
王刚
</姓名>
<姓名 电话=”13001001234” >
李强
</姓名>
</客户信息>
```

4)．DTD中的实体

- 可以在DTD中定义实体，从而在与DTD关联的XML文档中可以引用它。
- DTD中的实体分为两类：


- - 普通实体


- - - 普通实体在DTD中定义，与DTD关联的XML文档通过实体引用来使用实体，解析器在解析标记中的数据时，使用实体的内容来替换实体引用；


- - 参数实体。


- - - 参数实体也在DTD中定义，但仅在标记声明中才能使用。

- 在DTD中声明实体的格式如下：

​		<!ENTITY [%] 实体名 “实体值”>

- - 如果实体声明中使用了%选项，表示这个实体是参数实体，否则就是普通实体。 dtd_sample3.dtd

- <!ENTITY BMWX5 “BMWX5是德国宝马公司生产的顶级SUV”>

- <!ENTITY CAYENNE “CAYENNE是保时捷公司生产的顶级SUV”>

- <!ELEMENT 欢迎光临本公司 ANY>

- <!ELEMENT 宝马产品 ANY>

- <!ELEMENT 保时捷产品 ANY>

- ```
  xml_sample3.xml
  <?xml version=”1.0”>
  <!DOCTYPE 欢迎光临本公司 SYSTEM “dtd_sample3.dtd”>
  <欢迎光临本公司>
  	<宝马产品>
  		本周特别推荐产品是&BMWX5
  	</宝马产品>
  	<保时捷产品>
  		本周特别推荐产品是&CAYENNE
  	</保时捷产品>
  </欢迎光临本公司>
  ```

# 14.       3  命名空间

- 由于XML允许自定义标记，因此可能会使得不同的XML文档或同一个XML文档中出现名字相同的标记，这显然会带来混乱，因为处理XML文档的软件系统必须能无二义地识别XML文档中的标记。
- 为了解决这一问题，就需要在XML中使用命名空间。
- 命名空间的目的是有效地区分名字相同的标记，也就是说，当两个标记的名字相同时，可以通过它们所在的命名空间不同来进行区分。
- W3C为命名空间定义了一个标准，详细信息可以查阅[http://www.w3.org/TR/REC-xml-names](http://www.w3.org/TR/REC-xml-names)。

1)．命名空间的声明格式

- 命名空间的声明格式如下：

    <标记名 xmlns[:前缀] = 命名空间名>

- 其中的方括号表示是可选项。
- 如果在定义命名空间名时定义了前缀，那么每次使用该标记及其子标记时，都必须把前缀放在标记名前面，表明此标记是属于这个命名空间的。
- 如果不加前缀，说明此命名空间是默认命名空间，一个标记最多只能有一个默认命名空间。
- 如果两个标记同名，只要它们所在的命名空间不同，就被视为两个不同的标记。
- 对于命名空间的名称来说，如果两个命名空间名字相同，即使它们的前缀不同，也被视为相同的命名空间；
- 而如果两个命名空间名字不同，即使它们的前缀相同，也被视为不同的命名空间。
- 当然作为良好的代码规范来说，在XML文档中一般不会使用相同的前缀名来表示不同的命名空间，也一般不会为同一个命名空间取两个不同的名字。

```
<BMW xmlns:sample = ”BMWDocument”>
宝马公司产品介绍
</BMW>
这个例子中定义了一个名为BMW的标记，其前缀名为sample，那么将来如果这个标记及其子标记隶属于这个命名空间，那么必须通过这个前缀来引用此命名空间 
<sample:BMW5Series>
宝马公司入门级商务轿车系列产品
</sample:BMW5Series>
<BMW xmlns = “BMWNameSpace1”
	       xmlns:ns2=”BMWNameSpace2”>
	<BMW5Series>
		<name> 宝马5系车型 </name>
		<price> $30,000-50,0000</price>
	</BMW5Sereis>
	<BMW7Series>
		<ns2:name> 宝马7系车型 </ns2:name>
		<ns2:price> $55,000-80,0000</ns2:price>
	</BMW7Sereis>
</BMW>
```

2)．命名空间的作用域

- 一个标记如果使用了命名空间声明，那么该命名空间的作用域就是该标记及其所有的子孙标记。


- - 这个标记及其子孙标记在使用时如果要隶属于这个命名空间，需要通过前缀来引用此命名空间。


- 但即使在父标记中声明了一个命名空间，在它的子孙标记中同样可以重新声明同名的命名空间，虽然这么做不是一种好习惯。

```
<BMW xmlns:ns = “BMWNameSpace1”>

	宝马公司产品介绍

	<BMW5Series xmlns:ns = “BMWNameSpace2”>

		宝马5系介绍

		<ns:BMW520>

			宝马520介绍

		</ns:BMW520>

	</ BMW5Series >

</ BMW> 

```

3)．命名空间名

- 命名空间的名字通常有三种形式：


- - Internet主机名
  - Email地址
  - 一个文件的绝对路径


- 这三种形式统称为统一资源标示符（Uniform Resource Identifier，URI）。大多数情况下，URI会以URL的形式出现。
- 需要特别注意的是，在XML中，一个URI不必是有效的，尤其是以URL做URI的时候。


- - 比如[www.aaab.ccn](http://www.aaab.ccn/)不是一个存在的URL，但是在XML中可以将它作为URI存在。也就是说，XML不负责判断URI是否有效，只要格式上存在URI即可。 

4)．DTD与命名空间

- 在DTD中，命名空间的名字被看成一种特殊的属性, 使用ATTLIST来声明，
- 格式为：

<!ATTLIST 标记名 xmlns[:前缀] 命名空间名类型 命名空间名>

- - 一般将命名空间名类型固定为CDATA类型，命名空间名固定为#FIXED加命名空间名。
  - <!ALLIST BMW xmlns CDATA #FIXED “www.sdu.edu.cn”>
  - <!ALLIST ns:BMW xmlns:ns CDATA #FIXED “www.sdu.edu.cn”>

# 14．4 XML架构 ★

- 使用DTD来对XML文档的数据组织进行限制是有缺陷的。


- - DTD对XML文档中数据的类型不做判断，它会认为XML中所有的数据都是文本类型，显然，如果数据是数值、日期等类型的话，DTD无法完成对数据格式的限制。
  - DTD的语法与XML无关，因此XML解析器不能分析它们。以上的缺陷会使得DTD的使用受到一些限制，当需要XML中的数据类型进行约束的时候，DTD显然不能胜任。

1)．什么是XML架构

- 一个架构类似于一个类，一个符合架构定义结构的XML文档类似于这个架构类的一个对象。或者说，符合一个特定架构的XML文档都是这个架构的实例。
- XML架构（XML Schema）的提出是为了弥补以上所说的DTD的缺陷。目前，XML架构是最可能的DTD替代者。
- XML架构的问题在于它的标准过于复杂，而且支持它的解析器目前数量也比较少，本节所介绍的也只是它的一些基本概念和特征。
- 如果对XML文档的约束只限于文档中的标记和属性结构，而不涉及数据的具体内容的话，还是推荐使用DTD对XML文档进行约束。

2)．架构中的标记

- XML架构是扩展名为.xsd的一个文本文件，这个文本文件需要使用XML语法来编写。
- 架构本身使用一个来自叫做源架构的命名空间的一个词汇表写成，这个源架构就是[http://www.w3c.org/2001/XMLSchema](http://www.w3c.org/2001/XMLSchema)。每个架构都需要在第一行就指定这个命名空间，其格式为：

      `<xsd:schema xmlns:xsd = “[http://www.w3c.org/2001/XMLSchema](http://www.w3c.org/2001/XMLSchema)”>`

- - 如果要从源架构中引入名字，那么这个名字的前缀必然是xsd。
  - 一个架构文件的根标记就是schema。


- 架构的主要目的是约束相关联的XML文档中的标记，为了实现这一目的，可以使用源架构中的element标记。通常情况下，将element标记作为schema的子标记，在这种情况下，将这个element标记称为全局元素。这样，就可以使用element标记来约束关联XML文档中任意的子标记，不论这个子标记在哪个级别。
- 在架构中，还可以使用来自源架构的其他标记，这些标记主要是用来对XML文档中的数据进行约束。



3)．架构中的数据类型

- XML架构中有两类数据类型：简单数据类型和复杂数据类型。


- - 简单数据类型的内容只包含文本数据，而且关联的XML文档中的标记不允许有子标记，也不允许有属性。


- - - 虽然简单类型只包含文本数据，但实际上XML架构定义了44种基本数据类型，在后面会给出这44种基本数据类型中常用的一些。


- - 复杂数据类型是允许有属性和子标记的标记。


- 简单类型和复杂类型可以有类型名，也可以没有。如果一个数据类型没有类型名，那么它在关联XML文档中的作用域仅限于这个类型声明所在的标记。
- XML架构中数据类型的声明可以是全局的，也可以是局部的。

4)．简单数据类型

- 架构中定义简单数据类型的格式为：
- `<xsd:element name=”标记名” type=”简单数据类型名” [default=”默认值”] [fixed=”常量值”]/>`


- - 这里面的的element、name和type都来自源架构。
  - `<xsd:element name=”carName” type=”xsd:string”/>`
  - `<xsd:element name=”carName” type=”xsd:string” default=”BMWX5”/>`
  - `<xsd:element name=”carName” type=”xsd:string” fixed=”BMWX5”/>`


- 在XML架构中，用户还能对简单数据类型做简单的衍生。 

```
<xsd:simpleType name=”Hanname”>

	<xsd:restriction base=”xsd:string”>

		<xsd:maxLenth value=”8”/>

	</xsd:restriction>

</xsd:simpleType>

```

5)复杂的数据类型

```
schema_sample1.xsd
<xsd:schema xmlns:xsd = “http://www.w3c.org/2001/XMLSchema”>
	<xsd:element name=”汽车介绍”>
		<xsd:complexType>
			<xsd:sequence>
				<xsd:element name=”花冠”>
					<xsd:complexType>
						<xsd:sequence>
						      <xsd:element name=”价格” type=”float”>
						      <xsd:element name=”排量” type=”float”>
						</xsd:sequence>
					</xsd:complexType>
				</xsd:element>
				<xsd:element name=”宝来”>
					<xsd:complexType>
						<xsd:sequence>
						       <xsd:element name=”价格” type=”float”>
						       <xsd:element ref=”排量”>
						</xsd:sequence>
					</xsd:complexType>
				</xsd:element>
				<xsd:element name=”排量” type=”string”/>
			</xsd:sequence>
		</xsd:complexType>
	</xsd:element>
</xsd:schema>
```

```
	xml_sample4.xml
	<?xml version=”1.0”>
		<汽车介绍>
			<花冠>
				<价格>11.48</价格>
				<排量>1.6</排量>
			</花冠>
			<宝来>
				<价格>16.58</价格>
				<排量>1.8T</排量>
			</宝来>
		</汽车介绍>
```

6)．架构的验证	

- 在使用了XML架构对关联的XML文档做了一系列的约束后，如何去检查这些文档是否满足了这些约束呢？这一类的工作被称为XML架构的验证
- 工具来完成对XML的支持，其中的一部分针对XML架构验证的工具可以帮助我们自动实现对XML文档的验证。


- - 这些工具包括Altova XMLSpy、Xerces-C、XML Schema Validator等。	









# 14．5 XML解析器 ★

- 1)．XML解析器的用途


- - 检查XML文档是否符合基本语法；
  - 将DTD和XML架构中指定的默认值传递到XML文档中；
  - 替换所有XML文档中对实体的引用；
  - 如果XML文档关联了DTD或XML架构，那么可能要检查XML文档结构的合法性。


- XML解析器的种类有很多。在本节中，主要介绍基于DOM的解析器和基于事件的解析器。

2)．DOM方式

- DOM（Document Object Model，文档对象模型）是W3C制定的一套规范标准，也就是规定了解析文件的接口。


- - 各种语言可以按照DOM规范去实现这些接口，给出解析文件的解析器。
  - 如果使用某种语言使用DOM规范实现了这些接口，并给出实现这些接口的类的集合，那么把这个过程称为语言绑定。
  - DOM规范中所包含的文件范围很广，包括XML文档和HTML文档。


- 在使用基于DOM方式对XML文档进行解析的过程中，解析的数据存储在内存中。这些数据是以树的形式进行存储的，当文档解析完成后，整个文档的DOM表示就存放在了内存中，并可以以各种树的遍历方式进行访问。

3)．SAX方式

- SAX（Simple API for XML）提供了解析XML文档的API。
- 基于SAX的解析器将XML文档从头到尾扫描一遍，在扫描过程中，每当遇到一个语法结构（比如标记、属性、文本、标记的结束等），就会调用一个事件处理程序向事件处理器发送事件信息，事件处理器会处理所发现的数据。这些事件处理器的接口描述都是在SAX的API中定义的。
- DOM方式的优点在于：


- - 如果文档的某个部分被多次重复，那么使用DOM方式仅需处理一次，而SAX方式则需处理多次；
  - 如果解析器需要对文档做一些调整，那么使用DOM方式要方便得多；
  - DOM方式可以随机访问文档的某个部分，而SAX方式必须从文档的开头进行扫描；因为DOM方式的解析器在处理前可以看到整个文档，所以可以根据DTD或XML架构的规定来避免某些无效的操作。


- SAX方式的优势在于，


- - 因为DOM方式的整个扫描结果都存储在内存中，因此如果文档如果特别大的话，使用DOM方式会占用大量的内存空间，如果文档足够大，在内存中存储它的树形处理结构甚至是不可能的。而SAX方式则会轻松获取这些标记的文本数据，
  - SAX方式的另一个优势是它的处理速度比DOM方式要快。



# 19.5 文件操作：XML解析★

- 基于事件的解析器
- - - Expat 解析器，。

- 基于树的解析器


- - DOM解析器
  - impleXML解析器

```
<?xml version="1.0" encoding="ISO-8859-1"?>
<note>
<to>George</to>
<from>John</from>
<heading>Reminder</heading>
<body>Don't forget the meeting!</body>
</note>
```

- 通过 xml_parser_create() 函数初始化 XML 解析器。
- 创建配合不同事件处理程序的的函数，


- - 一般设计三个函数分别处理XML标签的开始，结束和元素间的字符。


- 添加 xml_set_element_handler() 函数来定义，


- - 当解析器遇到开始和结束标签时执行哪个函数。


- 添加 xml_set_character_data_handler() 函数来定义，


- - 当解析器遇到标签之间的字符数据时执行哪个函数。


- 通过 xml_parse() 函数来解析文件 
- 调用 xml_parser_free() 函数来释放分配给 xml_parser_create() 函数的内存

```
<?php
$parser=xml_parser_create();//初始化 XML 解析器
function start($parser,$element_name,$element_attrs)
  		{
 		   switch($element_name)
    		  {case "NOTE":echo "-- Note --<br />";
				break; 
   		   case "TO":echo "To: ";break; 
   		   case "FROM": echo "From: ";break; 
    		   case "HEADING": echo "Heading: ";break; 
   		   case "BODY":echo "Message: ";
    		   }
  		}
  		
 function stop($parser,$element_name)
  		{echo "<br />";}
function char($parser,$data)
  		{echo $data;}
xml_set_element_handler($parser,"start","stop");
xml_set_character_data_handler($parser,"char");
$fp=fopen("test.xml","r");
while ($data=fread($fp,4096))
  		{xml_parse($parser,$data,feof($fp));}
xml_parser_free($parser);
？>
```

- DOM解析器用DOMDocument类处理XML文件


- - saveXML() 是DOMDocument类的方法


- - - 把内部 XML 文档放入一个字符串

```
<?php
$xmlDoc = new DOMDocument();
$xmlDoc->load("test.xml"); // 加载Xml文件
print $xmlDoc->saveXML();
?>
```

```
<?php
$xmlDoc = new DOMDocument();
$xmlDoc->load("test.xml");
$x = $xmlDoc->documentElement;
foreach ($x->childNodes AS $item)
    {
    Print $item->nodeName."=". 
            $item->nodeValue."<br />";
    }
?>
```

```
PHP 5 中的新特性
SimpleXML 函数

<?php
$xml = simplexml_load_file("test.xml");
echo $xml->getName() . "<br />";
foreach($xml->children() as $child)
	{
  	echo $child->getName() . ": " . $child . "<br />";
  	}
?>
```

# 19.5 文件操作：文件

```
<?php
session_start();
if(($fp=fopen("counter.txt","r"))==false)
	{ 
	echo "打开文件失败!";
	}
else
{ 
$counter=fgets($fp,1024);//读取文件
fclose($fp); 
if(isset($_SESSION['temp']))
{
echo “您是网站的第”.$counter;
. "位访客";}
     
else
{
 $counter++;    
$fp=fopen("counter.txt","w"); fputs($fp,$counter);            fclose($fp);
$_SESSION['temp']=1;
}
}
?>
```

- `<input type="file" name="file1" id="file" /> `
- PHP会将上传的文件作为一个临时文件，保存在临时文件夹中。这个临时文件会在脚本结束时消失。
- 要保存被上传的文件，我们需要把它拷贝到另外的位置。PHP使用move_uploaded_file() 函数将上传的文件移动到新位置。该函数语法如下：


- - *bool move_uploaded_file ( string $filename , string $destination )*


- $_FILES["file"]["name"] - 被上传文件的名称。在上面的例子中，上传文件的名称是file1。
- $_FILES["file"]["type"] - 被上传文件的类型
- $_FILES["file"]["size"] - 被上传文件的大小，以字节计
- $_FILES["file"]["tmp_name"] - 存储在服务器的文件的临时副本的名称
- $_FILES["file"]["error"] - 由文件上传导致的错误代码


- 用户只能上传大小必须小于 20 kb 的gif文件。然后检测"upload"文件夹否已存在此文件，如果不存在，则完成文件的拷贝。

##  补充：XML技术优势★



- 数据重用


- - 用来存储，携带，交换数据的
  - 不是用来显示数据的


- 数据和表示分离


- - 数据的显示样式已从文档中分离出来，而放入相关的样式表文件中。
  - 例子


- 可扩展性
- 半结构化集成数据

```
student.xml
<?xml version="1.0" encoding="GB2312"?>
<?xml-stylesheet type="text/css" href="student.css"?> <student> <name>ZhangSan</name> <sex>女</sex> </student>
```

```
  student.css
student{ display:block; }
name{ display:block; font-size:110%; color:red }
sex{ display:block; text-indent:2em }

```

使用 CSS 格式化 XML 不是常用的方法，更不能代表 XML 文档样式化的未来。
W3C 推荐使用 XSLT。

## 补充：XML 应用领域 ★

- 1、数据交换


- - 应用程序可以共享和解析同一个XML文件
  - 使用XML做数据交换可以使应用程序更具有弹性，


- - - 可以用位置(与普通文件一样)
    - 或用元素名(从[数据库](http://lib.csdn.net/base/14))来存取XML数据。

- 2、Web服务


- 3、内容管理


- - 独立于平台和语言
  - 使用象XSLT这样的语言能够轻易地将XML文件转换成各种格式文件，比如HTML, WML, PDF, flat file, EDI, 等等。
  - XSL 指扩展样式表语言（*E*Xtensible *S*tylesheet *L*anguage）。
  - XSLT 是首选的 XML 样式表语言。
  - XSLT (eXtensible Stylesheet Language Transformations) 远比 CSS 更加完善。
  - 使用 XSLT 的方法之一是在浏览器显示 XML 文件之前，先把它转换为 HTML


- 4、配制


- - 将配制数据标记为XML格式，能使其更具可读性，并能方便地集成到应用系统中去。
  - **XQuery **被设计用来查询 **XML **数据
  - 解释 **XQuery **的最佳方式是：**XQuery **相对于 **XML**，等同于 **SQL **相对于数据库。