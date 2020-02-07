---
title: Microsoft 团队聊天室的管理概述
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
description: Microsoft 团队聊天室的管理概述。
ms.openlocfilehash: 3a56a03342ca0edb0da9dc9ed3a4cada77816bc7
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825880"
---
# <a name="management-overview"></a><span data-ttu-id="ea2f5-103">管理概述</span><span class="sxs-lookup"><span data-stu-id="ea2f5-103">Management overview</span></span>

<span data-ttu-id="ea2f5-104">你必须开发和执行持续维护和操作，以确保你的 Microsoft 团队聊天室系统适用于你的用户并提供出色的用户体验。</span><span class="sxs-lookup"><span data-stu-id="ea2f5-104">It’s essential that you develop and execute ongoing maintenance and operations to ensure that your Microsoft Teams Rooms systems are available for your users and deliver a great user experience.</span></span> 

## <a name="monitoring"></a><span data-ttu-id="ea2f5-105">监控</span><span class="sxs-lookup"><span data-stu-id="ea2f5-105">Monitoring</span></span> 

<span data-ttu-id="ea2f5-106">监视 Microsoft 团队聊天室系统包含两个关键活动：</span><span class="sxs-lookup"><span data-stu-id="ea2f5-106">Monitoring Microsoft Teams Rooms systems consists of two key activities:</span></span>

- <span data-ttu-id="ea2f5-107">设备、应用程序和外围设备监控</span><span class="sxs-lookup"><span data-stu-id="ea2f5-107">Device, application, and peripheral device monitoring</span></span>
- <span data-ttu-id="ea2f5-108">质量和可靠性监视（CQD）</span><span class="sxs-lookup"><span data-stu-id="ea2f5-108">Quality and reliability monitoring (CQD)</span></span>

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a><span data-ttu-id="ea2f5-109">Microsoft 团队聊天室设备、应用程序和外围设备监控</span><span class="sxs-lookup"><span data-stu-id="ea2f5-109">Microsoft Teams Rooms device, application, and peripheral device monitoring</span></span>

<span data-ttu-id="ea2f5-110">为确保用户能够使用 Microsoft 团队房间单元，设备必须处于打开状态，连接到 Microsoft 团队聊天室应用程序的网络已正确配置，并连接到正常工作的外围设备。</span><span class="sxs-lookup"><span data-stu-id="ea2f5-110">To ensure that users are able to use the Microsoft Teams Rooms units, the units must be on, connected to the network with the Microsoft Teams Rooms application correctly configured, and be connected to functioning peripheral devices.</span></span> 

<span data-ttu-id="ea2f5-111">有关 Microsoft 团队聊天室应用程序和连接的外围设备状态的信息由 Microsoft 团队聊天室应用程序写入 Windows 事件日志，并在[了解日志条目](azure-monitor-manage.md#understand-the-log-entries)中记录。</span><span class="sxs-lookup"><span data-stu-id="ea2f5-111">Information about the state of the Microsoft Teams Rooms application and connected peripheral devices is written by the Microsoft Teams Rooms application to the Windows event log and documented in [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries).</span></span> 

|<span data-ttu-id="ea2f5-112">**设置**</span><span class="sxs-lookup"><span data-stu-id="ea2f5-112">**Setting**</span></span>|<span data-ttu-id="ea2f5-113">**这样**</span><span class="sxs-lookup"><span data-stu-id="ea2f5-113">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ea2f5-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = （dword）1</span><span class="sxs-lookup"><span data-stu-id="ea2f5-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span></span>  <br/> |<span data-ttu-id="ea2f5-115">支持 Microsoft 团队会议室启动</span><span class="sxs-lookup"><span data-stu-id="ea2f5-115">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="ea2f5-116">电源管理-\>通过交流，10分钟后关闭屏幕</span><span class="sxs-lookup"><span data-stu-id="ea2f5-116">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="ea2f5-117">电源管理-\>在交流上，从不将系统置于睡眠状态</span><span class="sxs-lookup"><span data-stu-id="ea2f5-117">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="ea2f5-118">使 Microsoft 团队会议室能够关闭附加的显示并自动唤醒</span><span class="sxs-lookup"><span data-stu-id="ea2f5-118">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="ea2f5-119">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="ea2f5-119">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="ea2f5-120">或对本地帐户禁用密码过期的等效方法。</span><span class="sxs-lookup"><span data-stu-id="ea2f5-120">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="ea2f5-121">如果此操作失败，将最终导致 Skype 帐户无法登录，且被告知密码过期。</span><span class="sxs-lookup"><span data-stu-id="ea2f5-121">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="ea2f5-122">请注意，这会影响计算机上的所有本地帐户，因此，此设置失败还会导致已有的管理帐户最终也过期。</span><span class="sxs-lookup"><span data-stu-id="ea2f5-122">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="ea2f5-123">启用 Skype 帐户以始终登录</span><span class="sxs-lookup"><span data-stu-id="ea2f5-123">Enables Skype account to always log in</span></span>  <br/> |

<span data-ttu-id="ea2f5-124">在 "[配置文件" 项目](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)中讨论了使用组策略传输文件的内容。</span><span class="sxs-lookup"><span data-stu-id="ea2f5-124">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="ea2f5-125">使用 PowerShell 进行远程管理</span><span class="sxs-lookup"><span data-stu-id="ea2f5-125">Remote Management using PowerShell</span></span>
<span data-ttu-id="ea2f5-126"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="ea2f5-126"><a name="RemotePS"> </a></span></span>

