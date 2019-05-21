---
title: 配置联合路由和媒体流量
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 联盟是两个或多个 SIP 域之间的信任关系, 这些 SIP 域允许单独组织中的用户通过网络边界进行通信。 迁移到你的试点池后, 你需要从你以前的版本 Edge 服务器的联盟路径切换到 Skype for business Server 2019 Edge 服务器的联合路线。
ms.openlocfilehash: 6b76932c8b988dbed61cba1470f32a51f6585536
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298317"
---
# <a name="configure-federation-routes-and-media-traffic"></a>配置联合路由和媒体流量

联盟是两个或多个 SIP 域之间的信任关系, 这些 SIP 域允许单独组织中的用户通过网络边界进行通信。 迁移到试验池后, 您需要从您以前版本的边缘服务器的联盟路径切换到 Skype for business Server 2019 Edge 服务器的联盟路线。
  
使用以下过程可将你以前版本的 Edge 服务器和控制器中的联盟路由和媒体流量路由转换到 Skype for business Server 2019 Edge 服务器 (对于单站点部署)。
  
> [!IMPORTANT]
> 更改联盟路由和媒体流量路由需要你为 Skype for Business Server 2019 和早期版本 Edge 服务器安排维护停机时间。 此整个过渡过程还意味着, 在中断期间, 联盟访问将不可用。 你应该将停机时间安排为预计最少的用户活动。 你还应向最终用户提供足够的通知。 为此停机安排相应的计划, 并在你的组织内设置适当的期望值。 
  
> [!IMPORTANT]
> 如果你的旧版 Edge 服务器配置为对访问边缘服务使用相同的 FQDN、Web 会议边缘服务和 A/V 边缘服务, 则不支持本部分中的过程。 如果将旧边缘服务配置为使用相同的 FQDN, 则必须首先迁移所有用户, 然后在 Skype for business Server 2019 Edge 服务器上启用联盟之前, 取消以前版本的边缘服务器。 
  
> [!IMPORTANT]
> 如果你的 XMPP 联盟通过 Skype for Business Server 2019 Edge 服务器路由, 则以前版本中的用户将无法与 XMPP 联盟合作伙伴通信, 直到所有用户都已移动到 Skype for Business Server 2019、XMPP 策略和证书已配置, XMPP 联盟合作伙伴已在 Skype for Business Server 2019 上配置, 最后, 已更新 DNS 条目。 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a>从 Skype for Business Server 2019 网站中删除旧式联合身份验证关联

1. 在 Skype for business 服务器2019前端服务器上, 在拓扑生成器中打开现有拓扑。 
    
2. 在左窗格中, 导航到位于 " **Skype For business" 服务器**正下方的 "网站" 节点。
    
3. 右键单击网站, 然后单击 "**编辑属性**"。
    
4. 在左窗格中, 选择 "**联盟路由**"。 
    
5. 在 "**站点联合路由分配**" 下, 清除 "**启用 SIP 联盟**" 复选框以通过旧环境禁用联盟路由。 
  
6. 单击 **"确定"** 以关闭 "编辑属性" 页面。 
    
7. 从**拓扑生成器**中, 选择顶部节点**Skype for business 服务器**。
    
8. 从 "**操作**" 菜单中, 单击 "**发布拓扑**"。
    
9. 单击 "**下一步**" 完成发布过程, 然后在发布过程完成时单击 "**完成**"。 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>将旧式边缘服务器配置为非联合边缘服务器

1. 在左窗格中, 导航到 "旧安装" 节点, 然后导航到 "**边缘池**" 节点。 
    
2. 右键单击边缘服务器, 然后单击 "**编辑属性**"。
    
3. 在左窗格中选择 "**常规**"。 
    
4. 清除 "**为此 Edge 池启用联盟 (端口 5061)** " 复选框, 然后选择 **"确定"** 关闭页面。 
  
5. 从 "**操作**" 菜单中, 选择 "**发布拓扑**", 然后单击 "**下一步**"。
    
6. **发布向导**完成后, 单击 "**完成**" 关闭向导。 
    
7. 验证拓扑生成器中是否已禁用旧版 Edge 服务器的联盟。
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a>在旧版边缘服务器上配置证书

1. 从旧边缘服务器导出外部访问代理服务器证书和私钥。 
    
2. 在 Skype for Business Server 2019 Edge 服务器上, 然后从上一步导入 "访问代理服务器外部证书"。
    
3. 将访问代理服务器外部证书分配给 Edge 服务器的 Skype for business Server 2019 外部接口。
    
4. 应从受信任的 CA 请求并分配 Skype for business Server 2019 Edge 服务器的内部界面证书。 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a>将以前版本的联合身份验证路由更改为使用 Skype for Business Server 2019 Edge 服务器

1. 在 "拓扑生成器" 中, 在左窗格中, 导航到 " **Skype For Business 服务器 2019** " 节点, 然后导航到 "**边缘池**" 节点。 
    
2. 右键单击边缘服务器, 然后单击 "**编辑属性**"。
    
3. 在左窗格中选择 "**常规**"。 
    
4. 选中 "为**此 Edge 池启用联盟 (端口 5061)**" 复选框, 然后单击 **"确定"** 关闭页面。 
  
5. 从 "**操作**" 菜单中, 选择 "**发布拓扑**", 然后单击 "**下一步**"。
    
