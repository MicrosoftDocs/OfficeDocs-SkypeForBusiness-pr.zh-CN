---
title: 在 Lync Server 2013 中部署一个 SQL Server 非标准端口和别名。
TOCTitle: 在 Lync Server 2013 中部署一个 SQL Server 非标准端口和别名。
ms:assetid: 2da92c1f-250e-407a-8651-fb2aec76aeb0
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn776290(v=OCS.15)
ms:contentKeyID: 62634512
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中部署一个 SQL Server 非标准端口和别名。

 

_**上一次修改主题：** 2016-12-08_

Microsoft Lync Server 2013 支持在 SQL Server 中使用非标准端口和别名。使用 SQL Server 非标准端口和别名可以增强安全性并为 Lync 部署创建一个更为灵活的环境。这些步骤只是正确保证您的 Lync Server 2013 环境安全性的简单步骤。若要降低 Lync Server 2013 实施的攻击面，应采取额外步骤。

下面的文章中描述了在 Lync Server 2013 中设置 SQL Server 非标准端口和别名所需的步骤。

## 在 Lync Server 2013 中部署 SQL Server 非标准端口和别名

Lync Server 2013拓扑生成器 支持在配置 Lync Server 2013 时使用 SQL Server 别名作为完全限定域名 (FQDN) 而不是使用实际 SQL Server FQDN。 这可以隐藏实际 SQL Server FQDN，以免受恶意攻击。此外，使用非标准端口可以向任何尝试攻击标准端口 1433 的攻击者隐藏实际端口，如下图所示。

![黑客不知道要攻击的端口号。](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "黑客不知道要攻击的端口号。")

为成功确定 Lync Server 2013 用于与 SQL Server 通信的端口，攻击者需要扫描所有端口以获取端口信息。攻击者扫描端口增加了安全防护探测和阻止指令的机会。除使用非标准端口增加安全性之外，您也可以使用 SQL Server 别名为部署提供灵活性。在需要更改 SQL Server 名称的场景下，这对于减少配置更改非常有用。

> [!NOTE]  
> SQL Server 提供了两种容错方法（故障转移群集和镜像）。将 SQL Server 非标准端口和别名以及 Lync Server 2013 结合使用支持这两种 SQL Server 容错方法。



当从 拓扑生成器 里配置 SQL Server 数据库连接时，或使用 Install-CsDatabase cmdlet 时，无法明确定义一个 SQL Server 非标准端口号并将其与 SQL 实例联系起来。若要设置一个非标准端口，您需要使用 SQL Server 和 Windows Server 实用程序。

若要设置一个与 Lync Server 2013 配合使用的 SQL Server 非标准端口和别名，您需要完成以下三个主要步骤。这些步骤是：

  - 确保 Lync Server 2013 已应用了最新的更新。

  - 设置 SQL Server 非标准端口和别名。

  - 使用 拓扑生成器 配置 Lync Server 2013 和 SQL Server 别名

  - 发布拓扑，并验证数据库。

## 确保 Lync Server 2013 已应用了最新的更新

