---
title: 管理 Skype 会议室系统帐户
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: b6d61f4ddc9fe5e296ffd98b685e1000151d5db2
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768655"
---
# <a name="manage-skype-room-system-accounts"></a>管理 Skype 会议室系统帐户
 
阅读本主题，了解如何管理 Skype 会议室系统帐户。 

> [!NOTE]
> Microsoft 团队聊天室是具有不同的依赖项和部署过程的其他产品。 有关 Microsoft 团队聊天室的信息，请参阅 Microsoft 团队聊天室[管理概述](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage)。
  
## <a name="move-the-skype-room-system-account-between-pools"></a>在池之间移动 Skype 会议室系统帐户

如果需要将 Skype 会议室系统帐户从一个 Skype for business 服务器池移动到另一个（例如，在升级期间），请使用以下命令移动 Skype 会议室系统帐户池： 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>禁用 Skype for business 服务的 Skype 会议室系统帐户

如果您需要从 Skype for business 服务器池上的 Skype for Business 服务禁用现有 Skype 会议室系统帐户，请使用以下命令禁用帐户： 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>可选：在 Active Directory 中创建 Skype 会议室系统管理员组

加入域的每个 Skype 会议室系统客户都可以通过 Skype 会议室系统设备电脑上具有本地管理员权限的域用户进行完全管理。 因此，你可以在 Active Directory 中创建一个专用管理员组，并在设置新的 Skype 会议室系统计算机期间授予此组管理权限。
  

