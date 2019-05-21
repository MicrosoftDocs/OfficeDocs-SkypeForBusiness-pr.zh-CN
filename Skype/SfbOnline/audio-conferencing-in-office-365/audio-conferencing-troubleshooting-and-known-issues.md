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
f1keywords: None
ms.custom:
- Audio Conferencing
description: '获取在使用 Microsoft 作为其电话拨入式会议提供商、状态和某些解决方法时的已知问题列表。 '
ms.openlocfilehash: 9b70cfcdeeb80be43cd0ecc99ca7eced71bb9319
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289580"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>音频会议故障排除和已知问题

 **本文适用于使用 Microsoft 作为其音频会议提供商的 Skype for business 用户。它不会应用于使用第三方音频会议提供商 (ACP) 的客户。**
  
## <a name="troubleshooting-and-known-issues"></a>疑难解答和已知问题

使用 Microsoft 作为音频会议提供商的音频会议包含当前正在跟踪和主动调查的问题, 并且在 Office 365 的未来版本中更新功能时可能会解决这些问题。
  
现在, 当你解决在你的组织中使用 Skype for Business 设置和处理人员的潜在问题时, 请使用此参考。

|**问题**|**行为/症状**|**已知解决方法**|**发现日期**|
|:-----|:-----|:-----|:-----|
|当会议启动时, 进入和退出通知将处于打开状态, 但他们在会议启动后很快就会关闭。  <br/> |默认情况下, 将对参与者从两个 Skype for Business 应用和他们拨入时的会议禁用进入和退出通知。 你可以在 skype for business 应用中的**Skype 会议选项**中启用通知。 对于所有参与者拨入加入的会议，默认情况下会启用进入和退出通知，因为任何参与者都无法获得参与者名单。 当会议已开始且仅参与者呼叫时, 将打开 "进入和退出" 通知, 但当参与者使用 Skype for Business 应用进行联接时, 将关闭通知。 关闭时, 可以使用 skype for Business 应用中的**Skype 会议选项**重新启用通知。 <br/> |无解决方法。  <br/> |8/30/2017  <br/> |
|如果用户是通过分配一个 E5 许可证首次预配的, 则在未启用该邮箱的情况下, 不会向用户发送音频会议欢迎电子邮件。  <br/> |如果发生这种情况, 您始终可以使用 Skype for Business 管理中心中的**音频会议**或使用 PowerShell 重新发送用户的音频会议信息。 请参阅[在音频会议设置更改时启用或禁用发送电子邮件](enable-or-disable-sending-emails-when-their-settings-change.md)。  <br/> **注意:** 为了将音频会议 PIN 重新发送给用户, 必须重置 PIN。 也可以在 Skype for Business 管理中心或使用 PowerShell 中使用**音频会议**来执行此操作。          |无解决方法。  <br/> |8/30/2017  <br/> |
|音频会议呼叫可能需要长达24小时才能显示在使用情况报告中。  <br/> |我们期待在未来的服务更新中对此领域进行改进。  <br/> |无解决方法。  <br/> |8/30/2017  <br/> |
|当呼叫者在会议已被 Skype for Business 用户锁定之后拨入会议桥后, Skype for business 应用程序中没有通知, 说明用户正在大厅中等待。  <br/> |当前此设置是特意为之，但我们会考虑此反馈以便在未来的服务更新中支持此功能。  <br/> |无解决方法。  <br/> |8/30/2017  <br/> |
   
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
