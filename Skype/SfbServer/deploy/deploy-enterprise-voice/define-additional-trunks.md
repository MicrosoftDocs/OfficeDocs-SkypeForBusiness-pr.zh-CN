---
title: 为业务服务器中 Skype 的拓扑生成器中定义其他中继
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 摘要： 了解如何为业务服务器中 Skype 的拓扑生成器中定义其他中继的中介服务器和对等网关之间。
ms.openlocfilehash: 308cd200af2ee046a3e2bcc84815d3755cea932f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892858"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a>为业务服务器中 Skype 的拓扑生成器中定义其他中继
 
**摘要：** 了解如何为业务服务器中 Skype 的拓扑生成器中定义其他中继的中介服务器和对等网关之间。
  
按照以下步骤来定义其他中继到可与中介服务器关联的对等方。 对等方提供连接到公共公用电话交换网 (PSTN) 启用了企业语音的用户。 对等方可以是用于 Internet 电话服务提供商 (ITSP) 的 PSTN 网关、IP-PBX 或会话边界控制器 (SBC)。
  
中继是中介服务器和网关之间的逻辑连接。
  
> [!NOTE]
> 本主题假定您具有安装 PSTN 网关和根 trunk 与至少一个并置或独立中介服务器或池的如部署文档中所述[定义拓扑生成器中的业务服务器 Skype 的网关](define-a-gateway.md)。
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>若要定义其他中继的中介服务器和对等网关之间

1. 启动拓扑生成器： 单击**开始**，单击**所有程序**、 都单击**业务服务器 2015年的 Skype**，，然后都单击**业务 Server 2015Topology 生成器的 Skype**。
    
2. 下 Skype 业务服务器**共享组件**，在您网站的名称，右键单击**Trunk**节点，然后单击**新建 Trunk**。
   1. 在“定义新的 Trunk”**** 中，指定唯一标识中继的友好名称。 您不得有两个具有相同名称的中继。
    
      > [!NOTE]
      > 如果您作为传输类型指定传输层安全性 (TLS)，则必须指定而不是中介服务器的对等的 IP 地址的 FQDN。 
  
3. 在“关联的 PSTN 网关”**** 下，选择 PSTN 对等网关以与此中继相关联。
    5. 在**PSTN 网关的侦听端口**框中，键入侦听端口的对等方 （PSTN 网关、 IP-PBX 或 SBC） 将从要与此中继相关联的中介服务器接收 SIP 消息。 对于传输控制协议 (TCP) 来说，默认对等端口为 5066，对于传输层安全性 (TLS)，默认端口为 5067。 默认 Survivable Branch Appliance 端口是 5081 tcp 和 tls 5082。
    
4. 在“SIP 传输协议”**** 下，单击对等方使用的传输类型。
    
    > [!NOTE]
    > 出于安全考虑，强烈建议您将对等部署到中介服务器可以使用 TLS 的。 
  
5. **关联的中介服务器**下，选择要与此对等方的根中继关联的中介服务器池
    
6. 在**关联的中介服务器端口**框中，键入中介服务器，将从对等方接收 SIP 消息的侦听端口。
    
    > [!NOTE]
    > 使用多个业务服务器中 Skype 的中继支持，具有不同中继名称的两个中继无法配置具有同一**关联的中介服务器端口**和**IP/PSTN 网关的侦听端口**
  
    > [!NOTE]
    > 使用多个业务服务器中 Skype 的中继支持，多个 SIP 信号端口可用于通信的中介服务器上定义与多个对等方。 定义中继时,**关联的中介服务器端口**号必须在各自的协议允许中介服务器的侦听端口的范围内。 此端口范围为业务服务器和中介服务器池定义 Skype 下。 右键单击相关的中介服务器池，然后选择**编辑属性**。 Specify the port range in the **Listening ports** field.
  
7. 单击“**确定**”。 
    

