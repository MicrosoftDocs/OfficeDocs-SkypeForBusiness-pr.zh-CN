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
ms.openlocfilehash: 621020816ae7882d25f65ab2a40578ddebcfe837
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-in-lync-server-2013"></a><span data-ttu-id="1cdb7-102">Lync Server 2013 中的 UserAgentDef 表</span><span class="sxs-lookup"><span data-stu-id="1cdb7-102">UserAgentDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1cdb7-103">_**上次修改的主题：** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="1cdb7-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="1cdb7-104">UserAgentDef 表将用户代理标识符映射到代理的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="1cdb7-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="1cdb7-105">用户代理是用于连接到 Microsoft Lync Server 2013 的软件客户端。</span><span class="sxs-lookup"><span data-stu-id="1cdb7-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="1cdb7-106">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="1cdb7-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1cdb7-107">UAType</span><span class="sxs-lookup"><span data-stu-id="1cdb7-107">UAType</span></span></th>
<th><span data-ttu-id="1cdb7-108">UAName</span><span class="sxs-lookup"><span data-stu-id="1cdb7-108">UAName</span></span></th>
<th><span data-ttu-id="1cdb7-109">UACategory</span><span class="sxs-lookup"><span data-stu-id="1cdb7-109">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1cdb7-110">1</span><span class="sxs-lookup"><span data-stu-id="1cdb7-110">1</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="1cdb7-111">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-112">MediationServer</span><span class="sxs-lookup"><span data-stu-id="1cdb7-112">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cdb7-113">双面</span><span class="sxs-lookup"><span data-stu-id="1cdb7-113">2</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="1cdb7-114">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-115">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="1cdb7-115">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cdb7-116">4</span><span class="sxs-lookup"><span data-stu-id="1cdb7-116">4</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-117">OC</span><span class="sxs-lookup"><span data-stu-id="1cdb7-117">OC</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-118">OC</span><span class="sxs-lookup"><span data-stu-id="1cdb7-118">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cdb7-119">8 </span><span class="sxs-lookup"><span data-stu-id="1cdb7-119">8</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="1cdb7-120">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-121">OCPhone</span><span class="sxs-lookup"><span data-stu-id="1cdb7-121">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cdb7-122">16 </span><span class="sxs-lookup"><span data-stu-id="1cdb7-122">16</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-123">LMC</span><span class="sxs-lookup"><span data-stu-id="1cdb7-123">LMC</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-124">LMC</span><span class="sxs-lookup"><span data-stu-id="1cdb7-124">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cdb7-125">32</span><span class="sxs-lookup"><span data-stu-id="1cdb7-125">32</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-126">DVT</span><span class="sxs-lookup"><span data-stu-id="1cdb7-126">DVT</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-127">DVT</span><span class="sxs-lookup"><span data-stu-id="1cdb7-127">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cdb7-128">64</span><span class="sxs-lookup"><span data-stu-id="1cdb7-128">64</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-129">MM</span><span class="sxs-lookup"><span data-stu-id="1cdb7-129">MM</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-130">MM</span><span class="sxs-lookup"><span data-stu-id="1cdb7-130">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cdb7-131">64</span><span class="sxs-lookup"><span data-stu-id="1cdb7-131">64</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-132">EMC</span><span class="sxs-lookup"><span data-stu-id="1cdb7-132">MC</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-133">MM</span><span class="sxs-lookup"><span data-stu-id="1cdb7-133">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cdb7-134">128</span><span class="sxs-lookup"><span data-stu-id="1cdb7-134">128</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-135">随</span><span class="sxs-lookup"><span data-stu-id="1cdb7-135">Attendant</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-136">随</span><span class="sxs-lookup"><span data-stu-id="1cdb7-136">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cdb7-137">256</span><span class="sxs-lookup"><span data-stu-id="1cdb7-137">256</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-138">Conferencing_Announcement_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="1cdb7-138">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-139">CAS</span><span class="sxs-lookup"><span data-stu-id="1cdb7-139">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cdb7-140">512</span><span class="sxs-lookup"><span data-stu-id="1cdb7-140">512</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-141">Conferencing_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="1cdb7-141">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-142">CAA</span><span class="sxs-lookup"><span data-stu-id="1cdb7-142">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cdb7-143">512</span><span class="sxs-lookup"><span data-stu-id="1cdb7-143">512</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-144">Conference_Auto_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="1cdb7-144">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-145">CAA</span><span class="sxs-lookup"><span data-stu-id="1cdb7-145">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cdb7-146">1024</span><span class="sxs-lookup"><span data-stu-id="1cdb7-146">1024</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-147">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="1cdb7-147">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-148">RGS</span><span class="sxs-lookup"><span data-stu-id="1cdb7-148">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cdb7-149">1032</span><span class="sxs-lookup"><span data-stu-id="1cdb7-149">1032</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-150">Call_Park_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="1cdb7-150">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-151">CPS</span><span class="sxs-lookup"><span data-stu-id="1cdb7-151">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cdb7-152">1040</span><span class="sxs-lookup"><span data-stu-id="1cdb7-152">1040</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-153">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="1cdb7-153">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-154">AS</span><span class="sxs-lookup"><span data-stu-id="1cdb7-154">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cdb7-155">2048</span><span class="sxs-lookup"><span data-stu-id="1cdb7-155">2048</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-156">Microsoft Ccs</span><span class="sxs-lookup"><span data-stu-id="1cdb7-156">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-157">CCS</span><span class="sxs-lookup"><span data-stu-id="1cdb7-157">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cdb7-158">16386</span><span class="sxs-lookup"><span data-stu-id="1cdb7-158">16386</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="1cdb7-159">CoMo</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-160">CoMo</span><span class="sxs-lookup"><span data-stu-id="1cdb7-160">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cdb7-161">16387</span><span class="sxs-lookup"><span data-stu-id="1cdb7-161">16387</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-162">CWA</span><span class="sxs-lookup"><span data-stu-id="1cdb7-162">CWA</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-163">CWA</span><span class="sxs-lookup"><span data-stu-id="1cdb7-163">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cdb7-164">16388</span><span class="sxs-lookup"><span data-stu-id="1cdb7-164">16388</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="1cdb7-165">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-166">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="1cdb7-166">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cdb7-167">16389</span><span class="sxs-lookup"><span data-stu-id="1cdb7-167">16389</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="1cdb7-168">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-169">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="1cdb7-169">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cdb7-170">16393</span><span class="sxs-lookup"><span data-stu-id="1cdb7-170">16393</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-171">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="1cdb7-171">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-172">ExUM</span><span class="sxs-lookup"><span data-stu-id="1cdb7-172">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cdb7-173">16395</span><span class="sxs-lookup"><span data-stu-id="1cdb7-173">16395</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-174">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="1cdb7-174">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-175">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="1cdb7-175">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cdb7-176">16396</span><span class="sxs-lookup"><span data-stu-id="1cdb7-176">16396</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-177">圣保罗</span><span class="sxs-lookup"><span data-stu-id="1cdb7-177">ST</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-178">圣保罗</span><span class="sxs-lookup"><span data-stu-id="1cdb7-178">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cdb7-179">16397</span><span class="sxs-lookup"><span data-stu-id="1cdb7-179">16397</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-180">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="1cdb7-180">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-181">ASMCU</span><span class="sxs-lookup"><span data-stu-id="1cdb7-181">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cdb7-182">16398</span><span class="sxs-lookup"><span data-stu-id="1cdb7-182">16398</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="1cdb7-183">WPLync</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-184">WPLync</span><span class="sxs-lookup"><span data-stu-id="1cdb7-184">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cdb7-185">16399</span><span class="sxs-lookup"><span data-stu-id="1cdb7-185">16399</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="1cdb7-186">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-187">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="1cdb7-187">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cdb7-188">16400</span><span class="sxs-lookup"><span data-stu-id="1cdb7-188">16400</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="1cdb7-189">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-190">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="1cdb7-190">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cdb7-191">16401</span><span class="sxs-lookup"><span data-stu-id="1cdb7-191">16401</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="1cdb7-192">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-193">iPadLync</span><span class="sxs-lookup"><span data-stu-id="1cdb7-193">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cdb7-194">16402</span><span class="sxs-lookup"><span data-stu-id="1cdb7-194">16402</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="1cdb7-195">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-196">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="1cdb7-196">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cdb7-197">16403</span><span class="sxs-lookup"><span data-stu-id="1cdb7-197">16403</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="1cdb7-198">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-199">LyncImm</span><span class="sxs-lookup"><span data-stu-id="1cdb7-199">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cdb7-200">16404</span><span class="sxs-lookup"><span data-stu-id="1cdb7-200">16404</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-201">电脑</span><span class="sxs-lookup"><span data-stu-id="1cdb7-201">PCS</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-202">电脑</span><span class="sxs-lookup"><span data-stu-id="1cdb7-202">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cdb7-203">16405</span><span class="sxs-lookup"><span data-stu-id="1cdb7-203">16405</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-204">LWA</span><span class="sxs-lookup"><span data-stu-id="1cdb7-204">LWA</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-205">LWA</span><span class="sxs-lookup"><span data-stu-id="1cdb7-205">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cdb7-206">16406</span><span class="sxs-lookup"><span data-stu-id="1cdb7-206">16406</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-207">OWA</span><span class="sxs-lookup"><span data-stu-id="1cdb7-207">OWA</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-208">OWA</span><span class="sxs-lookup"><span data-stu-id="1cdb7-208">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cdb7-209">16407</span><span class="sxs-lookup"><span data-stu-id="1cdb7-209">16407</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-210">AOC</span><span class="sxs-lookup"><span data-stu-id="1cdb7-210">AOC</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-211">AOC</span><span class="sxs-lookup"><span data-stu-id="1cdb7-211">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cdb7-212">16408</span><span class="sxs-lookup"><span data-stu-id="1cdb7-212">16408</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-213">GCC</span><span class="sxs-lookup"><span data-stu-id="1cdb7-213">GCC</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-214">GCC</span><span class="sxs-lookup"><span data-stu-id="1cdb7-214">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cdb7-215">16409</span><span class="sxs-lookup"><span data-stu-id="1cdb7-215">16409</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="1cdb7-216">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-217">IMMCU</span><span class="sxs-lookup"><span data-stu-id="1cdb7-217">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cdb7-218">16410</span><span class="sxs-lookup"><span data-stu-id="1cdb7-218">16410</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-219">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="1cdb7-219">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-220">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="1cdb7-220">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cdb7-221">32769</span><span class="sxs-lookup"><span data-stu-id="1cdb7-221">32769</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-222">网关</span><span class="sxs-lookup"><span data-stu-id="1cdb7-222">Gateway</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-223">网关</span><span class="sxs-lookup"><span data-stu-id="1cdb7-223">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cdb7-224">32770</span><span class="sxs-lookup"><span data-stu-id="1cdb7-224">32770</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="1cdb7-225">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="1cdb7-226">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="1cdb7-226">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

