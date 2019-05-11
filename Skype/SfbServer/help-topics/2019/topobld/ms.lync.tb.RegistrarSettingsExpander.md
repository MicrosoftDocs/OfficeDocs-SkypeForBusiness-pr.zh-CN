---
title: 注册器设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
ROBOTS: NOINDEX, NOFOLLOW
description: 恢复能力提供高可用性和灾难恢复的注册器池。 通过提供发生故障的主注册器，备份注册器可以接管失败的注册器，为备份注册器允许用户登录并进行通信。 用户可能可以体验缩减的功能，具体取决于其系统已失败的主注册器。
ms.openlocfilehash: 0902c8490d650208c072ed7d2856738b9bd7f2c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906730"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="fb64e-105">注册器设置扩展器</span><span class="sxs-lookup"><span data-stu-id="fb64e-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="fb64e-106">恢复能力提供高可用性和灾难恢复的注册器池。</span><span class="sxs-lookup"><span data-stu-id="fb64e-106">Resiliency provides high availability and disaster recovery for the Registrar pool.</span></span> <span data-ttu-id="fb64e-107">通过提供发生故障的主注册器，备份注册器可以接管失败的注册器，为备份注册器允许用户登录并进行通信。</span><span class="sxs-lookup"><span data-stu-id="fb64e-107">By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate.</span></span> <span data-ttu-id="fb64e-108">用户可能可以体验缩减的功能，具体取决于其系统已失败的主注册器。</span><span class="sxs-lookup"><span data-stu-id="fb64e-108">Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="fb64e-109">在**编辑属性**对话框的 Survivable Branch Appliance 或 Survivable Branch Server**复原**部分中，您可以更改以下设置：</span><span class="sxs-lookup"><span data-stu-id="fb64e-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="fb64e-110">**关联的用户服务和备份注册器池**在下拉列表中，选择 Enterprise Edition 前端池或 Standard Edition 前端服务器，以用作 Survivable Branch Appliance 或 Survivable Branch Server 备份注册器。</span><span class="sxs-lookup"><span data-stu-id="fb64e-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="fb64e-111">**启用故障转移和故障回复**选择此设置，以注册器和主注册器是备份和已准备好继续注册器过程的自动确定允许自动检测失败。</span><span class="sxs-lookup"><span data-stu-id="fb64e-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="fb64e-112">**故障检测间隔 （秒）** 键入确定主注册器已失败之前应经过的秒的数。</span><span class="sxs-lookup"><span data-stu-id="fb64e-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="fb64e-113">默认值为 120 秒。</span><span class="sxs-lookup"><span data-stu-id="fb64e-113">The default value is 120 seconds.</span></span> <span data-ttu-id="fb64e-114">如果选择**启用故障转移和故障回复**，则需要此字段。</span><span class="sxs-lookup"><span data-stu-id="fb64e-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="fb64e-115">**回退检测间隔 （秒）** 键入确定备份的主注册器之前应经过的秒的数。</span><span class="sxs-lookup"><span data-stu-id="fb64e-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="fb64e-116">默认值为 240 秒。</span><span class="sxs-lookup"><span data-stu-id="fb64e-116">The default value is 240 seconds.</span></span> <span data-ttu-id="fb64e-117">如果选择**启用故障转移和回退**，则需要此字段。</span><span class="sxs-lookup"><span data-stu-id="fb64e-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="fb64e-118">定义故障检测间隔和回退检测间隔时, 是时间的注意不要输入间隔将导致故障转移和回退发生如果注册器没有响应期间较短。</span><span class="sxs-lookup"><span data-stu-id="fb64e-118">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="fb64e-119">则可能的主注册器可能不响应短期基于加载的池或服务器的时间。</span><span class="sxs-lookup"><span data-stu-id="fb64e-119">It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

