---
title: 在 Skype for Business Server 中部署 VIS 服务器角色
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6401e67-59fe-4419-a0ab-ffac88e67632
description: '摘要: 在 Skype for Business 服务器中部署视频互操作服务器 (VIS) 角色。'
ms.openlocfilehash: 963c934846af2f791e7efde48f8b4ddd5be3dcb2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302719"
---
# <a name="deploy-the-vis-server-role-in-skype-for-business-server"></a><span data-ttu-id="a02ae-103">在 Skype for Business Server 中部署 VIS 服务器角色</span><span class="sxs-lookup"><span data-stu-id="a02ae-103">Deploy the VIS server role in Skype for Business Server</span></span>
 
<span data-ttu-id="a02ae-104">**摘要:** 在 Skype for Business 服务器中部署视频互操作服务器 (VIS) 角色。</span><span class="sxs-lookup"><span data-stu-id="a02ae-104">**Summary:** Deploy the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
<span data-ttu-id="a02ae-105">若要在刚刚在拓扑生成器中创建的服务器上设置 VIS 服务, 请启动 Skype for business Server 部署向导, 按**安装或更新 skype for Business Server 系统**, 然后按照向导中的以下步骤操作:</span><span class="sxs-lookup"><span data-stu-id="a02ae-105">To set up the VIS service on the server just created in Topology Builder, start the Skype for Business Server deployment wizard, press **Install or Update Skype for Business Server System** and follow these steps in the wizard:</span></span>
  
1.  <span data-ttu-id="a02ae-106">选择**安装本地配置存储**。</span><span class="sxs-lookup"><span data-stu-id="a02ae-106">Select **Install Local Configuration Store**.</span></span>
    
2. <span data-ttu-id="a02ae-107">选择 "**设置" 或 "删除 Skype For Business 服务器" 组件**。</span><span class="sxs-lookup"><span data-stu-id="a02ae-107">Select **Setup or Remove Skype for Business Server Components**.</span></span>
    
3. <span data-ttu-id="a02ae-108">选择**请求、安装或分配证书**。</span><span class="sxs-lookup"><span data-stu-id="a02ae-108">Select **Request, Install or Assign Certificates**.</span></span>
    
4. <span data-ttu-id="a02ae-109">选择**启动服务**。</span><span class="sxs-lookup"><span data-stu-id="a02ae-109">Select **Start services**.</span></span>
    
<span data-ttu-id="a02ae-110">The software for this service is now installed and running.</span><span class="sxs-lookup"><span data-stu-id="a02ae-110">The software for this service is now installed and running.</span></span> <span data-ttu-id="a02ae-111">您可以打开服务 mmc 工具, 查看**skype For Business 服务器视频互操作服务器**服务是否与其他 skype For business 服务器服务一起运行。</span><span class="sxs-lookup"><span data-stu-id="a02ae-111">You may open the Services mmc tool to see if the **Skype for Business Server Video Interop Server** service is running along with other Skype for Business Server services.</span></span> <span data-ttu-id="a02ae-112">Next, you must configure the VIS server or pool.</span><span class="sxs-lookup"><span data-stu-id="a02ae-112">Next, you must configure the VIS server or pool.</span></span>
## <a name="see-also"></a><span data-ttu-id="a02ae-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a02ae-113">See also</span></span>

[<span data-ttu-id="a02ae-114">在 Skype for Business 服务器中配置视频互操作服务器</span><span class="sxs-lookup"><span data-stu-id="a02ae-114">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
