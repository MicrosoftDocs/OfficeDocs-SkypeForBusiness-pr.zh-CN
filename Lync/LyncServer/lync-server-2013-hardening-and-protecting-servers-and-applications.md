---
title: Lync Server 2013：强化和保护服务器和应用程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting servers and applications for Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518331(v=OCS.15)
ms:contentKeyID: 62625491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b0a6179e77e4688693fe277748a8933a9dbe911
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006198"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a>强化和保护 Lync Server 2013 的服务器和应用程序

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-12-05_

您应根据特定组件的最佳做法强化和保护操作系统及应用程序。 本节介绍如何强化应用程序服务器和使用组策略来实现安全锁定。

<div>


> [!NOTE]  
> 您还可以加强和保护用于 Microsoft Lync Server 2013 部署的数据库。 有关详细信息，请参阅<A href="lync-server-2013-hardening-and-protecting-databases.md">强化和保护 Lync Server 2013 的数据库</A>。



</div>

<div>

## <a name="securing-application-servers"></a>保护应用程序服务器

对于应用程序服务器，应强化操作系统和应用程序。例如，对于专门用来运行 Microsoft Internet Security and Acceleration (ISA) Server 2006 的 Windows Server 2008 计算机，应从操作系统和应用程序方面进行强化。应将尽量减少服务器提供的正在运行的服务数作为主要目标。

</div>

<div>

## <a name="securing-virtual-servers"></a>保护虚拟服务器

虚拟服务器快照包含服务器的数据磁盘的副本，还包含内存中的数据的转储，这两种都可能包含可能导致攻击的敏感加密数据。 对于使用虚拟化实现的生产服务器，应禁用所有服务器快照或以受严格控制的方式管理它们。 有关保护 Hyper-v 虚拟服务器的详细信息，请参阅以下位置的 Hyper-v 安全指南： [http://go.microsoft.com/fwlink/p/?LinkId=214176](http://go.microsoft.com/fwlink/p/?linkid=214176)。

</div>

<div>

## <a name="group-policy"></a>组策略

在 Windows Server 2008 和 Windows Server 2008 R2 中，组策略提供基于目录的桌面配置管理。通过在组策略对象 (GPO) 中定义以下各项的“计算机和用户”设置，可以使用组策略来实现安全锁定：

  - 基于注册表的策略

  - 安全性

  - 软件安装

  - 脚本

  - 文件夹重定向

  - 远程安装服务

为了向管理员提供用于配置这些设置的用户界面，管理模板随操作系统版本、service pack 版本和一些应用程序（包括 Lync Server 2013）一起提供。

Communicator .adm 文件是一个随 Lync Server 2013 提供的管理模板，安装在% windir%\\inf\\目录中，并提供组策略设置的接口。 Communicator.adm 中的每项设置均与注册表中影响应用程序行为的设置对应。

利用 Active Directory 用户和计算机控制台以及组策略管理控制台 (GPMC) 中提供的 GPedit.dll，可以访问这些设置。

</div>

<div>

## <a name="group-policy-security-settings"></a>组策略安全设置

组策略包含 GPO 的安全设置，当通过 GPedit.dll 访问这些安全设置时，它们位于“计算机配置”/“Windows 设置”/“安全设置”下。 可以导入安全模板以配置 GPO 的安全设置。 Windows Server 2008 安全指南（网址[http://go.microsoft.com/fwlink/p/?LinkId=145186](http://go.microsoft.com/fwlink/p/?linkid=145186)为）和 windows Server 2008 R2 安全合规性管理[http://go.microsoft.com/fwlink/p/?LinkId=211882](http://go.microsoft.com/fwlink/p/?linkid=211882)工具包包含多个示例模板，可以对它们进行修改以满足您的需求。

</div>

<div>

## <a name="best-practices"></a>最佳做法

  - 强化所有服务器操作系统和应用程序。

  - 保护服务器快照和增强所有虚拟服务器的安全性。

  - 使用组策略实现安全锁定。

</div>

</div>

<span> </span>

</div>

</div>

</div>

