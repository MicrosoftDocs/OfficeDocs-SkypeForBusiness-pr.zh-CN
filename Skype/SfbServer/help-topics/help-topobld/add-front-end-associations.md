---
title: 添加前端关联
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndAssociationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95620425-defd-47fd-a5c0-e4a283d812a5
description: 您可以通过立即将服务器角色与前端池相关联，支持对需要部署其他服务器的特定功能的支持。 您还可以在以后将服务器角色与前端池相关联。 可以与前端池相关联的服务器角色包括以下各项：
ms.openlocfilehash: 13d796bd5c33b0f56ebc43ba11f82a188cce0c76
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218383"
---
# <a name="add-front-end-associations"></a><span data-ttu-id="61c06-105">添加前端关联</span><span class="sxs-lookup"><span data-stu-id="61c06-105">Add Front End Associations</span></span>

<span data-ttu-id="61c06-106">您可以通过立即将服务器角色与前端池相关联，支持对需要部署其他服务器的特定功能的支持。</span><span class="sxs-lookup"><span data-stu-id="61c06-106">You can enable support for specific features that require the deployment of other servers by associating the server roles with the Front End pool now.</span></span> <span data-ttu-id="61c06-107">您还可以在以后将服务器角色与前端池相关联。</span><span class="sxs-lookup"><span data-stu-id="61c06-107">You can also associate server roles with the Front End pool at a later time.</span></span> <span data-ttu-id="61c06-108">可以与前端池相关联的服务器角色包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="61c06-108">The server roles that can be associated with a Front End pool include the following:</span></span>

- <span data-ttu-id="61c06-109">A/V 边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="61c06-109">A/V Edge Server.</span></span> <span data-ttu-id="61c06-110">有关如何实现 A/V 边缘服务器的详细信息，请参阅规划文档中 [的规划会议](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="61c06-110">For details about the implementation of an A/V Edge Server, see [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) in the Planning documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="61c06-111">如果现在启用对上述任何功能的支持，您发布的拓扑设计将包含实现每个选定功能所需的服务器组件。</span><span class="sxs-lookup"><span data-stu-id="61c06-111">If you enable support for any of these features now, the topology design that you publish will include the server components that are required to implement each selected feature.</span></span> <span data-ttu-id="61c06-112">若要成功发布拓扑，而不出现错误，则必须将物理计算机加入域。</span><span class="sxs-lookup"><span data-stu-id="61c06-112">For the publishing of a topology to succeed without error, you must have the physical computers joined to the domain.</span></span> <span data-ttu-id="61c06-113">例如，如果现在启用对存档的支持，则必须先部署存档服务器并配置适当的存档选项，然后才能开始存档组织的通信。</span><span class="sxs-lookup"><span data-stu-id="61c06-113">For example, if you enable support for archiving now, you must then deploy an Archiving Server and configure the appropriate archiving options before you start archiving communications for your organization.</span></span>


