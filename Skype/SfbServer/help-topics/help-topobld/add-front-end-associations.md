---
title: 添加前端关联
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 通过将服务器角色与前端池关联，可以启用对需要部署其他服务器的特定功能的支持。 还可以稍后将服务器角色与前端池关联。 可以与前端池关联的服务器角色包括：
ms.openlocfilehash: 8ff7d11a40f7eccfda78643fd8b3a17146c014d7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103248"
---
# <a name="add-front-end-associations"></a><span data-ttu-id="433b9-105">添加前端关联</span><span class="sxs-lookup"><span data-stu-id="433b9-105">Add Front End Associations</span></span>

<span data-ttu-id="433b9-106">通过将服务器角色与前端池关联，可以启用对需要部署其他服务器的特定功能的支持。</span><span class="sxs-lookup"><span data-stu-id="433b9-106">You can enable support for specific features that require the deployment of other servers by associating the server roles with the Front End pool now.</span></span> <span data-ttu-id="433b9-107">还可以稍后将服务器角色与前端池关联。</span><span class="sxs-lookup"><span data-stu-id="433b9-107">You can also associate server roles with the Front End pool at a later time.</span></span> <span data-ttu-id="433b9-108">可以与前端池关联的服务器角色包括：</span><span class="sxs-lookup"><span data-stu-id="433b9-108">The server roles that can be associated with a Front End pool include the following:</span></span>

- <span data-ttu-id="433b9-109">A/V 边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="433b9-109">A/V Edge Server.</span></span> <span data-ttu-id="433b9-110">有关 A/V 边缘服务器的实现的详细信息，请参阅规划文档中 [的](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing) 规划会议。</span><span class="sxs-lookup"><span data-stu-id="433b9-110">For details about the implementation of an A/V Edge Server, see [Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing) in the Planning documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="433b9-111">如果现在启用对这些功能的任何支持，则发布的拓扑设计将包括实现每个选定功能所需的服务器组件。</span><span class="sxs-lookup"><span data-stu-id="433b9-111">If you enable support for any of these features now, the topology design that you publish will include the server components that are required to implement each selected feature.</span></span> <span data-ttu-id="433b9-112">若要成功发布拓扑而不出现错误，必须将物理计算机加入域。</span><span class="sxs-lookup"><span data-stu-id="433b9-112">For the publishing of a topology to succeed without error, you must have the physical computers joined to the domain.</span></span> <span data-ttu-id="433b9-113">例如，如果现在启用存档支持，则必须先部署存档服务器并配置相应的存档选项，然后再开始为组织存档通信。</span><span class="sxs-lookup"><span data-stu-id="433b9-113">For example, if you enable support for archiving now, you must then deploy an Archiving Server and configure the appropriate archiving options before you start archiving communications for your organization.</span></span>