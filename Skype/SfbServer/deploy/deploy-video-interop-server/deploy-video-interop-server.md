---
title: 在 Skype for Business 服务器中部署视频互操作服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bb7d2abd-d033-4d7d-b588-6d9228c3eccf
description: 摘要：在 Skype for Business 服务器中部署 VIS 服务器角色。
ms.openlocfilehash: 51db16a115871f7720379157aa1b97ae89e9031f
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798029"
---
# <a name="deploy-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="83c9a-103">在 Skype for Business 服务器中部署视频互操作服务器</span><span class="sxs-lookup"><span data-stu-id="83c9a-103">Deploy Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="83c9a-104">**摘要：** 在 Skype for Business 服务器中部署 VIS 服务器角色。</span><span class="sxs-lookup"><span data-stu-id="83c9a-104">**Summary:** Deploy the VIS server role in Skype for Business Server.</span></span>
  
<span data-ttu-id="83c9a-105">现在，Skype for Business 服务器可以直接与 Cisco teleconferencing 系统（VTCs）（如 Cisco C60 或 Cisco MX300）集成。</span><span class="sxs-lookup"><span data-stu-id="83c9a-105">Skype for Business Server can now integrate directly with Cisco teleconferencing systems (VTCs) such as the Cisco C60 or Cisco MX300.</span></span> <span data-ttu-id="83c9a-106">这需要引入一个名为视频互操作服务器（VIS）的新服务器角色，以及正确配置它将与之互操作的 VIS 和设备。</span><span class="sxs-lookup"><span data-stu-id="83c9a-106">This requires the introduction of a new server role called the Video Interop Server (VIS), and correct configuration of both the VIS and the equipment it will interoperate with.</span></span> <span data-ttu-id="83c9a-107">VTC 注册现有 Cisco 基础结构（比如 Cisco Unified Communication Manager (CUCM)），在 CUCM 和 VIS 池之间使用视频 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="83c9a-107">A VTC registers with existing Cisco infrastructure such as Cisco Unified Communication Manager (CUCM), and a video SIP trunk is used between CUCM and the VIS pool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="83c9a-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="83c9a-108">In this section</span></span>

<span data-ttu-id="83c9a-109">要在 VIS 服务器或池与 VTC 系统之间配置互操作性，必须执行以下五个步骤：</span><span class="sxs-lookup"><span data-stu-id="83c9a-109">Configuring interoperability between a VIS server or pool and VTC systems requires performing the following five procedures:</span></span> 
  
- [<span data-ttu-id="83c9a-110">在 Skype for Business 服务器中创建 VIS 池</span><span class="sxs-lookup"><span data-stu-id="83c9a-110">Create a VIS pool in Skype for Business Server</span></span>](create-a-vis-pool.md)
    
- [<span data-ttu-id="83c9a-111">在 Skype for Business Server 中部署 VIS 服务器角色</span><span class="sxs-lookup"><span data-stu-id="83c9a-111">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)
    
- [<span data-ttu-id="83c9a-112">在 Skype for Business 服务器中配置视频互操作服务器</span><span class="sxs-lookup"><span data-stu-id="83c9a-112">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
    
- [<span data-ttu-id="83c9a-113">为与 Skype for Business 服务器的互操作配置 CUCM</span><span class="sxs-lookup"><span data-stu-id="83c9a-113">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
    
- [<span data-ttu-id="83c9a-114">为与 Skype for Business 服务器的互操作配置 VTC</span><span class="sxs-lookup"><span data-stu-id="83c9a-114">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
    
## <a name="related-sections"></a><span data-ttu-id="83c9a-115">相关部分</span><span class="sxs-lookup"><span data-stu-id="83c9a-115">Related sections</span></span>

[<span data-ttu-id="83c9a-116">Skype for business Server 中的视频互操作服务器计划</span><span class="sxs-lookup"><span data-stu-id="83c9a-116">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  

