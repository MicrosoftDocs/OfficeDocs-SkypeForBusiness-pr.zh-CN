---
title: 迁移 XMPP 联合
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: b8d2b4b9-d0ed-4b48-820a-2c257fbdd2fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721861(v=OCS.15)
ms:contentKeyID: 49733794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61a48c579ed9afa3f1a09ed1c3a7129e9e24924d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a><span data-ttu-id="8fa8e-102">迁移 XMPP 联合</span><span class="sxs-lookup"><span data-stu-id="8fa8e-102">Migrating XMPP federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fa8e-103">_**上次修改的主题：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="8fa8e-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="8fa8e-104">早期版本的 Lync Server 和 Office 通信服务器提供了可扩展消息和状态协议（XMPP）网关，可将其作为单独的服务器角色进行部署，以允许与 XMPP 部署进行联盟。</span><span class="sxs-lookup"><span data-stu-id="8fa8e-104">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="8fa8e-105">在 Lync Server 2013 中，可以将 XMPP 功能部署为功能。</span><span class="sxs-lookup"><span data-stu-id="8fa8e-105">In Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="8fa8e-106">XMPP 功能安装在两个部分中：作为运行在 Lync Server 2013 边缘服务器上的 XMPP 代理，以及在 Lync Server 2013 前端服务器上运行的 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="8fa8e-106">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the Lync Server 2013 Edge Server, and the XMPP Gateway that runs on the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="8fa8e-107">从迁移的角度来看，Lync Server 用户帐户可以移动到 Lync Server 2013 池，并继续使用旧版 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="8fa8e-107">From a migration perspective, a Lync Server user account can be moved to a Lync Server 2013 pool and continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="8fa8e-108">仅当未在 Lync Server 2013 中配置 XMPP 联盟伙伴时，才可以这样做。</span><span class="sxs-lookup"><span data-stu-id="8fa8e-108">This is possible only when the XMPP federated partner is not configured in Lync Server 2013.</span></span>

<span data-ttu-id="8fa8e-109">总而言之，如果已使用 Office 通信服务器 2007 R2 XMPP 网关部署了 Lync Server 2010，并且已为旧版 Lync Server 2010 用户启用了 XMPP 联盟，请将 XMPP 联合迁移到 Lync Server 2013：</span><span class="sxs-lookup"><span data-stu-id="8fa8e-109">In summary, if Lync Server 2010 has been deployed with the Office Communications Server 2007 R2 XMPP Gateway and XMPP federation has been enabled for legacy Lync Server 2010 users, to migrate the XMPP federation to Lync Server 2013:</span></span>

1.  <span data-ttu-id="8fa8e-110">部署 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="8fa8e-110">Deploy a Lync Server 2013 pool.</span></span>

2.  <span data-ttu-id="8fa8e-111">部署 Lync Server 2013 边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="8fa8e-111">Deploy a Lync Server 2013 Edge server.</span></span>

3.  <span data-ttu-id="8fa8e-112">将所有用户移动到 Lync Server 2013 池</span><span class="sxs-lookup"><span data-stu-id="8fa8e-112">Move all users to the Lync Server 2013 pool</span></span>

4.  <span data-ttu-id="8fa8e-113">为边缘服务器创建 XMPP 访问策略和证书。</span><span class="sxs-lookup"><span data-stu-id="8fa8e-113">Create XMPP access policies and certificates for the Edge Server.</span></span>

5.  <span data-ttu-id="8fa8e-114">在 Lync Server 2013 中启用 XMPP 联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="8fa8e-114">Enable XMPP federation in Lync Server 2013.</span></span> 

6.  <span data-ttu-id="8fa8e-115">将 DNS 条目更新为指向 Lync Server 2013 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="8fa8e-115">Update the DNS entries to point to the Lync Server 2013 XMPP Gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

