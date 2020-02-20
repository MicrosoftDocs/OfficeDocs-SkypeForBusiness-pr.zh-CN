---
title: 配置观察程序节点测试用户和配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring watcher node test users and configuration settings
ms:assetid: ab00e9cb-f539-4aa6-bcb4-5533fbe7bc44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205152(v=OCS.15)
ms:contentKeyID: 48185048
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d66eb347fbd26f2d50828924d41075680fdcc09
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154084"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中配置观察程序节点测试用户和配置设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-07-29_

在配置将充当观察程序节点的计算机之后，您必须：

1.  创建可供这些观察程序节点使用的测试帐户。 如果您使用的是 Negotiate 身份验证方法，则必须同时使用 [Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15)) cmdlet 来启用这些测试帐户，以在观察程序节点上使用。

2.  更新观察程序节点配置设置。

本节介绍：

  - 配置测试用户帐户

  - 使用默认综合事务配置基本观察程序节点

  - 配置扩展的测试

  - 添加和删除综合事务

  - 查看和测试观察程序节点配置

<div>

## <a name="configuring-test-user-accounts"></a>配置测试用户帐户

测试用户不需要表示实际人员，但必须是有效的 Active Directory 域服务帐户;此外，必须为 Lync Server 2013 启用这些帐户，它们必须具有有效的 SIP 地址，并且应为企业语音启用这些帐户（以使用 CsPstnPeerToPeerCall 综合事务）。 如果使用 TrustedServer 身份验证方法，则您所需要做的就是确保这些帐户存在并且已按此处所指定的那样进行配置。 您应为要测试的每个池至少分配三个测试用户。

如果使用的是协商身份验证方法，则还必须使用**CsTestUserCredential** Cmdlet 和 Lync Server 命令行管理程序，以使这些测试帐户能够处理综合事务。 您可以通过运行与以下类似的命令来执行此操作（这些命令假设已创建三个 nm-ad-2nd 用户帐户，并且已针对 nm-server-w15-long 启用这些帐户。 （这些命令假定已经创建了三个 Active Directory 用户帐户，并且已为这些帐户启用了 Lync Server 2013。）：

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

请注意，不仅必须包括 SIP 地址，而且还要包括用户名和密码。 如果不包括密码，Set-CsTestUserCredential 将提示您输入该信息。 可以使用上面显示的域名\\用户名格式指定用户名，或使用格式用户 name@domain 名称指定名称。例如：

    -UserName "watcher3@litwareinc.com"

若要验证是否已创建测试用户凭据，请在 Lync Server 命令行管理程序中运行以下命令：

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

应针对每个用户返回与以下类似的信息：

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>使用默认综合事务配置基本观察程序节点

在创建测试用户之后，您可以使用与以下类似的命令创建观察程序节点：

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

此命令会创建一个新的观察程序节点，该节点使用默认设置并运行默认的综合事务集。 新的观察程序节点还使用测试用户 watcher1@litwareinc.com、watcher2@litwareinc.com 和 watcher3@litwareinc.com。 如果观察程序节点使用的是 TrustedServer 身份验证，则这三个测试帐户可以是为 Active Directory 和 Lync Server 启用的任何有效的用户帐户。 如果观察程序节点使用的是 Negotiate 身份验证方法，您必须同时使用 **Set-CsTestUserCredential** cmdlet 为观察程序节点启用这些用户帐户。

</div>

<div>

## <a name="configuring-extended-tests"></a>配置扩展的测试

如果您想要启用公用电话交换网（PSTN 测试），以验证与公用电话交换网的连接，则需要在设置观察程序节点时执行一些额外的配置。 首先，您需要将测试用户与 PSTN 测试类型相关联。 若要执行此操作，请在 Lync Server 命令行管理程序中运行与以下内容类似的命令：

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

请注意，必须将此命令的结果存储在变量中。 在此示例中，指的是名为 $pstnTest 的变量。

