---
title: Lync Server 2013：从另一个应用程序启动 Lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Starting Lync from another application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398376(v=OCS.15)
ms:contentKeyID: 48184184
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d10e70615083796baa0934c6291b377dcd18005
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519509"
---
# <a name="starting-lync-from-another-application"></a><span data-ttu-id="dea10-102">从另一个应用程序启动 Lync</span><span class="sxs-lookup"><span data-stu-id="dea10-102">Starting Lync from another application</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dea10-103">_**上次修改的主题：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="dea10-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="dea10-104">您可以使用命令行参数快速启动 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="dea10-104">You can use command-line parameters to quick-start Lync 2013.</span></span> <span data-ttu-id="dea10-105">例如，如果用户在另一个应用程序中单击某个电话号码，则应用程序可以启动 Lync 2013 的一个实例，并启动对该号码的呼叫。</span><span class="sxs-lookup"><span data-stu-id="dea10-105">For example, if a user clicks a phone number in another application, the application can start an instance of Lync 2013 and initiate a call to that number.</span></span>

<span data-ttu-id="dea10-106">Lync 2013 还可以识别以分号分隔的多方会议联系人姓名列表。</span><span class="sxs-lookup"><span data-stu-id="dea10-106">Lync 2013 can also recognize a semicolon-delimited list of contact names for multiparty conferencing.</span></span>

<span data-ttu-id="dea10-107">如果 Lync 2013 配置为在启动时自动登录，则使用命令行参数启动 Lync 2013 将打开 Lync 主窗口。</span><span class="sxs-lookup"><span data-stu-id="dea10-107">If Lync 2013 is configured to automatically sign in when started, then starting Lync 2013 with command-line parameters will open the Lync main window.</span></span> <span data-ttu-id="dea10-108">如果 Lync 没有配置为启动时自动登录，将打开登录窗口。</span><span class="sxs-lookup"><span data-stu-id="dea10-108">If Lync is not configured to automatically sign in when started, the sign-in window opens.</span></span>

<span data-ttu-id="dea10-109">下表显示了可用的参数。</span><span class="sxs-lookup"><span data-stu-id="dea10-109">The following table shows the available parameters.</span></span>

