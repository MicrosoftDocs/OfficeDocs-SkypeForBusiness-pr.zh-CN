---
title: 在 Skype for Business Server 2015 拓扑生成器中定义网关
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 摘要： 了解如何在拓扑生成器在 Skype 的 PSTN 网关定义为业务服务器 2015年。
ms.openlocfilehash: 7fa7f95fd04cf491dad32b0ab6cc050c5ebb0b0e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 拓扑生成器中定义网关
 
**摘要：**了解如何定义业务服务器 2015年在拓扑生成器在 Skype 的 PSTN 网关。
  
请按照以下步骤使用拓扑生成器来定义可以将中介服务器的用户启用了企业语音提供公用交换的电话网 (PSTN) 的连接关联的对等。 PSTN 网关，IP PBX 或会话边框控制器 (SBC) 的互联网电话服务提供程序 (ITSP) 所通过配置 SIP 中继连接可以是到中介服务器的对等方。
  
### <a name="to-define-a-peer-for-the-mediation-server"></a>定义中介服务器的对等方

1. 起始拓扑生成器中： 单击**开始**，单击**所有程序**、 都单击**业务服务器 2015年的 Skype**，然后都单击**Skype 业务服务器 2015Topology 生成器**。
    
2. 在 Skype 业务服务器共享组件，在站点名称， **PSTN 网关**节点中，用鼠标右键单击，然后单击**新的 PSTN 网关**。
3. 在“定义新的 IP/PSTN 网关”****中，键入对等方的完全限定的域名 (FQDN) 或 IP 地址，然后单击“下一步”****。
    
    > [!NOTE]
    > 如果您指定传输层安全 (TLS) 作为传输类型，则必须指定 FQDN 而不是中介服务器的对等方的 IP 地址。 
  
4. 定义新的 PSTN 网关的 IP 地址的侦听模式（IPv4 或 IPv6），然后单击“下一步”****。

5. 定义的 PSTN 网关根主干。 主干是由元组唯一标识一个网关中介服务器之间的逻辑连接。
    
    {中介服务器 FQDN，中介服务器侦听端口 （TLS 或 TCP）： 网关 IP 和 FQDN，网关监听端口}
    
     - 在 PSTN 网关定义在拓扑生成器时，您必须定义已成功添加到您的拓扑的 PSTN 网关根主干。
    
     - 在删除关联的 PSTN 网关之前，无法删除根中继。
    
6. 在**IP/PSTN 网关的侦听端口**下, 键入网关、 PBX、 或 SBC 将用于将与根主干的 PSTN 网关关联的中介服务器的 SIP 消息的侦听端口。 （默认情况下，端口可以是 5066 传输控制协议 (TCP) 和 PSTN 网关，PBX 或 SBC 5067 传输层安全 (TLS)。 高存活力的分支装置在分支站点，默认端口为 TCP 的 5081 和 TLS 的 5082。）
    
7. 在“SIP 传输协议”****下，单击对等方使用的传输类型，然后单击“确定”****。
    
    > [!NOTE]
    > 出于安全原因，强烈建议将对等部署到可以使用 TLS 中介服务器。 
  
8. 下**相关中介服务器**，选择要与此 PSTN 网关根主干的中介服务器池。
    
9. 在**关联的中介服务器端口**下, 键入 SIP 消息从网关将使用中介服务器的侦听端口。
    
    > [!NOTE]
    > 使用中的多中继支持 Skype 业务服务器，您可以定义多个 SIP 信号中介服务器与多个 PSTN 网关的通信端口。 当定义中继，**相关中介服务器端口**必须各自的协议所允许的中介服务器的侦听端口的范围内。 此端口范围定义下 Skype 业务服务器和中介池。 中介服务器池感兴趣，用鼠标右键单击并选择**编辑属性**。 在**侦听端口**字段中指定的端口范围。
  
10. 确保您定义的对等方正在运行并使用指定的 FQDN 或 IP 地址。然后单击“完成”****。
    
11. 右键单击“**Skype for Business Server**”节点，然后单击“**发布拓扑**”。
    

