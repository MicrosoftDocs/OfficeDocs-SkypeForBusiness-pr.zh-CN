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
ms.openlocfilehash: c2b17d36756de3db0418fceb85f49535387bd138
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508709"
---
# <a name="user-registration-report-in-lync-server-2013"></a><span data-ttu-id="98bbd-102">Lync Server 2013 中的用户注册报告</span><span class="sxs-lookup"><span data-stu-id="98bbd-102">User Registration Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98bbd-103">_**上次修改的主题：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="98bbd-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="98bbd-104">用户注册报告概述了用户登录活动，最值得注意的是，有关登录到 Microsoft Lync Server 2013 的用户数的信息在指定时间段内 (每小时、每天、每周、每月) 。</span><span class="sxs-lookup"><span data-stu-id="98bbd-104">The User Registration Report provides an overview of user logon activity, most notably information about the number of users who logged on to Microsoft Lync Server 2013 during a specified time period (hourly, daily, weekly, monthly).</span></span> <span data-ttu-id="98bbd-105">请注意，报告仅告知您登录的用户数。</span><span class="sxs-lookup"><span data-stu-id="98bbd-105">Keep in mind that the report only tells you how many people logged on.</span></span> <span data-ttu-id="98bbd-106">它不会告知您登录 *的* 用户。</span><span class="sxs-lookup"><span data-stu-id="98bbd-106">It does not tell you *which* people logged on.</span></span> <span data-ttu-id="98bbd-107">监视报告不提供有关哪些特定用户使用 Lync Server 2013 (以及哪些用户未) 的信息。</span><span class="sxs-lookup"><span data-stu-id="98bbd-107">Monitoring Reports do not provide information about which specific users are using Lync Server 2013 (and which ones are not).</span></span> <span data-ttu-id="98bbd-108">不过，您可以使用用户活动报告获取用户信息的粗略估计。</span><span class="sxs-lookup"><span data-stu-id="98bbd-108">However, you can get a rough estimate of user information by using the User Activity Report.</span></span>

<span data-ttu-id="98bbd-109">在提供有关用户登录的信息时，用户注册报告会进行两个重要区分。</span><span class="sxs-lookup"><span data-stu-id="98bbd-109">When providing information about user logons, the User Registration Report draws two important distinctions.</span></span> <span data-ttu-id="98bbd-110">首先，它将登录细分为两个主要类别：内部登录和外部登录。</span><span class="sxs-lookup"><span data-stu-id="98bbd-110">First, it breaks logons down into two primary categories: internal logons and external logons.</span></span> <span data-ttu-id="98bbd-111">内部登录表示从组织防火墙内登录（即，在连接至企业网络时）的用户。</span><span class="sxs-lookup"><span data-stu-id="98bbd-111">Internal logons represent users who logged on from inside your organization's firewall (that is, while connected to the corporate network).</span></span> <span data-ttu-id="98bbd-112">外部登录代表从防火墙外部通过边缘服务器登录的用户 (例如，从 Internet 咖啡馆登录的用户将计数为外部登录) 。</span><span class="sxs-lookup"><span data-stu-id="98bbd-112">External logons represent users who logged on from outside the firewall through an Edge Server (for example, a user who logged on from an Internet café counts as an external logon).</span></span> <span data-ttu-id="98bbd-113">如果需要了解从防火墙外登录的用户数，用户注册报告可为您提供此信息。</span><span class="sxs-lookup"><span data-stu-id="98bbd-113">If you need to know how many of your users are logging on from outside the firewall, the User Registration Report can provide you with this information.</span></span>

<span data-ttu-id="98bbd-114">此外，用户注册报告还会记录在给定时间段内在线的*活动* 用户数。</span><span class="sxs-lookup"><span data-stu-id="98bbd-114">In addition, the User Registration Report notes how many *active* users were present during a given time period.</span></span> <span data-ttu-id="98bbd-115">活动用户是在即时消息 (IM) 会话中参与的用户，参与 Lync 会议、拨打或接听电话呼叫，或在该时间段使用 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="98bbd-115">An active user is a user who took part in an instant messaging (IM) session, participated in a Lync Meeting, made or received a phone call, or otherwise used Lync Server during that period of time.</span></span> <span data-ttu-id="98bbd-116">这与登录但从未实际使用系统的用户不同。</span><span class="sxs-lookup"><span data-stu-id="98bbd-116">This is different from a user who logged on, but never actually used the system.</span></span>

