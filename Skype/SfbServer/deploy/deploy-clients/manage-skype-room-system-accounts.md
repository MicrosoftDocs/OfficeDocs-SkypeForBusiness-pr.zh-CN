---
title: 管理 Skype 会议室系统账户
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: 阅读本主题，了解如何管理 Skype 会议室系统帐户。
ms.openlocfilehash: e6b905b065badb729ccc9281d63ba050fc032ef2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093290"
---
# <a name="manage-skype-room-system-accounts"></a>管理 Skype 会议室系统账户
 
阅读本主题，了解如何管理 Skype 会议室系统帐户。 

> [!NOTE]
> Microsoft Teams 会议室是具有不同的依赖项和部署过程的不同产品。 有关 Microsoft Teams 会议室的信息，请参阅 Microsoft Teams 会议室 [管理概述](/microsoftteams/rooms/rooms-manage)。
  
## <a name="move-the-skype-room-system-account-between-pools"></a>在池之间移动 Skype 会议室系统帐户

如果需要将 Skype 会议室系统帐户从一个 Skype for Business Server 池移动到另一个 (例如，在升级) 期间，请使用以下命令移动 Skype 会议室系统帐户池： 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>禁用 Skype for Business 服务的 Skype 会议室系统帐户

如果需要从 Skype for Business Server 池上的 Skype for Business 服务禁用现有 Skype 会议室系统帐户，请使用以下命令禁用该帐户： 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>可选：在 Active Directory 中创建 Skype 会议室系统管理员组

加入域的每个 Skype 会议室系统客户端都可以由在 Skype 会议室系统电脑中具有本地管理员权限的域用户完全管理。 因此，可以在 Active Directory 中创建专用管理员组，在设置新的 Skype 会议室系统计算机期间授予此组管理权限。
