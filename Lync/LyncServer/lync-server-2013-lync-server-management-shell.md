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
ms.openlocfilehash: d519b647eae4937af10a38673803484a253baef7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-management-shell"></a>Lync Server 2013 命令行管理程序

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2017-09-20_

<div>


> [!NOTE]  
> Skype for Business cmdlet 参考已移至 docs.microsoft.com。 单击下面的链接将转至新的 docs.microsoft.com 页面。 内容现在是开源的，可通过 GitHub 用于社区投稿。 对投稿感兴趣？ 查看存储库中的自述文件：<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A>



</div>

Microsoft Lync Server 2010 引入了一组大型的新功能和改进功能，与 Microsoft Office 通信服务器 2007 R2 中的可用功能相比较。 一个改进是你管理实现的方式。 例如，有一个新的用户界面，称为 Lync Server 控制面板，它表示与大多数人在 Microsoft 管理控制台中的最大转变。 易管理性的另一重大改进是包含 Windows PowerShell。

Windows PowerShell 允许你从命令行管理 Microsoft 应用程序。 它包括命令行环境、特定于产品的命令和完整的脚本语言。 Windows PowerShell 第一次引入于2006中的 Windows 操作系统的可下载版本，并已被合并为 Microsoft Exchange Server 2007 的可管理性的命令行界面。 从此时起，它将持续增长，并已合并到大多数 Microsoft 服务器产品中，最新的是 Microsoft Lync Server 2013。 Lync Server 2010 引入了一些特定于550的特定 cmdlet，可用于管理你的部署的各个方面。

以下各节包含 cmdlet 及其说明的列表。 也可直接从命令行获取此信息。 只需在 Lync Server Management Shell 命令提示符处键入以下内容：

    Get-Help <cmdlet name> -Full

例如，要通过命令提示符检索有关 **New-CsVoicePolicy** cmdlet 的帮助，请键入以下内容：

    Get-Help New-CsVoicePolicy -Full

有关在 Lync Server 2013 中了解 Windows PowerShell 的事项：

  - 若要运行 Lync Server cmdlet，请打开 Lync Server 命令行管理程序。
    
    <div>
    

    > [!WARNING]  
    > 如果打开的是 Windows PowerShell 窗口而不是 Lync Server Management Shell，则默认情况下你将无法运行 Lync Server cmdlet。 若要从 Windows PowerShell 中运行 Lync Server cmdlet，请首先在 Windows PowerShell 命令提示符处键入以下内容：<BR>导入模块 Lync

    
    </div>

  - Lync Server 命令行管理程序自动安装在每个 Lync Server 企业版前端服务器或标准版服务器上。

  - 有关 Windows PowerShell 和 Microsoft Lync Server 2013 cmdlet 的新增和更新信息、示例脚本以及有关 Windows PowerShell 和 Microsoft Lync Server cmdlet 的详细信息，请访问 Lync [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)Server Windows PowerShell 博客。

</div>

<span> </span>

</div>

</div>

</div>

