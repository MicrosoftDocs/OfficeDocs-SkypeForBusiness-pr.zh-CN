---
title: 综合事务的特殊设置说明
TOCTitle: 综合事务的特殊设置说明
ms:assetid: 694cbe05-5dba-4035-a01c-c87ebfb0478b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688080(v=OCS.15)
ms:contentKeyID: 49888450
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 综合事务的特殊设置说明

 

_**上一次修改主题：** 2015-11-16_

大多数综合事务可按原样在观察程序节点上运行；也就是说，一旦将综合事务添加到观察程序节点配置设置，观察程序节点就可在其测试通过期间开始使用综合事务。但此情况并不适用于所有综合事务。以下几节讨论了这些例外（需要特定安装说明的综合事务）。

## 数据会议综合事务

在观察程序节点位于外围网络外部的情况下，除非首先为 Network Service 帐户禁用 Internet Explorer 代理设置，否则您可能无法运行数据会议综合事务。若要为此服务禁用代理设置，请完成以下过程：

1.  在观察程序节点计算机上，依次单击“开始”、“所有程序”和“附件”，再右键单击“命令提示符”，然后单击“以管理员身份运行”。

2.  在控制台窗口中键入以下命令，然后按 Enter：
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

命令窗口中将显示以下消息：

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

此消息意味着您已为 Network Service 帐户禁用 Internet Explorer 代理设置。

## Exchange 统一消息综合事务

Exchange 统一消息 (UM) 综合事务验证测试用户是否能连接到驻留在 Exchange 中的语音邮件帐户。需要先为这些测试用户预配置语音邮件帐户，然后他们才能使用 Exchange UM 测试。

## 持久聊天综合事务

若要使用持久聊天综合事务，管理员必须先创建一个通道并向测试用户授予使用该通道的权限。可以使用 [Test-CsPersistentChatMessage](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsPersistentChatMessage) cmdlet 正确配置这些测试用户：

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

必须从企业内部运行此设置任务：

  - 如果从非服务器计算机运行，则运行此 cmdlet 的用户必须是基于角色的访问控制 (RBAC) 的 PersistentChatAdministrators 角色的成员。

  - 如果从服务器本身运行，则运行此 cmdlet 的用户应是 RTCUniversalServerAdmins 组的成员。

在上面的命令中，已包含 Setup 参数并设置为 True ($True)。如果包含 Setup 参数，则 Test-CsPersistentChatMessage 将创建一个特殊的持久聊天聊天室并使用测试用户填充此聊天室。这有助于确保实际存在一个可用于测试目的的聊天室。请注意，只应从前端服务器中运行 Setup 参数。

仅管理员能够删除由 Test-CsPersistentChatMessage 创建的聊天室。

## PSTN 对等呼叫综合事务

[Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsPstnPeerToPeerCall) 综合事务验证是否能通过公用电话交换网 (PSTN) 发出和接收呼叫。

若要运行此综合事务，管理员必须：

  - 为两个测试用户（呼叫者和接收者）启用企业语音。

  - 为每个用户帐户配置外线直拨分机 (DID) 号码。

  - 配置允许对接收者的号码的呼叫到达 PSTN 网关的语音策略和语音路由。

  - 配置接受呼叫的 PSTN 网关和基于拨打的号码将呼叫路由回接收者主池的媒体。

## 统一的联系人存储库综合事务

统一的联系人存储库综合事务验证 Lync Server 2013 是否能代表用户从 Microsoft Exchange Server 2013 中检索联系人。

若要使用此综合事务，必须满足以下条件：

  - 必须在 Lync Server 2013 和 Exchange 2013 之间配置[在 Lync Server 2013 中管理服务器到服务器身份验证 (Oauth) 和合作伙伴应用程序](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。

  - 测试用户必须具有有效的 Exchange 2013 邮箱。

在满足这些条件后，管理员可以运行以下命令来验证 SIP 地址为 kenmyer@litwareinc.com 的用户是否能从统一的联系人存储库中检索其联系人：

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

请注意上面的命令中使用的 Setup 参数的用法。如果运行 Test-CsUnifiedContactStore 时包含 Setup 参数，则指定用户的联系人（在此示例中，为 sip:kenmyer@litwareinc.com）将被移至统一的联系人存储库中。（当然，如果该用户的联系人已包含在统一的联系人存储库中，则无需移动他们。）Setup 参数通常只被使用一次（在首次执行 Test-CsUnifiedContactStore 时）且仅用于测试用户；也就是说，用于绝不会实际登录到 Lync Server 的用户帐户。在将测试用户迁移到统一的联系人存储库后，可通过调用 Test-CsUnifiedContactStore（不带 Setup 参数）来验证是否能检索用户的联系人：

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

## XMPP 综合事务

XMPP（可扩展消息传递和状态协议）IM 综合事务要求为一个或多个联盟域配置 XMPP 功能。

若要启用 XMPP 综合事务，则必须将 XmppTestReceiverMailAddress 参数与可路由的 XMPP 域中的用户帐户一起提供。例如：

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

在此示例中，需已存在 Lync Server 2013 规则才能将 litwareinc.com 的消息路由到 XMPP 网关。

