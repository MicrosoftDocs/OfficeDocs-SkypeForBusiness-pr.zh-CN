---
title: 迁移现有会议和会议内容
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 将用户帐户从 2019 Skype for Business Server 2019 服务器时，会随该用户帐户一起移动以下信息：
ms.openlocfilehash: 826b511250e46e2c87720a5b074b43cd545b15c6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589298"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>迁移现有会议和会议内容

将用户帐户移动到 Skype for Business Server 2019 服务器时，会随该用户帐户一起移动以下信息：
  
- **用户已安排的会议**。这包括移动会议目录和会议数据。
    
- **用户的个人标识号 (PIN) 。** 用户的当前 PIN 将继续工作，直到其过期或用户请求新的 PIN。
    
以下用户帐户信息不会移至新服务器。
  
- **会议内容**。 若要移动会议期间共享的内容（如 PowerPoint、白板、附件或投票数据），请使用 **-MoveConferenceData** 参数作为 **Move-CsUser** cmdlet 的一部分。 
    