<div>

## <a name="accessing-the-user-registration-report"></a><span data-ttu-id="98bbd-117">访问用户注册报告</span><span class="sxs-lookup"><span data-stu-id="98bbd-117">Accessing the User Registration Report</span></span>

<span data-ttu-id="98bbd-p104">只能从“监控报告”主页中访问用户注册报告。用户注册报告不链接至其他任何报告。</span><span class="sxs-lookup"><span data-stu-id="98bbd-p104">You access the User Registration Report only from the Monitoring Reports home page. The User Registration Report does not link to any other reports.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-registration-report"></a><span data-ttu-id="98bbd-120">充分利用用户注册报告</span><span class="sxs-lookup"><span data-stu-id="98bbd-120">Making the Best Use of the User Registration Report</span></span>

<span data-ttu-id="98bbd-121">部署 Lync Server 后，一个常见问题是：如何知道我的用户是否确实在使用此新技术？</span><span class="sxs-lookup"><span data-stu-id="98bbd-121">After you've deployed Lync Server one commonly-asked question is this: How do I know if my users are actually using this new technology?</span></span> <span data-ttu-id="98bbd-122">尽管对于这一点仍存在一些限制，但用户注册报告可以帮助您回答此问题。</span><span class="sxs-lookup"><span data-stu-id="98bbd-122">Although it has a few limitations in this regard, the User Registration Report can help you answer this question.</span></span> <span data-ttu-id="98bbd-123">若要确定用户是否正在使用 Lync Server，您需要执行两项操作。</span><span class="sxs-lookup"><span data-stu-id="98bbd-123">To determine whether or not users are using Lync Server, you need to do two things.</span></span> <span data-ttu-id="98bbd-124">首先，从用户注册报告中获取“唯一登录用户”指标的值。</span><span class="sxs-lookup"><span data-stu-id="98bbd-124">First, get the value of the Unique logon users metric from the User Registration Report.</span></span> <span data-ttu-id="98bbd-125">此值告诉你登录到 Lync Server 有多少不同的个人。</span><span class="sxs-lookup"><span data-stu-id="98bbd-125">This value tells you how many distinct individuals logged on to Lync Server.</span></span>

<span data-ttu-id="98bbd-126">相比之下，Total 登录跃点数显示登录到 Lync Server 的任何人的总次数。</span><span class="sxs-lookup"><span data-stu-id="98bbd-126">By comparison, the Total logons metric shows how many total times anyone logged on to Lync Server.</span></span> <span data-ttu-id="98bbd-127">例如，假设 Ken Myer 在一天内登录到 Lync Server 5 个不同的时间。</span><span class="sxs-lookup"><span data-stu-id="98bbd-127">For example, suppose Ken Myer logged on to Lync Server five different times in a single day.</span></span> <span data-ttu-id="98bbd-128">在此情况下，Ken Myer 将在“登录总数”指标中记为五次单独的登录会话，但对于“唯一登录用户”指标只是一个登录用户。</span><span class="sxs-lookup"><span data-stu-id="98bbd-128">In that case, Ken Myer would count as five separate logon sessions for the Total logons metric, but just one logon user for the Unique logon users metric.</span></span> <span data-ttu-id="98bbd-129">同样，一个用户从多个设备或多个位置登录的情况也很常见。</span><span class="sxs-lookup"><span data-stu-id="98bbd-129">Likewise, it's not uncommon for a user to log on from multiple devices or multiple locations.</span></span> <span data-ttu-id="98bbd-130">例如，用户可以使用她的台式计算机（她的膝上型电脑）登录，并且可以有一个自动登录 Lync Server 的 IP 电话。</span><span class="sxs-lookup"><span data-stu-id="98bbd-130">For example, a user can log on using her desktop computer, her laptop computer, and she can have an IP phone that automatically logs on to Lync Server.</span></span> <span data-ttu-id="98bbd-131">在此示例中，一个唯一用户登录三次。</span><span class="sxs-lookup"><span data-stu-id="98bbd-131">In this example, there is one unique user with three logons.</span></span>

