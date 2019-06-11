---
title: 'Lync Server 2013: UserAgentDef table (QoE)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserAgentDef table (QoE)
ms:assetid: cfd8e3e0-4076-4162-9381-5276da8316d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205259(v=OCS.15)
ms:contentKeyID: 48185394
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3adfe05a24d2a45cf5d6d279b29d77b1c7654012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-qoe-in-lync-server-2013"></a><span data-ttu-id="6933c-102">Lync Server 2013 中的 UserAgentDef 表 (QoE)</span><span class="sxs-lookup"><span data-stu-id="6933c-102">UserAgentDef table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6933c-103">_**主题上次修改时间:** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="6933c-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="6933c-104">UserAgentDef 表将用户代理标识符映射到代理的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="6933c-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="6933c-105">用户代理是用于连接到 Microsoft Lync Server 2013 的软件客户端。</span><span class="sxs-lookup"><span data-stu-id="6933c-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6933c-106">UAType</span><span class="sxs-lookup"><span data-stu-id="6933c-106">UAType</span></span></th>
<th><span data-ttu-id="6933c-107">UAName</span><span class="sxs-lookup"><span data-stu-id="6933c-107">UAName</span></span></th>
<th><span data-ttu-id="6933c-108">UACategory</span><span class="sxs-lookup"><span data-stu-id="6933c-108">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6933c-109">1</span><span class="sxs-lookup"><span data-stu-id="6933c-109">1</span></span></p></td>
<td><p><span data-ttu-id="6933c-110">MediationServer</span><span class="sxs-lookup"><span data-stu-id="6933c-110">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="6933c-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="6933c-111">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6933c-112">2</span><span class="sxs-lookup"><span data-stu-id="6933c-112">2</span></span></p></td>
<td><p><span data-ttu-id="6933c-113">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="6933c-113">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="6933c-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="6933c-114">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6933c-115">4</span><span class="sxs-lookup"><span data-stu-id="6933c-115">4</span></span></p></td>
<td><p><span data-ttu-id="6933c-116">OC</span><span class="sxs-lookup"><span data-stu-id="6933c-116">OC</span></span></p></td>
<td><p><span data-ttu-id="6933c-117">OC</span><span class="sxs-lookup"><span data-stu-id="6933c-117">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6933c-118">个</span><span class="sxs-lookup"><span data-stu-id="6933c-118">8</span></span></p></td>
<td><p><span data-ttu-id="6933c-119">OCPhone</span><span class="sxs-lookup"><span data-stu-id="6933c-119">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="6933c-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="6933c-120">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6933c-121">utf-16</span><span class="sxs-lookup"><span data-stu-id="6933c-121">16</span></span></p></td>
<td><p><span data-ttu-id="6933c-122">LMC</span><span class="sxs-lookup"><span data-stu-id="6933c-122">LMC</span></span></p></td>
<td><p><span data-ttu-id="6933c-123">LMC</span><span class="sxs-lookup"><span data-stu-id="6933c-123">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6933c-124">32</span><span class="sxs-lookup"><span data-stu-id="6933c-124">32</span></span></p></td>
<td><p><span data-ttu-id="6933c-125">DVT</span><span class="sxs-lookup"><span data-stu-id="6933c-125">DVT</span></span></p></td>
<td><p><span data-ttu-id="6933c-126">DVT</span><span class="sxs-lookup"><span data-stu-id="6933c-126">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6933c-127">64</span><span class="sxs-lookup"><span data-stu-id="6933c-127">64</span></span></p></td>
<td><p><span data-ttu-id="6933c-128">分钟</span><span class="sxs-lookup"><span data-stu-id="6933c-128">MM</span></span></p></td>
<td><p><span data-ttu-id="6933c-129">分钟</span><span class="sxs-lookup"><span data-stu-id="6933c-129">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6933c-130">64</span><span class="sxs-lookup"><span data-stu-id="6933c-130">64</span></span></p></td>
<td><p><span data-ttu-id="6933c-131">MC</span><span class="sxs-lookup"><span data-stu-id="6933c-131">MC</span></span></p></td>
<td><p><span data-ttu-id="6933c-132">分钟</span><span class="sxs-lookup"><span data-stu-id="6933c-132">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6933c-133">128</span><span class="sxs-lookup"><span data-stu-id="6933c-133">128</span></span></p></td>
<td><p><span data-ttu-id="6933c-134">助理</span><span class="sxs-lookup"><span data-stu-id="6933c-134">Attendant</span></span></p></td>
<td><p><span data-ttu-id="6933c-135">助理</span><span class="sxs-lookup"><span data-stu-id="6933c-135">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6933c-136">256</span><span class="sxs-lookup"><span data-stu-id="6933c-136">256</span></span></p></td>
<td><p><span data-ttu-id="6933c-137">Conferencing_Announcement_Service_ 1。0</span><span class="sxs-lookup"><span data-stu-id="6933c-137">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="6933c-138">而言</span><span class="sxs-lookup"><span data-stu-id="6933c-138">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6933c-139">512</span><span class="sxs-lookup"><span data-stu-id="6933c-139">512</span></span></p></td>
<td><p><span data-ttu-id="6933c-140">Conferencing_Attendant_ 1。0</span><span class="sxs-lookup"><span data-stu-id="6933c-140">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="6933c-141">CAA</span><span class="sxs-lookup"><span data-stu-id="6933c-141">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6933c-142">512</span><span class="sxs-lookup"><span data-stu-id="6933c-142">512</span></span></p></td>
<td><p><span data-ttu-id="6933c-143">Conference_Auto_Attendant_ 1。0</span><span class="sxs-lookup"><span data-stu-id="6933c-143">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="6933c-144">CAA</span><span class="sxs-lookup"><span data-stu-id="6933c-144">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6933c-145">1024</span><span class="sxs-lookup"><span data-stu-id="6933c-145">1024</span></span></p></td>
<td><p><span data-ttu-id="6933c-146">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="6933c-146">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="6933c-147">RG</span><span class="sxs-lookup"><span data-stu-id="6933c-147">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6933c-148">1032</span><span class="sxs-lookup"><span data-stu-id="6933c-148">1032</span></span></p></td>
<td><p><span data-ttu-id="6933c-149">Call_Park_Service_ 1。0</span><span class="sxs-lookup"><span data-stu-id="6933c-149">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="6933c-150">方面</span><span class="sxs-lookup"><span data-stu-id="6933c-150">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6933c-151">1040</span><span class="sxs-lookup"><span data-stu-id="6933c-151">1040</span></span></p></td>
<td><p><span data-ttu-id="6933c-152">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="6933c-152">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="6933c-153">方式</span><span class="sxs-lookup"><span data-stu-id="6933c-153">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6933c-154">2048</span><span class="sxs-lookup"><span data-stu-id="6933c-154">2048</span></span></p></td>
<td><p><span data-ttu-id="6933c-155">Microsoft Ccs</span><span class="sxs-lookup"><span data-stu-id="6933c-155">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="6933c-156">CCS</span><span class="sxs-lookup"><span data-stu-id="6933c-156">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6933c-157">16386</span><span class="sxs-lookup"><span data-stu-id="6933c-157">16386</span></span></p></td>
<td><p><span data-ttu-id="6933c-158">CoMo</span><span class="sxs-lookup"><span data-stu-id="6933c-158">CoMo</span></span></p></td>
<td><p><span data-ttu-id="6933c-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="6933c-159">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6933c-160">16387</span><span class="sxs-lookup"><span data-stu-id="6933c-160">16387</span></span></p></td>
<td><p><span data-ttu-id="6933c-161">CWA</span><span class="sxs-lookup"><span data-stu-id="6933c-161">CWA</span></span></p></td>
<td><p><span data-ttu-id="6933c-162">CWA</span><span class="sxs-lookup"><span data-stu-id="6933c-162">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6933c-163">16388</span><span class="sxs-lookup"><span data-stu-id="6933c-163">16388</span></span></p></td>
<td><p><span data-ttu-id="6933c-164">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="6933c-164">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="6933c-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="6933c-165">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6933c-166">16389</span><span class="sxs-lookup"><span data-stu-id="6933c-166">16389</span></span></p></td>
<td><p><span data-ttu-id="6933c-167">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="6933c-167">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="6933c-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="6933c-168">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6933c-169">16393</span><span class="sxs-lookup"><span data-stu-id="6933c-169">16393</span></span></p></td>
<td><p><span data-ttu-id="6933c-170">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="6933c-170">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="6933c-171">ExUM</span><span class="sxs-lookup"><span data-stu-id="6933c-171">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6933c-172">16395</span><span class="sxs-lookup"><span data-stu-id="6933c-172">16395</span></span></p></td>
<td><p><span data-ttu-id="6933c-173">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="6933c-173">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="6933c-174">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="6933c-174">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6933c-175">16396</span><span class="sxs-lookup"><span data-stu-id="6933c-175">16396</span></span></p></td>
<td><p><span data-ttu-id="6933c-176">短期</span><span class="sxs-lookup"><span data-stu-id="6933c-176">ST</span></span></p></td>
<td><p><span data-ttu-id="6933c-177">短期</span><span class="sxs-lookup"><span data-stu-id="6933c-177">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6933c-178">16397</span><span class="sxs-lookup"><span data-stu-id="6933c-178">16397</span></span></p></td>
<td><p><span data-ttu-id="6933c-179">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="6933c-179">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="6933c-180">ASMCU</span><span class="sxs-lookup"><span data-stu-id="6933c-180">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6933c-181">16398</span><span class="sxs-lookup"><span data-stu-id="6933c-181">16398</span></span></p></td>
<td><p><span data-ttu-id="6933c-182">WPLync</span><span class="sxs-lookup"><span data-stu-id="6933c-182">WPLync</span></span></p></td>
<td><p><span data-ttu-id="6933c-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="6933c-183">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6933c-184">16399</span><span class="sxs-lookup"><span data-stu-id="6933c-184">16399</span></span></p></td>
<td><p><span data-ttu-id="6933c-185">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="6933c-185">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="6933c-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="6933c-186">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6933c-187">16400</span><span class="sxs-lookup"><span data-stu-id="6933c-187">16400</span></span></p></td>
<td><p><span data-ttu-id="6933c-188">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="6933c-188">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="6933c-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="6933c-189">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6933c-190">16401</span><span class="sxs-lookup"><span data-stu-id="6933c-190">16401</span></span></p></td>
<td><p><span data-ttu-id="6933c-191">iPadLync</span><span class="sxs-lookup"><span data-stu-id="6933c-191">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="6933c-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="6933c-192">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6933c-193">16402</span><span class="sxs-lookup"><span data-stu-id="6933c-193">16402</span></span></p></td>
<td><p><span data-ttu-id="6933c-194">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="6933c-194">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="6933c-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="6933c-195">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6933c-196">16403</span><span class="sxs-lookup"><span data-stu-id="6933c-196">16403</span></span></p></td>
<td><p><span data-ttu-id="6933c-197">LyncImm</span><span class="sxs-lookup"><span data-stu-id="6933c-197">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="6933c-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="6933c-198">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6933c-199">16404</span><span class="sxs-lookup"><span data-stu-id="6933c-199">16404</span></span></p></td>
<td><p><span data-ttu-id="6933c-200">笔记本电脑</span><span class="sxs-lookup"><span data-stu-id="6933c-200">PCS</span></span></p></td>
<td><p><span data-ttu-id="6933c-201">笔记本电脑</span><span class="sxs-lookup"><span data-stu-id="6933c-201">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6933c-202">16405</span><span class="sxs-lookup"><span data-stu-id="6933c-202">16405</span></span></p></td>
<td><p><span data-ttu-id="6933c-203">LWA</span><span class="sxs-lookup"><span data-stu-id="6933c-203">LWA</span></span></p></td>
<td><p><span data-ttu-id="6933c-204">LWA</span><span class="sxs-lookup"><span data-stu-id="6933c-204">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6933c-205">16406</span><span class="sxs-lookup"><span data-stu-id="6933c-205">16406</span></span></p></td>
<td><p><span data-ttu-id="6933c-206">OWA</span><span class="sxs-lookup"><span data-stu-id="6933c-206">OWA</span></span></p></td>
<td><p><span data-ttu-id="6933c-207">OWA</span><span class="sxs-lookup"><span data-stu-id="6933c-207">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6933c-208">16407</span><span class="sxs-lookup"><span data-stu-id="6933c-208">16407</span></span></p></td>
<td><p><span data-ttu-id="6933c-209">AOC</span><span class="sxs-lookup"><span data-stu-id="6933c-209">AOC</span></span></p></td>
<td><p><span data-ttu-id="6933c-210">AOC</span><span class="sxs-lookup"><span data-stu-id="6933c-210">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6933c-211">16408</span><span class="sxs-lookup"><span data-stu-id="6933c-211">16408</span></span></p></td>
<td><p><span data-ttu-id="6933c-212">GCC</span><span class="sxs-lookup"><span data-stu-id="6933c-212">GCC</span></span></p></td>
<td><p><span data-ttu-id="6933c-213">GCC</span><span class="sxs-lookup"><span data-stu-id="6933c-213">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6933c-214">16409</span><span class="sxs-lookup"><span data-stu-id="6933c-214">16409</span></span></p></td>
<td><p><span data-ttu-id="6933c-215">IMMCU</span><span class="sxs-lookup"><span data-stu-id="6933c-215">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="6933c-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="6933c-216">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6933c-217">16410</span><span class="sxs-lookup"><span data-stu-id="6933c-217">16410</span></span></p></td>
<td><p><span data-ttu-id="6933c-218">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="6933c-218">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="6933c-219">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="6933c-219">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6933c-220">32769</span><span class="sxs-lookup"><span data-stu-id="6933c-220">32769</span></span></p></td>
<td><p><span data-ttu-id="6933c-221">网关</span><span class="sxs-lookup"><span data-stu-id="6933c-221">Gateway</span></span></p></td>
<td><p><span data-ttu-id="6933c-222">网关</span><span class="sxs-lookup"><span data-stu-id="6933c-222">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6933c-223">32770</span><span class="sxs-lookup"><span data-stu-id="6933c-223">32770</span></span></p></td>
<td><p><span data-ttu-id="6933c-224">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="6933c-224">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="6933c-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="6933c-225">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

