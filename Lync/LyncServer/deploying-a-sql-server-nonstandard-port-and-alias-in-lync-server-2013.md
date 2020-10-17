---
title: 在 Lync Server 2013 中部署 SQL Server 非标准端口和别名
description: 在 Lync Server 2013 中部署 SQL Server 非标准端口和别名。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a SQL Server nonstandard port and alias in Lync Server 2013
ms:assetid: 2da92c1f-250e-407a-8651-fb2aec76aeb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn776290(v=OCS.15)
ms:contentKeyID: 62634609
ms.date: 09/17/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da76db2b946a47e13fe3549d7184b0b12894a83a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551228"
---
# <a name="deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013"></a>在 Lync Server 2013 中部署 SQL Server 非标准端口和别名

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2015-09-16_

Microsoft Lync Server 2013 支持在 SQL Server 中使用非标准端口和别名。 使用 SQL Server 非标准端口和别名可提高安全性，并为 Lync 部署创建更灵活的环境。 这些步骤只是正确保护 Lync Server 2013 环境的一个步骤。 应采取其他步骤来减小 Lync Server 2013 实施的受攻击面。

下面的文章介绍了在 Lync Server 2013 中设置 SQL Server 非标准端口和别名所需的步骤。

<div>

## <a name="deploying-a-sql-server-non-standard-port-and-alias-in-lync-server-2013"></a>在 Lync Server 2013 中部署 SQL Server 非标准端口和别名

Lync Server 2013 拓扑生成器支持在配置 Lync Server 2013 时使用 SQL Server 别名作为完全限定的域名 (FQDN) 而不是实际的 SQL Server FQDN。 这样，就可以从任何恶意攻击者中隐藏实际的 SQL Server FQDN。 此外，如果使用非标准端口遮盖实际端口，攻击者可能会试图攻击标准端口1433上的数据库，如下图所示。

![黑客不知道要攻击的端口号。](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "黑客不知道要攻击的端口号。")

为了在确定端口 Lync Server 2013 正在使用与 SQL Server 通信时成功，攻击者需要扫描所有端口以获取端口信息。 攻击者对端口进行扫描可提高安全性检测和停止指令的机会。 除了使用非标准端口添加更高的安全性之外，还可以使用 SQL Server 别名为部署提供灵活性。 在需要更改 SQL Server 名称的情况下，这一点非常有用，从而减少了配置更改。

<div>


