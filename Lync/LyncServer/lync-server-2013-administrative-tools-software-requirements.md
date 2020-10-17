---
title: Lync Server 2013：管理工具软件要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administrative tools software requirements
ms:assetid: 2fb172c3-7b84-4e49-981c-2a17e7a00a29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195653(v=OCS.15)
ms:contentKeyID: 48183740
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7c7b08d22933947c2f8079a2713fd134feb4629
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509039"
---
# <a name="administrative-tools-software-requirements-in-lync-server-2013"></a>Lync Server 2013 中的管理工具软件要求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-11-07_

本主题介绍除了操作系统要求之外，安装和使用 Lync Server 2013 管理工具所需的软件。

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Lync Server 2013 需要64位版本的 Microsoft .NET Framework 4.5。

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

运行 Microsoft Lync Server 2013 的任何组件需要 Windows PowerShell 3.0。 有关详细信息，请参阅 [安装适用于 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。

</div>

<div>

## <a name="windows-installer-version-45"></a>Windows Installer 版本 4.5

Lync Server 2013 使用 Windows Installer 技术安装、卸载和维护各种服务器角色。 Windows Installer 4.5 可用作 Windows Server 操作系统的可再发行组件。 Windows Installer 4.5 附带 Windows Server 2012 R2、Windows Server 2012 和 Windows Server 2008 R2，这意味着您无需为任何运行 Lync Server 2013 的计算机下载该实用工具。  (Lync Server 2013 仅可安装在运行 Windows Server 2012 R2、Windows Server 2012 或 Windows Server 2008 R2 的计算机上 ) 

但是，如果要在管理员工作站上安装 Lync Server 命令行管理程序或 Lync Server 拓扑生成器，可能需要下载 Windows Installer 4.5。 该实用工具附带 Windows 7 和 Windows 2008 R2，但不是在任何以前版本的 Windows 操作系统上提供。 您可以从 Microsoft 下载中心下载 Windows Installer 4.5 <https://go.microsoft.com/fwlink/p/?linkid=197395> 。

</div>

<div>

## <a name="microsoft-silverlight-5-browser-plug-in"></a>Microsoft Silverlight 5 浏览器插件

Lync Server 2013 控制面板是一种基于 web 的工具，需要安装最新版本的 Microsoft Silverlight 5 浏览器插件。 当您启动 Lync Server 2013 控制面板时，如果未安装此软件或安装了早期版本，Lync Server 2013 控制面板将提示您安装所需的版本。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)  


[Lync Server 2013 中的管理工具基础结构要求](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[安装和管理 Lync Server 2013 所需的管理员权利和权限](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

