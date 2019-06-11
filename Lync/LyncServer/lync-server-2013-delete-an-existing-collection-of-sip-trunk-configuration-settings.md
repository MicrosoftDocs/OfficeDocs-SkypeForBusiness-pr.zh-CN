---
title: 删除现有 SIP 中继配置设置的集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of SIP trunk configuration settings
ms:assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688024(v=OCS.15)
ms:contentKeyID: 49733614
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b896d53760184d15b02afed14b8a9c0d660f96b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-lync-server-2013"></a>删除 Lync Server 2013 中的现有 SIP 中继配置设置集合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-22_

SIP 中继配置设置定义了在服务提供商处中介服务器和公共交换电话网络 (PSTN) 网关、IP 公共分支 exchange (PBX) 或会话边界控制器 (SBC) 之间的关系和能力。 这些设置可执行如下所指定内容的操作：

  - 是否在中继上启用媒体旁路功能。

  - 发送实时传输控制协议 (RTCP) 数据包的条件。

  - 每个主干上是否需要安全的实时协议 (SRTP) 加密。

安装 Microsoft Lync Server 2013 时, 将为你创建一个全局 SIP 中继配置设置集合。 此全局集合设置无法删除。 但是, 你可以使用 Lync Server 控制面板或[new-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) cmdlet 将全局集合中的属性 "重置" 为其默认值。 例如，如果已将 Enable3pccRefer 属性设置为 True，则当您重置全局集合时，Enable3pccRefer 属性将还原为其默认值 False。

管理员还可以在站点作用域或服务作用域（针对单个 PSTN 网关）创建自定义中继配置设置；这些自定义设置可以删除。在删除这些自定义设置时，请注意以下事项：

  - 如果删除了服务作用域设置，由这些设置管理的 SIP 中继将由应用于这些站点的设置（如果存在）管理。如果站点设置不存在，这些中继随后会由中继配置设置的全局集合管理。

  - 如果删除了站点作用域设置，由这些设置管理的任何 SIP 中继都将立即由中继配置设置的全局集合管理。

<div>

## <a name="to-remove-trunk-configuration-settings-with-lync-server-control-panel"></a>通过 Lync Server 控制面板删除中继配置设置

1.  在 "Lync Server 控制面板" 中, 单击 "**语音路由**", 然后单击 "**中继配置**"。

2.  在“Trunk 配置”**** 选项卡上，选择要删除的 SIP 中继配置设置的集合，单击“编辑”****，然后单击“删除”****。若要在同一操作中删除多个集合，请单击第一个要删除的集合，然后按住 Ctrl 键并单击任何其他要删除的集合。

3.  集合的“状态”**** 属性将更新为“未提交”****。若要提交更改和删除集合，请单击“提交”****，然后单击“全部提交”****。

4.  在“未提交的语音配置设置”**** 对话框中，单击“确定”****。

5.  在 " **Microsoft Lync Server 2013 控制面板**" 对话框中, 单击 **"确定"**。

6.  If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**. 当显示 " **Microsoft Lync Server 2013 控制面板**" 对话框时, 单击 **"确定"**。

</div>

<div>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 删除中继配置设置

你可以使用 Windows PowerShell 和**new-cstrunkconfiguration** cmdlet 删除中继配置设置。 你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-remove-a-specified-collection-of-settings"></a>删除指定的设置集合

  - 以下命令将删除应用于 Redmond 站点的中继配置设置：
    
        Remove-CsTrunkConfiguration -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>删除适用于站点范围的所有集合

  - 以下命令将删除应用于服务作用域的所有中继配置设置：
    
        Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration

</div>

<div>

## <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>删除启用了媒体旁路的所有集合

  - 以下命令将删除启用了媒体旁路的所有中继配置设置：
    
        Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration

</div>

有关详细信息, 请参阅[new-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

