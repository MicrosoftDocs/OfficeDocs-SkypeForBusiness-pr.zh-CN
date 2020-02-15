---
title: Lync Server 2013： Lync Server 命令行管理程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server Management Shell
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398474(v=OCS.15)
ms:contentKeyID: 48184386
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d8ba2330e59d4f352407d94c6e73f96a5fff816
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006158"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-management-shell"></a>Lync Server 2013 命令行管理程序

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2017-09-20_

<div>


> [!NOTE]  
> Skype for Business cmdlet reference 已移动到 docs.microsoft.com。 单击下面的链接将转到新的 docs.microsoft.com 页面。 现在，内容是开放的，可用于通过 GitHub 进行社区贡献。 对所做的贡献有兴趣？ 查看存储库中的自述文件：<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A>



</div>

Microsoft Lync Server 2010 引入了一组大型的新的和改进的功能，与 Microsoft Office 通信服务器 2007 R2 中提供的功能相比。 其中一项改进是管理实现的方法。 例如，有一个新的用户界面（称为 "Lync Server 控制面板"），它表示在 Microsoft 管理控制台中使用最多的人的巨大转变。 可管理性的另一个主要改进是包含 Windows PowerShell。

Windows PowerShell 允许您从命令行管理 Microsoft 应用程序。 它包括命令行环境、特定于产品的命令和完整的脚本语言。 Windows PowerShell 首次被引入为2006中的 Windows 操作系统的可下载版本，并被合并为 Microsoft Exchange Server 2007 的可管理性的命令行界面。 从那一开始，它将继续增长，并已合并到大多数 Microsoft Server 产品中，这是 Microsoft Lync Server 2013 的最新产品。 Lync Server 2010 引入了接近550个产品的特定 cmdlet，您可以使用这些 cmdlet 来管理您的部署的各个方面。

以下各节包含 cmdlet 及其说明的列表。 也可直接从命令行获取此信息。 只需在 Lync Server 命令行管理程序命令提示符处键入以下内容：

    Get-Help <cmdlet name> -Full

例如，要通过命令提示符检索有关 **New-CsVoicePolicy** cmdlet 的帮助，请键入以下内容：

    Get-Help New-CsVoicePolicy -Full

有关在 Lync Server 2013 中了解 Windows PowerShell 的事项：

  - 若要运行 Lync Server cmdlet，请打开 Lync Server 命令行管理程序。
    
    <div>
    

    > [!WARNING]  
    > 如果打开的是 Windows PowerShell 窗口而不是 Lync Server 命令行管理程序，则默认情况下将无法运行 Lync Server cmdlet。 若要从 Windows PowerShell 中运行 Lync Server cmdlet，请首先在 Windows PowerShell 命令提示符处键入以下命令：<BR>Import-Module Lync

    
    </div>

  - Lync Server 命令行管理程序将自动安装在每个 Lync Server Enterprise Edition 前端服务器或 Standard Edition server 上。

  - Lync Server Windows PowerShell 博客[https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)中提供了新的和更新的信息、示例脚本和帮助，以了解有关 Windows Powershell 和 Microsoft Lync server 2013 cmdlet 的入门和帮助。

</div>

<span> </span>

</div>

</div>

</div>

