---
title: 'Lync Server 2013: 创建或修改 CDR 配置设置的集合'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of CDR configuration settings
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49733812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44ec5383a8050370ba259350aed4528765838b47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改 CDR 配置设置的集合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-23_

利用呼叫详细信息记录 (CDR)，可以跟踪对等即时消息会话、IP 语音 (VoIP) 电话呼叫和会议呼叫等的使用情况。此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。

安装 Microsoft Lync Server 2013 时, 将为你创建单个的 CDR 配置设置的全局集合。 管理员还具有创建站点作用域的自定义设置的选项。 使用这些站点作用域设置时，它们将优先于全局设置。 例如，如果您为 Redmond 站点创建了站点作用域设置，则这些设置（而不是全局设置）将用于管理 Redmond 内的 CDR。

你可以使用 Lync Server 控制面板或[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) CMDLET 创建 CDR 配置设置。 你可以使用 Lync Server 控制面板或[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet 修改现有设置。 如果您使用的是 Lync Server 控制面板来创建或修改设置, 您将可以使用以下选项:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>UI 设置</th>
<th>PowerShell 参数</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>名称</p></td>
<td><p>Identity</p></td>
<td><p>所创建的 CDR 配置设置的唯一标识符。这些设置只能在站点作用域内创建。</p></td>
</tr>
<tr class="even">
<td><p>启用 CDR 监控</p></td>
<td><p>EnableCDR</p></td>
<td><p>指示是否启用 CDR。</p></td>
</tr>
<tr class="odd">
<td><p>启用 CDR 清除</p></td>
<td><p>EnablePurging</p></td>
<td><p>指示是否将定期从 CDR 数据库中删除 CDR 记录。</p></td>
</tr>
<tr class="even">
<td><p>CDR 最长保留期限（天）</p></td>
<td><p>KeepCallDetailForDays</p></td>
<td><p>指示 CDR 记录在 CDR 数据库中保留的天数。任何早于指定天数的记录都将被自动删除。（请注意，仅当启用清除后，才会执行清除操作。）</p></td>
</tr>
<tr class="odd">
<td><p>错误报告数据最长保留期限（天）</p></td>
<td><p>KeepErrorReportForDays</p></td>
<td><p>指示 CDR 错误报告的保留天数。任何早于指定天数的记录都将被自动删除。CDR 错误报告是客户端应用程序上传的诊断报告。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> CsCdrConfiguration 和 CsCdrConfiguration cmdlet 包括 "Lync Server 控制面板" 中不可用的其他选项。 有关详细信息, 请参阅<A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">新的 CsCdrConfiguration</A>和<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">CsCdrConfiguration</A>的帮助主题。



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a>使用 Lync Server "控制面板" 创建 CDR 配置设置

1.  在 Lync Server 控制面板中, 单击 "**监视和存档**"。

2.  在 "**呼叫详细记录**" 选项卡上, 单击 "**新建**"。

3.  在“**选择站点**”对话框中，选择要在其中创建新配置设置的站点。如果该对话框为空，则表示所有站点均已被分配 CDR 配置设置集合。每个站点均限制为只有一个此类集合。在这种情况下，您可以删除设置然后重新创建，也可以只修改现有设置。

4.  在“**新建呼叫详细信息记录 (CDR) 设置**”  对话框中进行所需选择，然后单击“**提交**”。

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a>使用 Lync Server "控制面板" 修改现有 CDR 配置设置

1.  在 Lync Server 控制面板中, 单击 "**监视和存档**"。

2.  双击要修改的设置集合，或选择集合后单击“**编辑**”，然后单击“**显示详细信息**”。 请注意，一次只能修改一个集合。 若要对多个集合进行相同的更改, 请改用 Lync Server 命令行管理程序。

3.  在“**编辑呼叫详细信息记录 (CDR) 设置**”对话框中进行所需选择，然后单击“**提交**”。

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 创建 CDR 配置设置

你可以创建 CDR 配置设置, 也可以使用 Windows PowerShell 和**CsCdrConfiguration** cmdlet 创建 CDR 配置设置。 你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>创建新的 CDR 配置设置集合

  - 以下命令将创建新的应用于 Redmond 站点的 CDR 配置设置集合：
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>创建可禁用呼叫详细信息记录的 CDR 配置设置集合

  - 由于上述命令中未指定参数（不包括必需的 Identity 参数），新的配置设置集合的所有属性都将使用默认值。要创建使用不同属性值的设置，只需包含相应的参数和参数值。例如，要创建默认情况下允许禁用呼叫详细信息记录的呼叫详细信息配置设置集合，请使用如下命令：
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>在创建新的 CDR 配置设置集合时指定多个属性值

  - 您可以通过包含多个参数来修改多个属性值。例如，以下命令将新设置配置为将呼叫详细信息记录保留 30 天，而将错误报告保留 90 天：
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

有关详细信息, 请参阅[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

