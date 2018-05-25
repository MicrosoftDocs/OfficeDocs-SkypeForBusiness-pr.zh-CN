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
description: 摘要： 为业务服务器 2015 使用拓扑生成器创建 Skype 视频互操作服务器池。
ms.openlocfilehash: 89fcdf34480bc9b99295993d28e32ca547f07893
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="create-a-vis-pool-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中创建 VIS 池
 
**摘要：** 为业务服务器 2015 使用拓扑生成器创建 Skype 视频互操作服务器池。
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a>使用拓扑生成器创建 VIS 或 VIS 池

1. 在前端服务器上打开拓扑生成器。 从拓扑生成器的左窗格中，右键单击 * * 视频互操作服务器池 * *，然后选择**新的视频互操作服务器池**。 
    
2. 这将打开“**创建新的视频互操作服务器池**”向导。 为新的视频互操作服务器提供池 FQDN，然后选择**此池具有一台服务器**或**此池中具有多个服务器**基于您的要求，然后按**下一步**。
    
    如果您想要部署视频互操作服务器池以提供高可用性，请选择**此池具有多个服务器**。 对于该选项，请记住： 
    
    - 您必须部署 DNS 负载平衡来支持视频互操作服务器池。 
    
   - 在下一页的“**定义此池中的计算机**”条目上，在文本字段中输入池中每台服务器的**计算机 FQDN**，然后单击“**添加**”。 重复此步骤以向池添加视频互操作的另一台服务器。 定义完池中的所有计算机后，请单击“**下一步**”。
    
    如果您想要部署在池中只有一台视频互操作服务器，因为不要求具备高可用性，然后选择**此池中具有一台服务器**，并按**下一步**。
    
3. 从下拉列表中选择下一个跃点池/FE，然后单击“**下一步**”。
    
4. 选择要与 VIS 关联的边缘池，然后单击“**完成**”。
    
5. 设置 TCP 或 TLS 端口。
    
    从拓扑生成器的左窗格中选择新添加的视频互操作服务器，右键单击它，然后选择**编辑属性**。 根据您的要求启用或更新 TCP 或 TLS 端口，然后选择“**确定**”。 尽管默认会添加 TLS，但只为 CUCM 全面测试了 TCP。
    
6. 添加视频网关。要执行此操作，展开“共享组件”，右键单击“**视频网关**”，然后选择“**新建视频网关**”。
    
7. 提供视频网关 FQDN 或 IP 地址。视频网关可以在子域或其他域中。您系统的 VTC 使用的 CUCM 充当视频网关。
    
8. 适当地选择 IPv4 或 IPv6。您可以使用所有配置的 IP 地址或限制服务使用选定的 IP 地址。
    
9. 选择视频网关的侦听端口。 选择传输协议 （TCP 或 TLS），并将其与为视频的 SIP 中继设置视频互操作服务器关联。 视频网关的传输协议应与为 VIS 配置的传输协议相匹配。
    
10. 完成上述步骤后，将添加对应的 SIP 视频中继。 右键单击 SIP 视频中继，然后选择刚才添加的中继。 该视频的 SIP 中继名称，关联视频互操作服务器 SIP 传输协议和端口可所有更改。 
    
    > [!NOTE]
    >  视频互操作服务器支持 1: n 中继。 因此多个中继可以将添加，与单个视频互操作服务器，其中每个中继终止在不同的视频网关相关联。 限制是特定视频网关，可以对业务服务器部署 Skype 定义的且只有一个中继。
  
11. 发布拓扑文档中所述[创建和发布新拓扑中 Skype 的业务服务器 2015年](../../deploy/install/create-and-publish-new-topology.md)。
    
    > [!NOTE]
    > 若要提高恢复能力，您可能想要配置第二个视频互操作服务器或 VIS 池或备份的前端池。 有关更多信息，请参阅[Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency)。
  
现已完成所有使用拓扑生成器执行的任务。请继续在新的 VIS 服务器上安装软件。
## <a name="see-also"></a>另请参阅

#### 

[为业务服务器 2015年部署中 Skype VIS 服务器角色](deploy-the-vis-server-role.md)

[规划视频互操作性中的服务器 Skype 业务 Server 2015](../../plan-your-deployment/video-interop-server.md)
  
[创建和发布新拓扑中 Skype 的业务服务器 2015](../../deploy/install/create-and-publish-new-topology.md)

