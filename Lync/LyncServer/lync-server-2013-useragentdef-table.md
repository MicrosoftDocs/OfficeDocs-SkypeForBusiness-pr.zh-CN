---
title: 'Lync Server 2013: UserAgentDef 表'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserAgentDef table
ms:assetid: 96c49239-d999-4045-8b64-9d1940cce8ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205100(v=OCS.15)
ms:contentKeyID: 48184860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b378b6d71bb5163d1d2d2e9146cf3877c0d38a19
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845468"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-in-lync-server-2013"></a><span data-ttu-id="251ec-102">Lync Server 2013 中的 UserAgentDef 表</span><span class="sxs-lookup"><span data-stu-id="251ec-102">UserAgentDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="251ec-103">_**主题上次修改时间:** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="251ec-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="251ec-104">UserAgentDef 表将用户代理标识符映射到代理的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="251ec-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="251ec-105">用户代理是用于连接到 Microsoft Lync Server 2013 的软件客户端。</span><span class="sxs-lookup"><span data-stu-id="251ec-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="251ec-106">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="251ec-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="251ec-107">UAType</span><span class="sxs-lookup"><span data-stu-id="251ec-107">UAType</span></span></th>
<th><span data-ttu-id="251ec-108">UAName</span><span class="sxs-lookup"><span data-stu-id="251ec-108">UAName</span></span></th>
<th><span data-ttu-id="251ec-109">UACategory</span><span class="sxs-lookup"><span data-stu-id="251ec-109">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="251ec-110">1</span><span class="sxs-lookup"><span data-stu-id="251ec-110">1</span></span></p></td>
<td><p><span data-ttu-id="251ec-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="251ec-111">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="251ec-112">MediationServer</span><span class="sxs-lookup"><span data-stu-id="251ec-112">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="251ec-113">2</span><span class="sxs-lookup"><span data-stu-id="251ec-113">2</span></span></p></td>
<td><p><span data-ttu-id="251ec-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="251ec-114">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="251ec-115">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="251ec-115">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="251ec-116">4</span><span class="sxs-lookup"><span data-stu-id="251ec-116">4</span></span></p></td>
<td><p><span data-ttu-id="251ec-117">OC</span><span class="sxs-lookup"><span data-stu-id="251ec-117">OC</span></span></p></td>
<td><p><span data-ttu-id="251ec-118">OC</span><span class="sxs-lookup"><span data-stu-id="251ec-118">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="251ec-119">个</span><span class="sxs-lookup"><span data-stu-id="251ec-119">8</span></span></p></td>
<td><p><span data-ttu-id="251ec-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="251ec-120">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="251ec-121">OCPhone</span><span class="sxs-lookup"><span data-stu-id="251ec-121">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="251ec-122">utf-16</span><span class="sxs-lookup"><span data-stu-id="251ec-122">16</span></span></p></td>
<td><p><span data-ttu-id="251ec-123">LMC</span><span class="sxs-lookup"><span data-stu-id="251ec-123">LMC</span></span></p></td>
<td><p><span data-ttu-id="251ec-124">LMC</span><span class="sxs-lookup"><span data-stu-id="251ec-124">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="251ec-125">32</span><span class="sxs-lookup"><span data-stu-id="251ec-125">32</span></span></p></td>
<td><p><span data-ttu-id="251ec-126">DVT</span><span class="sxs-lookup"><span data-stu-id="251ec-126">DVT</span></span></p></td>
<td><p><span data-ttu-id="251ec-127">DVT</span><span class="sxs-lookup"><span data-stu-id="251ec-127">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="251ec-128">64</span><span class="sxs-lookup"><span data-stu-id="251ec-128">64</span></span></p></td>
<td><p><span data-ttu-id="251ec-129">分钟</span><span class="sxs-lookup"><span data-stu-id="251ec-129">MM</span></span></p></td>
<td><p><span data-ttu-id="251ec-130">分钟</span><span class="sxs-lookup"><span data-stu-id="251ec-130">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="251ec-131">64</span><span class="sxs-lookup"><span data-stu-id="251ec-131">64</span></span></p></td>
<td><p><span data-ttu-id="251ec-132">MC</span><span class="sxs-lookup"><span data-stu-id="251ec-132">MC</span></span></p></td>
<td><p><span data-ttu-id="251ec-133">分钟</span><span class="sxs-lookup"><span data-stu-id="251ec-133">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="251ec-134">128</span><span class="sxs-lookup"><span data-stu-id="251ec-134">128</span></span></p></td>
<td><p><span data-ttu-id="251ec-135">助理</span><span class="sxs-lookup"><span data-stu-id="251ec-135">Attendant</span></span></p></td>
<td><p><span data-ttu-id="251ec-136">助理</span><span class="sxs-lookup"><span data-stu-id="251ec-136">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="251ec-137">256</span><span class="sxs-lookup"><span data-stu-id="251ec-137">256</span></span></p></td>
<td><p><span data-ttu-id="251ec-138">Conferencing_Announcement_Service_ 1。0</span><span class="sxs-lookup"><span data-stu-id="251ec-138">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="251ec-139">而言</span><span class="sxs-lookup"><span data-stu-id="251ec-139">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="251ec-140">512</span><span class="sxs-lookup"><span data-stu-id="251ec-140">512</span></span></p></td>
<td><p><span data-ttu-id="251ec-141">Conferencing_Attendant_ 1。0</span><span class="sxs-lookup"><span data-stu-id="251ec-141">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="251ec-142">CAA</span><span class="sxs-lookup"><span data-stu-id="251ec-142">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="251ec-143">512</span><span class="sxs-lookup"><span data-stu-id="251ec-143">512</span></span></p></td>
<td><p><span data-ttu-id="251ec-144">Conference_Auto_Attendant_ 1。0</span><span class="sxs-lookup"><span data-stu-id="251ec-144">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="251ec-145">CAA</span><span class="sxs-lookup"><span data-stu-id="251ec-145">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="251ec-146">1024</span><span class="sxs-lookup"><span data-stu-id="251ec-146">1024</span></span></p></td>
<td><p><span data-ttu-id="251ec-147">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="251ec-147">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="251ec-148">RG</span><span class="sxs-lookup"><span data-stu-id="251ec-148">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="251ec-149">1032</span><span class="sxs-lookup"><span data-stu-id="251ec-149">1032</span></span></p></td>
<td><p><span data-ttu-id="251ec-150">Call_Park_Service_ 1。0</span><span class="sxs-lookup"><span data-stu-id="251ec-150">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="251ec-151">方面</span><span class="sxs-lookup"><span data-stu-id="251ec-151">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="251ec-152">1040</span><span class="sxs-lookup"><span data-stu-id="251ec-152">1040</span></span></p></td>
<td><p><span data-ttu-id="251ec-153">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="251ec-153">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="251ec-154">方式</span><span class="sxs-lookup"><span data-stu-id="251ec-154">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="251ec-155">2048</span><span class="sxs-lookup"><span data-stu-id="251ec-155">2048</span></span></p></td>
<td><p><span data-ttu-id="251ec-156">Microsoft Ccs</span><span class="sxs-lookup"><span data-stu-id="251ec-156">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="251ec-157">CCS</span><span class="sxs-lookup"><span data-stu-id="251ec-157">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="251ec-158">16386</span><span class="sxs-lookup"><span data-stu-id="251ec-158">16386</span></span></p></td>
<td><p><span data-ttu-id="251ec-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="251ec-159">CoMo</span></span></p></td>
<td><p><span data-ttu-id="251ec-160">CoMo</span><span class="sxs-lookup"><span data-stu-id="251ec-160">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="251ec-161">16387</span><span class="sxs-lookup"><span data-stu-id="251ec-161">16387</span></span></p></td>
<td><p><span data-ttu-id="251ec-162">CWA</span><span class="sxs-lookup"><span data-stu-id="251ec-162">CWA</span></span></p></td>
<td><p><span data-ttu-id="251ec-163">CWA</span><span class="sxs-lookup"><span data-stu-id="251ec-163">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="251ec-164">16388</span><span class="sxs-lookup"><span data-stu-id="251ec-164">16388</span></span></p></td>
<td><p><span data-ttu-id="251ec-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="251ec-165">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="251ec-166">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="251ec-166">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="251ec-167">16389</span><span class="sxs-lookup"><span data-stu-id="251ec-167">16389</span></span></p></td>
<td><p><span data-ttu-id="251ec-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="251ec-168">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="251ec-169">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="251ec-169">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="251ec-170">16393</span><span class="sxs-lookup"><span data-stu-id="251ec-170">16393</span></span></p></td>
<td><p><span data-ttu-id="251ec-171">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="251ec-171">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="251ec-172">ExUM</span><span class="sxs-lookup"><span data-stu-id="251ec-172">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="251ec-173">16395</span><span class="sxs-lookup"><span data-stu-id="251ec-173">16395</span></span></p></td>
<td><p><span data-ttu-id="251ec-174">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="251ec-174">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="251ec-175">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="251ec-175">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="251ec-176">16396</span><span class="sxs-lookup"><span data-stu-id="251ec-176">16396</span></span></p></td>
<td><p><span data-ttu-id="251ec-177">短期</span><span class="sxs-lookup"><span data-stu-id="251ec-177">ST</span></span></p></td>
<td><p><span data-ttu-id="251ec-178">短期</span><span class="sxs-lookup"><span data-stu-id="251ec-178">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="251ec-179">16397</span><span class="sxs-lookup"><span data-stu-id="251ec-179">16397</span></span></p></td>
<td><p><span data-ttu-id="251ec-180">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="251ec-180">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="251ec-181">ASMCU</span><span class="sxs-lookup"><span data-stu-id="251ec-181">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="251ec-182">16398</span><span class="sxs-lookup"><span data-stu-id="251ec-182">16398</span></span></p></td>
<td><p><span data-ttu-id="251ec-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="251ec-183">WPLync</span></span></p></td>
<td><p><span data-ttu-id="251ec-184">WPLync</span><span class="sxs-lookup"><span data-stu-id="251ec-184">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="251ec-185">16399</span><span class="sxs-lookup"><span data-stu-id="251ec-185">16399</span></span></p></td>
<td><p><span data-ttu-id="251ec-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="251ec-186">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="251ec-187">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="251ec-187">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="251ec-188">16400</span><span class="sxs-lookup"><span data-stu-id="251ec-188">16400</span></span></p></td>
<td><p><span data-ttu-id="251ec-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="251ec-189">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="251ec-190">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="251ec-190">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="251ec-191">16401</span><span class="sxs-lookup"><span data-stu-id="251ec-191">16401</span></span></p></td>
<td><p><span data-ttu-id="251ec-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="251ec-192">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="251ec-193">iPadLync</span><span class="sxs-lookup"><span data-stu-id="251ec-193">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="251ec-194">16402</span><span class="sxs-lookup"><span data-stu-id="251ec-194">16402</span></span></p></td>
<td><p><span data-ttu-id="251ec-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="251ec-195">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="251ec-196">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="251ec-196">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="251ec-197">16403</span><span class="sxs-lookup"><span data-stu-id="251ec-197">16403</span></span></p></td>
<td><p><span data-ttu-id="251ec-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="251ec-198">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="251ec-199">LyncImm</span><span class="sxs-lookup"><span data-stu-id="251ec-199">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="251ec-200">16404</span><span class="sxs-lookup"><span data-stu-id="251ec-200">16404</span></span></p></td>
<td><p><span data-ttu-id="251ec-201">笔记本电脑</span><span class="sxs-lookup"><span data-stu-id="251ec-201">PCS</span></span></p></td>
<td><p><span data-ttu-id="251ec-202">笔记本电脑</span><span class="sxs-lookup"><span data-stu-id="251ec-202">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="251ec-203">16405</span><span class="sxs-lookup"><span data-stu-id="251ec-203">16405</span></span></p></td>
<td><p><span data-ttu-id="251ec-204">LWA</span><span class="sxs-lookup"><span data-stu-id="251ec-204">LWA</span></span></p></td>
<td><p><span data-ttu-id="251ec-205">LWA</span><span class="sxs-lookup"><span data-stu-id="251ec-205">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="251ec-206">16406</span><span class="sxs-lookup"><span data-stu-id="251ec-206">16406</span></span></p></td>
<td><p><span data-ttu-id="251ec-207">OWA</span><span class="sxs-lookup"><span data-stu-id="251ec-207">OWA</span></span></p></td>
<td><p><span data-ttu-id="251ec-208">OWA</span><span class="sxs-lookup"><span data-stu-id="251ec-208">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="251ec-209">16407</span><span class="sxs-lookup"><span data-stu-id="251ec-209">16407</span></span></p></td>
<td><p><span data-ttu-id="251ec-210">AOC</span><span class="sxs-lookup"><span data-stu-id="251ec-210">AOC</span></span></p></td>
<td><p><span data-ttu-id="251ec-211">AOC</span><span class="sxs-lookup"><span data-stu-id="251ec-211">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="251ec-212">16408</span><span class="sxs-lookup"><span data-stu-id="251ec-212">16408</span></span></p></td>
<td><p><span data-ttu-id="251ec-213">GCC</span><span class="sxs-lookup"><span data-stu-id="251ec-213">GCC</span></span></p></td>
<td><p><span data-ttu-id="251ec-214">GCC</span><span class="sxs-lookup"><span data-stu-id="251ec-214">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="251ec-215">16409</span><span class="sxs-lookup"><span data-stu-id="251ec-215">16409</span></span></p></td>
<td><p><span data-ttu-id="251ec-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="251ec-216">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="251ec-217">IMMCU</span><span class="sxs-lookup"><span data-stu-id="251ec-217">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="251ec-218">16410</span><span class="sxs-lookup"><span data-stu-id="251ec-218">16410</span></span></p></td>
<td><p><span data-ttu-id="251ec-219">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="251ec-219">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="251ec-220">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="251ec-220">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="251ec-221">32769</span><span class="sxs-lookup"><span data-stu-id="251ec-221">32769</span></span></p></td>
<td><p><span data-ttu-id="251ec-222">网关</span><span class="sxs-lookup"><span data-stu-id="251ec-222">Gateway</span></span></p></td>
<td><p><span data-ttu-id="251ec-223">网关</span><span class="sxs-lookup"><span data-stu-id="251ec-223">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="251ec-224">32770</span><span class="sxs-lookup"><span data-stu-id="251ec-224">32770</span></span></p></td>
<td><p><span data-ttu-id="251ec-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="251ec-225">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="251ec-226">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="251ec-226">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

