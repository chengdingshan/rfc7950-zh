# 17. 安全考虑

本文档定义了一种用于编写和阅读管理信息描述的语言。语言本身对互联网没有安全影响。

基本`NETCONF`协议​​的相关考虑也是相关的（参见[[RFC6241](https://tools.ietf.org/html/rfc6241)][第9节](https://tools.ietf.org/html/rfc6241#section-9)）。

在`YANG`中建模的数据可能包含敏感信息。 `YANG`中定义的`RPC`或通知可能会传输敏感信息。

安全问题与`YANG`建模数据的使用有关。这些问题应该在描述数据模型的文件中进行处理，并且用来处理数据的接口文件，例如`NETCONF`文件。

以`YANG`为模型的数据依赖于：

- 用于发送敏感信息的传输基础设施的安全性。

- 存储或释放这种敏感信息的应用程序的安全性。

- 适当的身份验证和访问控制机制来限制敏感数据的使用。

`YANG`解析器对于格式错误的文档需要很强大。从未知或不可信的来源读取格式错误的文件可能导致攻击者获得运行`YANG`解析器的用户的权限。在极端的情况下，整个机器可能会受到影响。
