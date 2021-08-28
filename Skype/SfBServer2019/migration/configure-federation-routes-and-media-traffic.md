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
ms.localizationpriority: medium
description: 联盟是两个或更多 SIP 域之间的一种信任关系，它允许不同组织中的用户跨越网络边界进行通信。 迁移到试点池后，需要从以前版本边缘服务器的联盟路由转换到 Skype for Business Server 2019 边缘服务器的联盟路由。
ms.openlocfilehash: f051321667e12a468df1186147f6fab1d7bbe5cd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613401"
---
# <a name="configure-federation-routes-and-media-traffic"></a>配置联盟路由和媒体流量

联盟是两个或更多 SIP 域之间的一种信任关系，它允许不同组织中的用户跨越网络边界进行通信。 迁移到试点池后，需要从以前版本的边缘服务器的联盟路由转换到 Skype for Business Server 2019 边缘服务器的联盟路由。
  
使用以下过程将联盟路由和媒体流量路由从以前版本的边缘服务器和控制器转换到 Skype for Business Server 2019 边缘服务器，以用于单站点部署。
  
> [!IMPORTANT]
> 更改联盟路由和媒体流量路由需要为 2019 和早期版本的边缘服务器安排Skype for Business Server停机时间。 整个转换过程还意味着服务中断期间无法进行联盟访问。 应将停机时间安排在预计用户活动最少的时间段内。 还应向最终用户提供包含丰富信息的通知。 相应地规划这次服务中断并正确设置组织的期望。 
  
> [!IMPORTANT]
> 如果旧边缘服务器配置为对访问边缘服务、Web 会议边缘服务和 A/V 边缘服务使用相同的 FQDN，则本节中的过程不受支持。 如果旧边缘服务配置为使用相同的 FQDN，则必须先迁移所有用户，然后在 Skype for Business Server 2019 边缘服务器上启用联盟之前停用以前版本的边缘服务器。 
  
> [!IMPORTANT]
> 如果 XMPP 联盟通过 Skype for Business Server 2019 边缘服务器进行路由，则早期版本的用户将无法与 XMPP 联盟伙伴通信，直到所有用户移至 Skype for Business Server 2019、配置了 XMPP 策略和证书、XMPP 联盟伙伴已在 Skype for Business Server 2019 上配置，并且最后更新了 DNS 条目。 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a>从 2019 站点中删除旧Skype for Business Server关联

1. 在 Skype for Business Server 2019 前端服务器上，在拓扑生成器中打开现有拓扑。 
    
2. 在左窗格中，导航到网站节点，该节点位于网站 **Skype for Business Server。**
    
3. 右键单击站点，然后单击“编辑属性”。
    
4. 在左侧窗格中，选择“联盟路由”。 
    
5. 在 **"站点联盟路由分配"** 下，清除" **启用 SIP** 联盟"复选框以通过旧环境禁用联盟路由。 
  
6. 单击“确定”关闭“编辑属性”页。 
    
7. 从 **拓扑生成器中**，选择顶部节点 **"Skype for Business Server"。**
    
8. 从“操作”菜单上，单击“发布拓扑”。
    
9. 单击 **"** 下一步"完成发布过程，然后在 **发布过程** 完成后单击"完成"。 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>将旧边缘服务器配置为非联盟边缘服务器

1. 在左窗格中，导航到旧版安装节点，然后转到" **边缘池"** 节点。 
    
2. 右键单击该边缘服务器，然后单击“编辑属性”。
    
3. 在左窗格中，选择“常规”。 
    
4. 清除"**为此边缘池启用联盟 (端口 5061**) "复选框，然后选择"确定"关闭页面。 
  
5. 从“操作”菜单中，选择“发布部署”，然后单击“下一步”。
    
6. “发布向导”完成时，单击“完成”关闭向导。 
    
7. 验证拓扑生成器中是否禁用了旧边缘服务器的联盟。
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a>在旧边缘服务器上配置证书

1. 使用私钥从旧边缘服务器导出外部访问代理证书。 
    
2. 在 Skype for Business Server 2019 边缘服务器上，导入上一步中的访问代理外部证书。
    
3. 将访问代理外部证书分配给边缘Skype for Business Server 2019 外部接口。
    
4. 应从受信任的 CA 请求并分配 Skype for Business Server 2019 边缘服务器的内部接口证书。 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a>将以前版本的联盟路由更改为使用 Skype for Business Server 2019 边缘服务器

1. 在拓扑生成器的左窗格中，导航到 **"Skype for Business Server 2019"** 节点，然后导航到"边缘池 **"** 节点。 
    
2. 右键单击该边缘服务器，然后单击“编辑属性”。
    
3. 在左窗格中，选择“常规”。 
    
4. 选中"为此边缘池启用联盟"复选框 (**端口 5061**) "，然后单击 **"确定** "关闭页面。 
  
5. 从“操作”菜单中，选择“发布部署”，然后单击“下一步”。
    
