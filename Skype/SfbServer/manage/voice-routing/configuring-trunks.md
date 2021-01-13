---
title: 在 Skype for Business Server 中配置中继
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 作为 企业语音 部署的一部分，可以在中介服务器和一个或多个对等方之间配置中继，为您的组织中的 企业语音 客户端和设备提供公用电话交换网 (PSTN) 连接。
ms.openlocfilehash: 57b8635d635c0fd0b8c41c95f92af768ff84dfd4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800112"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a><span data-ttu-id="8ec3a-103">在 Skype for Business Server 中配置中继</span><span class="sxs-lookup"><span data-stu-id="8ec3a-103">Configuring trunks in Skype for Business Server</span></span>

<span data-ttu-id="8ec3a-104">作为 企业语音 部署的一部分，可以在中介服务器和以下一个或多个对等方之间配置中继，为您的组织中的 企业语音 客户端和设备提供公用电话交换网 (PSTN) 连接：</span><span class="sxs-lookup"><span data-stu-id="8ec3a-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

- <span data-ttu-id="8ec3a-105">到 Internet 电话服务提供商 (ITSP) 的 SIP 中继连接</span><span class="sxs-lookup"><span data-stu-id="8ec3a-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
- <span data-ttu-id="8ec3a-106">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="8ec3a-106">PSTN gateway</span></span>
- <span data-ttu-id="8ec3a-107">专用交换机 (PBX)</span><span class="sxs-lookup"><span data-stu-id="8ec3a-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="8ec3a-108">有关详细信息，请参阅 [在 Skype for Business Server 中规划 PSTN 连接](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)。</span><span class="sxs-lookup"><span data-stu-id="8ec3a-108">For details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ec3a-109">开始中继配置之前，请确认已创建拓扑，并且中介服务器及其对等方已配置并相互关联。</span><span class="sxs-lookup"><span data-stu-id="8ec3a-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="8ec3a-110">有关详细信息，请参阅 [在 Skype for Business Server 的拓扑生成器中定义网关](../../deploy/deploy-enterprise-voice/define-a-gateway.md)。</span><span class="sxs-lookup"><span data-stu-id="8ec3a-110">For details, see [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8ec3a-111">作为中继配置的一部分，可以启用 Skype for Business Server 媒体旁路功能，该功能使媒体可以绕过中介服务器。</span><span class="sxs-lookup"><span data-stu-id="8ec3a-111">As a part of trunk configuration, you can enable the Skype for Business Server media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="8ec3a-112">配置中继时可以启用媒体旁路，也可以不启用媒体旁路，但我们强烈建议您启用该功能。</span><span class="sxs-lookup"><span data-stu-id="8ec3a-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="8ec3a-113">有关详细信息，请参阅 [Skype for Business 中的媒体旁路计划](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="8ec3a-113">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>
