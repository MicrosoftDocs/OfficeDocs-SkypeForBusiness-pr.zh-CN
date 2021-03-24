---
title: 定义新的 Trunk
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 通过提供以下信息定义一个新的会话初始协议 (SIP) Trunk：
ms.openlocfilehash: 1b58da8880c65b0beecbd2756d0b5a5028f45e19
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095586"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="3cff9-103">定义新中继</span><span class="sxs-lookup"><span data-stu-id="3cff9-103">Define a New Trunk</span></span>

<span data-ttu-id="3cff9-104">通过提供以下信息定义一个新的会话初始协议 (SIP) Trunk：</span><span class="sxs-lookup"><span data-stu-id="3cff9-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="3cff9-105">**Trunk 名称**：标识此 Trunk 的拓扑中的唯一名称</span><span class="sxs-lookup"><span data-stu-id="3cff9-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="3cff9-106">**关联的 PSTN 网关**：从列表选择部署中的一个已部署且已配置的 PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="3cff9-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="3cff9-p101">**IP/PSTN 网关的侦听端口**：IP-PBX 或 PSTN 网关将侦听的端口。必须是唯一的，不同于部署中配置的所有其他 Trunk 侦听端口</span><span class="sxs-lookup"><span data-stu-id="3cff9-p101">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on. Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="3cff9-109">**SIP 传输协议**：从列表中选择 TCP 或 TLS</span><span class="sxs-lookup"><span data-stu-id="3cff9-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="3cff9-110">**关联的中介服务器**：从列表中选择在部署中部署和配置的中介服务器</span><span class="sxs-lookup"><span data-stu-id="3cff9-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="3cff9-111">**关联的中介服务器端口**：将端口值设置为等于此 SIP 中继将使用的中介服务器的 TCP 或 TLS 端口值</span><span class="sxs-lookup"><span data-stu-id="3cff9-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="3cff9-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3cff9-112">See also</span></span>

[<span data-ttu-id="3cff9-113">Skype for Business Server 2015 中的 M：N 中继</span><span class="sxs-lookup"><span data-stu-id="3cff9-113">M:N trunk in Skype for Business Server 2015</span></span>](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="3cff9-114">如何实施 SIP 中继？</span><span class="sxs-lookup"><span data-stu-id="3cff9-114">How do I implement SIP trunking?</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-how-do-i-implement-sip-trunking)