---
title: 在 Skype for Business Server 的拓扑生成器中定义其他中继
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 摘要：了解如何在 Skype for Business Server 的拓扑生成器中定义中介服务器和网关对等方之间的其他中继。
ms.openlocfilehash: 3aab744761420ab631f17e6b56391f1fab120ccf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836992"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a>在 Skype for Business Server 的拓扑生成器中定义其他中继
 
**摘要：** 了解如何在 Skype for Business Server 的拓扑生成器中定义中介服务器和对等网关之间的附加中继。
  
按照以下步骤定义可以将对等方与中介服务器关联的其他中继。 对等为启用呼叫企业语音 PSTN (公用电话交换网) 。 对等方可以是用于 Internet 电话服务提供商电话服务提供商 (ITSP) 的 PSTN 网关、IP-PBX 或会话边界控制器 (SBC)。
  
中继是中介服务器和网关之间的逻辑连接。
  
> [!NOTE]
> 本主题假定你已设置 PSTN 网关和根中继，其中至少具有一个并站或独立中介服务器或池，如部署文档中的"在 [Skype for Business Server](define-a-gateway.md) 的拓扑生成器中定义网关"中所述。
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>在中介服务器和对等网关之间定义其他中继

1. 启动拓扑生成器 **：单击"** 开始"，**单击"** 所有程序"，再单击 **"Skype for Business Server 2015"，** 然后单击 **"Skype for Business Server 2015Topology Builder"。**
    
2. 在 Skype for Business Server 下，站点名称 **、共享组件**、右键单击 **Trunk 节点**，然后单击 **"新建中继"。**
   1. 在“定义新的 Trunk”中，指定唯一标识中继的友好名称。 您不得有两个具有相同名称的中继。
    
      > [!NOTE]
      > 如果指定传输层安全性 (TLS) 作为传输类型，则必须指定 FQDN，而不是中介服务器的对等方 IP 地址。 
  
3. 在“关联的 PSTN 网关”下，选择 PSTN 对等网关以与此中继相关联。
    5. 在 **PSTN** 网关的"侦听端口"下，键入对等 (PSTN 网关、IP-PBX 或 SBC) 将接收来自中介服务器（将与此中继关联的 SIP 消息）的侦听端口。 对于传输控制协议 (TCP) 来说，默认对等端口为 5066，对于传输层安全性 (TLS)，默认端口为 5067。 默认的 Survivable Branch Appliance 端口为 5081（TCP）和 5082（对于 TLS）。
    
4. 在“SIP 传输协议”下，单击对等方使用的传输类型。
    
    > [!NOTE]
    > 出于安全考虑，强烈建议您部署可使用 TLS 的对等方中介服务器。 
  
5. 在 **"关联的中介服务器"下**，选择要与此对等方根中继关联的中介服务器池
    
6. 在 **"关联的中介服务器端口**"下，键入中介服务器将接收来自对等方 SIP 消息的侦听端口。
    
    > [!NOTE]
    > 在 Skype for Business Server 中具有多个中继支持时，不能使用相同的关联中介服务器端口和 **IP/PSTN** 网关的侦听端口配置两个中继名称不同的中继
  
    > [!NOTE]
    > 通过 Skype for Business Server 中的多个中继支持，可以在中介服务器上定义多个 SIP 信号端口，以与多个对等方通信。 定义中继时，关联的中介 **服务器端口** 号必须位于中介服务器允许的各自协议的侦听端口范围内。 此端口范围在 Skype for Business Server 和中介服务器池下定义。 右键单击相关的中介服务器池，然后选择"**编辑属性"。** 在“侦听端口”字段中指定端口范围。
  
7. 单击“确定”。 
    