6. **发布向导**完成后, 单击 "**完成**" 关闭向导。 
    
7. 验证在拓扑结构生成器中是否已将 "**联盟" (端口 5061)** 设置为 "**已启用**"。
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a>更新 Skype for Business Server 2019 Edge 服务器联合身份验证下一跃点

1. 在 "拓扑生成器" 中, 在左窗格中, 导航到 " **Skype For Business 服务器 2019** " 节点, 然后导航到 "**边缘池**" 节点。 
    
2. 展开节点, 右键单击列出的边缘服务器, 然后单击 "**编辑属性**"。 
    
3. 在 "**常规**" 页面上的 "**下一跃点选择**" 下, 从下拉列表中选择 Skype for business Server 2019 池。
  
4. 单击 **"确定"** 以关闭 "编辑属性" 页面。 
    
5. 从**拓扑生成器**中, 选择顶部节点**Skype for business 服务器**。 
    
6. 从 "**操作**" 菜单中, 单击 "**发布拓扑**" 并完成向导。 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a>配置 Skype for Business Server 2019 Edge 服务器出站媒体路径

1. 从拓扑生成器的左窗格中, 导航到**Skype For Business Server 2019**节点, 然后导航到**标准版前端服务器**或**企业版前端池**下的池。
    
2. 右键单击该池, 然后单击 "**编辑属性**"。
    
3. 在 "**关联**" 部分中, 选择 "**关联边缘池 (适用于媒体组件)** " 复选框。 
  
4. 从下拉框中, 选择 Skype for Business Server 2019 Edge 服务器。
    
5. 单击 **"确定"** 以关闭 "**编辑属性**" 页面。 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a>打开 Skype for Business Server 2019 Edge 服务器联合体

1. 在 "拓扑生成器" 中, 在左窗格中, 导航到 " **Skype For Business 服务器 2019** " 节点, 然后导航到 "**边缘池**" 节点。 
    
2. 展开节点, 右键单击列出的边缘服务器, 然后单击 "**编辑属性**"。 
    
    > [!NOTE]
    > 仅可对单个边缘池启用联合身份验证。 如果你有多个边缘池, 请选择一个以用作联盟边缘池。 
  
3. 在 "**常规**" 页面上, 验证已选中 "**为此 Edge 池启用联盟 (端口 5061)** " 复选框。 
  
4. 单击 **"确定"** 以关闭 "编辑属性" 页面。 
    
5. 导航到 "网站" 节点。 
    
6. 右键单击网站, 然后单击 "**编辑属性**"。
    
7. 在左窗格中, 单击 "**联盟路由**"。
    
8. 在 "**站点联合路由分配**" 下, 选择 "**启用 SIP 联盟**", 然后从列表中选择列出的 Skype For Business server 2019 Edge 服务器。 
  
9. 单击 **"确定"** 以关闭 "**编辑属性**" 页面。 
    
     对于多站点部署, 请在每个网站上完成此过程。 
    
## <a name="to-publish-edge-server-configuration-changes"></a>发布边缘服务器配置更改

1. 从**拓扑生成器**中, 选择顶部节点**Skype for business 服务器**。 
    
2. 从 "**操作**" 菜单中, 选择 "**发布拓扑**" 并完成向导。 
    
3. 等待对部署中的所有池执行 Active Directory 复制。
    
    > [!NOTE]
    > 您可能会看到以下消息:**警告: 该拓扑包含多个联合边缘服务器。在迁移到产品的较新版本的过程中可能会发生这种情况。在这种情况下, 仅有一台边缘服务器将主动用于联盟。验证外部 DNS SRV 记录是否指向正确的边缘服务器。如果要将多个联合边缘服务器部署为同时活动 (即不是迁移方案), 请验证所有联盟伙伴是否都在使用 Skype for Business 服务器。验证外部 DNS SRV 记录是否列出所有启用联盟的边缘服务器。** 此警告是预期的, 可以安全忽略。 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a>配置 Skype for Business Server 2019 Edge 服务器

1. 使所有 Skype for business 服务器2019边缘服务器联机。 
    
2. 更新外部防火墙路由规则或硬件负载平衡器设置, 以将外部访问 (通常为端口 443) 和联盟 (通常为端口 5061) 的 SIP 流量发送到 Skype for business Server 2019 Edge 服务器, 而不是旧版边缘服务器。
    
    > [!NOTE]
    > 如果你没有硬件负载平衡器, 则需要更新联合身份验证的 DNS A 记录, 以解析为新的 Skype for Business 服务器访问边缘服务器。 若要以最小的中断完成此操作, 请减少外部 Skype for business 服务器访问边缘 FQDN 的 TLL 值, 以便在更新 DNS 以指向新的 Skype for Business 服务器访问边缘时, 将快速更新联盟和远程访问。 
  
3. 停止每台边缘服务器计算机的**Skype For Business 服务器访问边缘**。 
    
4. 从每个旧式边缘服务器计算机上, 从 "**管理工具**" 中打开 "**服务**" 小程序。
    
5. 在 "服务" 列表中, 找到 " **Skype for Business 服务器访问边缘**"。
    
6. 右键单击服务名称, 然后选择 "**停止**" 以停止该服务。 
    
7. 将 "启动类型" 设置为 "**已禁用**"。 
    
8. 单击 **"确定"** 以关闭 "**属性**" 窗口。 
    

