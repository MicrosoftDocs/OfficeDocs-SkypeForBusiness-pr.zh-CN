---
title: Lync Server 2013：为单个内部池配置 web 发布规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web publishing rules for a single internal pool
ms:assetid: 86ff4b2a-1ba9-46a2-a175-8b19e00a49dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429712(v=OCS.15)
ms:contentKeyID: 48184725
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d87e0096ee71fb08da396188d419e918f66e125
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-publishing-rules-for-a-single-internal-pool-in-lync-server-2013"></a>在 Lync Server 2013 中为单个内部池配置 web 发布规则

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-07-07_

Microsoft Forefront 威胁管理网关2010和 Internet Information Server 应用程序请求路由（IIS ARR）使用 web 发布规则将内部资源（如会议 URL）发布到 Internet 上的用户。

除了虚拟目录的 Web 服务 Url 之外，还必须为简单 Url、Lyncdiscover. URL 和 Office Web Apps Server 创建发布规则。 对于每个简单 URL，必须在指向该简单 URL 的反向代理上创建单个规则。

如果您部署移动功能并使用自动发现，则需要为外部自动发现服务 URL 创建发布规则。 自动发现还需要用于您的控制器池和前端池的外部 Lync Server Web 服务 URL 的发布规则。 有关创建用于自动发现的 web 发布规则的详细信息，请参阅[在 Lync Server 2013 中配置反向代理以实现移动性](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)。

使用以下过程创建 Web 发布规则。

<div>


> [!NOTE]  
> 这些过程假定您已安装了标准版 Forefront 威胁管理网关（TMG）2010或已使用应用程序请求路由（IIS ARR）扩展安装并配置了 Internet Information Server。 您使用的是 TMG 或 IIS ARR。



</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-tmg-2010"></a>在运行 TMG 2010 的计算机上创建 Web 服务器发布规则

1.  单击“开始”****，依次选择“程序”****、“Microsoft Forefront TMG”****，然后单击“Forefront TMG 管理”****。

2.  在左窗格中展开“服务器名称”****，右键单击“防火墙策略”****，选择“新建”****，然后单击“网站发布规则”****。

3.  在“欢迎使用新建 Web 发布规则向导”**** 页上，为发布规则键入一个显示名称（例如，LyncServerWebDownloadsRule）。

4.  在“选择规则操作”**** 页上，选择“允许”****。

5.  在“发布类型”**** 页上，选择“发布单个网站或负载平衡器”****。

6.  在“服务器连接安全性”**** 页上，选择“使用 SSL 连接到发布的 Web 服务器或服务器场”****。

7.  在“内部发布详细信息”**** 页的“内部站点名称”**** 框中，键入承载会议内容和通讯簿内容的内部 Web 场的完全限定域名 (FQDN)。
    
    <div>
    

    > [!NOTE]  
    > 如果内部服务器是 Standard Edition Server，则此 FQDN 为 Standard Edition Server 的 FQDN。 如果内部服务器是前端池，则此 FQDN 是用于平衡内部 Web 场服务器负载的硬件负载平衡器虚拟 IP (VIP)。 TMG 服务器必须能够将 FQDN 解析为内部 Web 服务器的 IP 地址。 如果 TMG 服务器无法将 FQDN 解析为正确的 IP 地址，则可以选择 "<STRONG>使用计算机名称或 ip 地址连接到已发布的服务器</STRONG>"，然后在 "<STRONG>计算机名称或</STRONG> <STRONG>ip 地址</STRONG>" 框中，键入内部 web 服务器的 IP 地址。 如果这样做，则必须确保在 TMG 服务器上打开端口 53，且 TMG 服务器可以访问位于外围网络中的 DNS 服务器。 还可以使用本地主机文件中的条目提供名称解析。

    
    </div>

8.  在 "**内部发布详细信息**" 页上的 "**路径（可选）** " ** / **框中，键入为要发布的文件夹的路径。
    
    <div>
    

    > [!NOTE]  
    > 在网站发布向导中，只能指定一个路径。可以通过修改规则的属性来添加其他路径。

    
    </div>

9.  在“发布名称详细信息”**** 页上，确认在“接受请求”**** 下选择“此域名”****，在“公共名称”**** 框中键入外部 Web 服务的 FQDN。

10. 在“选择 Web 侦听器”**** 页上单击“新建”****，以打开“新建 Web 侦听器定义向导”。

11. 在“欢迎使用新建 Web 侦听器向导”**** 页上的“Web 侦听器名称”**** 框中为 Web 侦听器键入一个名称（例如 LyncServerWebServers）。

