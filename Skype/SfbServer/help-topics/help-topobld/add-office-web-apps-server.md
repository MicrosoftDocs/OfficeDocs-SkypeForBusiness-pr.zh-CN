---
title: 添加 Office Web Apps 服务器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: "\"定义新的 Office Web Apps Server\"向导定义部署中的新 Office Web Apps 服务器。 请填写以下信息："
ms.openlocfilehash: 002566fb77539745d1d0023159e9af7852b1ecdc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119701"
---
# <a name="add-office-web-apps-server"></a><span data-ttu-id="07daa-104">添加 Office Web Apps 服务器</span><span class="sxs-lookup"><span data-stu-id="07daa-104">Add Office Web Apps Server</span></span>

<span data-ttu-id="07daa-105">" **定义新的 Office Web Apps Server"** 向导定义部署中的新 Office Web Apps 服务器。</span><span class="sxs-lookup"><span data-stu-id="07daa-105">The **Define New Office Web Apps Server** wizard defines a new Office Web Apps Server in your deployment.</span></span> <span data-ttu-id="07daa-106">请填写以下信息：</span><span class="sxs-lookup"><span data-stu-id="07daa-106">You fill in the following information:</span></span>

 <span data-ttu-id="07daa-107">**Office Web Apps Server FQDN：** 键入将承载 Office Web Apps 服务器的服务器的完全限定域名</span><span class="sxs-lookup"><span data-stu-id="07daa-107">**Office Web Apps Server FQDN**: Type the fully qualified domain name of the server that will host the Office Web Apps Server</span></span>

 <span data-ttu-id="07daa-108">**Office Web Apps Server 发现 URL：** 键入 Office Web Apps Server (URL) 统一资源定位器</span><span class="sxs-lookup"><span data-stu-id="07daa-108">**Office Web Apps Server discovery URL**: Type the full uniform resource locator (URL) of the Office Web Apps Server</span></span>

> [!TIP]
> <span data-ttu-id="07daa-109">**Office Web Apps Server** 发现 URL 的默认行为是基于 Office Web Apps Server 的 FQDN 创建 URL，格式为 `https://<FQDN of the Office Web Apps Server/hosting/discovery` ：。</span><span class="sxs-lookup"><span data-stu-id="07daa-109">The default behavior of the **Office Web Apps Server discovery URL** is to create the URL based on the FQDN of the Office Web Apps Server in the format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span></span> <span data-ttu-id="07daa-110">在大多数情况下，不需要更改默认格式。</span><span class="sxs-lookup"><span data-stu-id="07daa-110">In most cases you will not need to change the default format.</span></span> <span data-ttu-id="07daa-111">如果 Office Web Apps Server 和 Office Web Apps 服务器发现 URL 必须不同，您可能需要更改默认格式。</span><span class="sxs-lookup"><span data-stu-id="07daa-111">You may need to change the default format in the event that the Office Web Apps Server and the Office Web Apps Server discovery URL must be different.</span></span> <span data-ttu-id="07daa-112">例如，您的 Office Web Apps Server 位于外围网络中，并且根据位置将具有不同的 URL。</span><span class="sxs-lookup"><span data-stu-id="07daa-112">For example, your Office Web Apps Server is placed in the perimeter network and will have a different URL based on the location.</span></span>

 <span data-ttu-id="07daa-113">Office Web Apps Server 部署在外部网络 (即外围 **/Internet) ：** 如果您的 Office Web Apps 服务器位于内部防火墙之外（如外围网络、外部网络或其他与内部网络不同的网络区域）中，请选中该复选框。</span><span class="sxs-lookup"><span data-stu-id="07daa-113">**Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**: Select the check box if your Office Web Apps Server is placed outside of your internal firewall, such as the perimeter network, external network, or other network zone that is not the same as your internal network.</span></span>

## <a name="see-also"></a><span data-ttu-id="07daa-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07daa-114">See also</span></span>

[<span data-ttu-id="07daa-115">用于会议的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="07daa-115">Components and Topologies for Conferencing</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)