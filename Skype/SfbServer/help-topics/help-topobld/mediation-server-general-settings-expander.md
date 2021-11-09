---
title: 中介服务器常规设置扩展器
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 4/14/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: de4d09db10610bee5f498b07cca6a052b6a79a38
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852096"
---
# <a name="mediation-server-general-settings-expander"></a>中介服务器常规设置扩展器
 


## <a name="general-settings"></a>常规设置

中介服务器池或中介服务器的完全限定域名 (FQDN)。编辑服务器的 FQDN 以更改该值。必须具有与新值一致的域名系统 (DNS) 主机 (A) 记录。
  
在 **“关联”** 部分中，选择要与中介服务器池或中介服务器关联的边缘服务器或边缘服务器池。 选择中介服务器的媒体组件用于外部用户配置的边缘企业语音。
  
如果当前未定义边缘服务器，而需要将中介服务器与边缘服务器关联，请单击 **“新建”**，然后通过“定义新的边缘池”向导定义新的边缘服务器或边缘服务器池。
  
## <a name="next-hop-settings"></a>下一跃点设置

通过从下拉列表中选择定义的 Enterprise Edition 前端池或 Standard Edition 前端服务器，可指定中介服务器池或中介服务器的下一个跃点。 控制器或控制器池不是中介服务器池或中介服务器下一个跃点的有效选择，不会显示在列表中。 单击 **"确定** "接受并保存更改。 单击“取消”将放弃所做的更改并退出属性页面。
  
## <a name="pstn-gateway-settings"></a>PSTN 网关设置

1. 定义与中介服务器池或中介服务器关联的 PSTN 网关。如果已定义了网关，它们将可用于与中介服务器关联。如果启用中介服务器并置，请在池服务器上为传输层安全性 (TLS) 定义侦听端口范围。默认情况下，该端口为 5067。如果选择“启用 TCP 端口”，则必须为并置的中介服务器定义一个传输控制协议 (TCP) 端口。这是一个可选设置，您应该参考网关要求或 PSTN 要求以确定是否需要此设置。默认情况下，TCP 端口值为 5068。
    
2. 与并置的中介服务器关联的中继。如果已定义了中继，则它们可用于与中介服务器关联。 
    
3. 如果将多个中继与中介服务器关联，则可以通过选择某个中继然后单击“设为默认值”来指定默认中继。若要将某个网关取消选为默认网关，请单击“取消设为默认值”。 
    

