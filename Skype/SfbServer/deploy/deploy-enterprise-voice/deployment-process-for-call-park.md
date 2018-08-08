---
title: Skype for Business 中的呼叫寄存的部署过程
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
description: 部署过程和步骤中的业务 Server 企业语音的 Skype 的呼叫寄存。
ms.openlocfilehash: 76046b8dbd39ecf9b17675ec8b3c1270a6c70122
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20988309"
---
# <a name="deployment-process-for-call-park-in-skype-for-business"></a>Skype for Business 中的呼叫寄存的部署过程
 
部署过程和步骤中的业务 Server 企业语音的 Skype 的呼叫寄存。
  
呼叫寄存使企业语音用户能够从一部电话将呼叫置于保持状态，然后通过内部号码 （称为呼叫寄存轨道） 从任何电话更高版本中检索呼叫。
  
自动安装和部署企业语音时，前端服务器或 Standard Edition 服务器上启用呼叫寄存使用的组件。 但是，您必须使用以下步骤配置呼叫寄存之前对用户可用。 
  
**呼叫寄存部署过程**

|**阶段**|**步骤**|**所需的组和角色**|**部署文档**|
|:-----|:-----|:-----|:-----|
|在通道表中配置呼叫寄存通道范围  <br/> |使用 Skype 业务 Server Control Panel 或**New-cscallparkorbit** cmdlet 在呼叫寄存通道表中创建通道范围，并将其与关联的应用程序服务承载的呼叫寄存应用程序。 <br/> **注意：** 与现有的拨号计划的无缝集成，通常作为虚拟分机块配置通道范围。 不支持将外线直拨分机 (DID) 号码分配为呼叫寄存通道表中的通道号码。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[创建或修改呼叫寄存通道范围中的业务的 Skype](create-or-modify-a-call-park-orbit-range.md) <br/> |
|配置呼叫寄存设置  <br/> | 使用**Set-cscpsconfiguration** cmdlet 配置呼叫寄存设置。 至少，我们建议您配置用于寄存的呼叫超时后的回退目标配置**OnTimeoutURI**选项。您还可以配置以下设置： <br/>  （可选）**配置 EnableMusicOnHold**以启用或禁用保持音乐。 <br/>  （可选）**MaxCallPickupAttempts**来转接呼叫到回退统一资源标识符 (URI) 之前确定的次数回应答电话寄存的呼叫铃声。 <br/>  （可选）**配置 CallPickupTimeoutThreshold**以确定回拨此前呼叫寄存后到其中应答呼叫的电话之前的时间量。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business 中配置呼叫寄存设置](configure-call-park-settings.md) <br/> |
|（可选）自定义保持音乐  <br/> |使用**Set-cscallparkservicemusiconholdfile** cmdlet 自定义并上载音频文件，如果您不想要使用默认保持音乐保留。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[自定义业务保留 inSkype 的呼叫寄存音乐](customize-call-park-music-on-hold.md) <br/> |
|配置语音策略为用户启用呼叫寄存  <br/> |使用业务 Server Control Panel 或带有**EnableCallPark**选项的**Set-csvoicepolicy** cmdlet Skype 在语音策略中为用户启用呼叫寄存。 <br/> 默认情况下，对所有用户禁用呼叫寄存。  <br/> 如果具有多个语音策略，请确保为每个语音策略（而不只是默认策略）设置 EnableCallPark 属性。  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business 中的用户启用呼叫寄存](enable-call-park-for-users.md) <br/> |
|验证呼叫寄存的规范化规则  <br/> |不能对呼叫寄存通道进行规范化。验证规范化规则是否未包含任何通道范围。如有必要，创建其他规范化规则以阻止对通道进行规范化。  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[验证 Skype for Business 中的呼叫寄存的规范化规则](verify-normalization-rules-for-call-park.md) <br/> |
|验证呼叫寄存部署  <br/> |测试寄存和取回呼叫以确保配置按预期工作。  <br/> |-  <br/> |[（可选）验证呼叫寄存部署中的业务的 Skype](optional-verify-call-park-deployment.md) <br/> |
   