<span data-ttu-id="98bbd-132">为了进一步解释登录总数和唯一登录之间的差别，请考虑下表中给定时间段的登录数。</span><span class="sxs-lookup"><span data-stu-id="98bbd-132">To further explain the difference between total logons and unique logons, consider the logons for a given time period in the following table.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98bbd-133">用户</span><span class="sxs-lookup"><span data-stu-id="98bbd-133">User</span></span></th>
<th><span data-ttu-id="98bbd-134">登录时间</span><span class="sxs-lookup"><span data-stu-id="98bbd-134">Logon time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98bbd-135">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="98bbd-135">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="98bbd-136">7/7/2012 8:45 AM</span><span class="sxs-lookup"><span data-stu-id="98bbd-136">7/7/2012 8:45 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98bbd-137">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="98bbd-137">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="98bbd-138">7/7/2012 8:46 AM</span><span class="sxs-lookup"><span data-stu-id="98bbd-138">7/7/2012 8:46 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98bbd-139">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="98bbd-139">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="98bbd-140">7/7/2012 9:17 AM</span><span class="sxs-lookup"><span data-stu-id="98bbd-140">7/7/2012 9:17 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98bbd-141">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="98bbd-141">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="98bbd-142">7/7/2012 9:22 AM</span><span class="sxs-lookup"><span data-stu-id="98bbd-142">7/7/2012 9:22 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98bbd-143">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="98bbd-143">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="98bbd-144">7/7/2012 9:31 AM</span><span class="sxs-lookup"><span data-stu-id="98bbd-144">7/7/2012 9:31 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="98bbd-p107">请注意，总共有五次登录；但只有两个唯一登录用户：Ken Myer（登录三次）和 Pilar Ackerman（登录两次）。这就是登录用户和唯一登录用户之间的差异。</span><span class="sxs-lookup"><span data-stu-id="98bbd-p107">Notice that there is a total of five logons; however, there are only two unique logon users: Ken Myer (who logged on three times) and Pilar Ackerman (who logged on twice). That's the difference between logons and unique logon users.</span></span>

<span data-ttu-id="98bbd-147">除了了解唯一登录次数之外，还需要知道已为 Lync Server 启用的用户总数。</span><span class="sxs-lookup"><span data-stu-id="98bbd-147">In addition to knowing the number of unique logons, you need to know the total number of users who have been enabled for Lync Server.</span></span> <span data-ttu-id="98bbd-148">可以通过打开 Lync Server 2013 命令行管理程序并运行以下 Windows PowerShell 命令来检索该值：</span><span class="sxs-lookup"><span data-stu-id="98bbd-148">That value can be retrieved by opening the Lync Server 2013 Management Shell and running the following Windows PowerShell command:</span></span>

    (Get-CsUser).Count

<span data-ttu-id="98bbd-149">如果前面的命令返回值1236，且唯一的登录用户指标返回的平均值为667，则表示每日启用 Lync 的用户的一半实际上是每日登录系统 (即，667除以1236，即大约 54% ) 。</span><span class="sxs-lookup"><span data-stu-id="98bbd-149">If the preceding command returns a value of 1,236 and Unique logon users metric returns an average value of 667, that suggests that a little over half of your users enable for Lync are actually logging on to the system each day (that is, 667 divided by 1,236, which is approximately 54%).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="98bbd-150">请注意，登录指标记录在指定时间段内实际登录的用户。</span><span class="sxs-lookup"><span data-stu-id="98bbd-150">Keep in mind that the logon metrics record users who actually logged on during the specified time period.</span></span> <span data-ttu-id="98bbd-151">他们不会跟踪已登录到系统的用户。</span><span class="sxs-lookup"><span data-stu-id="98bbd-151">They don't keep track of users who were already logged on to the system.</span></span> <span data-ttu-id="98bbd-152">例如，如果您的唯一登录用户指标显示667个登录，并且您有1236个用户，则表明您的用户登录到系统时大约一半。</span><span class="sxs-lookup"><span data-stu-id="98bbd-152">For example, if your Unique logon users metric shows 667 logons and you have 1,236 users, that suggests that about half your users are logging on to the system.</span></span> <span data-ttu-id="98bbd-153">但是，假设300用户已在您开始检查登录数据时登录到系统。</span><span class="sxs-lookup"><span data-stu-id="98bbd-153">However, suppose 300 users were already logged on to the system at the time you began checking the logon data.</span></span> <span data-ttu-id="98bbd-154">这意味着，您实际上已经有将近1000个登录到 Lync Server 的用户，这意味着更接近用户的80% 登录。</span><span class="sxs-lookup"><span data-stu-id="98bbd-154">That would mean that you actually had nearly 1,000 users logged on to Lync Server, which would mean that closer to 80% of your users were logged on.</span></span>



