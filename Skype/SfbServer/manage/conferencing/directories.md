---
title: 在会议目录中Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 摘要：了解如何在会议Skype for Business Server。
ms.openlocfilehash: ef274901e2d70c9ae5e2184568a5a749e73f774c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763860"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a>在会议目录中Skype for Business Server
 
**摘要：** 了解如何在会议目录中创建Skype for Business Server。
  
会议目录维护使用 Skype for Business 时参与者用于加入会议的字母数字会议 ID 与电话拨入式会议参与者加入会议时使用的仅数字会议 ID 之间的映射。 
  
## <a name="create-a-conference-directory"></a>创建会议目录

创建多个会议目录将确保会议 ID 将短暂停留，直到创建了大量会议。 
  
在每个用户需要参与典型数量会议的组织中，建议您为池中的每 999 个用户创建一个会议目录。 使用此指南，会议 ID 通常可以保持较小。 但是，一旦跨池 (目录) 超过 9，会议 ID 长度将增长以支持其他会议。
  
会议 ID 的格式如下： 
  
```console
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

若要创建会议目录，请使用 **New-CsConferenceDirectory** cmdlet。 例如，以下命令创建一个标识为 42 的会议目录，该目录托管在 atl-cs-001.litwareinc.com：
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

有关详细信息，请参阅 [New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps)。
