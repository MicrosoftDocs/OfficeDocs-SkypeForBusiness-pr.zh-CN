---
title: Lync Server 2013：安装适用于 Windows Phone 的 Lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync for Windows Phone
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690996(v=OCS.15)
ms:contentKeyID: 51541513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 349a4b2609f3b810d0aa64c9e71786f309f21918
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045284"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a><span data-ttu-id="54a9a-102">在 Lync Server 2013 中安装适用于 Windows Phone 的 Lync</span><span class="sxs-lookup"><span data-stu-id="54a9a-102">Installing Lync for Windows Phone in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54a9a-103">_**上次修改的主题：** 2014-02-03_</span><span class="sxs-lookup"><span data-stu-id="54a9a-103">_**Topic Last Modified:** 2014-02-03_</span></span>

<span data-ttu-id="54a9a-104">适用于 Windows phone 的 Lync 2013 是可在 Windows Phone 市场中使用的用户可安装的应用程序。</span><span class="sxs-lookup"><span data-stu-id="54a9a-104">Lync 2013 for Windows Phone is a user-installable application that is available in the Windows Phone Marketplace.</span></span>

<div>

## <a name="installing-lync-for-windows-mobile"></a><span data-ttu-id="54a9a-105">安装 Lync for Windows Mobile</span><span class="sxs-lookup"><span data-stu-id="54a9a-105">Installing Lync for Windows Mobile</span></span>

<span data-ttu-id="54a9a-106">您可以指示用户通过将 Lync 2013 for Windows Phone 安装在其设备上，具体方法是将其定向到<http://go.microsoft.com/fwlink/p/?linkid=231901>Windows phone Marketplace。</span><span class="sxs-lookup"><span data-stu-id="54a9a-106">You can instruct your users to install Lync 2013 for Windows Phone on their devices by directing them to the Windows Phone Marketplace at <http://go.microsoft.com/fwlink/p/?linkid=231901>.</span></span>

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a><span data-ttu-id="54a9a-107">如果使用 DNS SRV 记录发布 Exchange Web 服务</span><span class="sxs-lookup"><span data-stu-id="54a9a-107">If You Use a DNS SRV Record to Publish Exchange Web Services</span></span>

<span data-ttu-id="54a9a-108">若要为 Lync 客户端启用 Exchange 集成，某些组织会使用 DNS SRV 记录发布 Exchange Web 服务 URL。</span><span class="sxs-lookup"><span data-stu-id="54a9a-108">To enable Exchange integration for Lync clients, some organizations publish the Exchange Web Services URL by using a DNS SRV record.</span></span> <span data-ttu-id="54a9a-109">Microsoft 下载中心[http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095)中的 "了解和疑难解答 Exchange 集成" 文档介绍了可能需要此功能的情况。</span><span class="sxs-lookup"><span data-stu-id="54a9a-109">The document "Understanding and Troubleshooting Exchange Integration," available in the Microsoft Download Center at [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095), describes scenarios in which this might be necessary.</span></span> <span data-ttu-id="54a9a-110">但是，由于 Windows Phone 平台不支持 SRV 查找，因此 Windows Phone 用户的 Exchange 集成将无法在这种情况下运行。</span><span class="sxs-lookup"><span data-stu-id="54a9a-110">However, Exchange integration for Windows Phone users will not work in this scenario, because the Windows Phone platform does not support SRV lookups.</span></span> <span data-ttu-id="54a9a-111">你将需要指示 Windows Phone 用户指定 Exchange Web 服务 URL，而不是允许电话自动检测服务器。</span><span class="sxs-lookup"><span data-stu-id="54a9a-111">You will need to instruct Windows Phone users to specify the Exchange Web Services URL instead of allowing the phone to automatically detect the server.</span></span>

<span data-ttu-id="54a9a-112">指导用户在其 Windows phone 上配置 Lync 设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="54a9a-112">Instruct your users to configure the Lync settings on their Windows Phones as follows:</span></span>

1.  <span data-ttu-id="54a9a-113">在 Windows Phone 中，在 "Lync 设置" 中，选择 " **Exchange** " 屏幕。</span><span class="sxs-lookup"><span data-stu-id="54a9a-113">In Windows Phone, in the Lync settings, select the **Exchange** screen.</span></span>

2.  <span data-ttu-id="54a9a-114">将**自动检测服务器**移动到**关闭状态**。</span><span class="sxs-lookup"><span data-stu-id="54a9a-114">Move **Auto-Detect Server** to **Off**.</span></span>

3.  <span data-ttu-id="54a9a-115">点击空字段并输入 Exchange Web 服务的完全限定的域名（FQDN）或 URL。</span><span class="sxs-lookup"><span data-stu-id="54a9a-115">Tap the empty field and enter the fully qualified domain name (FQDN) or URL for Exchange Web Services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54a9a-116">您可以指定 Exchange Web 服务服务器的完全限定域名（FQDN）或完整 URL。</span><span class="sxs-lookup"><span data-stu-id="54a9a-116">You can specify either the fully qualified domain name (FQDN) or the full URL of your Exchange Web Services server.</span></span> <span data-ttu-id="54a9a-117">如果指定 FQDN，则将自动添加协议（https://）和 Exchange Web 服务路径（/ews/exchange.asmx）。</span><span class="sxs-lookup"><span data-stu-id="54a9a-117">If you specify the FQDN, the protocol (https://) and the Exchange Web Services path (/ews/exchange.asmx) are added automatically.</span></span> <span data-ttu-id="54a9a-118">如果您的 Exchange Web 服务路径不同，您可以指定完整的 URL。</span><span class="sxs-lookup"><span data-stu-id="54a9a-118">If your Exchange Web Services path is different, you can specify the full URL.</span></span>

    
    </div>

