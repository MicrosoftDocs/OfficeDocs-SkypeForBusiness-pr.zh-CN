---
title: Skype for Business 2015 中的组内呼叫应答部署过程
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
description: 部署过程和步骤组调用的业务服务器企业语音的 Skype 在装货。
ms.openlocfilehash: 1e87b475e5628aa9df46d025c95d80dc355c6567
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business-2015"></a>Deployment process for Group Call Pickup in Skype for Business 2015
 
部署过程和步骤组调用的业务服务器企业语音的 Skype 在装货。
  
组调用拾取使用户能够应答传入呼叫向其同事，从他们自己的电话。 
  
 自动安装和部署企业语音时，前端服务器或标准版服务器上启用组调用拾取使用的组件。 但是，必须使用以下步骤来配置组调用装货之前可供用户使用。
  
**组调用拾取的部署过程**

|**阶段**|**步骤**|**所需的组和角色**|**部署文档**|
|:-----|:-----|:-----|:-----|
|启用在您的拓扑结构的 SEFAUtil 工具  <br/> |
使用 New CsTrustedApplicationPool cmdlet 来创建新的受信任的应用程序池。 使用 New CsTrustedApplication cmdlet 指定为受信任的应用程序的 SEFAUtil 工具。 运行启用 CsTopology 用于启用拓扑结构。 如果您尚没有它，商业服务器版本的 SEFAUtil 工具 Skype 从该位置上, 下载并安装它您在步骤 1 中创建受信任的应用程序池。 验证 SEFAUtil 正常运行，方法是运行它，以显示部署中用户的呼叫转接设置。 |RTCUniversalServerAdmins  <br/> |[部署企业 2015年的 Skype 的 SEFAUtil 工具](deploy-the-sefautil-tool.md) <br/> [新 CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps)[新 CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplication?view=skype-ps)[启用 CsTopology](https://docs.microsoft.com/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [Lync Server 2013 资源工具包工具的文档](https://technet.microsoft.com/en-us/library/jj945604%28v=ocs.15%29.aspx)。 （为 Skype 业务服务器必须使用当前版本的工具，但本文档从 Lync Server 2013 仍然适用。  <br/> |
|在呼叫寄存通道表中配置呼叫应答号码范围  <br/> |使用**New CSCallParkOrbit** cmdlet 调用公园轨道表中创建调用拾取数字范围和分配类型**GroupPickup**的调用拾取范围。  <br/> 为与现有拨号计划进行无缝集成，号码范围通常配置为虚拟分机块。不支持将外线直拨分机 (DID) 号码分配为呼叫寄存轨道表中的范围号码。<br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[创建或修改组调用装货数量范围在 Skype 的业务 2015](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|将呼叫拾取号码指派给用户，并为用户启用组调用装货  <br/> |/Enablegrouppickup 参数用于在 SEFAUtil 资源工具包工具中启用组调用拾取并分配用户的呼叫拾取号码。  <br/> |-  <br/> |[为用户启用组调用装货和分配业务 2015年的 Skype 在一组数](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|通知用户其分配的呼叫应答号码和任何其他相关号码  <br/> |在您为用户启用组内呼叫应答后，使用电子邮件或一些其他机制来通知用户其呼叫应答组号码。通知用户他们可能希望监控的任何组的呼叫应答组号码。因为用户可以检索其他用户的呼叫（即使他们不在同一组中），所以用户可能需要多个组的呼叫应答组号码。  <br/> |-  <br/> ||
|请验证您的组调用拾取部署  <br/> | 测试发出和取回呼叫以确保配置按预期工作。至少验证以下几点： <br/>  呼叫一个已为其启用了组内呼叫应答的用户，让另一个用户取回此呼叫。后者可在同一个组，也可不在同一个组，或者尚未启用组内呼叫应答。 <br/>  呼叫一个已为其启用了组内呼叫应答的用户但不应答呼叫。 <br/> |-  <br/> ||
   

