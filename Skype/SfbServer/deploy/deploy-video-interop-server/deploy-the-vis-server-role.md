---
title: 在 Skype for Business Server 中部署 VIS 服务器角色
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
ms.assetid: b6401e67-59fe-4419-a0ab-ffac88e67632
description: 摘要：在 Skype for Business Server (VIS) 角色部署视频互操作服务器。
ms.openlocfilehash: 773e2ddf790aa1b6c36ff6926d8bc4d16ea613f5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801962"
---
# <a name="deploy-the-vis-server-role-in-skype-for-business-server"></a><span data-ttu-id="deb7a-103">在 Skype for Business Server 中部署 VIS 服务器角色</span><span class="sxs-lookup"><span data-stu-id="deb7a-103">Deploy the VIS server role in Skype for Business Server</span></span>
 
<span data-ttu-id="deb7a-104">**摘要：** 在 Skype for Business Server (VIS) 角色部署视频互操作服务器。</span><span class="sxs-lookup"><span data-stu-id="deb7a-104">**Summary:** Deploy the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
<span data-ttu-id="deb7a-105">若要在拓扑生成器中刚刚创建的服务器上设置 VIS 服务，请启动 Skype for Business Server 部署向导，按"安装"或"更新 **Skype for Business Server 系统** "并按照向导中的以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="deb7a-105">To set up the VIS service on the server just created in Topology Builder, start the Skype for Business Server deployment wizard, press **Install or Update Skype for Business Server System** and follow these steps in the wizard:</span></span>
  
1.  <span data-ttu-id="deb7a-106">选择 **"安装本地配置存储"。**</span><span class="sxs-lookup"><span data-stu-id="deb7a-106">Select **Install Local Configuration Store**.</span></span>
    
2. <span data-ttu-id="deb7a-107">选择 **"安装"或删除"Skype for Business Server 组件"。**</span><span class="sxs-lookup"><span data-stu-id="deb7a-107">Select **Setup or Remove Skype for Business Server Components**.</span></span>
    
3. <span data-ttu-id="deb7a-108">选择 **"请求、安装或分配证书"。**</span><span class="sxs-lookup"><span data-stu-id="deb7a-108">Select **Request, Install or Assign Certificates**.</span></span>
    
4. <span data-ttu-id="deb7a-109">选择 **"启动服务"。**</span><span class="sxs-lookup"><span data-stu-id="deb7a-109">Select **Start services**.</span></span>
    
<span data-ttu-id="deb7a-110">此服务的软件现已安装并运行。</span><span class="sxs-lookup"><span data-stu-id="deb7a-110">The software for this service is now installed and running.</span></span> <span data-ttu-id="deb7a-111">你可以打开服务 mmc 工具，查看 **Skype for Business Server 视频互操作服务器** 服务是否与其他 Skype for Business Server 服务一起运行。</span><span class="sxs-lookup"><span data-stu-id="deb7a-111">You may open the Services mmc tool to see if the **Skype for Business Server Video Interop Server** service is running along with other Skype for Business Server services.</span></span> <span data-ttu-id="deb7a-112">接下来，必须配置 VIS 服务器或池。</span><span class="sxs-lookup"><span data-stu-id="deb7a-112">Next, you must configure the VIS server or pool.</span></span>
## <a name="see-also"></a><span data-ttu-id="deb7a-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="deb7a-113">See also</span></span>

[<span data-ttu-id="deb7a-114">在 Skype for Business Server 中配置视频互操作服务器</span><span class="sxs-lookup"><span data-stu-id="deb7a-114">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
