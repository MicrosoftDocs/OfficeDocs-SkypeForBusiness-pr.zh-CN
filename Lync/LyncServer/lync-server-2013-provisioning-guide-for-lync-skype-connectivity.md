---
title: Lync Server 2013：Lync-Skype 连接设置指南
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Provisioning guide for Lync-Skype connectivity
ms:assetid: 69adda9b-5b72-4538-9be6-079b2f462e09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440173(v=OCS.15)
ms:contentKeyID: 57793363
ms.date: 11/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f595916502a7c7ec27ff220a7b3f138b41e6fc2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="provisioning-guide-for-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="73029-102">Lync Server 2013 中的 Lync-Skype 连接设置指南</span><span class="sxs-lookup"><span data-stu-id="73029-102">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73029-103">_**主题上次修改时间:** 2014-11-26_</span><span class="sxs-lookup"><span data-stu-id="73029-103">_**Topic Last Modified:** 2014-11-26_</span></span>

<span data-ttu-id="73029-p101">Lync Server 2013 支持与 Skype 进行连接。此连接使 Lync 2013 用户能够使用 Skype 用户的 Microsoft 帐户 (MSA) 添加 Skype 联系人。Skype 客户端也可以将 Lync 用户添加到其联系人列表。根据 Lync Server 中以管理方式设置的策略，Lync 和 Skype 用户将能够使用即时消息进行通信、查看彼此的状态和启动音频和视频呼叫。Lync-Skype 连接也是 Lync Online 的一项功能，可以从 Office 365 门户中的 Lync 管理中心为 Lync Online 客户启用。</span><span class="sxs-lookup"><span data-stu-id="73029-p101">Lync Server 2013 supports connectivity with Skype. This connectivity enables your Lync 2013 users to add Skype contacts by using the Skype user’s Microsoft Account (MSA). Skype clients can also add Lync users to their contact list. Based on policies administratively set in Lync Server, Lync and Skype users will be able to communicate using instant messaging, see each other’s presence, and initiate audio and video calls. Lync-Skype connectivity is also a feature of Lync Online, and can be enabled for Lync Online customers from the Lync Administration Center within the Office 365 portal.</span></span>

<div>

> [!IMPORTANT]  
> <span data-ttu-id="73029-p102">如果 Lync Server 已配置为使用公共即时消息连接 (PIC) 与 Windows Messenger 进行连接，则您的部署已配置 Lync-Skype 连接。您可能需要考虑的唯一更改是将现有 Messenger PIC 条目重命名为 Skype。有关详细信息，请参阅本指南后面的“针对 Lync 配置 Skype PIC 提供程序设置”。</span><span class="sxs-lookup"><span data-stu-id="73029-p102">If Lync Server is already configured to connect with Windows Messenger by using Public Instant Messaging Connectivity (PIC), your deployment is already configured for Lync-Skype connectivity. The only change you may want to consider is to rename your existing Messenger PIC entry as Skype. For details, see Configure the Skype PIC provider setting for Lync later in this guide.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="73029-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="73029-112">In This Section</span></span>

  - [<span data-ttu-id="73029-113">关于 lync-lync Server 2013 for Lync Online 客户的 Skype 连接说明</span><span class="sxs-lookup"><span data-stu-id="73029-113">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>](lync-server-2013-note-about-lync-skype-connectivity-for-lync-on.md)

  - [<span data-ttu-id="73029-114">从 Lync Server 2013 访问 Lync Server 公共 IM 连接设置站点</span><span class="sxs-lookup"><span data-stu-id="73029-114">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>](lync-server-2013-accessing-the-lync-server-public-im-connectivity-provisioning-site.md)

  - [<span data-ttu-id="73029-115">在 Lync Server 2013 中启用 Lync-Skype 连接</span><span class="sxs-lookup"><span data-stu-id="73029-115">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-enabling-lync-skype-connectivity.md)

  - [<span data-ttu-id="73029-116">在 Lync Server 2013 中使用 Lync-Skype 连接作为最终用户</span><span class="sxs-lookup"><span data-stu-id="73029-116">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

  - [<span data-ttu-id="73029-117">常见问题：为 Lync Server 2013 设置 Skype 连接</span><span class="sxs-lookup"><span data-stu-id="73029-117">Frequently Asked Questions: Provisioning Lync Server 2013 for Skype connectivity</span></span>](lync-server-2013-frequently-asked-questions-provisioning-lync-server-for-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

