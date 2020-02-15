---
title: Lync Server 2013：删除存档策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an Archiving policy
ms:assetid: 4739a691-41cc-4128-8bb8-6d5a4c02107a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520989(v=OCS.15)
ms:contentKeyID: 48184043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bde8694cb5249cd5c284bfadc89d9784ca76ac31
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-policy-in-lync-server-2013"></a>在 Lync Server 2013 中删除存档策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

可以删除用户策略或站点策略。 无法删除全局策略。 如果您尝试删除全局策略，Lync Server 2013 会自动将策略重置为默认值。

<div>


> [!NOTE]  
> 如果为您的部署启用了 Microsoft Exchange 集成，Exchange 策略将控制是否为驻留在 Exchange 2013 上的用户启用存档，并将其邮箱置于就地保留状态。 有关详细信息，请参阅部署文档中的<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 集成时，请参阅在 Lync Server 2013 中设置存档策略</A>。



</div>

<div>

## <a name="to-delete-a-user-or-site-policy-for-archiving"></a>删除用户存档策略或站点存档策略

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档策略”**。

4.  在存档策略列表中，单击要删除的用户策略或站点策略，再单击“编辑”****，然后单击“删除”****。

5.  单击“提交”****。

</div>

<div>

## <a name="removing-archiving-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 删除存档策略

可以使用 Windows PowerShell 和**new-csarchivingpolicy** cmdlet 删除存档策略。 此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>

## <a name="to-remove-a-specified-archiving-policy"></a>删除指定的存档策略

  - 作为示例，**Remove-CsArchivingPolicy** 删除了 Identity 为 site:Redmond 的策略。请注意，删除站点作用域的策略时，全局存档策略将自动控制网站策略之前管理的用户。以下命令删除适用于 Redmond 站点的策略：
    
        Remove-CsArchivingPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-applied-to-the-per-user-scope"></a>删除应用于每用户作用域的所有存档策略

  - 此命令将删除所有适用于每用户范围的存档策略：
    
        Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-that-disable-internal-archiving"></a>删除禁用内部存档的所有存档策略

  - 此命令将删除其中禁用了内部存档的所有存档策略：
    
        Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy

</div>

有关详细信息，请参阅[new-csarchivingpolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) cmdlet 的帮助主题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中管理内部和外部通信的存档](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

