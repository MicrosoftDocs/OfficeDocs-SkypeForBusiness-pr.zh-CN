---
title: Skype for Business 中的组呼叫装货的部署过程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
description: Skype for Business Server Enterprise Voice 中的组呼叫装货的部署过程和步骤。
ms.openlocfilehash: f493c3c83f3fa703dd5f62989f4f2e444e83ed5d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289922"
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business"></a>Skype for Business 中的组呼叫装货的部署过程
 
Skype for Business Server Enterprise Voice 中的组呼叫装货的部署过程和步骤。
  
组呼叫允许用户通过其自己的电话应答传入呼叫的同事。 
  
 部署企业语音时, 将在前端服务器或标准版服务器上自动安装和启用组呼叫拾取使用的组件。 但是, 你必须使用以下步骤配置组呼叫挑选, 然后才可供用户使用。
  
**组内呼叫应答部署过程**

|**阶段**|**步骤**|**所需的组和角色**|**部署文档**|
|:-----|:-----|:-----|:-----|
|启用拓扑中的 SEFAUtil 工具|使用 CsTrustedApplicationPool cmdlet 创建新的受信任的应用程序池。 使用 CsTrustedApplication cmdlet 将 SEFAUtil 工具指定为受信任的应用程序。 运行 Enable-CsTopology cmdlet 以启用拓扑。 如果尚未安装, 请从该位置下载 SEFAUtil 工具的 Skype for business 服务器版本, 并将其安装在您在步骤1中创建的受信任的应用程序池中。 验证 SEFAUtil 正常运行，方法是运行它，以显示部署中用户的呼叫转接设置。 |RTCUniversalServerAdmins  <br/> |[在 Skype for Business 中部署 SEFAUtil 工具](deploy-the-sefautil-tool.md) <br/> [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) </br>[New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplication?view=skype-ps)</br>[Enable-CsTopology](https://docs.microsoft.com/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [Skype For Business 服务器2015资源工具包工具文档](../../management-tools/resource-kit-tools.md)。 (对于 Skype for business 服务器, 你必须使用该工具的当前版本, 但来自 Lync Server 2013 的本文档仍然适用。)  <br/> |
|在呼叫寄存通道表中配置呼叫应答号码范围  <br/> |使用 **New-CSCallParkOrbit** cmdlet 在呼叫寄存通道表中创建呼叫应答号码范围，并为呼叫应答范围分配 **GroupPickup** 类型。  <br/> 为与现有拨号计划进行无缝集成，号码范围通常配置为虚拟分机块。不支持将外线直拨分机 (DID) 号码分配为呼叫寄存轨道表中的范围号码。<br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在 Skype for Business 中创建或修改组呼叫装货号码范围](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|为用户分配呼叫装货号码, 并为用户启用组呼叫装货  <br/> |使用 SEFAUtil 资源工具包工具中的/enablegrouppickup 参数启用组呼叫装货, 并为用户分配呼叫装货号码。  <br/> |-  <br/> |[为用户启用组呼叫装货, 并在 Skype for Business 中分配组号码](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|通知用户其分配的呼叫应答号码和任何其他相关号码  <br/> |在您为用户启用组内呼叫应答后，使用电子邮件或一些其他机制来通知用户其呼叫应答组号码。通知用户他们可能希望监控的任何组的呼叫应答组号码。因为用户可以检索其他用户的呼叫（即使他们不在同一组中），所以用户可能需要多个组的呼叫应答组号码。  <br/> |-  <br/> ||
|验证组呼叫装货部署  <br/> | 测试发出和取回呼叫以确保配置按预期工作。至少验证以下几点： <br/>  呼叫一个已为其启用了组内呼叫应答的用户，让另一个用户取回此呼叫。后者可在同一个组，也可不在同一个组，或者尚未启用组内呼叫应答。 <br/>  呼叫一个已为其启用了组内呼叫应答的用户但不应答呼叫。 <br/> |-  <br/> ||
   