### <a name="lync-2013-command-line-parameters"></a><span data-ttu-id="dea10-110">Lync 2013 Command-Line 参数</span><span class="sxs-lookup"><span data-stu-id="dea10-110">Lync 2013 Command-Line Parameters</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dea10-111">扩展名</span><span class="sxs-lookup"><span data-stu-id="dea10-111">Extension</span></span></th>
<th><span data-ttu-id="dea10-112">数据格式</span><span class="sxs-lookup"><span data-stu-id="dea10-112">Format of Data</span></span></th>
<th><span data-ttu-id="dea10-113">操作</span><span class="sxs-lookup"><span data-stu-id="dea10-113">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dea10-114">电话</span><span class="sxs-lookup"><span data-stu-id="dea10-114">tel:</span></span></p></td>
<td><p><span data-ttu-id="dea10-115">tel URI</span><span class="sxs-lookup"><span data-stu-id="dea10-115">tel URI</span></span></p></td>
<td><p><span data-ttu-id="dea10-116">打开音频呼叫的“对话”窗口，但不拨打指定号码。</span><span class="sxs-lookup"><span data-stu-id="dea10-116">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dea10-117">callto</span><span class="sxs-lookup"><span data-stu-id="dea10-117">callto:</span></span></p></td>
<td><p><span data-ttu-id="dea10-118">tel:、sip: 或可键入的 tel URI</span><span class="sxs-lookup"><span data-stu-id="dea10-118">tel:, sip:, or typeable tel URI</span></span></p></td>
<td><p><span data-ttu-id="dea10-119">打开音频呼叫的“对话”窗口，但不拨打指定号码。</span><span class="sxs-lookup"><span data-stu-id="dea10-119">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dea10-120">sip</span><span class="sxs-lookup"><span data-stu-id="dea10-120">sip:</span></span></p></td>
<td><p><span data-ttu-id="dea10-121">SIP URI</span><span class="sxs-lookup"><span data-stu-id="dea10-121">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="dea10-122">使用参与者列表中指定的 SIP 统一资源标识符 (URI) 打开“对话”窗口。</span><span class="sxs-lookup"><span data-stu-id="dea10-122">Opens the Conversation window with the specified SIP Uniform Resource Identifier (URI) in the participant list.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dea10-123">那些</span><span class="sxs-lookup"><span data-stu-id="dea10-123">Sips:</span></span></p></td>
<td><p><span data-ttu-id="dea10-124">SIP URI</span><span class="sxs-lookup"><span data-stu-id="dea10-124">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="dea10-125">如果将 Lync 2013 配置为使用传输层安全性 (TLS) 协议，则功能与 sip 完全一样：。</span><span class="sxs-lookup"><span data-stu-id="dea10-125">If Lync 2013 is configured to use the Transport Layer Security (TLS) protocol, functions exactly like sip:.</span></span> <span data-ttu-id="dea10-126">如果没有使用 TLS，将显示一个对话框，通知用户需要更高级别的安全性。</span><span class="sxs-lookup"><span data-stu-id="dea10-126">If TLS is not being used, displays a dialog box informing the user that a higher level of security is required.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dea10-127">会议</span><span class="sxs-lookup"><span data-stu-id="dea10-127">conf:</span></span></p></td>
<td><p><span data-ttu-id="dea10-128">要加入的会议的 SIP URI</span><span class="sxs-lookup"><span data-stu-id="dea10-128">SIP URI of conference to join</span></span></p></td>
<td><p><span data-ttu-id="dea10-p104">如果 URI 是自身，则将实例化会议状态中心，并打开仅显示名单的视图。否则，将打开名单视图，但不会发送 INVITE。</span><span class="sxs-lookup"><span data-stu-id="dea10-p104">If URI is self, instantiates the focus and brings up roster-only view. Otherwise, brings up roster view but does not send INVITE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dea10-131">im</span><span class="sxs-lookup"><span data-stu-id="dea10-131">im:</span></span></p></td>
<td><p><span data-ttu-id="dea10-132">SIP URI</span><span class="sxs-lookup"><span data-stu-id="dea10-132">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="dea10-133">使用 SIP URI 打开仅显示即时消息 (IM) 的“对话”窗口。</span><span class="sxs-lookup"><span data-stu-id="dea10-133">Displays an instant messaging (IM)-only Conversation window with the SIP URI.</span></span> <span data-ttu-id="dea10-134">接受在 &lt; &gt; 不带任何分隔符的尖括号 () 中指定的多个 SIP uri。</span><span class="sxs-lookup"><span data-stu-id="dea10-134">Accepts multiple SIP URIs specified inside angle brackets (&lt;&gt;) without any separator.</span></span></p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dea10-135">下表提供了这些命令行参数的示例。</span><span class="sxs-lookup"><span data-stu-id="dea10-135">The following table provides examples of these command-line parameters.</span></span>

### <a name="command-line-parameter-examples"></a><span data-ttu-id="dea10-136">命令行参数示例</span><span class="sxs-lookup"><span data-stu-id="dea10-136">Command-Line Parameter Examples</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dea10-137">实例</span><span class="sxs-lookup"><span data-stu-id="dea10-137">Instance</span></span></th>
<th><span data-ttu-id="dea10-138">结果</span><span class="sxs-lookup"><span data-stu-id="dea10-138">Results</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dea10-139">电话： + 14255550101</span><span class="sxs-lookup"><span data-stu-id="dea10-139">Tel:+14255550101</span></span></p></td>
<td><p><span data-ttu-id="dea10-140">使用 +14255550101 打开仅显示电话的视图。</span><span class="sxs-lookup"><span data-stu-id="dea10-140">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dea10-141">Callto:tel:+ 14255550101</span><span class="sxs-lookup"><span data-stu-id="dea10-141">Callto:tel:+ 14255550101</span></span></p></td>
<td><p><span data-ttu-id="dea10-142">使用 +14255550101 打开仅显示电话的视图。</span><span class="sxs-lookup"><span data-stu-id="dea10-142">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dea10-143">Callto:sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="dea10-143">Callto:sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="dea10-144">使用 kazuto@litwareinc.com 打开仅显示电话的视图。</span><span class="sxs-lookup"><span data-stu-id="dea10-144">Opens a phone-only view with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dea10-145">sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="dea10-145">sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="dea10-146">使用 kazuto@litwareinc.com 打开“对话”窗口。</span><span class="sxs-lookup"><span data-stu-id="dea10-146">Opens a Conversation window with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dea10-147">会议： sip：https://meet.contoso.com/kazuto/7322994</span><span class="sxs-lookup"><span data-stu-id="dea10-147">conf:sip:https://meet.contoso.com/kazuto/7322994</span></span></p></td>
<td><p><span data-ttu-id="dea10-148">打开对话窗口并显示会议音频加入选项。</span><span class="sxs-lookup"><span data-stu-id="dea10-148">Opens a Conversation window and displays meeting audio join options.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

