---
title: 'Lync Server 2013： UserAgentDef table (QoE) '
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
ms.openlocfilehash: 7294c70a0ebfd49f954bbe911d2fccb81d79fa54
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530099"
---
# <a name="useragentdef-table-qoe-in-lync-server-2013"></a><span data-ttu-id="17c0d-102">Lync Server 2013 中的 UserAgentDef 表 (QoE) </span><span class="sxs-lookup"><span data-stu-id="17c0d-102">UserAgentDef table (QoE) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17c0d-103">_**上次修改的主题：** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="17c0d-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="17c0d-104">UserAgentDef 表将用户代理标识符映射到代理的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="17c0d-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="17c0d-105">用户代理是用于连接到 Microsoft Lync Server 2013 的软件客户端。</span><span class="sxs-lookup"><span data-stu-id="17c0d-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17c0d-106">UAType</span><span class="sxs-lookup"><span data-stu-id="17c0d-106">UAType</span></span></th>
<th><span data-ttu-id="17c0d-107">UAName</span><span class="sxs-lookup"><span data-stu-id="17c0d-107">UAName</span></span></th>
<th><span data-ttu-id="17c0d-108">UACategory</span><span class="sxs-lookup"><span data-stu-id="17c0d-108">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17c0d-109">1</span><span class="sxs-lookup"><span data-stu-id="17c0d-109">1</span></span></p></td>
<td><p><span data-ttu-id="17c0d-110">MediationServer</span><span class="sxs-lookup"><span data-stu-id="17c0d-110">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="17c0d-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="17c0d-111">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17c0d-112">双面</span><span class="sxs-lookup"><span data-stu-id="17c0d-112">2</span></span></p></td>
<td><p><span data-ttu-id="17c0d-113">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="17c0d-113">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="17c0d-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="17c0d-114">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17c0d-115">4 </span><span class="sxs-lookup"><span data-stu-id="17c0d-115">4</span></span></p></td>
<td><p><span data-ttu-id="17c0d-116">OC</span><span class="sxs-lookup"><span data-stu-id="17c0d-116">OC</span></span></p></td>
<td><p><span data-ttu-id="17c0d-117">OC</span><span class="sxs-lookup"><span data-stu-id="17c0d-117">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17c0d-118">8 </span><span class="sxs-lookup"><span data-stu-id="17c0d-118">8</span></span></p></td>
<td><p><span data-ttu-id="17c0d-119">OCPhone</span><span class="sxs-lookup"><span data-stu-id="17c0d-119">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="17c0d-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="17c0d-120">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17c0d-121">16 </span><span class="sxs-lookup"><span data-stu-id="17c0d-121">16</span></span></p></td>
<td><p><span data-ttu-id="17c0d-122">LMC</span><span class="sxs-lookup"><span data-stu-id="17c0d-122">LMC</span></span></p></td>
<td><p><span data-ttu-id="17c0d-123">LMC</span><span class="sxs-lookup"><span data-stu-id="17c0d-123">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17c0d-124">32</span><span class="sxs-lookup"><span data-stu-id="17c0d-124">32</span></span></p></td>
<td><p><span data-ttu-id="17c0d-125">DVT</span><span class="sxs-lookup"><span data-stu-id="17c0d-125">DVT</span></span></p></td>
<td><p><span data-ttu-id="17c0d-126">DVT</span><span class="sxs-lookup"><span data-stu-id="17c0d-126">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17c0d-127">64</span><span class="sxs-lookup"><span data-stu-id="17c0d-127">64</span></span></p></td>
<td><p><span data-ttu-id="17c0d-128">MM</span><span class="sxs-lookup"><span data-stu-id="17c0d-128">MM</span></span></p></td>
<td><p><span data-ttu-id="17c0d-129">MM</span><span class="sxs-lookup"><span data-stu-id="17c0d-129">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17c0d-130">64</span><span class="sxs-lookup"><span data-stu-id="17c0d-130">64</span></span></p></td>
<td><p><span data-ttu-id="17c0d-131">EMC</span><span class="sxs-lookup"><span data-stu-id="17c0d-131">MC</span></span></p></td>
<td><p><span data-ttu-id="17c0d-132">MM</span><span class="sxs-lookup"><span data-stu-id="17c0d-132">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17c0d-133">128</span><span class="sxs-lookup"><span data-stu-id="17c0d-133">128</span></span></p></td>
<td><p><span data-ttu-id="17c0d-134">助理版</span><span class="sxs-lookup"><span data-stu-id="17c0d-134">Attendant</span></span></p></td>
<td><p><span data-ttu-id="17c0d-135">助理版</span><span class="sxs-lookup"><span data-stu-id="17c0d-135">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17c0d-136">256</span><span class="sxs-lookup"><span data-stu-id="17c0d-136">256</span></span></p></td>
<td><p><span data-ttu-id="17c0d-137">Conferencing_Announcement_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="17c0d-137">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="17c0d-138">CAS</span><span class="sxs-lookup"><span data-stu-id="17c0d-138">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17c0d-139">512</span><span class="sxs-lookup"><span data-stu-id="17c0d-139">512</span></span></p></td>
<td><p><span data-ttu-id="17c0d-140">Conferencing_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="17c0d-140">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="17c0d-141">CAA</span><span class="sxs-lookup"><span data-stu-id="17c0d-141">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17c0d-142">512</span><span class="sxs-lookup"><span data-stu-id="17c0d-142">512</span></span></p></td>
<td><p><span data-ttu-id="17c0d-143">Conference_Auto_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="17c0d-143">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="17c0d-144">CAA</span><span class="sxs-lookup"><span data-stu-id="17c0d-144">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17c0d-145">1024</span><span class="sxs-lookup"><span data-stu-id="17c0d-145">1024</span></span></p></td>
<td><p><span data-ttu-id="17c0d-146">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="17c0d-146">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="17c0d-147">RGS</span><span class="sxs-lookup"><span data-stu-id="17c0d-147">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17c0d-148">1032</span><span class="sxs-lookup"><span data-stu-id="17c0d-148">1032</span></span></p></td>
<td><p><span data-ttu-id="17c0d-149">Call_Park_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="17c0d-149">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="17c0d-150">CPS</span><span class="sxs-lookup"><span data-stu-id="17c0d-150">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17c0d-151">1040</span><span class="sxs-lookup"><span data-stu-id="17c0d-151">1040</span></span></p></td>
<td><p><span data-ttu-id="17c0d-152">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="17c0d-152">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="17c0d-153">AS</span><span class="sxs-lookup"><span data-stu-id="17c0d-153">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17c0d-154">2048</span><span class="sxs-lookup"><span data-stu-id="17c0d-154">2048</span></span></p></td>
<td><p><span data-ttu-id="17c0d-155">Microsoft Ccs</span><span class="sxs-lookup"><span data-stu-id="17c0d-155">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="17c0d-156">CCS</span><span class="sxs-lookup"><span data-stu-id="17c0d-156">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17c0d-157">16386</span><span class="sxs-lookup"><span data-stu-id="17c0d-157">16386</span></span></p></td>
<td><p><span data-ttu-id="17c0d-158">CoMo</span><span class="sxs-lookup"><span data-stu-id="17c0d-158">CoMo</span></span></p></td>
<td><p><span data-ttu-id="17c0d-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="17c0d-159">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17c0d-160">16387</span><span class="sxs-lookup"><span data-stu-id="17c0d-160">16387</span></span></p></td>
<td><p><span data-ttu-id="17c0d-161">CWA</span><span class="sxs-lookup"><span data-stu-id="17c0d-161">CWA</span></span></p></td>
<td><p><span data-ttu-id="17c0d-162">CWA</span><span class="sxs-lookup"><span data-stu-id="17c0d-162">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17c0d-163">16388</span><span class="sxs-lookup"><span data-stu-id="17c0d-163">16388</span></span></p></td>
<td><p><span data-ttu-id="17c0d-164">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="17c0d-164">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="17c0d-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="17c0d-165">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17c0d-166">16389</span><span class="sxs-lookup"><span data-stu-id="17c0d-166">16389</span></span></p></td>
<td><p><span data-ttu-id="17c0d-167">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="17c0d-167">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="17c0d-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="17c0d-168">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17c0d-169">16393</span><span class="sxs-lookup"><span data-stu-id="17c0d-169">16393</span></span></p></td>
<td><p><span data-ttu-id="17c0d-170">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="17c0d-170">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="17c0d-171">ExUM</span><span class="sxs-lookup"><span data-stu-id="17c0d-171">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17c0d-172">16395</span><span class="sxs-lookup"><span data-stu-id="17c0d-172">16395</span></span></p></td>
<td><p><span data-ttu-id="17c0d-173">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="17c0d-173">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="17c0d-174">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="17c0d-174">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17c0d-175">16396</span><span class="sxs-lookup"><span data-stu-id="17c0d-175">16396</span></span></p></td>
<td><p><span data-ttu-id="17c0d-176">圣保罗</span><span class="sxs-lookup"><span data-stu-id="17c0d-176">ST</span></span></p></td>
<td><p><span data-ttu-id="17c0d-177">圣保罗</span><span class="sxs-lookup"><span data-stu-id="17c0d-177">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17c0d-178">16397</span><span class="sxs-lookup"><span data-stu-id="17c0d-178">16397</span></span></p></td>
<td><p><span data-ttu-id="17c0d-179">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="17c0d-179">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="17c0d-180">ASMCU</span><span class="sxs-lookup"><span data-stu-id="17c0d-180">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17c0d-181">16398</span><span class="sxs-lookup"><span data-stu-id="17c0d-181">16398</span></span></p></td>
<td><p><span data-ttu-id="17c0d-182">WPLync</span><span class="sxs-lookup"><span data-stu-id="17c0d-182">WPLync</span></span></p></td>
<td><p><span data-ttu-id="17c0d-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="17c0d-183">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17c0d-184">16399</span><span class="sxs-lookup"><span data-stu-id="17c0d-184">16399</span></span></p></td>
<td><p><span data-ttu-id="17c0d-185">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="17c0d-185">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="17c0d-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="17c0d-186">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17c0d-187">16400</span><span class="sxs-lookup"><span data-stu-id="17c0d-187">16400</span></span></p></td>
<td><p><span data-ttu-id="17c0d-188">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="17c0d-188">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="17c0d-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="17c0d-189">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17c0d-190">16401</span><span class="sxs-lookup"><span data-stu-id="17c0d-190">16401</span></span></p></td>
<td><p><span data-ttu-id="17c0d-191">iPadLync</span><span class="sxs-lookup"><span data-stu-id="17c0d-191">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="17c0d-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="17c0d-192">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17c0d-193">16402</span><span class="sxs-lookup"><span data-stu-id="17c0d-193">16402</span></span></p></td>
<td><p><span data-ttu-id="17c0d-194">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="17c0d-194">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="17c0d-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="17c0d-195">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17c0d-196">16403</span><span class="sxs-lookup"><span data-stu-id="17c0d-196">16403</span></span></p></td>
<td><p><span data-ttu-id="17c0d-197">LyncImm</span><span class="sxs-lookup"><span data-stu-id="17c0d-197">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="17c0d-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="17c0d-198">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17c0d-199">16404</span><span class="sxs-lookup"><span data-stu-id="17c0d-199">16404</span></span></p></td>
<td><p><span data-ttu-id="17c0d-200">电脑</span><span class="sxs-lookup"><span data-stu-id="17c0d-200">PCS</span></span></p></td>
<td><p><span data-ttu-id="17c0d-201">电脑</span><span class="sxs-lookup"><span data-stu-id="17c0d-201">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17c0d-202">16405</span><span class="sxs-lookup"><span data-stu-id="17c0d-202">16405</span></span></p></td>
<td><p><span data-ttu-id="17c0d-203">LWA</span><span class="sxs-lookup"><span data-stu-id="17c0d-203">LWA</span></span></p></td>
<td><p><span data-ttu-id="17c0d-204">LWA</span><span class="sxs-lookup"><span data-stu-id="17c0d-204">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17c0d-205">16406</span><span class="sxs-lookup"><span data-stu-id="17c0d-205">16406</span></span></p></td>
<td><p><span data-ttu-id="17c0d-206">OWA</span><span class="sxs-lookup"><span data-stu-id="17c0d-206">OWA</span></span></p></td>
<td><p><span data-ttu-id="17c0d-207">OWA</span><span class="sxs-lookup"><span data-stu-id="17c0d-207">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17c0d-208">16407</span><span class="sxs-lookup"><span data-stu-id="17c0d-208">16407</span></span></p></td>
<td><p><span data-ttu-id="17c0d-209">AOC</span><span class="sxs-lookup"><span data-stu-id="17c0d-209">AOC</span></span></p></td>
<td><p><span data-ttu-id="17c0d-210">AOC</span><span class="sxs-lookup"><span data-stu-id="17c0d-210">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17c0d-211">16408</span><span class="sxs-lookup"><span data-stu-id="17c0d-211">16408</span></span></p></td>
<td><p><span data-ttu-id="17c0d-212">GCC</span><span class="sxs-lookup"><span data-stu-id="17c0d-212">GCC</span></span></p></td>
<td><p><span data-ttu-id="17c0d-213">GCC</span><span class="sxs-lookup"><span data-stu-id="17c0d-213">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17c0d-214">16409</span><span class="sxs-lookup"><span data-stu-id="17c0d-214">16409</span></span></p></td>
<td><p><span data-ttu-id="17c0d-215">IMMCU</span><span class="sxs-lookup"><span data-stu-id="17c0d-215">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="17c0d-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="17c0d-216">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17c0d-217">16410</span><span class="sxs-lookup"><span data-stu-id="17c0d-217">16410</span></span></p></td>
<td><p><span data-ttu-id="17c0d-218">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="17c0d-218">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="17c0d-219">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="17c0d-219">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17c0d-220">32769</span><span class="sxs-lookup"><span data-stu-id="17c0d-220">32769</span></span></p></td>
<td><p><span data-ttu-id="17c0d-221">网关</span><span class="sxs-lookup"><span data-stu-id="17c0d-221">Gateway</span></span></p></td>
<td><p><span data-ttu-id="17c0d-222">网关</span><span class="sxs-lookup"><span data-stu-id="17c0d-222">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17c0d-223">32770</span><span class="sxs-lookup"><span data-stu-id="17c0d-223">32770</span></span></p></td>
<td><p><span data-ttu-id="17c0d-224">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="17c0d-224">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="17c0d-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="17c0d-225">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

