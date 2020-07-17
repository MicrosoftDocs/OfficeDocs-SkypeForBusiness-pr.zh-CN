---
title: 迁移模拟设备
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
description: Skype for Business Server 为模拟设备提供支持。 具体地说，支持的模拟设备是模拟音频电话和模拟传真机。 您可以配置合格的网关，以支持在 Skype for Business Server 环境中使用模拟设备。 迁移到 Skype for business Server 2019 后，还必须迁移与模拟设备关联的 contact 对象。 使用 Skype for Business Server 命令行管理程序先检索与旧模拟设备关联的所有 contact 对象，然后将这些对象移至 Skype for Business Server 2019 池。
ms.openlocfilehash: 7b90a52486725c2cf30856dc643660d569d698e2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752824"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="adbb1-107">迁移模拟设备</span><span class="sxs-lookup"><span data-stu-id="adbb1-107">Migrate analog devices</span></span>

<span data-ttu-id="adbb1-108">Skype for Business Server 为模拟设备提供支持。</span><span class="sxs-lookup"><span data-stu-id="adbb1-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="adbb1-109">具体地说，支持的模拟设备是模拟音频电话和模拟传真机。</span><span class="sxs-lookup"><span data-stu-id="adbb1-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="adbb1-110">您可以配置合格的网关，以支持在 Skype for Business Server 环境中使用模拟设备。</span><span class="sxs-lookup"><span data-stu-id="adbb1-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="adbb1-111">迁移到 Skype for business Server 2019 后，还必须迁移与模拟设备关联的 contact 对象。</span><span class="sxs-lookup"><span data-stu-id="adbb1-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="adbb1-112">使用 Skype for Business Server 命令行管理程序先检索与旧模拟设备关联的所有 contact 对象，然后将这些对象移至 Skype for Business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="adbb1-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="adbb1-113">迁移模拟设备</span><span class="sxs-lookup"><span data-stu-id="adbb1-113">To migrate analog devices</span></span>

1. <span data-ttu-id="adbb1-114">启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Skype for business server 2019**"，然后单击 " **Skype for business server Management Shell**"。</span><span class="sxs-lookup"><span data-stu-id="adbb1-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="adbb1-115">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="adbb1-115">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="adbb1-116">验证是否已将所有 contact 对象移动到 Skype for Business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="adbb1-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="adbb1-117">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="adbb1-117">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="adbb1-118">验证所有联系人对象现在是否与 Skype for Business Server 2019 池相关联。</span><span class="sxs-lookup"><span data-stu-id="adbb1-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


