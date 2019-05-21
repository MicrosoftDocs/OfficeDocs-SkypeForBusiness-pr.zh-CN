---
title: 在 Skype for Business Server 中配置无 PIN 会议加入
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: '摘要: 了解如何在 Skype for Business 服务器中配置 PIN 更少的会议加入选项。'
ms.openlocfilehash: ecd1d2bf184dd6b9e1ff78e16c2ca1eb8da73ef9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280381"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>在 Skype for Business Server 中配置无 PIN 会议加入
 
**摘要:** 了解如何在 Skype for Business 服务器中配置 PIN 更少的会议加入选项。
  
当拨入呼叫者尝试加入会议时, 会议自动助理 (CAA) 服务会将呼叫者置于不同于会议厅 & # x2014 的保留笔中。如果演示者尚未在通话中, 并且拨入呼叫方没有输入引线引脚。 无 PIN 会议加入选项使拨入呼叫方无需输入主持人 PIN 就能加入会议，即使他们是第一个从加入通话的人也是如此。 
  
配置此功能时，请记住以下几点：
  
- 仅适用于秘密会议。
    
- 允许 PSTN 呼叫方保持在不包含经过身份验证的用户的私密会议中。
    
- 在设置发生更改后，它适用于所有现有和新的私密会议。
    
- 既可以在组织者网站也可以在全局级别启用。
    
- 可以为以下各项设置能够绕过大厅的人员的选项： 
    
  - **我的组织中的任何人和呼叫者都可以直接参加**
    
  - **任何人（没有限制）和呼叫者可以直接参加**（这是默认设置。）
    
- 当配置为启用无 PIN 加入时，CAA 服务仍会提示提供主持人 PIN。 无论是否输入 PIN，用户都可以加入会议。 但是, 保持引线引脚的功能允许拨入呼叫者作为领导者进行身份验证, 如有必要, 请管理会议。
    
## <a name="configure-pin-less-meeting-join"></a>配置无 PIN 会议加入

若要为你的用户启用 PIN 更少加入会议, 请将[CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) Cmdlet 与 AllowAnonymousPstnActivation 参数配合使用, 如下所示:
  
```
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

例如，以下命令可为站点 Redmond 启用无 PIN 会议加入：
  
```
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

为安全起见，当启用无 PIN 会议加入时，你可能需要通过确保 ConferencingPolicy 设置如下来限制匿名用户拨出：
  
```
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

有关详细信息, 请参阅[设置 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
  

