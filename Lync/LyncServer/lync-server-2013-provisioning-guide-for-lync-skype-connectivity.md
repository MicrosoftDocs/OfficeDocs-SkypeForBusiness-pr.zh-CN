---
title: Lync Server 2013： Lync 的预配指南-Skype 连接
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
ms.openlocfilehash: e8f6e1b9262e0e7ed0f9060f3e509924aee9ba62
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="provisioning-guide-for-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="2dec9-102">Lync Server 2013 中的 Lync-Skype 连接的预配指南</span><span class="sxs-lookup"><span data-stu-id="2dec9-102">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2dec9-103">_**上次修改的主题：** 2014-11-26_</span><span class="sxs-lookup"><span data-stu-id="2dec9-103">_**Topic Last Modified:** 2014-11-26_</span></span>

<span data-ttu-id="2dec9-104">Lync Server 2013 支持与 Skype 的连接。</span><span class="sxs-lookup"><span data-stu-id="2dec9-104">Lync Server 2013 supports connectivity with Skype.</span></span> <span data-ttu-id="2dec9-105">此连接使 Lync 2013 用户能够通过使用 Skype 用户的 Microsoft 帐户（MSA）添加 Skype 联系人。</span><span class="sxs-lookup"><span data-stu-id="2dec9-105">This connectivity enables your Lync 2013 users to add Skype contacts by using the Skype user’s Microsoft Account (MSA).</span></span> <span data-ttu-id="2dec9-106">Skype 客户端也可以将 Lync 用户添加到其联系人列表中。</span><span class="sxs-lookup"><span data-stu-id="2dec9-106">Skype clients can also add Lync users to their contact list.</span></span> <span data-ttu-id="2dec9-107">根据 Lync Server 中管理员设置的策略，Lync 和 Skype 用户将能够使用即时消息进行通信、查看彼此的状态以及启动音频和视频呼叫。</span><span class="sxs-lookup"><span data-stu-id="2dec9-107">Based on policies administratively set in Lync Server, Lync and Skype users will be able to communicate using instant messaging, see each other’s presence, and initiate audio and video calls.</span></span> <span data-ttu-id="2dec9-108">Lync-Skype 连接也是 Lync Online 的一项功能，可以在 Office 365 门户内的 Lync 管理中心中为 Lync Online 客户启用此功能。</span><span class="sxs-lookup"><span data-stu-id="2dec9-108">Lync-Skype connectivity is also a feature of Lync Online, and can be enabled for Lync Online customers from the Lync Administration Center within the Office 365 portal.</span></span>

<div>

> [!IMPORTANT]  
> <span data-ttu-id="2dec9-109">如果已使用公共即时消息连接（PIC）将 Lync Server 配置为使用 Windows Messenger 进行连接，则您的部署已配置为使用 Lync-Skype 连接。</span><span class="sxs-lookup"><span data-stu-id="2dec9-109">If Lync Server is already configured to connect with Windows Messenger by using Public Instant Messaging Connectivity (PIC), your deployment is already configured for Lync-Skype connectivity.</span></span> <span data-ttu-id="2dec9-110">您可能需要考虑的唯一更改是将现有的 Messenger PIC 条目重命名为 Skype。</span><span class="sxs-lookup"><span data-stu-id="2dec9-110">The only change you may want to consider is to rename your existing Messenger PIC entry as Skype.</span></span> <span data-ttu-id="2dec9-111">有关详细信息，请参阅本指南后面的为 Lync 配置 Skype PIC 提供程序设置。</span><span class="sxs-lookup"><span data-stu-id="2dec9-111">For details, see Configure the Skype PIC provider setting for Lync later in this guide.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2dec9-112">本部分内容</span><span class="sxs-lookup"><span data-stu-id="2dec9-112">In This Section</span></span>

  - [<span data-ttu-id="2dec9-113">有关 lync Online 客户的 Lync Server 2013 中的 Lync-Skype 连接说明</span><span class="sxs-lookup"><span data-stu-id="2dec9-113">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>](lync-server-2013-note-about-lync-skype-connectivity-for-lync-on.md)

  - [<span data-ttu-id="2dec9-114">从 Lync Server 2013 访问 Lync Server 公共 IM 连接设置网站</span><span class="sxs-lookup"><span data-stu-id="2dec9-114">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>](lync-server-2013-accessing-the-lync-server-public-im-connectivity-provisioning-site.md)

  - [<span data-ttu-id="2dec9-115">在 Lync Server 2013 中启用 Lync Skype 连接</span><span class="sxs-lookup"><span data-stu-id="2dec9-115">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-enabling-lync-skype-connectivity.md)

  - [<span data-ttu-id="2dec9-116">在 Lync Server 2013 中使用 Lync Skype 连接作为最终用户</span><span class="sxs-lookup"><span data-stu-id="2dec9-116">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

  - [<span data-ttu-id="2dec9-117">常见问题：设置适用于 Skype 连接的 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2dec9-117">Frequently Asked Questions: Provisioning Lync Server 2013 for Skype connectivity</span></span>](lync-server-2013-frequently-asked-questions-provisioning-lync-server-for-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

