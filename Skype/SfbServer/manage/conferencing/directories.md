---
title: 在 Skype for Business 服务器中创建会议目录
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 摘要：了解如何在 Skype for Business Server 中创建会议目录。
ms.openlocfilehash: 0ed141b743d436ca2082b8a4f5010011a0256479
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991847"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a>在 Skype for Business 服务器中创建会议目录
 
**摘要：** 了解如何在 Skype for Business 服务器中创建会议目录。
  
会议目录在使用 Skype for Business 时，在参与者用于加入会议的字母数字会议 ID 之间保留一个映射，以及电话拨入式会议参与者用于加入会议的仅限数字的会议 ID。 
  
## <a name="create-a-conference-directory"></a>创建会议目录

创建多个会议目录可以确保会议 ID 短暂停留，直到创建了大量会议。 
  
如果组织中每个用户的会议数量为典型值，建议为池中的每 999 个用户创建一个会议目录。通过使用此指南，通常可使会议 ID 保持较小数量。但是，只要会议目录数（所有池中）超过 9，会议 ID 长度就会增加以支持更多会议。
  
会议 ID 的格式如下： 
  
```
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

若要创建会议目录，请使用 **New-CsConferenceDirectory** cmdlet。例如，下面的命令创建 Identify 为 42 的会议目录，托管在池 atl-cs-001.litwareinc.com 上面：
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

有关详细信息，请参阅[CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps)。
  

