---
title: Skype for Business 中的呼叫寄存的部署过程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
description: Skype for business Server 企业版中的呼叫寄存的部署过程和步骤。
ms.openlocfilehash: 55fc887d77d3b68088bb396763a244ef81ce3a6b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233015"
---
# <a name="deployment-process-for-call-park-in-skype-for-business"></a>Skype for Business 中的呼叫寄存的部署过程
 
Skype for business Server 企业版中的呼叫寄存的部署过程和步骤。
  
"呼叫驻留" 使企业语音用户可以通过一条电话将呼叫置于保持状态, 然后通过从任何电话拨入内部号码 (称为呼叫公园轨道), 稍后检索呼叫。
  
当部署企业语音时, 将在前端服务器或标准版服务器上自动安装和启用调用寄存使用的组件。 但是, 你必须使用以下步骤配置呼叫寄存, 然后才可供用户使用。 
  
**呼叫寄存部署过程**

|**阶段**|**步骤**|**所需的组和角色**|**部署文档**|
|:-----|:-----|:-----|:-----|
|在通道表中配置呼叫寄存通道范围  <br/> |使用 Skype for Business 服务器控制面板或**CSCallParkOrbit** cmdlet 在 "呼叫公园轨道" 表中创建轨道范围, 并将它们与托管呼叫寄存应用程序的应用程序服务相关联。 <br/> **注意:** 对于与现有拨号计划的无缝集成, 轨道范围通常配置为虚拟扩展块。 不支持将外线直拨分机 (DID) 号码分配为呼叫寄存通道表中的通道号码。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在 Skype for Business 中创建或修改呼叫寄存的轨道范围](create-or-modify-a-call-park-orbit-range.md) <br/> |
|配置呼叫寄存设置  <br/> | 使用**CsCpsConfiguration** Cmdlet 配置呼叫寄存设置。 我们建议你将**OnTimeoutURI**选项配置为配置备用目标以在停止通话超时时使用。您还可以配置以下设置: <br/>  （可选）配置 **EnableMusicOnHold** 以启用或禁用保持音乐。 <br/>  （可选）配置 **MaxCallPickupAttempts** 以确定将寄存呼叫转接到回退统一资源标识符 (URI) 之前该呼叫回拨应答电话的次数。 <br/>  （可选）配置 **CallPickupTimeoutThreshold** 以确定呼叫寄存后到回拨应答该呼叫的电话之前等待的时间。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在 Skype for Business 中配置呼叫寄存设置](configure-call-park-settings.md) <br/> |
|（可选）自定义保持音乐  <br/> |使用 **Set-CsCallParkServiceMusicOnHoldFile** cmdlet 自定义并上载音频文件（如果不使用默认的保持音乐）。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[自定义呼叫驻留 inSkype for Business 的暂停音乐](customize-call-park-music-on-hold.md) <br/> |
|配置语音策略以为用户启用呼叫寄存  <br/> |使用 Skype for Business Server 控制面板或带有**EnableCallPark**选项的**CSVoicePolicy** cmdlet 为语音策略中的用户启用呼叫寄存。 <br/> 默认情况下, 将对所有用户禁用 "呼叫寄存"。  <br/> 如果具有多个语音策略，请确保为每个语音策略（而不只是默认策略）设置 EnableCallPark 属性。  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[为 Skype for Business 中的用户启用呼叫寄存](enable-call-park-for-users.md) <br/> |
|验证呼叫寄存的规范化规则  <br/> |不能对呼叫寄存通道进行规范化。验证规范化规则是否未包含任何通道范围。如有必要，创建其他规范化规则以阻止对通道进行规范化。  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在 Skype for Business 中验证呼叫寄存的规范化规则](verify-normalization-rules-for-call-park.md) <br/> |
|验证您的电话寄存部署  <br/> |测试寄存和取回呼叫以确保配置按预期工作。  <br/> |-  <br/> |[可选在 Skype for Business 中验证呼叫寄存部署](optional-verify-call-park-deployment.md) <br/> |
   

