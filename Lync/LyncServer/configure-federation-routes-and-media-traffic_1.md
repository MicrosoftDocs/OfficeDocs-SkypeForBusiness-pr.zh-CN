---
title: 配置联盟路由和媒体流量
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d6af77188809b092050629c1b74cdab8b20a2cc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754958"
---
# <a name="configure-federation-routes-and-media-traffic"></a>配置联盟路由和媒体流量

 


联盟是两个或更多 SIP 域之间的一种信任关系，它允许不同组织中的用户跨越网络边界进行通信。 在迁移到 Lync Server 2013 引导池之后，需要从 Microsoft Office 通信服务器 2007 R2 边缘服务器的联合路由转换为 Lync Server 2013 边缘服务器的联合路由。

使用以下过程将联合路由和媒体流量路由从 Office 通信服务器 2007 R2 边缘服务器和控制器转换为 Lync Server 2013 边缘服务器，以实现单站点部署。


> [!IMPORTANT]  
> 若要更改联合路由和媒体流量路由，需要为 Lync Server 2013 和 Office 通信服务器 2007 R2 边缘服务器安排维护停机时间。 整个转换过程还意味着服务中断期间无法进行联盟访问。 应将停机时间安排在预计用户活动最少的时间段内。 还应向最终用户提供包含丰富信息的通知。 相应地规划这次服务中断并正确设置组织的期望。




> [!IMPORTANT]  
> 如果您的旧版 Office 通信服务器 2007 R2 边缘服务器配置为对访问边缘服务、Web 会议边缘服务和 A/V 边缘服务使用相同的 FQDN，则不支持此部分中的过程将联合身份验证设置转换为 Lync Server 2013 边缘服务器。 如果将旧边缘服务配置为使用相同的 FQDN，则必须首先将所有用户从 Office 通信服务器 2007 R2 迁移到 Lync Server 2013，然后在 Lync Server 2013 边缘服务器上启用联合之前，先停止 Office 通信服务器 2007 R2 边缘服务器。 有关详细信息，请参阅下列主题： 
> <UL>
> <LI>
> <P><A href="move-remaining-users-to-lync-server-2013_1.md">将其余用户移动到 Lync Server 2013</A></P>
> <LI>
> <P>"删除服务器和服务器角色"<A href="https://go.microsoft.com/fwlink/p/?linkid=268790">https://go.microsoft.com/fwlink/p/?LinkId=268790</A></P></LI></UL>




> [!IMPORTANT]  
> 如果您的 XMPP 联盟通过 Lync Server 2013 边缘服务器路由，则旧版 Office 通信服务器 2007 R2 用户将无法与 XMPP 联盟伙伴通信，直到所有用户都已移动到 Lync Server 2013、已配置 XMPP 策略和证书、已在 Lync Server 2013 上配置了 XMPP 联盟伙伴，最后更新了 DNS 条目。



若要在添加或删除服务器角色时成功发布、启用或禁用拓扑，应以 RTCUniversalServerAdmins 和 Domain Admins 组成员的用户身份登录。 还可以委派用于添加服务器角色的相应用户权限。 有关详细信息，请参阅 Standard Edition server 或 Enterprise Edition server Deployment 文档中的 "[在 Lync Server 2013 中委派安装程序权限](lync-server-2013-delegate-setup-permissions.md)"。 对于其他配置更改，只需要 RTCUniversalServerAdmins 组的成员身份。

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>将旧联盟关联从 Lync Server 2013 站点中删除

1.  使用拓扑生成器打开试点池拓扑。

2.  在左窗格中，导航到站点节点。

3.  右键单击站点，然后单击“编辑属性”****。

4.  在左窗格中，选择“联盟路由”****。

5.  在“站点联盟路由分配”下，清除“启用 SIP 联盟”**** 旁边的复选框以通过“BackCompatSite”**** 禁用联盟路由。
    
    !["编辑属性" 对话框（联合路由）](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg ""编辑属性" 对话框（联合路由）")

6.  单击“确定”**** 关闭“编辑属性”页。

7.  从“拓扑生成器”**** 中，选择顶部节点“Lync Server”****。

8.  从“操作”**** 菜单中，单击“发布拓扑”**** 并完成向导。

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>将旧边缘服务器配置为非联盟边缘服务器

1.  从“拓扑生成器”**** 的“操作”**** 菜单中，单击“合并 Office Communications Server 2007 R2 拓扑”****。

2.  单击“下一步”**** 继续。

