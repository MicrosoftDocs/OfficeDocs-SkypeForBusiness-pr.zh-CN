---
title: 中介服务器常规设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: be969f1dc3c860ccae3cd12b4e86d4b9e97788f2
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796221"
---
# <a name="mediation-server-general-settings-expander"></a>中介服务器常规设置扩展器
 


## <a name="general-settings"></a>常规设置

中介服务器池或中介服务器的完全限定的域名（FQDN）。 编辑服务器的 FQDN 以更改该值。 必须具有与新值一致的域名系统 (DNS) 主机 (A) 记录。
  
在 "**关联**" 部分中，选择要与中介服务器池或中介服务器相关联的边缘服务器或边缘服务器池。 选择中介服务器的媒体组件将用于外部用户企业语音的边缘。
  
如果当前未定义边缘服务器，并且需要将中介服务器与 Edge 服务器相关联，请单击 "**新建**"，然后在 "定义新的边缘池" 向导中定义新的 edge 服务器或边缘服务器池。
  
## <a name="next-hop-settings"></a>下一跃点设置

通过从下拉列表中选择 "定义的企业版前端池" 或 "标准版前端服务器"，可以指定中介服务器池或中介服务器下一跃点。 Director 或控制器池不是中介服务器池或中介服务器下一跃点的有效选择，不会显示在列表中。 单击 **"确定"** 接受并保存所做的更改。 单击“**取消**”将放弃所做的更改并退出属性页面。
  
## <a name="pstn-gateway-settings"></a>PSTN 网关设置

1. 定义与中介服务器池或中介服务器相关联的 PSTN 网关。 如果您已定义网关，则它们将可与中介服务器相关联。 如果启用中介服务器并置，请在池服务器上为传输层安全性 (TLS) 定义侦听端口范围。 默认情况下，此端口为 5067。 如果选择“**启用 TCP 端口**”，则必须为并置的中介服务器定义传输控制协议 (TCP) 端口。 这是一个可选设置，您应该参考网关要求或 PSTN 要求以确定是否需要此设置。 默认情况下，TCP 端口值为 5068。
    
2. 与并置的中介服务器关联的中继。如果已经定义中继，则可以将它们与中介服务器关联。 
    
3. 如果你有多个与中介服务器关联的中继，则可以通过选择主干，然后单击 "**设为默认值**" 来指定一个默认干线。 若要取消选择网关作为默认网关，请单击“**取消设为默认值**”。 
    