</div>

<span data-ttu-id="98bbd-155">还应将“唯一登录用户”值与“唯一活动用户”指标的值进行比较。</span><span class="sxs-lookup"><span data-stu-id="98bbd-155">You should also compare the Unique logon users value with the value of the Unique active users metric.</span></span> <span data-ttu-id="98bbd-156">"唯一活动用户" 指标告诉您实际使用 Lync Server 的唯一用户数：他们进行了电话呼叫，他们加入了 Lync 会议，或者参加了 IM 会话。</span><span class="sxs-lookup"><span data-stu-id="98bbd-156">The Unique active users metric tells you how many unique users actually used Lync Server: they made a phone call, they joined a Lync Meeting, or they participated in an IM session.</span></span> <span data-ttu-id="98bbd-157">这是有用的信息，因为 Microsoft Lync 2013 可以配置为在用户每次启动 Windows 时自动启动。</span><span class="sxs-lookup"><span data-stu-id="98bbd-157">This is useful information, because Microsoft Lync 2013 can be configured to automatically start each time a user starts Windows.</span></span> <span data-ttu-id="98bbd-158">因此，您可能会有大量用户在每天登录到 Windows 时自动登录到 Lync，但在该时间段内不会实际使用 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="98bbd-158">Because of that, you might have a large number of users who automatically log on to Lync when they log on to Windows each day, but then never actually use Lync Server during that time period.</span></span>

<span data-ttu-id="98bbd-159">"唯一的活动用户" 指标也提供了组织中的更有意义的数据，在该组织中，用户通常不会在一天结束时注销 Windows。</span><span class="sxs-lookup"><span data-stu-id="98bbd-159">The Unique active users metric also provides more meaningful data in an organization where users typically do not log off Windows at the end of the day.</span></span> <span data-ttu-id="98bbd-160">相反，它们只是锁定其计算机，并让 Windows 和 Lync 保持运行状态。</span><span class="sxs-lookup"><span data-stu-id="98bbd-160">Instead, they simply lock their computers and leave Windows and Lync running.</span></span> <span data-ttu-id="98bbd-161">在此类情况下，由于用户在若干天之前登录并且从未注销，因此每天的登录数可能很少。</span><span class="sxs-lookup"><span data-stu-id="98bbd-161">In a situation like that, you might end up with very few logons per day because your users logged on several days ago and never logged off.</span></span> <span data-ttu-id="98bbd-162">但是，唯一的活动用户告诉你用户是主动使用 Lync 还是使用其他 Lync Server 客户端。</span><span class="sxs-lookup"><span data-stu-id="98bbd-162">However, Unique active users tells you whether users are actively using Lync or another Lync Server client.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="98bbd-163">筛选器</span><span class="sxs-lookup"><span data-stu-id="98bbd-163">Filters</span></span>

<span data-ttu-id="98bbd-164">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。</span><span class="sxs-lookup"><span data-stu-id="98bbd-164">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="98bbd-165">例如，用户注册报告使您能够查看所有注册器池和边缘服务器的数据，或者查看单个池的数据。</span><span class="sxs-lookup"><span data-stu-id="98bbd-165">For example, the User Registration Report enables you to view data for all your Registrar pool and Edge Servers or to view data for an individual pool.</span></span> <span data-ttu-id="98bbd-166">您还可以选择数据的分组方式。</span><span class="sxs-lookup"><span data-stu-id="98bbd-166">You can also choose how data should be grouped.</span></span> <span data-ttu-id="98bbd-167">在此示例中，将按小时、日、周或月对注册进行分组。</span><span class="sxs-lookup"><span data-stu-id="98bbd-167">In this case, registrations grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="98bbd-168">下表列出了可用于用户注册报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="98bbd-168">The following table lists the filters that you can use with the User Registration Report.</span></span>

