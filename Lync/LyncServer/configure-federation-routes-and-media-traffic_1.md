---
title: 配置联合路由和媒体流量
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4542ae02cc72dfbac05dfa982e2fbda7f2924919
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837784"
---
# <a name="configure-federation-routes-and-media-traffic"></a>配置联合路由和媒体流量

 


联盟是两个或多个 SIP 域之间的信任关系, 这些 SIP 域允许单独组织中的用户通过网络边界进行通信。 在迁移到 Lync Server 2013 试验池之后, 你需要从 Microsoft Office 通信服务器 2007 R2 Edge 服务器的联合路线转换到 Lync Server 2013 Edge 服务器的联合路由。

使用下面的过程将联合路由和媒体流量路由从 Office 通信服务器 2007 R2 Edge 服务器和控制器转到 Lync Server 2013 Edge 服务器 (对于单站点部署)。


> [!IMPORTANT]  
> 更改联盟路由和媒体流量路由需要你为 Lync Server 2013 和 Office 通信服务器 2007 R2 Edge 服务器安排维护停机时间。 此整个过渡过程还意味着, 在中断期间, 联盟访问将不可用。 你应该将停机时间安排为预计最少的用户活动。 你还应向最终用户提供足够的通知。 为此停机安排相应的计划, 并在你的组织内设置适当的期望值。




> [!IMPORTANT]  
> 如果旧版 Office 通信服务器 2007 R2 Edge 服务器配置为对访问边缘服务使用相同的 FQDN, 请使用 Web 会议边缘服务和 A/V 边缘服务, 此部分中的过程可将联盟设置转换为 Lync 服务器2013 Edge 服务器不受支持。 如果将旧边缘服务配置为使用相同的 FQDN, 则必须先将 Office 通信服务器 2007 R2 中的所有用户迁移到 Lync Server 2013, 然后在启用联盟之前解除 Office 通信服务器 2007 R2 Edge 服务器Lync Server 2013 Edge 服务器。 有关详细信息，请参阅以下主题： 
> <UL>
> <LI>
> <P><A href="move-remaining-users-to-lync-server-2013_1.md">将其余用户移动到 Lync Server 2013</A></P>
> <LI>
> <P>"删除服务器和服务器角色"<A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></P></LI></UL>




> [!IMPORTANT]  
> 如果你的 XMPP 联盟通过 Lync Server 2013 Edge 服务器路由, 则旧版 Office 通信服务器 2007 R2 用户将无法与 XMPP 联盟合作伙伴通信, 直到所有用户都已移动到 Lync Server 2013、XMPP 策略和证书已配置, 已在 Lync Server 2013 上配置了 XMPP 联盟合作伙伴, 最后更新了 DNS 条目。



