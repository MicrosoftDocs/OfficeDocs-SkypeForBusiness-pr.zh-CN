---
title: 创建或修改 CDR 配置设置的集合
TOCTitle: 创建或修改 CDR 配置设置的集合
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49888605
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 创建或修改 CDR 配置设置的集合

 

_**上一次修改主题：** 2015-03-09_

利用呼叫详细信息记录 (CDR)，可以跟踪对等即时消息会话、IP 语音 (VoIP) 电话呼叫和会议呼叫等的使用情况。此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。

当安装 Microsoft Lync Server 2013 时，将为您创建一个全局的 CDR 配置设置集合。管理员还可以在站点作用域内创建自定义设置。无论何时使用这些站点作用域的设置，它们都优先于全局设置。例如，如果为 Redmond 站点创建了站点作用域的设置，则这些设置（不是全局设置）将用于管理 Redmond 中的 CDR。

您可以使用 Lync Server 控制面板或 [New-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCdrConfiguration) cmdlet 创建 CDR 配置设置。可以使用 Lync Server 控制面板或 [Set-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCdrConfiguration) cmdlet 修改现有设置。如果使用 Lync Server 控制面板创建或修改设置，可使用以下选项：


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
<td><p>指示是否定期从 CDR 数据库中删除 CDR 记录。</p></td>
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


> [!NOTE]  
> New-CsCdrConfiguration 和 Set-CsCdrConfiguration cmdlet 包括 Lync Server 控制面板中未提供的其他选项。有关详细信息，请参阅 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</a> 和 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</a> 帮助主题。



## 使用 Lync Server 控制面板创建 CDR 配置设置

1.  在 Lync Server 控制面板中单击“监控和存档”。

2.  在“呼叫详细信息记录”选项卡上，单击“新建”。

3.  在“选择站点”对话框中，选择要在其中创建新配置设置的站点。如果该对话框为空，则表示所有站点均已被分配 CDR 配置设置集合。每个站点均限制为只有一个此类集合。在这种情况下，您可以删除设置然后重新创建，也可以只修改现有设置。

4.  在“新建呼叫详细信息记录(CDR)设置”对话框中进行所需选择，然后单击“提交”。

## 使用 Lync Server 控制面板修改现有 CDR 配置设置

1.  在 Lync Server 控制面板中单击“监控和存档”。

2.  双击要修改的设置集合，或选择集合后单击“编辑”，然后单击“显示详细信息”。请注意，一次只能修改一个集合。要对多个集合进行相同更改，请改用 Lync Server 命令行管理程序。

3.  在“编辑呼叫详细信息记录(CDR)设置”对话框中进行所需选择，然后单击“提交”。

## 使用 Lync Server 命令行管理程序 cmdlet 创建 CDR 配置设置

您还可以使用 Windows PowerShell 和 **New-CsCdrConfiguration** cmdlet 创建 CDR 配置设置。可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 创建新的 CDR 配置设置集合

  - 以下命令将创建新的应用于 Redmond 站点的 CDR 配置设置集合：
    
        New-CsCdrConfiguration -Identity "site:Redmond"

## 创建可禁用呼叫详细信息记录的 CDR 配置设置集合

  - 由于上述命令中未指定参数（不包括必需的 Identity 参数），新的配置设置集合的所有属性都将使用默认值。要创建使用不同属性值的设置，只需包含相应的参数和参数值。例如，要创建默认情况下允许禁用呼叫详细信息记录的呼叫详细信息配置设置集合，请使用如下命令：
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

## 在创建新的 CDR 配置设置集合时指定多个属性值

  - 您可以通过包含多个参数来修改多个属性值。例如，以下命令将新设置配置为将呼叫详细信息记录保留 30 天，而将错误报告保留 90 天：
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

有关详细信息，请参阅 [New-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCdrConfiguration) cmdlet 的帮助主题。

