---
title: 管理 Skype 会议室系统帐户
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
description: 阅读本主题，了解如何管理 Skype 会议室系统帐户。
ms.openlocfilehash: c47765b617e0856d1db25c7ed4902fe0af9924f2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-skype-room-system-accounts"></a>管理 Skype 会议室系统帐户
 
阅读本主题，了解如何管理 Skype 会议室系统帐户。
  
## <a name="move-the-skype-room-system-account-between-pools"></a>池间移动的 Skype 的空间系统帐户

如果您需要在 Skype 的空间系统帐户在一个 Skype 业务服务器池之间移动 （例如，在升级期间），使用下面的命令将 Skype 的空间系统帐户池移动： 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Skype 在 Skype 的空间系统帐户禁用业务服务

如果您需要禁用现有 Skype 的空间系统上的帐户从 Skype 业务服务 Skype 业务服务器池，请使用以下命令来禁用该帐户： 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>可选： 在活动目录中创建的 Skype 的空间系统管理员组

使用 Skype 的空间系统装置计算机上的本地管理员权限的域用户可以完全管理加入域每个 Skype 的空间系统客户端。 因此，可以在 Active Directory 中创建专用的管理员组，并且放弃此组的管理权限集中在新的 Skype 的空间系统计算机。
  