6. “发布向导”完成时，单击“完成”关闭向导。 
    
7. 验证拓扑 **(中是否) 5061** 端口的联盟设置为已启用。
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a>更新 2019 Skype for Business Server边缘服务器联盟下一跃点

1. 在拓扑生成器的左窗格中，导航到 **"Skype for Business Server 2019"** 节点，然后导航到"边缘池 **"** 节点。 
    
2. 展开节点，右键单击列出的边缘服务器，然后单击“编辑属性”。 
    
3. 在"**常规"** 页上的"下一 **个跃** 点选择"下，从下拉列表中选择"Skype for Business Server 2019 池"。
  
4. 单击“确定”关闭“编辑属性”页。 
    
5. 从 **拓扑生成器中**，选择顶部节点 **"Skype for Business Server"。** 
    
6. 从“操作”菜单中，单击“发布拓扑”并完成向导。 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a>配置 Skype for Business Server 2019 边缘服务器出站媒体路径

1. 在拓扑生成器的左窗格中，导航到 **"Skype for Business Server 2019"** 节点，然后导航到"前端服务器"或"Standard Edition池"Enterprise Edition池 **。** 
    
2. 右键单击该池，然后单击“编辑属性”。
    
3. 在“关联”部分，选中“关联边缘池(用于媒体组件)”复选框。 
  
4. 从下拉框中，选择"Skype for Business Server 2019 边缘服务器"。
    
5. 单击“确定”关闭“编辑属性”页。 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a>启用 2019 Skype for Business Server 2019 边缘服务器联盟

1. 在拓扑生成器的左窗格中，导航到 **"Skype for Business Server 2019"** 节点，然后导航到"边缘池 **"** 节点。 
    
2. 展开节点，右键单击列出的边缘服务器，然后单击“编辑属性”。 
    
    > [!NOTE]
    > 只能为单个边缘池启用联盟。 如果具有多个边缘池，请选择一个用作联盟边缘池。 
  
3. 在" **常规"** 页上，确认已选中"为此边缘池启用联盟 **(端口 5061**) 复选框。 
  
4. 单击“确定”关闭“编辑属性”页。 
    
5. 导航到站点节点。 
    
6. 右键单击站点，然后单击“编辑属性”。
    
7. 在左窗格中，单击“联盟路由”。
    
8. 在 **"站点联盟路由分配"** 下，选择"**启用 SIP** 联盟"，然后从列表中选择列出的"Skype for Business Server 2019 边缘服务器"。 
  
9. 单击“确定”关闭“编辑属性”页。 
    
     对于多站点部署，在每个站点上完成该过程。 
    
## <a name="to-publish-edge-server-configuration-changes"></a>发布边缘服务器配置更改

1. 从 **拓扑生成器中**，选择顶部节点 **"Skype for Business Server"。** 
    
2. 从“操作”菜单中，选择“发布拓扑”并完成向导。 
    
3. 稍待片刻以便在部署中的所有池间执行 Active Directory 复制。
    
    > [!NOTE]
    > 您可能会看到以下消息：**警告：拓扑包含多个联盟边缘服务器。在迁移到产品的最新版本期间，可能会发生这种情况。在这种情况下，只有一台边缘服务器会主动用于联盟。验证外部 DNS SRV 记录是否指向正确的边缘服务器。如果要部署多个联盟边缘服务器以同时 (（而不是迁移方案) ，请验证所有联盟伙伴是否都Skype for Business Server。验证外部 DNS SRV 记录是否列出了所有启用联盟的边缘服务器。** 该警告是预期警告，可以放心地忽略。 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a>配置 Skype for Business Server 2019 边缘服务器

1. 使所有 Skype for Business Server 2019 边缘服务器联机。 
    
2. 更新外部防火墙路由规则或硬件负载平衡器设置以发送外部访问的 SIP 流量 (通常端口 443) 和联盟 (通常将 5061) 移植到 Skype for Business Server 2019 边缘服务器，而不是旧边缘服务器。
    
    > [!NOTE]
    > 如果您没有硬件负载平衡器，则需要更新联盟的 DNS A 记录，以解析为新的 Skype for Business Server 访问边缘服务器。 若要尽可能减少中断，请减小外部 Skype for Business Server 访问边缘 FQDN 的 TLL 值，以便当 DNS 更新为指向新的 Skype for Business Server 访问边缘时，联盟和远程访问将快速更新。 
  
3. 从每台 **Skype for Business Server服务器计算机** 停止访问边缘。 
    
4. 从每台旧版边缘服务器计算机中，从"管理工具"中打开 **"服务"小程序**。
    
5. 在服务列表中，找到 **"Skype for Business Server边缘"。**
    
6. 右键单击服务名称，然后选择“停止”以停止该服务。 
    
7. 将“启动”类型设置为“已禁用”。 
    
8. 单击“确定”关闭“属性”窗口。 
    

