---
title: Lync Server 2013： UserAgentDef table （QoE）
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
ms.openlocfilehash: 146c22b77ac6d2681c1844feade86242e1fcd72f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-qoe-in-lync-server-2013"></a><span data-ttu-id="92673-102">Lync Server 2013 中的 UserAgentDef 表（QoE）</span><span class="sxs-lookup"><span data-stu-id="92673-102">UserAgentDef table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92673-103">_**主题上次修改时间：** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="92673-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="92673-104">UserAgentDef 表将用户代理标识符映射到代理的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="92673-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="92673-105">用户代理是用于连接到 Microsoft Lync Server 2013 的软件客户端。</span><span class="sxs-lookup"><span data-stu-id="92673-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="92673-106">UAType</span><span class="sxs-lookup"><span data-stu-id="92673-106">UAType</span></span></th>
<th><span data-ttu-id="92673-107">UAName</span><span class="sxs-lookup"><span data-stu-id="92673-107">UAName</span></span></th>
<th><span data-ttu-id="92673-108">UACategory</span><span class="sxs-lookup"><span data-stu-id="92673-108">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92673-109">1</span><span class="sxs-lookup"><span data-stu-id="92673-109">1</span></span></p></td>
<td><p><span data-ttu-id="92673-110">MediationServer</span><span class="sxs-lookup"><span data-stu-id="92673-110">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="92673-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="92673-111">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92673-112">ppls-2</span><span class="sxs-lookup"><span data-stu-id="92673-112">2</span></span></p></td>
<td><p><span data-ttu-id="92673-113">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="92673-113">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="92673-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="92673-114">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92673-115">4</span><span class="sxs-lookup"><span data-stu-id="92673-115">4</span></span></p></td>
<td><p><span data-ttu-id="92673-116">OC</span><span class="sxs-lookup"><span data-stu-id="92673-116">OC</span></span></p></td>
<td><p><span data-ttu-id="92673-117">OC</span><span class="sxs-lookup"><span data-stu-id="92673-117">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92673-118">个</span><span class="sxs-lookup"><span data-stu-id="92673-118">8</span></span></p></td>
<td><p><span data-ttu-id="92673-119">OCPhone</span><span class="sxs-lookup"><span data-stu-id="92673-119">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="92673-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="92673-120">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92673-121">utf-16</span><span class="sxs-lookup"><span data-stu-id="92673-121">16</span></span></p></td>
<td><p><span data-ttu-id="92673-122">LMC</span><span class="sxs-lookup"><span data-stu-id="92673-122">LMC</span></span></p></td>
<td><p><span data-ttu-id="92673-123">LMC</span><span class="sxs-lookup"><span data-stu-id="92673-123">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92673-124">32</span><span class="sxs-lookup"><span data-stu-id="92673-124">32</span></span></p></td>
<td><p><span data-ttu-id="92673-125">DVT</span><span class="sxs-lookup"><span data-stu-id="92673-125">DVT</span></span></p></td>
<td><p><span data-ttu-id="92673-126">DVT</span><span class="sxs-lookup"><span data-stu-id="92673-126">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92673-127">64</span><span class="sxs-lookup"><span data-stu-id="92673-127">64</span></span></p></td>
<td><p><span data-ttu-id="92673-128">分钟</span><span class="sxs-lookup"><span data-stu-id="92673-128">MM</span></span></p></td>
<td><p><span data-ttu-id="92673-129">分钟</span><span class="sxs-lookup"><span data-stu-id="92673-129">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92673-130">64</span><span class="sxs-lookup"><span data-stu-id="92673-130">64</span></span></p></td>
<td><p><span data-ttu-id="92673-131">MC</span><span class="sxs-lookup"><span data-stu-id="92673-131">MC</span></span></p></td>
<td><p><span data-ttu-id="92673-132">分钟</span><span class="sxs-lookup"><span data-stu-id="92673-132">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92673-133">128</span><span class="sxs-lookup"><span data-stu-id="92673-133">128</span></span></p></td>
<td><p><span data-ttu-id="92673-134">助理</span><span class="sxs-lookup"><span data-stu-id="92673-134">Attendant</span></span></p></td>
<td><p><span data-ttu-id="92673-135">助理</span><span class="sxs-lookup"><span data-stu-id="92673-135">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92673-136">256</span><span class="sxs-lookup"><span data-stu-id="92673-136">256</span></span></p></td>
<td><p><span data-ttu-id="92673-137">Conferencing_Announcement_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="92673-137">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="92673-138">而言</span><span class="sxs-lookup"><span data-stu-id="92673-138">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92673-139">512</span><span class="sxs-lookup"><span data-stu-id="92673-139">512</span></span></p></td>
<td><p><span data-ttu-id="92673-140">Conferencing_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="92673-140">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="92673-141">CAA</span><span class="sxs-lookup"><span data-stu-id="92673-141">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92673-142">512</span><span class="sxs-lookup"><span data-stu-id="92673-142">512</span></span></p></td>
<td><p><span data-ttu-id="92673-143">Conference_Auto_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="92673-143">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="92673-144">CAA</span><span class="sxs-lookup"><span data-stu-id="92673-144">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92673-145">1024</span><span class="sxs-lookup"><span data-stu-id="92673-145">1024</span></span></p></td>
<td><p><span data-ttu-id="92673-146">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="92673-146">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="92673-147">RG</span><span class="sxs-lookup"><span data-stu-id="92673-147">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92673-148">1032</span><span class="sxs-lookup"><span data-stu-id="92673-148">1032</span></span></p></td>
<td><p><span data-ttu-id="92673-149">Call_Park_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="92673-149">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="92673-150">方面</span><span class="sxs-lookup"><span data-stu-id="92673-150">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92673-151">1040</span><span class="sxs-lookup"><span data-stu-id="92673-151">1040</span></span></p></td>
<td><p><span data-ttu-id="92673-152">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="92673-152">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="92673-153">方式</span><span class="sxs-lookup"><span data-stu-id="92673-153">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92673-154">2048</span><span class="sxs-lookup"><span data-stu-id="92673-154">2048</span></span></p></td>
<td><p><span data-ttu-id="92673-155">Microsoft Ccs</span><span class="sxs-lookup"><span data-stu-id="92673-155">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="92673-156">CCS</span><span class="sxs-lookup"><span data-stu-id="92673-156">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92673-157">16386</span><span class="sxs-lookup"><span data-stu-id="92673-157">16386</span></span></p></td>
<td><p><span data-ttu-id="92673-158">CoMo</span><span class="sxs-lookup"><span data-stu-id="92673-158">CoMo</span></span></p></td>
<td><p><span data-ttu-id="92673-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="92673-159">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92673-160">16387</span><span class="sxs-lookup"><span data-stu-id="92673-160">16387</span></span></p></td>
<td><p><span data-ttu-id="92673-161">CWA</span><span class="sxs-lookup"><span data-stu-id="92673-161">CWA</span></span></p></td>
<td><p><span data-ttu-id="92673-162">CWA</span><span class="sxs-lookup"><span data-stu-id="92673-162">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92673-163">16388</span><span class="sxs-lookup"><span data-stu-id="92673-163">16388</span></span></p></td>
<td><p><span data-ttu-id="92673-164">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="92673-164">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="92673-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="92673-165">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92673-166">16389</span><span class="sxs-lookup"><span data-stu-id="92673-166">16389</span></span></p></td>
<td><p><span data-ttu-id="92673-167">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="92673-167">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="92673-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="92673-168">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92673-169">16393</span><span class="sxs-lookup"><span data-stu-id="92673-169">16393</span></span></p></td>
<td><p><span data-ttu-id="92673-170">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="92673-170">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="92673-171">ExUM</span><span class="sxs-lookup"><span data-stu-id="92673-171">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92673-172">16395</span><span class="sxs-lookup"><span data-stu-id="92673-172">16395</span></span></p></td>
<td><p><span data-ttu-id="92673-173">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="92673-173">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="92673-174">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="92673-174">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92673-175">16396</span><span class="sxs-lookup"><span data-stu-id="92673-175">16396</span></span></p></td>
<td><p><span data-ttu-id="92673-176">短期</span><span class="sxs-lookup"><span data-stu-id="92673-176">ST</span></span></p></td>
<td><p><span data-ttu-id="92673-177">短期</span><span class="sxs-lookup"><span data-stu-id="92673-177">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92673-178">16397</span><span class="sxs-lookup"><span data-stu-id="92673-178">16397</span></span></p></td>
<td><p><span data-ttu-id="92673-179">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="92673-179">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="92673-180">ASMCU</span><span class="sxs-lookup"><span data-stu-id="92673-180">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92673-181">16398</span><span class="sxs-lookup"><span data-stu-id="92673-181">16398</span></span></p></td>
<td><p><span data-ttu-id="92673-182">WPLync</span><span class="sxs-lookup"><span data-stu-id="92673-182">WPLync</span></span></p></td>
<td><p><span data-ttu-id="92673-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="92673-183">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92673-184">16399</span><span class="sxs-lookup"><span data-stu-id="92673-184">16399</span></span></p></td>
<td><p><span data-ttu-id="92673-185">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="92673-185">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="92673-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="92673-186">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92673-187">16400</span><span class="sxs-lookup"><span data-stu-id="92673-187">16400</span></span></p></td>
<td><p><span data-ttu-id="92673-188">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="92673-188">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="92673-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="92673-189">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92673-190">16401</span><span class="sxs-lookup"><span data-stu-id="92673-190">16401</span></span></p></td>
<td><p><span data-ttu-id="92673-191">iPadLync</span><span class="sxs-lookup"><span data-stu-id="92673-191">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="92673-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="92673-192">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92673-193">16402</span><span class="sxs-lookup"><span data-stu-id="92673-193">16402</span></span></p></td>
<td><p><span data-ttu-id="92673-194">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="92673-194">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="92673-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="92673-195">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92673-196">16403</span><span class="sxs-lookup"><span data-stu-id="92673-196">16403</span></span></p></td>
<td><p><span data-ttu-id="92673-197">LyncImm</span><span class="sxs-lookup"><span data-stu-id="92673-197">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="92673-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="92673-198">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92673-199">16404</span><span class="sxs-lookup"><span data-stu-id="92673-199">16404</span></span></p></td>
<td><p><span data-ttu-id="92673-200">笔记本电脑</span><span class="sxs-lookup"><span data-stu-id="92673-200">PCS</span></span></p></td>
<td><p><span data-ttu-id="92673-201">笔记本电脑</span><span class="sxs-lookup"><span data-stu-id="92673-201">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92673-202">16405</span><span class="sxs-lookup"><span data-stu-id="92673-202">16405</span></span></p></td>
<td><p><span data-ttu-id="92673-203">LWA</span><span class="sxs-lookup"><span data-stu-id="92673-203">LWA</span></span></p></td>
<td><p><span data-ttu-id="92673-204">LWA</span><span class="sxs-lookup"><span data-stu-id="92673-204">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92673-205">16406</span><span class="sxs-lookup"><span data-stu-id="92673-205">16406</span></span></p></td>
<td><p><span data-ttu-id="92673-206">OWA</span><span class="sxs-lookup"><span data-stu-id="92673-206">OWA</span></span></p></td>
<td><p><span data-ttu-id="92673-207">OWA</span><span class="sxs-lookup"><span data-stu-id="92673-207">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92673-208">16407</span><span class="sxs-lookup"><span data-stu-id="92673-208">16407</span></span></p></td>
<td><p><span data-ttu-id="92673-209">AOC</span><span class="sxs-lookup"><span data-stu-id="92673-209">AOC</span></span></p></td>
<td><p><span data-ttu-id="92673-210">AOC</span><span class="sxs-lookup"><span data-stu-id="92673-210">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92673-211">16408</span><span class="sxs-lookup"><span data-stu-id="92673-211">16408</span></span></p></td>
<td><p><span data-ttu-id="92673-212">GCC</span><span class="sxs-lookup"><span data-stu-id="92673-212">GCC</span></span></p></td>
<td><p><span data-ttu-id="92673-213">GCC</span><span class="sxs-lookup"><span data-stu-id="92673-213">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92673-214">16409</span><span class="sxs-lookup"><span data-stu-id="92673-214">16409</span></span></p></td>
<td><p><span data-ttu-id="92673-215">IMMCU</span><span class="sxs-lookup"><span data-stu-id="92673-215">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="92673-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="92673-216">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92673-217">16410</span><span class="sxs-lookup"><span data-stu-id="92673-217">16410</span></span></p></td>
<td><p><span data-ttu-id="92673-218">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="92673-218">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="92673-219">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="92673-219">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92673-220">32769</span><span class="sxs-lookup"><span data-stu-id="92673-220">32769</span></span></p></td>
<td><p><span data-ttu-id="92673-221">网关</span><span class="sxs-lookup"><span data-stu-id="92673-221">Gateway</span></span></p></td>
<td><p><span data-ttu-id="92673-222">网关</span><span class="sxs-lookup"><span data-stu-id="92673-222">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92673-223">32770</span><span class="sxs-lookup"><span data-stu-id="92673-223">32770</span></span></p></td>
<td><p><span data-ttu-id="92673-224">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="92673-224">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="92673-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="92673-225">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

