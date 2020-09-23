---
title: Lync Server 2010 的中介服务器常规设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 19687f8d6a97a9174782c094f80c5b52d6973caf
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215153"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="b9838-105">Lync Server 2010 的中介服务器常规设置扩展器</span><span class="sxs-lookup"><span data-stu-id="b9838-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>

<span data-ttu-id="b9838-106">在此对话框中编辑中介服务器的属性。</span><span class="sxs-lookup"><span data-stu-id="b9838-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="b9838-107">左侧是一组快速链接，带您设置常规设置、下一个跃点设置和 PSTN 网关设置。</span><span class="sxs-lookup"><span data-stu-id="b9838-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="b9838-108">每个部分的设置如下：</span><span class="sxs-lookup"><span data-stu-id="b9838-108">In each section are the following settings:</span></span>

 <span data-ttu-id="b9838-109">**常规**：</span><span class="sxs-lookup"><span data-stu-id="b9838-109">**General**:</span></span>

- <span data-ttu-id="b9838-110">**FQDN**：编辑中介服务器的完全限定的域名称</span><span class="sxs-lookup"><span data-stu-id="b9838-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>

- <span data-ttu-id="b9838-111">**关联**：选中 " **关联) 媒体组件的边缘池 (** " 复选框，然后选择要用作外部访问的媒体路径的中介服务器的边缘服务器或边缘池。</span><span class="sxs-lookup"><span data-stu-id="b9838-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>

  <span data-ttu-id="b9838-112">**下一个跃点**：</span><span class="sxs-lookup"><span data-stu-id="b9838-112">**Next hop**:</span></span>

- <span data-ttu-id="b9838-113">**下一跃点选择**：从列表中选择前端服务器或前端池用作中介服务器的路径，以用于与您的部署进行通信。</span><span class="sxs-lookup"><span data-stu-id="b9838-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>

  <span data-ttu-id="b9838-114">**PSTN 网关**：</span><span class="sxs-lookup"><span data-stu-id="b9838-114">**PSTN gateway**:</span></span>

  <span data-ttu-id="b9838-115">**中介服务器 PSTN 网关**：</span><span class="sxs-lookup"><span data-stu-id="b9838-115">**Mediation Server PSTN gateway**:</span></span>

- <span data-ttu-id="b9838-116">**侦听端口**：定义中介服务器将侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="b9838-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="b9838-117">可以为 **TLS**（即传输层安全性）或 **TCP**（即传输控制协议）定义端口。</span><span class="sxs-lookup"><span data-stu-id="b9838-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="b9838-118">要让 TCP 端口输入可用，必须选中“启用 TCP 端口”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="b9838-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b9838-119">请参阅公用电话交换网 (PSTN) 网关的文档和配置设置，以确定是需要启用并定义端口值 TLS 和/或 TCP。</span><span class="sxs-lookup"><span data-stu-id="b9838-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="b9838-120">TLS 是一种更安全的协议，它使用证书来加密中介服务器和 PSTN 网关之间的通信。</span><span class="sxs-lookup"><span data-stu-id="b9838-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="b9838-121">并非所有的 PSTN 网关都支持 TLS。</span><span class="sxs-lookup"><span data-stu-id="b9838-121">Not all PSTN gateways support TLS.</span></span>

- <span data-ttu-id="b9838-122">列出针对部署定义和配置的 SIP 中继和网关列表。</span><span class="sxs-lookup"><span data-stu-id="b9838-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="b9838-123">如果未提供任何项目，则未针对部署配置任何 SIP 中继或 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="b9838-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="b9838-124">您可以在拓扑生成器中的 " **共享组件** " 下定义和配置中继和网关。</span><span class="sxs-lookup"><span data-stu-id="b9838-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9838-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9838-125">See also</span></span>

[<span data-ttu-id="b9838-126">SIP 中继的概述</span><span class="sxs-lookup"><span data-stu-id="b9838-126">Overview of SIP Trunking</span></span>](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[<span data-ttu-id="b9838-127">PSTN 网关部署选项</span><span class="sxs-lookup"><span data-stu-id="b9838-127">PSTN Gateway Deployment Options</span></span>](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
