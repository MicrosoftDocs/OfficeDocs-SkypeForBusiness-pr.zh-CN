---
title: 呼叫管理中的呼叫Skype for Business
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
description: 部署过程中呼叫的呼叫Skype for Business Server 企业语音。
ms.openlocfilehash: bfc6a2455ba010f05083872ee8c394244ef4827b
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393384"
---
# <a name="deployment-process-for-call-park-in-skype-for-business"></a>呼叫管理中的呼叫Skype for Business
 
部署过程中呼叫的呼叫Skype for Business Server 企业语音。
  
通过呼叫企业语音用户可以从一部电话将呼叫置于保持状态，稍后通过从任何电话拨打内部号码 (称为呼叫) 取回呼叫。
  
在前端服务器或前端服务器上部署呼叫Standard Edition会自动安装并启用呼叫企业语音。 但是，必须先使用以下步骤来配置呼叫呼叫管理，然后才能供用户使用。 
  
**呼叫寄存部署过程**

|**阶段**|**步骤**|**所需的组和角色**|**部署文档**|
|:-----|:-----|:-----|:-----|
|在通道表中配置呼叫寄存通道范围  <br/> |使用 Skype for Business Server 控制面板或 **New-CSCallParkOrbit** cmdlet 在呼叫托管通道表中创建通道范围，并将其与承载呼叫托管应用程序的应用程序服务关联。 <br/> **注意：** 为了与现有拨号计划无缝集成，通道范围通常配置为虚拟分机块。 不支持将外线直拨分机 (DID) 号码分配为呼叫寄存通道表中的通道号码。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Create or modify a Call Park orbit range in Skype for Business](create-or-modify-a-call-park-orbit-range.md) <br/> |
|配置呼叫寄存设置  <br/> | 使用 **Set-CsCpsConfiguration** cmdlet 配置呼叫库设置。 建议至少配置 **OnTimeoutURI** 选项，以配置在已呼叫退出时使用的回退目标。还可以配置以下设置： <br/>  （可选）配置 **EnableMusicOnHold** 以启用或禁用保持音乐。 <br/>  （可选）配置 **MaxCallPickupAttempts** 以确定将寄存呼叫转接到回退统一资源标识符 (URI) 之前该呼叫回拨应答电话的次数。 <br/>  （可选）配置 **CallPickupTimeoutThreshold** 以确定呼叫寄存后到回拨应答该呼叫的电话之前等待的时间。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在呼叫管理中配置呼叫Skype for Business](configure-call-park-settings.md) <br/> |
|（可选）自定义保持音乐  <br/> |使用 **Set-CsCallParkServiceMusicOnHoldFile** cmdlet 自定义并上载音频文件（如果不使用默认的保持音乐）。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在Skype for Business 中自定义呼叫等待音乐](customize-call-park-music-on-hold.md) <br/> |
|配置语音策略以启用用户的呼叫等待  <br/> |使用Skype for Business Server控制面板或 **Set-CSVoicePolicy** cmdlet 和 **EnableCallPark** 选项为语音策略中的用户启用呼叫呼叫等待。 <br/> 默认情况下，将禁用所有用户的呼叫等待。  <br/> 如果具有多个语音策略，请确保为每个语音策略（而不只是默认策略）设置 EnableCallPark 属性。  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[为呼叫服务中的用户启用Skype for Business](enable-call-park-for-users.md) <br/> |
|验证呼叫寄存的规范化规则  <br/> |不能对呼叫寄存通道进行规范化。验证规范化规则是否未包含任何通道范围。如有必要，创建其他规范化规则以阻止对通道进行规范化。  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在呼叫管理中验证呼叫Skype for Business](verify-normalization-rules-for-call-park.md) <br/> |
|验证呼叫管理部署  <br/> |测试停叫和取回呼叫，以确保配置能够正常工作。  <br/> |-  <br/> |[ (中) 验证呼叫Skype for Business](optional-verify-call-park-deployment.md) <br/> |
   

