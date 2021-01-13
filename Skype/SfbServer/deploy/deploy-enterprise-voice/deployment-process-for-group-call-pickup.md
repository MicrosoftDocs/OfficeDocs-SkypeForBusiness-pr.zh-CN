---
title: Skype for Business 中的组内呼叫分拣的部署过程
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
description: Skype for Business Server 企业语音 中的组内呼叫分拣的部署过程和企业语音。
ms.openlocfilehash: 5c89522828e5e5a0dc04ffccb0907c0a2cb8a008
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812342"
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business"></a>Skype for Business 中的组内呼叫分拣的部署过程
 
Skype for Business Server 企业语音 中的组内呼叫分拣的部署过程和企业语音。
  
利用组内呼叫应答，用户可以从自己的电话应答传入同事的呼叫。 
  
 在部署客户端时，会自动在前端服务器或 Standard Edition 服务器上安装并启用组呼叫企业语音。 但是，您必须使用以下步骤配置组内呼叫分拣，然后用户才能使用。
  
**组内呼叫分拣部署过程**

|**阶段**|**步骤**|**所需的组和角色**|**部署文档**|
|:-----|:-----|:-----|:-----|
|在拓扑中启用 SEFAUtil 工具|使用 New-CsTrustedApplicationPool cmdlet 创建新的受信任应用程序池。 使用 New-CsTrustedApplication cmdlet 将 SEFAUtil 工具指定为受信任应用程序。 运行 Enable-CsTopology cmdlet 以启用拓扑。 如果你还没有，请从此位置下载 Skype for Business Server 版本的 SEFAUtil 工具，并安装在你在步骤 1 中创建的受信任应用程序池安装它。 通过运行 SEFAUtil 来显示部署中的用户的呼叫转发设置，验证 SEFAUtil 是否正确运行。 |RTCUniversalServerAdmins  <br/> |[在 Skype for Business 中部署 SEFAUtil 工具](deploy-the-sefautil-tool.md) <br/> [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) </br>[New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplication?view=skype-ps)</br>[Enable-CsTopology](https://docs.microsoft.com/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [Skype for Business Server 2015 资源工具包工具文档](../../management-tools/resource-kit-tools.md)。  (对于 Skype for Business Server，必须使用该工具的当前版本，但 Lync Server 2013 中的本文档仍适用。)   <br/> |
|在呼叫允许通道表中配置呼叫接听号码范围  <br/> |使用 **New-CSCallParkOrbit** cmdlet 在呼叫阻止通道表中创建呼叫接听号码范围，并将呼叫接听范围类型分配为 **GroupPickup。**  <br/> 为了与现有拨号计划无缝集成，号码范围通常配置为虚拟分机块。 不支持在呼叫 (表中将 DID) DID 号码分配为范围号码。  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在 Skype for Business 中创建或修改组内呼叫接听号码范围](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|为用户分配呼叫接听号码，并启用用户的组内呼叫接听  <br/> |使用 SEFAUtil 资源工具包工具中的 /enablegrouppickup 参数启用组内呼叫接听，并分配用户的呼叫接听号码。  <br/> |-  <br/> |[为用户启用组内呼叫接听，在 Skype for Business 中分配组号码](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|通知用户其分配的呼叫接听号码和任何其他关注号码  <br/> |为用户启用组内呼叫接听后，使用电子邮件或其他一些机制通知用户其呼叫接听组号码。 通知用户他们可能想要监视的任何组的呼叫接听组号码。 因为用户可以检索其他用户的呼叫，即使他们不在同一组中，用户可能需要多个组的呼叫接听组号码。  <br/> |-  <br/> ||
|验证组内呼叫接听部署  <br/> | 测试发出和检索呼叫以确保配置正常工作。 至少应验证以下内容： <br/>  呼叫启用了组内呼叫接听的用户，然后让另一个用户取回呼叫。 另一个用户可以位于同一组、不同组中，或者未启用组内呼叫接听。 <br/>  呼叫启用了组内呼叫应答且未应答呼叫的用户。 <br/> |-  <br/> ||
   

