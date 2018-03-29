---
title: Lync Server 2010 中的中介服务器的常规设置扩展器
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 编辑此对话框中的中介服务器的属性。 沿左侧是一套快速链接使您转到常规设置、 下一跃点设置和 PSTN 网关设置的设置。 在每一节包括下列设置：
ms.openlocfilehash: bc5016c9dbeb6b0693444f930c9883b1736258d2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>Lync Server 2010 中的中介服务器的常规设置扩展器
 
编辑此对话框中的中介服务器的属性。 沿左侧是一套快速链接使您转到常规设置、 下一跃点设置和 PSTN 网关设置的设置。 在每一节包括下列设置：
  
 **常规**：
  
- **FQDN**： 编辑中介服务器的完全限定的域名称
    
- **关联**： 选择**关联边池 （对于媒体组件）**复选框，然后选择要用作介质路径外部访问边缘服务器或中介服务器的边缘池。
    
 **下一个跃点**：
  
- **下一跃点选择**： 从列表中选择要用作中介服务器的路径，使用与您的部署进行通信的前端服务器或前端池。
    
 **PSTN 网关**：
  
 **中介服务器 PSTN 网关**：
  
- **侦听端口**： 定义中介服务器将侦听的端口。 您可以定义一个用于**TLS**或传输层安全性或**TCP**，端口或传输控制协议。 可用的 TCP 端口条目，您必须**启用 TCP**端口选择复选框。 
    
    > [!IMPORTANT]
    > 请参阅以确定是否您需要启用并定义端口值 TLS 和 / 或 TCP 公用交换的电话网络 (PSTN) 网关的文档和配置设置。 TLS 是更安全的协议，使用证书来加密中介服务器和 PSTN 网关之间的通信。 不是所有的 PSTN 网关支持 TLS。 
  
- 列出的 SIP 中继和定义并为您的部署配置的网关列表。 如果任何条目存在，任何 SIP 中继或 PSTN 网关配置为您的部署。 定义并在拓扑生成器配置中继和**共享组件**下的网关。
    
## <a name="see-also"></a>另请参阅

#### 

[SIP 中继的概述](http://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)
  
[PSTN 网关部署选项](http://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)

