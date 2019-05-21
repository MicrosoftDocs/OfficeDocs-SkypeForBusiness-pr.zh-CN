---
title: 在 Skype for Business Server 的拓扑生成器中部署中介服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: '摘要: 了解如何在 Skype for Business Server 的拓扑生成器中定义和部署中介服务器。'
ms.openlocfilehash: 61b90bb874d96579d975a1672238a7427350a5dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284646"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a>在 Skype for Business Server 的拓扑生成器中部署中介服务器
 
**摘要:** 了解如何在 Skype for Business Server 的拓扑生成器中定义和部署中介服务器。
  
企业语音工作负荷、电话拨入式会议和高级企业语音应用程序 (响应组应用程序、呼叫驻留应用程序、呼叫许可控制 (CAC) 等) 均可在前端池中使用。 中介服务器的功能内置于前端服务器中。 不需要单独的独立中介服务器。 
  
唯一的例外是将 SIP 中继配置为连接到 Internet 电话服务提供商的会话边界控制器的情况。 要将企业语音基础结构连接到 SIP 中继提供商, 必须部署单独的中介服务器。
  
Skype for Business 服务器 (中介服务器 collocated 在前端池或独立中介服务器上) 与网关之间的连接定义为称为主干的逻辑关联。 本部分中的主题介绍如何定义主干以及如何部署独立中介服务器 (如果你连接到 SIP 主干)。
  
## <a name="define-a-mediation-server-in-topology-builder"></a>在拓扑生成器中定义中介服务器

你可以在前端池上添加中介服务器作为 collocated 角色, 或者定义单独的独立中介服务器池。
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>将中介服务器添加到前端池

1. 启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 "skype for business **server 2015**", 然后单击 "skype for business**服务器2015Topology 生成器**"。
    
2. 在拓扑生成器的控制台树中, 展开要为其定义前端池的网站的名称。
    
3. 在控制台树中, 右键单击所需的前端池类型, 然后单击 "**新建前端池"。**
    
4. 在“定义新的前端池”**** 向导中导航，直到到达“选择并置服务器角色”**** 页。
    
5. 在 "**选择 collocated 服务器角色**" 中, 选中 " **Collocate 中介服务器**" 选项。
    
    > [!NOTE]
    > 如果所选的前端池的类型为 "企业版", 则将在该前端池的所有前端服务器上安装中介服务器组件。 
  
    > [!NOTE]
    > 中介服务器使用的**下一个跃点池**将是中介服务器 Collocated 的前端池。
  
    > [!NOTE]
    > 中介服务器使用的**edge 池**将是与中介服务器 Collocated 的前端池关联的同一 edge 池。
  
6. 单击 "**设为默认值**" 使用此前端池路由到 PSTN 的呼叫。
    
7. 完成将一个或多个对等方关联到前端池后, 单击 "**完成**"。
    
    > [!NOTE]
    > 在你继续执行企业语音部署过程中的下一步骤之前, 请确保使用你指定的 Fqdn 将中介服务器池 (即具有中介服务器组件 collocated 的前端池) 使用。 
  
8. 右键单击**Skype for Business Server 2015**节点, 然后单击 "**发布拓扑**"。
    
### <a name="to-add-a-standalone-mediation-server"></a>添加独立中介服务器

1. 启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 "skype for business **server 2015**", 然后单击 "skype for business**服务器2015Topology 生成器**"。
    
2. 在拓扑生成器的控制台树中, 展开要为其定义中介服务器的网站的名称。
    
3. 在控制台树中, 右键单击 "**中介池**" 节点, 然后单击 "**中介服务器池**"。
    
4. 在 "**定义新中介池**" 中, 键入中介服务器池完全限定的域名 (FQDN)。
    
5. 接下来，执行下列操作之一：
    
   - 如果你想要在池中部署多个中介服务器以提供高可用性, 请选择 "**多台计算机池**"。
    
     > [!NOTE]
     > 必须[部署](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing)才能支持具有多个中介服务器的中介服务器池。
  
   - 如果你只希望在池中部署一个中介服务器, 因为你不需要高可用性, 然后选择 "**单个计算机池**"。 跳过以下步骤。
    
6. 如果在前一步骤中选择了“多计算机池”****，那么在“定义此池中的计算机”**** 项上单击“计算机 FQDN”****，键入此池中每个服务器的 FQDN，然后单击“添加”****。 对要添加到池中的所有其他中介服务器重复此步骤。 定义该池中的所有计算机后，单击“下一步”****。
    
7. 在 "**选择下一跃点"** 页面上, 单击 "**下一跃点池**", 单击将使用此中介服务器池的前端池的 FQDN, 然后单击 "**下一步**"。
    
8. 在“选择边缘服务器”**** 页上执行下列操作之一：
    
   - 如果你想要为已启用企业语音的外部用户提供 PSTN 连接, 请在 "**选择此中介服务器使用的 Edge 池**" 下, 单击将使用此中介服务器池提供 PSTN 连接的 edge 服务器池的 FQDN这些外部用户, 然后单击 "**下一步**"。
    
   - 如果您不打算为企业语音启用外部用户, 或者如果您不想在内部网络外部向用户提供 PSTN 连接, 请单击 "**下一步**"。
    
9. 右键单击**Skype for Business Server 2015**节点, 然后单击 "**发布拓扑**"。
    
## <a name="define-the-mediation-server-listening-ports"></a>定义中介服务器侦听端口

按照本主题中的步骤, 使用拓扑生成器定义中介服务器或池将接受来自网关对等的传入连接的侦听端口。
  
### <a name="to-modify-the-mediation-server-listening-ports"></a>修改中介服务器侦听端口

1. 启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 "skype for business **server 2015**", 然后单击 "skype for business**服务器2015Topology 生成器**"。
    
2. 在拓扑生成器的控制台树中, 展开 "**中介池**" 节点, 然后右键单击以前创建的中介服务器。
    
3. 默认情况下, 中介服务器上的 SIP 侦听端口为来自 Skype for Business 服务器的 TLS 流量 5070, 而5067用于来自对等方 (如网关、PBXes 或 SBCs) 的 TLS 流量。 默认情况下，TCP 端口处于禁用状态。 如果有不支持 TLS 的网关，则必须启用 TCP 端口。
    
4. 指定所需的 TLS 或 TCP 侦听端口范围中介服务器将接受来自 PSTN 网关的传入连接。
    
    > [!NOTE]
    > 如果未选中“启用 TCP 端口”****，则不需要输入 TCP 端口范围。此设置是可选的。
  

