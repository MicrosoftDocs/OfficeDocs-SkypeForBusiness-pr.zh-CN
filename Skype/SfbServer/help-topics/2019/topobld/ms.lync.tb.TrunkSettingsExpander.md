---
title: Trunk 设置扩展器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
ROBOTS: NOINDEX, NOFOLLOW
description: 若要编辑或修改 SIP 中继的设置，请执行下列操作：
ms.openlocfilehash: 907348defb35ef872ce36f84e6e6cc7695921529
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101778"
---
# <a name="trunk-settings-expander"></a><span data-ttu-id="b39d2-103">中继设置扩展器</span><span class="sxs-lookup"><span data-stu-id="b39d2-103">Trunk Settings Expander</span></span>

<span data-ttu-id="b39d2-104">若要编辑或修改 SIP 中继的设置，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b39d2-104">To edit or modify the settings for a SIP trunk, you do the following:</span></span>

 <span data-ttu-id="b39d2-105">“Trunk 名称”是必填项，并唯一标识部署中的 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="b39d2-105">**Trunk name** is a required entry and uniquely identifies the SIP trunk in the deployment.</span></span>

 <span data-ttu-id="b39d2-106">**关联的 PSTN 网关**：选择部署中已定义的现有 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="b39d2-106">**Associated PSTN gateway**: Select an existing PSTN gateway that has been defined in the deployment.</span></span>

 <span data-ttu-id="b39d2-p101">**IP/PSTN 网关的侦听端口**：指示网关要在其上侦听请求的 TCP/IP 端口。根据网关的供应商，所需的值可能会有所不同，但默认为端口 5067。</span><span class="sxs-lookup"><span data-stu-id="b39d2-p101">**Listening port for IP/PSTN gateway**: Indicates what TCP/IP port the gateway will be listening for requests on. The required value may differ, based on the vendor of the gateway, but the default is port 5067.</span></span>

 <span data-ttu-id="b39d2-p102">**SIP 传输协议**：使用的协议可以是 TCP，也可以是 TLS。TLS 为默认选项。有关网关所支持的选项，请参考网关供应商文档。默认为 TLS，且如果网关支持 TLS，则应将其视为更安全的选择。</span><span class="sxs-lookup"><span data-stu-id="b39d2-p102">**SIP Transport Protocol**: The protocol used is either TCP or TLS. TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>

 <span data-ttu-id="b39d2-113">**关联的中介服务器**：从部署中选择现有中介服务器以与 SIP 中继关联。</span><span class="sxs-lookup"><span data-stu-id="b39d2-113">**Associated Mediation Server**: Select an existing Mediation Server from the deployment to associate with the SIP trunk.</span></span>

> [!NOTE]
> <span data-ttu-id="b39d2-114">只有根中继可以与中介服务器关联。</span><span class="sxs-lookup"><span data-stu-id="b39d2-114">Only the root trunk can be associated with a Mediation Server.</span></span>

 <span data-ttu-id="b39d2-115">**关联的中介服务器端口**：一个必需值，设置为中介服务器配置为侦听的值。</span><span class="sxs-lookup"><span data-stu-id="b39d2-115">**Associated Mediation Server port**: A required value, this is set to the value that the Mediation Server is configured to listen on.</span></span>

![中继设置扩展器](../../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a><span data-ttu-id="b39d2-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b39d2-117">See also</span></span>

[<span data-ttu-id="b39d2-118">SIP 中继部署清单</span><span class="sxs-lookup"><span data-stu-id="b39d2-118">SIP Trunking Deployment Checklist</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-sip-trunk-deployment-checklist)

[<span data-ttu-id="b39d2-119">用于 SIP 中继的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="b39d2-119">Components and Topologies for SIP Trunking</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-sip-trunking)