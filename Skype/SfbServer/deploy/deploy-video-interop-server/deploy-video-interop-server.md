---
title: 在 Skype for Business Server 2015 中部署视频互操作服务器
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bb7d2abd-d033-4d7d-b588-6d9228c3eccf
description: 摘要： 为业务服务器 2015年部署在 Skype 的 VIS 的服务器角色。
ms.openlocfilehash: 0716ce427814c7cf17385074727a7af4f45cfd66
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-video-interop-server-in-skype-for-business-server-2015"></a><span data-ttu-id="66c36-103">在 Skype for Business Server 2015 中部署视频互操作服务器</span><span class="sxs-lookup"><span data-stu-id="66c36-103">Deploy Video Interop Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="66c36-104">**摘要：**为业务服务器 2015年部署在 Skype 的 VIS 的服务器角色。</span><span class="sxs-lookup"><span data-stu-id="66c36-104">**Summary:** Deploy the VIS server role in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="66c36-105">Skype 业务服务器现在可以直接与 Cisco 远程会议系统 (VTCs)，例如 Cisco C60 或 Cisco MX300 集成。</span><span class="sxs-lookup"><span data-stu-id="66c36-105">Skype for Business Server can now integrate directly with Cisco teleconferencing systems (VTCs) such as the Cisco C60 or Cisco MX300.</span></span> <span data-ttu-id="66c36-106">这就要求引入新的服务器角色称为视频互操作服务器 (VIS) 和 VIS 和设备的正确配置将与互操作。</span><span class="sxs-lookup"><span data-stu-id="66c36-106">This requires the introduction of a new server role called the Video Interop Server (VIS), and correct configuration of both the VIS and the equipment it will interoperate with.</span></span> <span data-ttu-id="66c36-107">VTC 注册现有 Cisco 基础结构（比如 Cisco Unified Communication Manager (CUCM)），在 CUCM 和 VIS 池之间使用视频 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="66c36-107">A VTC registers with existing Cisco infrastructure such as Cisco Unified Communication Manager (CUCM), and a video SIP trunk is used between CUCM and the VIS pool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="66c36-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="66c36-108">In this section</span></span>

<span data-ttu-id="66c36-109">要在 VIS 服务器或池与 VTC 系统之间配置互操作性，必须执行以下五个步骤：</span><span class="sxs-lookup"><span data-stu-id="66c36-109">Configuring interoperability between a VIS server or pool and VTC systems requires performing the following five procedures:</span></span> 
  
- [<span data-ttu-id="66c36-110">在 Skype 的 VIS 池创建的业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="66c36-110">Create a VIS pool in Skype for Business Server 2015</span></span>](create-a-vis-pool.md)
    
- [<span data-ttu-id="66c36-111">为业务服务器 2015年部署在 Skype 的 VIS 服务器角色</span><span class="sxs-lookup"><span data-stu-id="66c36-111">Deploy the VIS server role in Skype for Business Server 2015</span></span>](deploy-the-vis-server-role.md)
    
- [<span data-ttu-id="66c36-112">在 Skype 为业务服务器 2015年配置互操作的视频服务器</span><span class="sxs-lookup"><span data-stu-id="66c36-112">Configure the Video Interop Server in Skype for Business Server 2015</span></span>](configure-the-vis.md)
    
- [<span data-ttu-id="66c36-113">将 CUCM 配置为与 Skype 业务服务器 2015年的互操作</span><span class="sxs-lookup"><span data-stu-id="66c36-113">Configure CUCM for Interoperation with Skype for Business Server 2015</span></span>](configure-cucm-for-interoperation.md)
    
- [<span data-ttu-id="66c36-114">配置 VTC Skype 业务服务器 2015年的互操作</span><span class="sxs-lookup"><span data-stu-id="66c36-114">Configure a VTC for Interoperation with Skype for Business Server 2015</span></span>](configure-a-vtc-for-interoperation.md)
    
## <a name="related-sections"></a><span data-ttu-id="66c36-115">相关的章节</span><span class="sxs-lookup"><span data-stu-id="66c36-115">Related sections</span></span>

[<span data-ttu-id="66c36-116">在 Skype 的视频互操作服务器业务服务器 2015年计划</span><span class="sxs-lookup"><span data-stu-id="66c36-116">Plan for Video Interop Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/video-interop-server.md)
  

