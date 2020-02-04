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
ms.openlocfilehash: 1a3f174b4f699add911149128e3d7d48aa00e1c5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administrative-tools-software-requirements-in-lync-server-2013"></a>Lync Server 2013 中的管理工具软件要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-11-07_

本主题介绍除了操作系统要求之外，安装和使用 Lync Server 2013 管理工具所需的软件。

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Lync Server 2013 需要64位版本的 Microsoft .NET Framework 4.5。

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

运行 Microsoft Lync Server 2013 的任何组件需要 Windows PowerShell 3.0。 有关详细信息，请参阅[安装 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。

</div>

<div>

## <a name="windows-installer-version-45"></a>Windows Installer 版本4。5

Lync Server 2013 使用 Windows Installer 技术安装、卸载和维护各种服务器角色。 Windows Installer 版本4.5 可用作 Windows Server 操作系统的可再发行组件。 Windows Installer 4.5 附带 Windows Server 2012 R2、Windows Server 2012 和 Windows Server 2008 R2，这意味着无需为运行 Lync Server 2013 的任何计算机下载该实用工具。 （Lync Server 2013 仅可安装在运行 Windows Server 2012 R2、Windows Server 2012 或 Windows Server 2008 R2 的计算机上。）

但是，如果你想要在管理员工作站上安装 Lync Server Management Shell 或 Lync Server 拓扑生成器，可能需要下载 Windows Installer 4.5。 该实用工具附带 Windows 7 和 Windows 2008 R2，但不附带任何以前版本的 Windows 操作系统。 您可以从 Microsoft 下载中心下载 Windows Installer 4.5 <http://go.microsoft.com/fwlink/p/?linkid=197395>。

</div>

<div>

## <a name="microsoft-silverlight-5-browser-plug-in"></a>Microsoft Silverlight 5 浏览器插件

Lync Server 2013 控制面板是基于 web 的工具，需要安装最新版本的 Microsoft Silverlight 5 浏览器插件。 当你启动 Lync Server 2013 控制面板时，如果未安装此软件或者安装了早期版本，则 Lync Server 2013 控制面板会提示你安装所需的版本。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)  


[Lync Server 2013 中的管理工具基础结构要求](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[Lync Server 2013 的安装和管理所需的管理员权限](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

