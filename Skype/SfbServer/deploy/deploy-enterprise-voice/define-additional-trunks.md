---
title: 在 Skype for Business Server 2015 拓扑生成器中定义其他中继
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
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 摘要： 了解如何定义中介服务器之间的网关等其他干线在拓扑生成器在 Skype 业务服务器 2015年。
ms.openlocfilehash: 67d378a794ed6a80b5721f9eb2e9e988ee4db048
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 拓扑生成器中定义其他中继
 
**摘要：**了解如何定义中介服务器之间的网关等其他干线在拓扑生成器在 Skype 业务服务器 2015年。
  
请按照以下步骤定义的可与中介服务器关联对等其他干线。 对等方提供用户启用企业语音连接到公共的交换电话网络 (PSTN)。 对等方可以是用于 Internet 电话服务提供商 (ITSP) 的 PSTN 网关、IP-PBX 或会话边界控制器 (SBC)。
  
主干是中介服务器和网关之间的逻辑连接。
  
> [!NOTE]
> 本主题假定您已经安装的 PSTN 网关和根中继线与至少一个按顺序排列或独立中介服务器或池的所述[定义业务服务器 2015年的 Skype 在拓扑生成器中的网关](define-a-gateway.md)部署文档中。
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>若要定义中介服务器之间的网关等其他干线

1. 起始拓扑生成器中： 单击**开始**，单击**所有程序**、 都单击**业务服务器 2015年的 Skype**，然后都单击**Skype 业务服务器 2015Topology 生成器**。
    
2. 在 Skype 业务服务器**共享组件**，在站点名称，**中继**节点中，用鼠标右键单击，然后单击**新干线**。
    3. 在“定义新的 Trunk”****中，指定唯一标识中继的友好名称。您不得有两个具有相同名称的中继。
    
    > [!NOTE]
    > 如果您指定传输层安全 (TLS) 作为传输类型，则必须指定 FQDN 而不是中介服务器的对等方的 IP 地址。 
  
4. 在“关联的 PSTN 网关”****下，选择 PSTN 对等网关以与此中继相关联。
    5. 在**PSTN 网关的侦听端口**下, 键入侦听端口的对等方 （PSTN 网关，IP PBX 或 SBC） 将接收从中介服务器将与该干线的 SIP 消息。 对于传输控制协议 (TCP) 来说，默认对等端口为 5066，对于传输层安全性 (TLS)，默认端口为 5067。 默认高存活力的分支装置的端口为 TCP 的 5081 和 TLS 的 5082。
    
6. 在“SIP 传输协议”****下，单击对等方使用的传输类型。
    
    > [!NOTE]
    > 出于安全原因，强烈建议将对等部署到可以使用 TLS 中介服务器。 
  
7. 在下，**相关中介服务器**，选择要与此对等机器的根主干的中介服务器池
    
8. 在**关联的中介服务器端口**下, 键入中介服务器将接收来自对等方的 SIP 消息的侦听端口。
    
    > [!NOTE]
    > 多业务服务器在 Skype 的干线支持，不能与其他干线名称的两种中继配置使用同一**相关中介服务器端口**和**IP/PSTN 网关的侦听端口**
  
    > [!NOTE]
    > 多业务服务器在 Skype 的干线支持，多个 SIP 信号端口可以通信的中介服务器上定义多个对等方。 当定义中继，**相关中介服务器的端口**号必须在各自的协议所允许的中介服务器的侦听端口的范围内。 此端口范围定义下 Skype 业务服务器和中介服务器池。 相关的中介服务器池，右键单击并选择**编辑属性**。 在**侦听端口**字段中指定的端口范围。
  
9. 单击“**确定**”。 
    

