---
title: 'Lync Server 2013: 从另一个应用程序启动 Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Starting Lync from another application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398376(v=OCS.15)
ms:contentKeyID: 48184184
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35e2d28a8083a7e7f1e693ddf55c5cfe3e758e96
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845809"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a><span data-ttu-id="b7076-102">从另一个应用程序启动 Lync</span><span class="sxs-lookup"><span data-stu-id="b7076-102">Starting Lync from another application</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7076-103">_**主题上次修改时间:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="b7076-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="b7076-104">可以使用命令行参数快速启动 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="b7076-104">You can use command-line parameters to quick-start Lync 2013.</span></span> <span data-ttu-id="b7076-105">例如, 如果用户单击另一个应用程序中的电话号码, 应用程序可以启动 Lync 2013 的一个实例, 并启动对该号码的调用。</span><span class="sxs-lookup"><span data-stu-id="b7076-105">For example, if a user clicks a phone number in another application, the application can start an instance of Lync 2013 and initiate a call to that number.</span></span>

<span data-ttu-id="b7076-106">Lync 2013 还可以识别以分号分隔的多方会议的联系人姓名列表。</span><span class="sxs-lookup"><span data-stu-id="b7076-106">Lync 2013 can also recognize a semicolon-delimited list of contact names for multiparty conferencing.</span></span>

<span data-ttu-id="b7076-107">如果 Lync 2013 配置为在启动时自动登录, 则通过命令行参数启动 Lync 2013 将打开 Lync 主窗口。</span><span class="sxs-lookup"><span data-stu-id="b7076-107">If Lync 2013 is configured to automatically sign in when started, then starting Lync 2013 with command-line parameters will open the Lync main window.</span></span> <span data-ttu-id="b7076-108">如果 Lync 未配置为在启动时自动登录, 则登录窗口将打开。</span><span class="sxs-lookup"><span data-stu-id="b7076-108">If Lync is not configured to automatically sign in when started, the sign-in window opens.</span></span>

<span data-ttu-id="b7076-109">下表显示了可用的参数。</span><span class="sxs-lookup"><span data-stu-id="b7076-109">The following table shows the available parameters.</span></span>

