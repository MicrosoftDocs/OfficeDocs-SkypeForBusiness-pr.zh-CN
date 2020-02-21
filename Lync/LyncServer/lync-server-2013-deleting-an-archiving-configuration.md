---
title: Lync Server 2013：删除存档配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an Archiving configuration
ms:assetid: a8744d39-5cf2-474c-9a99-a0f3a37f846f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205167(v=OCS.15)
ms:contentKeyID: 48185093
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b864bb96ea7d342dbfd449cc9a151b0d7c2dee6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202468"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-configuration-in-lync-server-2013"></a>在 Lync Server 2013 中删除存档配置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

您可以删除站点配置或池配置。 无法删除全局配置。 如果删除全局配置，该配置将自动重置为默认值。 有关如何实施存档配置的详细信息，包括可以指定哪些选项以及存档配置的层次结构，请参阅规划文档、部署文档或操作文档中的[存档在 Lync Server 2013 中的工作原理](lync-server-2013-how-archiving-works.md)。

<div>

## <a name="to-delete-a-site-or-pool-configuration-for-archiving"></a>删除用于存档的站点或池配置

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档配置”**。

4.  在存档配置列表中，单击要删除的站点或池配置，单击 "**编辑**"，然后单击 "**删除**"。

5.  单击“提交”****。

</div>

<div>

## <a name="removing-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 删除存档配置设置

可以使用 Windows PowerShell 和**set-csarchivingconfiguration** cmdlet 删除存档配置设置。 此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>

## <a name="to-remove-a-specified-collection-of-archiving-configuration-settings"></a>删除指定的一组存档配置设置

  - 以下命令将删除应用于 Redmond 站点的存档配置设置：
    
        Remove-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-archiving-configuration-settings-applied-to-the-site-scope"></a>删除应用到站点范围的所有存档配置设置

  - 此命令将删除应用于服务范围的所有存档配置设置：
    
        Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration

</div>

<div>

## <a name="to-remove-archiving-configuration-settings-based-on-a-specified-property-value"></a>根据指定的属性值删除存档配置设置

  - 此命令将删除已禁用 Exchange 存档的所有存档配置设置：
    
        Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration

</div>

有关详细信息，请参阅[set-csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingConfiguration) cmdlet 的帮助主题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的存档工作原理](lync-server-2013-how-archiving-works.md)  


[在 Lync Server 2013 中管理内部和外部通信的存档](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

