---
title: 配置和管理 Skype for Business 云连接器版本
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ce323f4b-24e4-4ddf-84a3-67da82bb0c87
description: 了解如何配置 Skype 商务云连接器版，最少内部拓扑以启用内部部署语音基础结构与电话系统的 Skype 中的 Office 365 (云 PBX) 语音服务业务 online 的集成。
ms.openlocfilehash: 5d057a299e51bfb83bd6711fcf1fbe8b4ee98f02
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897996"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="3407c-103">配置和管理 Skype for Business 云连接器版本</span><span class="sxs-lookup"><span data-stu-id="3407c-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
<span data-ttu-id="3407c-104">了解如何配置 Skype 商务云连接器版，最少内部拓扑以启用内部部署语音基础结构与电话系统的 Skype 中的 Office 365 (云 PBX) 语音服务业务 online 的集成。</span><span class="sxs-lookup"><span data-stu-id="3407c-104">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System in Office 365 (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="3407c-105">在开始之前，您应查看中[规划 Skype 商业云连接器 edition](plan-skype-for-business-cloud-connector-edition.md)的先决条件。</span><span class="sxs-lookup"><span data-stu-id="3407c-105">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3407c-106">本主题中的步骤仅适用于云连接器版本 1.4.1 及更高版本。</span><span class="sxs-lookup"><span data-stu-id="3407c-106">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="3407c-107">如果你尚未升级到云连接器版本 2.1，请参阅[Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="3407c-107">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="3407c-108">您可以下载中的安装文件[https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)。</span><span class="sxs-lookup"><span data-stu-id="3407c-108">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="3407c-109">配置 Skype for Business 云连接器版本的步骤</span><span class="sxs-lookup"><span data-stu-id="3407c-109">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="3407c-110">下表列出了安装和配置云连接器版本所需执行的步骤：</span><span class="sxs-lookup"><span data-stu-id="3407c-110">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="3407c-111">**步骤**</span><span class="sxs-lookup"><span data-stu-id="3407c-111">**Step**</span></span>|<span data-ttu-id="3407c-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="3407c-112">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="3407c-113">准备云连接器设备</span><span class="sxs-lookup"><span data-stu-id="3407c-113">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="3407c-114">下载该安装文件、 准备证书、 配置 HYPER-V，和云连接器部署准备您的环境。</span><span class="sxs-lookup"><span data-stu-id="3407c-114">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="3407c-115">Deploy a single site in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="3407c-115">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="3407c-116">在云连接器部署中创建站点。</span><span class="sxs-lookup"><span data-stu-id="3407c-116">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="3407c-117">在云连接器中部署多个站点</span><span class="sxs-lookup"><span data-stu-id="3407c-117">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="3407c-118">向部署中添加站点，并了解单站点部署与多站点部署之间的差别。</span><span class="sxs-lookup"><span data-stu-id="3407c-118">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="3407c-119">Configure Cloud Connector integration with your Office 365 tenant</span><span class="sxs-lookup"><span data-stu-id="3407c-119">Configure Cloud Connector integration with your Office 365 tenant</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="3407c-120">添加 DNS 记录、配置混合连接、设置 PSTN 网关，并为用户启用 Office 365 中的电话系统语音邮件。</span><span class="sxs-lookup"><span data-stu-id="3407c-120">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System in Office 365 voice mail.</span></span>  <br/> |
|[<span data-ttu-id="3407c-121">Validate your Cloud Connector deployment</span><span class="sxs-lookup"><span data-stu-id="3407c-121">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="3407c-122">确保部署正常运行。</span><span class="sxs-lookup"><span data-stu-id="3407c-122">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="3407c-123">Upgrade to a new version of Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="3407c-123">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="3407c-124">将现有云连接器部署升级到 2.1 版。</span><span class="sxs-lookup"><span data-stu-id="3407c-124">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="3407c-125">Modify the configuration of an existing Cloud Connector deployment</span><span class="sxs-lookup"><span data-stu-id="3407c-125">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="3407c-126">已部署后，请更改云 Connector 中的设置。</span><span class="sxs-lookup"><span data-stu-id="3407c-126">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="3407c-127">在云连接器版本中部署媒体旁路</span><span class="sxs-lookup"><span data-stu-id="3407c-127">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="3407c-128">了解如何在云连接器中部署媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="3407c-128">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="3407c-129">Cloud Connector cmdlet reference</span><span class="sxs-lookup"><span data-stu-id="3407c-129">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="3407c-130">了解云连接器中使用的 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3407c-130">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="3407c-131">对云连接器部署进行故障排除</span><span class="sxs-lookup"><span data-stu-id="3407c-131">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="3407c-132">与云连接器部署中遇到的常见问题的解决方案。</span><span class="sxs-lookup"><span data-stu-id="3407c-132">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

