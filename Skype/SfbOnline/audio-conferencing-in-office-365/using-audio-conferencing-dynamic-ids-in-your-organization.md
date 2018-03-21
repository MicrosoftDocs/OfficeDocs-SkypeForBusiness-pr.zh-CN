---
title: "在您的组织中使用音频会议动态 Id"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: e55e4bff-fb67-4389-8695-f03024baa9b6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "正在更新音频会议服务以提供每个 Skype 业务和 Microsoft 小组会议与其他会议 Id。 动态的会议 Id 通过静态的会议 Id，是一项显著改进，因为它们提供了："
ms.openlocfilehash: 146e09843fbd9234d4d1b651663d59d7ec48fc49
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
# <a name="using-audio-conferencing-dynamic-ids-in-your-organization"></a>在您的组织中使用音频会议动态 Id

正在更新音频会议服务以提供每个 Skype 业务和 Microsoft 小组会议与其他会议 Id。 动态的会议 Id 通过静态的会议 Id，是一项显著改进，因为它们提供了：
  
- **增强的安全性**会议 Id 是唯一的每个 Skype 业务或 Microsoft 小组会议，预定会议时，将生成。
    
- **提供了更好的背靠背和侧对侧会议体验** 系统会为一个组织者安排的每场会议提供特定的拨入信息，当多个会议的时间彼此邻近时，这些信息可防止一个会议的电话参与者与其他会议的参与者混淆在一起。
    
- **可以无缝过渡** 为组织启用动态会议 ID 后，组织中具有静态会议 ID 的所有已安排会议将继续有效。
    
> [!TIP]
> 动态的 Id 才可用于为启用的用户 * * 音频会议 * * 和 microsoft 设置为其音频会议提供商。 为您的用户，可以[为音频会议提供商指定的 Microsoft](assign-microsoft-as-the-audio-conferencing-provider.md) 。
  
## <a name="what-changes-will-the-users-in-my-organization-see"></a>我的组织中的用户将看到哪些更改？

为您的组织启用了动态会议 Id 之后，任何新的业务或 Microsoft 小组会议，Skype 所计划的启用音频会议将有会议 Id，将从不同组织中的用户他们以前的静态的会议 ID。 他们非常静态的组织者需要提醒用户加入他们他们现在需要在会议邀请中使用新的会议 ID，才能参加它的会议之前的会议 Id。
  
> [!NOTE]
> 计划由具有静态会议 Id 的用户组织启用的 Id 将继续具有静态的会议 Id，因此他们将继续安排会议，而不影响动态会议之前的会议。 
  
这些示例演示两个 Skype 按同一个用户的业务会议的新体验，但是现在都为两个不同的会话 Id: 
  
 **会议 1** 已安排在上午 9 点到上午 10 点，且会议 ID 为 93907123：
  
![First Dynamic Conference ID.](../images/997b2473-7645-46df-9774-95eb070c2239.png)
  
 **会议 2** 已由同一个用户安排在上午 10 点到上午 11 点，且会议 ID 为 16353789：
  
![Second Dynamic Conference IDs](../images/e1eecc76-812b-426c-90e8-80e9f6f4ad31.png)
  
## <a name="related-topics"></a>相关主题

- [设置 Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- [设置音频会议 for Skype Business 和 Microsoft 团队](set-up-audio-conferencing.md)
    
- [Skype for Business 和 Microsoft Teams 外接程序许可](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
    

