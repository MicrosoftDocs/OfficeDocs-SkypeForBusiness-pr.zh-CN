---
title: 在 Skype for Business 服务器中配置中继
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 作为企业语音部署的一部分, 你可以在中介服务器和一个或多个对等方之间配置主干, 以便为组织中的企业语音客户端和设备提供公共交换电话网络 (PSTN) 连接。
ms.openlocfilehash: c350723720dccee069a28a4d9aa2c40517f6d1bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275001"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a><span data-ttu-id="56c6b-103">在 Skype for Business 服务器中配置中继</span><span class="sxs-lookup"><span data-stu-id="56c6b-103">Configuring trunks in Skype for Business Server</span></span>

<span data-ttu-id="56c6b-104">作为企业语音部署的一部分, 您可以在中介服务器和一个或多个以下对等方之间配置主干, 以便为企业语音客户端和组织中的设备提供公共交换电话网络 (PSTN) 连接:</span><span class="sxs-lookup"><span data-stu-id="56c6b-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

- <span data-ttu-id="56c6b-105">到 Internet 电话服务提供商 (ITSP) 的 SIP 中继连接</span><span class="sxs-lookup"><span data-stu-id="56c6b-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
- <span data-ttu-id="56c6b-106">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="56c6b-106">PSTN gateway</span></span>
- <span data-ttu-id="56c6b-107">专用交换机 (PBX)</span><span class="sxs-lookup"><span data-stu-id="56c6b-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="56c6b-108">有关详细信息, 请参阅[在 Skype For Business 服务器中规划 PSTN 连接](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)。</span><span class="sxs-lookup"><span data-stu-id="56c6b-108">For details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="56c6b-109">在开始中继配置之前, 验证已创建拓扑, 并且中介服务器及其对等已配置并与另一个关联。</span><span class="sxs-lookup"><span data-stu-id="56c6b-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="56c6b-110">有关详细信息, 请参阅[在 Skype For Business 服务器的拓扑生成器中定义网关](../../deploy/deploy-enterprise-voice/define-a-gateway.md)。</span><span class="sxs-lookup"><span data-stu-id="56c6b-110">For details, see [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span></span>

> [!NOTE]
> <span data-ttu-id="56c6b-111">作为中继配置的一部分, 您可以启用 Skype for business 服务器媒体旁路功能, 这使媒体能够绕过中介服务器。</span><span class="sxs-lookup"><span data-stu-id="56c6b-111">As a part of trunk configuration, you can enable the Skype for Business Server media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="56c6b-112">中继可以使用或不启用媒体旁路进行配置, 但我们强烈建议你启用它。</span><span class="sxs-lookup"><span data-stu-id="56c6b-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="56c6b-113">有关详细信息, 请参阅[在 Skype For business 中规划媒体旁路](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="56c6b-113">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>
