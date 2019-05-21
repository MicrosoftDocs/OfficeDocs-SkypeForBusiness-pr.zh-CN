---
title: 注册器设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
ROBOTS: NOINDEX, NOFOLLOW
description: 复原功能为注册机构池提供高可用性和灾难恢复。 通过在主注册机出现故障的情况下提供备份注册机构, 备份注册机构可以接管失败的注册机构, 从而允许用户登录和通信。 用户可能会遇到缩减功能, 具体取决于使用主注册器失败的系统。
ms.openlocfilehash: 122124140c93afb3ce58b1d9423839f3e21dbcad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277837"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="528e6-105">注册器设置扩展器</span><span class="sxs-lookup"><span data-stu-id="528e6-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="528e6-106">复原功能为注册机构池提供高可用性和灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="528e6-106">Resiliency provides high availability and disaster recovery for the Registrar pool.</span></span> <span data-ttu-id="528e6-107">通过在主注册机出现故障的情况下提供备份注册机构, 备份注册机构可以接管失败的注册机构, 从而允许用户登录和通信。</span><span class="sxs-lookup"><span data-stu-id="528e6-107">By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate.</span></span> <span data-ttu-id="528e6-108">用户可能会遇到缩减功能, 具体取决于使用主注册器失败的系统。</span><span class="sxs-lookup"><span data-stu-id="528e6-108">Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="528e6-109">在 Survivable 分支装置或 Survivable 分支服务器的 "**编辑属性**" 对话框的 "**弹性**" 部分中, 您可以更改以下设置:</span><span class="sxs-lookup"><span data-stu-id="528e6-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="528e6-110">**关联的用户服务和备份注册机构池**在下拉列表中, 选择要用作 Survivable 分支装置或 Survivable 分支服务器的备份注册机构的企业版前端池或标准版前端服务器。</span><span class="sxs-lookup"><span data-stu-id="528e6-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="528e6-111">**启用故障转移和故障回复**选择此设置以允许自动检测失败的注册机构, 并自动确定主注册机构是否已备份并准备好继续注册过程。</span><span class="sxs-lookup"><span data-stu-id="528e6-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="528e6-112">**故障检测间隔 (秒)** 键入在确定主注册机构失败之前应经过的秒数。</span><span class="sxs-lookup"><span data-stu-id="528e6-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="528e6-113">默认值为120秒。</span><span class="sxs-lookup"><span data-stu-id="528e6-113">The default value is 120 seconds.</span></span> <span data-ttu-id="528e6-114">如果选择 "**启用故障转移和故障回复**", 则此字段是必需的。</span><span class="sxs-lookup"><span data-stu-id="528e6-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="528e6-115">**回退检测间隔 (秒)** 键入在确定主注册器备份之前应经过的秒数。</span><span class="sxs-lookup"><span data-stu-id="528e6-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="528e6-116">默认值为240秒。</span><span class="sxs-lookup"><span data-stu-id="528e6-116">The default value is 240 seconds.</span></span> <span data-ttu-id="528e6-117">如果选择 "**启用故障转移和回退**", 则此字段是必需的。</span><span class="sxs-lookup"><span data-stu-id="528e6-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="528e6-118">当您定义 "故障检测间隔" 和 "回退检测间隔" 时, 请注意不要输入一个时间间隔, 如果注册机构在短时间内无法响应, 则会导致故障转移和回退发生。</span><span class="sxs-lookup"><span data-stu-id="528e6-118">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="528e6-119">主注册器可能不会根据加载池或服务器的短时间进行响应。</span><span class="sxs-lookup"><span data-stu-id="528e6-119">It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

