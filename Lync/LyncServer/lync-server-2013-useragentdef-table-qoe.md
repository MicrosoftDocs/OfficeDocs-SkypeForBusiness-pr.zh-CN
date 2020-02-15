---
title: Lync Server 2013： UserAgentDef 表（QoE）
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
ms.openlocfilehash: ebddb1e0313d0c47acb4171929d12d352f69c260
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007601"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-qoe-in-lync-server-2013"></a><span data-ttu-id="52c86-102">Lync Server 2013 中的 UserAgentDef 表（QoE）</span><span class="sxs-lookup"><span data-stu-id="52c86-102">UserAgentDef table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52c86-103">_**上次修改的主题：** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="52c86-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="52c86-104">UserAgentDef 表将用户代理标识符映射到代理的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="52c86-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="52c86-105">用户代理是用于连接到 Microsoft Lync Server 2013 的软件客户端。</span><span class="sxs-lookup"><span data-stu-id="52c86-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52c86-106">UAType</span><span class="sxs-lookup"><span data-stu-id="52c86-106">UAType</span></span></th>
<th><span data-ttu-id="52c86-107">UAName</span><span class="sxs-lookup"><span data-stu-id="52c86-107">UAName</span></span></th>
<th><span data-ttu-id="52c86-108">UACategory</span><span class="sxs-lookup"><span data-stu-id="52c86-108">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52c86-109">1 </span><span class="sxs-lookup"><span data-stu-id="52c86-109">1</span></span></p></td>
<td><p><span data-ttu-id="52c86-110">MediationServer</span><span class="sxs-lookup"><span data-stu-id="52c86-110">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="52c86-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="52c86-111">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c86-112">2 </span><span class="sxs-lookup"><span data-stu-id="52c86-112">2</span></span></p></td>
<td><p><span data-ttu-id="52c86-113">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="52c86-113">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="52c86-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="52c86-114">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c86-115">4 </span><span class="sxs-lookup"><span data-stu-id="52c86-115">4</span></span></p></td>
<td><p><span data-ttu-id="52c86-116">OC</span><span class="sxs-lookup"><span data-stu-id="52c86-116">OC</span></span></p></td>
<td><p><span data-ttu-id="52c86-117">OC</span><span class="sxs-lookup"><span data-stu-id="52c86-117">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c86-118">8 </span><span class="sxs-lookup"><span data-stu-id="52c86-118">8</span></span></p></td>
<td><p><span data-ttu-id="52c86-119">OCPhone</span><span class="sxs-lookup"><span data-stu-id="52c86-119">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="52c86-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="52c86-120">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c86-121">16 </span><span class="sxs-lookup"><span data-stu-id="52c86-121">16</span></span></p></td>
<td><p><span data-ttu-id="52c86-122">LMC</span><span class="sxs-lookup"><span data-stu-id="52c86-122">LMC</span></span></p></td>
<td><p><span data-ttu-id="52c86-123">LMC</span><span class="sxs-lookup"><span data-stu-id="52c86-123">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c86-124">32</span><span class="sxs-lookup"><span data-stu-id="52c86-124">32</span></span></p></td>
<td><p><span data-ttu-id="52c86-125">DVT</span><span class="sxs-lookup"><span data-stu-id="52c86-125">DVT</span></span></p></td>
<td><p><span data-ttu-id="52c86-126">DVT</span><span class="sxs-lookup"><span data-stu-id="52c86-126">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c86-127">64</span><span class="sxs-lookup"><span data-stu-id="52c86-127">64</span></span></p></td>
<td><p><span data-ttu-id="52c86-128">MM</span><span class="sxs-lookup"><span data-stu-id="52c86-128">MM</span></span></p></td>
<td><p><span data-ttu-id="52c86-129">MM</span><span class="sxs-lookup"><span data-stu-id="52c86-129">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c86-130">64</span><span class="sxs-lookup"><span data-stu-id="52c86-130">64</span></span></p></td>
<td><p><span data-ttu-id="52c86-131">EMC</span><span class="sxs-lookup"><span data-stu-id="52c86-131">MC</span></span></p></td>
<td><p><span data-ttu-id="52c86-132">MM</span><span class="sxs-lookup"><span data-stu-id="52c86-132">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c86-133">128</span><span class="sxs-lookup"><span data-stu-id="52c86-133">128</span></span></p></td>
<td><p><span data-ttu-id="52c86-134">随</span><span class="sxs-lookup"><span data-stu-id="52c86-134">Attendant</span></span></p></td>
<td><p><span data-ttu-id="52c86-135">随</span><span class="sxs-lookup"><span data-stu-id="52c86-135">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c86-136">256</span><span class="sxs-lookup"><span data-stu-id="52c86-136">256</span></span></p></td>
<td><p><span data-ttu-id="52c86-137">Conferencing_Announcement_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="52c86-137">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="52c86-138">CAS</span><span class="sxs-lookup"><span data-stu-id="52c86-138">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c86-139">512</span><span class="sxs-lookup"><span data-stu-id="52c86-139">512</span></span></p></td>
<td><p><span data-ttu-id="52c86-140">Conferencing_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="52c86-140">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="52c86-141">CAA</span><span class="sxs-lookup"><span data-stu-id="52c86-141">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c86-142">512</span><span class="sxs-lookup"><span data-stu-id="52c86-142">512</span></span></p></td>
<td><p><span data-ttu-id="52c86-143">Conference_Auto_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="52c86-143">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="52c86-144">CAA</span><span class="sxs-lookup"><span data-stu-id="52c86-144">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c86-145">1024</span><span class="sxs-lookup"><span data-stu-id="52c86-145">1024</span></span></p></td>
<td><p><span data-ttu-id="52c86-146">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="52c86-146">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="52c86-147">RGS</span><span class="sxs-lookup"><span data-stu-id="52c86-147">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c86-148">1032</span><span class="sxs-lookup"><span data-stu-id="52c86-148">1032</span></span></p></td>
<td><p><span data-ttu-id="52c86-149">Call_Park_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="52c86-149">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="52c86-150">CPS</span><span class="sxs-lookup"><span data-stu-id="52c86-150">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c86-151">1040</span><span class="sxs-lookup"><span data-stu-id="52c86-151">1040</span></span></p></td>
<td><p><span data-ttu-id="52c86-152">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="52c86-152">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="52c86-153">AS</span><span class="sxs-lookup"><span data-stu-id="52c86-153">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c86-154">2048</span><span class="sxs-lookup"><span data-stu-id="52c86-154">2048</span></span></p></td>
<td><p><span data-ttu-id="52c86-155">Microsoft Ccs</span><span class="sxs-lookup"><span data-stu-id="52c86-155">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="52c86-156">CCS</span><span class="sxs-lookup"><span data-stu-id="52c86-156">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c86-157">16386</span><span class="sxs-lookup"><span data-stu-id="52c86-157">16386</span></span></p></td>
<td><p><span data-ttu-id="52c86-158">CoMo</span><span class="sxs-lookup"><span data-stu-id="52c86-158">CoMo</span></span></p></td>
<td><p><span data-ttu-id="52c86-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="52c86-159">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c86-160">16387</span><span class="sxs-lookup"><span data-stu-id="52c86-160">16387</span></span></p></td>
<td><p><span data-ttu-id="52c86-161">CWA</span><span class="sxs-lookup"><span data-stu-id="52c86-161">CWA</span></span></p></td>
<td><p><span data-ttu-id="52c86-162">CWA</span><span class="sxs-lookup"><span data-stu-id="52c86-162">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c86-163">16388</span><span class="sxs-lookup"><span data-stu-id="52c86-163">16388</span></span></p></td>
<td><p><span data-ttu-id="52c86-164">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="52c86-164">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="52c86-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="52c86-165">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c86-166">16389</span><span class="sxs-lookup"><span data-stu-id="52c86-166">16389</span></span></p></td>
<td><p><span data-ttu-id="52c86-167">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="52c86-167">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="52c86-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="52c86-168">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c86-169">16393</span><span class="sxs-lookup"><span data-stu-id="52c86-169">16393</span></span></p></td>
<td><p><span data-ttu-id="52c86-170">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="52c86-170">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="52c86-171">ExUM</span><span class="sxs-lookup"><span data-stu-id="52c86-171">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c86-172">16395</span><span class="sxs-lookup"><span data-stu-id="52c86-172">16395</span></span></p></td>
<td><p><span data-ttu-id="52c86-173">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="52c86-173">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="52c86-174">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="52c86-174">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c86-175">16396</span><span class="sxs-lookup"><span data-stu-id="52c86-175">16396</span></span></p></td>
<td><p><span data-ttu-id="52c86-176">圣保罗</span><span class="sxs-lookup"><span data-stu-id="52c86-176">ST</span></span></p></td>
<td><p><span data-ttu-id="52c86-177">圣保罗</span><span class="sxs-lookup"><span data-stu-id="52c86-177">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c86-178">16397</span><span class="sxs-lookup"><span data-stu-id="52c86-178">16397</span></span></p></td>
<td><p><span data-ttu-id="52c86-179">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="52c86-179">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="52c86-180">ASMCU</span><span class="sxs-lookup"><span data-stu-id="52c86-180">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c86-181">16398</span><span class="sxs-lookup"><span data-stu-id="52c86-181">16398</span></span></p></td>
<td><p><span data-ttu-id="52c86-182">WPLync</span><span class="sxs-lookup"><span data-stu-id="52c86-182">WPLync</span></span></p></td>
<td><p><span data-ttu-id="52c86-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="52c86-183">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c86-184">16399</span><span class="sxs-lookup"><span data-stu-id="52c86-184">16399</span></span></p></td>
<td><p><span data-ttu-id="52c86-185">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="52c86-185">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="52c86-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="52c86-186">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c86-187">16400</span><span class="sxs-lookup"><span data-stu-id="52c86-187">16400</span></span></p></td>
<td><p><span data-ttu-id="52c86-188">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="52c86-188">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="52c86-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="52c86-189">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c86-190">16401</span><span class="sxs-lookup"><span data-stu-id="52c86-190">16401</span></span></p></td>
<td><p><span data-ttu-id="52c86-191">iPadLync</span><span class="sxs-lookup"><span data-stu-id="52c86-191">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="52c86-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="52c86-192">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c86-193">16402</span><span class="sxs-lookup"><span data-stu-id="52c86-193">16402</span></span></p></td>
<td><p><span data-ttu-id="52c86-194">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="52c86-194">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="52c86-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="52c86-195">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c86-196">16403</span><span class="sxs-lookup"><span data-stu-id="52c86-196">16403</span></span></p></td>
<td><p><span data-ttu-id="52c86-197">LyncImm</span><span class="sxs-lookup"><span data-stu-id="52c86-197">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="52c86-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="52c86-198">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c86-199">16404</span><span class="sxs-lookup"><span data-stu-id="52c86-199">16404</span></span></p></td>
<td><p><span data-ttu-id="52c86-200">电脑</span><span class="sxs-lookup"><span data-stu-id="52c86-200">PCS</span></span></p></td>
<td><p><span data-ttu-id="52c86-201">电脑</span><span class="sxs-lookup"><span data-stu-id="52c86-201">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c86-202">16405</span><span class="sxs-lookup"><span data-stu-id="52c86-202">16405</span></span></p></td>
<td><p><span data-ttu-id="52c86-203">LWA</span><span class="sxs-lookup"><span data-stu-id="52c86-203">LWA</span></span></p></td>
<td><p><span data-ttu-id="52c86-204">LWA</span><span class="sxs-lookup"><span data-stu-id="52c86-204">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c86-205">16406</span><span class="sxs-lookup"><span data-stu-id="52c86-205">16406</span></span></p></td>
<td><p><span data-ttu-id="52c86-206">OWA</span><span class="sxs-lookup"><span data-stu-id="52c86-206">OWA</span></span></p></td>
<td><p><span data-ttu-id="52c86-207">OWA</span><span class="sxs-lookup"><span data-stu-id="52c86-207">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c86-208">16407</span><span class="sxs-lookup"><span data-stu-id="52c86-208">16407</span></span></p></td>
<td><p><span data-ttu-id="52c86-209">AOC</span><span class="sxs-lookup"><span data-stu-id="52c86-209">AOC</span></span></p></td>
<td><p><span data-ttu-id="52c86-210">AOC</span><span class="sxs-lookup"><span data-stu-id="52c86-210">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c86-211">16408</span><span class="sxs-lookup"><span data-stu-id="52c86-211">16408</span></span></p></td>
<td><p><span data-ttu-id="52c86-212">GCC</span><span class="sxs-lookup"><span data-stu-id="52c86-212">GCC</span></span></p></td>
<td><p><span data-ttu-id="52c86-213">GCC</span><span class="sxs-lookup"><span data-stu-id="52c86-213">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c86-214">16409</span><span class="sxs-lookup"><span data-stu-id="52c86-214">16409</span></span></p></td>
<td><p><span data-ttu-id="52c86-215">IMMCU</span><span class="sxs-lookup"><span data-stu-id="52c86-215">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="52c86-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="52c86-216">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c86-217">16410</span><span class="sxs-lookup"><span data-stu-id="52c86-217">16410</span></span></p></td>
<td><p><span data-ttu-id="52c86-218">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="52c86-218">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="52c86-219">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="52c86-219">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c86-220">32769</span><span class="sxs-lookup"><span data-stu-id="52c86-220">32769</span></span></p></td>
<td><p><span data-ttu-id="52c86-221">网关</span><span class="sxs-lookup"><span data-stu-id="52c86-221">Gateway</span></span></p></td>
<td><p><span data-ttu-id="52c86-222">网关</span><span class="sxs-lookup"><span data-stu-id="52c86-222">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c86-223">32770</span><span class="sxs-lookup"><span data-stu-id="52c86-223">32770</span></span></p></td>
<td><p><span data-ttu-id="52c86-224">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="52c86-224">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="52c86-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="52c86-225">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

