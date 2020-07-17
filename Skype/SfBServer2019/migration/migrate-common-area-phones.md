---
title: 迁移公共区域电话
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 公共区域电话是最常位于共享工作区或公共区域（例如会议厅、厨房或工厂车间）的 IP 电话。 公用区域电话无需连接到计算机即可提供 Skype for Business Server 统一通信（UC）功能。 将部署迁移到 Skype for business Server 2019 后，还必须迁移与旧版公用区域电话关联的 contact 对象。 使用 Skype for Business Server 命令行管理程序，将首先检索与旧版公用区域电话关联的所有 contact 对象，然后将这些对象移至 Skype for Business Server 2019 池。
ms.openlocfilehash: b9cf5a32614ac41ac3c82773af4f37907c16e6f2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752704"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="ccc19-106">迁移公共区域电话</span><span class="sxs-lookup"><span data-stu-id="ccc19-106">Migrate Common Area Phones</span></span>

<span data-ttu-id="ccc19-107">公共区域电话是最常位于共享工作区或公共区域（例如会议厅、厨房或工厂车间）的 IP 电话。</span><span class="sxs-lookup"><span data-stu-id="ccc19-107">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="ccc19-108">公用区域电话无需连接到计算机即可提供 Skype for Business Server 统一通信（UC）功能。</span><span class="sxs-lookup"><span data-stu-id="ccc19-108">Common Area Phones do not need to be connected to a computer to provide Skype for Business Server unified communications (UC) functionality.</span></span> <span data-ttu-id="ccc19-109">将部署迁移到 Skype for business Server 2019 后，还必须迁移与旧版公用区域电话关联的 contact 对象。</span><span class="sxs-lookup"><span data-stu-id="ccc19-109">After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="ccc19-110">使用 Skype for Business Server 命令行管理程序，将首先检索与旧版公用区域电话关联的所有 contact 对象，然后将这些对象移至 Skype for Business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="ccc19-110">Using Skype for Business Server Management Shell, you will first retrieve all contact objects associated with the legacy Common Area Phones, and then move those objects to the Skype for Business Server 2019 pool.</span></span>
  
### <a name="migrate-common-area-phones"></a><span data-ttu-id="ccc19-111">迁移公共区域电话</span><span class="sxs-lookup"><span data-stu-id="ccc19-111">Migrate Common Area Phones</span></span>

1. <span data-ttu-id="ccc19-112">在 Skype for Business Server 2019 前端服务器中，打开 Skype for Business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="ccc19-112">From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="ccc19-113">从命令行键入：</span><span class="sxs-lookup"><span data-stu-id="ccc19-113">From the command line, type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. <span data-ttu-id="ccc19-114">若要验证是否已将所有 contact 对象移至 Skype for business Server 2019 池，请从 Skype for Business Server 命令行管理程序键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="ccc19-114">To verify that all contact objects have been moved to the Skype for Business Server 2019 pool, from the Skype for Business Server Management Shell type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    <span data-ttu-id="ccc19-115">验证所有 contact 对象现在是否与 Skype for Business Server 2019 池相关联。</span><span class="sxs-lookup"><span data-stu-id="ccc19-115">Verify that all contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>
    

