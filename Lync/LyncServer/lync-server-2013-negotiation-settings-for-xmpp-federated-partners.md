---
title: Lync Server 2013：XMPP 联盟伙伴的协商设置
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
ms.openlocfilehash: 995ee34d0a2dcf28ca6aa4f8158d0e08d1533191
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="d116d-102">Lync Server 2013 中 XMPP 联盟伙伴的协商设置</span><span class="sxs-lookup"><span data-stu-id="d116d-102">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d116d-103">_**主题上次修改时间：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="d116d-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="d116d-104">XMPP 合作伙伴配置中的协商类型的设置有多种可能的组合。</span><span class="sxs-lookup"><span data-stu-id="d116d-104">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="d116d-105">并非所有这些组合都有效。</span><span class="sxs-lookup"><span data-stu-id="d116d-105">Not all of these combinations are valid.</span></span> <span data-ttu-id="d116d-106">本主题中所述的表将定义有效和无效的设置。</span><span class="sxs-lookup"><span data-stu-id="d116d-106">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="d116d-107">常见配置显示在第一个表中，第二个表介绍了所有可能的组合。</span><span class="sxs-lookup"><span data-stu-id="d116d-107">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="d116d-108">请注意，除非也提供了 "*传输层安全性*（TLS）"，**否则**不能具有*简单的身份验证和安全层*（SASL）。</span><span class="sxs-lookup"><span data-stu-id="d116d-108">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="d116d-109">使用不加密的（可读）格式发送 SASL，除非受到另一种方式（如 TLS）保护，否则切勿传输。</span><span class="sxs-lookup"><span data-stu-id="d116d-109">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="d116d-110">常见的 XMPP 联盟协商方法</span><span class="sxs-lookup"><span data-stu-id="d116d-110">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="d116d-111">传输层安全性（TLS）</span><span class="sxs-lookup"><span data-stu-id="d116d-111">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="d116d-112">简单身份验证和安全层（SASL）</span><span class="sxs-lookup"><span data-stu-id="d116d-112">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="d116d-113">回拨身份验证</span><span class="sxs-lookup"><span data-stu-id="d116d-113">Dialback Authentication</span></span></th>
<th><span data-ttu-id="d116d-114">预期的身份验证方法</span><span class="sxs-lookup"><span data-stu-id="d116d-114">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="d116d-115">注释</span><span class="sxs-lookup"><span data-stu-id="d116d-115">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d116d-116">必需</span><span class="sxs-lookup"><span data-stu-id="d116d-116">Required</span></span></p></td>
<td><p><span data-ttu-id="d116d-117">必需</span><span class="sxs-lookup"><span data-stu-id="d116d-117">Required</span></span></p></td>
<td><p><span data-ttu-id="d116d-118">False</span><span class="sxs-lookup"><span data-stu-id="d116d-118">False</span></span></p></td>
<td><p><span data-ttu-id="d116d-119">TLS 上的 SASL</span><span class="sxs-lookup"><span data-stu-id="d116d-119">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="d116d-120">TLS 和 SASL 所需有助于确保 SASL 消息流的安全。</span><span class="sxs-lookup"><span data-stu-id="d116d-120">TLS and SASL required helps to ensure that the SASL message stream is secure.</span></span> <span data-ttu-id="d116d-121">如果 XMPP 联盟合作伙伴未将 TLS 设置为必需或可选，则回拨不可用，也不能用于回退方法。</span><span class="sxs-lookup"><span data-stu-id="d116d-121">Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d116d-122">必需</span><span class="sxs-lookup"><span data-stu-id="d116d-122">Required</span></span></p></td>
<td><p><span data-ttu-id="d116d-123">可选</span><span class="sxs-lookup"><span data-stu-id="d116d-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="d116d-124">True</span><span class="sxs-lookup"><span data-stu-id="d116d-124">True</span></span></p></td>
<td><p><span data-ttu-id="d116d-125">TLS 上的 SASL，TLS 回拨，TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="d116d-125">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="d116d-126">如果 XMPP 联盟合作伙伴已将 SASL 设置为 "可选" 或 "所需的 SASL"，则需要使用 TLS。</span><span class="sxs-lookup"><span data-stu-id="d116d-126">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used.</span></span> <span data-ttu-id="d116d-127">如果 SASL 不可用，将使用通过 TLS 的回拨。</span><span class="sxs-lookup"><span data-stu-id="d116d-127">If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d116d-128">可选</span><span class="sxs-lookup"><span data-stu-id="d116d-128">Optional</span></span></p></td>
<td><p><span data-ttu-id="d116d-129">可选</span><span class="sxs-lookup"><span data-stu-id="d116d-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="d116d-130">True</span><span class="sxs-lookup"><span data-stu-id="d116d-130">True</span></span></p></td>
<td><p><span data-ttu-id="d116d-131">TLS 上的 SASL，TLS 回拨，TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="d116d-131">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="d116d-132">在提供的协商方法中非常灵活，这些设置依赖于 XMPP 联盟伙伴的设置。</span><span class="sxs-lookup"><span data-stu-id="d116d-132">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings.</span></span> <span data-ttu-id="d116d-133">如果合作伙伴具有 TLS 可选或必需，但不支持 SASL，TLS 回拨将可用。</span><span class="sxs-lookup"><span data-stu-id="d116d-133">If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available.</span></span> <span data-ttu-id="d116d-134">如果合作伙伴将 TLS 和 SASL 设置为 "可选" 或 "所需"，则使用通过 SASL 的最佳选择。</span><span class="sxs-lookup"><span data-stu-id="d116d-134">If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d116d-135">否</span><span class="sxs-lookup"><span data-stu-id="d116d-135">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d116d-136">否</span><span class="sxs-lookup"><span data-stu-id="d116d-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d116d-137">True</span><span class="sxs-lookup"><span data-stu-id="d116d-137">True</span></span></p></td>
<td><p><span data-ttu-id="d116d-138">TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="d116d-138">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="d116d-139">在许多情况下，TCP 回拨是唯一可行的解决方案。</span><span class="sxs-lookup"><span data-stu-id="d116d-139">In many cases, TCP Dialback is the only possible solution.</span></span> <span data-ttu-id="d116d-140">比其他选项更少，它提供一定级别的信任。</span><span class="sxs-lookup"><span data-stu-id="d116d-140">Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="d116d-141">XMPP 联盟协商方法矩阵-完成</span><span class="sxs-lookup"><span data-stu-id="d116d-141">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="d116d-142">传输层安全性（TLS）</span><span class="sxs-lookup"><span data-stu-id="d116d-142">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="d116d-143">简单身份验证和安全层（SASL）</span><span class="sxs-lookup"><span data-stu-id="d116d-143">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="d116d-144">回拨身份验证</span><span class="sxs-lookup"><span data-stu-id="d116d-144">Dialback Authentication</span></span></th>
<th><span data-ttu-id="d116d-145">预期的身份验证方法</span><span class="sxs-lookup"><span data-stu-id="d116d-145">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="d116d-146">无效配置的备注、警告或错误</span><span class="sxs-lookup"><span data-stu-id="d116d-146">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d116d-147">必需</span><span class="sxs-lookup"><span data-stu-id="d116d-147">Required</span></span></p></td>
<td><p><span data-ttu-id="d116d-148">必需</span><span class="sxs-lookup"><span data-stu-id="d116d-148">Required</span></span></p></td>
<td><p><span data-ttu-id="d116d-149">True</span><span class="sxs-lookup"><span data-stu-id="d116d-149">True</span></span></p></td>
<td><p><span data-ttu-id="d116d-150">TLS 上的 SASL</span><span class="sxs-lookup"><span data-stu-id="d116d-150">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d116d-151">如果需要 SASL 和 TLS，则回拨不会运行。</span><span class="sxs-lookup"><span data-stu-id="d116d-151">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d116d-152">必需</span><span class="sxs-lookup"><span data-stu-id="d116d-152">Required</span></span></p></td>
<td><p><span data-ttu-id="d116d-153">必需</span><span class="sxs-lookup"><span data-stu-id="d116d-153">Required</span></span></p></td>
<td><p><span data-ttu-id="d116d-154">False</span><span class="sxs-lookup"><span data-stu-id="d116d-154">False</span></span></p></td>
<td><p><span data-ttu-id="d116d-155">TLS 上的 SASL</span><span class="sxs-lookup"><span data-stu-id="d116d-155">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d116d-156">可选</span><span class="sxs-lookup"><span data-stu-id="d116d-156">Optional</span></span></p></td>
<td><p><span data-ttu-id="d116d-157">必需</span><span class="sxs-lookup"><span data-stu-id="d116d-157">Required</span></span></p></td>
<td><p><span data-ttu-id="d116d-158">True</span><span class="sxs-lookup"><span data-stu-id="d116d-158">True</span></span></p></td>
<td><p><span data-ttu-id="d116d-159">TLS 上的 SASL，TLS 回拨，TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="d116d-159">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d116d-160">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="d116d-160">SASL requires TLS.</span></span> <span data-ttu-id="d116d-161">允许 TLS 是可选的可能会导致会话协商失败。</span><span class="sxs-lookup"><span data-stu-id="d116d-161">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d116d-162">可选</span><span class="sxs-lookup"><span data-stu-id="d116d-162">Optional</span></span></p></td>
<td><p><span data-ttu-id="d116d-163">必需</span><span class="sxs-lookup"><span data-stu-id="d116d-163">Required</span></span></p></td>
<td><p><span data-ttu-id="d116d-164">False</span><span class="sxs-lookup"><span data-stu-id="d116d-164">False</span></span></p></td>
<td><p><span data-ttu-id="d116d-165">TLS 上的 SASL</span><span class="sxs-lookup"><span data-stu-id="d116d-165">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d116d-166">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="d116d-166">SASL requires TLS.</span></span> <span data-ttu-id="d116d-167">允许 TLS 是可选的可能会导致会话协商失败。</span><span class="sxs-lookup"><span data-stu-id="d116d-167">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d116d-168">否</span><span class="sxs-lookup"><span data-stu-id="d116d-168">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d116d-169">必需</span><span class="sxs-lookup"><span data-stu-id="d116d-169">Required</span></span></p></td>
<td><p><span data-ttu-id="d116d-170">True</span><span class="sxs-lookup"><span data-stu-id="d116d-170">True</span></span></p></td>
<td><p><span data-ttu-id="d116d-171">TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="d116d-171">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d116d-172">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="d116d-172">SASL requires TLS.</span></span> <span data-ttu-id="d116d-173">允许 TLS 是可选的可能会导致会话协商失败。</span><span class="sxs-lookup"><span data-stu-id="d116d-173">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d116d-174">否</span><span class="sxs-lookup"><span data-stu-id="d116d-174">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d116d-175">必需</span><span class="sxs-lookup"><span data-stu-id="d116d-175">Required</span></span></p></td>
<td><p><span data-ttu-id="d116d-176">False</span><span class="sxs-lookup"><span data-stu-id="d116d-176">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d116d-177">配置无效</span><span class="sxs-lookup"><span data-stu-id="d116d-177">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d116d-178">由于 SASL 需要 TLS，并且 TLS 不可用，因此不能成功使用 SASL/TLS。</span><span class="sxs-lookup"><span data-stu-id="d116d-178">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed.</span></span> <span data-ttu-id="d116d-179">TCP 回拨已设置为 false，无法使用。</span><span class="sxs-lookup"><span data-stu-id="d116d-179">TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d116d-180">必需</span><span class="sxs-lookup"><span data-stu-id="d116d-180">Required</span></span></p></td>
<td><p><span data-ttu-id="d116d-181">可选</span><span class="sxs-lookup"><span data-stu-id="d116d-181">Optional</span></span></p></td>
<td><p><span data-ttu-id="d116d-182">True</span><span class="sxs-lookup"><span data-stu-id="d116d-182">True</span></span></p></td>
<td><p><span data-ttu-id="d116d-183">TLS 上的 SASL，TLS 回拨</span><span class="sxs-lookup"><span data-stu-id="d116d-183">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d116d-184">必需</span><span class="sxs-lookup"><span data-stu-id="d116d-184">Required</span></span></p></td>
<td><p><span data-ttu-id="d116d-185">可选</span><span class="sxs-lookup"><span data-stu-id="d116d-185">Optional</span></span></p></td>
<td><p><span data-ttu-id="d116d-186">False</span><span class="sxs-lookup"><span data-stu-id="d116d-186">False</span></span></p></td>
<td><p><span data-ttu-id="d116d-187">TLS 上的 SASL</span><span class="sxs-lookup"><span data-stu-id="d116d-187">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d116d-188">可选</span><span class="sxs-lookup"><span data-stu-id="d116d-188">Optional</span></span></p></td>
<td><p><span data-ttu-id="d116d-189">可选</span><span class="sxs-lookup"><span data-stu-id="d116d-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="d116d-190">True</span><span class="sxs-lookup"><span data-stu-id="d116d-190">True</span></span></p></td>
<td><p><span data-ttu-id="d116d-191">TLS 上的 SASL，TLS 回拨，TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="d116d-191">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d116d-192">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="d116d-192">SASL requires TLS.</span></span> <span data-ttu-id="d116d-193">允许 TLS 是可选的可能会导致会话协商失败。</span><span class="sxs-lookup"><span data-stu-id="d116d-193">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d116d-194">可选</span><span class="sxs-lookup"><span data-stu-id="d116d-194">Optional</span></span></p></td>
<td><p><span data-ttu-id="d116d-195">可选</span><span class="sxs-lookup"><span data-stu-id="d116d-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="d116d-196">False</span><span class="sxs-lookup"><span data-stu-id="d116d-196">False</span></span></p></td>
<td><p><span data-ttu-id="d116d-197">TLS 上的 SASL</span><span class="sxs-lookup"><span data-stu-id="d116d-197">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d116d-198">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="d116d-198">SASL requires TLS.</span></span> <span data-ttu-id="d116d-199">允许 TLS 是可选的可能会导致会话协商失败。</span><span class="sxs-lookup"><span data-stu-id="d116d-199">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d116d-200">否</span><span class="sxs-lookup"><span data-stu-id="d116d-200">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d116d-201">可选</span><span class="sxs-lookup"><span data-stu-id="d116d-201">Optional</span></span></p></td>
<td><p><span data-ttu-id="d116d-202">True</span><span class="sxs-lookup"><span data-stu-id="d116d-202">True</span></span></p></td>
<td><p><span data-ttu-id="d116d-203">TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="d116d-203">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d116d-204">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="d116d-204">SASL requires TLS.</span></span> <span data-ttu-id="d116d-205">允许 TLS 是可选的可能会导致会话协商失败。</span><span class="sxs-lookup"><span data-stu-id="d116d-205">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d116d-206">否</span><span class="sxs-lookup"><span data-stu-id="d116d-206">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d116d-207">可选</span><span class="sxs-lookup"><span data-stu-id="d116d-207">Optional</span></span></p></td>
<td><p><span data-ttu-id="d116d-208">False</span><span class="sxs-lookup"><span data-stu-id="d116d-208">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d116d-209">配置无效</span><span class="sxs-lookup"><span data-stu-id="d116d-209">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d116d-210">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="d116d-210">SASL requires TLS.</span></span> <span data-ttu-id="d116d-211">允许 TLS 是可选的可能会导致会话协商失败。</span><span class="sxs-lookup"><span data-stu-id="d116d-211">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d116d-212">必需</span><span class="sxs-lookup"><span data-stu-id="d116d-212">Required</span></span></p></td>
<td><p><span data-ttu-id="d116d-213">否</span><span class="sxs-lookup"><span data-stu-id="d116d-213">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d116d-214">True</span><span class="sxs-lookup"><span data-stu-id="d116d-214">True</span></span></p></td>
<td><p><span data-ttu-id="d116d-215">TLS 回拨</span><span class="sxs-lookup"><span data-stu-id="d116d-215">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="d116d-216">配置允许 TLS 回拨。</span><span class="sxs-lookup"><span data-stu-id="d116d-216">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d116d-217">必需</span><span class="sxs-lookup"><span data-stu-id="d116d-217">Required</span></span></p></td>
<td><p><span data-ttu-id="d116d-218">否</span><span class="sxs-lookup"><span data-stu-id="d116d-218">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d116d-219">False</span><span class="sxs-lookup"><span data-stu-id="d116d-219">False</span></span></p></td>
<td><p><span data-ttu-id="d116d-220">配置无效</span><span class="sxs-lookup"><span data-stu-id="d116d-220">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d116d-221">必须启用 SASL 或回拨。</span><span class="sxs-lookup"><span data-stu-id="d116d-221">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d116d-222">可选</span><span class="sxs-lookup"><span data-stu-id="d116d-222">Optional</span></span></p></td>
<td><p><span data-ttu-id="d116d-223">否</span><span class="sxs-lookup"><span data-stu-id="d116d-223">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d116d-224">True</span><span class="sxs-lookup"><span data-stu-id="d116d-224">True</span></span></p></td>
<td><p><span data-ttu-id="d116d-225">TLS 回拨，TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="d116d-225">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="d116d-226">根据其他终结点的协商选项，将接受 TCP 或 TLS 回拨。</span><span class="sxs-lookup"><span data-stu-id="d116d-226">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d116d-227">可选</span><span class="sxs-lookup"><span data-stu-id="d116d-227">Optional</span></span></p></td>
<td><p><span data-ttu-id="d116d-228">否</span><span class="sxs-lookup"><span data-stu-id="d116d-228">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d116d-229">False</span><span class="sxs-lookup"><span data-stu-id="d116d-229">False</span></span></p></td>
<td><p><span data-ttu-id="d116d-230">配置无效</span><span class="sxs-lookup"><span data-stu-id="d116d-230">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d116d-231">必须启用 SASL 或回拨。</span><span class="sxs-lookup"><span data-stu-id="d116d-231">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d116d-232">否</span><span class="sxs-lookup"><span data-stu-id="d116d-232">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d116d-233">否</span><span class="sxs-lookup"><span data-stu-id="d116d-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d116d-234">True</span><span class="sxs-lookup"><span data-stu-id="d116d-234">True</span></span></p></td>
<td><p><span data-ttu-id="d116d-235">TCP 回拨</span><span class="sxs-lookup"><span data-stu-id="d116d-235">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="d116d-236">TCP 回拨是唯一可用的协商方法</span><span class="sxs-lookup"><span data-stu-id="d116d-236">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d116d-237">否</span><span class="sxs-lookup"><span data-stu-id="d116d-237">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d116d-238">否</span><span class="sxs-lookup"><span data-stu-id="d116d-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d116d-239">False</span><span class="sxs-lookup"><span data-stu-id="d116d-239">False</span></span></p></td>
<td><p><span data-ttu-id="d116d-240">配置无效</span><span class="sxs-lookup"><span data-stu-id="d116d-240">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d116d-241">必须启用 SASL 或回拨。</span><span class="sxs-lookup"><span data-stu-id="d116d-241">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

