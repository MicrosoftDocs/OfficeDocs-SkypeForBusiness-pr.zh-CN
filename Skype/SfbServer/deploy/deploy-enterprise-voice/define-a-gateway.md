---
title: 在拓扑生成器中定义Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 摘要：了解如何在拓扑生成器中定义 PSTN Skype for Business Server。
ms.openlocfilehash: c3ea9b02f39b3ef93c7c725735599a3940f33641
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60753603"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a>在拓扑生成器中定义Skype for Business Server
 
**摘要：** 了解如何在拓扑生成器中定义 PSTN Skype for Business Server。
  
按照以下步骤使用拓扑生成器定义一个对等方，可以将中介服务器与该对等方关联，为启用了 企业语音 的用户提供与公用电话交换网 (PSTN) 的连接。 中介服务器的对等方可以是通过配置 SIP 中继连接到的 Internet 电话服务提供商 (ITSP) 的 PSTN 网关、IP-PBX 或会话边界控制器 (SBC) 。
  
### <a name="to-define-a-peer-for-the-mediation-server"></a>定义中介服务器的对等方

1. 启动拓扑生成器：单击"开始"，单击"所有程序"，Skype for Business Server **2015"，** 然后单击"Skype for Business Server **2015Topology Builder"。**
    
2. 在Skype for Business Server名称"共享组件"下，右键单击 **"PSTN 网关**"节点，然后单击"新建 **PSTN 网关"。**
3. 在“定义新的 IP/PSTN 网关”中，键入对等方的完全限定域名 (FQDN) 或 IP 地址，然后单击“下一步”。
    
    > [!NOTE]
    > 如果将传输层安全性 (TLS) 指定为传输类型，则必须指定 FQDN，而不是中介服务器的对等方 IP 地址。 
  
4. 定义新的 PSTN 网关的 IP 地址的侦听模式（IPv4 或 IPv6），然后单击“下一步”。

5. 定义 PSTN 网关的根中继。 中继是中介服务器和元组唯一标识的网关之间的逻辑连接。
    
    {Mediation Server FQDN， Mediation Server listening port (TLS or TCP) ： gateway IP and FQDN， gateway listening port}
    
     - 在拓扑生成器中定义 PSTN 网关时，必须定义根中继以将 PSTN 网关成功添加到拓扑。
    
     - 在删除关联的 PSTN 网关之前，无法删除根中继。
    
6. 在 **"IP/PSTN** 网关的侦听端口"下，键入网关、PBX 或 SBC 用于来自中介服务器的 SIP 消息的侦听端口，这些 SIP 消息将与该 PSTN 网关的根中继相关联。  (默认情况下，PSTN 网关、PBX 或 SBC 上的传输控制协议 (TCP) 的端口为 5066，传输层安全性 (TLS) 端口为 5067。 在分支站点的 Survivable Branch Appliance 上，TCP 的默认端口为 5081，TLS.) 
    
7. 在“SIP 传输协议”下，单击对等方使用的传输类型，然后单击“确定”。
    
    > [!NOTE]
    > 出于安全考虑，强烈建议您部署可使用 TLS 的中介服务器的对等方。 
  
8. 在 **"关联的中介服务器"** 下，选择要与此 PSTN 网关的根中继关联的中介服务器池。
    
9. 在 **"关联的中介服务器端口**"下，键入中介服务器用于网关的 SIP 消息的侦听端口。
    
    > [!NOTE]
    > 通过支持多个中继Skype for Business Server，可以在中介服务器上定义多个 SIP 信号端口，以与多个 PSTN 网关通信。 定义中继时，关联的中介 **服务器** 端口必须位于中介服务器允许的各自协议的侦听端口范围内。 此端口范围在"Skype for Business Server池"下定义。 右键单击感兴趣的中介服务器池，然后选择"编辑 **属性"。** 在“侦听端口”字段中指定端口范围。
  
10. 确保定义的对等方正在运行，并且使用了指定的 FQDN 或 IP 地址。 然后单击“完成”。
    
11. 右键单击 **"Skype for Business Server"** 节点，然后单击"发布 **拓扑"。**
    

