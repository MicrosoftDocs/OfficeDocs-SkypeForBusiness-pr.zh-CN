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
ms.openlocfilehash: 952f065c5377a4d4e94677f9088569ffca681151
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744372"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-in-lync-server-2013"></a><span data-ttu-id="cc392-102">Lync Server 2013 中的 UserAgentDef 表</span><span class="sxs-lookup"><span data-stu-id="cc392-102">UserAgentDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc392-103">_**主题上次修改时间：** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="cc392-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="cc392-104">UserAgentDef 表将用户代理标识符映射到代理的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="cc392-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="cc392-105">用户代理是用于连接到 Microsoft Lync Server 2013 的软件客户端。</span><span class="sxs-lookup"><span data-stu-id="cc392-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="cc392-106">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="cc392-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc392-107">UAType</span><span class="sxs-lookup"><span data-stu-id="cc392-107">UAType</span></span></th>
<th><span data-ttu-id="cc392-108">UAName</span><span class="sxs-lookup"><span data-stu-id="cc392-108">UAName</span></span></th>
<th><span data-ttu-id="cc392-109">UACategory</span><span class="sxs-lookup"><span data-stu-id="cc392-109">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc392-110">1</span><span class="sxs-lookup"><span data-stu-id="cc392-110">1</span></span></p></td>
<td><p><span data-ttu-id="cc392-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="cc392-111">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="cc392-112">MediationServer</span><span class="sxs-lookup"><span data-stu-id="cc392-112">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc392-113">ppls-2</span><span class="sxs-lookup"><span data-stu-id="cc392-113">2</span></span></p></td>
<td><p><span data-ttu-id="cc392-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="cc392-114">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="cc392-115">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="cc392-115">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc392-116">4</span><span class="sxs-lookup"><span data-stu-id="cc392-116">4</span></span></p></td>
<td><p><span data-ttu-id="cc392-117">OC</span><span class="sxs-lookup"><span data-stu-id="cc392-117">OC</span></span></p></td>
<td><p><span data-ttu-id="cc392-118">OC</span><span class="sxs-lookup"><span data-stu-id="cc392-118">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc392-119">个</span><span class="sxs-lookup"><span data-stu-id="cc392-119">8</span></span></p></td>
<td><p><span data-ttu-id="cc392-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="cc392-120">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="cc392-121">OCPhone</span><span class="sxs-lookup"><span data-stu-id="cc392-121">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc392-122">utf-16</span><span class="sxs-lookup"><span data-stu-id="cc392-122">16</span></span></p></td>
<td><p><span data-ttu-id="cc392-123">LMC</span><span class="sxs-lookup"><span data-stu-id="cc392-123">LMC</span></span></p></td>
<td><p><span data-ttu-id="cc392-124">LMC</span><span class="sxs-lookup"><span data-stu-id="cc392-124">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc392-125">32</span><span class="sxs-lookup"><span data-stu-id="cc392-125">32</span></span></p></td>
<td><p><span data-ttu-id="cc392-126">DVT</span><span class="sxs-lookup"><span data-stu-id="cc392-126">DVT</span></span></p></td>
<td><p><span data-ttu-id="cc392-127">DVT</span><span class="sxs-lookup"><span data-stu-id="cc392-127">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc392-128">64</span><span class="sxs-lookup"><span data-stu-id="cc392-128">64</span></span></p></td>
<td><p><span data-ttu-id="cc392-129">分钟</span><span class="sxs-lookup"><span data-stu-id="cc392-129">MM</span></span></p></td>
<td><p><span data-ttu-id="cc392-130">分钟</span><span class="sxs-lookup"><span data-stu-id="cc392-130">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc392-131">64</span><span class="sxs-lookup"><span data-stu-id="cc392-131">64</span></span></p></td>
<td><p><span data-ttu-id="cc392-132">MC</span><span class="sxs-lookup"><span data-stu-id="cc392-132">MC</span></span></p></td>
<td><p><span data-ttu-id="cc392-133">分钟</span><span class="sxs-lookup"><span data-stu-id="cc392-133">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc392-134">128</span><span class="sxs-lookup"><span data-stu-id="cc392-134">128</span></span></p></td>
<td><p><span data-ttu-id="cc392-135">助理</span><span class="sxs-lookup"><span data-stu-id="cc392-135">Attendant</span></span></p></td>
<td><p><span data-ttu-id="cc392-136">助理</span><span class="sxs-lookup"><span data-stu-id="cc392-136">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc392-137">256</span><span class="sxs-lookup"><span data-stu-id="cc392-137">256</span></span></p></td>
<td><p><span data-ttu-id="cc392-138">Conferencing_Announcement_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="cc392-138">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="cc392-139">而言</span><span class="sxs-lookup"><span data-stu-id="cc392-139">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc392-140">512</span><span class="sxs-lookup"><span data-stu-id="cc392-140">512</span></span></p></td>
<td><p><span data-ttu-id="cc392-141">Conferencing_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="cc392-141">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="cc392-142">CAA</span><span class="sxs-lookup"><span data-stu-id="cc392-142">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc392-143">512</span><span class="sxs-lookup"><span data-stu-id="cc392-143">512</span></span></p></td>
<td><p><span data-ttu-id="cc392-144">Conference_Auto_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="cc392-144">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="cc392-145">CAA</span><span class="sxs-lookup"><span data-stu-id="cc392-145">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc392-146">1024</span><span class="sxs-lookup"><span data-stu-id="cc392-146">1024</span></span></p></td>
<td><p><span data-ttu-id="cc392-147">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="cc392-147">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="cc392-148">RG</span><span class="sxs-lookup"><span data-stu-id="cc392-148">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc392-149">1032</span><span class="sxs-lookup"><span data-stu-id="cc392-149">1032</span></span></p></td>
<td><p><span data-ttu-id="cc392-150">Call_Park_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="cc392-150">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="cc392-151">方面</span><span class="sxs-lookup"><span data-stu-id="cc392-151">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc392-152">1040</span><span class="sxs-lookup"><span data-stu-id="cc392-152">1040</span></span></p></td>
<td><p><span data-ttu-id="cc392-153">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="cc392-153">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="cc392-154">方式</span><span class="sxs-lookup"><span data-stu-id="cc392-154">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc392-155">2048</span><span class="sxs-lookup"><span data-stu-id="cc392-155">2048</span></span></p></td>
<td><p><span data-ttu-id="cc392-156">Microsoft Ccs</span><span class="sxs-lookup"><span data-stu-id="cc392-156">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="cc392-157">CCS</span><span class="sxs-lookup"><span data-stu-id="cc392-157">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc392-158">16386</span><span class="sxs-lookup"><span data-stu-id="cc392-158">16386</span></span></p></td>
<td><p><span data-ttu-id="cc392-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="cc392-159">CoMo</span></span></p></td>
<td><p><span data-ttu-id="cc392-160">CoMo</span><span class="sxs-lookup"><span data-stu-id="cc392-160">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc392-161">16387</span><span class="sxs-lookup"><span data-stu-id="cc392-161">16387</span></span></p></td>
<td><p><span data-ttu-id="cc392-162">CWA</span><span class="sxs-lookup"><span data-stu-id="cc392-162">CWA</span></span></p></td>
<td><p><span data-ttu-id="cc392-163">CWA</span><span class="sxs-lookup"><span data-stu-id="cc392-163">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc392-164">16388</span><span class="sxs-lookup"><span data-stu-id="cc392-164">16388</span></span></p></td>
<td><p><span data-ttu-id="cc392-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="cc392-165">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="cc392-166">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="cc392-166">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc392-167">16389</span><span class="sxs-lookup"><span data-stu-id="cc392-167">16389</span></span></p></td>
<td><p><span data-ttu-id="cc392-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="cc392-168">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="cc392-169">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="cc392-169">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc392-170">16393</span><span class="sxs-lookup"><span data-stu-id="cc392-170">16393</span></span></p></td>
<td><p><span data-ttu-id="cc392-171">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="cc392-171">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="cc392-172">ExUM</span><span class="sxs-lookup"><span data-stu-id="cc392-172">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc392-173">16395</span><span class="sxs-lookup"><span data-stu-id="cc392-173">16395</span></span></p></td>
<td><p><span data-ttu-id="cc392-174">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="cc392-174">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="cc392-175">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="cc392-175">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc392-176">16396</span><span class="sxs-lookup"><span data-stu-id="cc392-176">16396</span></span></p></td>
<td><p><span data-ttu-id="cc392-177">短期</span><span class="sxs-lookup"><span data-stu-id="cc392-177">ST</span></span></p></td>
<td><p><span data-ttu-id="cc392-178">短期</span><span class="sxs-lookup"><span data-stu-id="cc392-178">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc392-179">16397</span><span class="sxs-lookup"><span data-stu-id="cc392-179">16397</span></span></p></td>
<td><p><span data-ttu-id="cc392-180">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="cc392-180">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="cc392-181">ASMCU</span><span class="sxs-lookup"><span data-stu-id="cc392-181">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc392-182">16398</span><span class="sxs-lookup"><span data-stu-id="cc392-182">16398</span></span></p></td>
<td><p><span data-ttu-id="cc392-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="cc392-183">WPLync</span></span></p></td>
<td><p><span data-ttu-id="cc392-184">WPLync</span><span class="sxs-lookup"><span data-stu-id="cc392-184">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc392-185">16399</span><span class="sxs-lookup"><span data-stu-id="cc392-185">16399</span></span></p></td>
<td><p><span data-ttu-id="cc392-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="cc392-186">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="cc392-187">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="cc392-187">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc392-188">16400</span><span class="sxs-lookup"><span data-stu-id="cc392-188">16400</span></span></p></td>
<td><p><span data-ttu-id="cc392-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="cc392-189">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="cc392-190">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="cc392-190">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc392-191">16401</span><span class="sxs-lookup"><span data-stu-id="cc392-191">16401</span></span></p></td>
<td><p><span data-ttu-id="cc392-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="cc392-192">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="cc392-193">iPadLync</span><span class="sxs-lookup"><span data-stu-id="cc392-193">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc392-194">16402</span><span class="sxs-lookup"><span data-stu-id="cc392-194">16402</span></span></p></td>
<td><p><span data-ttu-id="cc392-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="cc392-195">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="cc392-196">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="cc392-196">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc392-197">16403</span><span class="sxs-lookup"><span data-stu-id="cc392-197">16403</span></span></p></td>
<td><p><span data-ttu-id="cc392-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="cc392-198">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="cc392-199">LyncImm</span><span class="sxs-lookup"><span data-stu-id="cc392-199">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc392-200">16404</span><span class="sxs-lookup"><span data-stu-id="cc392-200">16404</span></span></p></td>
<td><p><span data-ttu-id="cc392-201">笔记本电脑</span><span class="sxs-lookup"><span data-stu-id="cc392-201">PCS</span></span></p></td>
<td><p><span data-ttu-id="cc392-202">笔记本电脑</span><span class="sxs-lookup"><span data-stu-id="cc392-202">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc392-203">16405</span><span class="sxs-lookup"><span data-stu-id="cc392-203">16405</span></span></p></td>
<td><p><span data-ttu-id="cc392-204">LWA</span><span class="sxs-lookup"><span data-stu-id="cc392-204">LWA</span></span></p></td>
<td><p><span data-ttu-id="cc392-205">LWA</span><span class="sxs-lookup"><span data-stu-id="cc392-205">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc392-206">16406</span><span class="sxs-lookup"><span data-stu-id="cc392-206">16406</span></span></p></td>
<td><p><span data-ttu-id="cc392-207">OWA</span><span class="sxs-lookup"><span data-stu-id="cc392-207">OWA</span></span></p></td>
<td><p><span data-ttu-id="cc392-208">OWA</span><span class="sxs-lookup"><span data-stu-id="cc392-208">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc392-209">16407</span><span class="sxs-lookup"><span data-stu-id="cc392-209">16407</span></span></p></td>
<td><p><span data-ttu-id="cc392-210">AOC</span><span class="sxs-lookup"><span data-stu-id="cc392-210">AOC</span></span></p></td>
<td><p><span data-ttu-id="cc392-211">AOC</span><span class="sxs-lookup"><span data-stu-id="cc392-211">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc392-212">16408</span><span class="sxs-lookup"><span data-stu-id="cc392-212">16408</span></span></p></td>
<td><p><span data-ttu-id="cc392-213">GCC</span><span class="sxs-lookup"><span data-stu-id="cc392-213">GCC</span></span></p></td>
<td><p><span data-ttu-id="cc392-214">GCC</span><span class="sxs-lookup"><span data-stu-id="cc392-214">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc392-215">16409</span><span class="sxs-lookup"><span data-stu-id="cc392-215">16409</span></span></p></td>
<td><p><span data-ttu-id="cc392-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="cc392-216">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="cc392-217">IMMCU</span><span class="sxs-lookup"><span data-stu-id="cc392-217">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc392-218">16410</span><span class="sxs-lookup"><span data-stu-id="cc392-218">16410</span></span></p></td>
<td><p><span data-ttu-id="cc392-219">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="cc392-219">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="cc392-220">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="cc392-220">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc392-221">32769</span><span class="sxs-lookup"><span data-stu-id="cc392-221">32769</span></span></p></td>
<td><p><span data-ttu-id="cc392-222">网关</span><span class="sxs-lookup"><span data-stu-id="cc392-222">Gateway</span></span></p></td>
<td><p><span data-ttu-id="cc392-223">网关</span><span class="sxs-lookup"><span data-stu-id="cc392-223">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc392-224">32770</span><span class="sxs-lookup"><span data-stu-id="cc392-224">32770</span></span></p></td>
<td><p><span data-ttu-id="cc392-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="cc392-225">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="cc392-226">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="cc392-226">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

