---
title: 请参阅  Skype for Business Online 中的音频会议号码列表
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 2d6b4ed4-e12b-4691-8405-fae720d69425
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '了解如何从 Skype for Business Online 中查找电话拨入式Skype for Business号码。 '
ms.openlocfilehash: 3be641b2a5c4b626f414d1a8ae8ee1b16adc7146
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58586030"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>请参阅  Skype for Business Online 中的音频会议号码列表

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> 有关 Microsoft Teams 中的音频会议号码的信息，请参阅 [Microsoft Teams 的音频会议号码列表](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams)。

当为  Skype for Business 用户设置时音频会议时，您可以查看为音频会议提供给他们的电话号码。 此列表将包含组织可用的所有音频会议电话号码。
  
 **正在搜索价格？** 请参阅 [音频会议定价](https://products.office.com/skype-for-business/audio-conferencing#Requirements)。
  
> [!IMPORTANT]
> **没有包含所有音频会议拨入号码列表的资源。** 如果你希望查看你的地区或国家/地区是否有可用的拨入电话号码，请转到 **Skype for Business** 管理中心语音 电话 号码，单击"添加"，然后单击"新建服务号码  >    >  "。   使用“国家/地区”、“省/直辖市/自治区/地区”和“城市”列表来筛选搜索结果。 此外，如果要查找免费服务号码，请从"州 **/** 地区"**列表中选择**"免费"。
  
如果仅有一个电话号码在你的组织中可用，则会将其作为你的所有用户的默认号码。 当多个电话号码可用时，你可以为每个用户选择默认电话号码。 此默认号码将包含在会议Skype for Business中。
  
你可以看到设置 [邀请中包含的电话号码](set-the-phone-numbers-included-on-invites.md) 以更改单个用户的拨入电话号码。
  
> [!NOTE]
> [!注释] 国内拨入号码供你的组织专用，是唯一可以设为默认电话号码的号码。 但是，国际拨入号码可能会在多个组织之间共享。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>查看音频会议电话号码

1. 使用工作或学校帐户登录。
    
2. 转到管理中心 **> Skype for Business。**
    
3. 在 **Skype for Business管理** 中心的 左侧导航中，转到音频会议 Microsoft  >  **网桥**，然后：
    
   - 您可以查看可用于音频会议的电话号码。
    
   - 您还可以查看位置以及音频会议自动助理将使用的主要和辅助语言。
    
> [!NOTE]
> 你可以转到"**音频** 会议用户"并选择用户的属性，通过从你的组织中可用号码列表中选择新号码来  >  更改默认号码。 请参阅 [设置邀请中包含的电话号码](set-the-phone-numbers-included-on-invites.md)。 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用 [Get-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Get-CsOnlineDialInConferencingServiceNumber) cmdlet。
    
- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用Windows PowerShell，Microsoft 365 Office 365单点管理来管理任务或任务，可在有多个任务需要执行时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为何需要将 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Microsoft 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell相比于仅使用 Microsoft 365 管理中心，在速度、简单性和工作效率方面具有许多优势，例如，一次为许多用户更改设置时。 请在以下主题中了解这些优点：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[尝试或购买音频会议Microsoft 365或Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
