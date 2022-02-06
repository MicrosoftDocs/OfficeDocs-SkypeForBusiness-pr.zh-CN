---
title: 管理 Skype 会议室系统账户
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: 阅读本主题，了解如何管理会议室Skype帐户。
---

# <a name="manage-skype-room-system-accounts"></a>管理 Skype 会议室系统账户
 
阅读本主题，了解如何管理会议室Skype帐户。 

> [!NOTE]
> Microsoft Teams 会议室是具有不同的依赖项和部署过程的不同产品。 有关管理Microsoft Teams 会议室，请参阅Microsoft Teams 会议室[管理概述](/microsoftteams/rooms/rooms-manage)。
  
## <a name="move-the-skype-room-system-account-between-pools"></a>在池Skype会议室系统帐户

如果需要将 Skype 会议室系统帐户从一个 Skype for Business Server 池移动到另一个 (例如，在升级) 期间，请使用以下命令移动 Skype 会议室系统帐户池： 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>为Skype禁用会议室系统Skype for Business帐户

如果需要从池上的 Skype 服务Skype for Business现有会议室系统Skype for Business Server，请使用以下命令禁用该帐户： 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>可选：在 Active Directory Skype聊天室系统管理员组

每个Skype加入域的会议室系统客户端都可以由在会议室系统设备电脑上具有本地管理员权限Skype域用户进行管理。 因此，您可以在 Active Directory 中创建专用管理员组，并授予该组在设置新会议室系统计算机Skype管理权限。