3.  在“指定边缘设置”**** 上，选择当前为联盟配置的“边缘服务器内部 FQDN”****，然后单击“更改”****。
    
    ![合并 OCS 2007 R2 拓扑，指定边缘设置](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "合并 OCS 2007 R2 拓扑，指定边缘设置")

4.  单击“下一步”**** 并接受默认设置，直到显示“指定外部边缘”**** 页：
    
    ![拓扑生成器指定外部边缘页面](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "拓扑生成器指定外部边缘页面")

5.  在“指定外部边缘”**** 中，清除“此边缘池用于联盟和公共 IM 连接”**** 复选框。这将删除与 BackCompatSite 的联盟关联。
    

    > [!IMPORTANT]  
    > 此步骤非常重要。必须清除该选项才能删除旧联盟关联。



6.  单击“下一步”**** 并接受向导其余页面的默认设置。

7.  在“摘要”**** 中，单击“下一步”**** 开始合并拓扑。

8.  在 "**状态**" 列中，验证值是否为 "**成功**"，然后单击 "**完成**" 以关闭向导。

9.  从“操作”**** 菜单中，选择“发布部署”****，然后单击“下一步”****。

10. “发布向导”**** 完成时，单击“完成”**** 关闭向导。
    
    ![在合并后显示网站的拓扑生成器](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "在合并后显示网站的拓扑生成器")
    
    如在上图中所示，将位于**站点联盟路由分配**下的 **SIP 联盟**设置为**已禁用**。

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a>在 Lync Server 2013 边缘服务器上配置证书

1.  从旧版 Office 通信服务器 2007 R2 边缘服务器导出外部访问代理证书和私钥。

2.  在 Lync Server 2013 边缘服务器上，导入上一步中的 "访问代理外部证书"。

3.  将访问代理外部证书分配给边缘服务器的 Lync Server 2013 外部接口。

4.  不应更改 Lync Server 2013 边缘服务器的内部接口证书。

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a>将 Office Communications Server 2007 R2 联盟路由更改为使用 Lync Server 2013 边缘服务器

1.  在 Office 通信服务器 2007 R2 Standard Edition server 或前端服务器上，打开 Office 通信服务器 2007 R2 管理工具。

2.  在左窗格中，展开顶层节点，然后右键单击“林”**** 节点。选择“属性”****，然后单击“全局属性”****。

3.  单击“联盟”**** 选项卡。

4.  选中用于启用联盟和公共 IM 连接的复选框。

