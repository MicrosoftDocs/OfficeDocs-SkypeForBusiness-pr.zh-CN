---
title: 在 Skype for Business Server 2015 中创建 VIS 池
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 摘要： 在 Skype 视频互操作服务器池创建的业务服务器 2015 使用拓扑生成器。
ms.openlocfilehash: ab34cf5b547301314bf169b56481818f78e9908a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="create-a-vis-pool-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中创建 VIS 池
 
**摘要：**在 Skype 为业务服务器 2015 使用拓扑生成器创建一个视频互操作服务器池。
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a>使用拓扑生成器创建 VIS 或 VIS 池

1. 在前端服务器上打开拓扑生成器。 拓扑生成器的左侧窗格中，右键单击 * * 视频互操作服务器池 * *，然后选择**新视频互操作服务器池**。 
    
2. 这将打开“**创建新的视频互操作服务器池**”向导。 提供新视频互操作服务器池的 FQDN，然后选择**此池中包含一台服务器**或根据您的要求，**该池有多个服务器**然后按**下一步**。
    
    如果您要部署一个视频互操作服务器池来提供高可用性，请选择**该池有多个服务器**。 对于该选项，请记住： 
    
    - 您必须部署 DNS 负载平衡支持视频互操作服务器池。 
    
   - 在下一页的“**定义此池中的计算机**”条目上，在文本字段中输入池中每台服务器的**计算机 FQDN**，然后单击“**添加**”。 重复此步骤可将视频互操作的另一个服务器添加到池。 定义完池中的所有计算机后，请单击“**下一步**”。
    
    如果您要部署池中的一个视频互操作服务器，因为您不需要高可用性，然后选择**该池中包含一台服务器**，并按**下一步**。
    
3. 从下拉列表中选择下一个跃点池/FE，然后单击“**下一步**”。
    
4. 选择要与 VIS 关联的边缘池，然后单击“**完成**”。
    
5. 设置 TCP 或 TLS 端口。
    
    选择新添加的视频互操作服务器从拓扑生成器的左窗格中，右击它并选择**编辑属性**。 根据您的要求启用或更新 TCP 或 TLS 端口，然后选择“**确定**”。 尽管默认会添加 TLS，但只为 CUCM 全面测试了 TCP。
    
6. 添加视频网关。要执行此操作，展开“共享组件”，右键单击“**视频网关**”，然后选择“**新建视频网关**”。
    
7. 提供视频网关 FQDN 或 IP 地址。视频网关可以在子域或其他域中。您系统的 VTC 使用的 CUCM 充当视频网关。
    
8. 适当地选择 IPv4 或 IPv6。您可以使用所有配置的 IP 地址或限制服务使用选定的 IP 地址。
    
9. 选择视频网关的侦听端口。 选择传输协议 （TCP 或 TLS） 并将其与互操作的视频服务器的视频的 SIP 中继设置。 视频网关的传输协议应与为 VIS 配置的传输协议相匹配。
    
10. 完成上述步骤后，将添加对应的 SIP 视频中继。 右键单击 SIP 视频中继，然后选择刚才添加的中继。 该视频的 SIP 中继名称，相关视频互操作服务器，SIP 传输协议和端口均可进行修改。 
    
    > [!NOTE]
    >  视频互操作服务器支持 1: n 的中继。 因此多中继可以添加，只有单一的视频互操作服务器，其中每个干线终止在不同的视频网关相关联。 限制是一个特定的视频网关有一个且只有一个可以被定义为业务服务器部署 Skype 的干线。
  
11. 发布拓扑文档中所述[创建并发布新的拓扑结构在 Skype 业务服务器 2015年](../../deploy/install/create-and-publish-new-topology.md)。
    
    > [!NOTE]
    > 为提高可恢复性，您可能需要配置第二个视频互操作服务器或 VIS 池或备份前端池。 有关更多信息，请参阅[Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency)。
  
现已完成所有使用拓扑生成器执行的任务。请继续在新的 VIS 服务器上安装软件。
## <a name="see-also"></a>另请参阅

#### 

[为业务服务器 2015年部署在 Skype 的 VIS 服务器角色](deploy-the-vis-server-role.md)
#### 

[在 Skype 的视频互操作服务器业务服务器 2015年计划](../../plan-your-deployment/video-interop-server.md)
  
[创建并发布新的拓扑结构在 Skype 业务服务器 2015](../../deploy/install/create-and-publish-new-topology.md)

