---
title: 配置本地 Lync Server 与 Exchange Online 的集成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring on-premises Lync Server integration with Exchange Online
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh533880(v=OCS.15)
ms:contentKeyID: 48184900
ms.date: 03/30/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60cfa8caa0aa2cb7dac704123f2a099bd305aed5
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a>配置本地 Lync Server 2013 与 Exchange Online 集成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2018-03-30_

使用本地 Lync Server 2013 部署的客户可以在混合部署模式下在 Microsoft Exchange Online 中配置与 Microsoft Outlook Web App 的互操作性。 互操作性功能包括单一登录和即时消息（IM）以及与 Outlook Web App 界面的状态集成。 若要启用此集成，您必须完成以下任务，在本地 Lync Server 部署中配置边缘服务器：

  - 配置共享 SIP 地址空间

  - 在边缘服务器上配置托管提供程序

  - 验证更新的中央管理存储的复制

如果 Lync Server 2013 与 Exchange Online 集成，则尝试从 OWA 登录 IM 的用户被视为远程用户或外部用户。 在这种情况下，必须为此用户分配一个已选择以下选项的外部访问策略：

**启用与远程用户的通信**

如果您希望组织中的用户（如正在旅行的远程办公和用户）能够通过 Internet 连接到 Lync Server，请启用此选项。

有关详细信息，请参阅[在 Lync Server 2013 中管理外部访问策略](lync-server-2013-manage-external-access-policy-for-your-organization.md)。

<div>

## <a name="configure-a-shared-sip-address-space"></a>配置共享 SIP 地址空间

若要将本地 Lync Server 2013 与 Exchange Online 集成，必须配置共享 SIP 地址空间。 Lync Server 和 Exchange Online 服务均支持相同的 SIP 域地址空间。

使用 Lync Server 命令行管理程序，使用以下示例中显示的参数运行**set-csaccessedgeconfiguration** cmdlet，从而配置边缘服务器以进行联合身份验证：

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - **AllowFederatedUsers** 指定是否允许内部用户与来自联盟域的用户进行通信。 此属性还确定内部用户是否可以使用 Lync Server 和 Exchange Online 与共享 SIP 地址空间方案中的用户进行通信。

有关如何使用 Lync Server 命令行管理程序的详细信息，请参阅[Lync server 2013 命令行管理](lync-server-2013-lync-server-management-shell.md)程序。

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>在边缘服务器上配置托管提供程序

使用 Lync Server 命令行管理程序在边缘服务器上配置托管提供程序。 为此，请使用以下示例中的参数运行**CsHostingProvider** cmdlet：

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> 如果使用由世纪互联运营的 Office 365，请将此示例（"exap.um.outlook.com"）中的<STRONG>ProxyFqdn</STRONG>参数的值替换为由世纪互联运营的服务的 FQDN： "exap.um.partner.outlook.cn"。



</div>

  - **Identity**为要创建的宿主提供程序指定唯一的字符串值标识符（例如，"Exchange Online"）。 包含空格的值必须用双引号引起来。

  - **Enabled** 指示您的域与承载服务提供商之间的网络连接是否已启用。 必须将其设置为**True**。

  - **EnabledSharedAddressSpace** 指示是否要在共享 SIP 地址空间方案中使用承载服务提供商。 必须将其设置为**True**。

  - **HostsOCSUsers**指示承载提供程序是否用于承载 Office 通信服务器或 Lync Server。 必须将其设置为**False**。

  - **ProxyFQDN** 指定托管服务提供商使用的代理服务器的完全限定的域名 (FQDN)。 对于 Exchange Online，FQDN 为 exap.um.outlook.com。

  - **IsLocal**指示承载提供程序使用的代理服务器是否包含在你的 Lync server 拓扑中。 必须将其设置为**False**。

  - **VerificationLevel**指示对托管提供程序发送和接收的邮件允许的验证级别。 指定**UseSourceVerification**。 此选项依赖于从托管提供程序发送的邮件中包含的验证级别。 如果未指定此级别，则邮件将因无法验证而被拒绝。

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a>验证更新的中央管理存储的复制

使用前面各节中的 cmdlet 所做的更改将自动应用于边缘服务器，并且通常需要不到一分钟的时间来进行复制。 您可以使用以下 cmdlet 验证复制状态以及是否已将更改应用到边缘服务器。

若要验证 Lync Server 部署中的内部服务器上的复制更新，请运行以下 cmdlet：

    Get-CsManagementStoreReplicationStatus

若要验证是否已应用所做的更改，请在边缘服务器上运行以下 cmdlet：

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a>另请参阅


[在托管 Exchange UM 上提供 Lync Server 2013 用户语音邮件](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[Lync Server 2013 中的托管 Exchange 统一消息集成](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