### <a name="lync-2013-command-line-parameters"></a><span data-ttu-id="b7076-110">Lync 2013 命令行参数</span><span class="sxs-lookup"><span data-stu-id="b7076-110">Lync 2013 Command-Line Parameters</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b7076-111">线</span><span class="sxs-lookup"><span data-stu-id="b7076-111">Extension</span></span></th>
<th><span data-ttu-id="b7076-112">数据的格式</span><span class="sxs-lookup"><span data-stu-id="b7076-112">Format of Data</span></span></th>
<th><span data-ttu-id="b7076-113">操作</span><span class="sxs-lookup"><span data-stu-id="b7076-113">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7076-114">tel</span><span class="sxs-lookup"><span data-stu-id="b7076-114">tel:</span></span></p></td>
<td><p><span data-ttu-id="b7076-115">电话 URI</span><span class="sxs-lookup"><span data-stu-id="b7076-115">tel URI</span></span></p></td>
<td><p><span data-ttu-id="b7076-116">为音频呼叫打开对话窗口, 但不拨打指定号码。</span><span class="sxs-lookup"><span data-stu-id="b7076-116">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7076-117">callto</span><span class="sxs-lookup"><span data-stu-id="b7076-117">callto:</span></span></p></td>
<td><p><span data-ttu-id="b7076-118">电话:、sip: 或 typeable 电话 URI</span><span class="sxs-lookup"><span data-stu-id="b7076-118">tel:, sip:, or typeable tel URI</span></span></p></td>
<td><p><span data-ttu-id="b7076-119">为音频呼叫打开对话窗口, 但不拨打指定号码。</span><span class="sxs-lookup"><span data-stu-id="b7076-119">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7076-120">sip</span><span class="sxs-lookup"><span data-stu-id="b7076-120">sip:</span></span></p></td>
<td><p><span data-ttu-id="b7076-121">SIP URI</span><span class="sxs-lookup"><span data-stu-id="b7076-121">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="b7076-122">在参与者列表中打开具有指定 SIP 统一资源标识符 (URI) 的对话窗口。</span><span class="sxs-lookup"><span data-stu-id="b7076-122">Opens the Conversation window with the specified SIP Uniform Resource Identifier (URI) in the participant list.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7076-123">那些</span><span class="sxs-lookup"><span data-stu-id="b7076-123">Sips:</span></span></p></td>
<td><p><span data-ttu-id="b7076-124">SIP URI</span><span class="sxs-lookup"><span data-stu-id="b7076-124">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="b7076-125">如果将 Lync 2013 配置为使用传输层安全 (TLS) 协议, 功能与 sip 完全一样:。</span><span class="sxs-lookup"><span data-stu-id="b7076-125">If Lync 2013 is configured to use the Transport Layer Security (TLS) protocol, functions exactly like sip:.</span></span> <span data-ttu-id="b7076-126">如果未使用 TLS, 则会显示一个对话框, 通知用户需要更高的安全级别。</span><span class="sxs-lookup"><span data-stu-id="b7076-126">If TLS is not being used, displays a dialog box informing the user that a higher level of security is required.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7076-127">会议</span><span class="sxs-lookup"><span data-stu-id="b7076-127">conf:</span></span></p></td>
<td><p><span data-ttu-id="b7076-128">要加入的会议的 SIP URI</span><span class="sxs-lookup"><span data-stu-id="b7076-128">SIP URI of conference to join</span></span></p></td>
<td><p><span data-ttu-id="b7076-129">如果 URI 为 self, 则实例化焦点并显示仅限名单的视图。</span><span class="sxs-lookup"><span data-stu-id="b7076-129">If URI is self, instantiates the focus and brings up roster-only view.</span></span> <span data-ttu-id="b7076-130">否则, 调出名单视图, 但不发送邀请。</span><span class="sxs-lookup"><span data-stu-id="b7076-130">Otherwise, brings up roster view but does not send INVITE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7076-131">im</span><span class="sxs-lookup"><span data-stu-id="b7076-131">im:</span></span></p></td>
<td><p><span data-ttu-id="b7076-132">SIP URI</span><span class="sxs-lookup"><span data-stu-id="b7076-132">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="b7076-133">显示带有 SIP URI 的即时消息 (IM) 对话窗口。</span><span class="sxs-lookup"><span data-stu-id="b7076-133">Displays an instant messaging (IM)-only Conversation window with the SIP URI.</span></span> <span data-ttu-id="b7076-134">接受不带任何分隔符的尖括号 (&lt;&gt;) 内指定的多个 SIP uri。</span><span class="sxs-lookup"><span data-stu-id="b7076-134">Accepts multiple SIP URIs specified inside angle brackets (&lt;&gt;) without any separator.</span></span></p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b7076-135">下表提供了这些命令行参数的示例。</span><span class="sxs-lookup"><span data-stu-id="b7076-135">The following table provides examples of these command-line parameters.</span></span>

### <a name="command-line-parameter-examples"></a><span data-ttu-id="b7076-136">命令行参数示例</span><span class="sxs-lookup"><span data-stu-id="b7076-136">Command-Line Parameter Examples</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b7076-137">示例</span><span class="sxs-lookup"><span data-stu-id="b7076-137">Instance</span></span></th>
<th><span data-ttu-id="b7076-138">结果</span><span class="sxs-lookup"><span data-stu-id="b7076-138">Results</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7076-139">电话: + 14255550101</span><span class="sxs-lookup"><span data-stu-id="b7076-139">Tel:+14255550101</span></span></p></td>
<td><p><span data-ttu-id="b7076-140">打开具有 + 14255550101 的仅手机视图。</span><span class="sxs-lookup"><span data-stu-id="b7076-140">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7076-141">Callto: 电话: + 14255550101</span><span class="sxs-lookup"><span data-stu-id="b7076-141">Callto:tel:+ 14255550101</span></span></p></td>
<td><p><span data-ttu-id="b7076-142">打开具有 + 14255550101 的仅手机视图。</span><span class="sxs-lookup"><span data-stu-id="b7076-142">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7076-143">Callto:sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b7076-143">Callto:sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="b7076-144">打开一个仅限手机的视图, kazuto@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="b7076-144">Opens a phone-only view with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7076-145">sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b7076-145">sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="b7076-146">打开一个带 kazuto@litwareinc.com 的对话窗口。</span><span class="sxs-lookup"><span data-stu-id="b7076-146">Opens a Conversation window with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7076-147">会议: sip:https://meet.contoso.com/kazuto/7322994</span><span class="sxs-lookup"><span data-stu-id="b7076-147">conf:sip:https://meet.contoso.com/kazuto/7322994</span></span></p></td>
<td><p><span data-ttu-id="b7076-148">打开对话窗口, 并显示会议音频联接选项。</span><span class="sxs-lookup"><span data-stu-id="b7076-148">Opens a Conversation window and displays meeting audio join options.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

