---
title: 配置联合路由和媒体流量
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure federation routes and media traffic
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49733720
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed16ac6b8aceea6828b600ce18da8b9a72827846
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-routes-and-media-traffic"></a>配置联合路由和媒体流量

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-15_

联盟是两个或多个 SIP 域之间的信任关系, 这些 SIP 域允许单独组织中的用户通过网络边界进行通信。 在迁移到 Lync Server 2013 试验池后, 需要从 Lync Server 2010 Edge 服务器的联盟路径切换到 Lync Server 2013 Edge 服务器的联合路由。

使用以下过程可将 Lync Server 2010 Edge 服务器和控制器中的联盟路由和媒体流量路由切换到 Lync Server 2013 Edge 服务器, 以便用于单个网站部署。

<div>


> [!IMPORTANT]  
> 更改联盟路由和媒体流量路由需要你为 Lync Server 2013 和 Lync Server 2010 Edge 服务器安排维护停机时间。 此整个过渡过程还意味着, 在中断期间, 联盟访问将不可用。 你应该将停机时间安排为预计最少的用户活动。 你还应向最终用户提供足够的通知。 为此停机安排相应的计划, 并在你的组织内设置适当的期望值。



</div>

<div>


> [!IMPORTANT]  
> 如果旧版 Lync Server 2010 Edge 服务器配置为对访问边缘服务、Web 会议边缘服务和 A/V 边缘服务使用相同的 FQDN, 则不支持本部分中的过程。 如果将旧边缘服务配置为使用相同的 FQDN, 则必须首先将所有用户从 Lync Server 2010 迁移到 Lync Server 2013, 然后在 Lync Server 2013 Edge 服务器上启用联盟之前解除 Lync Server 2010 Edge 服务器。



</div>

<div>


> [!IMPORTANT]  
> 如果你的 XMPP 联盟通过 Lync Server 2013 Edge 服务器路由, 则旧版 Lync Server 2010 用户将无法与 XMPP 联盟伙伴通信, 直到所有用户都已移动到 Lync Server 2013、XMPP 策略和证书已已配置, 已在 Lync Server 2013 上配置了 XMPP 联盟合作伙伴, 最后更新了 DNS 条目。



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>删除 Lync Server 2013 网站中的旧联合身份验证关联

1.  在 Lync Server 2013 前端服务器上, 在拓扑生成器中打开现有拓扑。

2.  在左窗格中, 导航到位于 " **Lync 服务器**" 正下方的 "网站" 节点。

3.  右键单击网站, 然后单击 "**编辑属性**"。

4.  在左窗格中, 选择 "**联盟路由**"。

5.  在 "**网站联合路由分配**" 下, 清除 "**启用 SIP 联盟**" 复选框以通过旧版 Lync Server 2010 环境禁用联盟路由。
    
    !["编辑属性" 对话框, "联盟路由" 页面](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "\"编辑属性\" 对话框, \"联盟路由\" 页面")

6.  单击 **"确定"** 以关闭 "编辑属性" 页面。

7.  从**拓扑生成器**中, 选择顶级节点**Lync 服务器**。

8.  从 "**操作**" 菜单中, 单击 "**发布拓扑**"。

9.  单击 "**下一步**" 完成发布过程, 然后在发布过程完成时单击 "**完成**"。

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>将旧式边缘服务器配置为非联合边缘服务器

1.  在左窗格中, 导航到**Lync Server 2010**节点, 然后导航到 "**边缘池**" 节点。

2.  右键单击边缘服务器, 然后单击 "**编辑属性**"。

3.  在左窗格中选择 "**常规**"。

4.  清除 "**为此 Edge 池启用联盟 (端口 5061)** " 复选框条目, 然后选择 **"确定"** 关闭页面。
    
    ![编辑属性, 常规, 清除启用联盟](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "编辑属性, 常规, 清除启用联盟")

5.  从 "**操作**" 菜单中, 选择 "**发布拓扑**", 然后单击 "**下一步**"。

6.  **发布向导**完成后, 单击 "**完成**" 关闭向导。

7.  验证旧版 Edge 服务器的联盟是否已禁用。
    
    ![拓扑生成器, Edge 池, 已禁用联合身份验证](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "拓扑生成器, Edge 池, 已禁用联合身份验证")

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a>在 Lync Server 2010 Edge 服务器上配置证书

1.  从旧版 Lync Server 2010 Edge 服务器导出外部访问代理服务器证书以及私钥。

2.  在 Lync Server 2013 Edge 服务器上, 导入上一步中的 "访问代理服务器外部证书"。

3.  将访问代理服务器外部证书分配给边缘服务器的 Lync Server 2013 外部接口。

4.  Lync Server 2013 Edge 服务器的内部界面证书应由受信任的 CA 请求并被分配。

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a>将 Lync Server 2010 联盟路由更改为使用 Lync Server 2013 Edge 服务器

1.  从拓扑生成器的左窗格中, 导航到**Lync Server 2013**节点, 然后导航到 "**边缘池**" 节点。

2.  右键单击边缘服务器, 然后单击 "**编辑属性**"。

3.  在左窗格中选择 "**常规**"。

4.  选中 "为**此 Edge 池启用联盟 (端口 5061)** " 复选框条目, 然后单击 **"确定"** 关闭页面。
    
    !["编辑属性" 对话框, "常规" 页面](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "\"编辑属性\" 对话框, \"常规\" 页面")

5.  从 "**操作**" 菜单中, 选择 "**发布拓扑**", 然后单击 "**下一步**"。

6.  **发布向导**完成后, 单击 "**完成**" 关闭向导。

