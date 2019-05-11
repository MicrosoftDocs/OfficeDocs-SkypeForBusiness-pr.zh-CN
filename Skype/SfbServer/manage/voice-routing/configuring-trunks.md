---
title: 为业务服务器中 Skype 配置中继
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 作为企业语音部署的一部分，您可以配置您的组织中的企业语音客户端和设备提供公用电话交换网 (pstn) 连接的中介服务器和一个或多个对等方之间的中继。
ms.openlocfilehash: 293685436997833c21dbd7b0d98521202e1beb99
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33896262"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a><span data-ttu-id="f7eb7-103">为业务服务器中 Skype 配置中继</span><span class="sxs-lookup"><span data-stu-id="f7eb7-103">Configuring trunks in Skype for Business Server</span></span>

<span data-ttu-id="f7eb7-104">作为企业语音部署的一部分，您可以配置中介服务器和一个或多个您的组织中的企业语音客户端和设备提供公用电话交换网 (pstn) 连接的以下的对等方之间中继：</span><span class="sxs-lookup"><span data-stu-id="f7eb7-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

- <span data-ttu-id="f7eb7-105">到 Internet 电话服务提供商 (ITSP) 的 SIP 中继连接</span><span class="sxs-lookup"><span data-stu-id="f7eb7-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
- <span data-ttu-id="f7eb7-106">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="f7eb7-106">PSTN gateway</span></span>
- <span data-ttu-id="f7eb7-107">专用交换机 (PBX)</span><span class="sxs-lookup"><span data-stu-id="f7eb7-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="f7eb7-108">有关详细信息，请参阅[规划中的业务服务器 Skype 的 PSTN 连接](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)。</span><span class="sxs-lookup"><span data-stu-id="f7eb7-108">For details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f7eb7-109">中继配置之前，验证已创建的拓扑和，中介服务器和其对等已配置并与另一个关联。</span><span class="sxs-lookup"><span data-stu-id="f7eb7-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="f7eb7-110">有关详细信息，请参阅[Define 拓扑生成器中的业务服务器 Skype 的网关](../../deploy/deploy-enterprise-voice/define-a-gateway.md)。</span><span class="sxs-lookup"><span data-stu-id="f7eb7-110">For details, see [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f7eb7-111">作为中继配置的一部分，您可以启用 Business Server 媒体绕过功能，使媒体绕过中介服务器的 Skype。</span><span class="sxs-lookup"><span data-stu-id="f7eb7-111">As a part of trunk configuration, you can enable the Skype for Business Server media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="f7eb7-112">可以使用或不启用媒体旁路配置中继，但强烈建议您启用它。</span><span class="sxs-lookup"><span data-stu-id="f7eb7-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="f7eb7-113">有关详细信息，请参阅[规划媒体绕过 Skype for Business 中](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="f7eb7-113">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>
