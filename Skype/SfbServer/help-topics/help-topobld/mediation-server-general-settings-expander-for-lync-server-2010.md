---
title: Lync Server 2010 中的中介服务器的常规设置扩展器
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 编辑此对话框中的中介服务器的属性。 沿左侧是一套快速链接使您转到常规设置、 下一跃点设置和 PSTN 网关设置的设置。 在每一节包括下列设置：
ms.openlocfilehash: bc5016c9dbeb6b0693444f930c9883b1736258d2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="92975-105">Lync Server 2010 中的中介服务器的常规设置扩展器</span><span class="sxs-lookup"><span data-stu-id="92975-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="92975-106">编辑此对话框中的中介服务器的属性。</span><span class="sxs-lookup"><span data-stu-id="92975-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="92975-107">沿左侧是一套快速链接使您转到常规设置、 下一跃点设置和 PSTN 网关设置的设置。</span><span class="sxs-lookup"><span data-stu-id="92975-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="92975-108">在每一节包括下列设置：</span><span class="sxs-lookup"><span data-stu-id="92975-108">In each section are the following settings:</span></span>
  
 <span data-ttu-id="92975-109">**常规**：</span><span class="sxs-lookup"><span data-stu-id="92975-109">**General**:</span></span>
  
- <span data-ttu-id="92975-110">**FQDN**： 编辑中介服务器的完全限定的域名称</span><span class="sxs-lookup"><span data-stu-id="92975-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>
    
- <span data-ttu-id="92975-111">**关联**： 选择**关联边池 （对于媒体组件）**复选框，然后选择要用作介质路径外部访问边缘服务器或中介服务器的边缘池。</span><span class="sxs-lookup"><span data-stu-id="92975-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>
    
 <span data-ttu-id="92975-112">**下一个跃点**：</span><span class="sxs-lookup"><span data-stu-id="92975-112">**Next hop**:</span></span>
  
- <span data-ttu-id="92975-113">**下一跃点选择**： 从列表中选择要用作中介服务器的路径，使用与您的部署进行通信的前端服务器或前端池。</span><span class="sxs-lookup"><span data-stu-id="92975-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>
    
 <span data-ttu-id="92975-114">**PSTN 网关**：</span><span class="sxs-lookup"><span data-stu-id="92975-114">**PSTN gateway**:</span></span>
  
 <span data-ttu-id="92975-115">**中介服务器 PSTN 网关**：</span><span class="sxs-lookup"><span data-stu-id="92975-115">**Mediation Server PSTN gateway**:</span></span>
  
- <span data-ttu-id="92975-116">**侦听端口**： 定义中介服务器将侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="92975-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="92975-117">您可以定义一个用于**TLS**或传输层安全性或**TCP**，端口或传输控制协议。</span><span class="sxs-lookup"><span data-stu-id="92975-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="92975-118">可用的 TCP 端口条目，您必须**启用 TCP**端口选择复选框。</span><span class="sxs-lookup"><span data-stu-id="92975-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="92975-119">请参阅以确定是否您需要启用并定义端口值 TLS 和 / 或 TCP 公用交换的电话网络 (PSTN) 网关的文档和配置设置。</span><span class="sxs-lookup"><span data-stu-id="92975-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="92975-120">TLS 是更安全的协议，使用证书来加密中介服务器和 PSTN 网关之间的通信。</span><span class="sxs-lookup"><span data-stu-id="92975-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="92975-121">不是所有的 PSTN 网关支持 TLS。</span><span class="sxs-lookup"><span data-stu-id="92975-121">Not all PSTN gateways support TLS.</span></span> 
  
- <span data-ttu-id="92975-122">列出的 SIP 中继和定义并为您的部署配置的网关列表。</span><span class="sxs-lookup"><span data-stu-id="92975-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="92975-123">如果任何条目存在，任何 SIP 中继或 PSTN 网关配置为您的部署。</span><span class="sxs-lookup"><span data-stu-id="92975-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="92975-124">定义并在拓扑生成器配置中继和**共享组件**下的网关。</span><span class="sxs-lookup"><span data-stu-id="92975-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="92975-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92975-125">See also</span></span>

#### 

[<span data-ttu-id="92975-126">SIP 中继的概述</span><span class="sxs-lookup"><span data-stu-id="92975-126">Overview of SIP Trunking</span></span>](http://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)
  
[<span data-ttu-id="92975-127">PSTN 网关部署选项</span><span class="sxs-lookup"><span data-stu-id="92975-127">PSTN Gateway Deployment Options</span></span>](http://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)

