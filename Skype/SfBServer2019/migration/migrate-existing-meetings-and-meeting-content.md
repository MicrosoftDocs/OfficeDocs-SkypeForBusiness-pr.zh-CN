---
title: 迁移现有会议和会议内容
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 当用户帐户从业务服务器 2019年服务器移至 Skype 时，与该用户帐户移动以下信息：
ms.openlocfilehash: bf10fa6b4ad4d555ce80dee5ec4e4a6584020ac7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231656"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>迁移现有会议和会议内容

当用户帐户移至 Skype 业务服务器 2019年服务器时，与该用户帐户移动以下信息：
  
- **已由用户安排的会议**。 这包括移动会议目录和会议数据。
    
- **用户的个人标识号 (PIN)**。 用户的当前 PIN 之前仍然到期或用户请求新 PIN。
    
下面的用户帐户信息不会移到新服务器。
  
- **会议内容**。 若要移动会议期间共享的内容，如 PowerPoint、 白板、 附件或投票数据，则会将 **-MoveConferenceData**参数用作**Move-csuser** cmdlet 的一部分。 
    

