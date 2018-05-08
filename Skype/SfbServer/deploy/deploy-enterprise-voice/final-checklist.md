---
title: 呼叫允许控制最终的部署清单 Skype 的业务服务器 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: 业务 Server 企业语音部署呼叫允许控制 (CAC) Skype 中的最后一个清单。
ms.openlocfilehash: beec5c03f47d8f06ec862c3e9a3609fba7b66f2c
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server-2015"></a><span data-ttu-id="dea44-103">Skype for Business Server 2015 的呼叫允许控制部署：最终检查表</span><span class="sxs-lookup"><span data-stu-id="dea44-103">Call admission control deployment: final checklist for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="dea44-104">业务 Server 企业语音部署呼叫允许控制 (CAC) Skype 中的最后一个清单。</span><span class="sxs-lookup"><span data-stu-id="dea44-104">Final checklist for deploying Call Admission Control (CAC) in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="dea44-105">使用以下检查表验证是否已完成部署呼叫允许控制 (CAC) 的所有必要配置任务。</span><span class="sxs-lookup"><span data-stu-id="dea44-105">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy Call Admission Control (CAC).</span></span>
  
- <span data-ttu-id="dea44-106">如果部署了一个或多个边缘服务器，每个外部接口 IP 地址必须为添加到子网列表中的网络配置设置，32 位掩码。</span><span class="sxs-lookup"><span data-stu-id="dea44-106">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="dea44-107">还应该将此子网（IP 地址）与在其中部署 A/V 边缘服务的地理位置的网络站点 ID 关联。</span><span class="sxs-lookup"><span data-stu-id="dea44-107">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dea44-108">边缘服务器无需实现 CAC。</span><span class="sxs-lookup"><span data-stu-id="dea44-108">Edge Servers are not required to implement CAC.</span></span> 
  
- <span data-ttu-id="dea44-109">请确保已启用 CAC，为中指定[的业务服务器 2015 Skype 中启用呼叫允许控制](enable-call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="dea44-109">Make sure that CAC is enabled, as specified in [Enable call admission control in Skype for Business Server 2015](enable-call-admission-control.md).</span></span>
    
- <span data-ttu-id="dea44-110">确保已在所有中央站点启用 CAC。</span><span class="sxs-lookup"><span data-stu-id="dea44-110">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="dea44-111">这可以通过在拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="dea44-111">This can be done through the Topology Builder.</span></span> <span data-ttu-id="dea44-112">如果您发布时生成一条警告，则*不*忽略它。</span><span class="sxs-lookup"><span data-stu-id="dea44-112">If a warning is generated when you publish,  *do not*  ignore it.</span></span>
    
- <span data-ttu-id="dea44-113">确保已在网络配置设置中配置在企业网络中管理的所有子网。</span><span class="sxs-lookup"><span data-stu-id="dea44-113">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="dea44-114">也是必需的每个子网将关联到网络站点，如[部署网络区域、 站点和子网中的业务 2015 Skype](deploy-network.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="dea44-114">It is also essential that every subnet be associated to a network site, as explained in [Deploy network regions, sites and subnets in Skype for Business 2015](deploy-network.md).</span></span>
    
- <span data-ttu-id="dea44-115">确保已在网络配置设置中配置所有前端服务器、Survivable Branch Appliance (SBA)、音频/视频会议服务器（如果位于单独的池中）和中介服务器的子网或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="dea44-115">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>
    

