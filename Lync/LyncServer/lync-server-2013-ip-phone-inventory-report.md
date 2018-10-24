---
title: Lync Server 2013：IP 电话清单报告
TOCTitle: IP 电话清单报告
ms:assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg615027(v=OCS.15)
ms:contentKeyID: 49313884
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 IP 电话清单报告

 

_**上一次修改主题：** 2015-03-09_

IP 电话清单报告会报告有关您的组织中目前所使用的 IP 电话的信息。IP 清单报告提供了在指定的报告期间实际上所使用的详细 IP 电话列表。除此之外，管理员还可以通过此报告了解是否存在应进行替换但仍在使用中的任何旧的、过时的电话；该报告还可以就组织中存在很少使用的昂贵电话这一实际情况，向管理员发出警报。当应该购买新电话或重新分配现有的电话时，该类型的信息非常重要。（例如，可能要求很少使用其昂贵电话的用户与较为频繁使用其电话的用户交换电话。）

值得注意的是，此报告在用作真正的清单报告时存在几点限制。首先，IP 电话报告只会列出在指定的时间段内已登录到 Lync Server 的所有电话（按其上次登录时间排序）。如果某个电话在指定的时间段内未登录，那么就不会在清单报告中列出。这包括在该时间段开始前已登录并且在指定的时间间隔内仍保持登录的电话。例如，假设您想要查看 2012 年 7 月的所有电话清单。同时假设在 2012 年 6 月 30 日有多个电话登录到 Lync Server，并且截至到 7 月 1 日为止仍处于登录状态。这些电话将不会在 7 月 1 日的清单报告上出现。

还必须注意的是，清单报告可能包括您的组织不再使用的电话。例如，假设在 2012 年 7 月 1 日有许多 Fabrikam 电话登录到系统；5 天后，您的组织清除了所有这些 Fabrikam 电话并将它们替换为较新的 Contoso 模型。Fabrikam 电话仍会显示在“清单”报告中，原因很简单，就是它们在 7 月份已登录到系统。

此外，IP 电话清单报告不会报告不同类型的电话总数摘要。例如，假设您拥有 105 个 Polycom CX600 电话。该报告不会告知您拥有 105 个此类电话；相反，您只会看到 105 个单独的 Polycom Cx600 条目。知道有 105 个 Polycom Cx600 条目的唯一方法是手动计算其中每一个条目。

> [!WARNING]
> 或者，导出数据，然后使用 Microsoft Excel 或 Windows PowerShell 为您进行计数。


## 访问 IP 电话清单报告

可以从“监控报告”主页访问 IP 电话清单报告。如果您单击“用户 URI”指标，即可访问该用户的“用户活动报告”。针对对等呼叫单击“最后一次活动”指标，会将您带到“对等会话详细信息报告”；针对会议单击相同的指标，会将您带到“会议详细信息报告”。

## 充分利用 IP 电话清单报告

如果您只对某特定类型的电话的使用信息（例如，“用户多久使用一次 Polycom CX600 电话？”）感兴趣，则可以通过筛选该特定类型的电话，直接从 IP 电话清单报告中获取该信息。但是，如果您想要了解所有电话的摘要信息（多少人正在使用 Polycom CX600、多少人正在使用 LG-Nortel IP8540 等），则需要导出数据，然后使用另一个应用程序（如 Windows PowerShell）执行该类型的分析。例如，假设将数据导出到逗号分隔值文件 (C:\\Data\\IP\_Phone\_Inventory\_Report.csv)。在这种情况下，您可以使用以下这两个命令提供所有电话的摘要数据：

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending

这将返回与以下类似的数据：

    Count    Name
    -----    ----
      267    POLYCOM, CX700
      267    POLYCOM, CX600
      166    POLYCOM, C
       68    Microsoft, CPE
       64    LG-Nortel, IP8540
       59    Aastra, 6725ip
       37    LG-Nortel, IP
       22    POLYCOM, CX3000
       11    Microsoft, CPE_A
        9    POLYCOM, CX500
        7    Aastra, 6721ip

类似地，这两个命令会告诉您哪些电话已登录到系统，但实际上从未用来发出呼叫（“最后一次活动”指标的值为空白，表示没有任何最后一次活动）：

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones | Where-Object {$_."Last activity" -eq ""}

针对尚未使用的每一个电话，将返回与以下类似的数据：

    Manufacturer     : POLYCOM
    Hardware version : CX600
    MAC address      : 00-04-F2-00-01-76
    User URI         : 422
    User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
    Last logon time  : 8/30/2010 4:44:48 PM
    Last logoff time : 8/30/2010 5:59:07 PM
    Last activity    :

使用 IP 电话清单报告的另一种有趣的方式如下：如果您具有 IP 电话的 MAC 地址，则只需在 MAC 地址文本框中输入该地址，即可判断最后一次使用该电话的用户。然后，IP 电话清单报告将返回使用该电话最后一次登录的用户的 SIP 地址。或者，您可以在“用户 URI”前缀框中输入用户 SIP 地址，以查明该用户已使用的所有电话。

## 筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，通过 IP 电话清单，您可以只查看特定公司制造的电话，甚至只查看这些电话的某个特定版本。您还可以选择数据的分组方式。在此示例中，将按小时、日、周或月对注册进行分组。

下表列出了可用于 IP 电话清单报告的筛选器。

### IP 电话清单报告筛选器

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
<td><p><strong>制造商</strong></p></td>
<td><p>制造 IP 电话的公司的名称。此筛选器的值将根据数据库中当前存有的 IP 电话自动填充。</p></td>
</tr>
<tr class="even">
<td><p><strong>硬件版本</strong></p></td>
<td><p>IP 电话的版本号；使用您可以专门识别特定电话类型的制造商和硬件版本筛选器。此筛选器的值将根据数据库中当前存有的 IP 电话自动填充。</p></td>
</tr>
<tr class="odd">
<td><p><strong>用户代理</strong></p></td>
<td><p>IP 电话使用的软件的标识符。此筛选器的值将根据数据库中当前存有的 IP 电话自动填充。</p></td>
</tr>
<tr class="even">
<td><p><strong>MAC 地址</strong></p></td>
<td><p>IP 电话的网络接口的唯一标识符。媒体访问控制 (MAC) 地址通常在电话制造时分配，并硬接线到设备硬件。</p>
<p>要搜索与特定 MAC 地址有关的记录，只需输入该地址。例如：</p>
<p>00-08-5D-16-16-48</p>
<p>您必须输入完整地址。只输入一部分地址（例如 00-08-5D）不会返回任何数据。</p></td>
</tr>
<tr class="odd">
<td><p><strong>此天数前的最后一次活动</strong></p></td>
<td><p>选择下列值之一：</p>
<ul>
<li><p>[所有]</p></li>
<li><p>10</p></li>
<li><p>20</p></li>
<li><p>30</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>此天数前的最后注销时间</strong></p></td>
<td><p>选择下列值之一：</p>
<ul>
<li><p>[所有]</p></li>
<li><p>10</p></li>
<li><p>20</p></li>
<li><p>30</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>用户 URI 前缀</strong></p></td>
<td><p>使用 IP 电话的用户的 SIP 地址。</p></td>
</tr>
</tbody>
</table>


## 指标

下表列出了 IP 电话清单报告中提供的信息。

### IP 电话清单报告指标

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
<td><p><strong>制造商</strong></p></td>
<td><p>是</p></td>
<td><p>制造 IP 电话的公司的名称。</p></td>
</tr>
<tr class="even">
<td><p><strong>硬件版本</strong></p></td>
<td><p>是</p></td>
<td><p>IP 电话的版本号。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MAC 地址</strong></p></td>
<td><p>是</p></td>
<td><p>IP 电话的网络接口的唯一标识符。MAC 地址通常在电话制造时分配，并硬接线到设备硬件。</p></td>
</tr>
<tr class="even">
<td><p><strong>用户 URI</strong></p></td>
<td><p>是</p></td>
<td><p>使用 IP 电话的用户的 SIP 地址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>用户代理</strong></p></td>
<td><p>是</p></td>
<td><p>IP 电话使用的软件的标识符。</p></td>
</tr>
<tr class="even">
<td><p><strong>上次登录时间</strong></p></td>
<td><p>是</p></td>
<td><p>IP 电话上次登录到 Lync Server 的日期和时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>上次注销时间</strong></p></td>
<td><p>是</p></td>
<td><p>IP 电话上次从 Lync Server 注销的日期和时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>最后一次活动</strong></p></td>
<td><p>是</p></td>
<td><p>上一次使用 IP 电话的日期和时间。</p></td>
</tr>
</tbody>
</table>

