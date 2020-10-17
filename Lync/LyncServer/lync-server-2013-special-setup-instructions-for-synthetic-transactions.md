---
title: Lync Server 2013：综合事务的特殊设置说明
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Special setup instructions for synthetic transactions
ms:assetid: 694cbe05-5dba-4035-a01c-c87ebfb0478b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688080(v=OCS.15)
ms:contentKeyID: 49733676
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3841cb8a582e44e14b9ae7c73f3b3aed6b6ded33
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519569"
---
# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a>Lync Server 2013 中的综合事务的特殊设置说明

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2015-11-16_

大多数综合事务可按原样在观察程序节点上运行；也就是说，一旦将综合事务添加到观察程序节点配置设置，观察程序节点就可在其测试通过期间开始使用综合事务。但此情况并不适用于所有综合事务。以下几节讨论了这些例外（需要特定安装说明的综合事务）。

<div>

## <a name="dealing-with-server-timeout-errors"></a>处理服务器超时错误

在某些情况下，您可能会发现您的综合事务失败，并出现服务器超时错误 (错误代码 504) 。 这些错误通常是由防火墙问题引起的。 执行综合事务时，该事务在 MonitoringHost.exe 进程下运行;反过来，MonitoringHost.exe 启动 PowerShell.exe 进程的一个实例。 如果防火墙阻止 MonitoringHost.exe 或 PowerShell.exe，则综合事务将失败，并将生成504错误。

若要解决此问题，您应手动为本地计算机上的 MonitoringHost.exe 和 PowerShell.exe 创建入站防火墙规则。 可以通过 Windows 防火墙或第三方本地防火墙软件执行此操作，具体取决于您的服务器的预先存在的配置。

如果要在综合事务主机和要监视的 Lync 服务器之间使用网络防火墙设备，则应将主机视为客户端计算机，并 [在 Lync Server 2013 中观察内部服务器的端口和协议中的](lync-server-2013-ports-and-protocols-for-internal-servers.md)所有防火墙端口要求。

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a>数据会议综合事务

如果您的观察程序节点计算机位于您的外围网络之外，则您可能无法运行数据会议综合事务，除非您首先禁用网络服务帐户的 Internet Explorer 代理设置。 若要为此服务禁用代理设置，请完成以下过程：

1.  在观察程序节点计算机上，依次单击“开始”****、“所有程序”****、“附件”****，右键单击“命令提示符”****，然后单击“以管理员身份运行”****。

2.  在控制台窗口中键入以下命令，然后按 Enter：
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

命令窗口中将显示以下消息：

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

此邮件表示您已禁用网络服务帐户的 Internet Explorer 代理设置。

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a>Exchange 统一消息综合事务

Exchange 统一消息 (UM) 综合事务验证测试用户是否可以连接到位于 Exchange 中的语音邮件帐户。 需要先为这些测试用户预配置语音邮件帐户，然后他们才能使用 Exchange UM 测试。

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a>持久聊天综合事务

若要使用持久聊天综合事务，管理员必须首先创建一个通道，并向测试用户授予使用该功能的权限。 [CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) cmdlet 可用于正确配置这些测试用户：

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

必须从企业内部运行此设置任务：

  - 如果从非服务器计算机运行，则运行此 cmdlet 的用户必须是基于角色的访问控制 (RBAC) 的 PersistentChatAdministrators 角色的成员。

  - 如果从服务器本身运行，则运行此 cmdlet 的用户应是 RTCUniversalServerAdmins 组的成员。

在上面的命令中，已包含 Setup 参数并设置为 True ($True)。 如果包含 Setup 参数，Test-CsPersistentChatMessage 将创建一个特殊的持久聊天室，并向测试用户填充该聊天室。 这有助于确保实际存在一个可用于测试目的的聊天室。 请注意，安装程序参数应仅在前端服务器上运行。

仅管理员能够删除由 Test-CsPersistentChatMessage 创建的聊天室。

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a>PSTN 对等呼叫综合事务

[CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall)综合事务通过公开交换电话网络 (PSTN) 验证是否可以拨打和接听呼叫。

若要运行此综合事务，管理员必须：

  -  (呼叫者和接收方) 启用企业语音的两个测试用户。

  - 为每个用户帐户配置外线直拨分机 (DID) 号码。

  - 配置允许对接收者的号码的呼叫到达 PSTN 网关的语音策略和语音路由。

  - 配置接受呼叫的 PSTN 网关和基于拨打的号码将呼叫路由回接收者主池的媒体。

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a>统一的联系人存储库综合事务

统一联系人存储综合事务验证 Lync Server 2013 是否可以代表用户从 Microsoft Exchange Server 2013 检索联系人。

若要使用此综合事务，必须满足以下条件：

  - 必须在 Lync Server 2013 和 Exchange 2013 之间配置[ (OAuth) 和在 Lync server 2013 中的合作伙伴应用程序管理服务器到服务器的身份验证](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。

  - 测试用户必须具有有效的 Exchange 2013 邮箱。

在满足这些条件后，管理员可以运行以下命令来验证 SIP 地址为 kenmyer@litwareinc.com 的用户是否能从统一的联系人存储库中检索其联系人：

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

请注意上面的命令中使用的 Setup 参数的用法。 如果运行 Test-CsUnifiedContactStore 时包含 Setup 参数，则指定用户的联系人（在此示例中，为 sip:kenmyer@litwareinc.com）将被移至统一的联系人存储库中。  (当然，如果用户的联系人已在统一联系人存储中，则无需移动它们。 ) 安装程序参数通常仅在第 Test-CsUnifiedContactStore 一次执行) 时 (使用一次，且只应与测试用户一起使用;即，用户帐户永远不会实际登录到 Lync Server。 在将测试用户迁移到统一的联系人存储库后，可通过调用 Test-CsUnifiedContactStore（不带 Setup 参数）来验证是否能检索用户的联系人：

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a>XMPP 综合事务

XMPP（可扩展消息传递和状态协议）IM 综合事务要求为一个或多个联盟域配置 XMPP 功能。

若要启用 XMPP 综合事务，则必须将 XmppTestReceiverMailAddress 参数与可路由的 XMPP 域中的用户帐户一起提供。 例如：

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

在此示例中，必须存在 Lync Server 2013 规则，才能将 litwareinc.com 的邮件路由到 XMPP 网关。

</div>

</div>

<span> </span>

</div>

</div>

</div>

