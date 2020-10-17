---
title: Lync Server 2013：响应组使用情况报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group Usage Report
ms:assetid: 3248b320-a552-400a-8485-6891af4eb0f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558632(v=OCS.15)
ms:contentKeyID: 48183811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 649fb55f6c7b698986c4c31057b3a0a8f1b00a76
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511619"
---
# <a name="response-group-usage-report-in-lync-server-2013"></a>Lync Server 2013 中的响应组使用情况报告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-22_

响应组应用程序为 Microsoft Lync Server 2013 提供了一种方法，以根据拨打的号码和呼叫者对一系列问题的响应（可选）应答和路由电话呼叫。 通常，响应组呼叫不路由到单个人员，而是路由到称为代理组的一组人员。 例如，如果有人呼叫帮助台的电话号码，Lync Server 2013 可以自动将该呼叫路由到第一个可用的技术支持代理。 或者，如果遇到硬件问题，Lync Server 可以 ( "请按1来提出一系列问题。 如果您有软件问题，请按 2。 如果遇到网络问题，请按3。) ，然后根据这些问题的答案将呼叫路由到最合适的技术支持代理。

响应组使用情况报告提供所有响应组工作流接收到的电话呼叫数的详细信息，然后将这些呼叫细分为更多有限类别，例如发起的呼叫、应答的呼叫和放弃的呼叫。

使用响应组使用情况报告的关键是了解报告的呼叫类型之间的差别：

  - **收到的呼叫**。响应组应用程序的所有实例收到的呼叫总数。

  - **成功呼叫**。 响应组应用程序选取的呼叫总数。

  - **发起的呼叫**。转接到响应组代理的呼叫总数。

  - **应答的呼叫**。响应组代理实际应答的呼叫总数。

  - **放弃的呼叫的百分比**。响应组应用程序已收到但代理未应答的呼叫的百分比。此值的计算方法是用“收到的呼叫数”减去“应答的呼叫数”，然后用所得的值除以收到的呼叫数。例如，如果收到 10 个呼叫，但应答了 7 个，则计算方法是 10 减去 7，得出未应答的呼叫是 3 个。然后用该值除以 10，得出放弃的呼叫的百分比为 30%。

  - **转接的呼叫**。因队列超时或队列溢出而转接的响应组呼叫总数。

如果您在查看响应组使用情况报告时想不起来其中任何呼叫类型的定义，只需将鼠标放在相应的呼叫类型标签上。将显示工具提示来提供呼叫类型的简要说明。

可通过响应组使用情况报告筛选工作流 URI（与该工作流关联的 SIP 地址）。不过，该报告中实际上并不显示工作流 URI。如果您希望了解哪些工作流应答最多的呼叫或哪些工作流遇到最多的转接呼叫等事项，请单击相应指标以打开该给定时间段内的响应组呼叫列表报告。该报告列出了工作流 URI。

<div>

## <a name="accessing-the-response-group-usage-report"></a>访问响应组使用情况报告

可从监控报告主页访问响应组使用情况报告。 您可以通过单击以下任一指标深入到 [Lync Server 2013 中的响应组呼叫列表报告](lync-server-2013-response-group-call-list-report.md) ：

  - 收到的呼叫

  - 成功呼叫

  - 发起的呼叫

  - 应答的呼叫

  - 转接的呼叫

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-usage-report"></a>充分利用响应组使用情况报告

响应组使用情况报告的值得关注的用途之一可能不是显而易见的：能够检索单个响应组工作流的使用情况信息。

<div>


> [!WARNING]  
> 响应组工作流基本上是一组指示用户拨打特定电话号码时的 Lync Server 应执行的操作的说明。 为此，每个工作流都与一个电话号码唯一关联。 当某人调用该号码时，工作流会确定如何处理呼叫。 例如，工作流可能会导致呼叫路由到一系列互动语音响应 (IVR) 提示呼叫者输入其他信息的问题 ( "按1以获得硬件支持。 按 2 以获取软件支持”）。 或者，工作流可能会导致呼叫放置在队列中，呼叫者将保留在队列中，直到有代理可用于应答呼叫。 工作流也可指示是否有代理能够应答呼叫：工作流用于配置工作时间（代理在一周中的哪几天、一天中的哪些时段能够应答呼叫）和假日（代理无法应答呼叫的日期）。 无论何时拨打属于响应组应用程序的电话号码，实际上都会调用响应组工作流。



</div>

虽然工作流 URI 不显示在响应组使用情况报告中，但仍可以查看单个工作流的使用情况统计信息，这通常极其有用。例如，假定您最近开展了一项新的广告活动并很想知道人们是否通过电话询问该产品。如果您已将响应组工作流与广告活动中提供的电话号码相关联，则可以轻松地查看有多少人（如果有）呼叫了该号码。

您可能还使用类似的方法来测量内部技术支持或客户服务部门处理的呼叫数。

若要查看特定工作流的使用情况统计信息，请在“工作流 URI”框中输入工作流 URI。 当然，正如上文所述，工作流 URI（与工作流关联的 SIP 地址）不显示在报告上。 这意味着您需要查找某种其他方法来确定工作流的 URI。 执行此操作的一种方法是使用 Windows PowerShell 和 Lync Server 命令行管理程序。 例如，以下命令返回您的所有响应组工作流的 URI：

    Get-CsRgsWorkflow | Select-Object Name, PrimaryUri

它将返回类似以下内容的数据：

    Name                            PrimaryUri
    ----                            ----------
    Customer Support                sip:support@litwareinc.com
    Help Desk                       sip:helpdesk@litwareinc.com
    New Ad Campaign                 sip:newads@litwareinc.com

以下命令返回名为“New Ad Campaign”的单个工作流的信息：

    Get-CsRgsWorkflow -Name "New Ad Campaign" | Select-Object Name, PrimaryUri

</div>

<div>

## <a name="filters"></a>筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，通过响应组使用情况报告，您可以查看所有响应组工作流的数据，也可以查看单个工作流的数据。您还可以选择数据的分组方式。在此示例中，将按小时、日、周或月对使用情况进行分组。

下表列出了可用于响应组使用情况报告的筛选器。

### <a name="response-group-usage-report-filters"></a>响应组使用情况报告筛选器

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
<td><p><strong>From</strong></p></td>
<td><p>时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Interval</strong></p></td>
<td><p>时间间隔。选择下列选项之一：</p>
<ul>
<li><p>每小时（最多可显示 25 个小时）</p></li>
<li><p>每天（最多可显示 31 天）</p></li>
<li><p>每周（最多可显示 12 周）</p></li>
<li><p>每月（最多可显示 12 个月）</p></li>
</ul>
<p>如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。例如，如果选择的开始日期为 8/7/2012、结束日期为 9/28/2012、间隔为“每天”，则显示从 8/7/2012 12:00 AM 到 9/7/2012 12:00 AM 这些天的数据（即总共 31 天的数据）。</p></td>
</tr>
<tr class="even">
<td><p><strong>工作流 URI</strong></p></td>
<td><p>允许您限制返回的数据，以便仅显示指定响应组工作流的数据。若要使用该筛选器，请输入工作流 SIP 地址。例如：</p>
<p>sip:helpdesk@litwareinc.com</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指标

下表列出了响应组使用情况报告中提供的信息。

### <a name="response-group-usage-report-metrics"></a>响应组使用情况报告指标

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
<td><p><strong>每小时</strong></p>
<p><strong>每天</strong></p>
<p><strong>每周</strong></p>
<p><strong>每月</strong></p></td>
<td><p>否</p></td>
<td><p>指示所选的时间间隔。如果适用，可单击某一给定的时间间隔以查看该间隔的详细信息。例如，如果使用“每天”间隔并单击 7/7/2012，可查看当日用户注册活动的每小时细分信息。</p></td>
</tr>
<tr class="even">
<td><p><strong>收到的呼叫</strong></p></td>
<td><p>否</p></td>
<td><p>响应组应用程序的所有实例收到的呼叫总数。单击此项时，报告向您显示所选时间段的响应组呼叫列表报告。</p></td>
</tr>
<tr class="odd">
<td><p><strong>成功呼叫</strong></p></td>
<td><p>否</p></td>
<td><p>响应组应用程序接听的呼叫总数。单击此项时，报告向您显示所选时间段的响应组呼叫列表报告。</p></td>
</tr>
<tr class="even">
<td><p><strong>提供的呼叫</strong></p></td>
<td><p>否</p></td>
<td><p>转接到响应组代理的呼叫总数。单击此项时，报告向您显示所选时间段的响应组呼叫列表报告。</p></td>
</tr>
<tr class="odd">
<td><p><strong>应答的呼叫</strong></p></td>
<td><p>否</p></td>
<td><p>响应组代理实际应答的呼叫总数。单击此项时，报告向您显示所选时间段的响应组呼叫列表报告。</p></td>
</tr>
<tr class="even">
<td><p><strong>放弃的呼叫的百分比</strong></p></td>
<td><p>否</p></td>
<td><p>响应组应用程序已收到但代理未应答的呼叫总数。它的计算方法是“收到的呼叫”减去“应答的呼叫”，然后用所得的值除以收到的呼叫数。例如，如果收到了 10 个呼叫，但应答了 7 个，则计算方式是 10 减去 7，得出未应答的呼叫是 3 个。然后用该值除以 10，得出放弃的呼叫的百分比为 30%。</p></td>
</tr>
<tr class="odd">
<td><p><strong>代理的平均呼叫分钟数</strong></p></td>
<td><p>否</p></td>
<td><p>响应组代理应答一个呼叫平均所用的时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>转接的呼叫</strong></p></td>
<td><p>否</p></td>
<td><p>因队列超时或队列溢出而转接的响应组呼叫总数。单击此项时，报告向您显示所选时间段的响应组呼叫列表报告。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

