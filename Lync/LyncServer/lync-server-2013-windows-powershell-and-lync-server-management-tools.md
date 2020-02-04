---
title: Lync Server 2013：Windows PowerShell 和 Lync Server 管理工具
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
ms.openlocfilehash: dbfd15ff3c1047f04a6878b65a3d16e63bac490b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-and-lync-server-2013-management-tools"></a>Windows PowerShell 和 Lync Server 2013 管理工具

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2016-07-20_

在 Microsoft Lync Server 2013 中，管理工具是使用 Windows PowerShell 实现的。 Windows PowerShell 包含命令行环境、特定于产品的命令和完整的脚本语言。 使用 Windows PowerShell 实现的 Lync Server 2013 工具包括以下内容：

  - **拓扑生成器**。 你可以使用拓扑生成器来创建、调整和发布你的计划拓扑，并在开始服务器安装之前验证你的拓扑。 在单个服务器上安装 Lync Server 2013 时，服务器会将已发布的拓扑作为安装过程的一部分进行读取，安装程序将按照拓扑中的指示部署该服务器。 After setup, configuration information is automatically replicated to all servers. Components can be added to your deployment only by using Topology Builder.

  - **Lync Server 命令行管理**程序。 你可以使用 Lync Server 命令行管理程序执行部署的完整命令行管理。

  - **Lync Server "控制面板"**。 你可以使用 Microsoft Lync Server 2013 控制面板用户界面管理你的部署中的最常见任务。

这些工具使用 Windows PowerShell cmdlet 管理你的部署，包括靠近550产品的特定 cmdlet。 Lync Server 2013 中包含的安全 cmdlet 主要用于管理身份验证以及用户权利和权限。 多种 cmdlet 可用于管理身份验证，包括用于证书和个人标识号 (PIN) 身份验证的 cmdlet。 此外，你可以使用一些 cmdlet 来使用新的基于角色的访问控制（RBAC）功能来委派 Lync Server 2013 的管理控制。 有关 Lync Server cmdlet 的详细信息，请参阅[Lync server 2013 命令行管理](lync-server-2013-lync-server-management-shell.md)程序。

Windows PowerShell 的脚本安全功能专门设计用于帮助避免较旧技术（包括 Microsoft Visual Basic 脚本编写 Edition （VBScript））的某些脚本相关安全问题。 Windows PowerShell 安全功能旨在创建用户无法轻松或不知不觉地运行脚本的环境。 默认情况下，Windows PowerShell 安全功能已启用。 你可以修改这些功能的状态，以满足你的脚本需求和各种安全目标。 这并不是说外壳程序使用户无法运行脚本。 相反，shell 使用户在运行脚本时无需意识到这样做会很困难———默认情况下。 有关详细信息，请参阅中的 Windows [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145)PowerShell 脚本安全性。

</div>

<span> </span>

</div>

</div>

</div>

