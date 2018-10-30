---
title: 删除前端池的 SQL Server 数据库
TOCTitle: 删除前端池的 SQL Server 数据库
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49888453
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除前端池的 SQL Server 数据库

 

_**上一次修改主题：** 2012-10-04_

在删除 Microsoft Lync Server 2010  前端池或重新配置池以使用不同的数据库后，可以删除承载池数据的 SQL Server 数据库。可使用以下过程从 拓扑生成器中删除定义，然后从数据库服务器中删除数据库和日志文件。

## 使用 拓扑生成器删除 SQL Server 数据库

1.  从 Lync Server 2013 前端服务器中，打开 拓扑生成器并下载现有拓扑。

2.  在拓扑生成器中，导航到“共享组件”，然后导航到“SQL Server 存储”，右键单击与所删除或重新配置的前端池相关联的 SQL Server 实例，然后单击“删除”。

3.  发布拓扑，然后检查复制状态。

## 从 SQL Server 中删除用户和应用程序数据库

1.  若要删除 SQL Server 上的数据库，您必须是要从中删除数据库文件的 SQL Server 的 SQL Server sysadmins 组的成员。

2.  打开 Lync Server 命令行管理程序

3.  若要删除池用户存储的数据库，请键入：
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    其中，*\<FQDN\>* 是数据库服务器的完全限定的域名 (FQDN)，*\<instance\>* 是命名数据库实例（如果已定义）。

4.  若要删除池应用程序存储的数据库，请键入：
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    其中，*\<FQDN\>* 是数据库服务器的 FQDN，*\<instance\>* 是命名数据库实例（如果已定义）。

5.  当 **Uninstall-CsDataBase** cmdlet 提示您确认操作时，请阅读信息，然后按 **Y** （或按 Enter 键）继续，或者如果您想要停止该 cmdlet（也就是，在出现错误的情况下），请按 **N** ，然后按 Enter 键。

