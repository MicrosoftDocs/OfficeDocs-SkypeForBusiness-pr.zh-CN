---
title: " (CQD) 创建通话质量仪表板的构建地图"
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: 了解如何创建可用于在通话质量仪表板 (CQD) 中上载租户和生成数据的构建地图。
ms.openlocfilehash: 890e5e9b394cf8b600e635014c90ebb9053a1e07
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584031"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a><span data-ttu-id="4fb3b-103"> (CQD) 创建通话质量仪表板的构建地图</span><span class="sxs-lookup"><span data-stu-id="4fb3b-103">Create a building map for Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="4fb3b-104">在 Microsoft 团队或 Skype for business Online 部署中，所有客户端都是外部客户端。</span><span class="sxs-lookup"><span data-stu-id="4fb3b-104">In a Microsoft Teams or Skype for Business Online deployment, all clients are external.</span></span> <span data-ttu-id="4fb3b-105">因此，默认情况下，所有客户在呼叫质量仪表板 (CQD) 中报告为外部，无论客户是否连接到内部公司网络。</span><span class="sxs-lookup"><span data-stu-id="4fb3b-105">As a result, by default, all clients are reported as outside in Call Quality Dashboard (CQD), regardless of whether the client is connected on an internal corporate network.</span></span>

<span data-ttu-id="4fb3b-106">使用 CQD 时，你需要知道终结点的位置以及它是否已连接到你可以管理的网络或无法管理的网络，假定你只能改进你可以管理的网络。</span><span class="sxs-lookup"><span data-stu-id="4fb3b-106">When you work with CQD, you need to know the location of an endpoint and whether it was connected to a network you can manage or a network you can't manage, the assumption being that you can only improve networks you can manage.</span></span> <span data-ttu-id="4fb3b-107">通过将子网和生成信息上载到 CQD，你可以启用 CQD 以确定终结点是连接到内部 (托管) 网络还是外部 (非托管) 网络。</span><span class="sxs-lookup"><span data-stu-id="4fb3b-107">By uploading subnet and building information to CQD, you enable CQD to determine whether the endpoint was connected to an internal (managed) network or to an external (unmanaged) network.</span></span> <span data-ttu-id="4fb3b-108">这就是为您的组织创建建筑地图并[将其上传到 CQD](CQD-upload-tenant-building-data.md)非常重要的原因。</span><span class="sxs-lookup"><span data-stu-id="4fb3b-108">That's why it's important to create a building map for your organization and [upload it to CQD](CQD-upload-tenant-building-data.md).</span></span>

## <a name="building-mapping-tools"></a><span data-ttu-id="4fb3b-109">构建地图工具</span><span class="sxs-lookup"><span data-stu-id="4fb3b-109">Building mapping tools</span></span>

<span data-ttu-id="4fb3b-110">可通过多种方式来映射组织的子网。</span><span class="sxs-lookup"><span data-stu-id="4fb3b-110">There are many ways to map your organization's subnets.</span></span> <span data-ttu-id="4fb3b-111">如果需要帮助，您可以使用此[博客文章](https://aka.ms/cqdtools)中介绍的 CQDTools PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="4fb3b-111">If you need help, you can use the CQDTools PowerShell Module described in this [blog post](https://aka.ms/cqdtools).</span></span> <span data-ttu-id="4fb3b-112">这些工具基于 PowerShell，并使用 Active Directory (AD) 网站和服务以及 Microsoft DHCP 服务来帮助预填充你的构建文件。</span><span class="sxs-lookup"><span data-stu-id="4fb3b-112">These tools are based on PowerShell and use Active Directory (AD) Sites and Services and Microsoft DHCP services to help pre-populate your building file.</span></span> <span data-ttu-id="4fb3b-113">这些工具将帮助你执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="4fb3b-113">These tools will help with the following tasks:</span></span>

1. <span data-ttu-id="4fb3b-114">查询广告网站和服务，并基于其中包含的信息创建构建文件。</span><span class="sxs-lookup"><span data-stu-id="4fb3b-114">Query AD Sites and Services, and create a building file based on the information contained within.</span></span>
1. <span data-ttu-id="4fb3b-115">查询 Microsoft DHCP 服务器或服务器以提取子网信息并自动创建构建文件。</span><span class="sxs-lookup"><span data-stu-id="4fb3b-115">Query a Microsoft DHCP server or servers to pull subnet information and automatically create a building file.</span></span>
1. <span data-ttu-id="4fb3b-116">验证现有生成文件、检查重复项和重叠。</span><span class="sxs-lookup"><span data-stu-id="4fb3b-116">Validate an existing building file, checking for duplicates and overlaps.</span></span>
1. <span data-ttu-id="4fb3b-117">在 CQD 中查找未映射的子网。</span><span class="sxs-lookup"><span data-stu-id="4fb3b-117">Find unmapped subnets in CQD.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4fb3b-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="4fb3b-118">Related topics</span></span>

[<span data-ttu-id="4fb3b-119">在 CQD 中上载租户和构建数据</span><span class="sxs-lookup"><span data-stu-id="4fb3b-119">Upload tenant and building data in CQD</span></span>](CQD-upload-tenant-building-data.md)