12. 在“客户端连接安全性”**** 页上，选择“需要与客户端建立 SSL 安全连接”****。

13. 在“Web 侦听器 IP 地址”**** 页上，选择“外部”****，然后单击“选择 IP 地址”****。

14. 在“外部侦听器 IP 选择”**** 页上，选择“所选网络中 Forefront TMG 计算机上指定的 IP 地址”****，选择适当的 IP 地址，然后单击“添加”****。

15. 在“侦听器 SSL 证书”**** 页上，选择“为每个 IP 地址分配一个证书”****，选择与外部 Web FQDN 关联的 IP 地址，然后单击“选择证书”****。

16. 在“选择证书”**** 页上，选择与在步骤 9 中指定的公共名称相匹配的证书，然后单击“选择”****。

17. 在“身份验证设置”**** 页上，选择“无身份验证”****。

18. 在“单一登录设置”**** 页上，单击“下一步”****。

19. 在“正在完成 Web 侦听器向导”**** 页上，确认“Web 侦听器”**** 设置正确，然后单击“完成”****。

20. 在“身份验证委派”**** 页上，选择“无委派，但是客户端可以直接进行身份验证”****。

21. 在“用户集”**** 页上，单击“下一步”****。

22. 在“正在完成新建 Web 发布规则向导”**** 页上，确认 Web 发布规则设置正确，然后单击“完成”****。

23. 在详细信息窗格中，单击“应用”****，以保存所做的更改并更新配置。

</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-iis-arr"></a>在运行 IIS ARR 的计算机上创建 web 服务器发布规则

1.  将用于反向代理的证书绑定到 HTTPS 协议。 单击 "**开始**"，选择 "**程序**"，选择 "**管理工具**"，然后单击 " **Internet 信息服务（IIS）管理器**"。
    
    <div>
    

    > [!NOTE]  
    > 有关部署和配置 IIS ARR 的其他帮助、屏幕截图和指南，请参阅<A href="http://go.microsoft.com/fwlink/?linkid=293391">使用 IIS arr 作为 Lync Server 2013 反向代理</A>的 NextHop 文章。

    
    </div>

2.  如果尚未执行此操作，请导入将用于反向代理的证书。 在**Internet Information Services （IIS）管理器**中，单击控制台左侧大小的反向代理服务器名称。 在位于控制台中间的**IIS**中，找到 "**服务器证书**"。 右键单击 "**服务器证书**"，然后选择 "**打开功能**"。

3.  在控制台的右侧，单击 "**导入 ...**"。 键入扩展名为的证书的路径和文件名，或单击 "" **...** 浏览证书。 选择证书，然后单击 "**打开**"。 提供用于保护私钥的密码（如果您在导出证书和私钥时分配了密码）。 单击“确定”。 如果证书导入成功，则证书将作为 "**服务器证书**" 中的条目显示在控制台的中间。

4.  分配用于 HTTPS 的证书。 在控制台的左侧，选择 "IIS 服务器" 的 "**默认网站**"。 单击右侧的 "**绑定 ...**"。 在 "**网站绑定**" 对话框中，单击 "**添加 ...**"。 在 "**类型：**" 下的 "**添加网站绑定**" 对话框中，选择 " **https**"。 选择 "https" 将允许您选择用于 https 的证书。 在 " **SSL 证书：**" 下，选择为反向代理导入的证书。 单击“确定”。 然后，单击 "**关闭**"。 证书现已绑定到安全套接字层（SSL）和传输层安全性（TLS）的反向代理。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您在关闭中间证书缺少的绑定对话框时收到警告，则需要查找并导入公用 CA 根证书颁发机构证书和任何中间 CA 证书。 请参阅从请求证书的公用 CA 处的说明，并按照说明请求和导入证书链。 如果从边缘服务器导出证书，则可以导出根 CA 证书和与边缘服务器关联的任何中间 CA 证书。 将根 CA 证书导入到计算机的受信任的根证书颁发机构存储和中间证书的计算机中（不要与用户存储混淆）。

    
    </div>

5.  在位于 IIS 服务器名称下方的控制台的左侧，右键单击 "**服务器场**"，然后单击 "**创建服务器场 ...**"。
    
    <div>
    

    > [!NOTE]  
    > 如果看不到 "<STRONG>服务器场</STRONG>" 节点，则需要安装应用程序请求路由。 有关详细信息，请参阅为<A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Lync Server 2013 设置反向代理服务器</A>。

    
    </div>
    
    在 "**服务器场名称**" 中的 "**创建服务器场**" 对话框中，为第一个 URL 键入一个名称（可以是标识目的的友好名称）。 单击“**下一步**”。

