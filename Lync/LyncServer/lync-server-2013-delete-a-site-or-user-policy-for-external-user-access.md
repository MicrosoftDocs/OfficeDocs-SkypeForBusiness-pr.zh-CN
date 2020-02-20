---
title: Lync Server 2013：删除用于外部用户访问的站点或用户策略
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
ms.openlocfilehash: dc50d2738329fd1ce9e07406b7b7212394257883
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-site-or-user-policy-for-external-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中删除用于外部用户访问的站点或用户策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-22_

您可以删除在 "**外部访问策略**" 页上的 "Lync Server 控制面板" 中列出的任何站点或用户策略。 删除全局策略时不会真正删除该策略，而只是将其重置为不支持任何外部用户访问选项的默认设置。 有关重置全局策略的详细信息，请参阅[在 Lync Server 2013 中重置外部用户访问的全局策略](lync-server-2013-reset-the-global-policy-for-external-user-access.md)。

<div>

## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>删除外部用户访问的站点或用户策略

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  单击“外部用户访问”****，再单击“外部访问策略”****。

4.  在“外部访问策略”**** 选项卡上，单击要删除的站点或用户策略，再单击“编辑”****，然后单击“删除”****。

5.  当系统提示您确认删除时，单击“确定”****。

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 删除 PIN 策略

可以使用 Windows PowerShell 和 Set-csexternalaccesspolicy cmdlet 删除外部访问策略。 此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>

## <a name="to-remove-a-specific-external-access-policy"></a>删除特定的外部访问策略

  - 此命令删除适用于 Redmond 站点的外部访问策略：
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>删除应用于每用户作用域的所有外部访问策略

  - 此命令删除在每用户范围配置的所有外部访问策略：
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>删除在禁用外部用户访问的所有外部访问策略

  - 此命令删除已禁用外部用户访问的所有外部访问策略：
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy

</div>

有关详细信息，请参阅[set-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

