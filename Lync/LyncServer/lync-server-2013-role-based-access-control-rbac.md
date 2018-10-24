---
title: Lync Server 2013 的基于角色的访问控制 (RBAC)
TOCTitle: Lync Server 2013 的基于角色的访问控制 (RBAC)
ms:assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn481134(v=OCS.15)
ms:contentKeyID: 59679365
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 的基于角色的访问控制 (RBAC)

 

_**上一次修改主题：** 2013-11-07_

Microsoft Lync Server 2013 包括基于角色的访问控制 (RBAC) 组，以使您能够在保持高标准安全性的同时委派管理任务。这些组是在林准备期间创建的。有关准备林的详细信息，请参阅 [Lync Server 2013 的 Active Directory 域服务](lync-server-2013-active-directory-domain-services-for-lync-server.md)。有关林准备创建的特定组的详细信息，请参阅部署文档中的[Lync Server 2013 中的林准备所做的更改](lync-server-2013-changes-made-by-forest-preparation.md)。

使用 RBAC，可以通过将用户分配至预定义的管理角色（包括 11 个可以执行多种常见管理任务的预定义角色）来授予管理权限。每个角色均与具有该角色的用户可以运行的 Lync Server 命令行管理程序 cmdlet 的特定列表相关联。可以使用 RBAC 来遵守“最小特权”原则，按照该原则，用户只能获得工作所需的管理能力。有关详细信息，请参阅规划文档中的[在 Lync Server 2013 中规划基于角色的访问控制](lync-server-2013-planning-for-role-based-access-control.md)。

