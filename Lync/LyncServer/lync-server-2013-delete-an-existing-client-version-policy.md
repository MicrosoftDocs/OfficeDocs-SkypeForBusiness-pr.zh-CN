---
title: Lync Server 2013：删除现有客户端版本策略
description: Lync Server 2013：删除现有客户端版本策略。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing client version policy
ms:assetid: b88aaa25-97ff-4eb6-bd34-b97332cd6890
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923064(v=OCS.15)
ms:contentKeyID: 50675349
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1328d54790b2a7856fa2776bb59feeb515bab1cf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553658"
---
# <a name="delete-an-existing-client-version-policy-in-lync-server-2013"></a>在 Lync Server 2013 中删除现有客户端版本策略

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

如果要删除以前配置的客户端版本策略，可以从 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序中将其删除。

<div>

## <a name="to-delete-client-version-policies-by-using-lync-server-control-panel"></a>使用 Lync Server 控制面板删除客户端版本策略

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击 " **客户端**"，然后单击 " **客户端版本策略** 导航" 按钮。

4.  在 " **客户端版本策略** " 页上，选择要删除的客户端版本策略或策略，单击 " **编辑**"，然后单击 " **删除**"。

</div>

<div>

## <a name="deleting-client-version-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 删除客户端版本策略

您可以使用 **CsClientVersionPolicy** cmdlet 删除客户端版本策略。 此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-remove-a-specific-client-version-policy"></a>删除特定的客户端版本策略

  - 此命令将删除应用于 Redmond 站点的客户端版本策略：
    
        Remove-CsClientVersionPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-client-version-policies-applied-to-the-site-scope"></a>删除应用到站点范围的所有客户端版本策略

  - 此命令将删除在站点范围内配置的所有客户端版本策略：
    
        Get-CsClientVersionPolicy -Fiter "site:*" | Remove-CsClientVersionPolicy

</div>

<div>

## <a name="to-remove-client-version-policies-that-do-not-include-a-specific-user-agent"></a>删除不包含特定用户代理的客户端版本策略

  - 此命令将删除任何不包含 Windows Phone Lync (WPLync) 用户代理规则的客户端版本策略：
    
        Get-CsClientVersionPolicy | Where-Object {$_.Rules -notmatch "UserAgent=WPLync" | Remove-CsClientVersionPolicy

</div>

有关详细信息，请参阅 [CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) Cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

