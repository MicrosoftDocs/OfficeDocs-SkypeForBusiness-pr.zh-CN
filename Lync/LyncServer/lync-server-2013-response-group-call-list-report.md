---
title: Lync Server 2013：响应组呼叫列表报告
TOCTitle: 响应组呼叫列表报告
ms:assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg615443(v=OCS.15)
ms:contentKeyID: 49313794
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的响应组呼叫列表报告

 

_**上一次修改主题：** 2015-03-09_

响应组应用程序提供一种可使 Microsoft Lync Server 2013 根据所拨打的号码，以及选择性地根据呼叫者对一系列问题的响应，来应答和路由电话呼叫。通常，不会将响应组呼叫路由到个人，而是路由到称为代理组的一组人员。例如，如果某人呼叫技术支持的电话号码， Lync Server 2013 可以自动将该呼叫路由到第一个可用的技术支持代理。或者， Lync Server 可能会问一系列问题（“如果您有硬件问题，请按 1。如果您有软件问题，请按 2。如果您有网络问题，请按 3。”），然后根据对这些问题的回答，将呼叫路由到最合适的技术支持代理。

响应组呼叫列表报告代表针对指定的时间段和指定的呼叫类型所进行的呼叫集合。响应组使用报告（必需先打开该报告，才能打开响应组呼叫列表报告）可识别以下呼叫类型：

  - **收到的呼叫**。响应组应用程序的所有实例收到的呼叫总数。

  - **成功呼叫**。响应组应用程序所接听的呼叫总数。

  - **提供的呼叫** 。已转接给响应组代理的呼叫总数。

  - **应答的呼叫** 。响应组代理实际应答的呼叫总数。

  - 放弃的呼叫的百分比。响应组应用程序已收到但代理未应答的呼叫的百分比。此值的计算方式为：”收到的呼叫“减去”应答的呼叫“，然后用所得的值除以收到的呼叫数。例如，如果收到了 10 个呼叫，但应答了 7 个，则计算方式是 10 减去 7，得出未应答的呼叫是 3 个。然后用该值除以 10，得出放弃的呼叫的百分比为 30%。

  - **转接的呼叫** 。因队列超时或队列溢出而转接的响应组呼叫总数。

## 访问响应组呼叫列表报告

只能通过单击在 [Lync Server 2013 中的响应组使用情况报告](lync-server-2013-response-group-usage-report.md)上找到的以下其中一个指标来访问响应组呼叫列表报告：

  - 收到的呼叫

  - 成功呼叫

  - 提供的呼叫

  - 应答的呼叫

  - 转接的呼叫

## 充分利用响应组呼叫列表报告

响应组呼叫列表报告允许您将所显示的数据限制为涉及特定响应组工作流的呼叫。为执行此操作，需要在“工作流 URI”框中输入工作流 URI（工作流的 SIP 地址）。但是，您必须实际上能够看到“工作流 URI”框，才能执行此操作。要显示响应组呼叫列表报告的筛选选项，请单击报告窗口左上部分的“显示/隐藏参数”按钮。

请注意，如果将鼠标停留在其中任一指标上，响应组呼叫列表不会显示有关响应代码或诊断 ID 的信息。如果您需要更多信息，则可以注释“响应代码”和/或“诊断 ID”，然后在[Lync Server 2013 中的主要故障报告](lync-server-2013-top-failures-report.md)中搜索这些值。

对于类似如下的问题：“哪个个别工作流收到的呼叫数最多？”，您可以执行以下操作：

1.  在“响应组使用报告”上，设置所需的时间段，然后单击“收到的呼叫”指标。这样即会打开“响应组呼叫列表报告”。

2.  导出“响应组呼叫列表报告”上所显示的数据。例如，可以使用 Microsoft Excel 格式导出数据，然后使用 Excel 将该数据转换为逗号分隔值文件。

3.  使用 Windows PowerShell 运行您的分析。

例如，如果已将数据保存到名为 C:\\Data\\Response\_Group\_Call\_List\_Report.csv 的文件，则可以使用以下命令，针对报告中所列出的每个工作流返回收到的呼叫总数：

    $calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
    $calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending

这将返回与以下类似的信息：

    Count    Name
    -----    ----
      160    Redmond Help Desk
       47    Dublin Help Desk
       31    North America Customer Support
       16    EMEA Customer Support
       14    Employment Opportunities

## 筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于响应组呼叫列表报告的筛选器。

### 响应组呼叫列表报告筛选器

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>名称</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>开始日期</strong></p></td>
<td><p>时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="even">
<td><p><strong>结束日期</strong></p></td>
<td><p>时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>工作流 URI</strong></p></td>
<td><p>允许您限制返回的数据，以便仅显示指定响应组工作流的数据。若要使用该筛选器，请输入工作流 SIP 地址。例如：</p>
<p>sip:helpdesk@litwareinc.com</p></td>
</tr>
<tr class="even">
<td><p><strong>呼叫</strong></p></td>
<td><p>可以选择以下呼叫类型之一：</p>
<ul>
<li><p>收到的呼叫</p></li>
<li><p>成功呼叫</p></li>
<li><p>提供的呼叫</p></li>
<li><p>应答的呼叫</p></li>
<li><p>转接的呼叫</p></li>
</ul></td>
</tr>
</tbody>
</table>


## 指标

下表列出了响应组应用程序收到的每个呼叫的响应组呼叫列表报告中提供的信息。

### 响应组呼叫列表报告指标

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名称</th>
<th>是否可按此项排序？</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>呼叫者</strong></p></td>
<td><p>否</p></td>
<td><p>呼叫者的 SIP 地址</p></td>
</tr>
<tr class="even">
<td><p><strong>工作流</strong></p></td>
<td><p>否</p></td>
<td><p>响应组工作流的 SIP 地址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>开始时间</strong></p></td>
<td><p>否</p></td>
<td><p>呼叫开始的日期和时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>结束时间</strong></p></td>
<td><p>否</p></td>
<td><p>呼叫结束的日期和时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>响应代码</strong></p></td>
<td><p>否</p></td>
<td><p>会话失败时发送的 SIP 响应代码。</p></td>
</tr>
<tr class="even">
<td><p><strong>诊断 ID</strong></p></td>
<td><p>否</p></td>
<td><p>附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。</p></td>
</tr>
</tbody>
</table>

