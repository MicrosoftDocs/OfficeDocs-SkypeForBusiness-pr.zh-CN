---
title: Lync Server for 2010 的注册器设置扩展器
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
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 编辑“复原”的设置并配置以下属性：
ms.openlocfilehash: 4271203bf9f737034796cc3b74c95836480df521
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217173"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a><span data-ttu-id="c3f65-103">Lync Server for 2010 的注册器设置扩展器</span><span class="sxs-lookup"><span data-stu-id="c3f65-103">Registrar Settings Expander for Lync Server for 2010</span></span>
 
<span data-ttu-id="c3f65-104">编辑“复原”\*\*\*\* 的设置并配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="c3f65-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>
  
- <span data-ttu-id="c3f65-105">从列表中选择“关联的备份注册器池”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c3f65-105">Select **Associated backup Registrar pool** from the list.</span></span>
    
    <span data-ttu-id="c3f65-106">或者，选中“语音的自动故障转移和故障回复”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="c3f65-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>
    
    <span data-ttu-id="c3f65-p101">配置“语音故障检测间隔(秒)”\*\*\*\* 和“语音故障回复间隔(秒)”\*\*\*\*。默认情况下，语音故障检测间隔为 120 秒，语音故障回复间隔为 240 秒。</span><span class="sxs-lookup"><span data-stu-id="c3f65-p101">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**. By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="c3f65-p102">为故障转移和故障回复间隔定义的秒数应谨慎测试，以确保恢复按预期运行。将间隔设置为低（即低于 120 秒）或故障转移和故障回复太密可能会导致实际故障转移和故障回复不能按预期运行。</span><span class="sxs-lookup"><span data-stu-id="c3f65-p102">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected. Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span> 
  
  <span data-ttu-id="c3f65-111">**确定** 接受更改并通过对话框提交更改。</span><span class="sxs-lookup"><span data-stu-id="c3f65-111">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="c3f65-112">**取消** 放弃更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="c3f65-112">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="c3f65-113">**帮助** 显示此帮助屏幕。</span><span class="sxs-lookup"><span data-stu-id="c3f65-113">**Help** Displays this help screen.</span></span>
  

