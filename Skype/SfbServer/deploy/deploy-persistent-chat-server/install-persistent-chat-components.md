---
title: 在 Skype for Business Server 2015 中安装持久聊天组件
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 61370aa6-9708-4ff8-b531-b258a928806f
description: 摘要：阅读本主题，了解如何使用 Skype for Business Server 部署向导安装 Skype for Business Server 2015 组件和服务。
ms.openlocfilehash: c3e68d5b5a41d06544f030df6877828da4b87c9e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802082"
---
# <a name="install-persistent-chat-components-in-skype-for-business-server-2015"></a><span data-ttu-id="c28e1-103">在 Skype for Business Server 2015 中安装持久聊天组件</span><span class="sxs-lookup"><span data-stu-id="c28e1-103">Install Persistent Chat components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c28e1-104">**摘要：** 阅读本主题，了解如何使用 Skype for Business Server 部署向导安装 Skype for Business Server 2015 组件和服务。</span><span class="sxs-lookup"><span data-stu-id="c28e1-104">**Summary:** Read this topic to learn how to use the Skype for Business Server Deployment Wizard to install Skype for Business Server 2015 components and services.</span></span>
  
<span data-ttu-id="c28e1-105">安装持久聊天组件之前，请确保已安装必备硬件和软件，并创建了相应的拓扑以支持持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="c28e1-105">Before you install Persistent Chat components, be sure you have already installed prerequisite hardware and software, and created the appropriate topology to support Persistent Chat Server.</span></span> <span data-ttu-id="c28e1-106">有关规划和要求的详细信息，请参阅 [Skype for Business 环境和](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) Plan for Persistent Chat Server in Skype for Business Server [2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)的要求。</span><span class="sxs-lookup"><span data-stu-id="c28e1-106">For details about planning and requirements, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="c28e1-107">若要了解如何更新和发布拓扑以包含持久聊天服务器，请参阅将持久聊天服务器添加到 [Skype for Business Server 2015 拓扑](add-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="c28e1-107">For information about how to update and publish your topology to include Persistent Chat Server, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](add-persistent-chat-server.md).</span></span>
  
> [!NOTE] 
> <span data-ttu-id="c28e1-108">持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="c28e1-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="c28e1-109">Teams 中也提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="c28e1-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="c28e1-110">有关详细信息，请参阅 [Microsoft Teams](/microsoftteams/upgrade-start-here)升级入门。</span><span class="sxs-lookup"><span data-stu-id="c28e1-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="c28e1-111">如果你需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="c28e1-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="install-and-start-services"></a><span data-ttu-id="c28e1-112">安装和启动服务</span><span class="sxs-lookup"><span data-stu-id="c28e1-112">Install and start services</span></span>

<span data-ttu-id="c28e1-113">使用 Skype for Business Server 部署向导，选择"安装或更新 Skype for Business Server 系统"以执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c28e1-113">Using the Skype for Business Server Deployment Wizard, choose Install or Update Skype for Business Server System to perform the following steps:</span></span> 
  
1. <span data-ttu-id="c28e1-114">安装本地配置存储</span><span class="sxs-lookup"><span data-stu-id="c28e1-114">Install Local Configuration Store</span></span>
    
2. <span data-ttu-id="c28e1-115">安装或删除 Skype for Business Server 组件</span><span class="sxs-lookup"><span data-stu-id="c28e1-115">Setup or Remove Skype for Business Server Components</span></span>
    
3. <span data-ttu-id="c28e1-116">请求、安装或分配证书</span><span class="sxs-lookup"><span data-stu-id="c28e1-116">Request, Install or Assign Certificates</span></span>
    
4. <span data-ttu-id="c28e1-117">启动服务</span><span class="sxs-lookup"><span data-stu-id="c28e1-117">Start services</span></span>
    
<span data-ttu-id="c28e1-118">有关如何使用部署向导安装组件、分配证书和启动服务的详细信息，请参阅在拓扑中的服务器上安装[Skype for Business Server 2015](../../deploy/install/install.md)和安装[Skype for Business Server 2015。](../../deploy/install/install-skype-for-business-server.md)</span><span class="sxs-lookup"><span data-stu-id="c28e1-118">For details on how to use the Deployment Wizard to install components, assign certificates, and start services, see [Install Skype for Business Server 2015](../../deploy/install/install.md) and [Install Skype for Business Server 2015 on servers in the topology](../../deploy/install/install-skype-for-business-server.md).</span></span>
  

