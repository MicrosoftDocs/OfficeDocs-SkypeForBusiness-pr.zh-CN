---
title: 在 Microsoft Teams 中设置包含在邀请中的电话号码
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: '获取为呼叫者创建默认电话号码以加入 Microsoft 团队会议的步骤。 '
ms.openlocfilehash: 88032829581224b339f47b34c432629019fd3bac
ms.sourcegitcommit: 33bec766519397f898518a999d358657a413924c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2020
ms.locfileid: "42583109"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>在 Microsoft Teams 中设置包含在邀请中的电话号码

Office 365 中的音频会议使组织中的用户可以创建 Microsoft 团队会议，然后允许用户使用手机拨入这些会议。
  
会议桥为你的组织提供了一套拨入电话号码。 它们都可用于加入会议组织者已创建的会议，但你可以选择在其会议邀请中包括哪些号码。
  
> [!NOTE]
> 会议组织者的会议邀请中最多可以有一个收费和一个免费电话号码，但每个会议邀请的底部还有一个链接，用于打开用来可加入会议的所有拨入电话号码的完整列表。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a>新用户的会议邀请中包含的电话号码的初始分配

启用音频会议的用户的会议邀请中包含的电话号码由默认会议收费电话号码和默认会议免费电话号码用户设置定义。 每个设置指定用户的会议邀请中将包含哪些收费电话号码和免费电话号码。 如上所述，每个会议邀请包含一个收费号码，一个可选的免费电话号码和一个链接，用于打开所有拨入电话号码的完整列表，这些电话号码可用于加入给定的会议。

对于新用户，根据为音频会议服务启用用户时在用户的 Office 365 管理中心中设置的使用位置，分配默认的会议收费号码。 如果在会议桥中有收费号码与用户所在的国家/地区相匹配，则该号码将自动分配为用户的默认收费号码。 如果没有，则定义为该会议桥的默认收费号码的号码将被分配为用户的默认收费号码。  

用户启用音频会议服务后，租户管理员可以随时从其初始值更改用户的默认收费电话号码和免费电话号码。

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>设置或更改会议组织者或用户的默认音频会议电话号码

![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标

1. 在左侧导航中，单击 "**用户**"。

    ![显示在 Microsoft 团队管理中心中选择用户](media/teams-set-phone-numbers-on-invites-image1.png)

2. 从可用用户列表中单击该用户名。

3. 在**音频会议**旁边，单击**编辑**。 
    
    ![单击 "音频会议" 旁边的 "编辑"](media/teams-set-phone-numbers-on-invites-image3.png)

4. 使用 "**收费电话号码**" 或 "免费**电话号码**" 字段输入用户的号码。


> [!IMPORTANT]
> 更改用户的音频会议设置时，必须更新定期和将来的 Microsoft 团队会议，并将其发送给与会者。 

## <a name="want-to-use-windows-powershell"></a>想要使用 Windows PowerShell？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。 
  
    
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[更改音频会议网桥中的电话号码](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
