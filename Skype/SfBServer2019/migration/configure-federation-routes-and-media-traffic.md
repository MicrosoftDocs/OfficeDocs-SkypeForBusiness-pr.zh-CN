---
title: 配置联盟路由和媒体流量
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 联盟是两个或更多 SIP 域之间的一种信任关系，它允许不同组织中的用户跨越网络边界进行通信。 迁移到你的试点池之后，需要从先前版本边缘服务器的联合路由转换为 Skype for Business Server 2019 边缘服务器的联合路由。
ms.openlocfilehash: 2fafe991b8d09a477d084bdf2081d240e4830589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754032"
---
# <a name="configure-federation-routes-and-media-traffic"></a>配置联盟路由和媒体流量

联盟是两个或更多 SIP 域之间的一种信任关系，它允许不同组织中的用户跨越网络边界进行通信。 迁移到你的试点池之后，需要从以前版本的边缘服务器的联合路由转换为 Skype for Business Server 2019 边缘服务器的联合路由。
  
使用以下过程可将联合路由和媒体流量路由从以前版本的边缘服务器和控制器转换为 Skype for business Server 2019 Edge 服务器（针对单站点部署）。
  
> [!IMPORTANT]
> 若要更改联合路由和媒体流量路由，需要为 Skype for Business Server 2019 和早期版本边缘服务器安排维护停机时间。 整个转换过程还意味着服务中断期间无法进行联盟访问。 应将停机时间安排在预计用户活动最少的时间段内。 还应向最终用户提供包含丰富信息的通知。 相应地规划这次服务中断并正确设置组织的期望。 
  
> [!IMPORTANT]
> 如果您的旧边缘服务器配置为对访问边缘服务、Web 会议边缘服务和 A/V 边缘服务使用相同的 FQDN，则不支持本节中的过程。 如果将旧边缘服务配置为使用相同的 FQDN，则必须先迁移所有用户，然后在 Skype for Business Server 2019 边缘服务器上启用联合之前，解除以前版本的边缘服务器。 
  
> [!IMPORTANT]
> 如果您的 XMPP 联盟通过 Skype for Business Server 2019 边缘服务器进行路由，则以前版本中的用户将无法与 XMPP 联盟伙伴通信，直到所有用户都已移动到 Skype for Business Server 2019、已配置 XMPP 策略和证书、已在 Skype for Business Server 2019 上配置 XMPP 联盟伙伴，最后更新了 DNS 条目。 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a>从 Skype for Business Server 2019 网站中删除旧版联合身份验证关联

1. 在 Skype for Business Server 2019 前端服务器上，在拓扑生成器中打开现有拓扑。 
    
2. 在左窗格中，导航到位于**Skype For Business Server**正下方的 "网站" 节点。
    
3. 右键单击站点，然后单击“编辑属性”****。
    
4. 在左侧窗格中，选择“联盟路由”****。 
    
5. 在 "**站点联合路由分配**" 下，清除 "**启用 SIP 联盟**" 复选框以禁用通过旧环境的联盟路由。 
  
6. 单击“确定”**** 关闭“编辑属性”页。 
    
7. 从**拓扑生成器**中，选择顶部节点 " **Skype for business Server**"。
    
8. 从“操作”**** 菜单上，单击“发布拓扑”****。
    
9. 单击 "**下一步**" 完成发布过程，然后在发布过程完成后单击 "**完成**"。 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>将旧边缘服务器配置为非联盟边缘服务器

1. 在左窗格中，导航到 "旧安装" 节点，然后导航到 "**边缘池**" 节点。 
    
2. 右键单击该边缘服务器，然后单击“编辑属性”****。
    
3. 在左窗格中，选择“常规”****。 
    
4. 清除 "**为此边缘池启用联盟（端口5061）** " 复选框，然后选择 **"确定"** 关闭该页面。 
  
5. 从“操作”**** 菜单中，选择“发布部署”****，然后单击“下一步”****。
    
6. “发布向导”**** 完成时，单击“完成”**** 关闭向导。 
    
7. 验证是否在拓扑生成器中禁用了旧版边缘服务器的联盟。
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a>在旧版边缘服务器上配置证书

1. 从旧版边缘服务器导出外部访问代理证书和私钥。 
    
2. 在 Skype for Business Server 2019 边缘服务器上，然后导入上一步中的访问代理外部证书。
    
3. 将访问代理外部证书分配给边缘服务器的 Skype for Business Server 2019 外部接口。
    
4. 应从受信任的 CA 请求并分配 Skype for business Server 2019 边缘服务器的内部接口证书。 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a>将以前版本的联盟路由更改为使用 Skype for Business Server 2019 边缘服务器

1. 从拓扑生成器的左侧窗格中，导航到 " **Skype For Business Server 2019** " 节点，然后导航到 "**边缘池**" 节点。 
    
2. 右键单击该边缘服务器，然后单击“编辑属性”****。
    
3. 在左窗格中，选择“常规”****。 
    
4. 选中 "为**此边缘池启用联盟（端口5061）**" 复选框，然后单击 **"确定"** 关闭该页面。 
  
5. 从“操作”**** 菜单中，选择“发布部署”****，然后单击“下一步”****。
    
