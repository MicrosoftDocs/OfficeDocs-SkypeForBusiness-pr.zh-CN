---
title: Lync Server 2013：设置 Lync-Skype 连接指南
description: Lync Server 2013：设置 Lync-Skype 连接的指南。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Provisioning guide for Lync-Skype connectivity
ms:assetid: 69adda9b-5b72-4538-9be6-079b2f462e09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440173(v=OCS.15)
ms:contentKeyID: 57793363
ms.date: 11/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9859a7a621ba4329fe0436fe50a0d9de1d0ae1ef
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569088"
---
# <a name="provisioning-guide-for-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="821dd-103">Lync Server 2013 中 Lync-Skype 连接的预配指南</span><span class="sxs-lookup"><span data-stu-id="821dd-103">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="821dd-104">_**上次修改的主题：** 2014-11-26_</span><span class="sxs-lookup"><span data-stu-id="821dd-104">_**Topic Last Modified:** 2014-11-26_</span></span>

<span data-ttu-id="821dd-105">Lync Server 2013 支持与 Skype 的连接。</span><span class="sxs-lookup"><span data-stu-id="821dd-105">Lync Server 2013 supports connectivity with Skype.</span></span> <span data-ttu-id="821dd-106">通过此连接，你的 Lync 2013 用户可以使用 Skype 用户的 Microsoft 帐户 (MSA) 添加 Skype 联系人。</span><span class="sxs-lookup"><span data-stu-id="821dd-106">This connectivity enables your Lync 2013 users to add Skype contacts by using the Skype user’s Microsoft Account (MSA).</span></span> <span data-ttu-id="821dd-107">Skype 客户端也可以将 Lync 用户添加到其联系人列表中。</span><span class="sxs-lookup"><span data-stu-id="821dd-107">Skype clients can also add Lync users to their contact list.</span></span> <span data-ttu-id="821dd-108">根据 Lync Server 中管理员设置的策略，Lync 和 Skype 用户将能够使用即时消息进行通信、查看彼此的状态以及启动音频和视频呼叫。</span><span class="sxs-lookup"><span data-stu-id="821dd-108">Based on policies administratively set in Lync Server, Lync and Skype users will be able to communicate using instant messaging, see each other’s presence, and initiate audio and video calls.</span></span> <span data-ttu-id="821dd-109">Lync-Skype 连接也是 Lync Online 的一项功能，并且可以在 Microsoft 365 管理中心内的 Lync 管理中心中为 Lync Online 客户启用此功能。</span><span class="sxs-lookup"><span data-stu-id="821dd-109">Lync-Skype connectivity is also a feature of Lync Online, and can be enabled for Lync Online customers from the Lync Administration Center within the Microsoft 365 admin center.</span></span>

<div>

> [!IMPORTANT]  
> <span data-ttu-id="821dd-110">如果已将 Lync Server 配置为通过使用公共即时消息连接 (PIC) 来连接 Windows Messenger，则您的部署已配置为 Lync-Skype 连接性。</span><span class="sxs-lookup"><span data-stu-id="821dd-110">If Lync Server is already configured to connect with Windows Messenger by using Public Instant Messaging Connectivity (PIC), your deployment is already configured for Lync-Skype connectivity.</span></span> <span data-ttu-id="821dd-111">您可能需要考虑的唯一更改是将现有的 Messenger PIC 条目重命名为 Skype。</span><span class="sxs-lookup"><span data-stu-id="821dd-111">The only change you may want to consider is to rename your existing Messenger PIC entry as Skype.</span></span> <span data-ttu-id="821dd-112">有关详细信息，请参阅本指南后面的为 Lync 配置 Skype PIC 提供程序设置。</span><span class="sxs-lookup"><span data-stu-id="821dd-112">For details, see Configure the Skype PIC provider setting for Lync later in this guide.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="821dd-113">本部分内容</span><span class="sxs-lookup"><span data-stu-id="821dd-113">In This Section</span></span>

  - [<span data-ttu-id="821dd-114">有关 Lync Online 客户在 Lync Server 2013 中 Lync-Skype 连接的说明</span><span class="sxs-lookup"><span data-stu-id="821dd-114">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>](lync-server-2013-note-about-lync-skype-connectivity-for-lync-on.md)

  - [<span data-ttu-id="821dd-115">从 Lync Server 2013 访问 Lync Server 公共 IM 连接设置网站</span><span class="sxs-lookup"><span data-stu-id="821dd-115">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>](lync-server-2013-accessing-the-lync-server-public-im-connectivity-provisioning-site.md)

  - [<span data-ttu-id="821dd-116">在 Lync Server 2013 中启用 Lync-Skype 连接</span><span class="sxs-lookup"><span data-stu-id="821dd-116">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-enabling-lync-skype-connectivity.md)

  - [<span data-ttu-id="821dd-117">在 Lync Server 2013 中使用 Lync-Skype 连接作为最终用户</span><span class="sxs-lookup"><span data-stu-id="821dd-117">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

  - [<span data-ttu-id="821dd-118">常见问题：设置适用于 Skype 连接的 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="821dd-118">Frequently Asked Questions: Provisioning Lync Server 2013 for Skype connectivity</span></span>](lync-server-2013-frequently-asked-questions-provisioning-lync-server-for-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

