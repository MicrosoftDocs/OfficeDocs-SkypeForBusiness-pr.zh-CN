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
ms.openlocfilehash: 42b8b9d3fc21c590bda12841cb6002987d4c0650
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a>强化和保护 Lync Server 2013 的服务器和应用程序

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-12-05_

你应该根据该特定组件的最佳做法来加强和保护你的操作系统和应用程序。 本部分介绍了如何加强应用程序服务器以及如何使用组策略实现安全 lockdowns。

<div>


> [!NOTE]  
> 你还可以加强和保护 Microsoft Lync Server 2013 部署所使用的数据库。 有关详细信息，请参阅<A href="lync-server-2013-hardening-and-protecting-databases.md">强化和保护 Lync Server 2013 的数据库</A>。



</div>

<div>

## <a name="securing-application-servers"></a>保护应用程序服务器

对于应用程序服务器，应加强操作系统和应用程序。 例如，专用于运行 Microsoft Internet 安全和加速（ISA） Server 2006 的 Windows Server 2008 计算机应从操作系统和应用程序的角度进行加强。 将服务器运行和提供的服务数量减到最少应该是一个主要目标。

</div>

<div>

## <a name="securing-virtual-servers"></a>保护虚拟服务器

虚拟服务器快照包含服务器数据磁盘的副本，还包含内存中数据的转储，这两者都可能包含可能导致攻击的敏感加密数据。 对于使用虚拟化实现的生产服务器，你应该禁用所有服务器快照或以一种非常受控制的方式管理它们。 有关保护 Hyper-v 虚拟服务器的详细信息，请参阅以下位置的 Hyper-v 安全指南： [http://go.microsoft.com/fwlink/p/?LinkId=214176](http://go.microsoft.com/fwlink/p/?linkid=214176)。

</div>

<div>

## <a name="group-policy"></a>组策略

在 Windows Server 2008 和 Windows Server 2008 R2 中，组策略提供基于目录的桌面配置管理。 你可以通过在组策略对象（GPO）内定义计算机和用户设置来使用组策略来实现安全 lockdowns，如下所示：

  - 基于注册表的策略

  - 安全性

  - 软件安装

  - 标

  - 文件夹重定向

  - 远程安装服务

若要为管理员提供配置这些设置的用户界面，管理模板随操作系统版本、service pack 版本和某些应用程序（包括 Lync Server 2013）一起提供。

Communicator 文件是随 Lync Server 2013 提供的管理模板，它安装在% windir%\\inf\\目录中，并提供组策略设置的接口。 Communicator .adm 中的每个设置对应于注册表中影响应用程序行为的设置。

可从 "Active Directory 用户和计算机" 控制台和 "组策略管理控制台（GPMC）" 中访问该设置，从 Gpedit.msc 访问这些设置。

</div>

<div>

## <a name="group-policy-security-settings"></a>组策略安全设置

组策略包含从 Gpedit.msc 访问的 "计算机配置/Windows 设置/安全设置" 下的 GPO 的安全设置。 可以导入安全模板来配置 GPO 的安全设置。 Windows Server 2008 安全指南（位于[http://go.microsoft.com/fwlink/p/?LinkId=145186](http://go.microsoft.com/fwlink/p/?linkid=145186) ）和 windows Server 2008 R2 安全合规性管理工具包[http://go.microsoft.com/fwlink/p/?LinkId=211882](http://go.microsoft.com/fwlink/p/?linkid=211882)中包含多个示例模板，可以修改这些模板来满足你的需求。

</div>

<div>

## <a name="best-practices"></a>最佳做法

  - 强化所有服务器操作系统和应用程序。

  - 保护服务器快照并增强所有虚拟服务器的安全性。

  - 使用组策略实现安全 lockdowns。

</div>

</div>

<span> </span>

</div>

</div>

</div>

