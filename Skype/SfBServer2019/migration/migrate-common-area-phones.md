---
title: 迁移公共区域电话
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 常见的区域电话是指通常位于共享工作区或通用区域 (如大厅、厨房或工厂地板) 的 IP 电话。 常用的区域电话无需连接到计算机即可提供 Skype for business 服务器统一通信 (UC) 功能。 将部署迁移到 Skype for business Server 2019 后, 还必须迁移与旧式公共区域电话相关联的联系人对象。 使用 Skype for Business 服务器管理外壳, 你将首先检索与旧式公共区域电话相关联的所有联系人对象, 然后将这些对象移动到 Skype for Business Server 2019 池。
ms.openlocfilehash: 915b0b86c4f0b1ac74e2575cdfcd65d0cbf23d31
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280817"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="73d97-106">迁移公共区域电话</span><span class="sxs-lookup"><span data-stu-id="73d97-106">Migrate Common Area Phones</span></span>

<span data-ttu-id="73d97-107">常见的区域电话是指通常位于共享工作区或通用区域 (如大厅、厨房或工厂地板) 的 IP 电话。</span><span class="sxs-lookup"><span data-stu-id="73d97-107">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="73d97-108">常用的区域电话无需连接到计算机即可提供 Skype for business 服务器统一通信 (UC) 功能。</span><span class="sxs-lookup"><span data-stu-id="73d97-108">Common Area Phones do not need to be connected to a computer to provide Skype for Business Server unified communications (UC) functionality.</span></span> <span data-ttu-id="73d97-109">将部署迁移到 Skype for business Server 2019 后, 还必须迁移与旧式公共区域电话相关联的联系人对象。</span><span class="sxs-lookup"><span data-stu-id="73d97-109">After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="73d97-110">使用 Skype for Business Server 命令行管理程序, 将首先检索与旧式公共区域电话相关联的所有联系人对象, 然后将这些对象移动到 Skype for business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="73d97-110">Using Skype for Business Server Management Shell, you will first retrieve all contact objects associated with the legacy Common Area Phones, and then move those objects to the Skype for Business Server 2019 pool.</span></span>
  
### <a name="migrate-common-area-phones"></a><span data-ttu-id="73d97-111">迁移公共区域电话</span><span class="sxs-lookup"><span data-stu-id="73d97-111">Migrate Common Area Phones</span></span>

1. <span data-ttu-id="73d97-112">从 Skype for business 服务器2019前端服务器, 打开 Skype for business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="73d97-112">From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="73d97-113">在命令行中, 键入以下内容:</span><span class="sxs-lookup"><span data-stu-id="73d97-113">From the command line, type the following:</span></span>
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. <span data-ttu-id="73d97-114">若要验证是否已将所有联系人对象移动到 Skype for business Server 2019 池, 请从 Skype for business 服务器管理外壳键入以下内容:</span><span class="sxs-lookup"><span data-stu-id="73d97-114">To verify that all contact objects have been moved to the Skype for Business Server 2019 pool, from the Skype for Business Server Management Shell type the following:</span></span>
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    <span data-ttu-id="73d97-115">验证所有联系人对象现已与 Skype for Business Server 2019 池相关联。</span><span class="sxs-lookup"><span data-stu-id="73d97-115">Verify that all contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>
    

