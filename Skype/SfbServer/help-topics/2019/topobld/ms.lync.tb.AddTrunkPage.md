---
title: 定义新的中继
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: 通过提供以下信息定义新的会话初始协议 (SIP) 中继：
ms.openlocfilehash: 206e2c1f23782bb3648dfc7c2a0eb1f26ca98d3f
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23260627"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="c8e53-103">定义新的中继</span><span class="sxs-lookup"><span data-stu-id="c8e53-103">Define a New Trunk</span></span>

<span data-ttu-id="c8e53-104">通过提供以下信息定义新的会话初始协议 (SIP) 中继：</span><span class="sxs-lookup"><span data-stu-id="c8e53-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="c8e53-105">**Trunk 名称**： 标识此 trunk 的拓扑中的唯一名称</span><span class="sxs-lookup"><span data-stu-id="c8e53-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="c8e53-106">**关联的 PSTN 网关**： 选择部署从列表中的部署和配置 PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="c8e53-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="c8e53-107">**IP/PSTN 网关的侦听端口**： 的 IP PBX 或 PSTN 网关将侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="c8e53-107">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on.</span></span> <span data-ttu-id="c8e53-108">必须是唯一的从所有部署中配置其他中继侦听端口</span><span class="sxs-lookup"><span data-stu-id="c8e53-108">Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="c8e53-109">**SIP 传输协议**： 从列表中选择 TCP 或 TLS</span><span class="sxs-lookup"><span data-stu-id="c8e53-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="c8e53-110">**关联的中介服务器**： 从列表中选择一个已部署且您部署中配置中介服务器</span><span class="sxs-lookup"><span data-stu-id="c8e53-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="c8e53-111">**关联的中介服务器端口**： 将端口值设置为等于该 SIP 中继将使用的中介服务器的 TCP 或 TLS 端口值</span><span class="sxs-lookup"><span data-stu-id="c8e53-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="c8e53-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8e53-112">See also</span></span>

[<span data-ttu-id="c8e53-113">Skype 业务服务器中的 M:N 中继</span><span class="sxs-lookup"><span data-stu-id="c8e53-113">M:N trunk in Skype for Business Server</span></span>](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="c8e53-114">如何实施 SIP 中继？</span><span class="sxs-lookup"><span data-stu-id="c8e53-114">How do I implement SIP trunking?</span></span>](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)