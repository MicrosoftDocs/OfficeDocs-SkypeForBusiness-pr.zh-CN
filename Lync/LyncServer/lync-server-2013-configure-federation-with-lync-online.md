---
title: Lync Server 2013：配置与 Lync Online 的联合身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation with Lync Online
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205126(v=OCS.15)
ms:contentKeyID: 48184946
ms.date: 08/15/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 957a0f338d0669d0c99570b541d6ddb4753c1145
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a>使用 Lync Online 配置 Lync Server 2013 联盟

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-08-15_

按照本节中的步骤操作，在本地部署和 Skype for business Online 之间配置互操作性。

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a>为使用 Skype for Business Online 的联盟配置本地边缘服务

联合身份验证允许本地部署中的用户与组织中的 Office 365 用户进行通信。 若要配置联合，请运行以下 cmdlet：

   ```powershell
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```powershell
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a>为共享的 SIP 地址空间配置 Skype for Business Online 租户

会话初始协议（SIP）地址是网络上每个用户的唯一标识符，类似于电话号码或电子邮件地址。 在尝试将 Lync 用户从本地迁移到 Skype for business Online 之前，需要将 Office 365 租户配置为与本地部署共享共享会话初始协议（SIP）地址空间。 如果未配置此设置，您可能会看到以下错误消息：

Move-Get-csuser： HostedMigration fault： Error = （510），Description = （此用户的租户未启用共享 sip 地址空间。）

若要配置共享 SIP 地址空间，请建立与 Skype for Business Online 的远程 PowerShell 会话，然后运行以下 cmdlet：
```powershell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```
若要建立与 Skype for Business Online 的远程 PowerShell 会话，首先需要安装可在此处获取的适用于 Windows PowerShell 的 Skype for Business Online 模块： [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911)。

安装该模块后，可以使用以下 cmdlet 建立远程会话：

   ```powershell
    Import-Module LyncOnlineConnector
   ```

   ```powershell
    $cred = Get-Credential
   ``` 

   ```powershell
    $CSSession = New-CsOnlineSession -Credential $cred
   ```

   ```powershell
    Import-PSSession $CSSession -AllowClobber
   ```

有关如何与 Skype for Business Online 建立远程 PowerShell 会话的详细信息，请参阅[使用 Windows PowerShell 连接到 Skype for Business online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。

有关使用 Skype for Business Online PowerShell 模块的详细信息，请参阅[使用 Windows PowerShell 管理 skype For Business online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。

</div>

<div>

## <a name="see-also"></a>另请参阅


[新 CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

