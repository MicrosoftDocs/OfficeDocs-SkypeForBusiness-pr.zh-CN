---
title: Lync Server 2013：安装适用于 Windows Phone 的 Lync
description: Lync Server 2013：安装适用于 Windows Phone 的 Lync。
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
ms.openlocfilehash: 6f5da90a5dc0babdc6944e4f9c426fe896d4f156
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573978"
---
# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a><span data-ttu-id="03c37-103">在 Lync Server 2013 中安装适用于 Windows Phone 的 Lync</span><span class="sxs-lookup"><span data-stu-id="03c37-103">Installing Lync for Windows Phone in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03c37-104">_**上次修改的主题：** 2014-02-03_</span><span class="sxs-lookup"><span data-stu-id="03c37-104">_**Topic Last Modified:** 2014-02-03_</span></span>

<span data-ttu-id="03c37-105">适用于 Windows phone 的 Lync 2013 是可在 Windows Phone 市场中使用的用户可安装的应用程序。</span><span class="sxs-lookup"><span data-stu-id="03c37-105">Lync 2013 for Windows Phone is a user-installable application that is available in the Windows Phone Marketplace.</span></span>

<div>

## <a name="installing-lync-for-windows-mobile"></a><span data-ttu-id="03c37-106">安装 Lync for Windows Mobile</span><span class="sxs-lookup"><span data-stu-id="03c37-106">Installing Lync for Windows Mobile</span></span>

<span data-ttu-id="03c37-107">您可以指示用户通过将 Lync 2013 for Windows Phone 安装在其设备上，具体方法是将其定向到 Windows Phone Marketplace <https://go.microsoft.com/fwlink/p/?linkid=231901> 。</span><span class="sxs-lookup"><span data-stu-id="03c37-107">You can instruct your users to install Lync 2013 for Windows Phone on their devices by directing them to the Windows Phone Marketplace at <https://go.microsoft.com/fwlink/p/?linkid=231901>.</span></span>

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a><span data-ttu-id="03c37-108">如果使用 DNS SRV 记录发布 Exchange Web 服务</span><span class="sxs-lookup"><span data-stu-id="03c37-108">If You Use a DNS SRV Record to Publish Exchange Web Services</span></span>

