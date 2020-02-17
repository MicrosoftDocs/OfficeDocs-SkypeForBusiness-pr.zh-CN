---
title: Lync Server 2013：用户注册报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Registration Report
ms:assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558614(v=OCS.15)
ms:contentKeyID: 48183486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 716d8324fba8346fa1326da2ed253dfa07bc3915
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-registration-report-in-lync-server-2013"></a>Lync Server 2013 中的用户注册报告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-21_

用户注册报告提供用户登录活动的概述，最值得注意的是，有关登录到 Microsoft Lync Server 2013 的用户数在指定时间段（每小时、每天、每周、每月）中的信息。 请注意，报告仅告知您登录的用户数。 它不会告知您登录*的*用户。 监视报告不提供有关哪些特定用户使用 Lync Server 2013 （以及哪些用户不是）的信息。 不过，您可以使用用户活动报告获取用户信息的粗略估计。

在提供有关用户登录的信息时，用户注册报告会进行两个重要区分。 首先，它将登录细分为两个主要类别：内部登录和外部登录。 内部登录表示从组织防火墙内登录（即，在连接至企业网络时）的用户。 外部登录代表从防火墙外部通过边缘服务器登录的用户（例如，从 Internet 咖啡馆登录的用户咖啡馆将计数为外部登录）。 如果需要了解从防火墙外登录的用户数，用户注册报告可为您提供此信息。

此外，用户注册报告还会记录在给定时间段内在线的*活动* 用户数。 活动用户是在即时消息（IM）会话中参与的用户，参与 Lync 会议、拨打或接听电话呼叫或在该时间段使用 Lync Server。 这与登录但从未实际使用系统的用户不同。

<div>

## <a name="accessing-the-user-registration-report"></a>访问用户注册报告

只能从“监控报告”主页中访问用户注册报告。用户注册报告不链接至其他任何报告。

</div>

<div>

## <a name="making-the-best-use-of-the-user-registration-report"></a>充分利用用户注册报告

部署 Lync Server 后，一个常见问题是：如何知道我的用户是否确实在使用此新技术？ 尽管对于这一点仍存在一些限制，但用户注册报告可以帮助您回答此问题。 若要确定用户是否正在使用 Lync Server，您需要执行两项操作。 首先，从用户注册报告中获取“唯一登录用户”指标的值。 此值告诉你登录到 Lync Server 有多少不同的个人。

相比之下，Total 登录跃点数显示登录到 Lync Server 的任何人的总次数。 例如，假设 Ken Myer 在一天内登录到 Lync Server 5 个不同的时间。 在此情况下，Ken Myer 将在“登录总数”指标中记为五次单独的登录会话，但对于“唯一登录用户”指标只是一个登录用户。 同样，一个用户从多个设备或多个位置登录的情况也很常见。 例如，用户可以使用她的台式计算机（她的膝上型电脑）登录，并且可以有一个自动登录 Lync Server 的 IP 电话。 在此示例中，一个唯一用户登录三次。

为了进一步解释登录总数和唯一登录之间的差别，请考虑下表中给定时间段的登录数。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>用户</th>
<th>登录时间</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 8:45 AM</p></td>
</tr>
<tr class="even">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 8:46 AM</p></td>
</tr>
<tr class="odd">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 9:17 AM</p></td>
</tr>
<tr class="even">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 9:22 AM</p></td>
</tr>
<tr class="odd">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 9:31 AM</p></td>
</tr>
</tbody>
</table>


请注意，总共有五次登录；但只有两个唯一登录用户：Ken Myer（登录三次）和 Pilar Ackerman（登录两次）。这就是登录用户和唯一登录用户之间的差异。

除了了解唯一登录次数之外，还需要知道已为 Lync Server 启用的用户总数。 可以通过打开 Lync Server 2013 命令行管理程序并运行以下 Windows PowerShell 命令来检索该值：

    (Get-CsUser).Count

如果前面的命令返回的值为1236，唯一的登录用户指标返回的平均值为667，表示为 Lync 启用了一半以上的用户每日实际登录系统（即667除以1236）。，约为54%。

