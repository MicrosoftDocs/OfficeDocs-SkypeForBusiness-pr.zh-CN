---
title: Microsoft 团队聊天室的管理概述
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection: M365-voice
description: Microsoft 团队聊天室的管理概述。
ms.openlocfilehash: db1569f86ba0066691b6797517351087307cf38a
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "36427870"
---
# <a name="management-overview"></a>管理概述 

你必须开发和执行持续维护和操作, 以确保你的 Microsoft 团队聊天室系统适用于你的用户并提供出色的用户体验。 

## <a name="monitoring"></a>监控 

监视 Microsoft 团队聊天室系统包含两个关键活动:

-  设备、应用程序和外围设备监控

-  质量和可靠性监视 (CQD)

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a>Microsoft 团队聊天室设备、应用程序和外围设备监控

为确保用户能够使用 Microsoft 团队房间单元, 设备必须处于打开状态, 连接到 Microsoft 团队聊天室应用程序的网络已正确配置, 并连接到正常工作的外围设备。 


有关 Microsoft 团队聊天室应用程序和连接的外围设备状态的信息由 Microsoft 团队聊天室应用程序写入 Windows 事件日志, 并在[了解日志条目](azure-monitor-manage.md#understand-the-log-entries)中记录。 

|**设置**|**这样**|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1  <br/> |支持 Microsoft 团队会议室启动  <br/> |
|电源管理-\>通过交流, 10 分钟后关闭屏幕  <br/> 电源管理-\>在交流上, 从不将系统置于睡眠状态  <br/> |使 Microsoft 团队会议室能够关闭附加的显示并自动唤醒  <br/> |
|net accounts /maxpwage:unlimited  <br/> 或对本地帐户禁用密码过期的等效方法。 如果此操作失败，将最终导致 Skype 帐户无法登录，且被告知密码过期。 请注意，这会影响计算机上的所有本地帐户，因此，此设置失败还会导致已有的管理帐户最终也过期。  <br/> |启用 Skype 帐户以始终登录  <br/> |
   
在 "[配置文件" 项目](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx)中讨论了使用组策略传输文件的内容。
  
## <a name="remote-management-using-powershell"></a>使用 PowerShell 进行远程管理
<a name="RemotePS"> </a>

我们建议你使用 Microsoft Operations Manager Suite 监视 Microsoft 团队聊天室系统。 有关如何设置监视和基本警报的指南, 请参阅[通过 Azure 监视器部署 Microsoft 团队聊天室管理](azure-monitor-deploy.md)。 

使用本指南, 你可以创建一个易于使用的仪表板, 以在你的部署中识别 Microsoft 团队会议室的任何问题。 

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确认你将使用 Operations Management Suite 监视 Microsoft 团队会议室部署。</li><li>确定要用于电子邮件通知的目标通讯组列表。</li></ul>|
|![](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>定义你的质量和可靠性监视方法。</li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a>质量和可靠性监视 (CQD)

我们建议你在部署中实现持续运营质量和可靠性监视过程, 以监控通话的趋势分析和会议质量以及可靠性, 从而确定任何需要考虑的问题并努力解决问题。 

将生成信息上载到 CQD 时, 你可以在每个建筑物级别上调查通话质量和可靠性趋势, 这使你可以轻松地比较建筑物并将注意力集中在特定问题上。

我们建议你查看并按照[体验质量检查指南](https://aka.ms/qerguide)来确定质量和可靠性趋势, 并创建行动计划来解决这些问题。 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a>更新 Microsoft 团队会议室 OS 和 Microsoft 团队聊天室应用程序

我们建议你更新 Microsoft 团队会议室操作系统和 Microsoft 团队聊天室应用程序, 以受益于产品更新和改进。 有关详细指导, 请参阅[管理 Microsoft 团队聊天室](room-systems-v2-operations.md#software-updates)。 

## <a name="windows-updates"></a>Windows 更新

Microsoft 团队聊天室在 Windows 10 企业版 IoT 或 Windows 10 企业版 (VL) 上运行, 并作为标准桌面接收相同的 Windows 更新和 OS 版本。 有关详细信息, 请参阅[管理 Windows 更新](updates.md)。


## <a name="troubleshooting"></a>疑难解答

我们建议你按照上述部分所述设置 Operations Management Suite 警报, 以便你的运营团队和帮助人员将收到任何 Microsoft 团队聊天室问题的通知。 在[使用 powershell 的远程管理](room-systems-v2-operations.md#remote-management-using-powershell)中介绍了用于 PowerShell 远程管理的选项。 当外围设备断开连接时, 你可能需要依赖本地 "smart 手" 或 IT 支持来调查和重新连接设备。 

有关疑难解答和管理员模式的详细信息, 请参阅[管理 Microsoft 团队聊天室](room-systems-v2-operations.md#admin-mode-and-device-management)。 


## <a name="see-also"></a>另请参阅

[Microsoft Teams 会议室帮助](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[规划 Microsoft 团队聊天室](skype-room-systems-v2-0.md)

[部署 Microsoft 团队聊天室](room-systems-v2.md)

[配置 Microsoft 团队聊天室控制台](console.md)

[使用 XML 配置文件远程管理 Microsoft 团队聊天室控制台设置](xml-config-file.md)
