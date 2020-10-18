---
title: Lync Server 2013：创建或修改 CDR 配置设置的集合
description: Lync Server 2013：创建或修改 CDR 配置设置的集合。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of CDR configuration settings
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49733812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ba911607db55a7b7206645495e70a27ed453784
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578328"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改 CDR 配置设置的集合

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

Call (CDR) 的详细记录使您能够跟踪对等即时消息会话的使用情况，如对等即时消息会话、网络语音协议 (VoIP) 电话联络和会议呼叫等内容。 此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。

安装 Microsoft Lync Server 2013 时，将为您创建一个 CDR 配置设置的全局集合。 管理员还可以选择在站点范围创建自定义设置。 无论何时使用这些站点范围的设置，它们都优先于全局设置。 例如，如果您为 Redmond 站点创建了网站范围的设置，则这些设置 (而不是全局设置) 将用于管理 Redmond 中的 CDR。

您可以使用 Lync Server 控制面板或 [set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) CMDLET 创建 CDR 配置设置。 您可以使用 Lync Server 控制面板或 [set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet 修改现有设置。 如果您使用 Lync Server 控制面板创建或修改设置，将对您可用以下选项：


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
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>标识</p></td>
<td><p>正在创建的 CDR 配置设置的唯一标识符。 这些设置只能在站点范围创建。</p></td>
</tr>
<tr class="even">
<td><p>启用对 Cdr 的监视</p></td>
<td><p>EnableCDR</p></td>
<td><p>指示是否启用 CDR。</p></td>
</tr>
<tr class="odd">
<td><p>启用清除 Cdr</p></td>
<td><p>EnablePurging</p></td>
<td><p>指示是否将定期从 CDR 数据库中删除 CDR 记录。</p></td>
</tr>
<tr class="even">
<td><p>将 Cdr 保留最长持续 (天) </p></td>
<td><p>KeepCallDetailForDays</p></td>
<td><p>指示 CDR 记录将保留在 CDR 数据库中的天数。 早于指定天数的任何记录将自动删除。  (请注意，仅在启用了清除功能时才会进行清除。 ) </p></td>
</tr>
<tr class="odd">
<td><p>将错误报告数据的最长持续时间 (天) </p></td>
<td><p>KeepErrorReportForDays</p></td>
<td><p>指示保留了 CDR 错误报告的天数。 将自动删除早于指定天数的任何报告。 CDR 错误报告是由客户端应用程序上传的诊断报告。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> New-CsCdrConfiguration 和 Set-CsCdrConfiguration cmdlet 包括 Lync Server 控制面板中不可用的其他选项。 有关详细信息，请参阅 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">set-cscdrconfiguration</A> 和 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">set-cscdrconfiguration</A> 帮助主题。



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a>使用 Lync Server 控制面板创建 CDR 配置设置

1.  在 Lync Server 控制面板中，单击 " **监控和存档**"。

2.  在 " **呼叫详细信息记录** " 选项卡上，单击 " **新建**"。

3.  在 " **选择站点** " 对话框中，选择要在其中创建新配置设置的站点。 如果对话框为空，则表示已为您的所有网站分配 CDR 配置设置的集合。 每个网站仅限于单个此类集合。 在这种情况下，您可以删除并重新创建设置，也可以只修改现有设置。

4.  在 " **新呼叫详细信息记录" (CDR) 设置** "对话框中，执行所需的选择，然后单击" **提交**"。

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a>使用 Lync Server 控制面板修改现有 CDR 配置设置的具体方法

1.  在 Lync Server 控制面板中，单击 " **监控和存档**"。

2.  双击要修改的设置集合，或选择该集合，单击 " **编辑**"，然后单击 " **显示详细信息**"。 请注意，一次只能修改一个集合。 若要对多个集合进行相同的更改，请改用 Lync Server 命令行管理程序。

3.  在 " **编辑呼叫详细信息记录" (CDR) 设置** "对话框中，执行所需的选择，然后单击" **提交**"。

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 创建 CDR 配置设置

您可以创建 CDR 配置设置，也可以使用 Windows PowerShell 和 **set-cscdrconfiguration** cmdlet 创建。 您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>创建新的 CDR 配置设置集合

  - 此命令将创建应用于 Redmond 站点的 CDR 配置设置的新集合：
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>创建禁用呼叫详细信息记录的 CDR 配置设置的集合

  - 由于在上述命令中未指定参数（不包括必需的 Identity 参数），新的配置设置集合的所有属性都将使用默认值。 要创建使用不同属性值的设置，只需包含相应的参数和参数值。 例如，若要创建呼叫详细信息配置设置的集合，默认情况下允许禁用呼叫详细信息记录，请使用类似如下的命令：
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>在创建新的 CDR 配置设置集合时指定多个属性值

  - 您可以通过包含多个参数来修改多个属性值。 例如，以下命令将新设置配置为将呼叫详细信息记录保留30天，错误报告为90天：
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

有关详细信息，请参阅 [set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

