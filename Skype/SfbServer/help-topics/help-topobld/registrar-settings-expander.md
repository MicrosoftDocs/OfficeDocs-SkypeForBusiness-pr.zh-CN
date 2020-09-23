---
title: 注册器设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: f6ea6907942111db92ca3bfe2dfef1712bd53a62
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217153"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="1a9f0-105">注册器设置扩展器</span><span class="sxs-lookup"><span data-stu-id="1a9f0-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="1a9f0-p102">复原为注册器池提供了高可用性和灾难恢复。它提供了备份注册器，当主注册器发生故障时，备份注册器可以接管发生故障的注册器，允许用户登录和进行通信。用户可能会发现功能降低，具体取决于哪些系统的主注册器发生故障。</span><span class="sxs-lookup"><span data-stu-id="1a9f0-p102">Resiliency provides high availability and disaster recovery for the Registrar pool. By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate. Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="1a9f0-109">在 Survivable Branch Appliance 或 Survivable Branch Server 的“编辑属性”\*\*\*\* 对话框的“复原”\*\*\*\* 部分，可以更改以下设置：</span><span class="sxs-lookup"><span data-stu-id="1a9f0-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="1a9f0-110">**关联的用户服务和备份注册器池** 在下拉列表中，选择要充当 Survivable 分支设备或 Survivable 分支服务器的备份注册器的 Enterprise Edition 前端池或 Standard Edition 前端服务器。</span><span class="sxs-lookup"><span data-stu-id="1a9f0-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="1a9f0-111">**启用故障转移和故障回复** 选择 "此设置" 可允许自动检测失败的注册器，并自动确定主注册器已备份并准备好恢复注册器进程。</span><span class="sxs-lookup"><span data-stu-id="1a9f0-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="1a9f0-112">\*\* (sec) 的故障检测间隔 \*\* 键入在确定主注册器失败之前应经过的秒数。</span><span class="sxs-lookup"><span data-stu-id="1a9f0-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="1a9f0-113">默认值为 120 秒。</span><span class="sxs-lookup"><span data-stu-id="1a9f0-113">The default value is 120 seconds.</span></span> <span data-ttu-id="1a9f0-114">如果选择 " **启用故障转移和故障回复**"，则此字段是必需的。</span><span class="sxs-lookup"><span data-stu-id="1a9f0-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="1a9f0-115">\*\* (sec) 的回退检测间隔 \*\* 键入在确定主注册器已备份之前应经过的秒数。</span><span class="sxs-lookup"><span data-stu-id="1a9f0-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="1a9f0-116">默认值为240秒。</span><span class="sxs-lookup"><span data-stu-id="1a9f0-116">The default value is 240 seconds.</span></span> <span data-ttu-id="1a9f0-117">如果选择 " **启用故障转移和回退**"，则此字段是必需的。</span><span class="sxs-lookup"><span data-stu-id="1a9f0-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="1a9f0-p105">定义故障检测时间间隔和回退检测时间间隔时，请注意不要输入在注册器短时间内未做出响应的情况下会导致发生故障转移和回退的时间间隔。主注册器可能会在短时间内没有响应，这取决于池或服务器的加载状况。</span><span class="sxs-lookup"><span data-stu-id="1a9f0-p105">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time. It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

