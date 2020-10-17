---
title: Lync Server 2013： XMPP 联盟伙伴的协商设置
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
ms.openlocfilehash: bdb09d52970b5fd97395acda6a2e4fbc824a378d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505589"
---
# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="33a98-102">Lync Server 2013 中 XMPP 联盟伙伴的协商设置</span><span class="sxs-lookup"><span data-stu-id="33a98-102">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33a98-103">_**上次修改的主题：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="33a98-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="33a98-104">XMPP 合作伙伴的配置中的协商类型设置有多种可能的组合。</span><span class="sxs-lookup"><span data-stu-id="33a98-104">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="33a98-105">并不是所有这些组合都有效。</span><span class="sxs-lookup"><span data-stu-id="33a98-105">Not all of these combinations are valid.</span></span> <span data-ttu-id="33a98-106">本主题中所述的表格将定义有效和无效的设置。</span><span class="sxs-lookup"><span data-stu-id="33a98-106">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="33a98-107">在第一个表中显示了常见配置，第二个表对所有可能的组合进行了详细说明。</span><span class="sxs-lookup"><span data-stu-id="33a98-107">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="33a98-108">请注意，除非还提供了*传输层安全性* (TLS) ，**否则**不能 (SASL) 具有*简单的身份验证和安全层*。</span><span class="sxs-lookup"><span data-stu-id="33a98-108">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="33a98-109">SASL 以未加密的 (可读) 格式发送，除非受到其他方式（如 TLS）的保护，否则永远不应传输。</span><span class="sxs-lookup"><span data-stu-id="33a98-109">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="33a98-110">常用 XMPP 联合身份验证协商方法</span><span class="sxs-lookup"><span data-stu-id="33a98-110">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="33a98-111">传输层安全性 (TLS)</span><span class="sxs-lookup"><span data-stu-id="33a98-111">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="33a98-112">简单身份验证和安全层 (SASL) </span><span class="sxs-lookup"><span data-stu-id="33a98-112">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="33a98-113">回拨身份验证</span><span class="sxs-lookup"><span data-stu-id="33a98-113">Dialback Authentication</span></span></th>
<th><span data-ttu-id="33a98-114"> (s) 的预期身份验证方法</span><span class="sxs-lookup"><span data-stu-id="33a98-114">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="33a98-115">注释</span><span class="sxs-lookup"><span data-stu-id="33a98-115">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33a98-116">必需</span><span class="sxs-lookup"><span data-stu-id="33a98-116">Required</span></span></p></td>
<td><p><span data-ttu-id="33a98-117">必需</span><span class="sxs-lookup"><span data-stu-id="33a98-117">Required</span></span></p></td>
<td><p><span data-ttu-id="33a98-118">False</span><span class="sxs-lookup"><span data-stu-id="33a98-118">False</span></span></p></td>
<td><p><span data-ttu-id="33a98-119">通过 TLS 的 SASL</span><span class="sxs-lookup"><span data-stu-id="33a98-119">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="33a98-120">TLS 和 SASL 必需有助于确保 SASL 邮件流是安全的。</span><span class="sxs-lookup"><span data-stu-id="33a98-120">TLS and SASL required helps to ensure that the SASL message stream is secure.</span></span> <span data-ttu-id="33a98-121">如果 XMPP 联盟伙伴未将 TLS 设置为必需或可选的，则不能使用回拨方法，也不能将其用于回退方法。</span><span class="sxs-lookup"><span data-stu-id="33a98-121">Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33a98-122">必需</span><span class="sxs-lookup"><span data-stu-id="33a98-122">Required</span></span></p></td>
<td><p><span data-ttu-id="33a98-123">可选</span><span class="sxs-lookup"><span data-stu-id="33a98-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="33a98-124">True</span><span class="sxs-lookup"><span data-stu-id="33a98-124">True</span></span></p></td>
<td><p><span data-ttu-id="33a98-125">TLS 上的 SASL，TLS 回拨，TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="33a98-125">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="33a98-126">如果 XMPP 联盟伙伴已将 SASL 设置为 "可选" 或 "必需的 SASL"，则需要使用 TLS。</span><span class="sxs-lookup"><span data-stu-id="33a98-126">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used.</span></span> <span data-ttu-id="33a98-127">如果 SASL 不可用，将使用 TLS 的回拨。</span><span class="sxs-lookup"><span data-stu-id="33a98-127">If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33a98-128">可选</span><span class="sxs-lookup"><span data-stu-id="33a98-128">Optional</span></span></p></td>
<td><p><span data-ttu-id="33a98-129">可选</span><span class="sxs-lookup"><span data-stu-id="33a98-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="33a98-130">True</span><span class="sxs-lookup"><span data-stu-id="33a98-130">True</span></span></p></td>
<td><p><span data-ttu-id="33a98-131">TLS 上的 SASL，TLS 回拨，TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="33a98-131">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="33a98-132">在提供的协商方法中非常灵活，这些设置依赖于 XMPP 联盟伙伴的设置。</span><span class="sxs-lookup"><span data-stu-id="33a98-132">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings.</span></span> <span data-ttu-id="33a98-133">如果合作伙伴的 TLS 是可选的或必需的，但不支持 SASL，TLS 回拨将可用。</span><span class="sxs-lookup"><span data-stu-id="33a98-133">If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available.</span></span> <span data-ttu-id="33a98-134">如果合作伙伴将 TLS 和 SASL 设置为 "可选" 或 "必需"，则使用最理想的 TLS over SASL 的选择。</span><span class="sxs-lookup"><span data-stu-id="33a98-134">If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33a98-135">不支持</span><span class="sxs-lookup"><span data-stu-id="33a98-135">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="33a98-136">不支持</span><span class="sxs-lookup"><span data-stu-id="33a98-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="33a98-137">True</span><span class="sxs-lookup"><span data-stu-id="33a98-137">True</span></span></p></td>
<td><p><span data-ttu-id="33a98-138">TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="33a98-138">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="33a98-139">在很多情况下，TCP 回拨是唯一可行的解决方案。</span><span class="sxs-lookup"><span data-stu-id="33a98-139">In many cases, TCP Dialback is the only possible solution.</span></span> <span data-ttu-id="33a98-140">比其他选项更不理想，它提供一定级别的信任。</span><span class="sxs-lookup"><span data-stu-id="33a98-140">Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="33a98-141">XMPP 联合协商方法矩阵-完整</span><span class="sxs-lookup"><span data-stu-id="33a98-141">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="33a98-142">传输层安全性 (TLS)</span><span class="sxs-lookup"><span data-stu-id="33a98-142">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="33a98-143">简单身份验证和安全层 (SASL) </span><span class="sxs-lookup"><span data-stu-id="33a98-143">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="33a98-144">回拨身份验证</span><span class="sxs-lookup"><span data-stu-id="33a98-144">Dialback Authentication</span></span></th>
<th><span data-ttu-id="33a98-145">预期的身份验证方法</span><span class="sxs-lookup"><span data-stu-id="33a98-145">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="33a98-146">无效配置的备注、警告或错误</span><span class="sxs-lookup"><span data-stu-id="33a98-146">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33a98-147">必需</span><span class="sxs-lookup"><span data-stu-id="33a98-147">Required</span></span></p></td>
<td><p><span data-ttu-id="33a98-148">必需</span><span class="sxs-lookup"><span data-stu-id="33a98-148">Required</span></span></p></td>
<td><p><span data-ttu-id="33a98-149">True</span><span class="sxs-lookup"><span data-stu-id="33a98-149">True</span></span></p></td>
<td><p><span data-ttu-id="33a98-150">通过 TLS 的 SASL</span><span class="sxs-lookup"><span data-stu-id="33a98-150">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="33a98-151">如果需要 SASL 和 TLS，回拨将不会运行。</span><span class="sxs-lookup"><span data-stu-id="33a98-151">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33a98-152">必需</span><span class="sxs-lookup"><span data-stu-id="33a98-152">Required</span></span></p></td>
<td><p><span data-ttu-id="33a98-153">必需</span><span class="sxs-lookup"><span data-stu-id="33a98-153">Required</span></span></p></td>
<td><p><span data-ttu-id="33a98-154">False</span><span class="sxs-lookup"><span data-stu-id="33a98-154">False</span></span></p></td>
<td><p><span data-ttu-id="33a98-155">通过 TLS 的 SASL</span><span class="sxs-lookup"><span data-stu-id="33a98-155">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33a98-156">可选</span><span class="sxs-lookup"><span data-stu-id="33a98-156">Optional</span></span></p></td>
<td><p><span data-ttu-id="33a98-157">必需</span><span class="sxs-lookup"><span data-stu-id="33a98-157">Required</span></span></p></td>
<td><p><span data-ttu-id="33a98-158">True</span><span class="sxs-lookup"><span data-stu-id="33a98-158">True</span></span></p></td>
<td><p><span data-ttu-id="33a98-159">TLS 上的 SASL，TLS 回拨，TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="33a98-159">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="33a98-160">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="33a98-160">SASL requires TLS.</span></span> <span data-ttu-id="33a98-161">允许 TLS 是可选的可能会导致会话协商失败。</span><span class="sxs-lookup"><span data-stu-id="33a98-161">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33a98-162">可选</span><span class="sxs-lookup"><span data-stu-id="33a98-162">Optional</span></span></p></td>
<td><p><span data-ttu-id="33a98-163">必需</span><span class="sxs-lookup"><span data-stu-id="33a98-163">Required</span></span></p></td>
<td><p><span data-ttu-id="33a98-164">False</span><span class="sxs-lookup"><span data-stu-id="33a98-164">False</span></span></p></td>
<td><p><span data-ttu-id="33a98-165">通过 TLS 的 SASL</span><span class="sxs-lookup"><span data-stu-id="33a98-165">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="33a98-166">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="33a98-166">SASL requires TLS.</span></span> <span data-ttu-id="33a98-167">允许 TLS 是可选的可能会导致会话协商失败。</span><span class="sxs-lookup"><span data-stu-id="33a98-167">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33a98-168">不支持</span><span class="sxs-lookup"><span data-stu-id="33a98-168">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="33a98-169">必需</span><span class="sxs-lookup"><span data-stu-id="33a98-169">Required</span></span></p></td>
<td><p><span data-ttu-id="33a98-170">True</span><span class="sxs-lookup"><span data-stu-id="33a98-170">True</span></span></p></td>
<td><p><span data-ttu-id="33a98-171">TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="33a98-171">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="33a98-172">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="33a98-172">SASL requires TLS.</span></span> <span data-ttu-id="33a98-173">允许 TLS 是可选的可能会导致会话协商失败。</span><span class="sxs-lookup"><span data-stu-id="33a98-173">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33a98-174">不支持</span><span class="sxs-lookup"><span data-stu-id="33a98-174">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="33a98-175">必需</span><span class="sxs-lookup"><span data-stu-id="33a98-175">Required</span></span></p></td>
<td><p><span data-ttu-id="33a98-176">False</span><span class="sxs-lookup"><span data-stu-id="33a98-176">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="33a98-177">配置无效</span><span class="sxs-lookup"><span data-stu-id="33a98-177">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="33a98-178">由于 SASL 需要 TLS，并且 TLS 不可用，因此 SASL/TLS 不能成功。</span><span class="sxs-lookup"><span data-stu-id="33a98-178">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed.</span></span> <span data-ttu-id="33a98-179">TCP 回拨被设置为 false，不能使用。</span><span class="sxs-lookup"><span data-stu-id="33a98-179">TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33a98-180">必需</span><span class="sxs-lookup"><span data-stu-id="33a98-180">Required</span></span></p></td>
<td><p><span data-ttu-id="33a98-181">可选</span><span class="sxs-lookup"><span data-stu-id="33a98-181">Optional</span></span></p></td>
<td><p><span data-ttu-id="33a98-182">True</span><span class="sxs-lookup"><span data-stu-id="33a98-182">True</span></span></p></td>
<td><p><span data-ttu-id="33a98-183">TLS 上的 SASL，TLS 回拨</span><span class="sxs-lookup"><span data-stu-id="33a98-183">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33a98-184">必需</span><span class="sxs-lookup"><span data-stu-id="33a98-184">Required</span></span></p></td>
<td><p><span data-ttu-id="33a98-185">可选</span><span class="sxs-lookup"><span data-stu-id="33a98-185">Optional</span></span></p></td>
<td><p><span data-ttu-id="33a98-186">False</span><span class="sxs-lookup"><span data-stu-id="33a98-186">False</span></span></p></td>
<td><p><span data-ttu-id="33a98-187">通过 TLS 的 SASL</span><span class="sxs-lookup"><span data-stu-id="33a98-187">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33a98-188">可选</span><span class="sxs-lookup"><span data-stu-id="33a98-188">Optional</span></span></p></td>
<td><p><span data-ttu-id="33a98-189">可选</span><span class="sxs-lookup"><span data-stu-id="33a98-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="33a98-190">True</span><span class="sxs-lookup"><span data-stu-id="33a98-190">True</span></span></p></td>
<td><p><span data-ttu-id="33a98-191">TLS 上的 SASL，TLS 回拨，TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="33a98-191">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="33a98-192">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="33a98-192">SASL requires TLS.</span></span> <span data-ttu-id="33a98-193">允许 TLS 是可选的可能会导致会话协商失败。</span><span class="sxs-lookup"><span data-stu-id="33a98-193">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33a98-194">可选</span><span class="sxs-lookup"><span data-stu-id="33a98-194">Optional</span></span></p></td>
<td><p><span data-ttu-id="33a98-195">可选</span><span class="sxs-lookup"><span data-stu-id="33a98-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="33a98-196">False</span><span class="sxs-lookup"><span data-stu-id="33a98-196">False</span></span></p></td>
<td><p><span data-ttu-id="33a98-197">通过 TLS 的 SASL</span><span class="sxs-lookup"><span data-stu-id="33a98-197">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="33a98-198">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="33a98-198">SASL requires TLS.</span></span> <span data-ttu-id="33a98-199">允许 TLS 是可选的可能会导致会话协商失败。</span><span class="sxs-lookup"><span data-stu-id="33a98-199">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33a98-200">不支持</span><span class="sxs-lookup"><span data-stu-id="33a98-200">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="33a98-201">可选</span><span class="sxs-lookup"><span data-stu-id="33a98-201">Optional</span></span></p></td>
<td><p><span data-ttu-id="33a98-202">True</span><span class="sxs-lookup"><span data-stu-id="33a98-202">True</span></span></p></td>
<td><p><span data-ttu-id="33a98-203">TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="33a98-203">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="33a98-204">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="33a98-204">SASL requires TLS.</span></span> <span data-ttu-id="33a98-205">允许 TLS 是可选的可能会导致会话协商失败。</span><span class="sxs-lookup"><span data-stu-id="33a98-205">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33a98-206">不支持</span><span class="sxs-lookup"><span data-stu-id="33a98-206">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="33a98-207">可选</span><span class="sxs-lookup"><span data-stu-id="33a98-207">Optional</span></span></p></td>
<td><p><span data-ttu-id="33a98-208">False</span><span class="sxs-lookup"><span data-stu-id="33a98-208">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="33a98-209">配置无效</span><span class="sxs-lookup"><span data-stu-id="33a98-209">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="33a98-210">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="33a98-210">SASL requires TLS.</span></span> <span data-ttu-id="33a98-211">允许 TLS 是可选的可能会导致会话协商失败。</span><span class="sxs-lookup"><span data-stu-id="33a98-211">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33a98-212">必需</span><span class="sxs-lookup"><span data-stu-id="33a98-212">Required</span></span></p></td>
<td><p><span data-ttu-id="33a98-213">不支持</span><span class="sxs-lookup"><span data-stu-id="33a98-213">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="33a98-214">True</span><span class="sxs-lookup"><span data-stu-id="33a98-214">True</span></span></p></td>
<td><p><span data-ttu-id="33a98-215">TLS 回拨</span><span class="sxs-lookup"><span data-stu-id="33a98-215">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="33a98-216">配置允许 TLS 回拨。</span><span class="sxs-lookup"><span data-stu-id="33a98-216">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33a98-217">必需</span><span class="sxs-lookup"><span data-stu-id="33a98-217">Required</span></span></p></td>
<td><p><span data-ttu-id="33a98-218">不支持</span><span class="sxs-lookup"><span data-stu-id="33a98-218">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="33a98-219">False</span><span class="sxs-lookup"><span data-stu-id="33a98-219">False</span></span></p></td>
<td><p><span data-ttu-id="33a98-220">配置无效</span><span class="sxs-lookup"><span data-stu-id="33a98-220">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="33a98-221">必须启用 SASL 或回拨。</span><span class="sxs-lookup"><span data-stu-id="33a98-221">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33a98-222">可选</span><span class="sxs-lookup"><span data-stu-id="33a98-222">Optional</span></span></p></td>
<td><p><span data-ttu-id="33a98-223">不支持</span><span class="sxs-lookup"><span data-stu-id="33a98-223">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="33a98-224">True</span><span class="sxs-lookup"><span data-stu-id="33a98-224">True</span></span></p></td>
<td><p><span data-ttu-id="33a98-225">TLS 回拨，TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="33a98-225">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="33a98-226">根据其他终结点的协商选择，将接受 TCP 或 TLS 回拨。</span><span class="sxs-lookup"><span data-stu-id="33a98-226">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33a98-227">可选</span><span class="sxs-lookup"><span data-stu-id="33a98-227">Optional</span></span></p></td>
<td><p><span data-ttu-id="33a98-228">不支持</span><span class="sxs-lookup"><span data-stu-id="33a98-228">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="33a98-229">False</span><span class="sxs-lookup"><span data-stu-id="33a98-229">False</span></span></p></td>
<td><p><span data-ttu-id="33a98-230">配置无效</span><span class="sxs-lookup"><span data-stu-id="33a98-230">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="33a98-231">必须启用 SASL 或回拨。</span><span class="sxs-lookup"><span data-stu-id="33a98-231">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33a98-232">不支持</span><span class="sxs-lookup"><span data-stu-id="33a98-232">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="33a98-233">不支持</span><span class="sxs-lookup"><span data-stu-id="33a98-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="33a98-234">True</span><span class="sxs-lookup"><span data-stu-id="33a98-234">True</span></span></p></td>
<td><p><span data-ttu-id="33a98-235">TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="33a98-235">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="33a98-236">TCP 回拨是唯一可用的协商方法</span><span class="sxs-lookup"><span data-stu-id="33a98-236">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33a98-237">不支持</span><span class="sxs-lookup"><span data-stu-id="33a98-237">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="33a98-238">不支持</span><span class="sxs-lookup"><span data-stu-id="33a98-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="33a98-239">False</span><span class="sxs-lookup"><span data-stu-id="33a98-239">False</span></span></p></td>
<td><p><span data-ttu-id="33a98-240">配置无效</span><span class="sxs-lookup"><span data-stu-id="33a98-240">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="33a98-241">必须启用 SASL 或回拨。</span><span class="sxs-lookup"><span data-stu-id="33a98-241">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