若要在添加或删除服务器角色时成功发布、启用或禁用拓扑, 您应作为 RTCUniversalServerAdmins 和域管理员组成员的用户登录。 也可以委派用于添加服务器角色的相应用户权限和权限。 有关详细信息, 请参阅在标准版服务器或企业版服务器部署文档中[Lync Server 2013 中的 "委派设置权限](lync-server-2013-delegate-setup-permissions.md)"。 对于其他配置更改, 仅需要 RTCUniversalServerAdmins 组中的成员身份。

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>删除 Lync Server 2013 网站中的旧联合身份验证关联

1.  使用拓扑生成器打开 "引导池" 拓扑。

2.  在左窗格中, 导航到 "网站" 节点。

3.  右键单击网站, 然后单击 "**编辑属性**"。

4.  在左窗格中选择 "**联盟路由**"。

5.  在 "网站联合路由分配" 下, 清除 "**启用 SIP 联合**" 旁边的复选框以禁用通过**BackCompatSite**的联盟路由。
    
    !["编辑属性" 对话框, "联盟" 路由](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "\"编辑属性\" 对话框, \"联盟\" 路由")

6.  单击 **"确定"** 以关闭 "编辑属性" 页面。

7.  从**拓扑生成器**中, 选择顶级节点**Lync 服务器**。

8.  从 "**操作**" 菜单中, 单击 "**发布拓扑**" 并完成向导。

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>将旧式边缘服务器配置为非联合边缘服务器

1.  从**拓扑生成器**中, 从 "**操作**" 菜单中单击 "**合并 Office 通信服务器 2007 R2 拓扑**"。

2.  单击“**下一步**”继续。

3.  在 "**指定边缘设置**" 中, 选择当前为联盟配置的**边缘服务器内部 FQDN** , 然后单击 "**更改**"。
    
    ![合并 OCS 2007 R2 拓扑, 指定边缘设置](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "合并 OCS 2007 R2 拓扑, 指定边缘设置")

4.  单击 "**下一步**", 接受默认设置, 直到到达 "**指定外部边缘**" 页面:
    
    ![拓扑生成器指定外部边缘页面](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "拓扑生成器指定外部边缘页面")

5.  在 "**指定外部边缘**" 中, 清除 "**此 Edge 池用于联盟和公用 IM 连接**" 复选框。 这将删除与 BackCompatSite 的联合身份验证关联。
    

    > [!IMPORTANT]  
    > 此步骤非常重要。 必须清除此选项才能删除旧版联合身份验证关联。



6.  单击 "**下一步**", 接受向导其余页面的默认设置。

7.  在 "**摘要**" 中, 单击 "**下一步**" 以开始合并拓扑。

8.  在 "**状态**" 列中, 验证值是否**成功**, 然后单击 "**完成**" 关闭向导。

9.  从 "**操作**" 菜单中, 选择 "**发布拓扑**", 然后单击 "**下一步**"。

10. **发布向导**完成后, 单击 "**完成**" 关闭向导。
    
    ![合并后显示网站的拓扑生成器](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "合并后显示网站的拓扑生成器")
    
    如上图所示, 在 "**站点联合路由分配**" 下找到的**SIP 联盟**设置为 "**已禁用**"。

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a>在 Lync Server 2013 Edge 服务器上配置证书

1.  从旧版 Office 通信服务器 2007 R2 Edge 服务器导出外部访问代理服务器证书和私钥。

2.  在 Lync Server 2013 Edge 服务器上, 导入上一步中的 "访问代理服务器外部证书"。

3.  将访问代理服务器外部证书分配给边缘服务器的 Lync Server 2013 外部接口。

4.  不应更改 Lync Server 2013 Edge 服务器的内部接口证书。

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a>若要将 Office 通信服务器 2007 R2 联合路由更改为使用 Lync Server 2013 Edge 服务器

1.  在 Office 通信服务器 2007 R2 标准版服务器或前端服务器上, 打开 Office 通信服务器 2007 R2 管理工具。

2.  在左窗格中, 展开顶部节点, 然后右键单击 "**林**" 节点。 选择 "**属性**", 然后单击 "**全局属性**"。

3.  单击 "**联盟**" 选项卡。

4.  选中复选框以启用联盟和公共 IM 连接。

5.  输入 Lync Server 2013 Edge 服务器的 FQDN, 然后单击 **"确定"**。
    
    ![OCS 全局属性, "联盟" 选项卡](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS 全局属性, \"联盟\" 选项卡")

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>打开 Lync Server 2013 Edge 服务器联合身份验证

1.  从拓扑生成器的左窗格中, 导航到 "Lync Server 2013 **Edge 池**" 节点。

2.  展开节点, 右键单击列出的边缘服务器, 然后单击 "**编辑属性**"。
    

    > [!NOTE]  
    > 仅可对单个边缘池启用联合身份验证。 如果你有多个边缘池, 请选择一个以用作联盟边缘池。



3.  在 "**常规**" 页面上, 选中 "**为此边缘池启用联盟 (端口 5061)** " 复选框。
    
    ![编辑属性, 常规, 启用边缘联盟](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "编辑属性, 常规, 启用边缘联盟")

4.  单击 **"确定"** 以关闭 "编辑属性" 页面。

5.  接下来, 导航到 "网站" 节点。

6.  右键单击网站, 然后单击 "**编辑属性**"。

7.  在左窗格中, 单击 "**联盟路由**"。

8.  在 "**站点联合路由分配**" 下, 选择 "**启用 SIP 联盟**", 然后从列表中选择列出的 Lync server 2013 Edge 服务器。

9.  单击 **"确定"** 以关闭 "**编辑属性**" 页面。
    
    ![编辑属性, 常规, 关联边缘池](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "编辑属性, 常规, 关联边缘池")
    
    对于多站点部署, 请在每个网站上完成此过程。

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>配置 Lync Server 2013 Edge 服务器出站媒体路径

1.  从**拓扑生成器**中, 导航到**标准版前端服务器**或**企业版前端池**下的 Lync Server 2013 池。

2.  右键单击该池, 然后单击 "**编辑属性**"。

3.  在 "**关联**" 部分中, 选择 "**关联边缘池 (适用于媒体组件)** " 复选框。

4.  从下拉框中, 选择 Lync Server 2013 Edge 服务器。
    
    !["编辑属性" 对话框, 关联边缘池](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "\"编辑属性\" 对话框, 关联边缘池")

5.  单击 **"确定"** 以关闭 "**编辑属性**" 页面。

## <a name="to-publish-edge-server-configuration-changes"></a>发布边缘服务器配置更改

1.  从**拓扑生成器**中, 选择顶级节点**Lync 服务器**。

2.  从 "**操作**" 菜单中, 选择 "**发布拓扑**" 并完成向导。

3.  等待对部署中的所有池执行 Active Directory 复制。
    

    > [!NOTE]  
    > 您可能会看到以下消息:<BR><STRONG>警告: 该拓扑包含多个联合边缘服务器。在迁移到产品的较新版本的过程中可能会发生这种情况。在这种情况下, 仅有一台边缘服务器将主动用于联盟。验证外部 DNS SRV 记录是否指向正确的边缘服务器。如果你想要将多个联合边缘服务器部署为同时活动 (即不是迁移方案), 请验证所有联盟伙伴都使用的是 Office 通信服务器 2007 R2 或 Lync Server。验证外部 DNS SRV 记录是否列出所有启用联盟的边缘服务器。</STRONG><BR>此警告是预期的, 可以安全忽略。



## <a name="to-verify-federation-and-remote-access-for-external-users"></a>验证外部用户的联盟和远程访问

1.  从 Lync Server 2013 前端服务器, 打开 Lync Server 命令行管理程序。

2.  若要验证联盟和远程访问的状态, 请从命令行键入以下命令:
    
        Get-CsAccessEdgeConfiguration

3.  若要启用联盟和远程访问, 请从命令行中键入以下内容:
    
        Set-CsAccessEdgeConfiguration
    
    有关这些 cmdlet 的详细信息, 请参阅以下主题: [CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg398574\(v=ocs.15\))和[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg413017\(v=ocs.15\))。

4.  请等待复制完成, 然后再使 Lync Server 2013 边缘服务器联机, 并测试联盟和外部访问。

## <a name="to-configure-lync-server-2013-edge-server"></a>配置 Lync Server 2013 Edge 服务器

1.  使所有 Lync Server 2013 边缘服务器联机。

2.  更新外部防火墙路由规则或硬件负载平衡器设置, 以将外部访问 (通常是端口 443) 和联盟 (通常为端口 5061) 的 SIP 流量发送到 Lync Server 2013 Edge 服务器, 而不是旧版边缘服务器。
    

    > [!NOTE]  
    > 如果你没有硬件负载平衡器, 你需要更新联合身份验证的 DNS A 记录, 以解决新的 Lync 服务器访问边缘服务器。 若要通过最小的中断完成此操作, 请减小外部 Lync Server 访问边缘 FQDN 的 TTL 值, 以便在更新 DNS 以指向新的 Lync 服务器访问边缘服务器时, 将快速更新联合身份验证和远程访问。



3.  接下来, 从每台边缘服务器计算机停止**Lync 服务器访问边缘**。

4.  从每个旧式边缘服务器计算机上, 从 "**管理工具**" 中打开 "**服务**" 小程序。

5.  在 "服务" 列表中, 找到 " **Office 通信服务器访问边缘**"。

6.  右键单击服务名称, 然后选择 "**停止**" 以停止该服务。

7.  将 "启动类型" 设置为 "**已禁用**"。

8.  单击 **"确定"** 以关闭 "**属性**" 窗口。

## <a name="to-test-connectivity-of-external-users-and-external-access"></a>测试外部用户和外部访问的连接

  - 至少一个联盟域中的用户, 即 Lync Server 2013 上的内部用户和 Office 通信服务器 2007 R2 上的用户。 测试即时消息 (IM)、状态、音频/视频 (A/V) 和桌面共享。

  - 你的组织支持的每个公共 IM 服务提供商的用户 (以及已完成的预配) 与 Lync Server 2013 上的用户和 Office 通信服务器 2007 R2 上的用户进行通信。

  - 验证匿名用户是否能够加入会议。

  - 在 Office 通信服务器 2007 R2 上使用远程用户访问 (从 intranet 外部 (但不2013使用 VPN 登录到 Office 通信服务器 2007 R2) 和 Office 通信服务器 2007 R2 上的用户的用户。 测试即时消息、状态、A/V 和桌面共享。

  - 在 lync server 2013 上托管的用户 (使用远程用户访问 (从 intranet 外部但不使用 VPN 登录到 Lync Server 2013) 与 Lync Server 2013 上的用户以及 Office 通信服务器 2007 R2 上的用户进行登录。 测试即时消息、状态、A/V 和桌面共享。

