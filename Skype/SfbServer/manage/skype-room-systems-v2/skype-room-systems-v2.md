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
# <a name="management-overview"></a>管理概述 

非常重要，在开发并执行日常维护和操作，以确保您的 Skype 会议室系统 v2 系统供您的用户，并且提供出色的用户体验。 

## <a name="monitoring"></a>监控 

监视 Skype 会议室系统 v2 系统包含两个关键活动：

-  设备、 应用程序和外围设备监视

-  质量和可靠性监视 (CQD)

### <a name="skype-room-systems-v2-device-application-and-peripheral-device-monitoring"></a>Skype 会议室系统 v2 设备、 应用程序和外围设备监视

若要确保用户能够使用 Skype 会议室系统 v2 单位，单位必须位于、 与 Skype 会议室系统 v2 应用程序正确配置，连接到网络和连接到正常运行的外围设备。 


Skype 会议室系统 v2 应用程序和连接的外围设备的状态信息写入到 Windows 事件日志的 Skype 会议室系统 v2 应用程序并记录[本文中](oms.md#understand-the-log-entries)。 

|**设置**|**允许**|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1  <br/> |允许 Skype 会议室系统 v2 启动  <br/> |
|电源管理-\>上交流，关闭屏幕 10 分钟后  <br/> 电源管理-\>上交流，从不提供系统进入休眠模式  <br/> |允许 Skype 会议室系统 v2 附加显示关闭并自动唤醒  <br/> |
|net accounts /maxpwage:unlimited  <br/> 或对本地帐户禁用密码过期的等效方法。 如果此操作失败，将最终导致 Skype 帐户无法登录，且被告知密码过期。 请注意，这会影响计算机上的所有本地帐户，因此，此设置失败还会导致已有的管理帐户最终也过期。  <br/> |启用 Skype 帐户以始终登录  <br/> |
   
[配置文件项目](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx)中讨论了如何使用组策略传输文件。
  
## <a name="remote-management-using-powershell"></a>使用 PowerShell 进行远程管理
<a name="RemotePS"> </a>


我们建议使用 Microsoft 操作管理器套件监视 Skype 会议室系统 v2 系统。 有关如何设置监视和基本警报的指南，请参阅[使用 OMS 的部署 Skype 会议室系统 v2 管理](../../deploy/deploy-clients/with-oms.md)。 

使用本指南，您可以创建简单易用的仪表板来确定与您 Skype 会议室系统 v2 单位的任何问题，您的部署。 

|    |     |
|-----------|------------|
|![](../../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确认您将使用操作管理套件监视 Skype 会议室系统 v2 部署。</li><li>决定将使用电子邮件通知的目标通讯组列表。</li></ul>|
|![](../../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>定义质量和可靠性监视方法。</li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a>质量和可靠性监视 (CQD)

我们建议您确定需要关注的任何区域和解决使用实现日常操作的质量和可靠性监视您的部署以监控呼叫和会议质量和可靠性的趋势的一部分的过程。 

上传到 CQD 构建信息时可以调查构建每个级别，这便于比较建筑物和重点关注特定问题的呼叫的质量和可靠性趋势。 有关详细信息，下载[监视器-CQD 的 Skype 业务 Online 送达和操作指南](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15)。 

我们建议您查看和[用户体验质量查看指南](https://aka.ms/qerguide)以了解质量和可靠性趋势和创建操作计划以解决这些问题。 

## <a name="updating-the-skype-room-systems-v2-os-and-skype-room-systems-application"></a>更新 Skype 会议室系统 v2 OS 和 Skype 会议室系统应用程序 

我们建议您更新的 Skype 会议室系统 v2 OS 和 Skype 会议室系统 v2 应用程序从产品更新和改进功能受益。 详细指南，请参阅[管理 Skype 会议室系统 v2](room-systems-v2-operations.md#software-updates)。 

## <a name="windows-updates"></a>Windows 更新

Skype 会议室系统 v2 (SR v2) Windows 10 企业 IoT 或 Windows 10 企业 (VL) 上运行并接收作为标准桌面相同的 Windows 更新和操作系统版本。 有关详细信息，请参阅[管理 Windows 更新](updates.md)。


## <a name="troubleshooting"></a>故障排除

我们建议您设置操作管理套件警报如以便任何 Skype 会议室系统 v2 问题将通知您的运营团队和帮助台以上一节中所述。 PowerShell 远程管理的选项是[远程管理使用 PowerShell](room-systems-v2-operations.md#remote-management-using-powershell)中所述。 中的外围设备已断开连接，您可能需要依赖于本地"智能指针"或 IT 支持调查和重新连接设备。 

有关疑难解答和管理模式的详细信息，请参阅[管理 Skype 会议室系统 v2](room-systems-v2-operations.md#admin-mode-and-device-management)。 


## <a name="see-also"></a>另请参阅

[Skype 会议室系统版本 2 帮助](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Plan for Skype Room Systems v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[部署 Skype 会议室系统 v2](../../deploy/deploy-clients/room-systems-v2.md)

[配置 Skype 会议室系统 v2 控制台](../../deploy/deploy-clients/console.md)

[使用 XML 配置文件远程管理 Skype 会议室系统 v2 控制台设置](xml-config-file.md)