### <a name="user-registration-report-filters"></a><span data-ttu-id="98bbd-169">用户注册报告筛选器</span><span class="sxs-lookup"><span data-stu-id="98bbd-169">User Registration Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98bbd-170">名称</span><span class="sxs-lookup"><span data-stu-id="98bbd-170">Name</span></span></th>
<th><span data-ttu-id="98bbd-171">说明</span><span class="sxs-lookup"><span data-stu-id="98bbd-171">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98bbd-172"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="98bbd-172"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="98bbd-p113">时间范围的开始日期和时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="98bbd-p113">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="98bbd-175">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="98bbd-175">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="98bbd-p114">如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="98bbd-p114">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="98bbd-178">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="98bbd-178">7/7/2012</span></span></p>
<p><span data-ttu-id="98bbd-179">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="98bbd-179">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="98bbd-180">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="98bbd-180">7/3/2012</span></span></p>
<p><span data-ttu-id="98bbd-181">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="98bbd-181">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98bbd-182"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="98bbd-182"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="98bbd-p115">时间范围的结束日期和时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="98bbd-p115">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="98bbd-185">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="98bbd-185">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="98bbd-p116">如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="98bbd-p116">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="98bbd-188">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="98bbd-188">7/7/2012</span></span></p>
<p><span data-ttu-id="98bbd-189">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="98bbd-189">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="98bbd-190">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="98bbd-190">7/3/2012</span></span></p>
<p><span data-ttu-id="98bbd-191">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="98bbd-191">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98bbd-192"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="98bbd-192"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="98bbd-p117">时间间隔。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="98bbd-p117">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="98bbd-195">每小时（最多可显示 25 个小时）</span><span class="sxs-lookup"><span data-stu-id="98bbd-195">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="98bbd-196">每天（最多可显示 31 天）</span><span class="sxs-lookup"><span data-stu-id="98bbd-196">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="98bbd-197">每周（最多可显示 12 周）</span><span class="sxs-lookup"><span data-stu-id="98bbd-197">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="98bbd-198">每月（最多可显示 12 个月）</span><span class="sxs-lookup"><span data-stu-id="98bbd-198">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="98bbd-p118">如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。例如，如果选择的开始日期为 8/7/2012、结束日期为 9/28/2012、间隔为“每天”，则显示从 8/7/2012 12:00 AM AM 到 9/7/2012 12:00 AM 这些天的数据（即总共 31 天的数据）。</span><span class="sxs-lookup"><span data-stu-id="98bbd-p118">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98bbd-201"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="98bbd-201"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="98bbd-202">注册器池或边缘服务器的完全限定域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="98bbd-202">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="98bbd-203">可以选择单个池，也可以选择“[所有]”<strong></strong>查看所有池的数据。</span><span class="sxs-lookup"><span data-stu-id="98bbd-203">You can either select an individual pool or choose <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="98bbd-204">系统根据数据库中的记录自动为您填充该下拉列表。</span><span class="sxs-lookup"><span data-stu-id="98bbd-204">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="98bbd-205">指标</span><span class="sxs-lookup"><span data-stu-id="98bbd-205">Metrics</span></span>

<span data-ttu-id="98bbd-206">下表列出了用户注册报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="98bbd-206">The following table lists the information provided in the User Registration Report.</span></span>

