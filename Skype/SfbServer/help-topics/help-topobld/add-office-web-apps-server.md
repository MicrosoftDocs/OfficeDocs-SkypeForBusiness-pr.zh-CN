---
title: 添加 Office Web Apps Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: "\"定义新的 Office Web Apps\" 向导在你的部署中定义新的 Office Web Apps 服务器。 请填写以下信息："
ms.openlocfilehash: d1b36a2146d6be0addd9b66fd02665eee8de907d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275197"
---
# <a name="add-office-web-apps-server"></a><span data-ttu-id="aadcd-104">添加 Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="aadcd-104">Add Office Web Apps Server</span></span>

<span data-ttu-id="aadcd-105">"**定义新的 Office Web apps** " 向导在你的部署中定义新的 Office Web apps 服务器。</span><span class="sxs-lookup"><span data-stu-id="aadcd-105">The **Define New Office Web Apps Server** wizard defines a new Office Web Apps Server in your deployment.</span></span> <span data-ttu-id="aadcd-106">请填写以下信息：</span><span class="sxs-lookup"><span data-stu-id="aadcd-106">You fill in the following information:</span></span>

 <span data-ttu-id="aadcd-107">**Office Web Apps 服务器 FQDN**: 键入将承载 Office Web Apps 服务器的服务器的完全限定的域名</span><span class="sxs-lookup"><span data-stu-id="aadcd-107">**Office Web Apps Server FQDN**: Type the fully qualified domain name of the server that will host the Office Web Apps Server</span></span>

 <span data-ttu-id="aadcd-108">**Office Web Apps 服务器发现 URL**: 键入 Office Web apps 服务器的完整统一资源定位器 (URL)</span><span class="sxs-lookup"><span data-stu-id="aadcd-108">**Office Web Apps Server discovery URL**: Type the full uniform resource locator (URL) of the Office Web Apps Server</span></span>

> [!TIP]
> <span data-ttu-id="aadcd-109">**Office Web Apps 服务器发现 url**的默认行为是基于 Office Web apps 服务器的 FQDN 创建 URL, 格式如下: `https://<FQDN of the Office Web Apps Server/hosting/discovery` 。</span><span class="sxs-lookup"><span data-stu-id="aadcd-109">The default behavior of the **Office Web Apps Server discovery URL** is to create the URL based on the FQDN of the Office Web Apps Server in the format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span></span> <span data-ttu-id="aadcd-110">在大多数情况下，不需要更改默认格式。</span><span class="sxs-lookup"><span data-stu-id="aadcd-110">In most cases you will not need to change the default format.</span></span> <span data-ttu-id="aadcd-111">在 Office Web Apps 服务器和 Office Web Apps 服务器发现 URL 必须不同的情况下, 可能需要更改默认格式。</span><span class="sxs-lookup"><span data-stu-id="aadcd-111">You may need to change the default format in the event that the Office Web Apps Server and the Office Web Apps Server discovery URL must be different.</span></span> <span data-ttu-id="aadcd-112">例如, 你的 Office Web Apps 服务器位于外围网络中, 并且将具有基于该位置的其他 URL。</span><span class="sxs-lookup"><span data-stu-id="aadcd-112">For example, your Office Web Apps Server is placed in the perimeter network and will have a different URL based on the location.</span></span>

 <span data-ttu-id="aadcd-113">**Office Web Apps 服务器部署在外部网络 (即, 圆周/Internet) 中**: 如果你的 Office Web apps 服务器位于内部防火墙之外 (如外围网络、外部网络或其他网络区域), 请选中该复选框这与您的内部网络不同。</span><span class="sxs-lookup"><span data-stu-id="aadcd-113">**Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**: Select the check box if your Office Web Apps Server is placed outside of your internal firewall, such as the perimeter network, external network, or other network zone that is not the same as your internal network.</span></span>

## <a name="see-also"></a><span data-ttu-id="aadcd-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aadcd-114">See also</span></span>

[<span data-ttu-id="aadcd-115">Components and Topologies for Conferencing</span><span class="sxs-lookup"><span data-stu-id="aadcd-115">Components and Topologies for Conferencing</span></span>](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
