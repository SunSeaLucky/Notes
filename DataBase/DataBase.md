# DataBase Notes

这篇笔记只有简洁的概念，只需要记住一个原则：$MFC$ ( Memorize the Fucking Concept )

## 1 绪论

$OLTP$ ：联机事务分析

$OLAP$ ：联机分析处理

**数据**：描述事物的符号记录

**数据库**：数据库是长期储存在计算机内、有组织、可共享的大量数据的集合。

**数据库管理系统**：数据库管理系统是位于用户与操作系统之间的一层数据管理软件。

**数据库系统**：由数据库、数据库管理系统（及其应用开发工具）、应用程序和数据库管理员组成的存储、管理、处理和维护数据的系统。

**数据库发展过程**：人工管理 -> 文件系统 -> 数据库系统

**数据模型**：对现实世界的数据特征抽象，主要两大类：概念模型一类、逻辑模型和物理模型一类。

**数据模型组成三要素**：数据结构、数据操作、数据的完整性约束条件

**概念模型**：按用户的观点来对数据和信息建模。

**逻辑模型**：
>
>**包括以下模型**
>
>层次模型：倒立的树
>
>
>网状模型
>
>
>关系模型：（重要）不可表中有表
>

**模式**：是数据库中全体数据的逻辑结构和特征的描述，是所有用户的公共数据视图。

**外模式**：数据库用户（包括应用程序员和最终用户）能够看见和使用的局部数据的逻辑结构和特征的描述，是数据库用户的数据视图，是与某一应用有关的数据的逻辑表示。如视图。

**内模式**：**一个数据库只有一个内模式**。它是数据物理结构和存储方式的描述，是数据在数据库内部的组织方式。

**外模式/模式映像**：当模式改变时(例如增加新的关系、新的属性、改变属性的数据类型等)，由数据库管理员对各个外模式/模式的映像作相应改变，可以使外模式保持不变。应用程序是依据数据的外模式编写的，从而应用程序不必修改，保证了数据与程序的逻辑独立性，简称**数据的逻辑独立性**。

**模式/内模式映像**：当数据库的存储结构改变时（例如选用了另一种存储结构），由数据库管理员对模式/内模式映像作相应改变，可以使模式保持不变，从而应用程序也不必改变。保证了数据与程序的物理独立性，简称**数据的物理独立性**。

## 2 关系数据库

**候选码**：关系中的某一属性组能唯一地标识一个元组，而其子集不能，称该属性组为候选码。

**主码**：多个候选码随便选一个。

**主属性**：候选码中的属性。

关系的三种类型：基本关系，查询表，视图表

基本关系的性质：列是同质的、每列是一个属性、列的顺序无所谓、列不可重、列的顺序无所谓、分量（列）必须取原子值

**关系模式**：$R(U, D, DOM, F)$

实体完整性：实体完整性规则若属性（指一个或一组属性）A是基本关系R的主属性，则A不能取空值。所谓空值就是“不知道”或“不存在”或“无意义”的值。

**参照完整性**：

设F是基本关系R的一个或一组属性，但不是关系R的码，K是基本关系S的主码。如果F与K相对应，则称F是R的外码，并称基本关系R为**参照关系**，基本关系S为被**参照关系或目标关系**。

若属性（或属性组）F是基本关系R的外码，它与基本关系S的主码K相对应(基本关系R和S不一定是不同的关系)，则对于R中每个元组在F上的值必须：

- 或者取空值(F的每个属性值均为空值)
- 或者等于S中某个元组的主码值

**用户定义的完整性**：用户定义的完整性就是针对某一具体关系数据库的约束条件，它反映某一具体应用所涉及的数据必须满足的语义要求。

## 3 关系数据库标准语言SQL

## 4 数据库安全性

数据库安全性控制的常用方法：

1. 用户身份鉴别
2. 存取控制

>**提示**
>
>存取控制分为两种：
>
>自主存取控制
>
>强制存取控制

3. 视图机制
4. 审计
5. 数据加密

## 5 数据库完整性

数据库完整性与数据库安全性的区别：
> 数据库的完整性是为了防止数据库中不符合语义的数据，防止错误信息的输入和输出。
>
> 数据库的安全性是为了保护数据库防止恶意的破坏和非法的存取。

## 6 关系数据理论

## 7 数据库设计

数据库设计流程：需求分析 -> 概念设计 -> 逻辑设计 -> 物理设计 -> 数据库实施 -> 数据库运行和维护

需求分析：
> 任务
>
> 方法
>
> 数据字典

概念结构设计：
> 概念模型
>
> E - R模型

各个子系统的 E-R 图之间的冲突
> 属性冲突（同一属性数据取的数据类型不同）
>
> 命名冲突（同名异义，异名同义）
>
> 结构冲突（对同一个实体的抽象等级不同）

逻辑结构设计：
> E - R图向关系模型的转换
>
> 数据模型的优化
>
> 设计用户子模式

物理结构设计：
> 物理设计的内容和方法
>
> 关系模式存取方法选择
>
> 确定数据库的存储结构
>
> 评价物理结构

数据库的实施和维护：
> 数据的载入和应用程序调试
>
> 数据库的试运行
>
> 数据库的运行和维护

## 8 数据库编程

## 9 关系查询处理和查询优化

## 10 数据库恢复技术

- 系统故障

造成数据状态不一致的原因：
> a. 未完成的事务的结果可能已经送入物理数据库，所有运行事物都非正常终止
>
> b. 一些已完成的事务可能有一部分甚至全部留在缓冲区，尚未写回到磁盘上的物理数据库中

恢复步骤：
> a. 强行撤销未完成事务
>
> b. 重做已提交的事务

## 11 并发控制

排他锁（X 锁，写锁）：若事务 T 对数据对象 A 加上 S 锁，则事务 T 可以读取和修改 A 。

共享锁（S 锁，读锁）：若事务 T 对数据对象 A 加上 S 锁，则事务 T 可以读 A 但不能修改 A。

一级封锁协议：