<span data-ttu-id="03c37-109">若要为 Lync 客户端启用 Exchange 集成，某些组织会使用 DNS SRV 记录发布 Exchange Web 服务 URL。</span><span class="sxs-lookup"><span data-stu-id="03c37-109">To enable Exchange integration for Lync clients, some organizations publish the Exchange Web Services URL by using a DNS SRV record.</span></span> <span data-ttu-id="03c37-110">Microsoft 下载中心中的 "了解和疑难解答 Exchange 集成" 文档 [https://go.microsoft.com/fwlink/?LinkID=391095](https://go.microsoft.com/fwlink/?linkid=391095) 介绍了可能需要此功能的情况。</span><span class="sxs-lookup"><span data-stu-id="03c37-110">The document "Understanding and Troubleshooting Exchange Integration," available in the Microsoft Download Center at [https://go.microsoft.com/fwlink/?LinkID=391095](https://go.microsoft.com/fwlink/?linkid=391095), describes scenarios in which this might be necessary.</span></span> <span data-ttu-id="03c37-111">但是，由于 Windows Phone 平台不支持 SRV 查找，因此 Windows Phone 用户的 Exchange 集成将无法在这种情况下运行。</span><span class="sxs-lookup"><span data-stu-id="03c37-111">However, Exchange integration for Windows Phone users will not work in this scenario, because the Windows Phone platform does not support SRV lookups.</span></span> <span data-ttu-id="03c37-112">你将需要指示 Windows Phone 用户指定 Exchange Web 服务 URL，而不是允许电话自动检测服务器。</span><span class="sxs-lookup"><span data-stu-id="03c37-112">You will need to instruct Windows Phone users to specify the Exchange Web Services URL instead of allowing the phone to automatically detect the server.</span></span>

<span data-ttu-id="03c37-113">指导用户在其 Windows phone 上配置 Lync 设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="03c37-113">Instruct your users to configure the Lync settings on their Windows Phones as follows:</span></span>

1.  <span data-ttu-id="03c37-114">在 Windows Phone 中，在 "Lync 设置" 中，选择 " **Exchange** " 屏幕。</span><span class="sxs-lookup"><span data-stu-id="03c37-114">In Windows Phone, in the Lync settings, select the **Exchange** screen.</span></span>

2.  <span data-ttu-id="03c37-115">将 **自动检测服务器** 移动到 **关闭状态**。</span><span class="sxs-lookup"><span data-stu-id="03c37-115">Move **Auto-Detect Server** to **Off**.</span></span>

3.  <span data-ttu-id="03c37-116">点击 "空" 字段，并输入 Exchange Web 服务 (FQDN) 或 URL 的完全限定的域名称。</span><span class="sxs-lookup"><span data-stu-id="03c37-116">Tap the empty field and enter the fully qualified domain name (FQDN) or URL for Exchange Web Services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="03c37-117">您可以指定完全限定的域名 (FQDN) 或 Exchange Web 服务服务器的完整 URL。</span><span class="sxs-lookup"><span data-stu-id="03c37-117">You can specify either the fully qualified domain name (FQDN) or the full URL of your Exchange Web Services server.</span></span> <span data-ttu-id="03c37-118">如果指定 FQDN，协议 (https://) 和 Exchange Web 服务路径 (/ews/exchange.asmx) 将自动添加。</span><span class="sxs-lookup"><span data-stu-id="03c37-118">If you specify the FQDN, the protocol (https://) and the Exchange Web Services path (/ews/exchange.asmx) are added automatically.</span></span> <span data-ttu-id="03c37-119">如果您的 Exchange Web 服务路径不同，您可以指定完整的 URL。</span><span class="sxs-lookup"><span data-stu-id="03c37-119">If your Exchange Web Services path is different, you can specify the full URL.</span></span>

    
    </div>

4.  <span data-ttu-id="03c37-120">关闭屏幕。</span><span class="sxs-lookup"><span data-stu-id="03c37-120">Close the screen.</span></span>

</div>

<div>

## <a name="verifying-mobile-client-installation"></a><span data-ttu-id="03c37-121">验证移动客户端安装</span><span class="sxs-lookup"><span data-stu-id="03c37-121">Verifying Mobile Client Installation</span></span>

<span data-ttu-id="03c37-122">配置客户端并成功登录后，请使用以下测试来验证您的 Lync 2013 安装是否在移动设备上正常运行。</span><span class="sxs-lookup"><span data-stu-id="03c37-122">After you configure the client and sign in successfully, use the following tests to verify that your installation of Lync 2013 is working correctly on your mobile device.</span></span>

<span data-ttu-id="03c37-123">**搜索企业目录中的联系人**</span><span class="sxs-lookup"><span data-stu-id="03c37-123">**Search for a contact in the corporate directory**</span></span>

1.  <span data-ttu-id="03c37-124">在“联系人”列表中，点击底部的“搜索”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="03c37-124">In the Contacts list, tap **Search** at the bottom.</span></span>

2.  <span data-ttu-id="03c37-125">搜索仅存在于全局地址列表中的联系人。</span><span class="sxs-lookup"><span data-stu-id="03c37-125">Search for a contact that exists only in the global address list.</span></span>

3.  <span data-ttu-id="03c37-126">确认联系人姓名出现在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="03c37-126">Verify that the contact name appears in the search results.</span></span>

<span data-ttu-id="03c37-127">**测试即时消息和状态**</span><span class="sxs-lookup"><span data-stu-id="03c37-127">**Test instant messaging and presence**</span></span>

1.  <span data-ttu-id="03c37-128">在“联系人”列表中，点击一个联系人。</span><span class="sxs-lookup"><span data-stu-id="03c37-128">In the Contacts list, tap a contact.</span></span>

2.  <span data-ttu-id="03c37-129">在联系人卡片中，点击“IM”\*\*\*\* 图标。</span><span class="sxs-lookup"><span data-stu-id="03c37-129">In the contact card, tap the **IM** icon.</span></span>

3.  <span data-ttu-id="03c37-130">验证即时消息 (IM) 窗口是否显示，以及是否可以键入和发送即时消息。</span><span class="sxs-lookup"><span data-stu-id="03c37-130">Verify that an instant messaging (IM) window appears and that you can type and send an IM.</span></span>

<span data-ttu-id="03c37-131">**测试电话拨出式会议**</span><span class="sxs-lookup"><span data-stu-id="03c37-131">**Test dial-out conferencing**</span></span>

1.  <span data-ttu-id="03c37-132">在 Outlook 中安排 Lync 会议。</span><span class="sxs-lookup"><span data-stu-id="03c37-132">In Outlook, schedule a Lync meeting.</span></span>

2.  <span data-ttu-id="03c37-133">在移动设备上，打开会议邀请。</span><span class="sxs-lookup"><span data-stu-id="03c37-133">On the mobile device, open the meeting invitation.</span></span>

3.  <span data-ttu-id="03c37-134">单击会议中的链接以加入会议。</span><span class="sxs-lookup"><span data-stu-id="03c37-134">Click the link in the meeting to join.</span></span>

4.  <span data-ttu-id="03c37-135">应答来自会议服务的呼叫，并确认您已连接到会议音频。</span><span class="sxs-lookup"><span data-stu-id="03c37-135">Answer the call from the conference service and verify that you are connected to meeting audio.</span></span>

<span data-ttu-id="03c37-136">**测试推送通知**</span><span class="sxs-lookup"><span data-stu-id="03c37-136">**Test push notifications**</span></span>

1.  <span data-ttu-id="03c37-137">在用户 A 的移动设备上，使用用户 A 的帐户登录 Lync。</span><span class="sxs-lookup"><span data-stu-id="03c37-137">On user A’s mobile device, sign in to Lync with user A’s account.</span></span>

2.  <span data-ttu-id="03c37-138">在移动设备上打开其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="03c37-138">Open another application on the mobile device.</span></span>

3.  <span data-ttu-id="03c37-139">在其他客户端上，使用用户 B 的帐户登录 Lync。</span><span class="sxs-lookup"><span data-stu-id="03c37-139">On a different client, sign in to Lync with user B’s account.</span></span>

4.  <span data-ttu-id="03c37-140">将 IM 从用户 B 发送到用户 A。</span><span class="sxs-lookup"><span data-stu-id="03c37-140">Send an IM from user B to user A.</span></span>

5.  <span data-ttu-id="03c37-141">确保用户 A 的移动设备上显示 IM 通知。</span><span class="sxs-lookup"><span data-stu-id="03c37-141">Verify that the IM notification appears on user A’s mobile device.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

