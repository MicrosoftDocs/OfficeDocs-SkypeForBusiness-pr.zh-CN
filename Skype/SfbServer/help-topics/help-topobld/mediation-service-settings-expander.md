---
title: 中介服务设置扩展器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 对于“中介服务器”，可以指定以下内容：
ms.openlocfilehash: 0e6e9101b8b0a530b0f47411f1d8ce1eaa2e01b5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810272"
---
# <a name="mediation-service-settings-expander"></a><span data-ttu-id="7aec6-103">中介服务设置扩展器</span><span class="sxs-lookup"><span data-stu-id="7aec6-103">Mediation Service Settings Expander</span></span>

<span data-ttu-id="7aec6-104">对于“中介服务器”，可以指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="7aec6-104">For **Mediation Server**, you can specify the following:</span></span>

<span data-ttu-id="7aec6-105">如果要将中介服务器并放在前端池或 Standard Edition 服务器上，请选中启用并 **排中介服务器的复选框**。</span><span class="sxs-lookup"><span data-stu-id="7aec6-105">If you are collocating the Mediation Server onto the Front End pool or the Standard Edition server, select the check box **Collocated Mediation Server enabled**.</span></span> <span data-ttu-id="7aec6-106">如果选择不并置中介服务器，则本节中没有可定义的设置。</span><span class="sxs-lookup"><span data-stu-id="7aec6-106">If you choose not to collocate the Mediation Server, there are no definable settings in this section.</span></span>

<span data-ttu-id="7aec6-p102">如果已启用中介服务器并置，则需要在服务器上为传输层安全性 (TLS) 定义侦听端口范围。默认情况下，此端口为 5067。如果选择“启用 TCP 端口”，则必须为并置的中介服务器定义传输控制协议 (TCP) 端口。这是一个可选设置，您应该参考网关要求或公用电话交换网 (PSTN) 要求以确定是否需要此设置。默认情况下，TCP 端口值为 5068。</span><span class="sxs-lookup"><span data-stu-id="7aec6-p102">If you have enabled the collocation of the Mediation Server, you need to define the listening port range on the server for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or public switched telephone network (PSTN) requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="7aec6-p103">定义与并置的中介服务器关联的 PSTN 网关。如果已定义网关，则可以将这些网关与中介服务器关联。</span><span class="sxs-lookup"><span data-stu-id="7aec6-p103">You define PSTN gateways that are associated with the collocated Mediation Server. If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span>

<span data-ttu-id="7aec6-p104">如果有多个网关与中介服务器关联，会将第一个关联的网关作为默认网关。如果需要选择其他网关作为默认网关，请选择要设为默认值的网关，然后单击“设为默认值”。若要取消选择网关作为默认网关，请单击“取消设为默认值”。</span><span class="sxs-lookup"><span data-stu-id="7aec6-p104">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway. If you need to choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**. To unselect the gateway as the default, click **Unmake Default**.</span></span>

<span data-ttu-id="7aec6-117">有关定义和配置 Enterprise Edition 前端池或 Standard Edition Server 的设置的详细信息，[](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx)请参阅"定义和配置拓扑和部署中介服务器"和"[定义对等方"。](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)</span><span class="sxs-lookup"><span data-stu-id="7aec6-117">For details about defining and configuring the settings for the Enterprise Edition Front End pool or Standard Edition server, see [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>