6.  在 "**服务器地址**" 中的 "**添加服务器**" 对话框中，键入前端服务器上的外部 web 服务的完全限定域名（FQDN）。 在此处用于示例目的的名称与在 Lync Server 2013 的反向代理的 "[证书摘要-反向代理](lync-server-2013-certificate-summary-reverse-proxy.md)" 的 "规划" 部分中使用的名称相同。 若要参考反向代理规划，请键入 FQDN `webext.contoso.com`。 确认 "**联机**" 旁边的复选框处于选中状态。 单击 "**添加**" 将服务器添加到此配置的 web 服务器池。
    
    <div>
    

    > [!WARNING]  
    > Lync Server 使用硬件负载平衡器来池控制器和前端服务器的 HTTP 和 HTTPS 流量。 仅在将服务器添加到 IIS ARR 服务器场时，才提供一个 FQDN。 FQDN 将是前端服务器或非池服务器配置中的控制器，或者是为服务器池配置的硬件负载平衡器的 FQDN。 对 HTTP 和 HTTPS 流量进行负载平衡的唯一受支持方法是使用硬件负载平衡器。

    
    </div>

7.  在 "**添加服务器**" 对话框中，单击 "**高级设置 ...**"。 这将打开一个对话框，用于定义对已配置的 FQDN 的请求的应用程序请求路由。 目的是在 IIS ARR 处理请求时重新定义要使用的端口。
    
    默认情况下，目标 HTTP 端口必须定义为8080。 单击当前**httpPort 80**的 "下一步"，并将值设置为**8080**。 单击当前**httpsPort 443**的 "下一步"，并将值设置为**4443**。 将**加权**参数保留在100。 如果需要，您可以在有基准统计信息之后重新定义给定规则的权重。 单击 "**完成**" 以完成规则配置的此部分。

8.  您可能会看到对话框重写规则，通知您 IIS 管理器可以创建 URL 重写规则，以自动将所有传入请求路由到服务器场。 单击“是”****。 您将手动调整这些规则，但选择 "是" 将设置初始配置。。

9.  单击刚创建的服务器场的名称。 在 IIS 管理器的 "功能" 视图中的 "**服务器场**" 下，双击 "**缓存**"。 取消选择 "**启用磁盘缓存**"。 单击右侧的 "**应用**"。

10. 单击服务器场的名称。 在 IIS 管理器的 "功能" 视图中的 "**服务器场**" 下，双击 "**代理**"。 在 "代理设置" 页上，将 "**超时（秒）** " 的值更改为适合您的部署的值。 单击 "**应用**" 以保存更改。
    
    <div>
    

    > [!IMPORTANT]  
    > 代理超时值是一个数字，该数字将因部署而异。 您应监视您的部署并修改客户端的最佳体验的价值。 您可以将值设置为低达200。 如果您在您的环境中支持 Lync 移动客户端，则应将此值设置为960，以允许从具有超时值为900的 Office 365 中推送通知超时。 很可能需要增加超时值，以避免在值太低时断开客户端连接，或者在客户端断开连接后，如果通过代理连接不会断开连接，则减小数字。 监视和基本排列环境的正常之处是确定此值的正确设置的唯一准确方法。

    
    </div>

11. 单击服务器场的名称。 在 IIS 管理器的 "功能" 视图中的 "**服务器场**" 下，双击 "**路由规则**"。 在 "路由" 下的 "路由规则" 对话框中，清除 "启用 SSL 卸载" 旁边的复选框。 如果清除复选框的功能不可用，请选中 "**使用 URL 重写检查传入的请求**" 复选框。 单击 "**应用**" 以保存所做的更改。
    
    <div>
    

    > [!WARNING]  
    > 不支持反向代理的 SSL 卸载。

    
    </div>

12. 对每个必须通过反向代理传递的 URL 重复步骤5-11。 常见的列表如下所示：
    
      - 前端服务器 Web 服务外部： webext.contoso.com （已通过初始浏览配置）
    
      - Director 的外部 Web 服务控制器： webdirext.contoso.com （在部署控制器时为可选）
    
      - 简单 URL 匹配： meet.contoso.com
    
      - 简单 URL 拨入： dialin.contoso.com
    
      - Lync 自动发现 URL： lyncdiscover.contoso.com
    
      - Office Web Apps Server URL： officewebapps01.contoso.com
        
        <div>
        

        > [!IMPORTANT]  
        > Office Web Apps Server 的 URL 将使用不同的 httpsPort 地址。 在步骤7中，将<STRONG>httpsPort</STRONG>定义为<STRONG>443</STRONG> ，将<STRONG>httpPort</STRONG>定义为端口<STRONG>80</STRONG>。 所有其他配置设置都是相同的。

        
        </div>