5.  输入 Lync Server 2013 边缘服务器的 FQDN，然后单击 **"确定"**。
    
    ![OCS 全局属性（联合选项卡）](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS 全局属性（联合选项卡）")

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>启用 Lync Server 2013 边缘服务器联盟

1.  从拓扑生成器的左侧窗格中，导航到 "Lync Server 2013 **Edge 池**" 节点。

2.  展开节点，右键单击列出的边缘服务器，然后单击“编辑属性”****。
    

    > [!NOTE]  
    > 仅可为单个边缘池启用联合身份验证。 如果具有多个边缘池，请选择一个用作联盟边缘池。



3.  在“常规”**** 页上，选中“为此边缘池启用联盟(端口 5061)”**** 复选框。
    
    ![编辑属性，常规，启用边缘联盟](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "编辑属性，常规，启用边缘联盟")

4.  单击“确定”**** 关闭“编辑属性”页。

5.  接下来，导航到站点节点。

6.  右键单击站点，然后单击“编辑属性”****。

7.  在左窗格中，单击“联盟路由”****。

8.  在 "**站点联合路由分配**" 下，选择 "**启用 SIP 联盟**"，然后从列表中选择列出的 Lync server 2013 边缘服务器。

9.  单击“确定”**** 关闭“编辑属性”**** 页。
    
    ![编辑属性，常规，关联边缘池](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "编辑属性，常规，关联边缘池")
    
    对于多站点部署，在每个站点上完成该过程。

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>配置 Lync Server 2013 边缘服务器出站媒体路径

1.  从**拓扑生成器**中，导航到 "Lync Server 2013 池" （位于**Standard edition 前端服务器**或**Enterprise edition 前端池的后面**）。

2.  右键单击该池，然后单击“编辑属性”****。

3.  在“关联”**** 部分，选中“关联边缘池(用于媒体组件)”**** 复选框。

4.  从下拉框中，选择 "Lync Server 2013 边缘服务器"。
    
    !["编辑属性" 对话框，关联边缘池](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg ""编辑属性" 对话框，关联边缘池")

5.  单击“确定”**** 关闭“编辑属性”**** 页。

## <a name="to-publish-edge-server-configuration-changes"></a>发布边缘服务器配置更改

1.  从“拓扑生成器”**** 中，选择顶层节点“Lync Server”****。

2.  从“操作”**** 菜单中，选择“发布拓扑”**** 并完成向导。

3.  稍待片刻以便在部署中的所有池间执行 Active Directory 复制。
    

    > [!NOTE]  
    > 您可能会看到以下消息：<BR><STRONG>警告: 拓扑包含多个联盟边缘服务器。在迁移到产品的更高版本时，可能会出现这种情况。在这种情况下，只有一个边缘服务器处于活动状态以用于联盟。请确保外部 DNS SRV 记录指向正确的边缘服务器。如果要将多个联盟边缘服务器部署为同时处于活动状态(非迁移情况下)，请确保所有联盟伙伴都在使用 Office Communications Server 2007 R2 或 Lync Server，并确保外部 DNS SRV 记录列出了所有已启用联盟的边缘服务器。</STRONG><BR>该警告是预期警告，可以放心地忽略。



## <a name="to-verify-federation-and-remote-access-for-external-users"></a>验证联盟和外部用户的远程访问

1.  在 Lync Server 2013 前端服务器中，打开 Lync Server 命令行管理程序。

2.  要验证联盟和远程访问的状态，请从命令行，键入以下内容：
    
        Get-CsAccessEdgeConfiguration

3.  要启用联盟和远程访问，请从命令行，键入以下内容：
    
        Set-CsAccessEdgeConfiguration
    
    有关这些 cmdlet 的详细信息，请参阅下列主题： [set-csaccessedgeconfiguration](https://technet.microsoft.com/library/gg398574\(v=ocs.15\))和[set-csaccessedgeconfiguration](https://technet.microsoft.com/library/gg413017\(v=ocs.15\))。

4.  等到复制完成之后再将 Lync Server 2013 边缘服务器联机，并测试联盟和外部访问。

## <a name="to-configure-lync-server-2013-edge-server"></a>配置 Lync Server 2013 边缘服务器

1.  使所有 Lync Server 2013 边缘服务器联机。

2.  更新外部防火墙路由规则或硬件负载平衡器设置以将外部访问的 SIP 通信（通常是端口443）和联合身份验证（通常是端口5061）发送到 Lync Server 2013 边缘服务器，而不是旧边缘服务器。
    

    > [!NOTE]  
    > 如果您没有硬件负载平衡器，则需要更新联盟的 DNS A 记录来解决新的 Lync Server 访问边缘服务器。要以最少的中断完成此操作，请减少外部 Lync Server Access Edge FQDN 的 TTL 值，以便更新 DNS 来指向新 Lync Server 访问边缘服务器时，将迅速更新联盟和远程访问。



3.  接下来，从每台边缘服务器计算机停止**Lync Server 访问边缘**。

4.  从每个旧边缘服务器计算机上，从 "**管理工具**" 中打开 "**服务**" 小程序。

5.  在服务列表中，找到“Office Communications Server 访问边缘”****。

6.  右键单击服务名称，然后选择“停止”**** 以停止该服务。

7.  将“启动”类型设置为“已禁用”****。

8.  单击“确定”**** 关闭“属性”**** 窗口。

## <a name="to-test-connectivity-of-external-users-and-external-access"></a>测试外部用户和外部访问的连接

  - 至少来自一个联盟域（Lync Server 2013 上的内部用户和 Office 通信服务器 2007 R2 上的用户）的用户。 测试即时消息 (IM)、状态、音频/视频 (A/V) 和桌面共享。

  - 您的组织支持的每个公共 IM 服务提供商的用户（和已完成的设置）与 Lync Server 2013 上的用户和 Office 通信服务器 2007 R2 上的用户进行通信。

  - 验证匿名用户是否能够加入会议。

  - 在 Office 通信服务器 2007 R2 上使用远程用户访问（从 intranet 外部（但不使用 VPN 登录到 Office 通信服务器 2007 R2），并在 Lync Server 2013 上的用户和 Office 通信服务器 2007 R2 上的用户进行登录的用户。 测试 IM、状态、A/V 和桌面共享。

  - 在 lync server 2013 上托管的用户（使用远程用户访问（从 intranet 外部，但不使用 VPN 登录到 Lync Server 2013）与 Lync Server 2013 上的用户以及 Office 通信服务器 2007 R2 上的用户。 测试 IM、状态、A/V 和桌面共享。

