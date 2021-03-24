---
title: 注册器 SBA 设置扩展器
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
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 编辑“复原”的设置并配置以下属性：
ms.openlocfilehash: 48ba2f95cc5cae31d71727d5707120c608ffda6e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104408"
---
# <a name="registrar-sba-settings-expander"></a><span data-ttu-id="85839-103">注册器 SBA 设置扩展器</span><span class="sxs-lookup"><span data-stu-id="85839-103">Registrar SBA Settings Expander</span></span>

<span data-ttu-id="85839-104">编辑“复原”的设置并配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="85839-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>

- <span data-ttu-id="85839-105">从列表选择“关联的用户服务和备份注册器池”。</span><span class="sxs-lookup"><span data-stu-id="85839-105">Select **Associated User service and backup Registrar pool** from the list.</span></span>

    <span data-ttu-id="85839-106">或者，选中“语音的自动故障转移和故障回复”复选框。</span><span class="sxs-lookup"><span data-stu-id="85839-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>

    <span data-ttu-id="85839-p101">配置“语音故障检测间隔(秒)”和“语音故障回复间隔(秒)”。默认情况下，语音故障检测间隔为 120 秒，语音故障回复间隔为 240 秒。</span><span class="sxs-lookup"><span data-stu-id="85839-p101">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**. By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="85839-p102">为故障转移和故障回复间隔定义的秒数应谨慎测试，以确保恢复按预期运行。将间隔设置为低（即低于 120 秒）或故障转移和故障回复太密可能会导致实际故障转移和故障回复不能按预期运行。</span><span class="sxs-lookup"><span data-stu-id="85839-p102">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected. Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span>

  <span data-ttu-id="85839-111">**确定** 接受更改并通过对话框提交更改。</span><span class="sxs-lookup"><span data-stu-id="85839-111">**OK** Accepts and commits changes to the dialog.</span></span>

  <span data-ttu-id="85839-112">**取消** 放弃更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="85839-112">**Cancel** Discards changes and closes the dialog.</span></span>

  <span data-ttu-id="85839-113">**帮助** 显示此帮助屏幕。</span><span class="sxs-lookup"><span data-stu-id="85839-113">**Help** Displays this help screen.</span></span>

## <a name="see-also"></a><span data-ttu-id="85839-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="85839-114">See also</span></span>

[<span data-ttu-id="85839-115">规划企业语音恢复能力</span><span class="sxs-lookup"><span data-stu-id="85839-115">Planning for Enterprise Voice Resiliency</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency)