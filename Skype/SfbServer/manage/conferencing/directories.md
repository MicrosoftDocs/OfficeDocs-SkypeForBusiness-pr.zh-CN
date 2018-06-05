---
title: 在 Skype for Business Server 2015 中创建会议目录
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 摘要： 了解如何为业务服务器 2015 Skype 创建会议目录。
ms.openlocfilehash: 861172a76da68d39fd9f8213de6e45a892aa1780
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568743"
---
# <a name="create-conference-directories-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中创建会议目录
 
**摘要：** 了解如何为业务服务器 2015 Skype 创建会议目录。
  
会议目录维护参与者加入会议的业务，使用 Skype 时使用的字母数字会议 ID 和电话拨入式会议参与者使用加入会议的仅含数字会议 ID 之间的映射。 
  
## <a name="create-a-conference-directory"></a>创建会议目录

创建多个会议目录可以确保会议 ID 短暂停留，直到创建了大量会议。 
  
如果组织中每个用户的会议数量为典型值，建议为池中的每 999 个用户创建一个会议目录。通过使用此指南，通常可使会议 ID 保持较小数量。但是，只要会议目录数（所有池中）超过 9，会议 ID 长度就会增加以支持更多会议。
  
会议 ID 的格式如下： 
  
```
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

若要创建会议目录，请使用 **New-CsConferenceDirectory** cmdlet。例如，下面的命令创建 Identify 为 42 的会议目录，托管在池 atl-cs-001.litwareinc.com 上面：
  
```
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

有关详细信息，请参阅[New-csconferencedirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps)。
  

