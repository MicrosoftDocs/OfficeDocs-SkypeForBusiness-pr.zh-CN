---
title: 注册设置扩展器
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: 恢复注册池提供具有高可用性和灾难恢复能力。 通过在出现故障的主注册，注册可以接管失败的教务主任，在备份时备份注册器允许用户进行登录和通讯。 用户可能会遇到缩减的功能，具体取决于系统出现故障的主注册。
ms.openlocfilehash: 9d8460f0a883dfabc55153744ba4f3f886b34898
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="9b2a9-105">注册设置扩展器</span><span class="sxs-lookup"><span data-stu-id="9b2a9-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="9b2a9-106">恢复注册池提供具有高可用性和灾难恢复能力。</span><span class="sxs-lookup"><span data-stu-id="9b2a9-106">Resiliency provides high availability and disaster recovery for the Registrar pool.</span></span> <span data-ttu-id="9b2a9-107">通过在出现故障的主注册，注册可以接管失败的教务主任，在备份时备份注册器允许用户进行登录和通讯。</span><span class="sxs-lookup"><span data-stu-id="9b2a9-107">By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate.</span></span> <span data-ttu-id="9b2a9-108">用户可能会遇到缩减的功能，具体取决于系统出现故障的主注册。</span><span class="sxs-lookup"><span data-stu-id="9b2a9-108">Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="9b2a9-109">在高存活力的分支装置或自动恢复分支服务器**编辑属性**对话框中的**弹性**部分中，您可以更改以下设置：</span><span class="sxs-lookup"><span data-stu-id="9b2a9-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="9b2a9-110">**关联的用户服务和备份注册器池**在下拉列表中，选择标准版前端服务器是高存活力的分支装置或自动恢复分支服务器作为备份注册器的前端企业版池。</span><span class="sxs-lookup"><span data-stu-id="9b2a9-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="9b2a9-111">**启用故障转移和故障自动恢复**选择此设置以允许自动检测失败注册和主注册器是备份并且准备好继续注册过程的自动确定。</span><span class="sxs-lookup"><span data-stu-id="9b2a9-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="9b2a9-112">**故障检测时间间隔 （秒）**键入已确定由主注册器出现故障前应经过的秒数。</span><span class="sxs-lookup"><span data-stu-id="9b2a9-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="9b2a9-113">默认值为 120 秒。</span><span class="sxs-lookup"><span data-stu-id="9b2a9-113">The default value is 120 seconds.</span></span> <span data-ttu-id="9b2a9-114">如果您选择**启用故障转移和故障自动恢复**，则此字段是必需的。</span><span class="sxs-lookup"><span data-stu-id="9b2a9-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="9b2a9-115">**回退检测间隔 （秒）**键入它取决于备份的主注册前所经过的秒数。</span><span class="sxs-lookup"><span data-stu-id="9b2a9-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="9b2a9-116">默认值为 240 秒。</span><span class="sxs-lookup"><span data-stu-id="9b2a9-116">The default value is 240 seconds.</span></span> <span data-ttu-id="9b2a9-117">此字段是必需的如果您选择**启用故障转移和备用**。</span><span class="sxs-lookup"><span data-stu-id="9b2a9-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="9b2a9-118">故障检测间隔和备用检测间隔定义时，要小心，不要输入会导致故障转移时间间隔和后备如果注册机没有响应的短时间内发生。</span><span class="sxs-lookup"><span data-stu-id="9b2a9-118">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="9b2a9-119">很可能主要注册可能不响应的短时期内根据加载的池或服务器。</span><span class="sxs-lookup"><span data-stu-id="9b2a9-119">It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

