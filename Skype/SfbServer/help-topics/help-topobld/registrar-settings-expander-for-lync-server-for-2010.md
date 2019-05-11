---
title: 适合于 Lync Server for 2010 的注册器设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 编辑恢复能力的设置和配置以下属性：
ms.openlocfilehash: d02462b03b7255860695e373af276a69d92956e0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910247"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a><span data-ttu-id="828bf-103">适合于 Lync Server for 2010 的注册器设置扩展器</span><span class="sxs-lookup"><span data-stu-id="828bf-103">Registrar Settings Expander for Lync Server for 2010</span></span>
 
<span data-ttu-id="828bf-104">编辑**恢复能力**的设置和配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="828bf-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>
  
- <span data-ttu-id="828bf-105">从列表中选择**关联备份注册器池**。</span><span class="sxs-lookup"><span data-stu-id="828bf-105">Select **Associated backup Registrar pool** from the list.</span></span>
    
    <span data-ttu-id="828bf-106">或者，选择**自动故障转移和故障回复语音**复选框。</span><span class="sxs-lookup"><span data-stu-id="828bf-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>
    
    <span data-ttu-id="828bf-107">配置**语音故障检测间隔 （秒）** 和**语音故障回复间隔 （秒）**。</span><span class="sxs-lookup"><span data-stu-id="828bf-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="828bf-108">默认情况下，间隔为 120 秒语音故障检测和 240 秒语音故障回复。</span><span class="sxs-lookup"><span data-stu-id="828bf-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="828bf-109">为故障转移和故障回复间隔定义的秒数应仔细测试以确保恢复能力按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="828bf-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="828bf-110">将间隔设置为较低 （即，小于 120 秒） 或故障转移和故障回复太紧密设置可能会导致的实际故障转移和故障回复未按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="828bf-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span> 
  
  <span data-ttu-id="828bf-111">**确定** 接受更改并通过对话框提交更改。</span><span class="sxs-lookup"><span data-stu-id="828bf-111">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="828bf-112">**取消** 放弃更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="828bf-112">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="828bf-113">**帮助** 显示此帮助屏幕。</span><span class="sxs-lookup"><span data-stu-id="828bf-113">**Help** Displays this help screen.</span></span>
  