13. 在控制台的左侧，单击 IIS 服务器名称。 在控制台的中间，查找 " **IIS**" 下的 " **URL 重写**"。 双击 "URL 重写" 以打开 URL 重写规则配置。 您应该会看到您在前面步骤中创建的每个服务器场的规则。 如果不执行此操作，请确认是否在 Internet Information Server Manager 控制台中的 "**起始页**" 节点正下方单击了**IIS 服务器**名称。

14. 在 " **URL 重写**" 对话框中，使用 webext.contoso.com 作为示例，显示的规则的完整名称为**ARR\_webext.contoso.com\_loadbalance\_SSL**。
    
      - 双击该规则以打开 "**编辑入站规则**" 对话框。
    
      - 单击 "**添加 ...** " 在 "**条件**" 对话框中。
    
      - 在 "**条件输入：** 类型**\_{HTTP 主机}**" 中的 "**添加条件**"。 （在键入时，将显示一个对话框，让您选择条件）。 在 "**检查输入字符串：** 选择**匹配模式"** 下。 在**模式输入**类型**\*** 中。 应选择 "**忽略大小写**"。 单击“确定”。
    
      - 在 "**编辑入站规则**" 对话框中向下滚动以找到 "**操作**" 对话框。 **操作类型：** 应设置为**路由到服务器场**，**图式：** 设置为**https://**， **SERVER Farm：** 设置为应用此规则的 URL。 对于此示例，应将其设置为**webext.contoso.com**。 **路径：** 设置为 **/{R： 0}**
    
      - 单击 "**应用**" 以保存所做的更改。 单击 "**返回到规则**" 以返回到 URL 重写规则。

15. 对您定义的每个 SSL 重写规则（每个服务器场 URL 一个）重复步骤14中定义的过程。
    
    <div>
    

    > [!WARNING]  
    > 默认情况下，也会创建 HTTP 规则，并使用与 SSL 规则相似的命名来表示。 对于我们的当前示例，将 HTTP 规则命名为 " <STRONG>ARR_webext com_loadbalance</STRONG>。 这些规则不需要进行任何修改，可以安全地忽略它们。

    
    </div>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-tmg-2010"></a>修改 TMG 2010 中的 web 发布规则的属性

1.  单击 "**开始**"，指向 "**程序**"，选择 " **Microsoft Forefront tmg**"，然后单击 " **Forefront tmg 管理**"。

2.  在左窗格中，展开“服务器名称”****，然后单击“防火墙策略”****。

3.  在详细信息窗格中，右键单击在前面的过程中创建的 Web 服务器发布规则（例如，LyncServerExternalRule），然后单击“属性”****。

4.  在“属性”**** 页上的“从”**** 选项卡上，执行下列操作：
    
      - 在“此规则应用于来自这些源的通讯”**** 列表中，单击“任意位置”****，然后单击“删除”****。
    
      - 单击“添加”****。
    
      - 在“添加网络实体”**** 中，展开“网络”****，依次单击“外部”****、“添加”****，然后单击“关闭”****。

5.  在“到”**** 选项卡上，确保“转发原始主机头，而不是实际主机头”**** 复选框处于选中状态。

6.  在“桥接”**** 选项卡上，选中“将请求重定向到 SSL 端口”**** 复选框，然后指定端口 **4443**。

7.  在“公共名称”**** 选项卡上，添加简单 URL（例如，meet.contoso.com 和 dialin.contoso.com）。

8.  单击“应用”**** 保存更改，然后单击“确定”****。

9.  在详细信息窗格中，单击“应用”****，以保存所做的更改并更新配置。

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-iis-arr"></a>在 IIS ARR 中修改 web 发布规则的属性

1.  单击 "**开始**"，选择 "**程序**"，选择 "**管理工具**"，然后单击 " **Internet 信息服务（IIS）管理器**"。

2.  在控制台的左侧，单击 IIS 服务器名称。

3.  在控制台的中间，查找 " **IIS**" 下的 " **URL 重写**"。 双击 "URL 重写" 以打开 URL 重写规则配置。

4.  双击需要修改的规则。 根据需要进行修改，使其与 URL、**条件**、**服务器变量**或**操作****相匹配**。

5.  单击 "**应用**" 以提交所做的更改。 若要修改其他规则，请单击 "**返回到规则**"，或者关闭**IIS 管理器**控制台（如果您已完成更改）。

</div>

</div>

<span> </span>

</div>

</div>

</div>

