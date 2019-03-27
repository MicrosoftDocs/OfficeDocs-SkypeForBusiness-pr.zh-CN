---
title: 在 Skype for Business Server 2015 中安装持久聊天组件
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61370aa6-9708-4ff8-b531-b258a928806f
description: 摘要： 阅读本主题可了解如何使用业务 Server 部署向导的 Skype 安装 Skype 业务服务器 2015年组件和服务。
ms.openlocfilehash: 78fb134ef8db5b0c47c890db9454858ff392a624
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899552"
---
# <a name="install-persistent-chat-components-in-skype-for-business-server-2015"></a><span data-ttu-id="cc96d-103">在 Skype for Business Server 2015 中安装持久聊天组件</span><span class="sxs-lookup"><span data-stu-id="cc96d-103">Install Persistent Chat components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cc96d-104">**摘要：** 阅读本主题可了解如何使用业务 Server 部署向导的 Skype 安装 Skype 业务服务器 2015年组件和服务。</span><span class="sxs-lookup"><span data-stu-id="cc96d-104">**Summary:** Read this topic to learn how to use the Skype for Business Server Deployment Wizard to install Skype for Business Server 2015 components and services.</span></span>
  
<span data-ttu-id="cc96d-105">安装持久聊天组件之前，请确保您已安装系统必备的硬件和软件，并创建相应的拓扑以支持持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="cc96d-105">Before you install Persistent Chat components, be sure you have already installed prerequisite hardware and software, and created the appropriate topology to support Persistent Chat Server.</span></span> <span data-ttu-id="cc96d-106">有关规划和要求的详细信息，请参阅[Requirements for 您 Skype 业务环境](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)和[Plan for Persistent Chat Server in Skype 的业务服务器 2015年](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="cc96d-106">For details about planning and requirements, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="cc96d-107">有关如何更新和发布拓扑包括持久聊天服务器的信息，请参阅[将持久聊天服务器添加到您的业务服务器 2015年拓扑的 Skype](add-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="cc96d-107">For information about how to update and publish your topology to include Persistent Chat Server, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](add-persistent-chat-server.md).</span></span>
  
> [!NOTE] 
> <span data-ttu-id="cc96d-108">持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。</span><span class="sxs-lookup"><span data-stu-id="cc96d-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="cc96d-109">中团队提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="cc96d-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="cc96d-110">有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。</span><span class="sxs-lookup"><span data-stu-id="cc96d-110">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="cc96d-111">如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。</span><span class="sxs-lookup"><span data-stu-id="cc96d-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="install-and-start-services"></a><span data-ttu-id="cc96d-112">安装和启动服务</span><span class="sxs-lookup"><span data-stu-id="cc96d-112">Install and start services</span></span>

<span data-ttu-id="cc96d-113">使用 Skype 业务 Server 部署向导，选择安装或更新 Skype 业务 Server 系统，以执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="cc96d-113">Using the Skype for Business Server Deployment Wizard, choose Install or Update Skype for Business Server System to perform the following steps:</span></span> 
  
1. <span data-ttu-id="cc96d-114">安装本地配置存储</span><span class="sxs-lookup"><span data-stu-id="cc96d-114">Install Local Configuration Store</span></span>
    
2. <span data-ttu-id="cc96d-115">安装或删除 Skype for Business Server 组件</span><span class="sxs-lookup"><span data-stu-id="cc96d-115">Setup or Remove Skype for Business Server Components</span></span>
    
3. <span data-ttu-id="cc96d-116">请求、安装或分配证书</span><span class="sxs-lookup"><span data-stu-id="cc96d-116">Request, Install or Assign Certificates</span></span>
    
4. <span data-ttu-id="cc96d-117">启动服务</span><span class="sxs-lookup"><span data-stu-id="cc96d-117">Start services</span></span>
    
<span data-ttu-id="cc96d-118">有关如何使用部署向导安装组件的详细信息，分配证书，并启动服务，请参阅[的业务服务器 2015年安装 Skype](../../deploy/install/install.md)和[安装的拓扑中的服务器上的业务服务器 2015年的 Skype](../../deploy/install/install-skype-for-business-server.md)。</span><span class="sxs-lookup"><span data-stu-id="cc96d-118">For details on how to use the Deployment Wizard to install components, assign certificates, and start services, see [Install Skype for Business Server 2015](../../deploy/install/install.md) and [Install Skype for Business Server 2015 on servers in the topology](../../deploy/install/install-skype-for-business-server.md).</span></span>
  

