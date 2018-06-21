---
title: 注册器 SBA 设置扩展器
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 编辑恢复能力的设置和配置以下属性：
ms.openlocfilehash: 78c25613f1a552dbcfbfcaed9db787cf9a0fb7eb
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2018
ms.locfileid: "19976772"
---
# <a name="registrar-sba-settings-expander"></a><span data-ttu-id="40340-103">注册器 SBA 设置扩展器</span><span class="sxs-lookup"><span data-stu-id="40340-103">Registrar SBA Settings Expander</span></span>
 
<span data-ttu-id="40340-104">编辑**恢复能力**的设置和配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="40340-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>
  
- <span data-ttu-id="40340-105">从列表中选择**关联的用户服务和备份注册器池**。</span><span class="sxs-lookup"><span data-stu-id="40340-105">Select **Associated User service and backup Registrar pool** from the list.</span></span>
    
    <span data-ttu-id="40340-106">或者，选择**自动故障转移和故障回复语音**复选框。</span><span class="sxs-lookup"><span data-stu-id="40340-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>
    
    <span data-ttu-id="40340-107">配置**语音故障检测间隔 （秒）** 和**语音故障回复间隔 （秒）**。</span><span class="sxs-lookup"><span data-stu-id="40340-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="40340-108">默认情况下，间隔为 120 秒语音故障检测和 240 秒语音故障回复。</span><span class="sxs-lookup"><span data-stu-id="40340-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="40340-109">为故障转移和故障回复间隔定义的秒数应仔细测试以确保恢复能力按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="40340-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="40340-110">将间隔设置为较低 （即，小于 120 秒） 或故障转移和故障回复太紧密设置可能会导致的实际故障转移和故障回复未按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="40340-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span> 
  
 <span data-ttu-id="40340-111">**确定** 接受更改并通过对话框提交更改。</span><span class="sxs-lookup"><span data-stu-id="40340-111">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="40340-112">**取消** 放弃更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="40340-112">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="40340-113">**帮助** 显示此帮助屏幕。</span><span class="sxs-lookup"><span data-stu-id="40340-113">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="40340-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="40340-114">See also</span></span>

[<span data-ttu-id="40340-115">规划企业语音恢复能力</span><span class="sxs-lookup"><span data-stu-id="40340-115">Planning for Enterprise Voice Resiliency</span></span>](http://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)