---
title: 验证与 Lync 联机客户的通信
TOCTitle: 验证与 Lync 联机客户的通信
ms:assetid: c8287b15-e1bb-4b26-8354-0ec90b2fcfe7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh202189(v=OCS.15)
ms:contentKeyID: 49314223
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 验证与 Lync 联机客户的通信

 

_**上一次修改主题：** 2016-12-08_

若要使组织中的 Lync 用户可与 Microsoft Lync Online 2010 客户的用户通信，您必须完成以下步骤：

  - 满足所有先决条件。这包括部署内部和边缘服务器，为组织实现联盟支持以及设置用户帐户。有关详细信息，请参阅[与 Lync 联机客户联盟的先决条件](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)。

  - 配置内部部署中的域访问支持。这包括创建主机提供程序条目以及配置部署以允许 Lync Online 客户域的访问。有关详细信息，请参阅[为 Lync Online 域配置联盟支持](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)。

  - 将用户帐户配置为支持联盟。有关详细信息，请参阅[为与 Lync Online 客户的联盟配置用户访问](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)。

您完成了上述所有步骤并且 Lync Online 2010 客户的管理员也完成了支持您组织进行联盟的所有在线服务配置后，通过测试组织内部用户与 Lync Online 客户的用户之间的通信来验证通信。如果通信不成功，可以使用边缘服务器上的日志记录工具来捕获日志和跟踪文件，从而解决问题。有关使用日志记录工具的详细信息，请参阅操作文档中的[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。有关日志记录工具的详细信息，请参阅 TechNet 库中的 Lync Server 2010 日志记录工具文档，网址为 [http://go.microsoft.com/fwlink/?linkid=199265\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=199265%26clcid=0x804)。

