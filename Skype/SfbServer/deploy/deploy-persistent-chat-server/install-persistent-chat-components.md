---
title: 在 Skype for Business Server 2015 中安装持久聊天组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61370aa6-9708-4ff8-b531-b258a928806f
description: '摘要: 阅读本主题, 了解如何使用 Skype for business 服务器部署向导安装 Skype for business Server 2015 组件和服务。'
ms.openlocfilehash: 6c30ba33f1ff22b5088080048210c7dcb862cb3b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273802"
---
# <a name="install-persistent-chat-components-in-skype-for-business-server-2015"></a><span data-ttu-id="aeb67-103">在 Skype for Business Server 2015 中安装持久聊天组件</span><span class="sxs-lookup"><span data-stu-id="aeb67-103">Install Persistent Chat components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="aeb67-104">**摘要:** 阅读本主题, 了解如何使用 Skype for Business 服务器部署向导安装 Skype for business Server 2015 组件和服务。</span><span class="sxs-lookup"><span data-stu-id="aeb67-104">**Summary:** Read this topic to learn how to use the Skype for Business Server Deployment Wizard to install Skype for Business Server 2015 components and services.</span></span>
  
<span data-ttu-id="aeb67-105">在安装持久聊天组件之前, 请确保已安装必备硬件和软件, 并创建适当的拓扑以支持持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="aeb67-105">Before you install Persistent Chat components, be sure you have already installed prerequisite hardware and software, and created the appropriate topology to support Persistent Chat Server.</span></span> <span data-ttu-id="aeb67-106">有关规划和要求的详细信息, 请参阅 skype for business[环境要求](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)和[Skype for business server 2015 中的持久聊天服务器计划](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="aeb67-106">For details about planning and requirements, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="aeb67-107">有关如何更新和发布拓扑以包括持久聊天服务器的信息, 请参阅[将持久聊天服务器添加到 Skype for Business server 2015 拓扑](add-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="aeb67-107">For information about how to update and publish your topology to include Persistent Chat Server, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](add-persistent-chat-server.md).</span></span>
  
> [!NOTE] 
> <span data-ttu-id="aeb67-108">Skype for business Server 2015 中提供了持久聊天, 但 Skype for business Server 2019 不再支持此功能。</span><span class="sxs-lookup"><span data-stu-id="aeb67-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="aeb67-109">团队中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="aeb67-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="aeb67-110">有关详细信息, 请参阅[从 Skype For Business 迁移到 Microsoft 团队](/microsoftteams/journey-skypeforbusiness-teams)。</span><span class="sxs-lookup"><span data-stu-id="aeb67-110">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="aeb67-111">如果需要使用持久聊天, 您可以选择将需要此功能的用户迁移到团队, 或继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="aeb67-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="install-and-start-services"></a><span data-ttu-id="aeb67-112">安装和启动服务</span><span class="sxs-lookup"><span data-stu-id="aeb67-112">Install and start services</span></span>

<span data-ttu-id="aeb67-113">使用 Skype for Business 服务器部署向导, 选择 "安装或更新 Skype for business 服务器系统" 以执行以下步骤:</span><span class="sxs-lookup"><span data-stu-id="aeb67-113">Using the Skype for Business Server Deployment Wizard, choose Install or Update Skype for Business Server System to perform the following steps:</span></span> 
  
1. <span data-ttu-id="aeb67-114">安装本地配置存储</span><span class="sxs-lookup"><span data-stu-id="aeb67-114">Install Local Configuration Store</span></span>
    
2. <span data-ttu-id="aeb67-115">安装或删除 Skype for Business Server 组件</span><span class="sxs-lookup"><span data-stu-id="aeb67-115">Setup or Remove Skype for Business Server Components</span></span>
    
3. <span data-ttu-id="aeb67-116">请求、安装或分配证书</span><span class="sxs-lookup"><span data-stu-id="aeb67-116">Request, Install or Assign Certificates</span></span>
    
4. <span data-ttu-id="aeb67-117">启动服务</span><span class="sxs-lookup"><span data-stu-id="aeb67-117">Start services</span></span>
    
<span data-ttu-id="aeb67-118">有关如何使用部署向导安装组件、分配证书和启动服务的详细信息, 请参阅在拓扑中[安装 skype for Business server 2015](../../deploy/install/install.md)和[安装 Skype for business server 2015](../../deploy/install/install-skype-for-business-server.md)。</span><span class="sxs-lookup"><span data-stu-id="aeb67-118">For details on how to use the Deployment Wizard to install components, assign certificates, and start services, see [Install Skype for Business Server 2015](../../deploy/install/install.md) and [Install Skype for Business Server 2015 on servers in the topology](../../deploy/install/install-skype-for-business-server.md).</span></span>
  

