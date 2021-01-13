---
title: 在 Skype for Business Server 的拓扑生成器中部署中介服务器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
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
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 摘要：了解如何在 Skype for Business Server 的拓扑生成器中定义和部署中介服务器。
ms.openlocfilehash: b74819d7e68f76392beaa89427b3cf76f24b82d9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836912"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a>在 Skype for Business Server 的拓扑生成器中部署中介服务器
 
**摘要：** 了解如何在 Skype for Business Server 的拓扑生成器中定义和部署中介服务器。
  
前端池中提供了 企业语音 工作负载、电话拨入式会议和高级 企业语音 应用程序 (响应组应用程序、呼叫停止应用程序、呼叫允许控制 (CAC) 等) 。 中介服务器的功能内置于前端服务器中。 不需要单独的独立中介服务器。 
  
唯一的例外是将 SIP 中继配置为连接到 Internet 电话服务提供商的会话边界控制器的情况。 若要将企业语音基础结构连接到 SIP 中继提供商，必须部署单独的中介服务器。
  
Skype for Business Server (前端池上并排的中介服务器或独立中介服务器) 与网关之间的连接定义为称为中继的逻辑关联。 本节中的主题介绍如何定义中继，以及在连接到 SIP 中继的情况下，如何部署独立的中介服务器。
  
## <a name="define-a-mediation-server-in-topology-builder"></a>在拓扑生成器中定义中介服务器

可以将中介服务器添加为前端池上的并排角色，或定义单独的独立中介服务器池。
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>将中介服务器添加到前端池

1. 启动拓扑生成器 **：单击"** 开始"，**单击"** 所有程序"，再单击 **"Skype for Business Server 2015"，** 然后单击 **"Skype for Business Server 2015Topology Builder"。**
    
2. 在拓扑生成器的控制台树中，展开要定义其前端池的站点的名称。
    
3. 在控制台树中，右键单击您想要的前端池的类型，然后单击 **"新建前端池"。**
    
4. 在“定义新的前端池”向导中导航，直到到达“选择并置服务器角色”页。
    
5. 在 **"选择并集服务器角色"中**，选中" **并插中介服务器"选项**。
    
    > [!NOTE]
    > 如果选择的前端池的类型为 Enterprise Edition，则中介服务器组件将安装在该前端池的所有前端服务器上。 
  
    > [!NOTE]
    > 中介 **服务器使用的** 下一个跃点池将是并排中介服务器的前端池。
  
    > [!NOTE]
    > 中介 **服务器** 使用的边缘池将是与并排中介服务器的前端池关联的同一边缘池。
  
6. 单击 **"默认** "以使用此前端池将呼叫路由到 PSTN。
    
7. 完成 **将** 一个或多个对等方与前端池关联后，单击"完成"。
    
    > [!NOTE]
    > 在继续执行 企业语音 部署过程中的下一步之前，请确保中介服务器池 (即与) 并排的中介服务器组件的前端池正在使用指定的 FQDN。 
  
8. 右键单击 **Skype for Business Server 2015** 节点，然后单击"发布 **拓扑"。**
    
### <a name="to-add-a-standalone-mediation-server"></a>添加独立中介服务器

1. 启动拓扑生成器 **：单击"** 开始"，**单击"** 所有程序"，再单击 **"Skype for Business Server 2015"，** 然后单击 **"Skype for Business Server 2015Topology Builder"。**
    
2. 在拓扑生成器的控制台树中，展开要定义中介服务器的站点的名称。
    
3. 在控制台树中，右键单击 **中介池** 节点，然后单击 **中介服务器池**。
    
4. 在 **"定义新中介池"中**，键入中介服务器池的完全限定域名 (FQDN) 。
    
5. 接下来，执行下列操作之一：
    
   - 如果要在池中部署多个中介服务器以提供高可用性，请选择 **"多计算机池"。**
    
     > [!NOTE]
     > 必须 [部署以支持](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) 具有多个中介服务器的中介服务器池。
  
   - 如果因为不需要高可用性而只想在池中部署一台中介服务器，请选择"**单计算机池"。** 跳过以下步骤。
    
6. 如果在前一步骤中选择了“多计算机池”，那么在“定义此池中的计算机”项上单击“计算机 FQDN”，键入此池中每个服务器的 FQDN，然后单击“添加”。 对要添加到池中的所有其他中介服务器重复此步骤。 定义该池中的所有计算机后，单击“下一步”。
    
7. 在 **"选择下一** 跃点"页上，单击"下一跃点池"，单击将使用此中介服务器池的前端池的 FQDN，然后单击"下一 **步"。**
    
8. 在“选择边缘服务器”页上执行下列操作之一：
    
   - 如果要为启用 企业语音 的外部用户提供 PSTN 连接，请在"选择此中介服务器使用的边缘池"下，单击将使用此中介服务器池向这些外部用户提供 PSTN 连接的边缘服务器池的 FQDN，然后单击"下一步 **"。**
    
   - 如果您计划不为外部用户启用 企业语音，或者不希望在用户位于内部网络外部时为用户提供 PSTN 连接，请单击"下一 **步"。**
    
9. 右键单击 **Skype for Business Server 2015** 节点，然后单击"发布 **拓扑"。**
    
## <a name="define-the-mediation-server-listening-ports"></a>定义中介服务器侦听端口

按照本主题中的步骤使用拓扑生成器定义中介服务器或池将接受来自对等网关的传入连接的侦听端口。
  
### <a name="to-modify-the-mediation-server-listening-ports"></a>修改中介服务器侦听端口

1. 启动拓扑生成器 **：单击"** 开始"，**单击"** 所有程序"，再单击 **"Skype for Business Server 2015"，** 然后单击 **"Skype for Business Server 2015Topology Builder"。**
    
2. 在拓扑生成器的控制台树中，展开 **中介** 池节点，然后右键单击之前创建的中介服务器。
    
3. 默认情况下，中介服务器的 SIP 侦听端口对于来自 Skype for Business Server 的 TLS 流量为 5070，来自对等方（如网关、PBX 或 SBC）的 T (LS 流量为 5067) 。 默认情况下，TCP 处于禁用状态。 如果有不支持 TLS 的网关，则必须启用 TCP 端口。
    
4. 指定中介服务器将接受来自 PSTN 网关的传入连接所需的 TLS 或 TCP 侦听端口范围。
    
    > [!NOTE]
    > 如果未选中“启用 TCP 端口”，则不需要输入 TCP 端口范围。 此设置是可选的。
  

