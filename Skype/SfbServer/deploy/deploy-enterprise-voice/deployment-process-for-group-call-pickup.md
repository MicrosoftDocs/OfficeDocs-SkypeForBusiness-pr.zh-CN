---
title: 组中组内呼叫接听的部署Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
description: 组中组呼叫接听的部署过程Skype for Business Server 企业语音。
ms.openlocfilehash: c802f36594704625258da31d18171499315f7e2f1c93020ba71ab42ebb3d97e7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280307"
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business"></a>组中组内呼叫接听的部署Skype for Business
 
组中组呼叫接听的部署过程Skype for Business Server 企业语音。
  
通过组内呼叫应答，用户可以从自己的电话应答传入呼叫。 
  
 部署呼叫分拣时，会在前端服务器或 Standard Edition服务器上自动安装并启用组呼叫企业语音。 但是，必须先使用以下步骤配置组内呼叫接听，然后才能供用户使用。
  
**组内呼叫接听部署过程**

|**阶段**|**步骤**|**所需的组和角色**|**部署文档**|
|:-----|:-----|:-----|:-----|
|在拓扑中启用 SEFAUtil 工具|使用 New-CsTrustedApplicationPool cmdlet 创建新的受信任应用程序池。 使用 New-CsTrustedApplication cmdlet 将 SEFAUtil 工具指定为受信任应用程序。 运行 Enable-CsTopology cmdlet 以启用拓扑。 如果尚未安装该工具，请从此位置下载 Skype for Business Server 版本的 SEFAUtil 工具，应用程序池步骤 1 中创建的受信任工具。 通过运行 SEFAUtil 来显示部署中的用户的呼叫转发设置，验证它是否正确运行。 |RTCUniversalServerAdmins  <br/> |[在部署中部署 SEFAUtil Skype for Business](deploy-the-sefautil-tool.md) <br/> [New-CsTrustedApplicationPool](/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) </br>[New-CsTrustedApplication](/powershell/module/skype/new-cstrustedapplication?view=skype-ps)</br>[Enable-CsTopology](/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [Skype for Business Server 2015 资源工具包工具文档](../../management-tools/resource-kit-tools.md)。  (对于Skype for Business Server必须使用该工具的当前版本，但 Lync Server 2013 中的本文档仍适用。)   <br/> |
|在呼叫管理通道表中配置呼叫接听号码范围  <br/> |使用 **New-CSCallParkOrbit** cmdlet 在呼叫分配通道表中创建呼叫接听号码范围，并将呼叫接听范围类型分配为 **GroupPickup**。  <br/> 为了与现有拨号计划无缝集成，号码范围通常配置为虚拟分机块。 不支持将外线直拨 (DID) 号码分配为呼叫建立通道表中的范围号码。  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Create or modify a Group Call Pickup number range in Skype for Business](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|向用户分配呼叫接听号码，然后为用户启用组内呼叫接听  <br/> |使用 SEFAUtil 资源工具包工具中的 /enablegrouppickup 参数启用组内呼叫接听，并分配用户的呼叫接听号码。  <br/> |-  <br/> |[为用户启用组内呼叫接听，并分配Skype for Business](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|通知用户其分配的呼叫接听号码和任何其他关注号码  <br/> |为用户启用组内呼叫接听后，使用电子邮件或其他一些机制通知用户他们的呼叫接听组号码。 通知用户他们可能想要监视的任何组的呼叫接听组号码。 因为用户可以检索其他用户的呼叫，即使他们并不在同一个组中，用户可能需要多个组的呼叫接听组号码。  <br/> |-  <br/> ||
|验证组内呼叫接听部署  <br/> | 测试发出和检索呼叫以确保配置能够正常工作。 至少验证以下内容： <br/>  呼叫启用了组内呼叫接听的用户，让另一个用户取回该呼叫。 另一个用户可以位于同一组中、位于不同的组中，或者未启用组内呼叫接听。 <br/>  呼叫启用了组内呼叫应答且未应答呼叫的用户。 <br/> |-  <br/> ||
