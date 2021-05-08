---
title: 音频会议故障排除和已知问题
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 72979911-5319-4de2-a275-4dd9a0f44fe6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '获取使用 Microsoft 作为拨入式会议提供商时已知问题的列表、状态和一些解决方法。 '
ms.openlocfilehash: 71d363ff98fc4590fb6d96cc3e8a8cb77b1fa24c
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237188"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>音频会议故障排除和已知问题

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 **本文适用于使用 microsoft Skype for Business音频会议提供商的用户。它不适用于使用第三方音频会议提供商 (ACP) 。**
  
## <a name="troubleshooting-and-known-issues"></a>故障排除和已知问题

使用 Microsoft 作为音频会议提供商的音频会议当前存在正在跟踪和积极调查的问题，并且在将来的 Microsoft 365 版本中更新该功能时，这些问题可能会得到解决。
  
现在，在解决在组织中设置音频会议以及为使用音频会议Skype for Business时，请使用此作为参考。

|**问题**|**行为/症状**|**已知解决方法**|**发现日期**|
|:-----|:-----|:-----|:-----|
|当会议开始时，进入和退出通知将打开，但在会议开始后不久，它们被关闭。  <br/> |默认情况下，对于参与者从两个应用和拨入Skype for Business加入的会议，会禁用进入和退出通知。 可以在应用应用Skype 会议 **选项**"Skype for Business公告。 对于所有参与者拨入加入的会议，默认情况下会启用进入和退出通知，因为任何参与者都无法获得参与者名单。 当会议开始时，只有与会者呼入时，进入和退出通知将打开，但当参与者使用 Skype for Business 应用加入时，通知将关闭。 关闭后，可以在应用内使用"Skype 会议 **选项**"重新Skype for Business通知。 <br/> |无解决方法。  <br/> |8/30/2017  <br/> |
|如果第一次为用户分配了 E5 许可证，则如果未启用邮箱，则音频会议欢迎电子邮件可能不会传递到用户。  <br/> |如果发生这种情况，你始终可以在管理中心内使用音频会议或 PowerShell 重新发送Skype for Business会议信息。 请参阅 [音频会议设置更改时启用或禁用发送电子邮件](enable-or-disable-sending-emails-when-their-settings-change.md)。  <br/> **注意：** 若要向用户重新发送音频会议 PIN，必须重置 PIN。 这也可通过使用 **音频会议在** Skype for Business 管理中心或 PowerShell 完成。          |无解决方法。  <br/> |8/30/2017  <br/> |
|音频会议呼叫最多可能需要 24 小时才能显示在使用情况报告中。  <br/> |我们期待在将来的服务更新中对此领域进行改进。  <br/> |无解决方法。  <br/> |8/30/2017  <br/> |
|当呼叫者在会议被 Skype for Business 用户锁定后拨入会议网桥时，Skype for Business 应用中没有通知指出用户正在大厅中等待。  <br/> |当前此设置是特意为之，但我们会考虑此反馈以便在未来的服务更新中支持此功能。  <br/> |无解决方法。  <br/> |8/30/2017  <br/> |
|2019 Skype for Business Server (2019 年 3 月 1) 之前分配了音频会议许可证的一位用户可能无法在会议邀请中看到拨入坐标。  <br/> |在Skype for Business Server之前Teams音频会议的用户预配。 它现在受支持，是"会议第 [一"的一个组件](/microsoftteams/meetings-first)。 用户必须具有一个Teams许可证。  <br/> |需要重新激活预配管道。 删除用户的音频会议许可证，等待几个小时，然后重新分配许可证。  <br/> |2019/3/1  <br/> |
   
## <a name="related-topics"></a>相关主题

[尝试或购买音频会议Microsoft 365或Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
