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
ms.openlocfilehash: b64dce1b74be8ed1aed0c5d1f515910341f57c52
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-client-version-policy-rules-in-lync-server-2013"></a>在 Lync Server 2013 中查看客户端版本策略规则

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-23_

客户端版本策略由一组客户端版本策略规则组成。 这些规则定义在用户尝试使用特定客户端和客户端版本登录时应采取的操作。 你可以从 Lync Server 2013 控制面板或 Lync Server 2013 管理外壳查看客户端版本策略规则。

<div>

## <a name="to-view-client-version-policy-rules-by-using-lync-server-control-panel"></a>使用 Lync Server "控制面板" 查看客户端版本策略规则

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**客户端**"，然后单击 "**客户端版本策略**导航" 按钮。

4.  在 "**客户端版本策略**" 页面上，双击要查看的客户端版本策略。

5.  这些规则将显示在 "**编辑客户端版本策略**" 页面上。 若要查看规则的详细信息，请选择规则，然后单击 "**显示详细信息**"。

</div>

<div>

## <a name="viewing-client-version-policy-rules-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看客户端版本策略规则

你可以使用 Lync Server 命令行管理程序和**CsClientVersionPolicyRule** cmdlet 查看客户端版本策略规则。 此 cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-view-client-version-policy-rules"></a>查看客户端版本策略规则

  - 若要查看客户端版本策略规则，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：
    
        Get-CsClientVersionPolicyRule
    
    这将针对每个配置的规则返回类似于以下内容的信息：
    
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

