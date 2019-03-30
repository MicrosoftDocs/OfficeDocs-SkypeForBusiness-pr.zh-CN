---
title: Microsoft 团队聊天室的管理概述
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
ms.collection: M365-voice
description: Microsoft 团队聊天室的管理概述。
ms.openlocfilehash: a06ffc6bb0aa69b493c95a516946c322034913f8
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012491"
---
# <a name="management-overview"></a>管理概述 

非常重要，在开发并执行日常维护和操作，以确保您的 Microsoft 团队聊天室系统供您的用户，并且提供出色的用户体验。 

## <a name="monitoring"></a>监控 

监视 Microsoft 团队聊天室系统包含两个关键活动：

-  设备、 应用程序和外围设备监视

-  质量和可靠性监视 (CQD)

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a>Microsoft 团队聊天室设备、 应用程序和外围设备监视

若要确保用户能够使用的 Microsoft 团队聊天室单位，单位必须位于、 与 Microsoft 团队聊天室应用程序正确配置，连接到网络和连接到正常运行的外围设备。 


有关 Microsoft 团队聊天室应用程序和连接的外围设备的状态信息进行写入到 Windows 事件日志的 Microsoft 团队聊天室应用程序并记录在[了解日志条目](azure-monitor.md#understand-the-log-entries)。 

|**设置**|**允许**|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1  <br/> |启用 Microsoft 团队聊天室启动  <br/> |
|电源管理-\>上交流，关闭屏幕 10 分钟后  <br/> 电源管理-\>上交流，从不提供系统进入休眠模式  <br/> |启用 Microsoft 团队聊天室附加显示关闭并自动唤醒  <br/> |
|net accounts /maxpwage:unlimited  <br/> 或对本地帐户禁用密码过期的等效方法。 如果此操作失败，将最终导致 Skype 帐户无法登录，且被告知密码过期。 请注意，这会影响计算机上的所有本地帐户，因此，此设置失败还会导致已有的管理帐户最终也过期。  <br/> |启用 Skype 帐户以始终登录  <br/> |
   
使用组策略的文件传输将在[配置文件项](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx)讨论。
  
## <a name="remote-management-using-powershell"></a>使用 PowerShell 进行远程管理
<a name="RemotePS"> </a>

我们建议使用 Microsoft 操作管理器套件来监视您的 Microsoft 团队聊天室系统。 有关如何设置监视和基本警报的指南，请参阅[部署 Microsoft 团队聊天室管理使用 Azure 监视器](../../deploy/deploy-clients/azure-monitor.md)。 

使用本指南，您可以创建简单易用的仪表板来确定与 Microsoft 团队聊天室单位的任何问题，您的部署。 

|    |     |
|-----------|------------|
|![](../../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确认您将使用操作管理套件监视您的 Microsoft 团队聊天室部署。</li><li>决定将使用电子邮件通知的目标通讯组列表。</li></ul>|
|![](../../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>定义质量和可靠性监视方法。</li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a>质量和可靠性监视 (CQD)

我们建议您确定需要关注的任何区域和解决使用实现日常操作的质量和可靠性监视您的部署以监控呼叫和会议质量和可靠性的趋势的一部分的过程。 

上传到 CQD 构建信息时可以调查构建每个级别，这便于比较建筑物和重点关注特定问题的呼叫的质量和可靠性趋势。 有关详细信息，下载[监视器-CQD 的 Skype 业务 Online 送达和操作指南](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15)。 

我们建议您查看和[用户体验质量查看指南](https://aka.ms/qerguide)以了解质量和可靠性趋势和创建操作计划以解决这些问题。 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a>更新的 Microsoft 团队聊天室 OS 和 Microsoft 团队聊天室的应用程序

我们建议您更新的 Microsoft 团队聊天室 OS 和 Microsoft 团队聊天室的应用程序从产品更新和改进功能受益。 详细指南，请参阅[Manage Microsoft 团队 Rooms](room-systems-v2-operations.md#software-updates)。 

## <a name="windows-updates"></a>Windows 更新

Microsoft 团队聊天室 Windows 10 企业 IoT 或 Windows 10 企业 (VL) 上运行并接收作为标准桌面相同的 Windows 更新和操作系统版本。 有关详细信息，请参阅[管理 Windows 更新](updates.md)。


## <a name="troubleshooting"></a>疑难解答

我们建议您设置操作管理套件警报如，以便向 Microsoft 团队会议室的任何问题将通知您的运营团队和帮助台以上一节中所述。 PowerShell 远程管理的选项是[远程管理使用 PowerShell](room-systems-v2-operations.md#remote-management-using-powershell)中所述。 中的外围设备已断开连接，您可能需要依赖于本地"智能指针"或 IT 支持调查和重新连接设备。 

有关疑难解答和管理模式的详细信息，请参阅[Manage Microsoft 团队 Rooms](room-systems-v2-operations.md#admin-mode-and-device-management)。 


## <a name="see-also"></a>另请参阅

[Microsoft 团队聊天室帮助](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[规划 Microsoft 团队聊天室](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[部署 Microsoft 团队聊天室](../../deploy/deploy-clients/room-systems-v2.md)

[配置 Microsoft 团队聊天室控制台](../../deploy/deploy-clients/console.md)

[使用 XML 配置文件远程管理 Microsoft 团队聊天室控制台设置](xml-config-file.md)
