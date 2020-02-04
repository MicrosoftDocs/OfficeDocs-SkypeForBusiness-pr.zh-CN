---
title: 注册器 SBA 设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
ROBOTS: NOINDEX, NOFOLLOW
description: 编辑复原设置并配置以下属性：
ms.openlocfilehash: 4297f70acfbf695d8dcfdcdb58a09d8f608add71
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41701637"
---
# <a name="registrar-sba-settings-expander"></a><span data-ttu-id="52e96-103">注册器 SBA 设置扩展器</span><span class="sxs-lookup"><span data-stu-id="52e96-103">Registrar SBA Settings Expander</span></span>

<span data-ttu-id="52e96-104">编辑**复原**设置并配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="52e96-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>

- <span data-ttu-id="52e96-105">从列表中选择**关联的用户服务和备份注册机构池**。</span><span class="sxs-lookup"><span data-stu-id="52e96-105">Select **Associated User service and backup Registrar pool** from the list.</span></span>

    <span data-ttu-id="52e96-106">（可选）选中 "**自动故障转移和语音故障回复**功能" 复选框。</span><span class="sxs-lookup"><span data-stu-id="52e96-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>

    <span data-ttu-id="52e96-107">配置**语音故障检测间隔（秒）** 和**语音回切间隔（秒）**。</span><span class="sxs-lookup"><span data-stu-id="52e96-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="52e96-108">默认情况下，语音故障回复的时间间隔为120秒，语音故障回复的240秒。</span><span class="sxs-lookup"><span data-stu-id="52e96-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="52e96-109">你为故障转移和故障回复间隔定义的秒数应该经过仔细测试，以确保复原功能按预期工作。</span><span class="sxs-lookup"><span data-stu-id="52e96-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="52e96-110">将间隔设置为 low （即小于120秒）或故障转移和故障回复的设置可能会导致实际故障转移和故障回复未按预期工作。</span><span class="sxs-lookup"><span data-stu-id="52e96-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span>

  <span data-ttu-id="52e96-111">**确定** 接受更改并通过对话框提交更改。</span><span class="sxs-lookup"><span data-stu-id="52e96-111">**OK** Accepts and commits changes to the dialog.</span></span>

  <span data-ttu-id="52e96-112">**取消** 放弃更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="52e96-112">**Cancel** Discards changes and closes the dialog.</span></span>

  <span data-ttu-id="52e96-113">**帮助** 显示此帮助屏幕。</span><span class="sxs-lookup"><span data-stu-id="52e96-113">**Help** Displays this help screen.</span></span>

## <a name="see-also"></a><span data-ttu-id="52e96-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52e96-114">See also</span></span>

[<span data-ttu-id="52e96-115">规划企业语音弹性</span><span class="sxs-lookup"><span data-stu-id="52e96-115">Planning for Enterprise Voice Resiliency</span></span>](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