<div>


> [!WARNING]  
> 请注意，登录指标记录在指定时间段内实际登录的用户。 他们不会跟踪已登录到系统的用户。 例如，如果您的唯一登录用户指标显示667个登录，并且您有1236个用户，则表明您的用户登录到系统时大约一半。 但是，假设300用户已在您开始检查登录数据时登录到系统。 这意味着，您实际上已经有将近1000个登录到 Lync Server 的用户，这意味着更接近用户的80% 登录。



</div>

还应将“唯一登录用户”值与“唯一活动用户”指标的值进行比较。 "唯一活动用户" 指标告诉您实际使用 Lync Server 的唯一用户数：他们进行了电话呼叫，他们加入了 Lync 会议，或者参加了 IM 会话。 这是有用的信息，因为 Microsoft Lync 2013 可以配置为在用户每次启动 Windows 时自动启动。 因此，您可能会有大量用户在每天登录到 Windows 时自动登录到 Lync，但在该时间段内不会实际使用 Lync Server。

"唯一的活动用户" 指标也提供了组织中的更有意义的数据，在该组织中，用户通常不会在一天结束时注销 Windows。 相反，它们只是锁定其计算机，并让 Windows 和 Lync 保持运行状态。 在此类情况下，由于用户在若干天之前登录并且从未注销，因此每天的登录数可能很少。 但是，唯一的活动用户告诉你用户是主动使用 Lync 还是使用其他 Lync Server 客户端。

</div>

<div>

## <a name="filters"></a>筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。 例如，用户注册报告使您能够查看所有注册器池和边缘服务器的数据，或者查看单个池的数据。 您还可以选择数据的分组方式。 在此示例中，将按小时、日、周或月对注册进行分组。

下表列出了可用于用户注册报告的筛选器。

### <a name="user-registration-report-filters"></a>用户注册报告筛选器

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
<td><p>时间范围的开始日期和时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>时间范围的结束日期和时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</p>
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
<p>如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。例如，如果选择的开始日期为 8/7/2012、结束日期为 9/28/2012、间隔为“每天”，则显示从 8/7/2012 12:00 AM AM 到 9/7/2012 12:00 AM 这些天的数据（即总共 31 天的数据）。</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>注册器池或边缘服务器的完全限定域名 (FQDN)。 可以选择单个池，也可以选择“[所有]”<strong></strong>查看所有池的数据。 系统根据数据库中的记录自动为您填充该下拉列表。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指标

下表列出了用户注册报告中提供的信息。

### <a name="user-registration-report-metrics"></a>用户注册报告指标

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
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>每小时</strong></p>
<p><strong>每天</strong></p>
<p><strong>每周</strong></p>
<p><strong>每月</strong></p></td>
<td><p>否</p></td>
<td><p>指示在筛选器工具栏上选择的时间间隔。如果适用，可单击某一给定的时间间隔以查看该间隔的详细信息。例如，如果使用“每天”间隔并单击 7/7/2012，可查看当日用户注册活动的每小时细分信息。</p></td>
</tr>
<tr class="even">
<td><p><strong>登录总数</strong></p></td>
<td><p>否</p></td>
<td><p>成功的登录会话总数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>内部登录数</strong></p></td>
<td><p>否</p></td>
<td><p>内部网络中的登录总数。</p></td>
</tr>
<tr class="even">
<td><p><strong>外部登录数</strong></p></td>
<td><p>否</p></td>
<td><p>内部网络之外使用边缘服务器的登录总数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>唯一登录用户</strong></p></td>
<td><p>否</p></td>
<td><p>至少具有一个登录会话的用户总数。具有多个登录会话的用户算作一个用户，与只具有一个登录会话的用户相同。</p></td>
</tr>
<tr class="even">
<td><p><strong>唯一活动用户</strong></p></td>
<td><p>否</p></td>
<td><p>点对点会话或会议会话中涉及的用户总数。具有多个会话的用户算作一个用户，与只具有一个会话的用户相同。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

