---
title: 迁移模拟设备
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype 业务服务器为模拟设备提供支持。 具体而言，受支持的模拟设备将模拟音频电话和模拟传真机。 您可以配置合格网关以支持在您 Skype 业务服务器环境中使用模拟设备。 您迁移到 Skype 业务服务器 2019年后，您还必须迁移相关联的模拟设备联系对象。 使用 Skype 的业务 Server Management Shell，以先检索所有联系对象相关联的旧的模拟设备，然后将这些对象移动到业务服务器 2019年池 Skype。
ms.openlocfilehash: 80edf5b806ffd192d125bd5da27207a37f3074d1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238388"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="42b1b-107">迁移模拟设备</span><span class="sxs-lookup"><span data-stu-id="42b1b-107">Migrate analog devices</span></span>

<span data-ttu-id="42b1b-108">Skype 业务服务器为模拟设备提供支持。</span><span class="sxs-lookup"><span data-stu-id="42b1b-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="42b1b-109">具体而言，受支持的模拟设备将模拟音频电话和模拟传真机。</span><span class="sxs-lookup"><span data-stu-id="42b1b-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="42b1b-110">您可以配置合格网关以支持在您 Skype 业务服务器环境中使用模拟设备。</span><span class="sxs-lookup"><span data-stu-id="42b1b-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="42b1b-111">您迁移到 Skype 业务服务器 2019年后，您还必须迁移相关联的模拟设备联系对象。</span><span class="sxs-lookup"><span data-stu-id="42b1b-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="42b1b-112">使用 Skype 的业务 Server Management Shell，以先检索所有联系对象相关联的旧的模拟设备，然后将这些对象移动到业务服务器 2019年池 Skype。</span><span class="sxs-lookup"><span data-stu-id="42b1b-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="42b1b-113">迁移模拟设备</span><span class="sxs-lookup"><span data-stu-id="42b1b-113">To migrate analog devices</span></span>

1. <span data-ttu-id="42b1b-114">为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**，都单击**Microsoft Skype 的业务服务器 2019年**，，然后都单击**Skype 的业务 Server Management Shell**。</span><span class="sxs-lookup"><span data-stu-id="42b1b-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="42b1b-115">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="42b1b-115">At the command line, type:</span></span>

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="42b1b-116">验证的所有联系对象已移至 Skype 业务服务器 2019年池。</span><span class="sxs-lookup"><span data-stu-id="42b1b-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="42b1b-117">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="42b1b-117">At the command line, type:</span></span>

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="42b1b-118">验证所有联系对象现在是否与业务服务器 2019年池 Skype 关联。</span><span class="sxs-lookup"><span data-stu-id="42b1b-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


