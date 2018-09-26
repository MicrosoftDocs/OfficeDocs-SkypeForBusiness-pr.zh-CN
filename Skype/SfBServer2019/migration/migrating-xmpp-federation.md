---
title: 迁移 XMPP 联盟
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 早期版本提供的可扩展消息和状态协议 (XMPP) 网关无法作为允许与 XMPP 部署联盟的单独的服务器角色部署。 不再可用和 Skype 的业务服务器 2019年中已弃用的 XMPP 功能。 如果您想要继续使用 XMPP 功能，可以将的适用 coexitence 环境与旧版本中 (业务服务器 2015年的 Skype / Lync Server 2013)。 XMPP 功能安装在两个部分： 为 XMPP 代理运行旧边缘服务器和 XMPP 网关的旧前端服务器上运行。
ms.openlocfilehash: d8db32bd823e4a0c15fa373f89ee930d2cd8d98c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25029865"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="d55b7-106">迁移 XMPP 联盟</span><span class="sxs-lookup"><span data-stu-id="d55b7-106">Migrating XMPP federation</span></span>

<span data-ttu-id="d55b7-107">早期版本提供的可扩展消息和状态协议 (XMPP) 网关无法作为允许与 XMPP 部署联盟的单独的服务器角色部署。</span><span class="sxs-lookup"><span data-stu-id="d55b7-107">Previous versions provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="d55b7-108">XMPP 功能不再可用，并在 Skype 中的业务服务器 2019年已弃用。</span><span class="sxs-lookup"><span data-stu-id="d55b7-108">The XMPP functionality is no longer available and is deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="d55b7-109">如果您想要继续使用 XMPP 功能，您可以这样在共存环境中使用旧版本 (Skype 业务服务器 2015年或 Lync Server 2013)。</span><span class="sxs-lookup"><span data-stu-id="d55b7-109">If you want to continue with the XMPP functionality, you can do so in a coexistence environment with a legacy version (Skype for Business Server 2015 or Lync Server 2013).</span></span> <span data-ttu-id="d55b7-110">XMPP 功能安装在两个部分： 为 XMPP 代理运行旧边缘服务器和 XMPP 网关的旧前端服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="d55b7-110">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the legacy Edge Server, and the XMPP Gateway that runs on the legacy Front End Server.</span></span> 
  
<span data-ttu-id="d55b7-111">从迁移的角度看，希望获得 XMPP 功能的用户应保留在旧服务器不应移动到 Skype 业务服务器 2019年池但继续使用旧的 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="d55b7-111">From a migration perspective, users who want to avail the XMPP feature should remain in the legacy server and should not be moved to a Skype for Business Server 2019 pool but continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="d55b7-112">这是可能的仅当在 Skype 业务服务器 2015年或 Lync Server 2013 配置 XMPP 联盟的伙伴时。</span><span class="sxs-lookup"><span data-stu-id="d55b7-112">This is possible only when the XMPP federated partner is configured in Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="d55b7-113">您应不迁移旧边缘服务器到 Skype 业务服务器 2019年如果您想要继续使用 XMPP 功能。</span><span class="sxs-lookup"><span data-stu-id="d55b7-113">You should not migrate the legacy Edge Server to Skype for Business Server 2019 if you want to continue with XMPP functionality.</span></span> <span data-ttu-id="d55b7-114">但是，您可以旧边缘服务器 （与 XMPP 代理） 和 Skype 业务 2019年边缘服务器共存。</span><span class="sxs-lookup"><span data-stu-id="d55b7-114">However, you can have coexistence of the legacy Edge Server (with XMPP Proxy) and the Skype for Business 2019 Edge Server.</span></span>
  

    

