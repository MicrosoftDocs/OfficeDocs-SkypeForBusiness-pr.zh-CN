---
title: Lync Server 2013：运行 Lync Server 2013 的服务器的系统要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 301cd234e2218fc806423a9ffe9beb49994402f2
ms.sourcegitcommit: 208179a3dd166f53b5a3058242cb84207909f4ee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2020
ms.locfileid: "41104491"
---
# <a name="system-requirements-for-servers-running-lync-server-2013"></a>运行 Lync Server 2013 的服务器的系统要求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-07-24_

<div>


> [!NOTE]  
> 有关硬件要求的详细信息，请参阅<A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013 的服务器硬件平台</A>。



</div>

标准版和企业版服务器共享相同的软件要求。

对于运行 Lync Server 2013 的服务器，企业版适用于作为主要组织部署的大型组织。 企业版服务器设计为每个池中大约80000穴用户。 运行 Lync Server 2013 的服务器的标准版适用于较小组织和组织内部部署中的远程位置。 一对标准版服务器最多可支持5000个用户。。 有关标准版服务器和企业版服务器之间的差异的详细信息，请参阅[Lync Server 2013 的部署概述](lync-server-2013-deployment-overview.md)。

<div>

## <a name="operating-system-installation"></a>操作系统安装

<div>


> [!IMPORTANT]  
> Lync Server 2013 仅在64位版本中可用，它需要64位硬件和 Windows Server 操作系统的一个64版本。 此版本不支持 Lync Server 2013 的32位版本。



</div>

标准版和企业版服务器可以使用以下任何一种：

  - Windows Server 2008 R2 SP1 或最新 service pack

  - Windows Server 2012

  - Windows Server 2012 R2

在标准版服务器或企业版前端服务器上安装操作系统软件。 应用所有更新，以使操作系统的最新更新和所需更新级别与组织的标准一致。 有关操作要求的更多详细信息，请参阅支持文档中的[Lync server 2013 中的 "服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)"。

> [!NOTE] Lync Server 2013 不支持操作系统就地升级。  必须部署单独的池并将用户迁移到具有不同操作系统的新池。

<div>


> [!NOTE]  
> 要使 Lync Server 2013 在 Windows Server 2012 R2 上工作，你可能需要在 Windows Server 中更改注册表项的值。 若要使证书正常工作，并且客户端向 Survivable 分支机构注册，则可能需要此更改。 有关详细信息，请参阅 <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A>。



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a>Lync Server 2013 的其他软件

除了操作系统需要的更新外，Lync Server 2013 还需要操作系统角色、功能和软件才能运行。 有关在发布拓扑和安装 Lync Server 2013 之前必须安装的其他软件的详细信息，请参阅规划文档中[Lync Server 2013 的其他软件要求](lync-server-2013-additional-software-requirements.md)。

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a>所有服务器角色所需的其他软件

在所有服务器角色上，还必须确保安装了 Windows PowerShell 命令行界面3.0 和 Microsoft .NET Framework 4.5。

此外，在运行 Lync Server 管理工具的任何计算机上都需要 Windows PowerShell 命令行界面3.0 和 Microsoft .NET Framework 4.5。

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Lync Server 2013 要求你在将参与 Lync Server 拓扑的每台计算机上安装 Windows PowerShell 3.0。 有关安装 Windows PowerShell 3.0 的详细信息，请参阅[安装 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。

<div>


> [!NOTE]  
> 在 Windows Server&nbsp;2008&nbsp;R2 SP1 上安装 Microsoft .net Framework 4.5 之前，无法安装 windows PowerShell 命令行界面3.0。



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

在将在 Windows Server 2012 或 Windows Server 2012 R2 上运行 Lync Server 2013 的服务器上安装 Microsoft .NET Framework 4.5 时，必须执行一个附加步骤。 安装 .NET Framework 4.5 后，请使用服务器管理器安装 HTTP 激活。

**在 Windows Server 2012 或 Windows Server 2012 R2 上安装 .NET 4.5 HTTP 激活**

1.  从 "**开始**" 菜单中，单击 "**程序**"，然后单击 "**管理工具**"，然后单击 "**服务器管理器**"。

2.  在服务器管理器中的 "**功能摘要**" 下，选择 "**添加功能**"。

3.  展开 **.Net Framework 4.5**。

4.  选择 " **WCF 激活**" （如果尚未选中）。 然后选择 " **HTTP 激活**"。

5.  单击 "**下一步**" 并按照提示完成安装。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

