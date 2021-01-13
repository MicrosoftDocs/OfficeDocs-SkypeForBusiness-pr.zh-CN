---
title: 在 Skype for Business Server 中部署视频互操作服务器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bb7d2abd-d033-4d7d-b588-6d9228c3eccf
description: 摘要：在 Skype for Business Server 中部署 VIS 服务器角色。
ms.openlocfilehash: 7b3ee96b1ff2e6c633efa9e1cc98aa14bb5babc3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801952"
---
# <a name="deploy-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="a90b0-103">在 Skype for Business Server 中部署视频互操作服务器</span><span class="sxs-lookup"><span data-stu-id="a90b0-103">Deploy Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="a90b0-104">**摘要：** 在 Skype for Business Server 中部署 VIS 服务器角色。</span><span class="sxs-lookup"><span data-stu-id="a90b0-104">**Summary:** Deploy the VIS server role in Skype for Business Server.</span></span>
  
<span data-ttu-id="a90b0-105">Skype for Business Server 现在可以直接与 Cisco 电话会议系统 (VTC) 如 Cisco C60 或 Cisco MX300。</span><span class="sxs-lookup"><span data-stu-id="a90b0-105">Skype for Business Server can now integrate directly with Cisco teleconferencing systems (VTCs) such as the Cisco C60 or Cisco MX300.</span></span> <span data-ttu-id="a90b0-106">这需要引入名为视频互操作服务器 (VIS) 的新服务器角色，并正确配置将进行互操作的 VIS 和设备。</span><span class="sxs-lookup"><span data-stu-id="a90b0-106">This requires the introduction of a new server role called the Video Interop Server (VIS), and correct configuration of both the VIS and the equipment it will interoperate with.</span></span> <span data-ttu-id="a90b0-107">VTC 向现有 Cisco 基础结构（如 Cisco 统一通信管理器 (CUCM) ）注册，在 CUCM 和 VIS 池之间使用视频 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="a90b0-107">A VTC registers with existing Cisco infrastructure such as Cisco Unified Communication Manager (CUCM), and a video SIP trunk is used between CUCM and the VIS pool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="a90b0-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="a90b0-108">In this section</span></span>

<span data-ttu-id="a90b0-109">配置 VIS 服务器或池与 VTC 系统之间的互操作性需要执行以下五个过程：</span><span class="sxs-lookup"><span data-stu-id="a90b0-109">Configuring interoperability between a VIS server or pool and VTC systems requires performing the following five procedures:</span></span> 
  
- [<span data-ttu-id="a90b0-110">在 Skype for Business Server 中创建 VIS 池</span><span class="sxs-lookup"><span data-stu-id="a90b0-110">Create a VIS pool in Skype for Business Server</span></span>](create-a-vis-pool.md)
    
- [<span data-ttu-id="a90b0-111">在 Skype for Business Server 中部署 VIS 服务器角色</span><span class="sxs-lookup"><span data-stu-id="a90b0-111">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)
    
- [<span data-ttu-id="a90b0-112">在 Skype for Business Server 中配置视频互操作服务器</span><span class="sxs-lookup"><span data-stu-id="a90b0-112">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
    
- [<span data-ttu-id="a90b0-113">配置 CUCM 以与 Skype for Business Server 进行互操作</span><span class="sxs-lookup"><span data-stu-id="a90b0-113">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
    
- [<span data-ttu-id="a90b0-114">配置 VTC 以与 Skype for Business Server 进行互操作</span><span class="sxs-lookup"><span data-stu-id="a90b0-114">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
    
## <a name="related-sections"></a><span data-ttu-id="a90b0-115">相关章节</span><span class="sxs-lookup"><span data-stu-id="a90b0-115">Related sections</span></span>

[<span data-ttu-id="a90b0-116">在 Skype for Business Server 中规划视频互操作服务器</span><span class="sxs-lookup"><span data-stu-id="a90b0-116">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  