6. “发布向导”**** 完成时，单击“完成”**** 关闭向导。 
    
7. 验证是否已在拓扑生成器中将**联合身份验证（端口5061）** 设置为 "**已启用**"。
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a>更新 Skype for Business Server 2019 边缘服务器联合下一个跃点

1. 从拓扑生成器的左侧窗格中，导航到 " **Skype For Business Server 2019** " 节点，然后导航到 "**边缘池**" 节点。 
    
2. 展开节点，右键单击列出的边缘服务器，然后单击“编辑属性”****。 
    
3. 在 "**常规**" 页面的 "**下一跃点选择**" 下，从下拉列表中选择 "Skype for business Server 2019 池"。
  
4. 单击“确定”**** 关闭“编辑属性”页。 
    
5. 从**拓扑生成器**中，选择顶部节点 " **Skype for business Server**"。 
    
6. 从“操作”**** 菜单中，单击“发布拓扑”**** 并完成向导。 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a>配置 Skype for Business Server 2019 边缘服务器出站媒体路径

1. 从拓扑生成器的左侧窗格中，导航到 " **Skype For Business Server 2019** " 节点，然后导航到 "低于**Standard edition 前端服务器**" 或 " **Enterprise Edition 前端池**" 的池。
    
2. 右键单击该池，然后单击“编辑属性”****。
    
3. 在“关联”**** 部分，选中“关联边缘池(用于媒体组件)”**** 复选框。 
  
4. 从下拉框中，选择 Skype for Business Server 2019 边缘服务器。
    
5. 单击“确定”**** 关闭“编辑属性”**** 页。 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a>启用 Skype for Business Server 2019 边缘服务器联盟

1. 从拓扑生成器的左侧窗格中，导航到 " **Skype For Business Server 2019** " 节点，然后导航到 "**边缘池**" 节点。 
    
2. 展开节点，右键单击列出的边缘服务器，然后单击“编辑属性”****。 
    
    > [!NOTE]
    > 仅可为单个边缘池启用联合身份验证。 如果具有多个边缘池，请选择一个用作联盟边缘池。 
  
3. 在 "**常规**" 页面上，验证是否已选中 "**为此边缘池启用联盟（端口5061）** " 复选框。 
  
4. 单击“确定”**** 关闭“编辑属性”页。 
    
5. 导航到 "网站" 节点。 
    
6. 右键单击站点，然后单击“编辑属性”****。
    
7. 在左窗格中，单击“联盟路由”****。
    
8. 在 "**站点联合路由分配**" 下，选择 "**启用 SIP 联盟**"，然后从列表中选择列出的 Skype For Business Server 2019 边缘服务器。 
  
9. 单击“确定”**** 关闭“编辑属性”**** 页。 
    
     对于多站点部署，在每个站点上完成该过程。 
    
## <a name="to-publish-edge-server-configuration-changes"></a>发布边缘服务器配置更改

1. 从**拓扑生成器**中，选择顶部节点 " **Skype for business Server**"。 
    
2. 从“操作”**** 菜单中，选择“发布拓扑”**** 并完成向导。 
    
3. 稍待片刻以便在部署中的所有池间执行 Active Directory 复制。
    
    > [!NOTE]
    > 您可能会看到以下消息：**警告：该拓扑包含多个联合边缘服务器。在迁移到产品的较新版本的过程中，可能会发生这种情况。在这种情况下，将只有一台边缘服务器主动用于联盟。验证外部 DNS SRV 记录是否指向正确的边缘服务器。如果要将多个联合边缘服务器部署为同时处于活动状态（即不是迁移方案），请验证所有联盟伙伴是否都在使用 Skype for Business Server。验证外部 DNS SRV 记录是否列出所有启用了联合身份验证的边缘服务器。** 该警告是预期警告，可以放心地忽略。 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a>配置 Skype for Business Server 2019 边缘服务器

1. 使所有 Skype for Business Server 2019 边缘服务器联机。 
    
2. 更新外部防火墙路由规则或硬件负载平衡器设置以将外部访问的 SIP 通信（通常是端口443）和联合身份验证（通常是端口5061）发送到 Skype for business Server 2019 边缘服务器，而不是旧边缘服务器。
    
    > [!NOTE]
    > 如果没有硬件负载平衡器，则需要更新联合的 DNS A 记录以解析为新的 Skype for Business Server 访问边缘服务器。 若要实现此目的，最大程度地减少中断，请减小外部 Skype for Business Server 访问边缘 FQDN 的 TLL 值，以便在将 DNS 更新为指向新的 Skype for Business Server 访问边缘时，将快速更新联合身份验证和远程访问。 
  
3. 从每台边缘服务器计算机停止**Skype For Business Server 访问边缘**。 
    
4. 从每个旧边缘服务器计算机上，从 "**管理工具**" 中打开 "**服务**" 小程序。
    
5. 在 "服务" 列表中，查找**Skype For Business Server 访问边缘**。
    
6. 右键单击服务名称，然后选择“停止”**** 以停止该服务。 
    
7. 将“启动”类型设置为“已禁用”****。 
    
8. 单击“确定”**** 关闭“属性”**** 窗口。 
    