4.  <span data-ttu-id="54a9a-119">关闭屏幕。</span><span class="sxs-lookup"><span data-stu-id="54a9a-119">Close the screen.</span></span>

</div>

<div>

## <a name="verifying-mobile-client-installation"></a><span data-ttu-id="54a9a-120">验证移动客户端安装</span><span class="sxs-lookup"><span data-stu-id="54a9a-120">Verifying Mobile Client Installation</span></span>

<span data-ttu-id="54a9a-121">配置客户端并成功登录后，请使用以下测试来验证您的 Lync 2013 安装是否在移动设备上正常运行。</span><span class="sxs-lookup"><span data-stu-id="54a9a-121">After you configure the client and sign in successfully, use the following tests to verify that your installation of Lync 2013 is working correctly on your mobile device.</span></span>

<span data-ttu-id="54a9a-122">**搜索企业目录中的联系人**</span><span class="sxs-lookup"><span data-stu-id="54a9a-122">**Search for a contact in the corporate directory**</span></span>

1.  <span data-ttu-id="54a9a-123">在“联系人”列表中，点击底部的“搜索”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="54a9a-123">In the Contacts list, tap **Search** at the bottom.</span></span>

2.  <span data-ttu-id="54a9a-124">搜索仅存在于全局地址列表中的联系人。</span><span class="sxs-lookup"><span data-stu-id="54a9a-124">Search for a contact that exists only in the global address list.</span></span>

3.  <span data-ttu-id="54a9a-125">确认联系人姓名出现在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="54a9a-125">Verify that the contact name appears in the search results.</span></span>

<span data-ttu-id="54a9a-126">**测试即时消息和状态**</span><span class="sxs-lookup"><span data-stu-id="54a9a-126">**Test instant messaging and presence**</span></span>

1.  <span data-ttu-id="54a9a-127">在“联系人”列表中，点击一个联系人。</span><span class="sxs-lookup"><span data-stu-id="54a9a-127">In the Contacts list, tap a contact.</span></span>

2.  <span data-ttu-id="54a9a-128">在联系人卡片中，点击“IM”\*\*\*\* 图标。</span><span class="sxs-lookup"><span data-stu-id="54a9a-128">In the contact card, tap the **IM** icon.</span></span>

3.  <span data-ttu-id="54a9a-129">验证即时消息（IM）窗口是否出现，以及您是否可以键入并发送即时消息。</span><span class="sxs-lookup"><span data-stu-id="54a9a-129">Verify that an instant messaging (IM) window appears and that you can type and send an IM.</span></span>

<span data-ttu-id="54a9a-130">**测试电话拨出式会议**</span><span class="sxs-lookup"><span data-stu-id="54a9a-130">**Test dial-out conferencing**</span></span>

1.  <span data-ttu-id="54a9a-131">在 Outlook 中安排 Lync 会议。</span><span class="sxs-lookup"><span data-stu-id="54a9a-131">In Outlook, schedule a Lync meeting.</span></span>

2.  <span data-ttu-id="54a9a-132">在移动设备上，打开会议邀请。</span><span class="sxs-lookup"><span data-stu-id="54a9a-132">On the mobile device, open the meeting invitation.</span></span>

3.  <span data-ttu-id="54a9a-133">单击会议中的链接以加入会议。</span><span class="sxs-lookup"><span data-stu-id="54a9a-133">Click the link in the meeting to join.</span></span>

4.  <span data-ttu-id="54a9a-134">应答来自会议服务的呼叫，并确认您已连接到会议音频。</span><span class="sxs-lookup"><span data-stu-id="54a9a-134">Answer the call from the conference service and verify that you are connected to meeting audio.</span></span>

<span data-ttu-id="54a9a-135">**测试推送通知**</span><span class="sxs-lookup"><span data-stu-id="54a9a-135">**Test push notifications**</span></span>

1.  <span data-ttu-id="54a9a-136">在用户 A 的移动设备上，使用用户 A 的帐户登录 Lync。</span><span class="sxs-lookup"><span data-stu-id="54a9a-136">On user A’s mobile device, sign in to Lync with user A’s account.</span></span>

2.  <span data-ttu-id="54a9a-137">在移动设备上打开其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="54a9a-137">Open another application on the mobile device.</span></span>

3.  <span data-ttu-id="54a9a-138">在其他客户端上，使用用户 B 的帐户登录 Lync。</span><span class="sxs-lookup"><span data-stu-id="54a9a-138">On a different client, sign in to Lync with user B’s account.</span></span>

4.  <span data-ttu-id="54a9a-139">将 IM 从用户 B 发送到用户 A。</span><span class="sxs-lookup"><span data-stu-id="54a9a-139">Send an IM from user B to user A.</span></span>

5.  <span data-ttu-id="54a9a-140">确保用户 A 的移动设备上显示 IM 通知。</span><span class="sxs-lookup"><span data-stu-id="54a9a-140">Verify that the IM notification appears on user A’s mobile device.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

