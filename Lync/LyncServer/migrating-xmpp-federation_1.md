---
title: 管理 XMPP 联盟
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49733692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e446a4981a3b9b255311ff5720e2c6dc36d61e9a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a><span data-ttu-id="5e1ec-102">管理 XMPP 联盟</span><span class="sxs-lookup"><span data-stu-id="5e1ec-102">Migrating XMPP federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e1ec-103">_**上次修改的主题：** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="5e1ec-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="5e1ec-104">早期版本的 Office 通信服务器提供了可扩展消息和状态协议（XMPP）网关，可将其作为单独的服务器角色进行部署，以允许与 XMPP 部署进行联盟。</span><span class="sxs-lookup"><span data-stu-id="5e1ec-104">Previous versions of Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="5e1ec-105">在 Lync Server 2013 中，可以将 XMPP 功能部署为功能。</span><span class="sxs-lookup"><span data-stu-id="5e1ec-105">In Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="5e1ec-106">XMPP 功能安装在两个部分中：作为运行在 Lync Server 2013 边缘服务器上的 XMPP 代理，以及在 Lync Server 2013 前端服务器上运行的 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="5e1ec-106">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the Lync Server 2013 Edge Server, and the XMPP Gateway that runs on the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="5e1ec-107">从迁移的角度来看，可以将 Office 通信服务器 2007 R2 用户帐户移动到 Lync Server 2013 池，并继续使用 Office 通信服务器 2007 R2 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="5e1ec-107">From a migration perspective, a Office Communications Server 2007 R2 user account can be moved to a Lync Server 2013 pool and continue to use the Office Communications Server 2007 R2 XMPP gateway.</span></span> <span data-ttu-id="5e1ec-108">仅当未在 Lync Server 2013 中配置 XMPP 联盟伙伴时，才可以这样做。</span><span class="sxs-lookup"><span data-stu-id="5e1ec-108">This is possible only when the XMPP federated partner is not configured in Lync Server 2013.</span></span>

<span data-ttu-id="5e1ec-109">总而言之，如果 Office 通信服务器已部署到 Office 通信服务器 2007 R2 XMPP 网关，并且已为旧版 Office 通信服务器 2007 R2 用户启用 XMPP 联盟，则将 XMPP 联合迁移到 Lync Server 2013：</span><span class="sxs-lookup"><span data-stu-id="5e1ec-109">In summary, if Office Communications Server has been deployed with the Office Communications Server 2007 R2 XMPP Gateway and XMPP federation has been enabled for legacy Office Communications Server 2007 R2 users, to migrate the XMPP federation to Lync Server 2013:</span></span>

1.  <span data-ttu-id="5e1ec-110">部署 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="5e1ec-110">Deploy a Lync Server 2013 pool.</span></span>

2.  <span data-ttu-id="5e1ec-111">部署 Lync Server 2013 边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="5e1ec-111">Deploy a Lync Server 2013 Edge server.</span></span>

3.  <span data-ttu-id="5e1ec-112">将所有用户移动到 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="5e1ec-112">Move all users to the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="5e1ec-113">为边缘服务器创建 XMPP 访问策略和证书。</span><span class="sxs-lookup"><span data-stu-id="5e1ec-113">Create XMPP access policies and certificates for the Edge Server.</span></span>

5.  <span data-ttu-id="5e1ec-114">在 Lync Server 2013 中启用 XMPP 联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="5e1ec-114">Enable XMPP federation in Lync Server 2013.</span></span> 

6.  <span data-ttu-id="5e1ec-115">将 DNS 条目更新为指向 Lync Server 2013 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="5e1ec-115">Update the DNS entries to point to the Lync Server 2013 XMPP Gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

