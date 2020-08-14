---
title: 配置和管理 Skype for Business 云连接器版本
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ce323f4b-24e4-4ddf-84a3-67da82bb0c87
description: 了解如何配置 Skype for Business 云连接器版本（最小本地拓扑），以便能够将本地语音基础结构与 Skype for Business Online 中的电话系统 (云 PBX) 语音服务集成。
ms.openlocfilehash: a7c157836497383d89055f8ab986aa15f7e11870
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219512"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="b6278-103">配置和管理 Skype for Business 云连接器版本</span><span class="sxs-lookup"><span data-stu-id="b6278-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
<span data-ttu-id="b6278-104">了解如何配置 Skype for Business 云连接器版本（最小本地拓扑），以便能够将本地语音基础结构与 Skype for Business Online 中的电话系统 (云 PBX) 语音服务集成。</span><span class="sxs-lookup"><span data-stu-id="b6278-104">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="b6278-105">在开始之前，应查看 [Plan For Skype For Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)中的先决条件。</span><span class="sxs-lookup"><span data-stu-id="b6278-105">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b6278-106">本主题中的步骤仅适用于云连接器版本1.4.1 和更高版本。</span><span class="sxs-lookup"><span data-stu-id="b6278-106">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="b6278-107">如果尚未升级到云连接器版本2.1，请参阅 [升级到新版本的云连接器](upgrade-to-a-new-version-of-cloud-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="b6278-107">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="b6278-108">您可以从下载安装文件 [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) 。</span><span class="sxs-lookup"><span data-stu-id="b6278-108">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="b6278-109">配置 Skype for Business 云连接器版本的步骤</span><span class="sxs-lookup"><span data-stu-id="b6278-109">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="b6278-110">下表列出了安装和配置云连接器版本所需的步骤：</span><span class="sxs-lookup"><span data-stu-id="b6278-110">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="b6278-111">**步骤**</span><span class="sxs-lookup"><span data-stu-id="b6278-111">**Step**</span></span>|<span data-ttu-id="b6278-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="b6278-112">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="b6278-113">准备云连接器设备</span><span class="sxs-lookup"><span data-stu-id="b6278-113">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="b6278-114">下载安装文件、准备证书、配置 Hyper-v，并让你的环境为你的云连接器部署做好准备。</span><span class="sxs-lookup"><span data-stu-id="b6278-114">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="b6278-115">在云连接器中部署单个站点</span><span class="sxs-lookup"><span data-stu-id="b6278-115">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="b6278-116">在你的云连接器部署中创建网站。</span><span class="sxs-lookup"><span data-stu-id="b6278-116">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="b6278-117">在云连接器中部署多个站点</span><span class="sxs-lookup"><span data-stu-id="b6278-117">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="b6278-118">将网站添加到部署，并了解单站点部署与多站点部署之间的差异。</span><span class="sxs-lookup"><span data-stu-id="b6278-118">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="b6278-119">配置与 Microsoft 365 或 Office 365 组织的云连接器集成</span><span class="sxs-lookup"><span data-stu-id="b6278-119">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="b6278-120">添加 DNS 记录，配置混合配置，设置 PSTN 网关，并为用户启用电话系统语音邮件。</span><span class="sxs-lookup"><span data-stu-id="b6278-120">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System voice mail.</span></span>  <br/> |
|[<span data-ttu-id="b6278-121">验证云连接器部署</span><span class="sxs-lookup"><span data-stu-id="b6278-121">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="b6278-122">请确保您的部署正常运行。</span><span class="sxs-lookup"><span data-stu-id="b6278-122">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="b6278-123">升级至新版本的云连接器</span><span class="sxs-lookup"><span data-stu-id="b6278-123">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="b6278-124">将现有云连接器部署升级到版本2.1。</span><span class="sxs-lookup"><span data-stu-id="b6278-124">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="b6278-125">修改现有云连接器部署的配置</span><span class="sxs-lookup"><span data-stu-id="b6278-125">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="b6278-126">在云连接器中更改已部署的设置后对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="b6278-126">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="b6278-127">在云连接器版本中部署媒体旁路</span><span class="sxs-lookup"><span data-stu-id="b6278-127">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="b6278-128">了解如何在云连接器中部署媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="b6278-128">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="b6278-129">云连接器 cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="b6278-129">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="b6278-130">了解在云连接器中使用的 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b6278-130">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="b6278-131">对云连接器部署进行故障排除</span><span class="sxs-lookup"><span data-stu-id="b6278-131">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="b6278-132">部署云连接器时遇到的常见问题的解决方案。</span><span class="sxs-lookup"><span data-stu-id="b6278-132">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

