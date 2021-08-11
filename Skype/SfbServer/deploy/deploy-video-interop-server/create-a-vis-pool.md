---
title: 在池中创建 VIS Skype for Business Server
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
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 摘要：使用拓扑生成器在 Skype for Business Server创建视频互操作服务器池。
ms.openlocfilehash: 91a1ed8b5b8d5ce728a666be507a1c1026b0c88460d9ba33b519f1f3d3825aa8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54283574"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a>在池中创建 VIS Skype for Business Server
 
**摘要：** 使用拓扑生成器在 Skype for Business Server创建视频互操作服务器池。
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a>使用拓扑生成器创建 VIS 或 VIS 池

1. 在前端服务器上打开拓扑生成器。 从拓扑生成器的左窗格中，右键单击"视频 **互操作服务器池"，** 然后选择"**新建视频互操作服务器池"。** 
    
2. 这将打开"新建 **视频互操作服务器池"** 向导。 提供新视频互操作服务器的池 FQDN，然后根据您的要求选择"此池具有一台服务器"或"此池具有多台服务器"，然后按"下一 **步"。**
    
    如果要部署视频互操作服务器池以提供高可用性，请选择"**此池具有多台服务器"。** 请牢记此选项： 
    
    - 必须部署 DNS 负载平衡以支持视频互操作服务器池。 
    
   - 下一页的"定义此池中的计算机"项中，在文本字段中输入池中每个服务器的计算机 **FQDN，** 然后单击"添加 **"。** 重复此步骤以向池中添加另一个视频互操作服务器。 定义池中的所有计算机后，按"下一 **步"。**
    
     如果因为不需要高可用性而只想在池中部署一个视频互操作服务器，请选择"此池有 **一** 台服务器"，然后按"下一 **步"。**
    
3. 从下拉列表中选择下一个跃点池/FE，然后按"下一 **步"。**
    
4. 选择要与 VIS 关联的边缘池，然后按"完成 **"。**
    
5. 设置 TCP 或 TLS 端口。
    
    从拓扑生成器的左窗格中选择新添加的视频互操作服务器，右键单击它，然后选择编辑 **属性**。 根据要求启用或更新 TCP 或 TLS 端口，然后选择"确定 **"。** 尽管默认情况下会添加 TLS，但只有 TCP 已使用 Cisco 统一通信管理器 (CallManager 或 CUCM) 。
    
6. 添加视频网关。 为此，请展开"共享组件"，右键单击 **"视频网关"，** 然后选择"**新建视频网关"。**
    
7. 提供视频网关 FQDN 或 IP 地址。 视频网关可能在不同的子域或其他域中。 系统 VTC 使用的 CUCM 充当视频网关。
    
8. 适当地选择 IPv4 或 IPv6。 可以使用所有已配置的 IP 地址或将服务用途限制为所选 IP 地址。
    
9. 选择视频网关的侦听端口。 选择 TCP 或 TLS (传输协议) 并将其与为视频 SIP 中继设置的视频互操作服务器关联。 视频网关的传输协议应匹配为 VIS 配置的传输协议。
    
10. 完成上述步骤后，会添加相应的 SIP 视频中继。 右键单击 SIP 视频中继，然后选择刚刚添加的中继。 视频 SIP 中继名称、关联的视频互操作服务器、SIP 传输协议和端口都可以更改。 
    
    > [!NOTE]
    >  视频互操作服务器支持 1：N 中继。 因此，可以添加多个中继，这些中继与一个视频互操作服务器相关联，其中每个中继终止在不同的视频网关上。 该限制是，特定视频网关具有一个且只有一个可定义到部署Skype for Business Server中继。
  
11. 发布拓扑文档，如 Create [and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md)中所述。
    
    > [!NOTE]
    > 为了提高恢复能力，您可能需要配置第二个视频互操作服务器或 VIS 池，或备份前端池。 有关详细信息 [，请参阅](../../plan-your-deployment/video-interop-server.md#resiliency) 复原机制。
  
现在，使用拓扑生成器执行的所有任务都应已完成。 继续将软件安装到新的 VIS 服务器或服务器上。
## <a name="see-also"></a>另请参阅

[部署 VIS 服务器角色Skype for Business Server](deploy-the-vis-server-role.md)

[规划视频互操作服务器Skype for Business Server](../../plan-your-deployment/video-interop-server.md)
  
[在 Skype for Business Server 2015 中创建新拓扑](../../deploy/install/create-and-publish-new-topology.md)
