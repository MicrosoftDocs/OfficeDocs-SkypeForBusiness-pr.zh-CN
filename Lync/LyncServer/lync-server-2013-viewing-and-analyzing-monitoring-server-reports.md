---
title: Lync Server 2013：查看和分析监视服务器报告
description: Lync Server 2013：查看和分析监视服务器报告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing and analyzing monitoring server reports
ms:assetid: 4dd448f1-01d2-49b2-b109-0728f36566b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720332(v=OCS.15)
ms:contentKeyID: 63969599
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f2a1812d76a49d487bea35acae3e22ea403f105
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580038"
---
# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a><span data-ttu-id="99b42-103">在 Lync Server 2013 中查看和分析监视服务器报告</span><span class="sxs-lookup"><span data-stu-id="99b42-103">Viewing and analyzing monitoring server reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99b42-104">_**上次修改的主题：** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="99b42-104">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="99b42-105">监视服务器报告提供了几种不同的语音质量指标，以监视正在传递给最终用户的 QoE。</span><span class="sxs-lookup"><span data-stu-id="99b42-105">Monitoring Server reports provides several different measures of voice quality to monitor the QoE that is being delivered to end-users.</span></span> <span data-ttu-id="99b42-106">此外，监视服务器还包括几个内置报告，您的组织可以使用这些报告来监视组织网络上的使用率和媒体质量趋势，并解决出现的媒体质量问题。</span><span class="sxs-lookup"><span data-stu-id="99b42-106">Additionally, Monitoring Server includes several built-in reports that your organization can use to watch usage and media quality trends on your organization's network and troubleshoot media quality issues that arise.</span></span>

<span data-ttu-id="99b42-107">使监视服务器报告对日常和每周操作感兴趣的主要部分是查看和分析媒体质量报告，具体具体如下：</span><span class="sxs-lookup"><span data-stu-id="99b42-107">A primary part of keeping Monitoring Server Reports interesting for daily and weekly operations is viewing and analyzing Media Quality Reports, in particular:</span></span>

  - <span data-ttu-id="99b42-108">QoE 摘要/趋势报告</span><span class="sxs-lookup"><span data-stu-id="99b42-108">QoE Summary/Trend Reports</span></span>

  - <span data-ttu-id="99b42-109">QoE 性能报告</span><span class="sxs-lookup"><span data-stu-id="99b42-109">QoE Performance Reports</span></span>

<div>

## <a name="view-reports-from-the-monitoring-server"></a><span data-ttu-id="99b42-110">查看来自监控服务器的报告</span><span class="sxs-lookup"><span data-stu-id="99b42-110">View reports from the monitoring server</span></span>

1.  <span data-ttu-id="99b42-111">在 web 浏览器中，找到托管 SQL 报告服务的服务器。</span><span class="sxs-lookup"><span data-stu-id="99b42-111">From a web browser, locate your servers hosting the SQL reporting services.</span></span>

2.  <span data-ttu-id="99b42-112">从浏览器屏幕查看所需的报告。</span><span class="sxs-lookup"><span data-stu-id="99b42-112">View the required reports from the browser screen.</span></span>

3.  <span data-ttu-id="99b42-113"> (可选) 通过选择 "导出" 选项和所需的输出格式导出报告。</span><span class="sxs-lookup"><span data-stu-id="99b42-113">(Optional) Export a report by selecting the export option and the required output format.</span></span>

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a><span data-ttu-id="99b42-114">配置 CDR)  (的呼叫详细记录</span><span class="sxs-lookup"><span data-stu-id="99b42-114">Configure call detail recording (CDR)</span></span>

1.  <span data-ttu-id="99b42-115">从属于 RTCUniversalServerAdmins 组成员的用户帐户 (或具有同等权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色，请登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="99b42-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent permissions), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="99b42-116">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="99b42-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="99b42-117">在左侧导航栏中，单击“监控和存档”\*\*\*\*，然后单击“呼叫详细信息记录”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="99b42-117">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="99b42-118">在“呼叫详细信息记录”\*\*\*\* 页上，单击表中的相应站点，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="99b42-118">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="99b42-119">若要打开清除，请选择 " **启用对监视服务器的清除**"。</span><span class="sxs-lookup"><span data-stu-id="99b42-119">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="99b42-120">在 " **保留呼叫详细信息记录" 的最长持续时间 (天) ：** 选择应保留的详细记录的最大天数。</span><span class="sxs-lookup"><span data-stu-id="99b42-120">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>

7.  <span data-ttu-id="99b42-121">在“错误报告数据最长保留期限(天):”\*\*\*\* 中选择错误报告的最长保留天数。</span><span class="sxs-lookup"><span data-stu-id="99b42-121">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>

8.  <span data-ttu-id="99b42-122">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="99b42-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="configure-qoe"></a><span data-ttu-id="99b42-123">配置 QoE</span><span class="sxs-lookup"><span data-stu-id="99b42-123">Configure QoE</span></span>

1.  <span data-ttu-id="99b42-124">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="99b42-124">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="99b42-125">有关详细信息，请参阅Delegate Setup Permissions。</span><span class="sxs-lookup"><span data-stu-id="99b42-125">For details, see Delegate Setup Permissions.</span></span>

2.  <span data-ttu-id="99b42-126">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="99b42-126">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="99b42-127">在左侧导航栏中，单击“监控和存档”\*\*\*\*，然后单击“用户体验质量数据”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="99b42-127">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="99b42-128">在“用户体验质量数据”\*\*\*\* 页上，单击表中的相应站点，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="99b42-128">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="99b42-129">若要打开清除，请选择 " **启用对监视服务器的清除**"。</span><span class="sxs-lookup"><span data-stu-id="99b42-129">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="99b42-130">在 " **保留呼叫详细信息记录的最长持续时间 (天) ：** 选择应保留 QoE 数据的最大天数。</span><span class="sxs-lookup"><span data-stu-id="99b42-130">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that QoE data should be retained.</span></span>

7.  <span data-ttu-id="99b42-131">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="99b42-131">Click Commit.</span></span>

</div>

<div>

## <a name="change-the-archiving-policy"></a><span data-ttu-id="99b42-132">更改存档策略</span><span class="sxs-lookup"><span data-stu-id="99b42-132">Change the archiving policy</span></span>

1.  <span data-ttu-id="99b42-133">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="99b42-133">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="99b42-134">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="99b42-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="99b42-135">在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档策略”**。</span><span class="sxs-lookup"><span data-stu-id="99b42-135">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="99b42-136">单击策略列表中的 **“全局”**，再单击 **“编辑”**，然后单击 **“显示详细信息”**。</span><span class="sxs-lookup"><span data-stu-id="99b42-136">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="99b42-137">在 **“编辑存档策略 - 全局”** 中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="99b42-137">In **Edit Archiving Policy - Global**, do the following:</span></span>

6.  <span data-ttu-id="99b42-138">若要启用或禁用部署的内部存档，请选中或清除 " **存档内部通信** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="99b42-138">To enable or disable internal archiving for the deployment, select or clear the **Archive internal communications** check box.</span></span>

7.  <span data-ttu-id="99b42-139">若要启用或禁用部署的外部存档，请选中或清除 " **存档外部通信** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="99b42-139">To enable or disable external archiving for the deployment, select or clear the **Archive external communications** check box.</span></span>

8.  <span data-ttu-id="99b42-140">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="99b42-140">Click **Commit**.</span></span>

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a><span data-ttu-id="99b42-141">将存档策略应用于用户</span><span class="sxs-lookup"><span data-stu-id="99b42-141">Apply an archiving policy to a user</span></span>

1.  <span data-ttu-id="99b42-142">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="99b42-142">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="99b42-143">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="99b42-143">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="99b42-144">在左侧导航栏中，单击“用户”\*\*\*\*，然后搜索要配置的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="99b42-144">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="99b42-145">在列出搜索结果的表中，单击相应的用户帐户，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="99b42-145">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="99b42-146">在 " **编辑 Lync Server 用户** " 中的 " **存档策略**" 下，选择要应用的存档用户策略。</span><span class="sxs-lookup"><span data-stu-id="99b42-146">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>

6.  <span data-ttu-id="99b42-147">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="99b42-147">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="99b42-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="99b42-148">See Also</span></span>


[<span data-ttu-id="99b42-149">在 Lync Server 2013 中使用监控报告</span><span class="sxs-lookup"><span data-stu-id="99b42-149">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
[<span data-ttu-id="99b42-150">Lync Server 2013 中的服务器性能报告</span><span class="sxs-lookup"><span data-stu-id="99b42-150">Server Performance Report in Lync Server 2013</span></span>](lync-server-2013-server-performance-report.md)  
[<span data-ttu-id="99b42-151">Lync Server 2013 中的媒体质量比较报告</span><span class="sxs-lookup"><span data-stu-id="99b42-151">Media Quality Comparison Report in Lync Server 2013</span></span>](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