<span data-ttu-id="ea2f5-127">我们建议你使用 Microsoft Operations Manager Suite 监视 Microsoft 团队聊天室系统。</span><span class="sxs-lookup"><span data-stu-id="ea2f5-127">We recommend that you use Microsoft Operations Manager Suite to monitor your Microsoft Teams Rooms systems.</span></span> <span data-ttu-id="ea2f5-128">有关如何设置监视和基本警报的指南，请参阅[通过 Azure 监视器部署 Microsoft 团队聊天室管理](azure-monitor-deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="ea2f5-128">For guidance on how to set up monitoring and basic alerting, see [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md).</span></span> 

<span data-ttu-id="ea2f5-129">使用本指南，你可以创建一个易于使用的仪表板，以在你的部署中识别 Microsoft 团队会议室的任何问题。</span><span class="sxs-lookup"><span data-stu-id="ea2f5-129">Using this guidance, you can create a simple-to-use dashboard to identify any issues with your Microsoft Teams Rooms units across your deployment.</span></span> 

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="ea2f5-130">决策点</span><span class="sxs-lookup"><span data-stu-id="ea2f5-130">Decision points</span></span>|<ul><li><span data-ttu-id="ea2f5-131">确认你将使用 Operations Management Suite 监视 Microsoft 团队会议室部署。</span><span class="sxs-lookup"><span data-stu-id="ea2f5-131">Confirm that you'll use Operations Management Suite to monitor your Microsoft Teams Rooms deployment.</span></span></li><li><span data-ttu-id="ea2f5-132">确定要用于电子邮件通知的目标通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="ea2f5-132">Decide the target distribution list you’ll use for email alerts.</span></span></li></ul>|
|![](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="ea2f5-133">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ea2f5-133">Next steps</span></span>|<ul><li><span data-ttu-id="ea2f5-134">定义你的质量和可靠性监视方法。</span><span class="sxs-lookup"><span data-stu-id="ea2f5-134">Define your quality and reliability monitoring approach.</span></span></li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a><span data-ttu-id="ea2f5-135">质量和可靠性监视（CQD）</span><span class="sxs-lookup"><span data-stu-id="ea2f5-135">Quality and reliability monitoring (CQD)</span></span>

<span data-ttu-id="ea2f5-136">我们建议你在部署中实现持续运营质量和可靠性监视过程，以监控通话的趋势分析和会议质量以及可靠性，从而确定任何需要考虑的问题并努力解决问题。</span><span class="sxs-lookup"><span data-stu-id="ea2f5-136">We recommend that you implement ongoing operational quality and reliability monitoring procedures as part of your deployment to monitor the trending of call and meeting quality and reliability, identifying any areas of concern and working toward a resolution.</span></span> 

<span data-ttu-id="ea2f5-137">将生成信息上载到 CQD 时，你可以在每个建筑物级别上调查通话质量和可靠性趋势，这使你可以轻松地比较建筑物并将注意力集中在特定问题上。</span><span class="sxs-lookup"><span data-stu-id="ea2f5-137">When you upload your building information to CQD you can investigate call quality and reliability trends on a per-building level, which makes it easy to compare buildings and focus your attention on specific problems.</span></span>

<span data-ttu-id="ea2f5-138">我们建议你查看并按照[体验质量检查指南](https://aka.ms/qerguide)来确定质量和可靠性趋势，并创建行动计划来解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="ea2f5-138">We recommend that you review and follow the [Quality of Experience Review Guide](https://aka.ms/qerguide) to identify quality and reliability trends, and create an action plan to resolve them.</span></span> 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a><span data-ttu-id="ea2f5-139">更新 Microsoft 团队会议室 OS 和 Microsoft 团队聊天室应用程序</span><span class="sxs-lookup"><span data-stu-id="ea2f5-139">Updating the Microsoft Teams Rooms OS and Microsoft Teams Rooms application</span></span>

<span data-ttu-id="ea2f5-140">我们建议你更新 Microsoft 团队会议室操作系统和 Microsoft 团队聊天室应用程序，以受益于产品更新和改进。</span><span class="sxs-lookup"><span data-stu-id="ea2f5-140">We recommend that you update the Microsoft Teams Rooms OS and Microsoft Teams Rooms application to benefit from product updates and improvements.</span></span> <span data-ttu-id="ea2f5-141">有关详细指导，请参阅[管理 Microsoft 团队聊天室](rooms-operations.md#software-updates)。</span><span class="sxs-lookup"><span data-stu-id="ea2f5-141">For detailed guidance, see [Manage Microsoft Teams Rooms](rooms-operations.md#software-updates).</span></span> 

## <a name="windows-updates"></a><span data-ttu-id="ea2f5-142">Windows 更新</span><span class="sxs-lookup"><span data-stu-id="ea2f5-142">Windows Updates</span></span>

<span data-ttu-id="ea2f5-143">Microsoft 团队聊天室在 Windows 10 企业版 IoT 或 Windows 10 企业版（VL）上运行，并作为标准桌面接收相同的 Windows 更新和 OS 版本。</span><span class="sxs-lookup"><span data-stu-id="ea2f5-143">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span> <span data-ttu-id="ea2f5-144">有关详细信息，请参阅[管理 Windows 更新](updates.md)。</span><span class="sxs-lookup"><span data-stu-id="ea2f5-144">See [Manage Windows Updates](updates.md) for details.</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="ea2f5-145">疑难解答</span><span class="sxs-lookup"><span data-stu-id="ea2f5-145">Troubleshooting</span></span>

<span data-ttu-id="ea2f5-146">我们建议你按照上述部分所述设置 Operations Management Suite 警报，以便你的运营团队和帮助人员将收到任何 Microsoft 团队聊天室问题的通知。</span><span class="sxs-lookup"><span data-stu-id="ea2f5-146">We recommend that you set up Operations Management Suite alerting as described in the section above so that your operations team and helpdesk will be alerted to any Microsoft Teams Rooms issues.</span></span> <span data-ttu-id="ea2f5-147">在[使用 powershell 的远程管理](rooms-operations.md#remote-management-using-powershell)中介绍了用于 PowerShell 远程管理的选项。</span><span class="sxs-lookup"><span data-stu-id="ea2f5-147">The options you have for PowerShell remote management are described in [Remote Management using PowerShell](rooms-operations.md#remote-management-using-powershell).</span></span> <span data-ttu-id="ea2f5-148">当外围设备断开连接时，你可能需要依赖本地 "smart 手" 或 IT 支持来调查和重新连接设备。</span><span class="sxs-lookup"><span data-stu-id="ea2f5-148">In the event that a peripheral device is disconnected, you might need to rely on local “smart hands” or IT support to investigate and reconnect the devices.</span></span> 

<span data-ttu-id="ea2f5-149">有关疑难解答和管理员模式的详细信息，请参阅[管理员模式和设备管理](rooms-operations.md#admin-mode-and-device-management)。</span><span class="sxs-lookup"><span data-stu-id="ea2f5-149">For more information about troubleshooting and admin mode, see [Admin mode and device management](rooms-operations.md#admin-mode-and-device-management).</span></span> 


## <a name="see-also"></a><span data-ttu-id="ea2f5-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ea2f5-150">See also</span></span>

[<span data-ttu-id="ea2f5-151">Microsoft Teams 会议室帮助</span><span class="sxs-lookup"><span data-stu-id="ea2f5-151">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="ea2f5-152">规划 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="ea2f5-152">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="ea2f5-153">部署 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="ea2f5-153">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)

[<span data-ttu-id="ea2f5-154">配置 Microsoft 团队聊天室控制台</span><span class="sxs-lookup"><span data-stu-id="ea2f5-154">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="ea2f5-155">使用 XML 配置文件远程管理 Microsoft 团队聊天室控制台设置</span><span class="sxs-lookup"><span data-stu-id="ea2f5-155">Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file</span></span>](xml-config-file.md)
