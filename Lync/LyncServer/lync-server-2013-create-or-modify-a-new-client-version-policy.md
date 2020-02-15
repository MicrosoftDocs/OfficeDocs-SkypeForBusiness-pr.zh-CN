---
title: Lync Server 2013：创建或修改新的客户端版本策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898476(v=OCS.15)
ms:contentKeyID: 50873756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8464e64c3de1e85f823bb3e1b5dac4dd1837effd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045975"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改新的客户端版本策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

您可以使用客户端版本策略指定您的环境中支持的客户端版本。 使用客户端版本控制有助于降低与支持多个客户端版本相关的成本。 它还可以改进总体用户体验，因为在更早和更高版本的客户端进行交互时，可通过早期版本的客户端来限制可用功能。 您可以从 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序创建或修改客户端版本策略。

<div>

## <a name="to-create-or-modify-client-version-policies-by-using-lync-server-control-panel"></a>使用 Lync Server 控制面板创建或修改客户端版本策略的具体方法

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“客户端”****。
    
    <div>
    

    > [!NOTE]  
    > 默认情况下，选中“客户端版本策略”<STRONG></STRONG>选项卡。

    
    </div>

4.  在 "**客户端版本策略**" 页上，执行下列操作之一：
    
      - 若要创建客户端版本策略，请单击 "**新建**"，选择 "**网站策略**"、"**池策略**" 或 "**用户策略**"，然后单击 **"确定"**。
    
      - 若要修改全局策略或其他现有客户端版本策略，请选择该策略，单击 "**编辑**"，然后单击 "**显示详细信息**"。

5.  在 "**编辑客户端版本策略**" 页上，创建或修改规则，如在[Lync Server 2013 中创建或修改新的客户端版本策略规则](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md)中所述。

</div>

<div>

## <a name="creating-or-modifying-client-version-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 创建或修改客户端版本策略

您可以使用**CsClientVersionPolicy** cmdlet 创建客户端版本策略，并使用**CsClientVersionPolicy** cmdlet 对其进行修改。 这些 cmdlet 可从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>

## <a name="to-create-a-new-site-scoped-client-version-policy"></a>创建新的网站范围的客户端版本策略

  - 以下命令将创建一个应用于 Redmond 站点的新客户端版本策略。 由于未指定其他参数，因此新策略将使用默认客户端版本设置。
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-per-user-client-version-policy"></a>创建新的每用户客户端版本策略

  - 若要创建每用户策略，请使用类似如下的命令：
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

</div>

有关详细信息，请参阅[CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) Cmdlet 和[CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

