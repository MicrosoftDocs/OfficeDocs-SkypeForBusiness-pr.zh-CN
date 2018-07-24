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
ms.openlocfilehash: ecb8a924bc72dd8220ab5d40481418cbec78737a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20969850"
---
# <a name="mediation-server-general-settings-expander"></a>中介服务器常规设置扩展器
 


## <a name="general-settings"></a>常规设置

完全限定的域名 (FQDN) 的中介服务器池或中介服务器。 编辑服务器的 FQDN 以更改该值。 必须具有与新值一致的域名系统 (DNS) 主机 (A) 记录。
  
在**关联**部分中，您可以选择边缘服务器或边缘服务器池与中介服务器池或中介服务器相关联。 选择中介服务器的媒体组件将用于外部用户企业语音的边缘。
  
如果您没有边缘服务器将当前定义，并且需要将中介服务器与边缘服务器相关联，单击**新建**并定义新建边缘池向导中定义的新的边缘服务器或边缘服务器池。
  
## <a name="next-hop-settings"></a>下一跃点设置

从下拉列表中选择的定义的 Enterprise Edition 前端池或 Standard Edition 前端服务器指定中介服务器池或中介服务器下一个跃点。 控制器或控制器池不是有效的选定内容的中介服务器池或中介服务器下一个跃点，并将不会出现在列表中。 单击**确定**接受并保存所做的更改。 单击“**取消**”将放弃所做的更改并退出属性页面。
  
## <a name="pstn-gateway-settings"></a>PSTN 网关设置

1. 定义 PSTN 网关与中介服务器池或中介服务器相关联。 如果已定义网关，它们将可用于与中介服务器相关联。 如果启用中介服务器并置，请在池服务器上为传输层安全性 (TLS) 定义侦听端口范围。 默认情况下，此端口为 5067。 如果选择“**启用 TCP 端口**”，则必须为并置的中介服务器定义传输控制协议 (TCP) 端口。 这是一个可选设置，您应该参考网关要求或 PSTN 要求以确定是否需要此设置。 默认情况下，TCP 端口值为 5068。
    
2. 与并置的中介服务器关联的中继。如果已经定义中继，则可以将它们与中介服务器关联。 
    
3. 如果您有多个与中介服务器关联的中继，您可以通过选择中继，然后单击**设为默认值**来指定默认中继。 若要取消选择网关作为默认网关，请单击“**取消设为默认值**”。 
    

