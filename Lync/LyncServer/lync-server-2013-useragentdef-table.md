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
ms.openlocfilehash: b7f63c9e5194c2b75ea6f637acec7201c86178e4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140715"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-in-lync-server-2013"></a><span data-ttu-id="a406a-102">Lync Server 2013 中的 UserAgentDef 表</span><span class="sxs-lookup"><span data-stu-id="a406a-102">UserAgentDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a406a-103">_**上次修改的主题：** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="a406a-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="a406a-104">UserAgentDef 表将用户代理标识符映射到代理的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="a406a-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="a406a-105">用户代理是用于连接到 Microsoft Lync Server 2013 的软件客户端。</span><span class="sxs-lookup"><span data-stu-id="a406a-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="a406a-106">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="a406a-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a406a-107">UAType</span><span class="sxs-lookup"><span data-stu-id="a406a-107">UAType</span></span></th>
<th><span data-ttu-id="a406a-108">UAName</span><span class="sxs-lookup"><span data-stu-id="a406a-108">UAName</span></span></th>
<th><span data-ttu-id="a406a-109">UACategory</span><span class="sxs-lookup"><span data-stu-id="a406a-109">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a406a-110">1</span><span class="sxs-lookup"><span data-stu-id="a406a-110">1</span></span></p></td>
<td><p><span data-ttu-id="a406a-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="a406a-111">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="a406a-112">MediationServer</span><span class="sxs-lookup"><span data-stu-id="a406a-112">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a406a-113">双面</span><span class="sxs-lookup"><span data-stu-id="a406a-113">2</span></span></p></td>
<td><p><span data-ttu-id="a406a-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="a406a-114">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="a406a-115">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="a406a-115">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a406a-116">4</span><span class="sxs-lookup"><span data-stu-id="a406a-116">4</span></span></p></td>
<td><p><span data-ttu-id="a406a-117">OC</span><span class="sxs-lookup"><span data-stu-id="a406a-117">OC</span></span></p></td>
<td><p><span data-ttu-id="a406a-118">OC</span><span class="sxs-lookup"><span data-stu-id="a406a-118">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a406a-119">8 </span><span class="sxs-lookup"><span data-stu-id="a406a-119">8</span></span></p></td>
<td><p><span data-ttu-id="a406a-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="a406a-120">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="a406a-121">OCPhone</span><span class="sxs-lookup"><span data-stu-id="a406a-121">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a406a-122">16 </span><span class="sxs-lookup"><span data-stu-id="a406a-122">16</span></span></p></td>
<td><p><span data-ttu-id="a406a-123">LMC</span><span class="sxs-lookup"><span data-stu-id="a406a-123">LMC</span></span></p></td>
<td><p><span data-ttu-id="a406a-124">LMC</span><span class="sxs-lookup"><span data-stu-id="a406a-124">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a406a-125">32</span><span class="sxs-lookup"><span data-stu-id="a406a-125">32</span></span></p></td>
<td><p><span data-ttu-id="a406a-126">DVT</span><span class="sxs-lookup"><span data-stu-id="a406a-126">DVT</span></span></p></td>
<td><p><span data-ttu-id="a406a-127">DVT</span><span class="sxs-lookup"><span data-stu-id="a406a-127">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a406a-128">64</span><span class="sxs-lookup"><span data-stu-id="a406a-128">64</span></span></p></td>
<td><p><span data-ttu-id="a406a-129">MM</span><span class="sxs-lookup"><span data-stu-id="a406a-129">MM</span></span></p></td>
<td><p><span data-ttu-id="a406a-130">MM</span><span class="sxs-lookup"><span data-stu-id="a406a-130">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a406a-131">64</span><span class="sxs-lookup"><span data-stu-id="a406a-131">64</span></span></p></td>
<td><p><span data-ttu-id="a406a-132">EMC</span><span class="sxs-lookup"><span data-stu-id="a406a-132">MC</span></span></p></td>
<td><p><span data-ttu-id="a406a-133">MM</span><span class="sxs-lookup"><span data-stu-id="a406a-133">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a406a-134">128</span><span class="sxs-lookup"><span data-stu-id="a406a-134">128</span></span></p></td>
<td><p><span data-ttu-id="a406a-135">随</span><span class="sxs-lookup"><span data-stu-id="a406a-135">Attendant</span></span></p></td>
<td><p><span data-ttu-id="a406a-136">随</span><span class="sxs-lookup"><span data-stu-id="a406a-136">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a406a-137">256</span><span class="sxs-lookup"><span data-stu-id="a406a-137">256</span></span></p></td>
<td><p><span data-ttu-id="a406a-138">Conferencing_Announcement_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="a406a-138">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="a406a-139">CAS</span><span class="sxs-lookup"><span data-stu-id="a406a-139">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a406a-140">512</span><span class="sxs-lookup"><span data-stu-id="a406a-140">512</span></span></p></td>
<td><p><span data-ttu-id="a406a-141">Conferencing_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="a406a-141">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="a406a-142">CAA</span><span class="sxs-lookup"><span data-stu-id="a406a-142">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a406a-143">512</span><span class="sxs-lookup"><span data-stu-id="a406a-143">512</span></span></p></td>
<td><p><span data-ttu-id="a406a-144">Conference_Auto_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="a406a-144">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="a406a-145">CAA</span><span class="sxs-lookup"><span data-stu-id="a406a-145">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a406a-146">1024</span><span class="sxs-lookup"><span data-stu-id="a406a-146">1024</span></span></p></td>
<td><p><span data-ttu-id="a406a-147">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="a406a-147">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="a406a-148">RGS</span><span class="sxs-lookup"><span data-stu-id="a406a-148">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a406a-149">1032</span><span class="sxs-lookup"><span data-stu-id="a406a-149">1032</span></span></p></td>
<td><p><span data-ttu-id="a406a-150">Call_Park_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="a406a-150">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="a406a-151">CPS</span><span class="sxs-lookup"><span data-stu-id="a406a-151">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a406a-152">1040</span><span class="sxs-lookup"><span data-stu-id="a406a-152">1040</span></span></p></td>
<td><p><span data-ttu-id="a406a-153">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="a406a-153">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="a406a-154">AS</span><span class="sxs-lookup"><span data-stu-id="a406a-154">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a406a-155">2048</span><span class="sxs-lookup"><span data-stu-id="a406a-155">2048</span></span></p></td>
<td><p><span data-ttu-id="a406a-156">Microsoft Ccs</span><span class="sxs-lookup"><span data-stu-id="a406a-156">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="a406a-157">CCS</span><span class="sxs-lookup"><span data-stu-id="a406a-157">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a406a-158">16386</span><span class="sxs-lookup"><span data-stu-id="a406a-158">16386</span></span></p></td>
<td><p><span data-ttu-id="a406a-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="a406a-159">CoMo</span></span></p></td>
<td><p><span data-ttu-id="a406a-160">CoMo</span><span class="sxs-lookup"><span data-stu-id="a406a-160">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a406a-161">16387</span><span class="sxs-lookup"><span data-stu-id="a406a-161">16387</span></span></p></td>
<td><p><span data-ttu-id="a406a-162">CWA</span><span class="sxs-lookup"><span data-stu-id="a406a-162">CWA</span></span></p></td>
<td><p><span data-ttu-id="a406a-163">CWA</span><span class="sxs-lookup"><span data-stu-id="a406a-163">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a406a-164">16388</span><span class="sxs-lookup"><span data-stu-id="a406a-164">16388</span></span></p></td>
<td><p><span data-ttu-id="a406a-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="a406a-165">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="a406a-166">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="a406a-166">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a406a-167">16389</span><span class="sxs-lookup"><span data-stu-id="a406a-167">16389</span></span></p></td>
<td><p><span data-ttu-id="a406a-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="a406a-168">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="a406a-169">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="a406a-169">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a406a-170">16393</span><span class="sxs-lookup"><span data-stu-id="a406a-170">16393</span></span></p></td>
<td><p><span data-ttu-id="a406a-171">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="a406a-171">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="a406a-172">ExUM</span><span class="sxs-lookup"><span data-stu-id="a406a-172">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a406a-173">16395</span><span class="sxs-lookup"><span data-stu-id="a406a-173">16395</span></span></p></td>
<td><p><span data-ttu-id="a406a-174">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="a406a-174">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="a406a-175">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="a406a-175">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a406a-176">16396</span><span class="sxs-lookup"><span data-stu-id="a406a-176">16396</span></span></p></td>
<td><p><span data-ttu-id="a406a-177">圣保罗</span><span class="sxs-lookup"><span data-stu-id="a406a-177">ST</span></span></p></td>
<td><p><span data-ttu-id="a406a-178">圣保罗</span><span class="sxs-lookup"><span data-stu-id="a406a-178">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a406a-179">16397</span><span class="sxs-lookup"><span data-stu-id="a406a-179">16397</span></span></p></td>
<td><p><span data-ttu-id="a406a-180">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="a406a-180">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="a406a-181">ASMCU</span><span class="sxs-lookup"><span data-stu-id="a406a-181">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a406a-182">16398</span><span class="sxs-lookup"><span data-stu-id="a406a-182">16398</span></span></p></td>
<td><p><span data-ttu-id="a406a-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="a406a-183">WPLync</span></span></p></td>
<td><p><span data-ttu-id="a406a-184">WPLync</span><span class="sxs-lookup"><span data-stu-id="a406a-184">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a406a-185">16399</span><span class="sxs-lookup"><span data-stu-id="a406a-185">16399</span></span></p></td>
<td><p><span data-ttu-id="a406a-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="a406a-186">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="a406a-187">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="a406a-187">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a406a-188">16400</span><span class="sxs-lookup"><span data-stu-id="a406a-188">16400</span></span></p></td>
<td><p><span data-ttu-id="a406a-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="a406a-189">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="a406a-190">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="a406a-190">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a406a-191">16401</span><span class="sxs-lookup"><span data-stu-id="a406a-191">16401</span></span></p></td>
<td><p><span data-ttu-id="a406a-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="a406a-192">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="a406a-193">iPadLync</span><span class="sxs-lookup"><span data-stu-id="a406a-193">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a406a-194">16402</span><span class="sxs-lookup"><span data-stu-id="a406a-194">16402</span></span></p></td>
<td><p><span data-ttu-id="a406a-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="a406a-195">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="a406a-196">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="a406a-196">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a406a-197">16403</span><span class="sxs-lookup"><span data-stu-id="a406a-197">16403</span></span></p></td>
<td><p><span data-ttu-id="a406a-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="a406a-198">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="a406a-199">LyncImm</span><span class="sxs-lookup"><span data-stu-id="a406a-199">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a406a-200">16404</span><span class="sxs-lookup"><span data-stu-id="a406a-200">16404</span></span></p></td>
<td><p><span data-ttu-id="a406a-201">电脑</span><span class="sxs-lookup"><span data-stu-id="a406a-201">PCS</span></span></p></td>
<td><p><span data-ttu-id="a406a-202">电脑</span><span class="sxs-lookup"><span data-stu-id="a406a-202">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a406a-203">16405</span><span class="sxs-lookup"><span data-stu-id="a406a-203">16405</span></span></p></td>
<td><p><span data-ttu-id="a406a-204">LWA</span><span class="sxs-lookup"><span data-stu-id="a406a-204">LWA</span></span></p></td>
<td><p><span data-ttu-id="a406a-205">LWA</span><span class="sxs-lookup"><span data-stu-id="a406a-205">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a406a-206">16406</span><span class="sxs-lookup"><span data-stu-id="a406a-206">16406</span></span></p></td>
<td><p><span data-ttu-id="a406a-207">OWA</span><span class="sxs-lookup"><span data-stu-id="a406a-207">OWA</span></span></p></td>
<td><p><span data-ttu-id="a406a-208">OWA</span><span class="sxs-lookup"><span data-stu-id="a406a-208">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a406a-209">16407</span><span class="sxs-lookup"><span data-stu-id="a406a-209">16407</span></span></p></td>
<td><p><span data-ttu-id="a406a-210">AOC</span><span class="sxs-lookup"><span data-stu-id="a406a-210">AOC</span></span></p></td>
<td><p><span data-ttu-id="a406a-211">AOC</span><span class="sxs-lookup"><span data-stu-id="a406a-211">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a406a-212">16408</span><span class="sxs-lookup"><span data-stu-id="a406a-212">16408</span></span></p></td>
<td><p><span data-ttu-id="a406a-213">GCC</span><span class="sxs-lookup"><span data-stu-id="a406a-213">GCC</span></span></p></td>
<td><p><span data-ttu-id="a406a-214">GCC</span><span class="sxs-lookup"><span data-stu-id="a406a-214">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a406a-215">16409</span><span class="sxs-lookup"><span data-stu-id="a406a-215">16409</span></span></p></td>
<td><p><span data-ttu-id="a406a-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="a406a-216">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="a406a-217">IMMCU</span><span class="sxs-lookup"><span data-stu-id="a406a-217">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a406a-218">16410</span><span class="sxs-lookup"><span data-stu-id="a406a-218">16410</span></span></p></td>
<td><p><span data-ttu-id="a406a-219">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="a406a-219">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="a406a-220">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="a406a-220">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a406a-221">32769</span><span class="sxs-lookup"><span data-stu-id="a406a-221">32769</span></span></p></td>
<td><p><span data-ttu-id="a406a-222">网关</span><span class="sxs-lookup"><span data-stu-id="a406a-222">Gateway</span></span></p></td>
<td><p><span data-ttu-id="a406a-223">网关</span><span class="sxs-lookup"><span data-stu-id="a406a-223">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a406a-224">32770</span><span class="sxs-lookup"><span data-stu-id="a406a-224">32770</span></span></p></td>
<td><p><span data-ttu-id="a406a-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="a406a-225">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="a406a-226">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="a406a-226">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

