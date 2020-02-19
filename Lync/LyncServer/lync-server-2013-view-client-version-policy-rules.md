---
title: Lync Server 2013：查看客户端版本策略规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version policy rules
ms:assetid: f3a0215f-f72f-4e9b-a07b-25858dc4203a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923060(v=OCS.15)
ms:contentKeyID: 50675350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa0b6166a3bf8c21c6d2eddcd9152c9c7d4efc37
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-client-version-policy-rules-in-lync-server-2013"></a>在 Lync Server 2013 中查看客户端版本策略规则

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

客户端版本策略由一组客户端版本策略规则组成。 这些规则定义在用户尝试使用特定客户端和客户端版本登录时应采取的操作。 您可以从 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序中查看客户端版本策略规则。

<div>

## <a name="to-view-client-version-policy-rules-by-using-lync-server-control-panel"></a>使用 Lync Server 控制面板查看客户端版本策略规则

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击 "**客户端**"，然后单击 "**客户端版本策略**导航" 按钮。

4.  在 "**客户端版本策略**" 页上，双击要查看的客户端版本策略。

5.  这些规则将显示在 "**编辑客户端版本策略**" 页上。 若要查看某个规则的详细信息，请选择该规则，然后单击 "**显示详细信息**"。

</div>

<div>

## <a name="viewing-client-version-policy-rules-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看客户端版本策略规则

您可以使用 Lync Server 命令行管理程序和**CsClientVersionPolicyRule** cmdlet 查看客户端版本策略规则。 此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>

## <a name="to-view-client-version-policy-rules"></a>查看客户端版本策略规则

  - 若要查看客户端版本策略规则，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：
    
        Get-CsClientVersionPolicyRule
    
    这将针对每个已配置的规则返回类似于以下内容的信息：
    
        Identity          : Global/2336c611-a243-4c5d-994b-eea8a524d0e4
        Priority          : 0
        RuleId            : 2336c611-a243-4c5d-994b-eea8a524d0e4
        Description       :
        Action            : Block
        ActionUrl         :
        MajorVersion      : 1
        MinorVersion      : 3
        BuildNumber       :
        QfeNumber         :
        UserAgent         : RTC
        UserAgentFullName :
        Enabled           : True
        CompareOp         : LEQ

</div>

有关详细信息，请参阅[CsClientVersionPolicyRule](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicyRule) cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

