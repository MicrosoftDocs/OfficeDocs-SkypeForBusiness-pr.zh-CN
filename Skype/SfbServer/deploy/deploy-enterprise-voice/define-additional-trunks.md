---
title: 在 Skype for Business Server 的拓扑生成器中定义其他中继
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: '摘要: 了解如何在 Skype for Business Server 的拓扑生成器中定义中介服务器与网关对等之间的其他主干。'
ms.openlocfilehash: eeaddf6b5b150298e7a77b819464b3c0ef653b70
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245608"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a>在 Skype for Business Server 的拓扑生成器中定义其他中继
 
**摘要:** 了解如何在 Skype for Business Server 的拓扑生成器中定义中介服务器与网关对等之间的其他主干。
  
按照以下步骤定义可将对等与中介服务器相关联的其他主干。 对等用户可通过连接到公共交换电话网络 (PSTN) 来为企业语音启用企业语音。 对等方可以是用于 Internet 电话服务提供商 (ITSP) 的 PSTN 网关、IP-PBX 或会话边界控制器 (SBC)。
  
主干是中介服务器和网关之间的逻辑连接。
  
> [!NOTE]
> 本主题假定你已使用至少一个 collocated 或独立中介服务器或池设置 PSTN 网关和根中继, 如在部署文档中的[Skype for Business 服务器的拓扑生成器中定义网关](define-a-gateway.md)中所述。
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>在中介服务器和网关对等之间定义其他主干

1. 启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 "skype for business **server 2015**", 然后单击 "skype for business**服务器2015Topology 生成器**"。
    
2. 在 "Skype for Business 服务器" 下, 您的网站名称、**共享组件**, 右键单击**中继**节点, 然后单击 "**新建主干**"。
   1. 在“定义新的 Trunk”**** 中，指定唯一标识中继的友好名称。 您不得有两个具有相同名称的中继。
    
      > [!NOTE]
      > 如果将传输层安全性 (TLS) 指定为传输类型, 则必须指定 FQDN, 而不是中介服务器对等的 IP 地址。 
  
3. 在“关联的 PSTN 网关”**** 下，选择 PSTN 对等网关以与此中继相关联。
    5. 在 " **PSTN 网关的侦听端口**" 下, 键入对等 (PSTN 网关、IP PBX 或 SBC) 将从要与该主干关联的中介服务器接收 SIP 消息的侦听端口。 对于传输控制协议 (TCP) 来说，默认对等端口为 5066，对于传输层安全性 (TLS)，默认端口为 5067。 默认的 Survivable 分支装置端口为用于 TLS 的 TCP 和5082的5081。
    
4. 在“SIP 传输协议”**** 下，单击对等方使用的传输类型。
    
    > [!NOTE]
    > 出于安全原因, 强烈建议你将对等部署到可以使用 TLS 的中介服务器。 
  
5. 在 "**关联的中介服务器**" 下, 选择要与此对等方的根中继相关联的中介服务器池
    
6. 在 "**关联的中介服务器端口**" 下, 键入中介服务器将从对等方接收 SIP 消息的侦听端口。
    
    > [!NOTE]
    > 利用 Skype for Business 服务器中的多个中继支持, 具有不同主干名称的两个中继不能配置为与**IP/PSTN 网关**相同的**关联中介服务器端口**和侦听端口
  
    > [!NOTE]
    > 通过 Skype for Business 服务器中的多个中继支持, 可以在中介服务器上定义多个 SIP 信号端口, 以便与多个对等方通信。 定义主干时, 关联的**中介服务器端口**号必须位于中介服务器允许的各个协议的侦听端口范围内。 此端口范围在 "Skype for Business 服务器" 和 "中介服务器池" 下定义。 右键单击相关的中介服务器池, 然后选择 "**编辑属性**"。 Specify the port range in the **Listening ports** field.
  
7. 单击“**确定**”。 
    

