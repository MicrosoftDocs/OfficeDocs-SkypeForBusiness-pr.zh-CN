---
title: 管理 XMPP 联盟
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 以前的版本提供了可扩展消息和状态协议（XMPP）网关，可将其部署为单独的服务器角色，以便允许与 XMPP 部署进行联盟。 XMPP 功能在 Skype for Business Server 2019 中不再可用 & 已弃用。 如果您想要继续处理 XMPP 功能，可通过旧版版本（Skype for business Server 2015/Lync Server 2013）在 coexitence 环境中 availed。 XMPP 功能安装在两个部分中：作为在旧版 Edge 服务器上运行的 XMPP 代理，以及在旧前端服务器上运行的 XMPP 网关。
ms.openlocfilehash: d8640d90427d5d7ae9c19a092dc10f0d299ae2be
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813430"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="a6073-106">管理 XMPP 联盟</span><span class="sxs-lookup"><span data-stu-id="a6073-106">Migrating XMPP federation</span></span>

<span data-ttu-id="a6073-107">以前的版本提供了可扩展消息和状态协议（XMPP）网关，可将其部署为单独的服务器角色，以便允许与 XMPP 部署进行联盟。</span><span class="sxs-lookup"><span data-stu-id="a6073-107">Previous versions provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="a6073-108">在 Skype for Business Server 2019 中，XMPP 功能不再可用且已弃用。</span><span class="sxs-lookup"><span data-stu-id="a6073-108">The XMPP functionality is no longer available and is deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="a6073-109">如果你想要继续使用 XMPP 功能，可以在具有旧版版本（Skype for business Server 2015 或 Lync Server 2013）的共存环境中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="a6073-109">If you want to continue with the XMPP functionality, you can do so in a coexistence environment with a legacy version (Skype for Business Server 2015 or Lync Server 2013).</span></span> <span data-ttu-id="a6073-110">XMPP 功能安装在两个部分中：作为在旧版 Edge 服务器上运行的 XMPP 代理，以及在旧前端服务器上运行的 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="a6073-110">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the legacy Edge Server, and the XMPP Gateway that runs on the legacy Front End Server.</span></span> 
  
<span data-ttu-id="a6073-111">从迁移的角度看，想要使用 XMPP 功能的用户应保留在旧服务器中，并且不应移动到 Skype for business Server 2019 池，但继续使用旧版 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="a6073-111">From a migration perspective, users who want to avail the XMPP feature should remain in the legacy server and should not be moved to a Skype for Business Server 2019 pool but continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="a6073-112">仅当在 Skype for Business Server 2015 或 Lync Server 2013 中配置了 XMPP 联盟伙伴时，才可以这样做。</span><span class="sxs-lookup"><span data-stu-id="a6073-112">This is possible only when the XMPP federated partner is configured in Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="a6073-113">如果要继续 XMPP 功能，则不应将旧式边缘服务器迁移到 Skype for business Server 2019。</span><span class="sxs-lookup"><span data-stu-id="a6073-113">You should not migrate the legacy Edge Server to Skype for Business Server 2019 if you want to continue with XMPP functionality.</span></span> <span data-ttu-id="a6073-114">但是，你可以使用旧版 Edge 服务器（使用 XMPP 代理）和 Skype for business 2019 Edge 服务器共存。</span><span class="sxs-lookup"><span data-stu-id="a6073-114">However, you can have coexistence of the legacy Edge Server (with XMPP Proxy) and the Skype for Business 2019 Edge Server.</span></span>
  

    

