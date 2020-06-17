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
localization_priority: Normal
description: 将用户帐户从迁移到 Skype for business Server 2019 服务器时，将使用该用户帐户移动以下信息：
ms.openlocfilehash: 6513f581f55028ec28d4cf05f1f1b3df37c49e65
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752684"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>迁移现有会议和会议内容

将用户帐户移动到 Skype for business Server 2019 服务器时，将使用该用户帐户移动以下信息：
  
- **用户已安排的会议**。 这包括移动会议目录和会议数据。
    
- **用户的个人标识号（PIN）**。 用户的当前 PIN 将继续工作，直到过期或用户请求新的 PIN。
    
以下用户帐户信息不会移至新服务器。
  
- **会议内容**。 为了移动在会议期间共享的内容（如 PowerPoint、白板、附件或轮询数据），请使用 **-MoveConferenceData**参数作为**get-csuser** cmdlet 的一部分。 
    

