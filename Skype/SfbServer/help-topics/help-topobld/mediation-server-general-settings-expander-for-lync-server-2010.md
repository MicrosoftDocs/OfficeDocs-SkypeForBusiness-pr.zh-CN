---
title: 适合于 Lync Server 2010 的中介服务器常规设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 在此对话框中编辑中介服务器的属性。 沿左侧是一组快速链接，可转到 "常规设置"、"下一跃点设置" 和 "PSTN 网关设置" 的设置。 每个部分都有以下设置：
ms.openlocfilehash: d439698bf0e383f9c89fb749ef4cedc7ae253997
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684545"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="3cf47-105">适合于 Lync Server 2010 的中介服务器常规设置扩展器</span><span class="sxs-lookup"><span data-stu-id="3cf47-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>

<span data-ttu-id="3cf47-106">在此对话框中编辑中介服务器的属性。</span><span class="sxs-lookup"><span data-stu-id="3cf47-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="3cf47-107">沿左侧是一组快速链接，可转到 "常规设置"、"下一跃点设置" 和 "PSTN 网关设置" 的设置。</span><span class="sxs-lookup"><span data-stu-id="3cf47-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="3cf47-108">每个部分都有以下设置：</span><span class="sxs-lookup"><span data-stu-id="3cf47-108">In each section are the following settings:</span></span>

 <span data-ttu-id="3cf47-109">**常规**：</span><span class="sxs-lookup"><span data-stu-id="3cf47-109">**General**:</span></span>

- <span data-ttu-id="3cf47-110">**FQDN**：编辑中介服务器的完全限定的域名</span><span class="sxs-lookup"><span data-stu-id="3cf47-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>

- <span data-ttu-id="3cf47-111">**关联**：选择 "**关联边缘池" （对于 "媒体组件"）** 复选框，然后选择要用作外部访问媒体路径的中介服务器的边缘服务器或边缘池。</span><span class="sxs-lookup"><span data-stu-id="3cf47-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>

  <span data-ttu-id="3cf47-112">**下一跃点**：</span><span class="sxs-lookup"><span data-stu-id="3cf47-112">**Next hop**:</span></span>

- <span data-ttu-id="3cf47-113">**下一跃点选择**：从列表中选择前端服务器或前端池作为用于与部署进行通信的中介服务器的路径。</span><span class="sxs-lookup"><span data-stu-id="3cf47-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>

  <span data-ttu-id="3cf47-114">**PSTN 网关**：</span><span class="sxs-lookup"><span data-stu-id="3cf47-114">**PSTN gateway**:</span></span>

  <span data-ttu-id="3cf47-115">**中介服务器 PSTN 网关**：</span><span class="sxs-lookup"><span data-stu-id="3cf47-115">**Mediation Server PSTN gateway**:</span></span>

- <span data-ttu-id="3cf47-116">**侦听端口**：定义中介服务器将侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="3cf47-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="3cf47-117">你可以为**TLS**或传输层安全性、 **TCP**或传输控制协议定义端口。</span><span class="sxs-lookup"><span data-stu-id="3cf47-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="3cf47-118">若要使 TCP 的端口项可用，必须选中 "**启用 tcp 端口**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="3cf47-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="3cf47-119">请参阅公共交换电话网络（PSTN）网关的文档和配置设置，确定是否需要启用和定义 TLS、TCP 或两者的端口值。</span><span class="sxs-lookup"><span data-stu-id="3cf47-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="3cf47-120">TLS 是一种更安全的协议，使用证书加密中介服务器和 PSTN 网关之间的流量。</span><span class="sxs-lookup"><span data-stu-id="3cf47-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="3cf47-121">并非所有 PSTN 网关都支持 TLS。</span><span class="sxs-lookup"><span data-stu-id="3cf47-121">Not all PSTN gateways support TLS.</span></span>

- <span data-ttu-id="3cf47-122">将列出 SIP 中继和为你的部署定义和配置的网关的列表。</span><span class="sxs-lookup"><span data-stu-id="3cf47-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="3cf47-123">如果不存在任何条目，则表示你的部署没有配置 SIP 中继或 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="3cf47-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="3cf47-124">在拓扑生成器中的 "**共享组件**" 下定义和配置中继和网关。</span><span class="sxs-lookup"><span data-stu-id="3cf47-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>

## <a name="see-also"></a><span data-ttu-id="3cf47-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3cf47-125">See also</span></span>

[<span data-ttu-id="3cf47-126">SIP 中继概述</span><span class="sxs-lookup"><span data-stu-id="3cf47-126">Overview of SIP Trunking</span></span>](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[<span data-ttu-id="3cf47-127">PSTN 网关部署选项</span><span class="sxs-lookup"><span data-stu-id="3cf47-127">PSTN Gateway Deployment Options</span></span>](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
