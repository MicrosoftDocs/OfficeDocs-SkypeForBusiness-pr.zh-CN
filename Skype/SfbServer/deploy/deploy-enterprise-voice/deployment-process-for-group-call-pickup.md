---
title: 组中的业务的 Skype 调用的分拣的部署过程
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
ms.assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
description: 部署过程和步骤组中的业务 Server 企业语音的 Skype 调用的分拣。
ms.openlocfilehash: 75c669e209c56680b1817ac5fb741dfe497e8689
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21019386"
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business"></a>组中的业务的 Skype 调用的分拣的部署过程
 
部署过程和步骤组中的业务 Server 企业语音的 Skype 调用的分拣。
  
组呼叫分拣使用户可以应答传入呼叫的其同事从其自己的电话。 
  
 自动安装和部署企业语音时，前端服务器或 Standard Edition 服务器上启用组呼叫分拣使用的组件。 但是，您必须使用以下步骤配置组呼叫分拣之前对用户可用。
  
**组内呼叫应答部署过程**

|**阶段**|**步骤**|**所需的组和角色**|**部署文档**|
|:-----|:-----|:-----|:-----|
|启用拓扑的 SEFAUtil 工具|使用 New-cstrustedapplicationpool cmdlet 可创建一个新的受信任应用程序池。 使用 New-cstrustedapplication cmdlet 可以指定为受信任应用程序的 SEFAUtil 工具。 运行 Enable-cstopology cmdlet 来启用拓扑。 如果您没有它，业务服务器版本的 SEFAUtil 工具 Skype 从该位置上, 下载并安装它在步骤 1 中创建的受信任应用程序池。 验证 SEFAUtil 正常运行，方法是运行它，以显示部署中用户的呼叫转接设置。 |RTCUniversalServerAdmins  <br/> |[部署中的业务的 Skype 的 SEFAUtil 工具](deploy-the-sefautil-tool.md) <br/> [新 CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) </br>[新 CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplication?view=skype-ps)</br>[Enable-cstopology](https://docs.microsoft.com/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [Lync Server 2013 资源工具包工具的文档](https://technet.microsoft.com/en-us/library/jj945604%28v=ocs.15%29.aspx)。 （对于 Skype 业务服务器中，您必须使用当前版本的工具，但本文档从 Lync Server 2013 仍然适用）。  <br/> |
|在呼叫寄存通道表中配置呼叫应答号码范围  <br/> |使用**New-cscallparkorbit** cmdlet 在呼叫寄存通道表中创建呼叫分拣号码范围，并分配呼叫分拣范围**GroupPickup**的类型。  <br/> 为与现有拨号计划进行无缝集成，号码范围通常配置为虚拟分机块。不支持将外线直拨分机 (DID) 号码分配为呼叫寄存轨道表中的范围号码。<br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[创建或修改 Skype for Business 中的组呼叫分拣号码范围](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|将呼叫分拣号码分配给用户，并为用户启用组呼叫分拣  <br/> |使用 SEFAUtil 资源工具包工具中 /enablegrouppickup 参数启用组呼叫分拣和分配用户的呼叫分拣号码。  <br/> |-  <br/> |[为用户启用组呼叫分拣和分配 Skype for Business 中的一组数](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|通知用户其分配的呼叫应答号码和任何其他相关号码  <br/> |在您为用户启用组内呼叫应答后，使用电子邮件或一些其他机制来通知用户其呼叫应答组号码。通知用户他们可能希望监控的任何组的呼叫应答组号码。因为用户可以检索其他用户的呼叫（即使他们不在同一组中），所以用户可能需要多个组的呼叫应答组号码。  <br/> |-  <br/> ||
|验证组呼叫分拣部署  <br/> | 测试发出和取回呼叫以确保配置按预期工作。至少验证以下几点： <br/>  呼叫一个已为其启用了组内呼叫应答的用户，让另一个用户取回此呼叫。后者可在同一个组，也可不在同一个组，或者尚未启用组内呼叫应答。 <br/>  呼叫一个已为其启用了组内呼叫应答的用户但不应答呼叫。 <br/> |-  <br/> ||
   

