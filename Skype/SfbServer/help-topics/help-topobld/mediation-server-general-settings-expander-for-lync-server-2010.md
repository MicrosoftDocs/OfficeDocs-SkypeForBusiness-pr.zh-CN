---
title: Lync Server 2010 的中介服务器常规设置扩展器
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
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 在此对话框中编辑中介服务器的属性。 左侧是一组快速链接，带您设置常规设置、下一个跃点设置和 PSTN 网关设置。 每个部分的设置如下：
ms.openlocfilehash: 6c8c238ce7d89db53f3b92a0f513c080976a3bab
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114188"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="fd265-105">适合于 Lync Server 2010 的中介服务器常规设置扩展器</span><span class="sxs-lookup"><span data-stu-id="fd265-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>

<span data-ttu-id="fd265-106">在此对话框中编辑中介服务器的属性。</span><span class="sxs-lookup"><span data-stu-id="fd265-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="fd265-107">左侧是一组快速链接，带您设置常规设置、下一个跃点设置和 PSTN 网关设置。</span><span class="sxs-lookup"><span data-stu-id="fd265-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="fd265-108">每个部分的设置如下：</span><span class="sxs-lookup"><span data-stu-id="fd265-108">In each section are the following settings:</span></span>

 <span data-ttu-id="fd265-109">**常规**：</span><span class="sxs-lookup"><span data-stu-id="fd265-109">**General**:</span></span>

- <span data-ttu-id="fd265-110">**FQDN：** 编辑中介服务器的完全限定域名</span><span class="sxs-lookup"><span data-stu-id="fd265-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>

- <span data-ttu-id="fd265-111">**关联**：选中"为媒体组件 (关联边缘池) "复选框 **，** 并选择中介服务器的边缘服务器或边缘池以用作外部访问的媒体路径。</span><span class="sxs-lookup"><span data-stu-id="fd265-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>

  <span data-ttu-id="fd265-112">**下一个跃点**：</span><span class="sxs-lookup"><span data-stu-id="fd265-112">**Next hop**:</span></span>

- <span data-ttu-id="fd265-113">**下一** 个跃点选择：从列表中选择前端服务器或前端池，以用作中介服务器与部署进行通信的路径。</span><span class="sxs-lookup"><span data-stu-id="fd265-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>

  <span data-ttu-id="fd265-114">**PSTN 网关**：</span><span class="sxs-lookup"><span data-stu-id="fd265-114">**PSTN gateway**:</span></span>

  <span data-ttu-id="fd265-115">**中介服务器 PSTN 网关**：</span><span class="sxs-lookup"><span data-stu-id="fd265-115">**Mediation Server PSTN gateway**:</span></span>

- <span data-ttu-id="fd265-116">**侦听端口**：定义中介服务器将侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="fd265-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="fd265-117">可以为 **TLS**（即传输层安全性）或 **TCP**（即传输控制协议）定义端口。</span><span class="sxs-lookup"><span data-stu-id="fd265-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="fd265-118">要让 TCP 端口输入可用，必须选中“启用 TCP 端口”复选框。</span><span class="sxs-lookup"><span data-stu-id="fd265-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fd265-119">请参阅公用电话交换网 (PSTN) 网关的文档和配置设置，以确定是需要启用并定义端口值 TLS 和/或 TCP。</span><span class="sxs-lookup"><span data-stu-id="fd265-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="fd265-120">TLS 是一种更安全的协议，使用证书加密中介服务器和 PSTN 网关之间的通信。</span><span class="sxs-lookup"><span data-stu-id="fd265-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="fd265-121">并非所有的 PSTN 网关都支持 TLS。</span><span class="sxs-lookup"><span data-stu-id="fd265-121">Not all PSTN gateways support TLS.</span></span>

- <span data-ttu-id="fd265-122">列出针对部署定义和配置的 SIP 中继和网关列表。</span><span class="sxs-lookup"><span data-stu-id="fd265-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="fd265-123">如果未提供任何项目，则未针对部署配置任何 SIP 中继或 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="fd265-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="fd265-124">在拓扑生成器中的"共享组件"下定义 **和配置中继** 和网关。</span><span class="sxs-lookup"><span data-stu-id="fd265-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>

## <a name="see-also"></a><span data-ttu-id="fd265-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd265-125">See also</span></span>

[<span data-ttu-id="fd265-126">SIP 中继的概述</span><span class="sxs-lookup"><span data-stu-id="fd265-126">Overview of SIP Trunking</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-sip-trunking)

[<span data-ttu-id="fd265-127">PSTN 网关部署选项</span><span class="sxs-lookup"><span data-stu-id="fd265-127">PSTN Gateway Deployment Options</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-gateway-deployment-options)