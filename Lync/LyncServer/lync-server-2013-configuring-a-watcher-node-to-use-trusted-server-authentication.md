---
title: 配置观察程序节点以使用受信任的服务器身份验证
TOCTitle: 配置观察程序节点以使用受信任的服务器身份验证
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204852(v=OCS.15)
ms:contentKeyID: 49312672
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置观察程序节点以使用受信任的服务器身份验证

 

_**上一次修改主题：** 2012-10-22_

如果观察程序节点计算机位于外围网络中，则使用受信任服务器身份验证可大大降低管理负担，只需维护单个证书即可，而无需维护大量用户帐户密码。

配置受信任服务器身份验证的第一步是创建受信任应用程序池以承载观察程序节点计算机。在创建受信任应用程序池后，您必须对观察程序节点上的综合事务进行配置，使其作为受信任应用程序运行。

> [!NOTE]  
> 受信任的应用程序是指获得了受信任的状态且作为 Lync Server 2013 的一部分运行的应用程序，但它不是产品的内置部分。受信任的状态意味着，每次运行该应用程序时，将不会要求其进行身份验证。



若要创建受信任的应用程序池，请打开 Lync Server 2013 命令行管理程序并运行与以下内容类似的命令：

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

> [!NOTE]  
> 要了解上述命令中使用的参数的详细信息，请在 Lync Server 命令行管理程序提示符处键入以下内容：<br />
Get-Help New-CsTrustedApplicationPool -Full | more



在创建受信任的应用程序池之后，可将观察程序节点计算机配置为将综合事务作为受信任的应用程序运行。这可以通过使用 **New-CsTrustedApplication** cmdlet 和类似于以下内容的命令来实现的：

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

在完成上述命令并创建受信任的应用程序之后，请运行 Enable-CsTopology 以确保更改生效：

    Enable-CsTopology

运行 Enable-CsTopology 之后，建议您重新启动计算机。

若要验证是否已创建新的受信任应用程序，请在 Lync Server 命令行管理程序提示符处键入：

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

## 在观察程序节点上配置默认证书

必须通过使用 Lync Server 部署向导为每个观察程序节点分配一个默认证书。

**分配默认证书**

1.  依次单击“开始”、“所有程序”、“Lync Server”和“Lync Server 部署向导”。

2.  在 Lync Server 部署向导中，单击“安装或更新 Lync Server 系统”，然后单击标题“请求、安装或分配证书”下方的“运行”。
    
    > [!NOTE]  
    > 如果禁用“运行”按钮，则您可能需要先单击“安装本地配置存储”下方的“运行”。
    


3.  执行下列操作之一：
    
      - 如果您已有一个可用作默认证书的证书，请单击证书向导中的“默认”，然后单击“分配”。按照证书分配向导中的步骤进行操作以分配此证书。
    
      - 如果您需要请求用作默认证书的证书，请单击“请求”，然后按照证书请求向导中的步骤进行操作以请求该证书。如果您使用 Web Server 证书的默认值，则您将获得可作为默认证书分配的证书。

## 安装和配置观察程序节点

在重新启动观察程序节点计算机并配置证书之后，您需要运行文件 Watchernode.msi。（您必须在同时安装了 Operations Manager 代理文件和 Lync Server 2013 核心组件的计算机上运行 Watchernode.msi。）

**安装和配置观察程序节点**

1.  通过依次单击“开始”、“所有程序”、“Lync Server”和“Lync Server 命令行管理程序”打开 Lync Server 命令行管理程序。

2.  在 Lync Server 命令行管理程序中，键入以下命令并按 Enter（指定您的 Watchernode.msi 副本的实际路径）：
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    > [!NOTE]  
    > 您还可以从命令窗口运行 Watchernode.msi。若要打开命令窗口，请单击“开始”，右键单击“命令提示符”，然后单击“以管理员身份运行”。在打开命令窗口后，键入相同的上述命令。
    


请注意，上述命令 Authentication=TrustedServer 中的名称/值对是区分大小写的。您必须如上所示准确地键入该命令。以下命令就是由于没有使用正确的字母大小写而失败了：

C:\\Tools\\Watchernode.msi authentication=trustedserver

您只能对外围网络中的计算机使用 TrustedServer 模式。当观察程序节点在 TrustedServer 模式中运行时，管理员无需维护计算机上的测试用户密码。

