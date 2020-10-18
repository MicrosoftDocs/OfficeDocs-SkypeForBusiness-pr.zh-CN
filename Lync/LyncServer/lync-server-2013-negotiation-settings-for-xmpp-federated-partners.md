---
title: Lync Server 2013： XMPP 联盟伙伴的协商设置
description: Lync Server 2013： XMPP 联盟伙伴的协商设置。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ac3d9c69d407dc750a1afb35f0a448869a88f09
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578638"
---
# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="36d84-103">Lync Server 2013 中 XMPP 联盟伙伴的协商设置</span><span class="sxs-lookup"><span data-stu-id="36d84-103">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36d84-104">_**上次修改的主题：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="36d84-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="36d84-105">XMPP 合作伙伴的配置中的协商类型设置有多种可能的组合。</span><span class="sxs-lookup"><span data-stu-id="36d84-105">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="36d84-106">并不是所有这些组合都有效。</span><span class="sxs-lookup"><span data-stu-id="36d84-106">Not all of these combinations are valid.</span></span> <span data-ttu-id="36d84-107">本主题中所述的表格将定义有效和无效的设置。</span><span class="sxs-lookup"><span data-stu-id="36d84-107">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="36d84-108">在第一个表中显示了常见配置，第二个表对所有可能的组合进行了详细说明。</span><span class="sxs-lookup"><span data-stu-id="36d84-108">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="36d84-109">请注意，除非还提供了*传输层安全性* (TLS) ，**否则**不能 (SASL) 具有*简单的身份验证和安全层*。</span><span class="sxs-lookup"><span data-stu-id="36d84-109">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="36d84-110">SASL 以未加密的 (可读) 格式发送，除非受到其他方式（如 TLS）的保护，否则永远不应传输。</span><span class="sxs-lookup"><span data-stu-id="36d84-110">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="36d84-111">常用 XMPP 联合身份验证协商方法</span><span class="sxs-lookup"><span data-stu-id="36d84-111">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="36d84-112">传输层安全性 (TLS)</span><span class="sxs-lookup"><span data-stu-id="36d84-112">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="36d84-113">简单身份验证和安全层 (SASL) </span><span class="sxs-lookup"><span data-stu-id="36d84-113">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="36d84-114">回拨身份验证</span><span class="sxs-lookup"><span data-stu-id="36d84-114">Dialback Authentication</span></span></th>
<th><span data-ttu-id="36d84-115"> (s) 的预期身份验证方法</span><span class="sxs-lookup"><span data-stu-id="36d84-115">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="36d84-116">注释</span><span class="sxs-lookup"><span data-stu-id="36d84-116">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36d84-117">必需</span><span class="sxs-lookup"><span data-stu-id="36d84-117">Required</span></span></p></td>
<td><p><span data-ttu-id="36d84-118">必需</span><span class="sxs-lookup"><span data-stu-id="36d84-118">Required</span></span></p></td>
<td><p><span data-ttu-id="36d84-119">False</span><span class="sxs-lookup"><span data-stu-id="36d84-119">False</span></span></p></td>
<td><p><span data-ttu-id="36d84-120">通过 TLS 的 SASL</span><span class="sxs-lookup"><span data-stu-id="36d84-120">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="36d84-121">TLS 和 SASL 必需有助于确保 SASL 邮件流是安全的。</span><span class="sxs-lookup"><span data-stu-id="36d84-121">TLS and SASL required helps to ensure that the SASL message stream is secure.</span></span> <span data-ttu-id="36d84-122">如果 XMPP 联盟伙伴未将 TLS 设置为必需或可选的，则不能使用回拨方法，也不能将其用于回退方法。</span><span class="sxs-lookup"><span data-stu-id="36d84-122">Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36d84-123">必需</span><span class="sxs-lookup"><span data-stu-id="36d84-123">Required</span></span></p></td>
<td><p><span data-ttu-id="36d84-124">可选</span><span class="sxs-lookup"><span data-stu-id="36d84-124">Optional</span></span></p></td>
<td><p><span data-ttu-id="36d84-125">True</span><span class="sxs-lookup"><span data-stu-id="36d84-125">True</span></span></p></td>
<td><p><span data-ttu-id="36d84-126">TLS 上的 SASL，TLS 回拨，TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="36d84-126">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="36d84-127">如果 XMPP 联盟伙伴已将 SASL 设置为 "可选" 或 "必需的 SASL"，则需要使用 TLS。</span><span class="sxs-lookup"><span data-stu-id="36d84-127">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used.</span></span> <span data-ttu-id="36d84-128">如果 SASL 不可用，将使用 TLS 的回拨。</span><span class="sxs-lookup"><span data-stu-id="36d84-128">If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36d84-129">可选</span><span class="sxs-lookup"><span data-stu-id="36d84-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="36d84-130">可选</span><span class="sxs-lookup"><span data-stu-id="36d84-130">Optional</span></span></p></td>
<td><p><span data-ttu-id="36d84-131">True</span><span class="sxs-lookup"><span data-stu-id="36d84-131">True</span></span></p></td>
<td><p><span data-ttu-id="36d84-132">TLS 上的 SASL，TLS 回拨，TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="36d84-132">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="36d84-133">在提供的协商方法中非常灵活，这些设置依赖于 XMPP 联盟伙伴的设置。</span><span class="sxs-lookup"><span data-stu-id="36d84-133">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings.</span></span> <span data-ttu-id="36d84-134">如果合作伙伴的 TLS 是可选的或必需的，但不支持 SASL，TLS 回拨将可用。</span><span class="sxs-lookup"><span data-stu-id="36d84-134">If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available.</span></span> <span data-ttu-id="36d84-135">如果合作伙伴将 TLS 和 SASL 设置为 "可选" 或 "必需"，则使用最理想的 TLS over SASL 的选择。</span><span class="sxs-lookup"><span data-stu-id="36d84-135">If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36d84-136">不支持</span><span class="sxs-lookup"><span data-stu-id="36d84-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="36d84-137">不支持</span><span class="sxs-lookup"><span data-stu-id="36d84-137">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="36d84-138">True</span><span class="sxs-lookup"><span data-stu-id="36d84-138">True</span></span></p></td>
<td><p><span data-ttu-id="36d84-139">TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="36d84-139">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="36d84-140">在很多情况下，TCP 回拨是唯一可行的解决方案。</span><span class="sxs-lookup"><span data-stu-id="36d84-140">In many cases, TCP Dialback is the only possible solution.</span></span> <span data-ttu-id="36d84-141">比其他选项更不理想，它提供一定级别的信任。</span><span class="sxs-lookup"><span data-stu-id="36d84-141">Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="36d84-142">XMPP 联合协商方法矩阵-完整</span><span class="sxs-lookup"><span data-stu-id="36d84-142">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="36d84-143">传输层安全性 (TLS)</span><span class="sxs-lookup"><span data-stu-id="36d84-143">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="36d84-144">简单身份验证和安全层 (SASL) </span><span class="sxs-lookup"><span data-stu-id="36d84-144">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="36d84-145">回拨身份验证</span><span class="sxs-lookup"><span data-stu-id="36d84-145">Dialback Authentication</span></span></th>
<th><span data-ttu-id="36d84-146">预期的身份验证方法</span><span class="sxs-lookup"><span data-stu-id="36d84-146">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="36d84-147">无效配置的备注、警告或错误</span><span class="sxs-lookup"><span data-stu-id="36d84-147">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36d84-148">必需</span><span class="sxs-lookup"><span data-stu-id="36d84-148">Required</span></span></p></td>
<td><p><span data-ttu-id="36d84-149">必需</span><span class="sxs-lookup"><span data-stu-id="36d84-149">Required</span></span></p></td>
<td><p><span data-ttu-id="36d84-150">True</span><span class="sxs-lookup"><span data-stu-id="36d84-150">True</span></span></p></td>
<td><p><span data-ttu-id="36d84-151">通过 TLS 的 SASL</span><span class="sxs-lookup"><span data-stu-id="36d84-151">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="36d84-152">如果需要 SASL 和 TLS，回拨将不会运行。</span><span class="sxs-lookup"><span data-stu-id="36d84-152">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36d84-153">必需</span><span class="sxs-lookup"><span data-stu-id="36d84-153">Required</span></span></p></td>
<td><p><span data-ttu-id="36d84-154">必需</span><span class="sxs-lookup"><span data-stu-id="36d84-154">Required</span></span></p></td>
<td><p><span data-ttu-id="36d84-155">False</span><span class="sxs-lookup"><span data-stu-id="36d84-155">False</span></span></p></td>
<td><p><span data-ttu-id="36d84-156">通过 TLS 的 SASL</span><span class="sxs-lookup"><span data-stu-id="36d84-156">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36d84-157">可选</span><span class="sxs-lookup"><span data-stu-id="36d84-157">Optional</span></span></p></td>
<td><p><span data-ttu-id="36d84-158">必需</span><span class="sxs-lookup"><span data-stu-id="36d84-158">Required</span></span></p></td>
<td><p><span data-ttu-id="36d84-159">True</span><span class="sxs-lookup"><span data-stu-id="36d84-159">True</span></span></p></td>
<td><p><span data-ttu-id="36d84-160">TLS 上的 SASL，TLS 回拨，TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="36d84-160">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="36d84-161">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="36d84-161">SASL requires TLS.</span></span> <span data-ttu-id="36d84-162">允许 TLS 是可选的可能会导致会话协商失败。</span><span class="sxs-lookup"><span data-stu-id="36d84-162">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36d84-163">可选</span><span class="sxs-lookup"><span data-stu-id="36d84-163">Optional</span></span></p></td>
<td><p><span data-ttu-id="36d84-164">必需</span><span class="sxs-lookup"><span data-stu-id="36d84-164">Required</span></span></p></td>
<td><p><span data-ttu-id="36d84-165">False</span><span class="sxs-lookup"><span data-stu-id="36d84-165">False</span></span></p></td>
<td><p><span data-ttu-id="36d84-166">通过 TLS 的 SASL</span><span class="sxs-lookup"><span data-stu-id="36d84-166">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="36d84-167">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="36d84-167">SASL requires TLS.</span></span> <span data-ttu-id="36d84-168">允许 TLS 是可选的可能会导致会话协商失败。</span><span class="sxs-lookup"><span data-stu-id="36d84-168">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36d84-169">不支持</span><span class="sxs-lookup"><span data-stu-id="36d84-169">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="36d84-170">必需</span><span class="sxs-lookup"><span data-stu-id="36d84-170">Required</span></span></p></td>
<td><p><span data-ttu-id="36d84-171">True</span><span class="sxs-lookup"><span data-stu-id="36d84-171">True</span></span></p></td>
<td><p><span data-ttu-id="36d84-172">TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="36d84-172">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="36d84-173">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="36d84-173">SASL requires TLS.</span></span> <span data-ttu-id="36d84-174">允许 TLS 是可选的可能会导致会话协商失败。</span><span class="sxs-lookup"><span data-stu-id="36d84-174">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36d84-175">不支持</span><span class="sxs-lookup"><span data-stu-id="36d84-175">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="36d84-176">必需</span><span class="sxs-lookup"><span data-stu-id="36d84-176">Required</span></span></p></td>
<td><p><span data-ttu-id="36d84-177">False</span><span class="sxs-lookup"><span data-stu-id="36d84-177">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="36d84-178">配置无效</span><span class="sxs-lookup"><span data-stu-id="36d84-178">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="36d84-179">由于 SASL 需要 TLS，并且 TLS 不可用，因此 SASL/TLS 不能成功。</span><span class="sxs-lookup"><span data-stu-id="36d84-179">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed.</span></span> <span data-ttu-id="36d84-180">TCP 回拨被设置为 false，不能使用。</span><span class="sxs-lookup"><span data-stu-id="36d84-180">TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36d84-181">必需</span><span class="sxs-lookup"><span data-stu-id="36d84-181">Required</span></span></p></td>
<td><p><span data-ttu-id="36d84-182">可选</span><span class="sxs-lookup"><span data-stu-id="36d84-182">Optional</span></span></p></td>
<td><p><span data-ttu-id="36d84-183">True</span><span class="sxs-lookup"><span data-stu-id="36d84-183">True</span></span></p></td>
<td><p><span data-ttu-id="36d84-184">TLS 上的 SASL，TLS 回拨</span><span class="sxs-lookup"><span data-stu-id="36d84-184">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36d84-185">必需</span><span class="sxs-lookup"><span data-stu-id="36d84-185">Required</span></span></p></td>
<td><p><span data-ttu-id="36d84-186">可选</span><span class="sxs-lookup"><span data-stu-id="36d84-186">Optional</span></span></p></td>
<td><p><span data-ttu-id="36d84-187">False</span><span class="sxs-lookup"><span data-stu-id="36d84-187">False</span></span></p></td>
<td><p><span data-ttu-id="36d84-188">通过 TLS 的 SASL</span><span class="sxs-lookup"><span data-stu-id="36d84-188">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36d84-189">可选</span><span class="sxs-lookup"><span data-stu-id="36d84-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="36d84-190">可选</span><span class="sxs-lookup"><span data-stu-id="36d84-190">Optional</span></span></p></td>
<td><p><span data-ttu-id="36d84-191">True</span><span class="sxs-lookup"><span data-stu-id="36d84-191">True</span></span></p></td>
<td><p><span data-ttu-id="36d84-192">TLS 上的 SASL，TLS 回拨，TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="36d84-192">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="36d84-193">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="36d84-193">SASL requires TLS.</span></span> <span data-ttu-id="36d84-194">允许 TLS 是可选的可能会导致会话协商失败。</span><span class="sxs-lookup"><span data-stu-id="36d84-194">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36d84-195">可选</span><span class="sxs-lookup"><span data-stu-id="36d84-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="36d84-196">可选</span><span class="sxs-lookup"><span data-stu-id="36d84-196">Optional</span></span></p></td>
<td><p><span data-ttu-id="36d84-197">False</span><span class="sxs-lookup"><span data-stu-id="36d84-197">False</span></span></p></td>
<td><p><span data-ttu-id="36d84-198">通过 TLS 的 SASL</span><span class="sxs-lookup"><span data-stu-id="36d84-198">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="36d84-199">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="36d84-199">SASL requires TLS.</span></span> <span data-ttu-id="36d84-200">允许 TLS 是可选的可能会导致会话协商失败。</span><span class="sxs-lookup"><span data-stu-id="36d84-200">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36d84-201">不支持</span><span class="sxs-lookup"><span data-stu-id="36d84-201">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="36d84-202">可选</span><span class="sxs-lookup"><span data-stu-id="36d84-202">Optional</span></span></p></td>
<td><p><span data-ttu-id="36d84-203">True</span><span class="sxs-lookup"><span data-stu-id="36d84-203">True</span></span></p></td>
<td><p><span data-ttu-id="36d84-204">TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="36d84-204">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="36d84-205">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="36d84-205">SASL requires TLS.</span></span> <span data-ttu-id="36d84-206">允许 TLS 是可选的可能会导致会话协商失败。</span><span class="sxs-lookup"><span data-stu-id="36d84-206">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36d84-207">不支持</span><span class="sxs-lookup"><span data-stu-id="36d84-207">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="36d84-208">可选</span><span class="sxs-lookup"><span data-stu-id="36d84-208">Optional</span></span></p></td>
<td><p><span data-ttu-id="36d84-209">False</span><span class="sxs-lookup"><span data-stu-id="36d84-209">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="36d84-210">配置无效</span><span class="sxs-lookup"><span data-stu-id="36d84-210">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="36d84-211">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="36d84-211">SASL requires TLS.</span></span> <span data-ttu-id="36d84-212">允许 TLS 是可选的可能会导致会话协商失败。</span><span class="sxs-lookup"><span data-stu-id="36d84-212">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36d84-213">必需</span><span class="sxs-lookup"><span data-stu-id="36d84-213">Required</span></span></p></td>
<td><p><span data-ttu-id="36d84-214">不支持</span><span class="sxs-lookup"><span data-stu-id="36d84-214">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="36d84-215">True</span><span class="sxs-lookup"><span data-stu-id="36d84-215">True</span></span></p></td>
<td><p><span data-ttu-id="36d84-216">TLS 回拨</span><span class="sxs-lookup"><span data-stu-id="36d84-216">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="36d84-217">配置允许 TLS 回拨。</span><span class="sxs-lookup"><span data-stu-id="36d84-217">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36d84-218">必需</span><span class="sxs-lookup"><span data-stu-id="36d84-218">Required</span></span></p></td>
<td><p><span data-ttu-id="36d84-219">不支持</span><span class="sxs-lookup"><span data-stu-id="36d84-219">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="36d84-220">False</span><span class="sxs-lookup"><span data-stu-id="36d84-220">False</span></span></p></td>
<td><p><span data-ttu-id="36d84-221">配置无效</span><span class="sxs-lookup"><span data-stu-id="36d84-221">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="36d84-222">必须启用 SASL 或回拨。</span><span class="sxs-lookup"><span data-stu-id="36d84-222">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36d84-223">可选</span><span class="sxs-lookup"><span data-stu-id="36d84-223">Optional</span></span></p></td>
<td><p><span data-ttu-id="36d84-224">不支持</span><span class="sxs-lookup"><span data-stu-id="36d84-224">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="36d84-225">True</span><span class="sxs-lookup"><span data-stu-id="36d84-225">True</span></span></p></td>
<td><p><span data-ttu-id="36d84-226">TLS 回拨，TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="36d84-226">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="36d84-227">根据其他终结点的协商选择，将接受 TCP 或 TLS 回拨。</span><span class="sxs-lookup"><span data-stu-id="36d84-227">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36d84-228">可选</span><span class="sxs-lookup"><span data-stu-id="36d84-228">Optional</span></span></p></td>
<td><p><span data-ttu-id="36d84-229">不支持</span><span class="sxs-lookup"><span data-stu-id="36d84-229">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="36d84-230">False</span><span class="sxs-lookup"><span data-stu-id="36d84-230">False</span></span></p></td>
<td><p><span data-ttu-id="36d84-231">配置无效</span><span class="sxs-lookup"><span data-stu-id="36d84-231">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="36d84-232">必须启用 SASL 或回拨。</span><span class="sxs-lookup"><span data-stu-id="36d84-232">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36d84-233">不支持</span><span class="sxs-lookup"><span data-stu-id="36d84-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="36d84-234">不支持</span><span class="sxs-lookup"><span data-stu-id="36d84-234">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="36d84-235">True</span><span class="sxs-lookup"><span data-stu-id="36d84-235">True</span></span></p></td>
<td><p><span data-ttu-id="36d84-236">TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="36d84-236">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="36d84-237">TCP 回拨是唯一可用的协商方法</span><span class="sxs-lookup"><span data-stu-id="36d84-237">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36d84-238">不支持</span><span class="sxs-lookup"><span data-stu-id="36d84-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="36d84-239">不支持</span><span class="sxs-lookup"><span data-stu-id="36d84-239">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="36d84-240">False</span><span class="sxs-lookup"><span data-stu-id="36d84-240">False</span></span></p></td>
<td><p><span data-ttu-id="36d84-241">配置无效</span><span class="sxs-lookup"><span data-stu-id="36d84-241">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="36d84-242">必须启用 SASL 或回拨。</span><span class="sxs-lookup"><span data-stu-id="36d84-242">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

