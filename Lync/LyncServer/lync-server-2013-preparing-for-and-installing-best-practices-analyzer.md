---
title: Lync Server 2013：准备和安装最佳做法分析器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing for and installing Best Practices Analyzer
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591347(v=OCS.15)
ms:contentKeyID: 48184149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f5992b45d8930bac880f66422d10ddbd4b94f18
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a>在 Lync Server 2013 中准备和安装最佳做法分析器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-11-07_

必须作为管理员组的成员登录才能执行本主题中所述的任务。

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a>最佳做法分析器安装的系统要求

若要运行 Lync Server 2013、最佳做法分析程序来扫描你的环境，计算机必须运行以下任一操作系统的64位版本：

  - Windows Server 2008 R2 Service Pack 1 （SP1）标准操作系统

  - Windows Server 2008 R2 与 SP1 企业版操作系统

  - Windows Server 2008 R2 与 SP1 Datacenter 操作系统

  - Windows Server 2012 Datacenter 操作系统

  - Windows Server 2012 标准操作系统

  - Windows Server 2012 企业版操作系统

  - Windows Server 2012 R2 Datacenter 操作系统

  - Windows Server 2012 R2 标准操作系统

  - Windows Server 2012 R2 企业版操作系统

  - Windows 8 操作系统

  - Windows 7 操作系统

计算机还必须运行以下内容：

  - Microsoft .NET Framework 4.5。 对于 Lync Server 2013，必须先在服务器上手动安装64位版本的 Microsoft .NET Framework 4.5，然后再安装 Lync Server 2013。

  - Lync Server 2013、核心组件。

  - WMI 向后兼容程序包。 有关详细信息，请参阅在迁移文档中[安装 WMI 向后兼容性程序包](install-wmi-backward-compatibility-package.md)。

  - Windows PowerShell 3.0。 有关详细信息，请参阅在部署文档中[安装 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md) 。

你可以在具有支持的操作系统的计算机上安装最佳做法分析器，该操作系统未运行 Lync Server 2013、Core 组件或 WMI 向后兼容性程序包，但你只能在这些计算机上使用最佳做法分析器来查看报表，而不是以运行扫描。

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a>选择计算机进行安装

我们建议在专用于 Lync Server 2013 管理的计算机上安装 Lync Server 2013 和最佳做法分析器。 可以在运行 Lync Server 2013 或运行 Lync Server 2013 管理工具的管理计算机的服务器上安装该工具。 如果在运行 Lync Server 的服务器上安装该工具，我们建议使用该工具仅扫描该服务器。

</div>

<div>

## <a name="installing-best-practices-analyzer"></a>安装最佳做法分析器

您可以在[http://go.microsoft.com/fwlink/p/?linkId=266539](http://go.microsoft.com/fwlink/p/?linkid=266539)下载 Lync Server 2013 的最佳做法分析器。

若要安装最佳做法分析器，请在要安装该工具的计算机上启动 Microsoft 安装程序文件 RtcBPA，然后按照屏幕上的说明进行操作。 安装程序文件的默认\<位置是系统驱动器\>\\程序文件\\Lync Server 2013\\BPA。

</div>

</div>

<span> </span>

</div>

</div>

</div>

