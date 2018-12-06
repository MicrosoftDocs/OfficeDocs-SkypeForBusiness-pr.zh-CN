---
title: Lync Server 2013：验证拓扑设计
TOCTitle: 验证拓扑设计
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412951(v=OCS.15)
ms:contentKeyID: 49314133
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中验证拓扑设计

 

_**上一次修改主题：** 2012-01-02_

拓扑生成器会自动验证拓扑。任何拓扑错误均被标识为验证错误，由服务器角色旁边的验证错误图标指示。验证拓扑是否正确代表部署的拓扑也很重要。

## 发布前验证拓扑

1.  检查所有简单 URL 是否配置正确。

2.  确认基于 SQL Server 的服务器处于联机状态，并可供安装 拓扑生成器以及所有必要防火墙规则的计算机使用。

3.  确认文件共享可用，并已定义适当的权限。

4.  确认拓扑中定义了满足部署要求的正确服务器角色。

5.  验证服务器是否存在于 Active Directory 域服务 中。如果已将服务器加入域，将自动验证。

如果已验证拓扑并且未出现验证错误，则发布拓扑的准备工作应该已经就绪。如果出现验证错误，则必须先更正错误，然后才能发布拓扑。有关发布拓扑的详细信息，请参阅 [在 Lync Server 2013 中发布拓扑](lync-server-2013-publish-the-topology.md)。