在这种情况下，您可以使用**new-cswatchernodeconfiguration** cmdlet 将测试类型（存储在变量 $pstnTest 中）与 Lync Server 2013 池相关联。 例如，下列命令会为池 atl-cs-001.litwareinc.com 创建新的观察程序节点配置，从而添加先前已创建的三个测试用户，并同时添加 PSTN 测试类型：

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

请注意，如果尚未在观察程序节点计算机上安装 Lync Server core 文件和 RTCLocal 数据库，则上述命令将失败。

要测试多个语音策略，需要使用 **New-CsExtendedTest** cmdlet 为每个策略创建一个扩展测试。 应使用所需的语音策略对分配给此测试的用户进行配置。 然后，使用与以下类似的命令将扩展测试传递到 **New-CsWatcherNodeConfiguration** cmdlet：

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

如果在未使用 Tests 参数的情况下呼叫 New-CsWatcherNodeConfiguration，则表示只会针对新的观察程序节点启用默认综合事务（以及指定的扩展综合事务）。这意味着该观察程序节点将测试以下组件：

  - 注册

  - IM

  - GroupIM

  - P2PAV（对等音频/视频会话）

  - AvConference（音频/会议）

  - 状态

  - ABS（通讯簿服务）

  - ABWQ（通讯簿 Web 服务）

  - PSTN（PSTN 网关呼叫，指定为扩展测试。默认情况下会禁用 PSTN。只是因为命令使用 ExtendedTests 参数启用了 PSTN，所以在这种情况下才会启用测试。）

这还意味着在默认情况下不会测试以下组件：

  - AVEdgeConnectivity

  - MCXP2PIM（移动设备即时消息）

  - ExumConnectivity（Exchange 统一消息）

  - JoinLauncher

  - PersistentChatMessage

  - DataConference

  - XmppIM

  - UnifiedContactStore

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a>添加和删除综合事务

在配置观察程序节点之后，您可以使用 **Set-CsWatcherNodeConfiguration** cmdlet 添加或从节点中删除综合事务。 例如，要将 PersistentChatMessage 测试添加到观察程序节点，请使用 Add 方法和与以下类似的命令：

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

可以通过使用逗号分隔测试名称来添加多个测试。例如：

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

请注意，如果已在观察程序节点上启用其中一个或多个测试（例如，DataConference），则将会发生错误。在这种情况下，您将收到与以下类似的错误消息：

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

发生此错误时，不会应用任何更改。 应通过删除的重复测试重新运行此命令。

要从观察程序节点中删除综合事务，请使用 Remove 方法而不是 Add 方法。例如，以下命令会从观察程序节点中删除 ABWQ 测试：

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

您也可以使用 Replace 方法将所有目前启用的测试替换为一个或多个新测试。例如，如果您只是希望观察程序节点运行 IM 测试，则可以使用以下命令对此进行配置：

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

在运行上述命令时，除了 IM 以外，将禁用指定观察程序节点上的所有综合事务。

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a>查看和测试观察程序节点配置

如果您想要查看已分配给观察程序节点的测试，请使用与以下类似的命令：

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

根据已分配给节点的综合事务，上述命令将返回与以下类似的信息：

    Registration
    IM
    GroupIM
    P2PAV
    AvConference
    Presence
    PersistentChatMessage
    DataConference

<div>


> [!TIP]
> 要按字母顺序查看综合事务，请改为使用以下命令：<BR>Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object



</div>

若要验证是否已创建观察程序节点，请在 Lync Server 命令行管理程序中键入以下命令：

    Get-CsWatcherNodeConfiguration

您将收到与以下类似的信息：

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

若要验证是否已正确配置观察程序节点，请在 Lync Server 命令行管理程序中键入以下命令：

    Test-CsWatcherNodeConfiguration

上述命令将测试您的部署中的每个观察程序节点，并告诉您诸如以下方面的信息：

  - 是否已安装所需的注册器角色。

  - 是否在您运行 Set-CsWatcherNodeConfiguration 时为您创建了所需的注册表项。

  - 您的服务器运行的是正确版本的 Lync Server。

  - 是否已正确配置您的端口。

  - 所分配的测试用户是否具有所需的凭据。

</div>

</div>

<span> </span>

</div>

</div>

</div>

