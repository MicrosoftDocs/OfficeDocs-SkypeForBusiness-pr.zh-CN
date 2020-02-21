---
title: Lync Server 2013：删除现有会议策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing conferencing policy
ms:assetid: 709ed771-790f-4bf1-a4de-b37ca5168688
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688089(v=OCS.15)
ms:contentKeyID: 49733688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 679d88a1d359ea9590262d78e49ab8fa7fbc3906
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202668"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-conferencing-policy-in-lync-server-2013"></a>在 Lync Server 2013 中删除现有会议策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

按照以下步骤删除用户级别或站点级别的会议策略。

<div>


> [!NOTE]  
> 无法删除全局会议策略。



</div>

<div>

## <a name="to-delete-a-site-or-user-conferencing-policy"></a>删除站点或用户会议策略

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“会议”****，然后单击“会议策略”****。

4.  在会议策略列表中，单击要删除的站点或用户策略，单击 "**编辑**"，然后单击 "**删除**"。

</div>

<div>

## <a name="removing-conferencing-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 删除会议策略

您可以使用 Lync Server 命令行管理程序和**set-csconferencingpolicy** cmdlet 删除会议策略。 您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>

## <a name="to-remove-a-specified-conferencing-policy"></a>删除指定会议策略

  - 以下命令删除 Identity 为 RedmondConferencingPolicy 的会议策略：
    
        Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-policies-applied-to-the-per-user-scope"></a>删除适用于每用户范围的所有会议策略

  - 以下命令删除在每用户范围配置的所有会议策略：
    
        Get-CsConferencingPolicy -Filter "tag:*" | Remove-CsConferencingPolicy

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-polices-that-allow-recording-by-external-users"></a>删除允许外部用户记录的所有会议策略

  - 以下命令删除允许外部用户记录会议的所有会议策略：
    
        Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy

</div>

有关详细信息，请参阅[set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsConferencingPolicy)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