保持 Lync Server 2013 最新非常重要。若要了解最新更新以及如何应用这些更新的信息，请参阅 [Lync Server 2013 的更新](http://support.microsoft.com/kb/2809243)。

## 设置 SQL Server 非标准端口和别名

SQL Server 非标准端口和别名必须在数据库实例中设置，然后才能从 Lync Server 2013拓扑生成器 中引用。 若要设置 SQL Server 非标准端口和别名，您需要完成三个主要步骤。这些步骤如下：

  - 更改默认 TCP/IP 协议值。

  - 创建和配置 SQL Server 别名。

  - 创建一个域名系统 (DNS) 规范名称 (CNAME) 资源记录。

**修改默认 TCP/IP 协议值**

1.  选择“**开始**”，然后选择“**SQL Server 配置管理器**”，如下图所示。
    
    ![SQL Server Management Studio 图标](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "SQL Server Management Studio 图标")

2.  在导航窗格中，选择展开“**SQL Server 实例**”，选择展开“**SQL Server 网络配置**”，然后选择“**\<实例名\>的协议**”，如下图所示。
    
    ![导航到 TCP/IP 属性](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "导航到 TCP/IP 属性")

3.  在右窗格中，右键单击“**TCP/IP**”，然后选择“**属性**”。将显示 TCP/IP 属性对话框。

4.  选择“**IP 地址**”选项卡。IP 地址选项卡显示了服务器上所有活动的 IP 地址。IP 地址格式为 IP1、IP2 直到 IPAll，如下图所示。
    
    ![打开 TCP/IP 属性。](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "打开 TCP/IP 属性。")

5.  为所有 IP 地址清除“**TCP 动态端口**”域。如果域包含 0 个字符，这意味着 SQL Server 正在侦听动态端口。请确保这些域都已清空且不包含 0。

6.  对于 Lync Server 将用于连接到数据库的 IP 地址，请确保将“**已启用**”设置成“**是**”，如下图所示。
    
    ![对于正确 IP 将“启用”设置为“是”。](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "对于正确 IP 将“启用”设置为“是”。")

7.  在对话框底部的“**IPAll**”部分中，在“**TCP 端口**”域中输入所需端口，如下图所示。在此例中，我们使用端口 50062，但您也可以使用端口 49152 至 65535 之间的任何端口。这些端口分配给动态和专用用途，确保您不会使用正被 Lync Server 2013 部署使用的其他端口。
    
    ![在 IPAll 部分中设置端口。](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "在 IPAll 部分中设置端口。")

8.  选择“**确定**”以退出 TCP/IP 属性框。

9.  通过选择 SQL Server 配置管理器左窗格中的“**SQL Server 服务**”以重启 SQL Server 实例。然后右键单击右窗格中的“**SQL Server \<实例名称\>**” ，然后选择“**重新启动**”，如下图所示。
    
    ![针对实例重置 SQL Server 服务。](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "针对实例重置 SQL Server 服务。")

> [!IMPORTANT]  
> 确保您更新了防火墙设置以容纳新的 SQL Server 端口。


**创建和配置 SQL Server 别名**

1.  选择“**开始**”，然后选择“**SQL Server 配置管理器**”，如下图所示。
    
    ![SQL Server Management Studio 图标](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "SQL Server Management Studio 图标")

2.  在左窗格中，选择展开“**SQL Server 实例**”，然后选择展开“**SQL Native Client \<版本\> 配置**”，然后选择“**别名**”，如下图所示。
    
    ![SQL Server 配置管理器中的别名。](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "SQL Server 配置管理器中的别名。")

3.  右键单击“**别名**”，选择“**新别名…**”。

4.  输入“**别名**”、“**端口号**”、“**协议**”和“**服务器**”，如下图所示。
    
    ![创建新别名](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "创建新别名")
    
    > [!CAUTION]
    > 确保输入您在之前的步骤中使用的同个非标准端口，因为这是 SQL Server 将侦听的端口。如果一个已配置的别名连接到错误的 SQL Server FQDN 或实例，请禁用并重新启动相关的网络协议。这样可以清除所有缓存的连接信息，使客户可以正确连接。


**创建一个 DNS CNAME 资源记录**

1.  登录到计算机管理 DNS。

2.  选择“**开始**”，然后选择“**管理器服务器**”，如下图所示。
    
    ![打开服务器器管理器](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "打开服务器器管理器")

3.  选择“**工具**”下拉菜单，并选择“**DNS**”，如下图所示。
    
    ![从服务器管理器打开 DNS。](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "从服务器管理器打开 DNS。")

4.  在左窗格中，展开服务器名称节点，展开“正向查找区域”节点，然后选择相关域。

5.  右键单击该域，然后选择“**新别名 (CNAME)…**”，如下图所示。
    
    ![选择选项以创建新的别名 CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "选择选项以创建新的别名 CNAME")

6.  输入“**别名**”和“**SQL Server FQDN**”，如下图所示。
    
    ![填充新的别名 CNAME 对话框。](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "填充新的别名 CNAME 对话框。")

7.  选择“**确定**”以保存该 CNAME 并在 DNS 管理器中查看。

## 验证数据库连接

有多种方法可以使其正常工作。建议您确保 SQL Server 数据库在侦听一个使用别名的特定端口。可以通过“**netstat**”和“**telnet**”命令快速检查。

> [!NOTE]  
> Telnet 客户端是 Windows Server 附带的一项功能，必须安装。Windows Server 功能可以通过打开服务器管理器并从“管理”菜单中选择“添加角色和功能”来安装。



**使用 netstat 和 telnet 以验证数据库连接**

1.  选择“**开始**”，然后输入“**cmd**”以打开一个命令提示符。

2.  输入“**netstat -a -f**”，并确保 SQL Server 使用正确的端口运行，如下图所示。
    
    ![使用 netstat 验证端口。](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "使用 netstat 验证端口。")

3.  输入“**telnet \<别名\> \<端口\#\>**”以确保连接到 SQL Server 实例。如果连接成功，telnet 将连接上且不会出现错误。这表明 SQL Server 实例正在侦听使用正确别名的正确端口。如果连接到 SQL Server 数据库出现问题，telnet 将显示连接失败错误。 现在您已在数据库服务器上检查了数据库连接，您可以在 Lync Server（通过网络）做同样的检查并确保没有防火墙阻挡访问。

## 结论

一旦 SQL Server 别名已配置，您可以使用它在 拓扑生成器 工具中创建一个 Lync Server 2013 拓扑。有关拓扑的详细信息，请参阅 [在 Lync Server 2013 中定义和配置拓扑](lync-server-2013-defining-and-configuring-the-topology.md)。

## 另请参阅

#### 概念

[Microsoft Lync Server 2013](microsoft-lync-server-2013.md)  

#### 其他资源

[规划 Lync Server 2013 的安全性](lync-server-2013-planning-for-security.md)  
[在 Lync Server 2013 中定义和配置拓扑](lync-server-2013-defining-and-configuring-the-topology.md)  
[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)

