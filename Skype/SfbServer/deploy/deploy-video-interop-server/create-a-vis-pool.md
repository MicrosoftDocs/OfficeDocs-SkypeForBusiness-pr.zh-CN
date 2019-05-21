---
title: 在 Skype for Business 服务器中创建 VIS 池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: '摘要: 使用拓扑生成器在 Skype for Business 服务器中创建视频互操作服务器池。'
ms.openlocfilehash: 3e01659c4cef268a8748bd14c658eb5168b3ac97
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302726"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a>在 Skype for Business 服务器中创建 VIS 池
 
**摘要:** 使用拓扑生成器在 Skype for Business 服务器中创建视频互操作服务器池。
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a>使用拓扑生成器创建 VIS 或 VIS 池

1. 在前端服务器上打开拓扑生成器。 在拓扑生成器的左窗格中, 右键单击 "**视频互操作服务器池**", 然后选择 "**新建视频互操作服务器池**"。 
    
2. 这将打开“**创建新的视频互操作服务器池**”向导。 为新视频互操作服务器提供池 FQDN, 然后选择 "**此池拥有一个服务器**" 或 "此池基于你的要求**拥有多台服务器**", 然后按 "**下一步**"。
    
    如果要部署视频互操作服务器池以提供高可用性, 请选择 "**此池具有多个服务器**"。 对于该选项，请记住： 
    
    - 必须部署 DNS 负载平衡以支持视频互操作服务器池。 
    
   - 在下一页的“**定义此池中的计算机**”条目上，在文本字段中输入池中每台服务器的**计算机 FQDN**，然后单击“**添加**”。 重复此步骤, 将另一个视频互操作服务器添加到池中。 定义完池中的所有计算机后，请单击“**下一步**”。
    
     如果你只希望在池中部署一个视频互操作服务器, 因为你不需要高可用性, 请选择 "**此池拥有一台服务器**", 然后按 "**下一步**"。
    
3. 从下拉列表中选择下一个跃点池/FE，然后单击“**下一步**”。
    
4. 选择要与 VIS 关联的边缘池，然后单击“**完成**”。
    
5. 设置 TCP 或 TLS 端口。
    
    从拓扑生成器左窗格中选择新添加的视频互操作服务器, 右键单击它, 然后选择 "**编辑属性**"。 根据您的要求启用或更新 TCP 或 TLS 端口，然后选择“**确定**”。 尽管添加默认 TLS, 但只有 TCP 已使用 Cisco 统一通信管理器 (CallManager 或 CUCM) 进行完全测试。
    
6. 添加视频网关。要执行此操作，展开“共享组件”，右键单击“**视频网关**”，然后选择“**新建视频网关**”。
    
7. 提供视频网关 FQDN 或 IP 地址。视频网关可以在子域或其他域中。您系统的 VTC 使用的 CUCM 充当视频网关。
    
8. 适当地选择 IPv4 或 IPv6。您可以使用所有配置的 IP 地址或限制服务使用选定的 IP 地址。
    
9. 选择视频网关的侦听端口。 选择传输协议 (TCP 或 TLS), 并将其与为视频 SIP 主干设置的视频互操作服务器相关联。 视频网关的传输协议应与为 VIS 配置的传输协议相匹配。
    
10. 完成上述步骤后，将添加对应的 SIP 视频中继。 右键单击 SIP 视频中继，然后选择刚才添加的中继。 视频 SIP 主干名称、关联的视频互操作服务器、SIP 传输协议和端口都可以更改。 
    
    > [!NOTE]
    >  视频互操作服务器支持 1: N 中继。 因此, 可以添加多个中继, 它们与单个视频互操作服务器相关联, 每个干线在不同的视频网关上终止。 限制是特定视频网关有一个且仅有一个可定义到 Skype for Business 服务器部署的主干。
  
11. 如在[Skype For Business Server 2015 中创建和发布新拓扑](../../deploy/install/create-and-publish-new-topology.md)中所述, 发布拓扑文档。
    
    > [!NOTE]
    > 若要提高复原能力, 您可能希望配置第二个视频互操作服务器或 VIS 池, 或备份前端池。 有关更多信息，请参阅[Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency)。
  
现已完成所有使用拓扑生成器执行的任务。 请继续在新的 VIS 服务器上安装软件。
## <a name="see-also"></a>另请参阅

[在 Skype for Business Server 中部署 VIS 服务器角色](deploy-the-vis-server-role.md)

[Skype for business Server 中的视频互操作服务器计划](../../plan-your-deployment/video-interop-server.md)
  
[在 Skype for Business Server 2015 中创建和发布新拓扑](../../deploy/install/create-and-publish-new-topology.md)
