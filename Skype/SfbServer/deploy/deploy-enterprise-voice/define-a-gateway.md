---
title: 为业务服务器中 Skype 的拓扑生成器中定义网关
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 摘要： 了解如何为业务服务器中 Skype 的拓扑生成器中定义 PSTN 网关。
ms.openlocfilehash: 50c5dca09608f6b0ef9046109e434f3ccbbba0d3
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886794"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a>为业务服务器中 Skype 的拓扑生成器中定义网关
 
**摘要：** 了解如何为业务服务器中 Skype 的拓扑生成器中定义 PSTN 网关。
  
按照以下步骤使用拓扑生成器定义可以与其关联将为用户启用企业语音提供连接到公用电话交换网 (PSTN) 的中介服务器的对等方。 PSTN 网关、 IP PBX 或会话边界控制器 (SBC) 的 Internet 电话服务提供商 (ITSP) 您通过配置 SIP 中继连接，可以是到中介服务器的对等方。
  
### <a name="to-define-a-peer-for-the-mediation-server"></a>定义中介服务器的对等方

1. 启动拓扑生成器： 单击**开始**，单击**所有程序**、 都单击**业务服务器 2015年的 Skype**，，然后都单击**业务 Server 2015Topology 生成器的 Skype**。
    
2. 下 Skype 业务服务器共享组件下，在您网站的名称，右键单击**PSTN 网关**节点中，，然后单击**新建 PSTN 网关**。
3. 在“定义新的 IP/PSTN 网关”**** 中，键入对等方的完全限定的域名 (FQDN) 或 IP 地址，然后单击“下一步”****。
    
    > [!NOTE]
    > 如果您作为传输类型指定传输层安全性 (TLS)，则必须指定而不是中介服务器的对等的 IP 地址的 FQDN。 
  
4. 定义新的 PSTN 网关的 IP 地址的侦听模式（IPv4 或 IPv6），然后单击“下一步”****。

5. 定义 PSTN 网关的 根中继。 中继是中介服务器与由元组唯一标识的网关之间的逻辑连接。
    
    {中介服务器 FQDN，中介服务器侦听端口 （TLS 或 TCP）： 网关 IP 和 FQDN，网关侦听端口}
    
     - 在拓扑生成器中定义 PSTN 网关时，您必须定义根中继才能成功添加到拓扑的 PSTN 网关。
    
     - 在删除关联的 PSTN 网关之前，无法删除根中继。
    
6. 在**IP/PSTN 网关的侦听端口**框中，键入网关、 PBX、 或 SBC 将用于从将与 PSTN 网关的根中继关联的中介服务器的 SIP 消息的侦听端口。 （默认情况下的端口可以是 5066 传输控制协议 (TCP) 和 PSTN 网关，PBX 或 SBC 5067 传输层安全性 (TLS)。 在分支站点为 Survivable Branch Appliance 上的默认端口是 5081 tcp 和 tls 5082。）
    
7. 在“SIP 传输协议”**** 下，单击对等方使用的传输类型，然后单击“确定”****。
    
    > [!NOTE]
    > 出于安全考虑，强烈建议您将对等部署到中介服务器可以使用 TLS 的。 
  
8. **关联的中介服务器**下，选择要与此 PSTN 网关的根中继关联的中介服务器池。
    
9. 在**关联的中介服务器端口**框中，键入中介服务器将用于来自网关的 SIP 消息的侦听端口。
    
    > [!NOTE]
    > 使用多个业务服务器中 Skype 的中继支持，您可以定义多个 SIP 信号中介服务器与多个 PSTN 网关进行通信的端口。 定义中继时,**关联的中介服务器端口**必须在各自的协议允许中介服务器的侦听端口的范围内。 此端口范围为业务服务器和中介池定义 Skype 下。 右键单击感兴趣，中介服务器池，然后选择**编辑属性**。 在**侦听端口**字段中指定的端口范围。
  
10. 确保您定义的对等方正在运行并使用指定的 FQDN 或 IP 地址。然后单击“完成”****。
    
11. 右键单击“**Skype for Business Server**”节点，然后单击“**发布拓扑**”。
    

