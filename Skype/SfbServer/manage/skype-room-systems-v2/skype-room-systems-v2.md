---
title: Skype 会议室系统 v2 的管理概述
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
description: Skype 会议室系统 v2 的管理概述。
ms.openlocfilehash: b30406c9f186fad699056a78ed1b18da9f59537a
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699350"
---
# <a name="management-overview"></a><span data-ttu-id="17284-103">管理概述</span><span class="sxs-lookup"><span data-stu-id="17284-103">Management overview</span></span> 

<span data-ttu-id="17284-104">非常重要，在开发并执行日常维护和操作，以确保您的 Skype 会议室系统 v2 系统供您的用户，并且提供出色的用户体验。</span><span class="sxs-lookup"><span data-stu-id="17284-104">It’s essential that you develop and execute ongoing maintenance and operations to ensure that your Skype Room Systems v2 systems are available for your users and deliver a great user experience.</span></span> 

## <a name="monitoring"></a><span data-ttu-id="17284-105">监控</span><span class="sxs-lookup"><span data-stu-id="17284-105">Monitoring</span></span> 

<span data-ttu-id="17284-106">监视 Skype 会议室系统 v2 系统包含两个关键活动：</span><span class="sxs-lookup"><span data-stu-id="17284-106">Monitoring Skype Room Systems v2 systems consists of two key activities:</span></span>

-  <span data-ttu-id="17284-107">设备、 应用程序和外围设备监视</span><span class="sxs-lookup"><span data-stu-id="17284-107">Device, application, and peripheral device monitoring</span></span>

-  <span data-ttu-id="17284-108">质量和可靠性监视 (CQD)</span><span class="sxs-lookup"><span data-stu-id="17284-108">Quality and reliability monitoring (CQD)</span></span>

### <a name="skype-room-systems-v2-device-application-and-peripheral-device-monitoring"></a><span data-ttu-id="17284-109">Skype 会议室系统 v2 设备、 应用程序和外围设备监视</span><span class="sxs-lookup"><span data-stu-id="17284-109">Skype Room Systems v2 device, application, and peripheral device monitoring</span></span>

<span data-ttu-id="17284-110">若要确保用户能够使用 Skype 会议室系统 v2 单位，单位必须位于、 与 Skype 会议室系统 v2 应用程序正确配置，连接到网络和连接到正常运行的外围设备。</span><span class="sxs-lookup"><span data-stu-id="17284-110">To ensure that users are able to use the Skype Room Systems v2 units, the units must be on, connected to the network with the Skype Room Systems v2 application correctly configured, and be connected to functioning peripheral devices.</span></span> 


