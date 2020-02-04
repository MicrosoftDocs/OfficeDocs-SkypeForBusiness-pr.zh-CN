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
ms.openlocfilehash: a3713844d5d2364459a28c5919bb1d32d421d706
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中配置观察程序节点测试用户和配置设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-07-29_

在配置将用作观察者节点的计算机后，必须：

1.  创建要由这些观察程序节点使用的测试帐户。 如果你使用协商身份验证方法，你还必须使用[CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ205341(v=OCS.15)) cmdlet 来启用这些测试帐户，以便在 "观察程序" 节点上使用。

2.  更新观察程序节点配置设置。

本部分包括：

  - 配置测试用户帐户

  - 使用默认合成事务配置基本观察程序节点

  - 配置扩展测试

  - 添加和删除综合事务

  - 查看和测试观察程序节点配置

<div>

## <a name="configuring-test-user-accounts"></a>配置测试用户帐户

测试用户不需要表示实际人员，但它们必须是有效的 Active Directory 域服务帐户;此外，必须为 Lync Server 2013 启用这些帐户，它们必须具有有效的 SIP 地址，并且应该为企业语音启用（以使用 CsPstnPeerToPeerCall 合成事务）。 如果你使用 TrustedServer 身份验证方法，则你需要做的就是确保这些帐户存在并且已按照此处的指定进行配置。 你应该为要测试的每个池至少分配三个测试用户。

如果你使用协商身份验证方法，你还必须使用**CsTestUserCredential** Cmdlet 和 Lync Server Management Shell 来使这些测试帐户能够处理合成事务。 你可以通过运行如下所示的命令来执行此操作。 （这些命令假设已经创建了三个 Active Directory 用户帐户，并且已为 Lync Server 2013 启用了这些帐户。）：

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

请注意，不仅必须包括 SIP 地址，还必须包括用户名和密码。 如果不包含密码集，CsTestUserCredential 将提示您输入该信息。 用户名可以使用上面显示的域名\\用户名格式指定，或使用 "设置用户格式" name@domain 名称;例如：

    -UserName "watcher3@litwareinc.com"

若要验证是否已创建测试用户凭据，请从 Lync Server 命令行管理程序中运行以下命令：

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

应为每个用户返回类似于以下内容的信息：

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>使用默认合成事务配置基本观察程序节点

在创建测试用户之后，你可以使用类似下面的命令创建观察程序节点：

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

此命令将创建一个新的监视程序节点，该节点使用默认设置并运行一组默认的合成事务。 新的观察程序节点还使用 test 用户 watcher1@litwareinc.com、watcher2@litwareinc.com 和 watcher3@litwareinc.com。 如果观察程序节点使用 TrustedServer 身份验证，则三个测试帐户可以是为 Active Directory 和 Lync Server 启用的任何有效用户帐户。 如果观察程序节点使用协商身份验证方法，则还必须通过使用**CsTestUserCredential** cmdlet 为观察程序节点启用这些用户帐户。

</div>

<div>

## <a name="configuring-extended-tests"></a>配置扩展测试

如果想要启用公共交换电话网络（PSTN 测试），它将验证与公共交换电话网络的连接性，则需要在设置观察程序节点时执行其他一些配置。 首先，你需要将测试用户与 PSTN 测试类型相关联。 若要执行此操作，请在 Lync Server 命令行管理程序中运行类似下面的命令：

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

请注意，此命令的结果必须存储在变量中。 在此示例中，这是一个名为 $pstnTest 的变量。

此时，你可以使用**CsWatcherNodeConfiguration** cmdlet 将测试类型（存储在变量 $pstnTest 中）与 Lync Server 2013 池相关联。 例如，以下命令为池 atl-cs-001.litwareinc.com 创建新的观察程序节点配置，添加以前创建的三个测试用户以及添加 PSTN 测试类型：

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

请注意，如果尚未在观察程序节点计算机上安装 Lync Server core 文件和 RTCLocal 数据库，上述命令将失败。

若要测试多个语音策略，你需要使用**CsExtendedTest** cmdlet 为每个策略创建扩展测试。 分配到此测试的用户应配置所需的语音策略。 然后，通过使用如下所示的命令将扩展测试传递到**CsWatcherNodeConfiguration** cmdlet：

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

如果在未使用 "测试" 参数的情况下调用 New CsWatcherNodeConfiguration，则表示新的观察程序节点仅启用默认合成事务（和指定的扩展合成事务）。 这意味着观察程序节点将测试以下组件：

  - 注册

  - 即时消息

  - GroupIM

  - P2PAV （对等音频/视频会话）

  - AvConference （音频/会议）

  - 状态

  - ABS （通讯簿服务）

  - ABWQ （通讯簿 web 服务）

  - PSTN （PSTN 网关呼叫，指定为扩展测试。 默认情况下，PSTN 处于禁用状态。 此测试仅在此情况下启用，因为命令通过使用 ExtendedTests 参数启用了 PSTN。）

这还意味着默认情况下不会测试以下组件：

  - AVEdgeConnectivity

  - MCXP2PIM （移动设备即时消息）

  - ExumConnectivity （Exchange 统一消息）

  - JoinLauncher

  - PersistentChatMessage

  - DataConference

  - XmppIM

  - UnifiedContactStore

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a>添加和删除综合事务

配置了观察程序节点后，你可以使用**CsWatcherNodeConfiguration** cmdlet 在节点中添加或删除合成事务。 例如，若要向观察程序节点添加 PersistentChatMessage 测试，请使用 Add 方法和类似如下的命令：

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

可通过使用逗号分隔测试名称来添加多个测试。 例如：

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

请注意，如果在观察程序节点上已启用一个或多个这些测试（例如 DataConference），将出现错误。 在这种情况下，你将收到类似于以下内容的错误消息：

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

发生此错误时，将不会应用任何更改。 应重新运行该命令，并删除重复的测试。

若要从观察程序节点中删除合成事务，请使用 Remove 方法，而不是 Add 方法。 例如，此命令将从观察程序节点中删除 ABWQ 测试：

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

你还可以使用 Replace 方法将当前启用的所有测试替换为一个或多个新测试。 例如，如果你只希望观察程序节点运行 IM 测试，则可以通过使用以下命令来配置它：

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

运行上述命令时，将禁用指定的观察程序节点上的所有合成事务，IM 除外。

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a>查看和测试观察程序节点配置

如果要查看已分配给观察程序节点的测试，请使用类似下面的命令：

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

上述命令将根据分配给节点的合成事务返回类似于此的信息：

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
> 若要按字母顺序查看合成事务，请改用以下命令：<BR>CsWatcherNodeConfiguration-Identity "atl-cs-001.litwareinc.com" |Select-对象-ExpandProperty 测试 |排序-对象



</div>

若要验证是否已创建观察程序节点，请在 Lync Server 命令行管理程序中键入以下命令：

    Get-CsWatcherNodeConfiguration

您将收到类似以下内容的信息：

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

若要验证是否正确配置了观察程序节点，请在 Lync Server 命令行管理程序中键入以下命令：

    Test-CsWatcherNodeConfiguration

前面的命令将在你的部署中测试每个观察程序节点并告诉你信息，例如：

  - 已安装所需的注册机构角色。

  - 当你运行 CsWatcherNodeConfiguration 时，将为你创建所需的注册表项。

  - 您的服务器运行的是正确版本的 Lync Server。

  - 您的端口配置正确。

  - 您分配的测试用户具有所需的凭据。

</div>

</div>

<span> </span>

</div>

</div>

</div>

