---
title: Lync Server 2013： UserAgentDef 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgentDef table
ms:assetid: 96c49239-d999-4045-8b64-9d1940cce8ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205100(v=OCS.15)
ms:contentKeyID: 48184860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0996abb7098ba636fc31d27388257f570a549ce2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-in-lync-server-2013"></a><span data-ttu-id="e10fd-102">Lync Server 2013 中的 UserAgentDef 表</span><span class="sxs-lookup"><span data-stu-id="e10fd-102">UserAgentDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e10fd-103">_**上次修改的主题：** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="e10fd-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="e10fd-104">UserAgentDef 表将用户代理标识符映射到代理的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="e10fd-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="e10fd-105">用户代理是用于连接到 Microsoft Lync Server 2013 的软件客户端。</span><span class="sxs-lookup"><span data-stu-id="e10fd-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="e10fd-106">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="e10fd-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e10fd-107">UAType</span><span class="sxs-lookup"><span data-stu-id="e10fd-107">UAType</span></span></th>
<th><span data-ttu-id="e10fd-108">UAName</span><span class="sxs-lookup"><span data-stu-id="e10fd-108">UAName</span></span></th>
<th><span data-ttu-id="e10fd-109">UACategory</span><span class="sxs-lookup"><span data-stu-id="e10fd-109">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e10fd-110">1 </span><span class="sxs-lookup"><span data-stu-id="e10fd-110">1</span></span></p></td>
<td><p><span data-ttu-id="e10fd-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="e10fd-111">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="e10fd-112">MediationServer</span><span class="sxs-lookup"><span data-stu-id="e10fd-112">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e10fd-113">2 </span><span class="sxs-lookup"><span data-stu-id="e10fd-113">2</span></span></p></td>
<td><p><span data-ttu-id="e10fd-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="e10fd-114">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="e10fd-115">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="e10fd-115">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e10fd-116">4 </span><span class="sxs-lookup"><span data-stu-id="e10fd-116">4</span></span></p></td>
<td><p><span data-ttu-id="e10fd-117">OC</span><span class="sxs-lookup"><span data-stu-id="e10fd-117">OC</span></span></p></td>
<td><p><span data-ttu-id="e10fd-118">OC</span><span class="sxs-lookup"><span data-stu-id="e10fd-118">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e10fd-119">8 </span><span class="sxs-lookup"><span data-stu-id="e10fd-119">8</span></span></p></td>
<td><p><span data-ttu-id="e10fd-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="e10fd-120">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="e10fd-121">OCPhone</span><span class="sxs-lookup"><span data-stu-id="e10fd-121">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e10fd-122">16 </span><span class="sxs-lookup"><span data-stu-id="e10fd-122">16</span></span></p></td>
<td><p><span data-ttu-id="e10fd-123">LMC</span><span class="sxs-lookup"><span data-stu-id="e10fd-123">LMC</span></span></p></td>
<td><p><span data-ttu-id="e10fd-124">LMC</span><span class="sxs-lookup"><span data-stu-id="e10fd-124">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e10fd-125">32</span><span class="sxs-lookup"><span data-stu-id="e10fd-125">32</span></span></p></td>
<td><p><span data-ttu-id="e10fd-126">DVT</span><span class="sxs-lookup"><span data-stu-id="e10fd-126">DVT</span></span></p></td>
<td><p><span data-ttu-id="e10fd-127">DVT</span><span class="sxs-lookup"><span data-stu-id="e10fd-127">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e10fd-128">64</span><span class="sxs-lookup"><span data-stu-id="e10fd-128">64</span></span></p></td>
<td><p><span data-ttu-id="e10fd-129">MM</span><span class="sxs-lookup"><span data-stu-id="e10fd-129">MM</span></span></p></td>
<td><p><span data-ttu-id="e10fd-130">MM</span><span class="sxs-lookup"><span data-stu-id="e10fd-130">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e10fd-131">64</span><span class="sxs-lookup"><span data-stu-id="e10fd-131">64</span></span></p></td>
<td><p><span data-ttu-id="e10fd-132">EMC</span><span class="sxs-lookup"><span data-stu-id="e10fd-132">MC</span></span></p></td>
<td><p><span data-ttu-id="e10fd-133">MM</span><span class="sxs-lookup"><span data-stu-id="e10fd-133">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e10fd-134">128</span><span class="sxs-lookup"><span data-stu-id="e10fd-134">128</span></span></p></td>
<td><p><span data-ttu-id="e10fd-135">随</span><span class="sxs-lookup"><span data-stu-id="e10fd-135">Attendant</span></span></p></td>
<td><p><span data-ttu-id="e10fd-136">随</span><span class="sxs-lookup"><span data-stu-id="e10fd-136">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e10fd-137">256</span><span class="sxs-lookup"><span data-stu-id="e10fd-137">256</span></span></p></td>
<td><p><span data-ttu-id="e10fd-138">Conferencing_Announcement_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="e10fd-138">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="e10fd-139">CAS</span><span class="sxs-lookup"><span data-stu-id="e10fd-139">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e10fd-140">512</span><span class="sxs-lookup"><span data-stu-id="e10fd-140">512</span></span></p></td>
<td><p><span data-ttu-id="e10fd-141">Conferencing_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="e10fd-141">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="e10fd-142">CAA</span><span class="sxs-lookup"><span data-stu-id="e10fd-142">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e10fd-143">512</span><span class="sxs-lookup"><span data-stu-id="e10fd-143">512</span></span></p></td>
<td><p><span data-ttu-id="e10fd-144">Conference_Auto_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="e10fd-144">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="e10fd-145">CAA</span><span class="sxs-lookup"><span data-stu-id="e10fd-145">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e10fd-146">1024</span><span class="sxs-lookup"><span data-stu-id="e10fd-146">1024</span></span></p></td>
<td><p><span data-ttu-id="e10fd-147">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="e10fd-147">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="e10fd-148">RGS</span><span class="sxs-lookup"><span data-stu-id="e10fd-148">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e10fd-149">1032</span><span class="sxs-lookup"><span data-stu-id="e10fd-149">1032</span></span></p></td>
<td><p><span data-ttu-id="e10fd-150">Call_Park_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="e10fd-150">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="e10fd-151">CPS</span><span class="sxs-lookup"><span data-stu-id="e10fd-151">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e10fd-152">1040</span><span class="sxs-lookup"><span data-stu-id="e10fd-152">1040</span></span></p></td>
<td><p><span data-ttu-id="e10fd-153">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="e10fd-153">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="e10fd-154">AS</span><span class="sxs-lookup"><span data-stu-id="e10fd-154">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e10fd-155">2048</span><span class="sxs-lookup"><span data-stu-id="e10fd-155">2048</span></span></p></td>
<td><p><span data-ttu-id="e10fd-156">Microsoft Ccs</span><span class="sxs-lookup"><span data-stu-id="e10fd-156">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="e10fd-157">CCS</span><span class="sxs-lookup"><span data-stu-id="e10fd-157">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e10fd-158">16386</span><span class="sxs-lookup"><span data-stu-id="e10fd-158">16386</span></span></p></td>
<td><p><span data-ttu-id="e10fd-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="e10fd-159">CoMo</span></span></p></td>
<td><p><span data-ttu-id="e10fd-160">CoMo</span><span class="sxs-lookup"><span data-stu-id="e10fd-160">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e10fd-161">16387</span><span class="sxs-lookup"><span data-stu-id="e10fd-161">16387</span></span></p></td>
<td><p><span data-ttu-id="e10fd-162">CWA</span><span class="sxs-lookup"><span data-stu-id="e10fd-162">CWA</span></span></p></td>
<td><p><span data-ttu-id="e10fd-163">CWA</span><span class="sxs-lookup"><span data-stu-id="e10fd-163">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e10fd-164">16388</span><span class="sxs-lookup"><span data-stu-id="e10fd-164">16388</span></span></p></td>
<td><p><span data-ttu-id="e10fd-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="e10fd-165">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="e10fd-166">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="e10fd-166">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e10fd-167">16389</span><span class="sxs-lookup"><span data-stu-id="e10fd-167">16389</span></span></p></td>
<td><p><span data-ttu-id="e10fd-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="e10fd-168">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="e10fd-169">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="e10fd-169">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e10fd-170">16393</span><span class="sxs-lookup"><span data-stu-id="e10fd-170">16393</span></span></p></td>
<td><p><span data-ttu-id="e10fd-171">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="e10fd-171">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="e10fd-172">ExUM</span><span class="sxs-lookup"><span data-stu-id="e10fd-172">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e10fd-173">16395</span><span class="sxs-lookup"><span data-stu-id="e10fd-173">16395</span></span></p></td>
<td><p><span data-ttu-id="e10fd-174">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="e10fd-174">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="e10fd-175">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="e10fd-175">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e10fd-176">16396</span><span class="sxs-lookup"><span data-stu-id="e10fd-176">16396</span></span></p></td>
<td><p><span data-ttu-id="e10fd-177">圣保罗</span><span class="sxs-lookup"><span data-stu-id="e10fd-177">ST</span></span></p></td>
<td><p><span data-ttu-id="e10fd-178">圣保罗</span><span class="sxs-lookup"><span data-stu-id="e10fd-178">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e10fd-179">16397</span><span class="sxs-lookup"><span data-stu-id="e10fd-179">16397</span></span></p></td>
<td><p><span data-ttu-id="e10fd-180">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="e10fd-180">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="e10fd-181">ASMCU</span><span class="sxs-lookup"><span data-stu-id="e10fd-181">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e10fd-182">16398</span><span class="sxs-lookup"><span data-stu-id="e10fd-182">16398</span></span></p></td>
<td><p><span data-ttu-id="e10fd-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="e10fd-183">WPLync</span></span></p></td>
<td><p><span data-ttu-id="e10fd-184">WPLync</span><span class="sxs-lookup"><span data-stu-id="e10fd-184">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e10fd-185">16399</span><span class="sxs-lookup"><span data-stu-id="e10fd-185">16399</span></span></p></td>
<td><p><span data-ttu-id="e10fd-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="e10fd-186">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="e10fd-187">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="e10fd-187">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e10fd-188">16400</span><span class="sxs-lookup"><span data-stu-id="e10fd-188">16400</span></span></p></td>
<td><p><span data-ttu-id="e10fd-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="e10fd-189">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="e10fd-190">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="e10fd-190">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e10fd-191">16401</span><span class="sxs-lookup"><span data-stu-id="e10fd-191">16401</span></span></p></td>
<td><p><span data-ttu-id="e10fd-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="e10fd-192">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="e10fd-193">iPadLync</span><span class="sxs-lookup"><span data-stu-id="e10fd-193">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e10fd-194">16402</span><span class="sxs-lookup"><span data-stu-id="e10fd-194">16402</span></span></p></td>
<td><p><span data-ttu-id="e10fd-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="e10fd-195">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="e10fd-196">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="e10fd-196">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e10fd-197">16403</span><span class="sxs-lookup"><span data-stu-id="e10fd-197">16403</span></span></p></td>
<td><p><span data-ttu-id="e10fd-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="e10fd-198">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="e10fd-199">LyncImm</span><span class="sxs-lookup"><span data-stu-id="e10fd-199">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e10fd-200">16404</span><span class="sxs-lookup"><span data-stu-id="e10fd-200">16404</span></span></p></td>
<td><p><span data-ttu-id="e10fd-201">电脑</span><span class="sxs-lookup"><span data-stu-id="e10fd-201">PCS</span></span></p></td>
<td><p><span data-ttu-id="e10fd-202">电脑</span><span class="sxs-lookup"><span data-stu-id="e10fd-202">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e10fd-203">16405</span><span class="sxs-lookup"><span data-stu-id="e10fd-203">16405</span></span></p></td>
<td><p><span data-ttu-id="e10fd-204">LWA</span><span class="sxs-lookup"><span data-stu-id="e10fd-204">LWA</span></span></p></td>
<td><p><span data-ttu-id="e10fd-205">LWA</span><span class="sxs-lookup"><span data-stu-id="e10fd-205">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e10fd-206">16406</span><span class="sxs-lookup"><span data-stu-id="e10fd-206">16406</span></span></p></td>
<td><p><span data-ttu-id="e10fd-207">OWA</span><span class="sxs-lookup"><span data-stu-id="e10fd-207">OWA</span></span></p></td>
<td><p><span data-ttu-id="e10fd-208">OWA</span><span class="sxs-lookup"><span data-stu-id="e10fd-208">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e10fd-209">16407</span><span class="sxs-lookup"><span data-stu-id="e10fd-209">16407</span></span></p></td>
<td><p><span data-ttu-id="e10fd-210">AOC</span><span class="sxs-lookup"><span data-stu-id="e10fd-210">AOC</span></span></p></td>
<td><p><span data-ttu-id="e10fd-211">AOC</span><span class="sxs-lookup"><span data-stu-id="e10fd-211">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e10fd-212">16408</span><span class="sxs-lookup"><span data-stu-id="e10fd-212">16408</span></span></p></td>
<td><p><span data-ttu-id="e10fd-213">GCC</span><span class="sxs-lookup"><span data-stu-id="e10fd-213">GCC</span></span></p></td>
<td><p><span data-ttu-id="e10fd-214">GCC</span><span class="sxs-lookup"><span data-stu-id="e10fd-214">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e10fd-215">16409</span><span class="sxs-lookup"><span data-stu-id="e10fd-215">16409</span></span></p></td>
<td><p><span data-ttu-id="e10fd-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="e10fd-216">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="e10fd-217">IMMCU</span><span class="sxs-lookup"><span data-stu-id="e10fd-217">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e10fd-218">16410</span><span class="sxs-lookup"><span data-stu-id="e10fd-218">16410</span></span></p></td>
<td><p><span data-ttu-id="e10fd-219">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="e10fd-219">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="e10fd-220">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="e10fd-220">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e10fd-221">32769</span><span class="sxs-lookup"><span data-stu-id="e10fd-221">32769</span></span></p></td>
<td><p><span data-ttu-id="e10fd-222">网关</span><span class="sxs-lookup"><span data-stu-id="e10fd-222">Gateway</span></span></p></td>
<td><p><span data-ttu-id="e10fd-223">网关</span><span class="sxs-lookup"><span data-stu-id="e10fd-223">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e10fd-224">32770</span><span class="sxs-lookup"><span data-stu-id="e10fd-224">32770</span></span></p></td>
<td><p><span data-ttu-id="e10fd-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="e10fd-225">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="e10fd-226">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="e10fd-226">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

