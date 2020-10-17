---
title: Lync Server 2013：创建体验质量配置设置
description: Lync Server 2013：创建经验丰富的配置设置的质量。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Quality of Experience configuration settings
ms:assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521006(v=OCS.15)
ms:contentKeyID: 48184357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 279265f396fc8fcbfba80d195fc587924a2979f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562188"
---
# <a name="create-quality-of-experience-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中创建体验质量配置设置

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

用户体验质量 (QoE) 指标跟踪组织中发出的语音和视频呼叫的质量，包括网络数据包丢失数目、背景噪音、“抖动”量（数据包延迟的差异）等。这些指标与其他数据（如呼叫详细信息记录）分开存储在一个数据库中，这样您就可以独立于其他数据记录启用和禁用 QoE。

安装 Microsoft Lync Server 2013 时，将为您创建一个 QoE 配置设置的单一全局集合。 管理员还可以选择在站点范围创建自定义设置。 无论何时使用这些站点范围的设置，它们都优先于全局设置。 例如，如果您为 Redmond 站点创建了站点作用域设置，则这些设置 (而不是全局设置) 将用于管理 Redmond 中的 QoE。

可以使用 Lync Server 控制面板或 [new-csqoeconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) Cmdlet 创建 QoE 配置设置。 如果您使用 Lync Server 控制面板创建新设置，以下选项将对您可用：


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
<td><p>要创建的设置的唯一标识符。 QoE 配置设置只能在网站范围内创建。</p></td>
</tr>
<tr class="even">
<td><p>启用对 QoE 数据的监视</p></td>
<td><p>EnableQoE</p></td>
<td><p>指定是否收集 QoE 记录并将其保存到监控数据库。</p></td>
</tr>
<tr class="odd">
<td><p>启用清除 QoE 数据</p></td>
<td><p>EnablePurging</p></td>
<td><p>指定在 "保持 QoE 数据" 中定义的持续时间 <strong> (天) </strong> 属性已过，是否将清除记录。</p></td>
</tr>
<tr class="even">
<td><p>保留 QoE 数据的最长持续时间 (天) </p></td>
<td><p>KeepQoEDataForDays</p></td>
<td><p>QoE 数据在从数据库中清除之前将存储的天数。 如果禁用清除，则忽略此值。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> New-CsQoEConfiguration cmdlet 包括 Lync Server 控制面板中不可用的其他选项。 有关详细信息，请参阅 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">new-csqoeconfiguration</A> 帮助主题。



</div>

<div>

## <a name="to-create-qoe-configuration-settings-by-using-lync-server-control-panel"></a>使用 Lync Server 控制面板创建 QoE 配置设置

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅 [Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“监控和存档”****，然后单击“用户体验质量数据”****。

4.  在 " **体验质量数据** " 页上，单击 " **新建**"。

5.  在 " **选择站点**" 中，单击要应用该策略的站点，然后单击 **"确定"**。

6.  在 " **新体验质量设置**" 中，执行以下操作：
    
      - 选择 " **启用对 QoE 数据的监视** " 以启用监控。
    
      - 选择 " **启用对 QoE 数据的清除** " 以启用清除。
    
      - 在 " **保持 QoE 的最长持续时间 (天) **中，选择应保留 QoE 记录的最大天数。

7.  单击“提交”****。

</div>

<div>

## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 创建 QoE 配置设置

您可以使用 Windows PowerShell 和 New-CsQoEConfiguration cmdlet 创建 QoE 配置设置。 您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>创建新的 QoE 配置设置集合

  - 此命令将创建应用于 Redmond 站点的 QoE 配置设置的新集合：
    
        New-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>创建新的 QoE 配置设置集合，其中禁用了 QoE 监视

  - 由于在上述命令中未指定参数（不包括必需的 Identity 参数），新的配置设置集合的所有属性都将使用默认值。 要创建使用不同属性值的设置，只需包含相应的参数和参数值。 例如，若要创建 "体验质量" 配置设置的集合，默认情况下，允许禁用 QoE 录制时，请使用如下所示的命令：
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>在创建新的 QoE 配置设置集合时指定多个属性值

  - 您可以通过包含多个参数来使用多个属性值。 例如，以下命令将新设置配置为将 QoE 数据保留30天，并在 3:00 AM 处清除旧数据：
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

</div>

有关详细信息，请参阅 [new-csqoeconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

