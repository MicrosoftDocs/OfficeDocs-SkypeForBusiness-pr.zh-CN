---
title: 添加 Office Web Apps Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 定义新 Office Web Apps Server 向导定义新的 Office Web Apps Server 部署中。 请填写以下信息：
ms.openlocfilehash: 34f8f1b58cc6d937432b667a110eb805dd5a2c88
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23245766"
---
# <a name="add-office-web-apps-server"></a><span data-ttu-id="d7fb8-104">添加 Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="d7fb8-104">Add Office Web Apps Server</span></span>

<span data-ttu-id="d7fb8-105">**定义新 Office Web Apps Server**向导定义新的 Office Web Apps Server 部署中。</span><span class="sxs-lookup"><span data-stu-id="d7fb8-105">The **Define New Office Web Apps Server** wizard defines a new Office Web Apps Server in your deployment.</span></span> <span data-ttu-id="d7fb8-106">请填写以下信息：</span><span class="sxs-lookup"><span data-stu-id="d7fb8-106">You fill in the following information:</span></span>

 <span data-ttu-id="d7fb8-107">**Office Web Apps 服务器 FQDN**： 键入将承载 Office Web Apps Server 的服务器的完全限定的域名</span><span class="sxs-lookup"><span data-stu-id="d7fb8-107">**Office Web Apps Server FQDN**: Type the fully qualified domain name of the server that will host the Office Web Apps Server</span></span>

 <span data-ttu-id="d7fb8-108">**Office Web Apps 服务器发现 URL**： 键入 Office Web Apps Server 的完全统一资源定位器 (URL)</span><span class="sxs-lookup"><span data-stu-id="d7fb8-108">**Office Web Apps Server discovery URL**: Type the full uniform resource locator (URL) of the Office Web Apps Server</span></span>

> [!TIP]
> <span data-ttu-id="d7fb8-109">**Office Web Apps 服务器发现 URL**的默认行为是创建基于格式的 Office Web Apps Server 的 FQDN 的 URL: `https://<FQDN of the Office Web Apps Server/hosting/discovery` 。</span><span class="sxs-lookup"><span data-stu-id="d7fb8-109">The default behavior of the **Office Web Apps Server discovery URL** is to create the URL based on the FQDN of the Office Web Apps Server in the format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span></span> <span data-ttu-id="d7fb8-110">在大多数情况下，不需要更改默认格式。</span><span class="sxs-lookup"><span data-stu-id="d7fb8-110">In most cases you will not need to change the default format.</span></span> <span data-ttu-id="d7fb8-111">您可能需要更改默认格式中的 Office Web Apps Server 和 Office Web Apps 服务器发现 URL 必须不同。</span><span class="sxs-lookup"><span data-stu-id="d7fb8-111">You may need to change the default format in the event that the Office Web Apps Server and the Office Web Apps Server discovery URL must be different.</span></span> <span data-ttu-id="d7fb8-112">例如，您的 Office Web Apps Server 位于外围网络中，并将具有不同基于位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="d7fb8-112">For example, your Office Web Apps Server is placed in the perimeter network and will have a different URL based on the location.</span></span>

 <span data-ttu-id="d7fb8-113">**在外部网络 (即，外围 /internet) 中部署 office Web Apps Server**： 如果您的 Office Web Apps Server 发出您的内部防火墙，如外围网络、 外部网络或其他网络区域之外选中复选框这不是内部网络相同。</span><span class="sxs-lookup"><span data-stu-id="d7fb8-113">**Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**: Select the check box if your Office Web Apps Server is placed outside of your internal firewall, such as the perimeter network, external network, or other network zone that is not the same as your internal network.</span></span>

## <a name="see-also"></a><span data-ttu-id="d7fb8-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7fb8-114">See also</span></span>

[<span data-ttu-id="d7fb8-115">会议的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="d7fb8-115">Components and Topologies for Conferencing</span></span>](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)