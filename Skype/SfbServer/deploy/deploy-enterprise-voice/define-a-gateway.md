---
title: 在 Skype for Business Server 的拓扑生成器中定义网关
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 摘要：了解如何在 Skype for Business Server 的拓扑生成器中定义 PSTN 网关。
ms.openlocfilehash: 41f5f37d7da23848c8a19d11347183d0c0697532
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767725"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a>在 Skype for Business Server 的拓扑生成器中定义网关
 
**摘要：** 了解如何在 Skype for Business Server 的拓扑生成器中定义 PSTN 网关。
  
请按照以下步骤使用拓扑生成器定义对等，你可以将中介服务器与之关联，以便为已启用企业语音的用户提供与公共交换电话网络（PSTN）的连接。 对中介服务器的对等可以是 PSTN 网关、IP PBX，或通过配置 SIP 主干连接的 Internet 电话服务提供商（ITSP）的会话边界控制器（SBC）。
  
### <a name="to-define-a-peer-for-the-mediation-server"></a>定义中介服务器的对等方

1. 启动拓扑生成器：单击 "**开始**"，单击 "**所有程序**"，单击 "skype for business **server 2015**"，然后单击 "skype for business**服务器2015Topology 生成器**"。
    
2. 在 "Skype for Business 服务器" 下，您的网站名称，"共享组件"，右键单击 " **Pstn 网**关" 节点，然后单击 "**新建 pstn 网关**"。
3. 在“定义新的 IP/PSTN 网关”**** 中，键入对等方的完全限定的域名 (FQDN) 或 IP 地址，然后单击“下一步”****。
    
    > [!NOTE]
    > 如果将传输层安全性（TLS）指定为传输类型，则必须指定 FQDN，而不是中介服务器对等的 IP 地址。 
  
4. 定义新的 PSTN 网关的 IP 地址的侦听模式（IPv4 或 IPv6），然后单击“下一步”****。

5. 定义 PSTN 网关的 根中继。 主干是中介服务器和由元组唯一标识的网关之间的逻辑连接。
    
    {中介服务器 FQDN、中介服务器侦听端口（TLS 或 TCP）：网关 IP 和 FQDN，网关侦听端口}
    
     - 在拓扑生成器中定义 PSTN 网关时，必须定义根干线才能成功地将 PSTN 网关添加到拓扑。
    
     - 在删除关联的 PSTN 网关之前，无法删除根中继。
    
6. 在 " **IP/PSTN 网关侦听端口**" 下，键入网关、PBX 或 SBC 将用于来自中介服务器的将与 PSTN 网关根干线关联的 SIP 消息的侦听端口。 （默认情况下，在 PSTN 网关、PBX 或 SBC 上，端口是传输控制协议（TCP）和5067的传输层安全性（TLS）的5066。 在分支站点的 Survivable 分支设备上，默认端口为适用于 TLS 的 TCP 和5082的默认端口5081。）
    
7. 在“SIP 传输协议”**** 下，单击对等方使用的传输类型，然后单击“确定”****。
    
    > [!NOTE]
    > 出于安全原因，强烈建议你将对等部署到可以使用 TLS 的中介服务器。 
  
8. 在 "**关联的中介服务器**" 下，选择要与此 PSTN 网关的根中继相关联的中介服务器池。
    
9. 在 "**关联的中介服务器端口**" 下，键入中介服务器将用于来自网关的 SIP 消息的侦听端口。
    
    > [!NOTE]
    > 通过 Skype for Business Server 中的多个中继支持，你可以在中介服务器上定义多个 SIP 信号端口，以便与多个 PSTN 网关进行通信。 定义主干时，关联的**中介服务器端口**必须位于中介服务器允许的各个协议的侦听端口范围内。 此端口范围在 "Skype for Business 服务器" 和 "中介池" 下定义。 右键单击感兴趣的中介服务器池，然后选择 "**编辑属性**"。 Specify the port range in the **Listening ports** field.
  
10. 确保您定义的对等方正在运行并使用指定的 FQDN 或 IP 地址。 然后单击“完成”****。
    
11. 右键单击“Skype for Business Server”**** 节点，然后单击“发布拓扑”****。
    

