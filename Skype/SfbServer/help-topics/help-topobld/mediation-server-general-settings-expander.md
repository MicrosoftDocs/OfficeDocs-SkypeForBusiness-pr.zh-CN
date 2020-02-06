---
title: 中介服务器常规设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/14/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: 1936034831ca3d66007e7f2186ce3772fbaaa06b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819604"
---
# <a name="mediation-server-general-settings-expander"></a><span data-ttu-id="3944b-102">中介服务器常规设置扩展器</span><span class="sxs-lookup"><span data-stu-id="3944b-102">Mediation Server General Settings Expander</span></span>
 


## <a name="general-settings"></a><span data-ttu-id="3944b-103">常规设置</span><span class="sxs-lookup"><span data-stu-id="3944b-103">General settings</span></span>

<span data-ttu-id="3944b-104">中介服务器池或中介服务器的完全限定的域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="3944b-104">Fully qualified domain name (FQDN) of the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="3944b-105">编辑服务器的 FQDN 以更改该值。</span><span class="sxs-lookup"><span data-stu-id="3944b-105">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="3944b-106">必须具有与新值一致的域名系统 (DNS) 主机 (A) 记录。</span><span class="sxs-lookup"><span data-stu-id="3944b-106">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="3944b-107">在 "**关联**" 部分中，选择要与中介服务器池或中介服务器相关联的边缘服务器或边缘服务器池。</span><span class="sxs-lookup"><span data-stu-id="3944b-107">In the **Associations** section, you select an Edge Server or Edge Server pool to associate with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="3944b-108">选择中介服务器的媒体组件将用于外部用户企业语音的边缘。</span><span class="sxs-lookup"><span data-stu-id="3944b-108">You select the Edge that the Mediation Server's media components will use for External user Enterprise Voice.</span></span>
  
<span data-ttu-id="3944b-109">如果当前未定义边缘服务器，并且需要将中介服务器与 Edge 服务器相关联，请单击 "**新建**"，然后在 "定义新的边缘池" 向导中定义新的 edge 服务器或边缘服务器池。</span><span class="sxs-lookup"><span data-stu-id="3944b-109">If you do not have an Edge Server currently defined and need to associate the Mediation Server with an Edge Server, click **New** and define the new Edge Server or Edge Server pool in the Define the New Edge pool wizard.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="3944b-110">下一跃点设置</span><span class="sxs-lookup"><span data-stu-id="3944b-110">Next hop settings</span></span>

<span data-ttu-id="3944b-111">通过从下拉列表中选择 "定义的企业版前端池" 或 "标准版前端服务器"，可以指定中介服务器池或中介服务器下一跃点。</span><span class="sxs-lookup"><span data-stu-id="3944b-111">You specify the Mediation Server pool or Mediation Server next hop by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="3944b-112">Director 或控制器池不是中介服务器池或中介服务器下一跃点的有效选择，不会显示在列表中。</span><span class="sxs-lookup"><span data-stu-id="3944b-112">A Director or Director pool is not a valid selection for a Mediation Server pool or Mediation Server next hop, and will not appear in the list.</span></span> <span data-ttu-id="3944b-113">单击 **"确定"** 接受并保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="3944b-113">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="3944b-114">单击“**取消**”将放弃所做的更改并退出属性页面。</span><span class="sxs-lookup"><span data-stu-id="3944b-114">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  
## <a name="pstn-gateway-settings"></a><span data-ttu-id="3944b-115">PSTN 网关设置</span><span class="sxs-lookup"><span data-stu-id="3944b-115">PSTN gateway settings</span></span>

1. <span data-ttu-id="3944b-116">定义与中介服务器池或中介服务器相关联的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="3944b-116">You define PSTN gateways that are associated with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="3944b-117">如果您已定义网关，则它们将可与中介服务器相关联。</span><span class="sxs-lookup"><span data-stu-id="3944b-117">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span> <span data-ttu-id="3944b-118">如果启用中介服务器并置，请在池服务器上为传输层安全性 (TLS) 定义侦听端口范围。</span><span class="sxs-lookup"><span data-stu-id="3944b-118">If you enable the collocation of the Mediation Server, define the listening port range on the pool servers for Transport Layer Security (TLS).</span></span> <span data-ttu-id="3944b-119">默认情况下，此端口为 5067。</span><span class="sxs-lookup"><span data-stu-id="3944b-119">By default, this port is 5067.</span></span> <span data-ttu-id="3944b-120">如果选择“**启用 TCP 端口**”，则必须为并置的中介服务器定义传输控制协议 (TCP) 端口。</span><span class="sxs-lookup"><span data-stu-id="3944b-120">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="3944b-121">这是一个可选设置，您应该参考网关要求或 PSTN 要求以确定是否需要此设置。</span><span class="sxs-lookup"><span data-stu-id="3944b-121">This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this.</span></span> <span data-ttu-id="3944b-122">默认情况下，TCP 端口值为 5068。</span><span class="sxs-lookup"><span data-stu-id="3944b-122">By default, the TCP port value is 5068.</span></span>
    
2. <span data-ttu-id="3944b-p105">与并置的中介服务器关联的中继。如果已经定义中继，则可以将它们与中介服务器关联。</span><span class="sxs-lookup"><span data-stu-id="3944b-p105">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span> 
    
3. <span data-ttu-id="3944b-125">如果你有多个与中介服务器关联的中继，则可以通过选择主干，然后单击 "**设为默认值**" 来指定一个默认干线。</span><span class="sxs-lookup"><span data-stu-id="3944b-125">If you have more than one trunk associated with a Mediation Server, you can specify a default trunk by selecting the trunk and then clicking **Make Default**.</span></span> <span data-ttu-id="3944b-126">若要取消选择网关作为默认网关，请单击“**取消设为默认值**”。</span><span class="sxs-lookup"><span data-stu-id="3944b-126">To unselect a gateway as the default, click **Unmake Default**.</span></span> 
    

