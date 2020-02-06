---
title: 适合于 Lync Server for 2010 的注册器设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 编辑复原设置并配置以下属性：
ms.openlocfilehash: adc3d3f0be42d542583cf269a7acf83d98df8dd7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819334"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a><span data-ttu-id="fa696-103">适合于 Lync Server for 2010 的注册器设置扩展器</span><span class="sxs-lookup"><span data-stu-id="fa696-103">Registrar Settings Expander for Lync Server for 2010</span></span>
 
<span data-ttu-id="fa696-104">编辑**复原**设置并配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="fa696-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>
  
- <span data-ttu-id="fa696-105">从列表中选择**关联的备份注册机构池**。</span><span class="sxs-lookup"><span data-stu-id="fa696-105">Select **Associated backup Registrar pool** from the list.</span></span>
    
    <span data-ttu-id="fa696-106">（可选）选中 "**自动故障转移和语音故障回复**功能" 复选框。</span><span class="sxs-lookup"><span data-stu-id="fa696-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>
    
    <span data-ttu-id="fa696-107">配置**语音故障检测间隔（秒）** 和**语音回切间隔（秒）**。</span><span class="sxs-lookup"><span data-stu-id="fa696-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="fa696-108">默认情况下，语音故障回复的时间间隔为120秒，语音故障回复的240秒。</span><span class="sxs-lookup"><span data-stu-id="fa696-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="fa696-109">你为故障转移和故障回复间隔定义的秒数应该经过仔细测试，以确保复原功能按预期工作。</span><span class="sxs-lookup"><span data-stu-id="fa696-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="fa696-110">将间隔设置为 low （即小于120秒）或故障转移和故障回复的设置可能会导致实际故障转移和故障回复未按预期工作。</span><span class="sxs-lookup"><span data-stu-id="fa696-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span> 
  
  <span data-ttu-id="fa696-111">**确定** 接受更改并通过对话框提交更改。</span><span class="sxs-lookup"><span data-stu-id="fa696-111">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="fa696-112">**取消** 放弃更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="fa696-112">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="fa696-113">**帮助** 显示此帮助屏幕。</span><span class="sxs-lookup"><span data-stu-id="fa696-113">**Help** Displays this help screen.</span></span>
  

