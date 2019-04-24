---
title: 迁移公共区域电话
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 公用区域电话是 IP 大多数通常位于共享工作区或公共区域电话如会议室、 厨房或工厂基底。 公用区域电话不需要连接到计算机以提供业务服务器 Skype 统一通信 (UC) 功能。 迁移后部署到 Skype 的业务服务器 2019年，您必须迁移与旧版公用区域电话联系对象。 Skype 用于业务 Server 命令行管理程序将先检索与旧的公用区域电话，关联的所有联系对象，然后将这些对象移动到业务服务器 2019年池的 Skype。
ms.openlocfilehash: d17e15224a9124eaf3e9fd6696e6ecd9265044eb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231663"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="d1b46-106">迁移公共区域电话</span><span class="sxs-lookup"><span data-stu-id="d1b46-106">Migrate Common Area Phones</span></span>

<span data-ttu-id="d1b46-107">公用区域电话是 IP 大多数通常位于共享工作区或公共区域电话如会议室、 厨房或工厂基底。</span><span class="sxs-lookup"><span data-stu-id="d1b46-107">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="d1b46-108">公用区域电话不需要连接到计算机以提供业务服务器 Skype 统一通信 (UC) 功能。</span><span class="sxs-lookup"><span data-stu-id="d1b46-108">Common Area Phones do not need to be connected to a computer to provide Skype for Business Server unified communications (UC) functionality.</span></span> <span data-ttu-id="d1b46-109">迁移后部署到 Skype 的业务服务器 2019年，您必须迁移与旧版公用区域电话联系对象。</span><span class="sxs-lookup"><span data-stu-id="d1b46-109">After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="d1b46-110">使用 Skype 业务 Server 命令行管理程序，您将先检索与旧的公用区域电话，关联的所有联系对象，然后将这些对象移动到业务服务器 2019年池 Skype。</span><span class="sxs-lookup"><span data-stu-id="d1b46-110">Using Skype for Business Server Management Shell, you will first retrieve all contact objects associated with the legacy Common Area Phones, and then move those objects to the Skype for Business Server 2019 pool.</span></span>
  
### <a name="migrate-common-area-phones"></a><span data-ttu-id="d1b46-111">迁移公共区域电话</span><span class="sxs-lookup"><span data-stu-id="d1b46-111">Migrate Common Area Phones</span></span>

1. <span data-ttu-id="d1b46-112">从业务服务器 2019年前端服务器的 Skype，打开业务 Server 命令行管理程序 Skype。</span><span class="sxs-lookup"><span data-stu-id="d1b46-112">From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="d1b46-113">从命令行中，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="d1b46-113">From the command line, type the following:</span></span>
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. <span data-ttu-id="d1b46-114">若要验证的所有联系对象已移至 Skype 业务服务器 2019年池，从业务 Server 命令行管理程序 Skype 键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="d1b46-114">To verify that all contact objects have been moved to the Skype for Business Server 2019 pool, from the Skype for Business Server Management Shell type the following:</span></span>
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    <span data-ttu-id="d1b46-115">验证所有联系对象现在是否与业务服务器 2019年池 Skype 关联。</span><span class="sxs-lookup"><span data-stu-id="d1b46-115">Verify that all contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>
    

