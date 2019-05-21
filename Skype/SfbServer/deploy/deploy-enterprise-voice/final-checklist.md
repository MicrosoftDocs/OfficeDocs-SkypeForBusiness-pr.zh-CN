---
title: 呼叫许可控制部署 Skype for Business 服务器的最终清单
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: 用于在 Skype for Business Server 企业语音中部署呼叫许可控制 (CAC) 的最终清单。
ms.openlocfilehash: fab6472d931d0475a3e3b0a0f413fce7775d7a15
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281588"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a><span data-ttu-id="083d1-103">呼叫许可控制部署: Skype for business 服务器的最终清单</span><span class="sxs-lookup"><span data-stu-id="083d1-103">Call admission control deployment: final checklist for Skype for Business Server</span></span>
 
<span data-ttu-id="083d1-104">用于在 Skype for Business Server 企业语音中部署呼叫许可控制 (CAC) 的最终清单。</span><span class="sxs-lookup"><span data-stu-id="083d1-104">Final checklist for deploying Call Admission Control (CAC) in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="083d1-105">使用以下检查表验证是否已完成部署呼叫允许控制 (CAC) 的所有必要配置任务。</span><span class="sxs-lookup"><span data-stu-id="083d1-105">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy Call Admission Control (CAC).</span></span>
  
- <span data-ttu-id="083d1-106">如果部署了一个或多个边缘服务器, 则每个外部接口 IP 地址都必须添加到网络配置设置中的子网列表中, 位掩码为32。</span><span class="sxs-lookup"><span data-stu-id="083d1-106">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="083d1-107">还应该将此子网（IP 地址）与在其中部署 A/V 边缘服务的地理位置的网络站点 ID 关联。</span><span class="sxs-lookup"><span data-stu-id="083d1-107">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="083d1-108">不需要边缘服务器实现 CAC。</span><span class="sxs-lookup"><span data-stu-id="083d1-108">Edge Servers are not required to implement CAC.</span></span> 
  
- <span data-ttu-id="083d1-109">请确保启用了 CAC, 如在[Skype For Business 服务器的 "启用呼叫许可控制](enable-call-admission-control.md)" 中所述。</span><span class="sxs-lookup"><span data-stu-id="083d1-109">Make sure that CAC is enabled, as specified in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
- <span data-ttu-id="083d1-110">确保已在所有中央站点启用 CAC。</span><span class="sxs-lookup"><span data-stu-id="083d1-110">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="083d1-111">这可以通过拓扑生成器完成。</span><span class="sxs-lookup"><span data-stu-id="083d1-111">This can be done through the Topology Builder.</span></span> <span data-ttu-id="083d1-112">如果发布时生成警告, 请*不要*忽略它。</span><span class="sxs-lookup"><span data-stu-id="083d1-112">If a warning is generated when you publish,  *do not*  ignore it.</span></span>
    
- <span data-ttu-id="083d1-113">确保已在网络配置设置中配置在企业网络中管理的所有子网。</span><span class="sxs-lookup"><span data-stu-id="083d1-113">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="083d1-114">每个子网都必须与网络网站相关联, 如在[Skype for business 中部署网络区域、网站和子网](deploy-network.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="083d1-114">It is also essential that every subnet be associated to a network site, as explained in [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
- <span data-ttu-id="083d1-115">确保已在网络配置设置中配置所有前端服务器、Survivable Branch Appliance (SBA)、音频/视频会议服务器（如果位于单独的池中）和中介服务器的子网或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="083d1-115">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>
    

