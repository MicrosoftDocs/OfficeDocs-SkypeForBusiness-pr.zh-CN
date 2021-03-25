---
title: 定义新 IP 或 PSTN 网关的根 Trunk
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPstnGatewayTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22203d9a-4612-45c7-9375-69ae9964ce1e
ROBOTS: NOINDEX, NOFOLLOW
description: 通过配置以下内容定义 IP 或公用电话交换网 (PSTN) 的根 Trunk：
ms.openlocfilehash: 183787e78fee0fa827bd3cc554fb7d43188014d2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116410"
---
# <a name="define-the-root-trunk-for-a-new-ip-or-pstn-gateway"></a><span data-ttu-id="5bb8d-103">定义新 IP 或 PSTN 网关的根中继</span><span class="sxs-lookup"><span data-stu-id="5bb8d-103">Define the Root Trunk for a New IP or PSTN Gateway</span></span>

<span data-ttu-id="5bb8d-104">通过配置以下内容定义 IP 或公用电话交换网 (PSTN) 的根 Trunk：</span><span class="sxs-lookup"><span data-stu-id="5bb8d-104">You define the root trunk for the IP or public switched telephone network (PSTN) by configuring the following:</span></span>

- <span data-ttu-id="5bb8d-105">**Trunk 名称**：定义与 Trunk 关联的完全限定域名</span><span class="sxs-lookup"><span data-stu-id="5bb8d-105">**Trunk name**: define the fully qualified domain name associated with the trunk</span></span>

- <span data-ttu-id="5bb8d-106">**IP/PSTN 网关的侦听端口**：定义此 Trunk 将侦听的端口</span><span class="sxs-lookup"><span data-stu-id="5bb8d-106">**Listening port for IP/PSTN gateway**: define the port that this trunk will listen on</span></span>

- <span data-ttu-id="5bb8d-107">**SIP 传输协议**：根据 Trunk 要求从列表中选择“TCP”或“TLS”</span><span class="sxs-lookup"><span data-stu-id="5bb8d-107">**SIP Transport Protocol**: select from the list either **TCP** or **TLS**, based on the trunk requirements</span></span>

- <span data-ttu-id="5bb8d-108">**关联的中介服务器**：从部署中的可用中介服务器列表中选择</span><span class="sxs-lookup"><span data-stu-id="5bb8d-108">**Associated Mediation Server**: select from the list of available Mediation Servers in your deployment</span></span>

- <span data-ttu-id="5bb8d-109">**关联的中介服务器端口**：定义所选中介服务器正在侦听的端口</span><span class="sxs-lookup"><span data-stu-id="5bb8d-109">**Associated Mediation Server port**: define the port that the selected Mediation Server is listening on</span></span>

## <a name="see-also"></a><span data-ttu-id="5bb8d-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5bb8d-110">See also</span></span>

[<span data-ttu-id="5bb8d-111">在 Skype for Business Server 中配置带媒体旁路的中继</span><span class="sxs-lookup"><span data-stu-id="5bb8d-111">Configure a trunk with media bypass in Skype for Business Server</span></span>](../../../deploy/deploy-enterprise-voice/configure-trunk-with-media-bypass.md)

[<span data-ttu-id="5bb8d-112">在 Skype for Business Server 中配置无媒体旁路的中继</span><span class="sxs-lookup"><span data-stu-id="5bb8d-112">Configure a trunk without media bypass in Skype for Business Server</span></span>](../../../deploy/deploy-enterprise-voice/configure-trunk-without-media-bypass.md)

[<span data-ttu-id="5bb8d-113">SIP 中继支持</span><span class="sxs-lookup"><span data-stu-id="5bb8d-113">SIP Trunking Support</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-sip-trunking-support)