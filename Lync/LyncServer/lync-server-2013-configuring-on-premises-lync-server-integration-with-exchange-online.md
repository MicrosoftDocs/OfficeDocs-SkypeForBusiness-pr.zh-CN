---
title: Lync Server 2013：配置本地 Lync Server 与 Exchange Online 的集成
TOCTitle: 配置本地 Lync Server 2013 与 Exchange Online 的集成
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh533880(v=OCS.15)
ms:contentKeyID: 49313652
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置本地 Lync Server 2013 与 Exchange Online 的集成

 

_**上一次修改主题：** 2014-07-02_

使用本地 Lync Server 2013 部署的用户可在混合部署模式中配置与 Microsoft Exchange Online 中的 Microsoft Outlook Web App 的互操作性。互操作性功能包括单一登录和即时消息 (IM) 以及与 Outlook Web App 接口的状态集成。若要实现此集成，您必须通过完成以下任务在您的本地 Lync Server 部署中配置 边缘服务器：

  - 配置共享的 SIP 地址空间

  - 在 边缘服务器上配置宿主提供程序

  - 确保复制更新后的 中央管理存储

## 配置共享的 SIP 地址空间

若要将本地 Lync Server 2013 与 Exchange Online 集成，您必须配置一个共享 SIP 地址空间。同一个 SIP 域地址空间同时受 Lync Server 和 Exchange Online 服务的支持。

利用 Lync Server 命令行管理程序，可通过使用以下示例中所示的参数运行 **Set-CSAccessEdgeConfiguration** cmdlet 来为联盟配置 边缘服务器：

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - **AllowFederatedUsers** 参数指定是否允许内部用户与联盟域中的用户进行通信。此属性还确定内部用户是否能够与包含 Lync Server 和 Exchange Online 的共享 SIP 地址空间方案中的用户进行通信。

有关使用 Lync Server 命令行管理程序的详细信息，请参阅 [Lync Server 命令行管理程序](lync-server-2013-lync-server-management-shell.md)。

## 在边缘服务器上配置宿主提供程序

利用 Lync Server 命令行管理程序，可通过使用以下示例中的参数运行 **New-CsHostingProvider** cmdlet 来在 边缘服务器上配置宿主提供程序：

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

> [!NOTE]  
> 如果您在中国使用 Office 365 世纪互联运营，请将此示例中 <strong>ProxyFqdn</strong> 参数的值替换为服务世纪互联运营的 FQDN“exap.um.partner.outlook.cn”。



  - **Identity** 将为您创建的宿主提供程序指定一个唯一的字符串值标识符（例如“Exchange Online”）。包含空格的值必须用双引号括起来。

  - **Enabled** 指示是否在域和宿主提供程序之间启用网络连接。必须将其设置为 True。

  - **EnabledSharedAddressSpace** 指示是否将在共享的 SIP 地址空间方案中使用托管提供程序。必须将其设置为 True。

  - **HostsOCSUsers** 指示是否将托管提供程序用于承载 Office Communications Server 或 Lync Server。必须将其设置为 False。

  - **ProxyFQDN** 指定宿主提供程序所使用的代理服务器的完全限定的域名 (FQDN)。对于 Exchange Online，FQDN 为 exap.um.outlook.com。

  - **IsLocal** 指示宿主提供程序所使用的代理服务器是否包含在 Lync Server 拓扑中。必须将其设置为 False。

  - **VerificationLevel** 指示在宿主提供程序中发送和接收的邮件所允许的验证级别。指定 **UseSourceVerification**，它依赖于从宿主提供程序发送的邮件中包含的验证级别。如果未指定此级别，则邮件将因未验证而被拒绝。

## 确保复制更新后的中央管理存储

您在前面各节中使用 cmdlet 所做的更改将自动应用于 边缘服务器，通常，复制所花费的时间少于一分钟。您可以验证复制状态，然后使用以下 cmdlet 验证是否已将这些更改应用于 边缘服务器。

若要验证复制更新，请在 Lync Server 部署中的内部服务器上，运行以下 cmdlet：

    Get-CsManagementStoreReplicationStatus

若要确保已应用更改，请在 边缘服务器上运行以下 cmdlet：

    Get-CsHostingProvider -LocalStore

## 另请参阅

#### 其他资源

[在托管 Exchange UM 上提供 Lync Server 2013 用户语音邮件](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[Lync Server 2013 中的托管 Exchange 统一消息集成](lync-server-2013-hosted-exchange-unified-messaging-integration.md)

