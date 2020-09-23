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
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: bd3047832b23604f87a1e298a42798b13bb6822a
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215163"
---
# <a name="mediation-server-general-settings-expander"></a><span data-ttu-id="4a174-102">中介服务器常规设置扩展器</span><span class="sxs-lookup"><span data-stu-id="4a174-102">Mediation Server General Settings Expander</span></span>
 


## <a name="general-settings"></a><span data-ttu-id="4a174-103">常规设置</span><span class="sxs-lookup"><span data-stu-id="4a174-103">General settings</span></span>

<span data-ttu-id="4a174-p101">中介服务器池或中介服务器的完全限定域名 (FQDN)。编辑服务器的 FQDN 以更改该值。必须具有与新值一致的域名系统 (DNS) 主机 (A) 记录。</span><span class="sxs-lookup"><span data-stu-id="4a174-p101">Fully qualified domain name (FQDN) of the Mediation Server pool or Mediation Server. Edit the FQDN of the server to change the value. You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="4a174-107">在 **“关联”** 部分中，选择要与中介服务器池或中介服务器关联的边缘服务器或边缘服务器池。</span><span class="sxs-lookup"><span data-stu-id="4a174-107">In the **Associations** section, you select an Edge Server or Edge Server pool to associate with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="4a174-108">选择中介服务器的媒体组件将用于外部用户企业语音的边缘。</span><span class="sxs-lookup"><span data-stu-id="4a174-108">You select the Edge that the Mediation Server's media components will use for External user Enterprise Voice.</span></span>
  
<span data-ttu-id="4a174-109">如果当前未定义边缘服务器，而需要将中介服务器与边缘服务器关联，请单击 **“新建”**，然后通过“定义新的边缘池”向导定义新的边缘服务器或边缘服务器池。</span><span class="sxs-lookup"><span data-stu-id="4a174-109">If you do not have an Edge Server currently defined and need to associate the Mediation Server with an Edge Server, click **New** and define the new Edge Server or Edge Server pool in the Define the New Edge pool wizard.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="4a174-110">下一跃点设置</span><span class="sxs-lookup"><span data-stu-id="4a174-110">Next hop settings</span></span>

<span data-ttu-id="4a174-111">通过从下拉列表中选择定义的 Enterprise Edition 前端池或 Standard Edition 前端服务器，可指定中介服务器池或中介服务器的下一个跃点。</span><span class="sxs-lookup"><span data-stu-id="4a174-111">You specify the Mediation Server pool or Mediation Server next hop by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="4a174-112">控制器或控制器池不是中介服务器池或中介服务器下一个跃点的有效选择，不会显示在列表中。</span><span class="sxs-lookup"><span data-stu-id="4a174-112">A Director or Director pool is not a valid selection for a Mediation Server pool or Mediation Server next hop, and will not appear in the list.</span></span> <span data-ttu-id="4a174-113">单击 **"确定"** 接受并保存更改。</span><span class="sxs-lookup"><span data-stu-id="4a174-113">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="4a174-114">单击“取消”\*\*\*\* 将放弃所做的更改并退出属性页面。</span><span class="sxs-lookup"><span data-stu-id="4a174-114">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  
## <a name="pstn-gateway-settings"></a><span data-ttu-id="4a174-115">PSTN 网关设置</span><span class="sxs-lookup"><span data-stu-id="4a174-115">PSTN gateway settings</span></span>

1. <span data-ttu-id="4a174-p104">定义与中介服务器池或中介服务器关联的 PSTN 网关。如果已定义了网关，它们将可用于与中介服务器关联。如果启用中介服务器并置，请在池服务器上为传输层安全性 (TLS) 定义侦听端口范围。默认情况下，该端口为 5067。如果选择“启用 TCP 端口”\*\*\*\*，则必须为并置的中介服务器定义一个传输控制协议 (TCP) 端口。这是一个可选设置，您应该参考网关要求或 PSTN 要求以确定是否需要此设置。默认情况下，TCP 端口值为 5068。</span><span class="sxs-lookup"><span data-stu-id="4a174-p104">You define PSTN gateways that are associated with the Mediation Server pool or Mediation Server. If you have already defined gateways, they will be available to associate with the Mediation Server. If you enable the collocation of the Mediation Server, define the listening port range on the pool servers for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>
    
2. <span data-ttu-id="4a174-p105">与并置的中介服务器关联的中继。如果已定义了中继，则它们可用于与中介服务器关联。</span><span class="sxs-lookup"><span data-stu-id="4a174-p105">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span> 
    
3. <span data-ttu-id="4a174-p106">如果将多个中继与中介服务器关联，则可以通过选择某个中继然后单击“设为默认值”\*\*\*\* 来指定默认中继。若要将某个网关取消选为默认网关，请单击“取消设为默认值”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4a174-p106">If you have more than one trunk associated with a Mediation Server, you can specify a default trunk by selecting the trunk and then clicking **Make Default**. To unselect a gateway as the default, click **Unmake Default**.</span></span> 
    

