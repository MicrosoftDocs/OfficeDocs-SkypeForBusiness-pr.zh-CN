---
title: 为业务服务器部署中 Skype 视频互操作性的服务器
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bb7d2abd-d033-4d7d-b588-6d9228c3eccf
description: 摘要： 业务服务器部署中 Skype VIS 服务器角色。
ms.openlocfilehash: 3f3c48279ba08ca124f11ac0fb90c457ae69ac9d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884555"
---
# <a name="deploy-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="53f46-103">为业务服务器部署中 Skype 视频互操作性的服务器</span><span class="sxs-lookup"><span data-stu-id="53f46-103">Deploy Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="53f46-104">**摘要：** 为业务 Server 部署中 Skype VIS 服务器角色。</span><span class="sxs-lookup"><span data-stu-id="53f46-104">**Summary:** Deploy the VIS server role in Skype for Business Server.</span></span>
  
<span data-ttu-id="53f46-105">Skype 业务服务器现在可以直接与如 Cisco C60 或 Cisco MX300 Cisco 电话会议系统 (VTCs) 集成。</span><span class="sxs-lookup"><span data-stu-id="53f46-105">Skype for Business Server can now integrate directly with Cisco teleconferencing systems (VTCs) such as the Cisco C60 or Cisco MX300.</span></span> <span data-ttu-id="53f46-106">这需要新的服务器角色调用的视频互操作服务器 (VIS) 和正确配置 VIS 和设备与将互操作的介绍。</span><span class="sxs-lookup"><span data-stu-id="53f46-106">This requires the introduction of a new server role called the Video Interop Server (VIS), and correct configuration of both the VIS and the equipment it will interoperate with.</span></span> <span data-ttu-id="53f46-107">VTC 注册现有 Cisco 基础结构（比如 Cisco Unified Communication Manager (CUCM)），在 CUCM 和 VIS 池之间使用视频 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="53f46-107">A VTC registers with existing Cisco infrastructure such as Cisco Unified Communication Manager (CUCM), and a video SIP trunk is used between CUCM and the VIS pool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="53f46-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="53f46-108">In this section</span></span>

<span data-ttu-id="53f46-109">要在 VIS 服务器或池与 VTC 系统之间配置互操作性，必须执行以下五个步骤：</span><span class="sxs-lookup"><span data-stu-id="53f46-109">Configuring interoperability between a VIS server or pool and VTC systems requires performing the following five procedures:</span></span> 
  
- [<span data-ttu-id="53f46-110">为 Business Server Skype 创建 VIS 池</span><span class="sxs-lookup"><span data-stu-id="53f46-110">Create a VIS pool in Skype for Business Server</span></span>](create-a-vis-pool.md)
    
- [<span data-ttu-id="53f46-111">为业务服务器部署中 Skype VIS 服务器角色</span><span class="sxs-lookup"><span data-stu-id="53f46-111">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)
    
- [<span data-ttu-id="53f46-112">为业务 Server Skype 中配置视频互操作性服务器</span><span class="sxs-lookup"><span data-stu-id="53f46-112">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
    
- [<span data-ttu-id="53f46-113">为业务服务器与 Skype 的互操作配置 CUCM</span><span class="sxs-lookup"><span data-stu-id="53f46-113">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
    
- [<span data-ttu-id="53f46-114">为业务服务器与 Skype 的互操作配置 VTC</span><span class="sxs-lookup"><span data-stu-id="53f46-114">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
    
## <a name="related-sections"></a><span data-ttu-id="53f46-115">相关的章节</span><span class="sxs-lookup"><span data-stu-id="53f46-115">Related sections</span></span>

[<span data-ttu-id="53f46-116">规划视频互操作性中的服务器 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="53f46-116">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  

