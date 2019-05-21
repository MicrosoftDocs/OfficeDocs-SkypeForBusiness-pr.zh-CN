---
title: Trunk 设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
description: 若要编辑或修改 SIP 中继的设置，请执行下列操作：
ms.openlocfilehash: 5b6c0384e2297f8bfd93ea493416fc7eea271033
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282215"
---
# <a name="trunk-settings-expander"></a><span data-ttu-id="f7e3b-103">中继设置扩展器</span><span class="sxs-lookup"><span data-stu-id="f7e3b-103">Trunk Settings Expander</span></span>

<span data-ttu-id="f7e3b-104">若要编辑或修改 SIP 中继的设置，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="f7e3b-104">To edit or modify the settings for a SIP trunk, you do the following:</span></span>

 <span data-ttu-id="f7e3b-105">“**Trunk 名称**”是必填项，并唯一标识部署中的 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="f7e3b-105">**Trunk name** is a required entry and uniquely identifies the SIP trunk in the deployment.</span></span>

 <span data-ttu-id="f7e3b-106">**关联的 PSTN 网关**：选择部署中已定义的现有 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="f7e3b-106">**Associated PSTN gateway**: Select an existing PSTN gateway that has been defined in the deployment.</span></span>

 <span data-ttu-id="f7e3b-p101">**IP/PSTN 网关的侦听端口**：指示网关要在其上侦听请求的 TCP/IP 端口。根据网关的供应商，所需的值可能会有所不同，但默认为端口 5067。</span><span class="sxs-lookup"><span data-stu-id="f7e3b-p101">**Listening port for IP/PSTN gateway**: Indicates what TCP/IP port the gateway will be listening for requests on. The required value may differ, based on the vendor of the gateway, but the default is port 5067.</span></span>

 <span data-ttu-id="f7e3b-p102">**SIP 传输协议**：使用的协议可以是 TCP，也可以是 TLS。TLS 为默认选项。有关网关所支持的选项，请参考网关供应商文档。默认为 TLS，且如果网关支持 TLS，则应将其视为更安全的选择。</span><span class="sxs-lookup"><span data-stu-id="f7e3b-p102">**SIP Transport Protocol**: The protocol used is either TCP or TLS. TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>

 <span data-ttu-id="f7e3b-113">**关联的中介服务器**: 从部署中选择现有中介服务器以与 SIP 主干相关联。</span><span class="sxs-lookup"><span data-stu-id="f7e3b-113">**Associated Mediation Server**: Select an existing Mediation Server from the deployment to associate with the SIP trunk.</span></span>

> [!NOTE]
> <span data-ttu-id="f7e3b-114">只有根干线才能与 Lync Server 2010 或 Lync Server 2013 中介服务器相关联。</span><span class="sxs-lookup"><span data-stu-id="f7e3b-114">Only the root trunk can be associated with a Lync Server 2010 or Lync Server 2013 Mediation Server.</span></span>

 <span data-ttu-id="f7e3b-115">**关联的中介服务器端口**: 一个必需值, 它设置为中介服务器配置为侦听的值。</span><span class="sxs-lookup"><span data-stu-id="f7e3b-115">**Associated Mediation Server port**: A required value, this is set to the value that the Mediation Server is configured to listen on.</span></span>

![中继设置扩展器](../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a><span data-ttu-id="f7e3b-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f7e3b-117">See also</span></span>

[<span data-ttu-id="f7e3b-118">SIP 中继部署清单</span><span class="sxs-lookup"><span data-stu-id="f7e3b-118">SIP Trunking Deployment Checklist</span></span>](https://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)

[<span data-ttu-id="f7e3b-119">SIP 中继的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="f7e3b-119">Components and Topologies for SIP Trunking</span></span>](https://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)
