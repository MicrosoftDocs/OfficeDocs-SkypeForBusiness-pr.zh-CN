---
title: 'Lync Server 2013: 创建或修改新的客户端版本策略'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a new client version policy
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898476(v=OCS.15)
ms:contentKeyID: 50873756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64e9d9d2879d4633b1775f8934186b8b01992d13
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改新的客户端版本策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-23_

你可以使用客户端版本策略指定你的环境支持的客户端版本。 使用客户端版本有助于减少与支持多个客户端版本相关的成本。 它还可以改进整体用户体验, 因为当客户端的早期版本和更高版本的客户端交互时, 可用的功能可以受到较早版本的客户端的限制。 可以从 Lync Server 2013 控制面板或 Lync Server 2013 管理外壳程序创建或修改客户端版本策略。

<div>

## <a name="to-create-or-modify-client-version-policies-by-using-lync-server-control-panel"></a>使用 Lync Server "控制面板" 创建或修改客户端版本策略

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中, 单击 "**客户端**"。
    
    <div>
    

    > [!NOTE]  
    > 默认情况下, "<STRONG>客户端版本策略</STRONG>" 选项卡处于选中状态。

    
    </div>

4.  在 "**客户端版本策略**" 页面上, 执行下列操作之一:
    
      - 若要创建客户端版本策略, 请单击 "**新建**", 选择 "**网站策略**"、"**池策略**" 或 "**用户策略**", 然后单击 **"确定"**。
    
      - 若要修改全局策略或其他现有的客户端版本策略, 请选择该策略, 单击 "**编辑**", 然后单击 "**显示详细信息**"。

5.  在 "**编辑客户端版本策略**" 页面上, 创建或修改规则, 如在[Lync Server 2013 中创建或修改新的客户端版本策略规则](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md)中所述。

</div>

<div>

## <a name="creating-or-modifying-client-version-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 创建或修改客户端版本策略

你可以使用**CsClientVersionPolicy** cmdlet 创建客户端版本策略, 并使用**CsClientVersionPolicy** cmdlet 对其进行修改。 这些 cmdlet 既可以从 Lync Server 2013 管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-create-a-new-site-scoped-client-version-policy"></a>创建新的网站范围的客户端版本策略

  - 以下命令将创建应用于 Redmond 网站的新客户端版本策略。 由于没有指定任何其他参数, 新策略将使用默认的客户端版本设置。
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-per-user-client-version-policy"></a>创建新的基于用户的客户端版本策略

  - 若要创建每用户策略, 请使用类似下面的命令:
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

</div>

有关详细信息, 请参阅[CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) Cmdlet 和[CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

