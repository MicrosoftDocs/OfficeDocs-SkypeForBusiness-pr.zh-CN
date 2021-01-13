---
title: 注册器设置扩展器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: 复原为注册器池提供了高可用性和灾难恢复。它提供了备份注册器，当主注册器发生故障时，备份注册器可以接管发生故障的注册器，允许用户登录和进行通信。用户可能会发现功能降低，具体取决于哪些系统的主注册器发生故障。
ms.openlocfilehash: 8ab5fc804b6fad1f049e70477d7c16cb35111f79
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818292"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="d73ed-105">注册器设置扩展器</span><span class="sxs-lookup"><span data-stu-id="d73ed-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="d73ed-p102">复原为注册器池提供了高可用性和灾难恢复。它提供了备份注册器，当主注册器发生故障时，备份注册器可以接管发生故障的注册器，允许用户登录和进行通信。用户可能会发现功能降低，具体取决于哪些系统的主注册器发生故障。</span><span class="sxs-lookup"><span data-stu-id="d73ed-p102">Resiliency provides high availability and disaster recovery for the Registrar pool. By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate. Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="d73ed-109">在 Survivable Branch Appliance 或 Survivable Branch Server 的“编辑属性”对话框的“复原”部分，可以更改以下设置：</span><span class="sxs-lookup"><span data-stu-id="d73ed-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="d73ed-110">**关联的用户服务和备份注册器池** 在下拉列表中，选择 Enterprise Edition 前端池或 Standard Edition 前端服务器，以用作 Survivable Branch Appliance 或 Survivable Branch Server 的备份注册器。</span><span class="sxs-lookup"><span data-stu-id="d73ed-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="d73ed-111">**启用故障转移和故障回复** 选择此设置可允许自动检测发生故障的注册器，并自动确定主注册器已备份并准备恢复注册器过程。</span><span class="sxs-lookup"><span data-stu-id="d73ed-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="d73ed-112">**故障检测间隔 (秒)** 键入确定主注册器失败之前应经过的秒数。</span><span class="sxs-lookup"><span data-stu-id="d73ed-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="d73ed-113">默认值为 120 秒。</span><span class="sxs-lookup"><span data-stu-id="d73ed-113">The default value is 120 seconds.</span></span> <span data-ttu-id="d73ed-114">如果选择"启用故障转移和故障回复 **"，则此字段是必需的**。</span><span class="sxs-lookup"><span data-stu-id="d73ed-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="d73ed-115">**回退检测间隔 (秒)** 键入确定备份主注册器之前应经过的秒数。</span><span class="sxs-lookup"><span data-stu-id="d73ed-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="d73ed-116">默认值为 240 秒。</span><span class="sxs-lookup"><span data-stu-id="d73ed-116">The default value is 240 seconds.</span></span> <span data-ttu-id="d73ed-117">如果选择"启用故障转移"和"回退 **"，则此字段是必需的**。</span><span class="sxs-lookup"><span data-stu-id="d73ed-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="d73ed-p105">定义故障检测时间间隔和回退检测时间间隔时，请注意不要输入在注册器短时间内未做出响应的情况下会导致发生故障转移和回退的时间间隔。主注册器可能会在短时间内没有响应，这取决于池或服务器的加载状况。</span><span class="sxs-lookup"><span data-stu-id="d73ed-p105">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time. It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

