---
title: Lync Server 2013：配置与 Lync Online 的联盟
TOCTitle: 配置与 Lync Online 的联盟
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205126(v=OCS.15)
ms:contentKeyID: 49313778
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置 Lync Server 2013 与 Lync Online 的联盟

 

_**上一次修改主题：** 2016-12-08_

执行本节中的步骤来配置您的内部部署和 Skype for Business Online 之间的互操作性。

## 配置本地边缘服务以实现与 Skype for Business Online 的联盟

联盟允许本地部署中的用户与组织内的 Office 365 用户通信。若要配置联盟，请运行以下 cmdlet：

    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting

   &nbsp;

    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root

## 针对共享 SIP 地址空间配置您的 Skype for Business Online 租户

会话初始协议 (SIP) 地址是网络上各用户的唯一标识符，类似于电话号码或电子邮件地址。在尝试将 Lync 用户从本地迁移到 Skype for Business Online 之前，您需要将 Office 365 租户配置为与本地部署共享共享会话初始协议 (SIP) 地址空间。如果未进行此配置，您可能会看到以下错误消息：

Move-CsUser : HostedMigration 错误: Error=(510), 描述=(没有为此用户的租户启用共享 sip 地址空间。)

要配置共享 SIP 地址空间，请建立与 Skype for Business Online 的远程 PowerShell 会话，然后运行以下 cmdlet：

    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true

要建立与 Skype for Business Online 的远程 PowerShell 会话，首先要安装 Windows PowerShell 的 Skype for Business Online 模块（可从此处获取：[http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911)）。

安装该模块后，您可以使用下列 cmdlet 建立远程会话：

    Import-Module LyncOnlineConnector

   &nbsp;

    $cred = Get-Credential

   &nbsp;

    $CSSession = New-CsOnlineSession -Credential $cred

   &nbsp;

    Import-PSSession $CSSession -AllowClobber

有关如何建立与 Skype for Business Online 的远程 PowerShell 会话的详细信息，请参阅[使用 Windows PowerShell 连接到 Lync Online](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。

有关如何使用 Skype for Business Online PowerShell 模块的详细信息，请参阅 [使用 Windows PowerShell 管理 Lync Online](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。

## 另请参阅

#### 其他资源

[New-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider)

