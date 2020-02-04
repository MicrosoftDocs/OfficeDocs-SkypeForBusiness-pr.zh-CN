---
title: 定义新中继
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: 通过提供以下信息来定义新的会话初始协议（SIP）中继：
ms.openlocfilehash: e6036942423e7d4f88050fead56e2a1336530cab
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689041"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="29c03-103">定义新中继</span><span class="sxs-lookup"><span data-stu-id="29c03-103">Define a New Trunk</span></span>

<span data-ttu-id="29c03-104">通过提供以下信息来定义新的会话初始协议（SIP）中继：</span><span class="sxs-lookup"><span data-stu-id="29c03-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="29c03-105">**主干名称**：拓扑中将标识此主干的唯一名称</span><span class="sxs-lookup"><span data-stu-id="29c03-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="29c03-106">**关联的 PSTN 网关**：从列表中选择部署中已部署的和配置的 PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="29c03-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="29c03-107">**Ip/PSTN 网关的侦听端口**： ip PBX 或 PSTN 网关将侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="29c03-107">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on.</span></span> <span data-ttu-id="29c03-108">在部署中配置的所有其他中继侦听端口必须是唯一的</span><span class="sxs-lookup"><span data-stu-id="29c03-108">Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="29c03-109">**SIP 传输协议**：从列表中选择 "TCP" 或 "TLS"</span><span class="sxs-lookup"><span data-stu-id="29c03-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="29c03-110">**关联的中介服务器**：从列表中选择在部署中部署和配置的中介服务器</span><span class="sxs-lookup"><span data-stu-id="29c03-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="29c03-111">**关联的中介服务器端口**：将 port 值设置为等于此 SIP 主干将使用的中介服务器的 TCP 或 TLS 端口值</span><span class="sxs-lookup"><span data-stu-id="29c03-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="29c03-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29c03-112">See also</span></span>

[<span data-ttu-id="29c03-113">Skype for Business 服务器中的 M:N 主干</span><span class="sxs-lookup"><span data-stu-id="29c03-113">M:N trunk in Skype for Business Server</span></span>](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="29c03-114">如何实现 SIP 中继？</span><span class="sxs-lookup"><span data-stu-id="29c03-114">How do I implement SIP trunking?</span></span>](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
