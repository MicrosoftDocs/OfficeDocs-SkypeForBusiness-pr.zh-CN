---
title: Skype for Business 2015 中的呼叫寄存部署过程
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
description: 部署过程，并在业务服务器企业语音的 Skype 通话公园的步骤。
ms.openlocfilehash: 9d5df92a95e52612c3b0dee005072b10de5c244c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deployment-process-for-call-park-in-skype-for-business-2015"></a>Skype for Business 2015 中的呼叫寄存部署过程
 
部署过程，并在业务服务器企业语音的 Skype 通话公园的步骤。
  
调用公园允许企业语音用户呼叫置于保持从一个电话，然后拨打任何电话从内部编号 （称为调用公园轨道） 以后中检索调用。
  
自动安装和部署企业语音时，前端服务器或标准版服务器上启用呼叫公园使用的组件。 但是，必须使用以下步骤配置呼叫公园之前可供用户使用。 
  
**调用公园部署过程**

|**阶段**|**步骤**|**所需的组和角色**|**部署文档**|
|:-----|:-----|:-----|:-----|
|在通道表中配置呼叫寄存通道范围  <br/> |使用 Skype 业务服务器的控制面板或**新建 CSCallParkOrbit** cmdlet 调用公园轨道表中创建轨道范围并将它们与应用程序服务用于承载公园调用应用程序。 <br/> **注意：**与现有拨号计划的无缝集成，轨道范围通常配置为虚拟扩展一个块。 不支持将外线直拨分机 (DID) 号码分配为呼叫寄存通道表中的通道号码。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[创建或修改业务 2015年的 Skype 通话公园轨道范围](create-or-modify-a-call-park-orbit-range.md) <br/> |
|配置呼叫寄存设置  <br/> | 使用**一组 CsCpsConfiguration** cmdlet 配置呼叫公园设置。 至少，我们建议您配置配置备用目标时停的调用超时使用的**OnTimeoutURI**选项。您还可以配置以下设置： <br/>  （可选）**EnableMusicOnHold** ，来启用或禁用候的音乐。 <br/>  （可选）**MaxCallPickupAttempts**调用回退的统一资源标识符 (URI) 到转发之前确定的次数回应答电话呼叫排队的环。 <br/>  （可选）**CallPickupTimeoutThreshold**以确定调用已被停回应答了电话铃响之前经过的时间量。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[配置中业务 2015年的 Skype 通话公园设置](configure-call-park-settings.md) <br/> |
|（可选）自定义保持音乐  <br/> |使用**一组 CsCallParkServiceMusicOnHoldFile** cmdlet 可以自定义和上载音频文件，如果您不想使用默认的音乐上保留。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[自定义业务 2015年的封存 inSkype 上的调用公园音乐](customize-call-park-music-on-hold.md) <br/> |
|配置语音策略为用户启用呼叫公园  <br/> |使用业务服务器的控制面板或使用**EnableCallPark**选项**设置 CSVoicePolicy** cmdlet Skype 语音策略中的用户启用呼叫公园。 <br/> 默认情况下，对所有用户禁用调用公园。  <br/> 如果具有多个语音策略，请确保为每个语音策略（而不只是默认策略）设置 EnableCallPark 属性。  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[启用呼叫公园中业务 2015年的 Skype 的用户](enable-call-park-for-users.md) <br/> |
|验证呼叫寄存的规范化规则  <br/> |不能对呼叫寄存通道进行规范化。验证规范化规则是否未包含任何通道范围。如有必要，创建其他规范化规则以阻止对通道进行规范化。  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[验证在企业 2015年的 Skype 通话公园的规范化规则](verify-normalization-rules-for-call-park.md) <br/> |
|验证呼叫公园部署  <br/> |测试寄存和取回呼叫以确保配置按预期工作。  <br/> |-  <br/> |[（可选）验证在企业 2015年的 Skype 通话公园部署](optional-verify-call-park-deployment.md) <br/> |
   

