---
title: Lync Server 2013：删除外部用户访问的站点或用户策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a site or user policy for external user access
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b928fcb1347fdbc89099a5b0dc649deefffa19e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-site-or-user-policy-for-external-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中删除外部用户访问的站点或用户策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-22_

你可以删除 "**外部访问策略**" 页面上 "Lync Server 控制面板" 中列出的任何网站或用户策略。 删除全局策略实际上并不会将其删除，而只是将其重置为默认设置，而不包括对任何外部用户访问选项的支持。 有关重置全局策略的详细信息，请参阅[在 Lync Server 2013 中重置外部用户访问的全局策略](lync-server-2013-reset-the-global-policy-for-external-user-access.md)。

<div>

## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>删除用于外部用户访问的网站或用户策略

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  单击 "**外部用户访问**"，单击 "**外部访问策略**"。

4.  在 "**外部访问策略**" 选项卡上，单击要删除的网站或用户策略，单击 "**编辑**"，然后单击 "**删除**"。

5.  当系统提示确认删除时，单击 **"确定"**。

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 删除 PIN 策略

可以使用 Windows PowerShell 和 CsExternalAccessPolicy cmdlet 删除外部访问策略。 此 cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-remove-a-specific-external-access-policy"></a>删除特定的外部访问策略

  - 此命令将删除应用于 Redmond 网站的外部访问策略：
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>删除应用到每用户范围的所有外部访问策略

  - 此命令将删除在每个用户范围内配置的所有外部访问策略：
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>删除禁用外部用户访问权限的所有外部访问策略

  - 此命令将删除在禁用外部用户访问权限的所有外部访问策略：
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy

</div>

有关详细信息，请参阅[CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

