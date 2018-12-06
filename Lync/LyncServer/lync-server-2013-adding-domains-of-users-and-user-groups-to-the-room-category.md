---
title: Lync Server 2013：将用户和用户组的域添加到聊天室类别
TOCTitle: 将用户和用户组的域添加到聊天室类别
ms:assetid: ee03f2cf-1c84-41c4-b524-d0729be33b8c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ215884(v=OCS.15)
ms:contentKeyID: 49314654
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中将用户和用户组的域添加到聊天室类别

 

_**上一次修改主题：** 2014-02-07_

要向聊天室添加较大的用户组，请参阅部署文档中的[在 Lync Server 2013 中配置类别](lync-server-2013-configure-categories.md)和[管理类别](manage-categories.md)。例如，此命令将 Active Directoryor 中 NorthAmericaUsers OU 中的所有用户添加到 NorthAmerica 聊天室：

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=litwareinc,DC=com"}

此命令将 Finance 通讯组中的所有成员添加到相同的聊天室：

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=litwareinc,DC=com"}