<span data-ttu-id="17284-111">Skype 会议室系统 v2 应用程序和连接的外围设备的状态信息写入到 Windows 事件日志的 Skype 会议室系统 v2 应用程序并记录[本文中](oms.md#understand-the-log-entries)。</span><span class="sxs-lookup"><span data-stu-id="17284-111">Information about the state of the Skype Room Systems v2 application and connected peripheral devices is written by the Skype Room Systems v2 application to the Windows event log and documented [in this article](oms.md#understand-the-log-entries).</span></span> 

|<span data-ttu-id="17284-112">**设置**</span><span class="sxs-lookup"><span data-stu-id="17284-112">**Setting**</span></span>|<span data-ttu-id="17284-113">**允许**</span><span class="sxs-lookup"><span data-stu-id="17284-113">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="17284-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span><span class="sxs-lookup"><span data-stu-id="17284-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span></span>  <br/> |<span data-ttu-id="17284-115">允许 Skype 会议室系统 v2 启动</span><span class="sxs-lookup"><span data-stu-id="17284-115">Enables Skype Room Systems v2 to boot up</span></span>  <br/> |
|<span data-ttu-id="17284-116">电源管理-\>上交流，关闭屏幕 10 分钟后</span><span class="sxs-lookup"><span data-stu-id="17284-116">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="17284-117">电源管理-\>上交流，从不提供系统进入休眠模式</span><span class="sxs-lookup"><span data-stu-id="17284-117">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="17284-118">允许 Skype 会议室系统 v2 附加显示关闭并自动唤醒</span><span class="sxs-lookup"><span data-stu-id="17284-118">Enables Skype Room Systems v2 to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="17284-119">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="17284-119">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="17284-120">或对本地帐户禁用密码过期的等效方法。</span><span class="sxs-lookup"><span data-stu-id="17284-120">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="17284-121">如果此操作失败，将最终导致 Skype 帐户无法登录，且被告知密码过期。</span><span class="sxs-lookup"><span data-stu-id="17284-121">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="17284-122">请注意，这会影响计算机上的所有本地帐户，因此，此设置失败还会导致已有的管理帐户最终也过期。</span><span class="sxs-lookup"><span data-stu-id="17284-122">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="17284-123">启用 Skype 帐户以始终登录</span><span class="sxs-lookup"><span data-stu-id="17284-123">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="17284-124">[配置文件项目](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx)中讨论了如何使用组策略传输文件。</span><span class="sxs-lookup"><span data-stu-id="17284-124">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="17284-125">使用 PowerShell 进行远程管理</span><span class="sxs-lookup"><span data-stu-id="17284-125">Remote Management using PowerShell</span></span>
<span data-ttu-id="17284-126"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="17284-126"></span></span>


<span data-ttu-id="17284-127">我们建议使用 Microsoft 操作管理器套件监视 Skype 会议室系统 v2 系统。</span><span class="sxs-lookup"><span data-stu-id="17284-127">We recommend that you use Microsoft Operations Manager Suite to monitor your Skype Room Systems v2 systems.</span></span> <span data-ttu-id="17284-128">有关如何设置监视和基本警报的指南，请参阅[使用 OMS 的部署 Skype 会议室系统 v2 管理](../../deploy/deploy-clients/with-oms.md)。</span><span class="sxs-lookup"><span data-stu-id="17284-128">For guidance on how to set up monitoring and basic alerting, see [Deploy Skype Room Systems v2 management with OMS](../../deploy/deploy-clients/with-oms.md).</span></span> 

<span data-ttu-id="17284-129">使用本指南，您可以创建简单易用的仪表板来确定与您 Skype 会议室系统 v2 单位的任何问题，您的部署。</span><span class="sxs-lookup"><span data-stu-id="17284-129">Using this guidance, you can create a simple-to-use dashboard to identify any issues with your Skype Room Systems v2 units across your deployment.</span></span> 

|    |     |
|-----------|------------|
|![](../../media/audio_conferencing_image7.png) <br/><span data-ttu-id="17284-130">决策点</span><span class="sxs-lookup"><span data-stu-id="17284-130">Decision points</span></span>|<ul><li><span data-ttu-id="17284-131">确认您将使用操作管理套件监视 Skype 会议室系统 v2 部署。</span><span class="sxs-lookup"><span data-stu-id="17284-131">Confirm that you'll use Operations Management Suite to monitor your Skype Room Systems v2 deployment.</span></span></li><li><span data-ttu-id="17284-132">决定将使用电子邮件通知的目标通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="17284-132">Decide the target distribution list you’ll use for email alerts.</span></span></li></ul>|
|![](../../media/audio_conferencing_image9.png)<br/><span data-ttu-id="17284-133">后续步骤</span><span class="sxs-lookup"><span data-stu-id="17284-133">Next steps</span></span>|<ul><li><span data-ttu-id="17284-134">定义质量和可靠性监视方法。</span><span class="sxs-lookup"><span data-stu-id="17284-134">Define your quality and reliability monitoring approach.</span></span></li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a><span data-ttu-id="17284-135">质量和可靠性监视 (CQD)</span><span class="sxs-lookup"><span data-stu-id="17284-135">Quality and reliability monitoring (CQD)</span></span>

<span data-ttu-id="17284-136">我们建议您确定需要关注的任何区域和解决使用实现日常操作的质量和可靠性监视您的部署以监控呼叫和会议质量和可靠性的趋势的一部分的过程。</span><span class="sxs-lookup"><span data-stu-id="17284-136">We recommend that you implement ongoing operational quality and reliability monitoring procedures as part of your deployment to monitor the trending of call and meeting quality and reliability, identifying any areas of concern and working toward a resolution.</span></span> 

<span data-ttu-id="17284-137">上传到 CQD 构建信息时可以调查构建每个级别，这便于比较建筑物和重点关注特定问题的呼叫的质量和可靠性趋势。</span><span class="sxs-lookup"><span data-stu-id="17284-137">When you upload your building information to CQD you can investigate call quality and reliability trends on a per-building level, which makes it easy to compare buildings and focus your attention on specific problems.</span></span> <span data-ttu-id="17284-138">有关详细信息，下载[监视器-CQD 的 Skype 业务 Online 送达和操作指南](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15)。</span><span class="sxs-lookup"><span data-stu-id="17284-138">For more information, download the [Monitor-CQD for Skype for Business Online-Delivery and Operations Guide](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15).</span></span> 

<span data-ttu-id="17284-139">我们建议您查看和[用户体验质量查看指南](https://aka.ms/qerguide)以了解质量和可靠性趋势和创建操作计划以解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="17284-139">We recommend that you review and follow the [Quality of Experience Review Guide](https://aka.ms/qerguide) to identify quality and reliability trends, and create an action plan to resolve them.</span></span> 

## <a name="updating-the-skype-room-systems-v2-os-and-skype-room-systems-application"></a><span data-ttu-id="17284-140">更新 Skype 会议室系统 v2 OS 和 Skype 会议室系统应用程序</span><span class="sxs-lookup"><span data-stu-id="17284-140">Updating the Skype Room Systems v2 OS and Skype Room Systems application</span></span> 

<span data-ttu-id="17284-141">我们建议您更新的 Skype 会议室系统 v2 OS 和 Skype 会议室系统 v2 应用程序从产品更新和改进功能受益。</span><span class="sxs-lookup"><span data-stu-id="17284-141">We recommend that you update the Skype Room Systems v2 OS and Skype Room Systems v2 application to benefit from product updates and improvements.</span></span> <span data-ttu-id="17284-142">详细指南，请参阅[管理 Skype 会议室系统 v2](room-systems-v2-operations.md#software-updates)。</span><span class="sxs-lookup"><span data-stu-id="17284-142">For detailed guidance, see [Manage Skype Room Systems v2](room-systems-v2-operations.md#software-updates).</span></span> 

## <a name="windows-updates"></a><span data-ttu-id="17284-143">Windows 更新</span><span class="sxs-lookup"><span data-stu-id="17284-143">Windows Updates</span></span>

<span data-ttu-id="17284-144">Skype 会议室系统 v2 (SR v2) Windows 10 企业 IoT 或 Windows 10 企业 (VL) 上运行并接收作为标准桌面相同的 Windows 更新和操作系统版本。</span><span class="sxs-lookup"><span data-stu-id="17284-144">Skype Room System v2 (SRS v2) runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span> <span data-ttu-id="17284-145">有关详细信息，请参阅[管理 Windows 更新](updates.md)。</span><span class="sxs-lookup"><span data-stu-id="17284-145">See [Manage Windows Updates](updates.md) for details.</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="17284-146">故障排除</span><span class="sxs-lookup"><span data-stu-id="17284-146">Troubleshooting</span></span>

<span data-ttu-id="17284-147">我们建议您设置操作管理套件警报如以便任何 Skype 会议室系统 v2 问题将通知您的运营团队和帮助台以上一节中所述。</span><span class="sxs-lookup"><span data-stu-id="17284-147">We recommend that you set up Operations Management Suite alerting as described in the section above so that your operations team and helpdesk will be alerted to any Skype Room Systems v2 issues.</span></span> <span data-ttu-id="17284-148">PowerShell 远程管理的选项是[远程管理使用 PowerShell](room-systems-v2-operations.md#remote-management-using-powershell)中所述。</span><span class="sxs-lookup"><span data-stu-id="17284-148">The options you have for PowerShell remote management are described in [Remote Management using PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span></span> <span data-ttu-id="17284-149">中的外围设备已断开连接，您可能需要依赖于本地"智能指针"或 IT 支持调查和重新连接设备。</span><span class="sxs-lookup"><span data-stu-id="17284-149">In the event that a peripheral device is disconnected, you might need to rely on local “smart hands” or IT support to investigate and reconnect the devices.</span></span> 

<span data-ttu-id="17284-150">有关疑难解答和管理模式的详细信息，请参阅[管理 Skype 会议室系统 v2](room-systems-v2-operations.md#admin-mode-and-device-management)。</span><span class="sxs-lookup"><span data-stu-id="17284-150">For more information about troubleshooting and admin mode, see [Manage Skype Room Systems v2](room-systems-v2-operations.md#admin-mode-and-device-management).</span></span> 


## <a name="see-also"></a><span data-ttu-id="17284-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="17284-151">See also</span></span>

[<span data-ttu-id="17284-152">Skype 会议室系统版本 2 帮助</span><span class="sxs-lookup"><span data-stu-id="17284-152">Skype Room Systems version 2 help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="17284-153">Plan for Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="17284-153">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[<span data-ttu-id="17284-154">部署 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="17284-154">Deploy Skype Room Systems v2</span></span>](../../deploy/deploy-clients/room-systems-v2.md)

[<span data-ttu-id="17284-155">配置 Skype 会议室系统 v2 控制台</span><span class="sxs-lookup"><span data-stu-id="17284-155">Configure a Skype Room Systems v2 console</span></span>](../../deploy/deploy-clients/console.md)

[<span data-ttu-id="17284-156">使用 XML 配置文件远程管理 Skype 会议室系统 v2 控制台设置</span><span class="sxs-lookup"><span data-stu-id="17284-156">Manage a Skype Room Systems v2 console settings remotely with an XML configuration file</span></span>](xml-config-file.md)
