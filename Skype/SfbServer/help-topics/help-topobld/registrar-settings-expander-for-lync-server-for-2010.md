---
title: Lync Server 2010 的注册设置扩展器
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 编辑的自我恢复能力的设置并配置以下属性：
ms.openlocfilehash: 88a2d75ff6f0225328a0f27743e0129950a5ca91
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a><span data-ttu-id="5f872-103">Lync Server 2010 的注册设置扩展器</span><span class="sxs-lookup"><span data-stu-id="5f872-103">Registrar Settings Expander for Lync Server for 2010</span></span>
 
<span data-ttu-id="5f872-104">编辑**的自我恢复能力**的设置并配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="5f872-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>
  
- <span data-ttu-id="5f872-105">从列表中选择**关联备份注册器池**。</span><span class="sxs-lookup"><span data-stu-id="5f872-105">Select **Associated backup Registrar pool** from the list.</span></span>
    
    <span data-ttu-id="5f872-106">或者，选择**自动故障切换和回切的声音**复选框。</span><span class="sxs-lookup"><span data-stu-id="5f872-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>
    
    <span data-ttu-id="5f872-107">配置**语音故障检测时间间隔 （秒）**和**语音故障回复间隔 （秒）**。</span><span class="sxs-lookup"><span data-stu-id="5f872-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="5f872-108">默认情况下，时间间隔是 120 秒的语音故障检测和故障回复语音 240 秒。</span><span class="sxs-lookup"><span data-stu-id="5f872-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="5f872-109">应仔细测试定义的故障转移和故障回复的间隔的秒数，以确保恢复正常工作。</span><span class="sxs-lookup"><span data-stu-id="5f872-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="5f872-110">将间隔设置为较低 （即小于 120 秒） 或故障转移和故障回复设置过于相似可能会导致实际的故障转移和故障自动恢复，未达到预期效果。</span><span class="sxs-lookup"><span data-stu-id="5f872-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span> 
  
 <span data-ttu-id="5f872-111">**确定** 接受更改并通过对话框提交更改。</span><span class="sxs-lookup"><span data-stu-id="5f872-111">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="5f872-112">**取消** 放弃更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="5f872-112">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="5f872-113">**帮助** 显示此帮助屏幕。</span><span class="sxs-lookup"><span data-stu-id="5f872-113">**Help** Displays this help screen.</span></span>
  