### <a name="user-registration-report-metrics"></a><span data-ttu-id="98bbd-207">用户注册报告指标</span><span class="sxs-lookup"><span data-stu-id="98bbd-207">User Registration Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98bbd-208">名称</span><span class="sxs-lookup"><span data-stu-id="98bbd-208">Name</span></span></th>
<th><span data-ttu-id="98bbd-209">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="98bbd-209">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="98bbd-210">说明</span><span class="sxs-lookup"><span data-stu-id="98bbd-210">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98bbd-211"><strong>每小时</strong></span><span class="sxs-lookup"><span data-stu-id="98bbd-211"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="98bbd-212"><strong>每天</strong></span><span class="sxs-lookup"><span data-stu-id="98bbd-212"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="98bbd-213"><strong>每周</strong></span><span class="sxs-lookup"><span data-stu-id="98bbd-213"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="98bbd-214"><strong>每月</strong></span><span class="sxs-lookup"><span data-stu-id="98bbd-214"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="98bbd-215">否</span><span class="sxs-lookup"><span data-stu-id="98bbd-215">No</span></span></p></td>
<td><p><span data-ttu-id="98bbd-p120">指示在筛选器工具栏上选择的时间间隔。如果适用，可单击某一给定的时间间隔以查看该间隔的详细信息。例如，如果使用“每天”间隔并单击 7/7/2012，可查看当日用户注册活动的每小时细分信息。</span><span class="sxs-lookup"><span data-stu-id="98bbd-p120">Indicates the time interval that you selected on the filter toolbar. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98bbd-219"><strong>登录总数</strong></span><span class="sxs-lookup"><span data-stu-id="98bbd-219"><strong>Total logons</strong></span></span></p></td>
<td><p><span data-ttu-id="98bbd-220">否</span><span class="sxs-lookup"><span data-stu-id="98bbd-220">No</span></span></p></td>
<td><p><span data-ttu-id="98bbd-221">成功的登录会话总数。</span><span class="sxs-lookup"><span data-stu-id="98bbd-221">Total number of successful logon sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98bbd-222"><strong>内部登录数</strong></span><span class="sxs-lookup"><span data-stu-id="98bbd-222"><strong>Internal logons</strong></span></span></p></td>
<td><p><span data-ttu-id="98bbd-223">否</span><span class="sxs-lookup"><span data-stu-id="98bbd-223">No</span></span></p></td>
<td><p><span data-ttu-id="98bbd-224">内部网络中的登录总数。</span><span class="sxs-lookup"><span data-stu-id="98bbd-224">Total number of logons within the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98bbd-225"><strong>外部登录数</strong></span><span class="sxs-lookup"><span data-stu-id="98bbd-225"><strong>External logons</strong></span></span></p></td>
<td><p><span data-ttu-id="98bbd-226">否</span><span class="sxs-lookup"><span data-stu-id="98bbd-226">No</span></span></p></td>
<td><p><span data-ttu-id="98bbd-227">内部网络之外使用边缘服务器的登录总数。</span><span class="sxs-lookup"><span data-stu-id="98bbd-227">Total number of logons from outside the internal network, using the Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98bbd-228"><strong>唯一登录用户</strong></span><span class="sxs-lookup"><span data-stu-id="98bbd-228"><strong>Unique logon users</strong></span></span></p></td>
<td><p><span data-ttu-id="98bbd-229">否</span><span class="sxs-lookup"><span data-stu-id="98bbd-229">No</span></span></p></td>
<td><p><span data-ttu-id="98bbd-p121">至少具有一个登录会话的用户总数。具有多个登录会话的用户算作一个用户，与只具有一个登录会话的用户相同。</span><span class="sxs-lookup"><span data-stu-id="98bbd-p121">Total number of users who had at least one logon session. A user who had multiple logon sessions counts as one user, the same as a person who had just a single logon session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98bbd-232"><strong>唯一活动用户</strong></span><span class="sxs-lookup"><span data-stu-id="98bbd-232"><strong>Unique active users</strong></span></span></p></td>
<td><p><span data-ttu-id="98bbd-233">否</span><span class="sxs-lookup"><span data-stu-id="98bbd-233">No</span></span></p></td>
<td><p><span data-ttu-id="98bbd-p122">点对点会话或会议会话中涉及的用户总数。具有多个会话的用户算作一个用户，与只具有一个会话的用户相同。</span><span class="sxs-lookup"><span data-stu-id="98bbd-p122">Total number of users who were involved in a peer-to-peer or conferencing session. A user who had multiple sessions counts as one user, the same as a person who had just a single session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

