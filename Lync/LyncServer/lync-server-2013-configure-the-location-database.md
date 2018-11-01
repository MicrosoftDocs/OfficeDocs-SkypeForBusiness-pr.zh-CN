---
title: 在 Lync Server 2013 中配置位置数据库
TOCTitle: 在 Lync Server 2013 中配置位置数据库
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398679(v=OCS.15)
ms:contentKeyID: 49313467
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置位置数据库

 

_**上一次修改主题：** 2012-09-17_

为使客户端能够自动检测其在网络中的位置，首先需要配置位置数据库。如果不配置位置数据库，且位置策略中的“所需位置”设置为“是”或“免责声明”，则会提示用户手动输入位置。

要配置位置数据库，请执行下列任务：

1.  使用网络元素到位置的映射填充数据库。如果您使用紧急位置标识号 (ELIN) 网关，则需要在\<公司名称\>字段中包含 ELIN。

2.  根据由 E9-1-1 服务提供商维护的主街道地址指南 (MSAG) 验证地址。

3.  发布更新的数据库。

> [!NOTE]  
> 另外，可以定义可用于代替位置数据库的辅助位置源数据库。有关详细信息，请参阅<a href="lync-server-2013-configure-a-secondary-location-information-service.md">配置辅助位置信息服务</a>。



## 本部分内容

  - [填充位置数据库](lync-server-2013-populate-the-location-database.md)

  - [验证地址](lync-server-2013-validate-addresses.md)

  - [发布位置数据库](lync-server-2013-publish-the-location-database.md)

