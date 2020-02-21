---
title: Lync Server 2013： Windows PowerShell 和 Lync Server 管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell and Lync Server 2013 management tools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59893869
ms.date: 07/20/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c24a94bf74b2ecf911179d64691e95153acceeeb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="windows-powershell-and-lync-server-2013-management-tools"></a>Windows PowerShell 和 Lync Server 2013 管理工具

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-07-20_

在 Microsoft Lync Server 2013 中，管理工具是使用 Windows PowerShell 实现的。 Windows PowerShell 包含命令行环境、产品特定命令和完整的脚本语言。 使用 Windows PowerShell 实施的 Lync Server 2013 工具包括以下各项：

  - **拓扑生成器**。 您可以使用拓扑生成器来创建、调整和发布规划的拓扑，并在开始服务器安装之前验证拓扑。 在各台服务器上安装 Lync Server 2013 时，服务器会在安装过程中读取已发布的拓扑，并且安装程序会在拓扑中按照指示部署服务器。 安装完成后，配置信息将自动复制到所有服务器。 仅可以使用拓扑生成器将组件添加到部署。

  - **Lync Server 命令行管理**程序。 您可以使用 Lync Server 命令行管理程序对部署进行完整的命令行管理。

  - **Lync Server 控制面板**。 您可以使用 Microsoft Lync Server 2013 控制面板用户界面来管理部署中的最常见任务。

这些工具使用 Windows PowerShell cmdlet 对部署进行管理，其中包含了近 550 个产品特定的 cmdlet。 Lync Server 2013 中包含的安全 cmdlet 主要用于管理身份验证，以及用户权限和权限。 多种 cmdlet 可用于管理身份验证，包括用于证书和个人标识号 (PIN) 身份验证的 cmdlet。 此外，许多 cmdlet 使您可以使用新的基于角色的访问控制（RBAC）功能委派 Lync Server 2013 的管理控制权。 有关 Lync Server cmdlet 的详细信息，请参阅[Lync server 2013 命令行管理](lync-server-2013-lync-server-management-shell.md)程序。

Windows PowerShell 的脚本安全功能专为帮助防止旧技术的脚本相关安全问题（包括 Microsoft Visual Basic Script Edition （VBScript））提供帮助。 Windows PowerShell 安全功能旨在创建一个用户无法轻松或无意中运行脚本的环境。 默认情况下，Windows PowerShell 安全功能处于启用状态。 您可以修改这些功能的状态以满足您的脚本需求和各种安全目标。 这并不是说命令行管理程序使用户无法运行脚本。 相反，在默认情况下，命令行管理程序会使用户在运行脚本时无需意识到这一点，这样做会变得困难。 有关详细信息，请参阅中的 Windows [https://go.microsoft.com/fwlink/p/?LinkId=213145](https://go.microsoft.com/fwlink/p/?linkid=213145)PowerShell 脚本安全性。

</div>

<span> </span>

</div>

</div>

</div>