7.  验证**联盟 (端口 5061)** 是否设置为 "**已启用**"。
    
    ![拓扑生成器、Edge 池、已启用联盟](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "拓扑生成器、Edge 池、已启用联盟")

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a>更新 Lync Server 2013 Edge 服务器联合身份验证下一跃点

1.  从拓扑生成器的左窗格中, 导航到**Lync Server 2013**节点, 然后导航到 "**边缘池**" 节点。

2.  展开节点, 右键单击列出的边缘服务器, 然后单击 "**编辑属性**"。

3.  在 "**常规**" 页面上的 "**下一跃点选择**" 下, 从下拉列表中选择 "Lync Server 2013 池"。
    
    !["编辑属性" 对话框, "下一跃点" 页面](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "\"编辑属性\" 对话框, \"下一跃点\" 页面")

4.  单击 **"确定"** 以关闭 "编辑属性" 页面。

5.  从**拓扑生成器**中, 选择顶级节点**Lync 服务器**。

6.  从 "**操作**" 菜单中, 单击 "**发布拓扑**" 并完成向导。

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>配置 Lync Server 2013 Edge 服务器出站媒体路径

1.  从拓扑生成器的左窗格中, 导航到**Lync Server 2013**节点, 然后导航到**标准版前端服务器**或**企业版前端池**下的池。

2.  右键单击该池, 然后单击 "**编辑属性**"。

3.  在 "**关联**" 部分中, 选择 "**关联边缘池 (适用于媒体组件)** " 复选框。
    
    ![编辑属性, 常规, 关联边缘池](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "编辑属性, 常规, 关联边缘池")

4.  从下拉框中, 选择 Lync Server 2013 Edge 服务器。

5.  单击 **"确定"** 以关闭 "**编辑属性**" 页面。

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>打开 Lync Server 2013 Edge 服务器联合身份验证

1.  从拓扑生成器的左窗格中, 导航到**Lync Server 2013**节点, 然后导航到 "**边缘池**" 节点。

2.  展开节点, 右键单击列出的边缘服务器, 然后单击 "**编辑属性**"。
    
    <div>
    

    > [!NOTE]  
    > 仅可对单个边缘池启用联合身份验证。 如果你有多个边缘池, 请选择一个以用作联盟边缘池。

    
    </div>

3.  在 "**常规**" 页面上, 验证 "为**此 Edge 池启用联盟 (端口 5061)** " 设置是否已选中。
    
    !["编辑属性" 对话框, "常规" 页面](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "\"编辑属性\" 对话框, \"常规\" 页面")

4.  单击 **"确定"** 以关闭 "编辑属性" 页面。

5.  接下来, 导航到 "网站" 节点。

6.  右键单击网站, 然后单击 "**编辑属性**"。

7.  在左窗格中, 单击 "**联盟路由**"。

8.  在 "**站点联合路由分配**" 下, 选择 "**启用 SIP 联盟**", 然后从列表中选择列出的 Lync server 2013 Edge 服务器。
    
    !["编辑属性"、"联盟路由" 页面](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "\"编辑属性\"、\"联盟路由\" 页面")

9.  单击 **"确定"** 以关闭 "**编辑属性**" 页面。
    
    对于多站点部署, 请在每个网站上完成此过程。

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a>发布边缘服务器配置更改

1.  从**拓扑生成器**中, 选择顶级节点**Lync 服务器**。

2.  从 "**操作**" 菜单中, 选择 "**发布拓扑**" 并完成向导。

3.  等待对部署中的所有池执行 Active Directory 复制。
    
    <div>
    

    > [!NOTE]  
    > 您可能会看到以下消息:<BR><STRONG>警告: 该拓扑包含多个联合边缘服务器。在迁移到产品的较新版本的过程中可能会发生这种情况。在这种情况下, 仅有一台边缘服务器将主动用于联盟。验证外部 DNS SRV 记录是否指向正确的边缘服务器。如果要将多个联合边缘服务器部署为同时活动 (即不是迁移方案), 请验证所有联盟伙伴是否都在使用 Lync Server。验证外部 DNS SRV 记录是否列出所有启用联盟的边缘服务器。</STRONG><BR>此警告是预期的, 可以安全忽略。

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a>配置 Lync Server 2013 Edge 服务器

1.  使所有 Lync Server 2013 边缘服务器联机。

2.  更新外部防火墙路由规则或硬件负载平衡器设置, 以将外部访问 (通常是端口 443) 和联盟 (通常为端口 5061) 的 SIP 流量发送到 Lync Server 2013 Edge 服务器, 而不是旧版边缘服务器。
    
    <div>
    

    > [!NOTE]  
    > 如果你没有硬件负载平衡器, 你需要更新联合身份验证的 DNS A 记录, 以解析到新的 Lync 服务器访问边缘服务器。 若要通过最小的中断完成此操作, 请减小外部 Lync Server 访问边缘 FQDN 的 TLL 值, 以便在更新 DNS 以指向新的 Lync 服务器访问边缘时, 将快速更新联合身份验证和远程访问。

    
    </div>

3.  接下来, 从每台边缘服务器计算机停止**Lync 服务器访问边缘**。

4.  从每个旧式边缘服务器计算机上, 从 "**管理工具**" 中打开 "**服务**" 小程序。

5.  在 "服务" 列表中, 找到 " **Lync Server Access Edge**"。

6.  右键单击服务名称, 然后选择 "**停止**" 以停止该服务。

7.  将 "启动类型" 设置为 "**已禁用**"。

8.  单击 **"确定"** 以关闭 "**属性**" 窗口。

</div>

</div>

<span> </span>

</div>

</div>

</div>

