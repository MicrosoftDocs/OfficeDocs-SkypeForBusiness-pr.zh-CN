---
title: 将观察程序节点配置为使用受信任服务器身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use Trusted Server authentication
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48184017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7279e18c73ecca9340f57d40794a3e9eb2dd160b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a>在 Lync Server 2013 中配置观察程序节点以使用受信任的服务器身份验证

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-22_

如果你的观察程序节点计算机位于外围网络内，使用受信任服务器身份验证，可以大大减少管理税，以维护单个证书而不是多个用户帐户密码。

配置受信任服务器身份验证的第一步是创建一个受信任的应用程序池来托管观察程序节点计算机。 创建受信任的应用程序池后，必须随后在该观察程序节点上配置合成事务以作为受信任的应用程序运行。

<div>


> [!NOTE]
> 受信任的应用程序是以 Lync Server 2013 的一部分运行的受信任状态的应用程序，但这不是产品的内置部分。 受信任状态意味着，每次运行该应用程序时，将不会要求其进行身份验证。



</div>

若要创建受信任的应用程序池，请打开 Lync Server 2013 命令行管理程序，并运行如下所示的命令：

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> 有关前一个命令中使用的参数的详细信息，请在 Lync Server Management Shell 提示符处键入以下内容：<BR>获取-帮助全新 CsTrustedApplicationPool-完全 |不再



</div>

创建受信任的应用程序池后，将观察程序节点计算机配置为将合成事务作为受信任的应用程序运行。 通过使用**CsTrustedApplication** cmdlet 和类似如下的命令来完成此操作：

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

当前面的命令完成且已创建受信任的应用程序时，请运行 Enable-CsTopology 以确保所做的更改会生效：

    Enable-CsTopology

运行 Enable-CsTopology 后，建议重新启动计算机。

若要验证是否已创建新的受信任的应用程序，请在 Lync Server Management Shell 提示符处键入以下内容：

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a>在 "观察程序" 节点上配置默认证书

每个观察程序节点都必须具有使用 Lync Server 部署向导分配的默认证书。

**分配默认证书**

1.  单击 "**开始**"，单击 "**所有程序**"，单击 " **lync server**"，然后单击 " **lync server 部署向导**"。

2.  在 Lync Server 部署向导中，单击 "**安装或更新 Lync Server 系统**"，然后单击标题请求下的 "**运行**" **，安装或分配证书**。
    
    <div>
    

    > [!NOTE]
    > 如果禁用 "<STRONG>运行</STRONG>" 按钮，可能需要先单击 "<STRONG>安装本地配置存储</STRONG>" 下的 "<STRONG>运行</STRONG>"。

    
    </div>

3.  请执行下列操作之一：
    
      - 如果您已经拥有可用作默认证书的证书，请单击证书向导中的 "**默认**"，然后单击 "**分配**"。 按照证书分配向导中的步骤分配此证书。
    
      - 如果需要申请使用默认证书的证书，请单击 "**请求**"，然后按照证书请求向导中的步骤请求该证书。 如果您使用 Web Server 证书的默认值，则您将获得可作为默认证书分配的证书。

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a>安装和配置观察程序节点

重新启动观察程序节点计算机并配置证书后，您需要运行文件 Watchernode。 （必须在安装了 Operations Manager 代理文件和 Lync Server 2013 核心组件的计算机上运行 Watchernode。）

**安装和配置观察程序节点**

1.  依次单击 "**开始**"、"**所有程序**"、" **lync server**"，然后单击 " **Lync Server Management Shell**"，打开 Lync Server 命令行管理程序。

2.  在 Lync Server 命令行管理器中，键入以下命令，然后按 ENTER （指定 Watchernode 副本的实际路径）：
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > 您也可以从命令窗口运行 Watchernode。 若要打开命令窗口，请单击“开始”<STRONG></STRONG>，右键单击“命令提示符”<STRONG></STRONG>，然后单击“以管理员身份运行”<STRONG></STRONG>。 当 "命令" 窗口打开时，请键入相同的前述命令。

    
    </div>

请注意，前面的命令身份验证 = TrustedServer 中的名称/值对是区分大小写的。 必须严格按显示内容键入。 以下命令将失败，因为它不使用正确的字母大小写：

C：\\Tools\\Watchernode 身份验证 = trustedserver

只能将 TrustedServer 模式用于位于外围网络内的计算机。 当观察程序节点在 TrustedServer 模式下运行时，管理员不必在计算机上维护测试用户密码。

</div>

</div>

<span> </span>

</div>

</div>

</div>

