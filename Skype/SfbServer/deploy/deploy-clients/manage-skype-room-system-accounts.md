---
title: 管理 Skype 会议室系统帐户
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: 阅读本主题，了解如何管理 Skype 会议室系统帐户。
ms.openlocfilehash: 4c276d4acf0cf15df7689fa5c11a0e6e2cde785b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212619"
---
# <a name="manage-skype-room-system-accounts"></a>管理 Skype 会议室系统帐户
 
阅读本主题，了解如何管理 Skype 会议室系统帐户。 

> [!NOTE]
> Microsoft 团队聊天室是一种不同的产品具有不同的依赖项以及部署过程。 有关 Microsoft 团队聊天室的信息，请参阅 Microsoft 团队聊天室[管理概述](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)。
  
## <a name="move-the-skype-room-system-account-between-pools"></a>池之间移动 Skype 会议室系统帐户

如果您需要 Skype 会议室系统帐户在一个 Skype 业务服务器池之间移动 （例如，在升级过程），请使用以下命令将 Skype 会议室系统帐户池： 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Skype 业务服务禁用的 Skype 会议室系统帐户

如果您需要禁用现有 Skype 会议室系统上的帐户从 Skype Business services Skype 业务服务器池，请使用以下命令禁用帐户： 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>可选： Active Directory 中创建的 Skype 会议室系统管理员组

通过使用 Skype 会议室系统装置 PC 上的本地管理员权限的域用户能完全管理加入到域每个 Skype 会议室系统客户端。 因此，您可以在 Active Directory 中创建专用的管理员组并放弃此组的管理权限期间设置新的 Skype 会议室系统计算机。
  

