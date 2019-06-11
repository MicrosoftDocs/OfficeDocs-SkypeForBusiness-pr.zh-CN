---
title: Lync Server 2013：XMPP 联盟伙伴的协商设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02d72870e4060be6aa4ec428159af7ab19cb68b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="ce9fc-102">Lync Server 2013 中 XMPP 联盟伙伴的协商设置</span><span class="sxs-lookup"><span data-stu-id="ce9fc-102">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce9fc-103">_**主题上次修改时间:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="ce9fc-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="ce9fc-104">XMPP 合作伙伴配置中的协商类型的设置有多种可能的组合。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-104">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="ce9fc-105">并非所有这些组合都有效。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-105">Not all of these combinations are valid.</span></span> <span data-ttu-id="ce9fc-106">本主题中所述的表将定义有效和无效的设置。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-106">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="ce9fc-107">常见配置显示在第一个表中, 第二个表介绍了所有可能的组合。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-107">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="ce9fc-108">请注意, 除非也提供了 "*传输层安全性*(TLS)",**否则**不能具有*简单的身份验证和安全层*(SASL)。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-108">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="ce9fc-109">使用不加密的 (可读) 格式发送 SASL, 除非受到另一种方式 (如 TLS) 保护, 否则切勿传输。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-109">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="ce9fc-110">常见的 XMPP 联盟协商方法</span><span class="sxs-lookup"><span data-stu-id="ce9fc-110">Common XMPP Federation Negotiation Methods</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce9fc-111">传输层安全性 (TLS)</span><span class="sxs-lookup"><span data-stu-id="ce9fc-111">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="ce9fc-112">简单身份验证和安全层 (SASL)</span><span class="sxs-lookup"><span data-stu-id="ce9fc-112">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="ce9fc-113">回拨身份验证</span><span class="sxs-lookup"><span data-stu-id="ce9fc-113">Dialback Authentication</span></span></th>
<th><span data-ttu-id="ce9fc-114">预期的身份验证方法</span><span class="sxs-lookup"><span data-stu-id="ce9fc-114">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="ce9fc-115">注释</span><span class="sxs-lookup"><span data-stu-id="ce9fc-115">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce9fc-116">必需</span><span class="sxs-lookup"><span data-stu-id="ce9fc-116">Required</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-117">必需</span><span class="sxs-lookup"><span data-stu-id="ce9fc-117">Required</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-118">False</span><span class="sxs-lookup"><span data-stu-id="ce9fc-118">False</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-119">TLS 上的 SASL</span><span class="sxs-lookup"><span data-stu-id="ce9fc-119">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-120">TLS 和 SASL 所需有助于确保 SASL 消息流的安全。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-120">TLS and SASL required helps to ensure that the SASL message stream is secure.</span></span> <span data-ttu-id="ce9fc-121">如果 XMPP 联盟合作伙伴未将 TLS 设置为必需或可选, 则回拨不可用, 也不能用于回退方法。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-121">Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce9fc-122">必需</span><span class="sxs-lookup"><span data-stu-id="ce9fc-122">Required</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-123">可选</span><span class="sxs-lookup"><span data-stu-id="ce9fc-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-124">True</span><span class="sxs-lookup"><span data-stu-id="ce9fc-124">True</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-125">TLS 上的 SASL, TLS 回拨, TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="ce9fc-125">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-126">如果 XMPP 联盟合作伙伴已将 SASL 设置为 "可选" 或 "所需的 SASL", 则需要使用 TLS。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-126">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used.</span></span> <span data-ttu-id="ce9fc-127">如果 SASL 不可用, 将使用通过 TLS 的回拨。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-127">If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce9fc-128">可选</span><span class="sxs-lookup"><span data-stu-id="ce9fc-128">Optional</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-129">可选</span><span class="sxs-lookup"><span data-stu-id="ce9fc-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-130">True</span><span class="sxs-lookup"><span data-stu-id="ce9fc-130">True</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-131">TLS 上的 SASL, TLS 回拨, TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="ce9fc-131">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-132">在提供的协商方法中非常灵活, 这些设置依赖于 XMPP 联盟伙伴的设置。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-132">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings.</span></span> <span data-ttu-id="ce9fc-133">如果合作伙伴具有 TLS 可选或必需, 但不支持 SASL, TLS 回拨将可用。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-133">If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available.</span></span> <span data-ttu-id="ce9fc-134">如果合作伙伴将 TLS 和 SASL 设置为 "可选" 或 "所需", 则使用通过 SASL 的最佳选择。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-134">If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce9fc-135">否</span><span class="sxs-lookup"><span data-stu-id="ce9fc-135">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-136">否</span><span class="sxs-lookup"><span data-stu-id="ce9fc-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-137">True</span><span class="sxs-lookup"><span data-stu-id="ce9fc-137">True</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-138">TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="ce9fc-138">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-139">在许多情况下, TCP 回拨是唯一可行的解决方案。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-139">In many cases, TCP Dialback is the only possible solution.</span></span> <span data-ttu-id="ce9fc-140">比其他选项更少, 它提供一定级别的信任。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-140">Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="ce9fc-141">XMPP 联盟协商方法矩阵-完成</span><span class="sxs-lookup"><span data-stu-id="ce9fc-141">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce9fc-142">传输层安全性 (TLS)</span><span class="sxs-lookup"><span data-stu-id="ce9fc-142">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="ce9fc-143">简单身份验证和安全层 (SASL)</span><span class="sxs-lookup"><span data-stu-id="ce9fc-143">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="ce9fc-144">回拨身份验证</span><span class="sxs-lookup"><span data-stu-id="ce9fc-144">Dialback Authentication</span></span></th>
<th><span data-ttu-id="ce9fc-145">预期的身份验证方法</span><span class="sxs-lookup"><span data-stu-id="ce9fc-145">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="ce9fc-146">无效配置的备注、警告或错误</span><span class="sxs-lookup"><span data-stu-id="ce9fc-146">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce9fc-147">必需</span><span class="sxs-lookup"><span data-stu-id="ce9fc-147">Required</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-148">必需</span><span class="sxs-lookup"><span data-stu-id="ce9fc-148">Required</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-149">True</span><span class="sxs-lookup"><span data-stu-id="ce9fc-149">True</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-150">TLS 上的 SASL</span><span class="sxs-lookup"><span data-stu-id="ce9fc-150">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="ce9fc-151">如果需要 SASL 和 TLS, 则回拨不会运行。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-151">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce9fc-152">必需</span><span class="sxs-lookup"><span data-stu-id="ce9fc-152">Required</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-153">必需</span><span class="sxs-lookup"><span data-stu-id="ce9fc-153">Required</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-154">False</span><span class="sxs-lookup"><span data-stu-id="ce9fc-154">False</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-155">TLS 上的 SASL</span><span class="sxs-lookup"><span data-stu-id="ce9fc-155">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce9fc-156">可选</span><span class="sxs-lookup"><span data-stu-id="ce9fc-156">Optional</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-157">必需</span><span class="sxs-lookup"><span data-stu-id="ce9fc-157">Required</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-158">True</span><span class="sxs-lookup"><span data-stu-id="ce9fc-158">True</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-159">TLS 上的 SASL, TLS 回拨, TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="ce9fc-159">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="ce9fc-160">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-160">SASL requires TLS.</span></span> <span data-ttu-id="ce9fc-161">允许 TLS 是可选的可能会导致会话协商失败。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-161">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce9fc-162">可选</span><span class="sxs-lookup"><span data-stu-id="ce9fc-162">Optional</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-163">必需</span><span class="sxs-lookup"><span data-stu-id="ce9fc-163">Required</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-164">False</span><span class="sxs-lookup"><span data-stu-id="ce9fc-164">False</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-165">TLS 上的 SASL</span><span class="sxs-lookup"><span data-stu-id="ce9fc-165">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="ce9fc-166">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-166">SASL requires TLS.</span></span> <span data-ttu-id="ce9fc-167">允许 TLS 是可选的可能会导致会话协商失败。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-167">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce9fc-168">否</span><span class="sxs-lookup"><span data-stu-id="ce9fc-168">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-169">必需</span><span class="sxs-lookup"><span data-stu-id="ce9fc-169">Required</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-170">True</span><span class="sxs-lookup"><span data-stu-id="ce9fc-170">True</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-171">TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="ce9fc-171">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="ce9fc-172">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-172">SASL requires TLS.</span></span> <span data-ttu-id="ce9fc-173">允许 TLS 是可选的可能会导致会话协商失败。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-173">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce9fc-174">否</span><span class="sxs-lookup"><span data-stu-id="ce9fc-174">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-175">必需</span><span class="sxs-lookup"><span data-stu-id="ce9fc-175">Required</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-176">False</span><span class="sxs-lookup"><span data-stu-id="ce9fc-176">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="ce9fc-177">配置无效</span><span class="sxs-lookup"><span data-stu-id="ce9fc-177">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="ce9fc-178">由于 SASL 需要 TLS, 并且 TLS 不可用, 因此不能成功使用 SASL/TLS。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-178">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed.</span></span> <span data-ttu-id="ce9fc-179">TCP 回拨已设置为 false, 无法使用。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-179">TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce9fc-180">必需</span><span class="sxs-lookup"><span data-stu-id="ce9fc-180">Required</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-181">可选</span><span class="sxs-lookup"><span data-stu-id="ce9fc-181">Optional</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-182">True</span><span class="sxs-lookup"><span data-stu-id="ce9fc-182">True</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-183">TLS 上的 SASL, TLS 回拨</span><span class="sxs-lookup"><span data-stu-id="ce9fc-183">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce9fc-184">必需</span><span class="sxs-lookup"><span data-stu-id="ce9fc-184">Required</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-185">可选</span><span class="sxs-lookup"><span data-stu-id="ce9fc-185">Optional</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-186">False</span><span class="sxs-lookup"><span data-stu-id="ce9fc-186">False</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-187">TLS 上的 SASL</span><span class="sxs-lookup"><span data-stu-id="ce9fc-187">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce9fc-188">可选</span><span class="sxs-lookup"><span data-stu-id="ce9fc-188">Optional</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-189">可选</span><span class="sxs-lookup"><span data-stu-id="ce9fc-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-190">True</span><span class="sxs-lookup"><span data-stu-id="ce9fc-190">True</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-191">TLS 上的 SASL, TLS 回拨, TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="ce9fc-191">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="ce9fc-192">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-192">SASL requires TLS.</span></span> <span data-ttu-id="ce9fc-193">允许 TLS 是可选的可能会导致会话协商失败。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-193">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce9fc-194">可选</span><span class="sxs-lookup"><span data-stu-id="ce9fc-194">Optional</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-195">可选</span><span class="sxs-lookup"><span data-stu-id="ce9fc-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-196">False</span><span class="sxs-lookup"><span data-stu-id="ce9fc-196">False</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-197">TLS 上的 SASL</span><span class="sxs-lookup"><span data-stu-id="ce9fc-197">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="ce9fc-198">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-198">SASL requires TLS.</span></span> <span data-ttu-id="ce9fc-199">允许 TLS 是可选的可能会导致会话协商失败。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-199">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce9fc-200">否</span><span class="sxs-lookup"><span data-stu-id="ce9fc-200">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-201">可选</span><span class="sxs-lookup"><span data-stu-id="ce9fc-201">Optional</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-202">True</span><span class="sxs-lookup"><span data-stu-id="ce9fc-202">True</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-203">TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="ce9fc-203">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="ce9fc-204">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-204">SASL requires TLS.</span></span> <span data-ttu-id="ce9fc-205">允许 TLS 是可选的可能会导致会话协商失败。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-205">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce9fc-206">否</span><span class="sxs-lookup"><span data-stu-id="ce9fc-206">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-207">可选</span><span class="sxs-lookup"><span data-stu-id="ce9fc-207">Optional</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-208">False</span><span class="sxs-lookup"><span data-stu-id="ce9fc-208">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="ce9fc-209">配置无效</span><span class="sxs-lookup"><span data-stu-id="ce9fc-209">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="ce9fc-210">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-210">SASL requires TLS.</span></span> <span data-ttu-id="ce9fc-211">允许 TLS 是可选的可能会导致会话协商失败。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-211">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce9fc-212">必需</span><span class="sxs-lookup"><span data-stu-id="ce9fc-212">Required</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-213">否</span><span class="sxs-lookup"><span data-stu-id="ce9fc-213">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-214">True</span><span class="sxs-lookup"><span data-stu-id="ce9fc-214">True</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-215">TLS 回拨</span><span class="sxs-lookup"><span data-stu-id="ce9fc-215">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-216">配置允许 TLS 回拨。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-216">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce9fc-217">必需</span><span class="sxs-lookup"><span data-stu-id="ce9fc-217">Required</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-218">否</span><span class="sxs-lookup"><span data-stu-id="ce9fc-218">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-219">False</span><span class="sxs-lookup"><span data-stu-id="ce9fc-219">False</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-220">配置无效</span><span class="sxs-lookup"><span data-stu-id="ce9fc-220">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="ce9fc-221">必须启用 SASL 或回拨。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-221">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce9fc-222">可选</span><span class="sxs-lookup"><span data-stu-id="ce9fc-222">Optional</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-223">否</span><span class="sxs-lookup"><span data-stu-id="ce9fc-223">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-224">True</span><span class="sxs-lookup"><span data-stu-id="ce9fc-224">True</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-225">TLS 回拨, TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="ce9fc-225">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-226">根据其他终结点的协商选项, 将接受 TCP 或 TLS 回拨。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-226">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce9fc-227">可选</span><span class="sxs-lookup"><span data-stu-id="ce9fc-227">Optional</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-228">否</span><span class="sxs-lookup"><span data-stu-id="ce9fc-228">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-229">False</span><span class="sxs-lookup"><span data-stu-id="ce9fc-229">False</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-230">配置无效</span><span class="sxs-lookup"><span data-stu-id="ce9fc-230">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="ce9fc-231">必须启用 SASL 或回拨。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-231">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce9fc-232">否</span><span class="sxs-lookup"><span data-stu-id="ce9fc-232">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-233">否</span><span class="sxs-lookup"><span data-stu-id="ce9fc-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-234">True</span><span class="sxs-lookup"><span data-stu-id="ce9fc-234">True</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-235">TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="ce9fc-235">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-236">TCP 回拨是唯一可用的协商方法</span><span class="sxs-lookup"><span data-stu-id="ce9fc-236">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce9fc-237">否</span><span class="sxs-lookup"><span data-stu-id="ce9fc-237">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-238">否</span><span class="sxs-lookup"><span data-stu-id="ce9fc-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-239">False</span><span class="sxs-lookup"><span data-stu-id="ce9fc-239">False</span></span></p></td>
<td><p><span data-ttu-id="ce9fc-240">配置无效</span><span class="sxs-lookup"><span data-stu-id="ce9fc-240">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="ce9fc-241">必须启用 SASL 或回拨。</span><span class="sxs-lookup"><span data-stu-id="ce9fc-241">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

