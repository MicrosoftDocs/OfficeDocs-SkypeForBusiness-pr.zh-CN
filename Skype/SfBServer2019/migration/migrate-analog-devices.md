---
title: 迁移模拟设备
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business 服务器提供模拟设备的支持。 具体说来, 受支持的模拟设备是模拟音频电话和模拟传真计算机。 你可以配置合格的网关以支持在 Skype for Business 服务器环境中使用模拟设备。 迁移到 Skype for business Server 2019 后, 还必须迁移与模拟设备相关联的联系人对象。 使用 Skype for Business Server Management Shell 首先检索与传统模拟设备相关联的所有联系人对象, 然后将这些对象移动到 Skype for business Server 2019 池。
ms.openlocfilehash: a822f8f73ad839654d266182172ef8e30d5d28e8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280841"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="084aa-107">迁移模拟设备</span><span class="sxs-lookup"><span data-stu-id="084aa-107">Migrate analog devices</span></span>

<span data-ttu-id="084aa-108">Skype for Business 服务器提供模拟设备的支持。</span><span class="sxs-lookup"><span data-stu-id="084aa-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="084aa-109">具体说来, 受支持的模拟设备是模拟音频电话和模拟传真计算机。</span><span class="sxs-lookup"><span data-stu-id="084aa-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="084aa-110">你可以配置合格的网关以支持在 Skype for Business 服务器环境中使用模拟设备。</span><span class="sxs-lookup"><span data-stu-id="084aa-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="084aa-111">迁移到 Skype for business Server 2019 后, 还必须迁移与模拟设备相关联的联系人对象。</span><span class="sxs-lookup"><span data-stu-id="084aa-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="084aa-112">使用 Skype for Business Server Management Shell 首先检索与传统模拟设备相关联的所有联系人对象, 然后将这些对象移动到 Skype for business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="084aa-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="084aa-113">迁移模拟设备</span><span class="sxs-lookup"><span data-stu-id="084aa-113">To migrate analog devices</span></span>

1. <span data-ttu-id="084aa-114">启动 Skype for Business Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft skype for business server 2019**", 然后单击 " **skype for business 服务器管理外壳**"。</span><span class="sxs-lookup"><span data-stu-id="084aa-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="084aa-115">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="084aa-115">At the command line, type:</span></span>

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="084aa-116">验证是否已将所有联系人对象移动到 Skype for business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="084aa-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="084aa-117">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="084aa-117">At the command line, type:</span></span>

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="084aa-118">验证所有联系人对象现已与 Skype for Business Server 2019 池相关联。</span><span class="sxs-lookup"><span data-stu-id="084aa-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


