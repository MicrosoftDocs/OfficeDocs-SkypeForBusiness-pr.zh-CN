---
title: 'Lync Server 2013： UserAgentDef table (QoE) '
description: Lync Server 2013： UserAgentDef table (QoE) 。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgentDef table (QoE)
ms:assetid: cfd8e3e0-4076-4162-9381-5276da8316d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205259(v=OCS.15)
ms:contentKeyID: 48185394
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8546a33e607524b23755e9abf3edb2d5e2e417d7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547338"
---
# <a name="useragentdef-table-qoe-in-lync-server-2013"></a><span data-ttu-id="e8356-103">Lync Server 2013 中的 UserAgentDef 表 (QoE) </span><span class="sxs-lookup"><span data-stu-id="e8356-103">UserAgentDef table (QoE) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8356-104">_**上次修改的主题：** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="e8356-104">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="e8356-105">UserAgentDef 表将用户代理标识符映射到代理的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="e8356-105">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="e8356-106">用户代理是用于连接到 Microsoft Lync Server 2013 的软件客户端。</span><span class="sxs-lookup"><span data-stu-id="e8356-106">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8356-107">UAType</span><span class="sxs-lookup"><span data-stu-id="e8356-107">UAType</span></span></th>
<th><span data-ttu-id="e8356-108">UAName</span><span class="sxs-lookup"><span data-stu-id="e8356-108">UAName</span></span></th>
<th><span data-ttu-id="e8356-109">UACategory</span><span class="sxs-lookup"><span data-stu-id="e8356-109">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8356-110">1</span><span class="sxs-lookup"><span data-stu-id="e8356-110">1</span></span></p></td>
<td><p><span data-ttu-id="e8356-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="e8356-111">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="e8356-112">MediationServer</span><span class="sxs-lookup"><span data-stu-id="e8356-112">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8356-113">双面</span><span class="sxs-lookup"><span data-stu-id="e8356-113">2</span></span></p></td>
<td><p><span data-ttu-id="e8356-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="e8356-114">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="e8356-115">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="e8356-115">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8356-116">4 </span><span class="sxs-lookup"><span data-stu-id="e8356-116">4</span></span></p></td>
<td><p><span data-ttu-id="e8356-117">OC</span><span class="sxs-lookup"><span data-stu-id="e8356-117">OC</span></span></p></td>
<td><p><span data-ttu-id="e8356-118">OC</span><span class="sxs-lookup"><span data-stu-id="e8356-118">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8356-119">8 </span><span class="sxs-lookup"><span data-stu-id="e8356-119">8</span></span></p></td>
<td><p><span data-ttu-id="e8356-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="e8356-120">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="e8356-121">OCPhone</span><span class="sxs-lookup"><span data-stu-id="e8356-121">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8356-122">16 </span><span class="sxs-lookup"><span data-stu-id="e8356-122">16</span></span></p></td>
<td><p><span data-ttu-id="e8356-123">LMC</span><span class="sxs-lookup"><span data-stu-id="e8356-123">LMC</span></span></p></td>
<td><p><span data-ttu-id="e8356-124">LMC</span><span class="sxs-lookup"><span data-stu-id="e8356-124">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8356-125">32</span><span class="sxs-lookup"><span data-stu-id="e8356-125">32</span></span></p></td>
<td><p><span data-ttu-id="e8356-126">DVT</span><span class="sxs-lookup"><span data-stu-id="e8356-126">DVT</span></span></p></td>
<td><p><span data-ttu-id="e8356-127">DVT</span><span class="sxs-lookup"><span data-stu-id="e8356-127">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8356-128">64</span><span class="sxs-lookup"><span data-stu-id="e8356-128">64</span></span></p></td>
<td><p><span data-ttu-id="e8356-129">MM</span><span class="sxs-lookup"><span data-stu-id="e8356-129">MM</span></span></p></td>
<td><p><span data-ttu-id="e8356-130">MM</span><span class="sxs-lookup"><span data-stu-id="e8356-130">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8356-131">64</span><span class="sxs-lookup"><span data-stu-id="e8356-131">64</span></span></p></td>
<td><p><span data-ttu-id="e8356-132">EMC</span><span class="sxs-lookup"><span data-stu-id="e8356-132">MC</span></span></p></td>
<td><p><span data-ttu-id="e8356-133">MM</span><span class="sxs-lookup"><span data-stu-id="e8356-133">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8356-134">128</span><span class="sxs-lookup"><span data-stu-id="e8356-134">128</span></span></p></td>
<td><p><span data-ttu-id="e8356-135">助理版</span><span class="sxs-lookup"><span data-stu-id="e8356-135">Attendant</span></span></p></td>
<td><p><span data-ttu-id="e8356-136">助理版</span><span class="sxs-lookup"><span data-stu-id="e8356-136">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8356-137">256</span><span class="sxs-lookup"><span data-stu-id="e8356-137">256</span></span></p></td>
<td><p><span data-ttu-id="e8356-138">Conferencing_Announcement_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="e8356-138">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="e8356-139">CAS</span><span class="sxs-lookup"><span data-stu-id="e8356-139">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8356-140">512</span><span class="sxs-lookup"><span data-stu-id="e8356-140">512</span></span></p></td>
<td><p><span data-ttu-id="e8356-141">Conferencing_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="e8356-141">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="e8356-142">CAA</span><span class="sxs-lookup"><span data-stu-id="e8356-142">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8356-143">512</span><span class="sxs-lookup"><span data-stu-id="e8356-143">512</span></span></p></td>
<td><p><span data-ttu-id="e8356-144">Conference_Auto_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="e8356-144">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="e8356-145">CAA</span><span class="sxs-lookup"><span data-stu-id="e8356-145">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8356-146">1024</span><span class="sxs-lookup"><span data-stu-id="e8356-146">1024</span></span></p></td>
<td><p><span data-ttu-id="e8356-147">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="e8356-147">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="e8356-148">RGS</span><span class="sxs-lookup"><span data-stu-id="e8356-148">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8356-149">1032</span><span class="sxs-lookup"><span data-stu-id="e8356-149">1032</span></span></p></td>
<td><p><span data-ttu-id="e8356-150">Call_Park_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="e8356-150">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="e8356-151">CPS</span><span class="sxs-lookup"><span data-stu-id="e8356-151">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8356-152">1040</span><span class="sxs-lookup"><span data-stu-id="e8356-152">1040</span></span></p></td>
<td><p><span data-ttu-id="e8356-153">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="e8356-153">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="e8356-154">AS</span><span class="sxs-lookup"><span data-stu-id="e8356-154">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8356-155">2048</span><span class="sxs-lookup"><span data-stu-id="e8356-155">2048</span></span></p></td>
<td><p><span data-ttu-id="e8356-156">Microsoft Ccs</span><span class="sxs-lookup"><span data-stu-id="e8356-156">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="e8356-157">CCS</span><span class="sxs-lookup"><span data-stu-id="e8356-157">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8356-158">16386</span><span class="sxs-lookup"><span data-stu-id="e8356-158">16386</span></span></p></td>
<td><p><span data-ttu-id="e8356-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="e8356-159">CoMo</span></span></p></td>
<td><p><span data-ttu-id="e8356-160">CoMo</span><span class="sxs-lookup"><span data-stu-id="e8356-160">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8356-161">16387</span><span class="sxs-lookup"><span data-stu-id="e8356-161">16387</span></span></p></td>
<td><p><span data-ttu-id="e8356-162">CWA</span><span class="sxs-lookup"><span data-stu-id="e8356-162">CWA</span></span></p></td>
<td><p><span data-ttu-id="e8356-163">CWA</span><span class="sxs-lookup"><span data-stu-id="e8356-163">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8356-164">16388</span><span class="sxs-lookup"><span data-stu-id="e8356-164">16388</span></span></p></td>
<td><p><span data-ttu-id="e8356-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="e8356-165">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="e8356-166">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="e8356-166">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8356-167">16389</span><span class="sxs-lookup"><span data-stu-id="e8356-167">16389</span></span></p></td>
<td><p><span data-ttu-id="e8356-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="e8356-168">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="e8356-169">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="e8356-169">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8356-170">16393</span><span class="sxs-lookup"><span data-stu-id="e8356-170">16393</span></span></p></td>
<td><p><span data-ttu-id="e8356-171">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="e8356-171">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="e8356-172">ExUM</span><span class="sxs-lookup"><span data-stu-id="e8356-172">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8356-173">16395</span><span class="sxs-lookup"><span data-stu-id="e8356-173">16395</span></span></p></td>
<td><p><span data-ttu-id="e8356-174">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="e8356-174">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="e8356-175">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="e8356-175">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8356-176">16396</span><span class="sxs-lookup"><span data-stu-id="e8356-176">16396</span></span></p></td>
<td><p><span data-ttu-id="e8356-177">圣保罗</span><span class="sxs-lookup"><span data-stu-id="e8356-177">ST</span></span></p></td>
<td><p><span data-ttu-id="e8356-178">圣保罗</span><span class="sxs-lookup"><span data-stu-id="e8356-178">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8356-179">16397</span><span class="sxs-lookup"><span data-stu-id="e8356-179">16397</span></span></p></td>
<td><p><span data-ttu-id="e8356-180">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="e8356-180">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="e8356-181">ASMCU</span><span class="sxs-lookup"><span data-stu-id="e8356-181">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8356-182">16398</span><span class="sxs-lookup"><span data-stu-id="e8356-182">16398</span></span></p></td>
<td><p><span data-ttu-id="e8356-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="e8356-183">WPLync</span></span></p></td>
<td><p><span data-ttu-id="e8356-184">WPLync</span><span class="sxs-lookup"><span data-stu-id="e8356-184">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8356-185">16399</span><span class="sxs-lookup"><span data-stu-id="e8356-185">16399</span></span></p></td>
<td><p><span data-ttu-id="e8356-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="e8356-186">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="e8356-187">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="e8356-187">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8356-188">16400</span><span class="sxs-lookup"><span data-stu-id="e8356-188">16400</span></span></p></td>
<td><p><span data-ttu-id="e8356-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="e8356-189">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="e8356-190">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="e8356-190">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8356-191">16401</span><span class="sxs-lookup"><span data-stu-id="e8356-191">16401</span></span></p></td>
<td><p><span data-ttu-id="e8356-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="e8356-192">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="e8356-193">iPadLync</span><span class="sxs-lookup"><span data-stu-id="e8356-193">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8356-194">16402</span><span class="sxs-lookup"><span data-stu-id="e8356-194">16402</span></span></p></td>
<td><p><span data-ttu-id="e8356-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="e8356-195">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="e8356-196">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="e8356-196">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8356-197">16403</span><span class="sxs-lookup"><span data-stu-id="e8356-197">16403</span></span></p></td>
<td><p><span data-ttu-id="e8356-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="e8356-198">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="e8356-199">LyncImm</span><span class="sxs-lookup"><span data-stu-id="e8356-199">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8356-200">16404</span><span class="sxs-lookup"><span data-stu-id="e8356-200">16404</span></span></p></td>
<td><p><span data-ttu-id="e8356-201">电脑</span><span class="sxs-lookup"><span data-stu-id="e8356-201">PCS</span></span></p></td>
<td><p><span data-ttu-id="e8356-202">电脑</span><span class="sxs-lookup"><span data-stu-id="e8356-202">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8356-203">16405</span><span class="sxs-lookup"><span data-stu-id="e8356-203">16405</span></span></p></td>
<td><p><span data-ttu-id="e8356-204">LWA</span><span class="sxs-lookup"><span data-stu-id="e8356-204">LWA</span></span></p></td>
<td><p><span data-ttu-id="e8356-205">LWA</span><span class="sxs-lookup"><span data-stu-id="e8356-205">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8356-206">16406</span><span class="sxs-lookup"><span data-stu-id="e8356-206">16406</span></span></p></td>
<td><p><span data-ttu-id="e8356-207">OWA</span><span class="sxs-lookup"><span data-stu-id="e8356-207">OWA</span></span></p></td>
<td><p><span data-ttu-id="e8356-208">OWA</span><span class="sxs-lookup"><span data-stu-id="e8356-208">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8356-209">16407</span><span class="sxs-lookup"><span data-stu-id="e8356-209">16407</span></span></p></td>
<td><p><span data-ttu-id="e8356-210">AOC</span><span class="sxs-lookup"><span data-stu-id="e8356-210">AOC</span></span></p></td>
<td><p><span data-ttu-id="e8356-211">AOC</span><span class="sxs-lookup"><span data-stu-id="e8356-211">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8356-212">16408</span><span class="sxs-lookup"><span data-stu-id="e8356-212">16408</span></span></p></td>
<td><p><span data-ttu-id="e8356-213">GCC</span><span class="sxs-lookup"><span data-stu-id="e8356-213">GCC</span></span></p></td>
<td><p><span data-ttu-id="e8356-214">GCC</span><span class="sxs-lookup"><span data-stu-id="e8356-214">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8356-215">16409</span><span class="sxs-lookup"><span data-stu-id="e8356-215">16409</span></span></p></td>
<td><p><span data-ttu-id="e8356-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="e8356-216">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="e8356-217">IMMCU</span><span class="sxs-lookup"><span data-stu-id="e8356-217">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8356-218">16410</span><span class="sxs-lookup"><span data-stu-id="e8356-218">16410</span></span></p></td>
<td><p><span data-ttu-id="e8356-219">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="e8356-219">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="e8356-220">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="e8356-220">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8356-221">32769</span><span class="sxs-lookup"><span data-stu-id="e8356-221">32769</span></span></p></td>
<td><p><span data-ttu-id="e8356-222">网关</span><span class="sxs-lookup"><span data-stu-id="e8356-222">Gateway</span></span></p></td>
<td><p><span data-ttu-id="e8356-223">网关</span><span class="sxs-lookup"><span data-stu-id="e8356-223">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8356-224">32770</span><span class="sxs-lookup"><span data-stu-id="e8356-224">32770</span></span></p></td>
<td><p><span data-ttu-id="e8356-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="e8356-225">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="e8356-226">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="e8356-226">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