> [!NOTE]  
> SQL Server 在故障转移群集和镜像) 中提供了两种容错方法 (。 使用 SQL Server 的非标准端口和使用 Lync Server 2013 的别名都支持这两种 SQL Server 容错方法。 如果池使用的 SQL Server 后端在镜像配置中，则当数据库故障转移到镜像 SQL Server 时，SQL Server 后端服务器上的 SQL browser service 应运行，以便前端服务器连接到镜像数据库。



</div>

在拓扑生成器中配置 SQL Server 数据库连接时，或者在使用 Install-CsDatabase cmdlet 时，不可能显式定义 SQL Server 非标准端口号，并将其与 SQL 实例关联。 若要设置非标准端口，需要使用 SQL Server 和 Windows Server 实用程序。

若要设置与 Lync Server 2013 一起使用的 SQL Server 非标准端口和别名，您需要完成三个主要步骤。 这些步骤是：

  - 确认 Lync Server 2013 应用了最新的更新。

  - 设置 SQL Server 非标准端口和别名。

  - 使用拓扑生成器将 Lync Server 2013 配置为 SQL Server 别名。

  - 发布拓扑，并验证数据库。

<div>

## <a name="confirm-that-lync-server-2013-has-the-latest-updates-applied"></a>确认 Lync Server 2013 已应用最新的更新

将 Lync Server 2013 保持为最新状态非常重要。 若要查看有关如何应用这些更新的最新更新和信息，请参阅 [Lync Server 2013 更新](https://support.microsoft.com/kb/2809243)。

</div>

<div>

## <a name="setup-the-sql-server-non-standard-port-and-alias"></a>设置 SQL Server 非标准端口和别名

必须先在数据库实例上设置 SQL Server 非标准端口和别名，然后才能从 Lync Server 2013 拓扑生成器中引用它。 若要设置 SQL Server 非标准端口和别名，您将需要完成三个主要步骤。 这些步骤如下：

  - 更改默认的 TCP/IP 协议值。

  - 创建和配置 SQL Server 别名。

  -  (DNS) 规范名称 (CNAME) 资源记录中创建域名系统。

**修改默认的 TCP/IP 协议值**

1.  选择 " **开始**"，然后选择 " **SQL Server 配置管理器**"，如下图所示。
    
    ![SQL Server Management Studio 图标](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "SQL Server Management Studio 图标")

2.  在导航窗格中，选择展开 " **Sql server" 实例**，选择展开 " **Sql server 网络配置**"，然后** \<instance name\> **选择 "协议"，如下图所示。
    
    ![导航到 "TCP/IP 属性"](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "导航到 "TCP/IP 属性"")

3.  在右窗格中，右键单击 " **tcp/ip**"，然后选择 " **属性**"。 将显示 "TCP/IP 属性" 对话框。

4.  选择 " **IP 地址** " 选项卡。"IP 地址" 选项卡显示服务器上的所有活动 IP 地址。 这些格式的格式为 IP1、IP2、最高为 IPAll，如下图所示。
    
    ![打开 "TCP/IP 属性"。](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "打开 "TCP/IP 属性"。")

5.  清除所有 IP 地址的 " **TCP 动态端口** " 字段。 如果该字段包含零个字符，则表示 SQL Server 正在侦听动态端口。 请确保这些字段已清除且不包含零。

6.  对于 Lync Server 将用于连接到数据库的 IP 地址，请确保 " **已启用** " 设置为 **"是"**，如下图所示。
    
    ![对于正确的 IP，请将启用设置为 Yes。](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "对于正确的 IP，请将启用设置为 Yes。")

7.  在对话框底部的 " **IPAll** " 部分中，在 " **TCP 端口** " 字段中输入所需的端口，如下图所示。 在此示例中，我们使用端口50062，但你可以使用49152和65535之间的任何端口。 这些端口分配给动态和专用用途，这样可确保您不会与 Lync Server 2013 部署中使用的其他端口发生冲突。
    
    ![在 "IPAll" 部分中设置端口。](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "在 "IPAll" 部分中设置端口。")

8.  选择 **"确定"** 退出 "tcp/ip 属性" 对话框。

9.  在 "SQL Server 配置管理器" 的左窗格中选择 " **Sql Server 服务** "，以重新启动 sql server 实例。 然后，在右侧窗格中右键单击 " **SQL Server \<instance name\> ** "，然后选择 "**重新启动**"，如下图所示。
    
    ![为实例重置 SQL Server 服务。](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "为实例重置 SQL Server 服务。")

<div>


> [!IMPORTANT]  
> 请确保更新防火墙设置以适应新的 SQL Server 端口。



</div>

**创建和配置 SQL Server 别名**

1.  选择 " **开始**"，然后选择 " **SQL Server 配置管理器**"，如下图所示。
    
    ![SQL Server Management Studio 图标](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "SQL Server Management Studio 图标")

2.  在左窗格中，选择展开 " **Sql Server 实例**"，选择展开 " **sql Native Client \<version\> 配置**"，然后选择 " **别名**"，如下图所示。
    
    ![SQL Server 配置管理器中的别名。](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "SQL Server 配置管理器中的别名。")

3.  右键单击 " **别名**"，然后选择 " **新建别名 ...**"。

4.  输入 **别名名称**、 **端口号**、 **协议**和 **服务器**，如下图所示。
    
    ![创建新别名](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "创建新别名")
    
    <div>
    

    > [!CAUTION]  
    > 请务必输入在上一步中使用的非标准端口，因为这是 SQL Server 将要侦听的端口。 如果配置的别名连接到了错误的 SQL Server FQDN 或实例，请禁用并重新启用关联的网络协议。 执行此操作将清除所有缓存的连接信息，并允许客户端正确连接。

    
    </div>

**创建 DNS CNAME 资源记录**

1.  登录到管理 DNS 的计算机。

2.  选择 " **开始**"，然后选择 " **服务器管理器**"，如下图所示。
    
    ![打开服务器管理器](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "打开服务器管理器")

3.  选择 " **工具** " 下拉下拉箭头，然后选择 " **DNS**"，如下图所示。
    
    ![从服务器管理器打开 DNS。](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "从服务器管理器打开 DNS。")

4.  在左窗格中，展开 "服务器名称" 节点，展开 "正向查找区域" 节点，然后选择相关域。

5.  右键单击域，然后选择 " **新建别名 (CNAME) ...**"，如下图所示。
    
    ![选择创建新的别名 CNAME 的选项](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "选择创建新的别名 CNAME 的选项")

6.  输入 " **别名** " 和 " **SQL Server 的 FQDN**"，如下图所示。
    
    ![填写 "新建别名 CNAME" 对话框。](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "填写 "新建别名 CNAME" 对话框。")

7.  选择 **"确定"** 以保存 CNAME 并在 DNS 管理器中查看。

</div>

<div>

## <a name="validate-database-connectivity"></a>验证数据库连接

有多种不同的方法可确保其正常工作。 您希望确保 SQL Server 数据库使用别名在指定的端口上进行侦听。 可以使用 **netstat** 和 **telnet** 命令完成快速检查。

<div>


> [!NOTE]  
> Telnet 客户端是 Windows Server 附带但必须安装的一项功能。 可以通过打开服务器管理器并从 "管理" 菜单中选择 "添加角色和功能" 来安装 Windows Server 功能。



</div>

**使用 netstat 和 telnet 验证数据库连接**

1.  选择 " **开始**"，然后键入 **cmd** 以打开命令提示符。

2.  键入 **netstat-a-f**，并确认 SQL Server 正在使用正确的端口运行，如下图所示。
    
    ![使用 netstat 验证端口。](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "使用 netstat 验证端口。")

3.  键入**telnet \<alias name\> \<port \#\> **以确认与 SQL Server 实例的连接。 如果连接成功，telnet 将会连接，并且您不会看到错误。 这表明 SQL Server 实例正在使用正确的别名在正确的端口上侦听。 如果连接到 SQL Server 数据库时出现问题，telnet 将显示一条错误消息，指出无法建立连接。 现在您已经检查了数据库服务器上的数据库连接，您可以通过网络) 从 Lync Server (中执行相同的操作，并确保没有任何防火墙阻止访问。

</div>

<div>

## <a name="conclusion"></a>总结

一旦配置了 SQL Server 别名，便可使用它在拓扑生成器工具中创建 Lync Server 2013 拓扑。 有关拓扑的详细信息，请参阅 [在 Lync Server 2013 中定义和配置拓扑](lync-server-2013-defining-and-configuring-the-topology.md)。

</div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[Microsoft Lync Server 2013](microsoft-lync-server-2013.md)  
[在 Lync Server 2013 中规划安全性](lync-server-2013-planning-for-security.md)  
[在 Lync Server 2013 中定义和配置拓扑](lync-server-2013-defining-and-configuring-the-topology.md)  
[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

