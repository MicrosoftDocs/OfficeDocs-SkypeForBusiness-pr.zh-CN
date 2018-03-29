---
title: 中介服务器常规设置扩展器
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 4/14/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: 51e00323c3c0d5df3915b2652b273f1fa189143e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="mediation-server-general-settings-expander"></a>中介服务器常规设置扩展器
 
## 

### <a name="general-settings"></a>常规设置

中介服务器池或中介服务器的完全合格的域名称 (FQDN)。 编辑服务器的 FQDN 以更改该值。 必须具有与新值一致的域名系统 (DNS) 主机 (A) 记录。
  
在**关联**部分中，选择要与中介服务器池或中介服务器关联的边缘服务器或边缘服务器池。 选择中介服务器的媒体组件将用于外部用户企业语音的边缘。
  
如果您确实没有边缘服务器将当前定义和需要中介服务器相关联的边缘服务器，单击**新建**并定义新边池向导中定义的新的边缘服务器或边缘服务器池。
  
### <a name="next-hop-settings"></a>下一跃点设置

通过从下拉列表中选择定义的企业版前端池或标准版前端服务器中指定的中介服务器池或中介服务器的下一个跃点。 总监或总监池不是一种有效选择，中介服务器池或中介服务器下一个跃点，并不会出现在列表中。 单击**确定**以接受并保存您的更改。 单击“**取消**”将放弃所做的更改并退出属性页面。
  
### <a name="pstn-gateway-settings"></a>PSTN 网关设置

1. 定义与中介服务器池或中介服务器相关联的 PSTN 网关。 如果您已经定义了网关，它们可中介服务器相关联。 如果启用中介服务器并置，请在池服务器上为传输层安全性 (TLS) 定义侦听端口范围。 默认情况下，此端口为 5067。 如果选择“**启用 TCP 端口**”，则必须为并置的中介服务器定义传输控制协议 (TCP) 端口。 这是一个可选设置，您应该参考网关要求或 PSTN 要求以确定是否需要此设置。 默认情况下，TCP 端口值为 5068。
    
2. 与并置的中介服务器关联的中继。如果已经定义中继，则可以将它们与中介服务器关联。 
    
3. 如果您有多个干线与中介服务器相关联，您可以指定默认中继主干中选择，然后单击**设为默认值**。 若要取消选择网关作为默认网关，请单击“**取消设为默认值**”。 
    

