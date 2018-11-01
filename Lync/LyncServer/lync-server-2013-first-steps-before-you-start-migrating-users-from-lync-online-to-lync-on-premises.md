---
title: 开始将用户从 Lync Online 迁移到本地 Lync 的第一步
TOCTitle: 开始将用户从 Lync Online 迁移到本地 Lync 的第一步
ms:assetid: 98245b04-ded4-4186-8da3-ba1c554b5c39
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn689118(v=OCS.15)
ms:contentKeyID: 62247374
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 开始将用户从 Lync Online 迁移到本地 Lync 的第一步

 

_**上一次修改主题：** 2016-12-08_

开始将 Lync Online 用户迁移到本地环境之前，请检查确保符合以下全部条件：

  - Lync Server 本地环境必须完全完成部署和验证。有关详细信息，请参阅 [部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)。

  - 您的 Lync Online 租户必须已配置远程 PowerShell 访问权限。
    
    为此，首先安装 Windows PowerShell 的 Skype for Business Online 模块，可通过此处下载此模块：[http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911)。
    
    安装模块后，可以在 Lync Server 命令行管理程序 中键入以下 cmdlet 建立远程会话：
    
        Import-Module LyncOnlineConnector

       &nbsp;
    
        $cred = Get-Credential

       &nbsp;
    
        $CSSession = New-CsOnlineSession -Credential $cred

       &nbsp;
    
        Import-PSSession $CSSession -AllowClobber
    
  有关如何建立与 Skype for Business Online 的远程 PowerShell 会话的详细信息，请参阅[使用 Windows PowerShell 连接到 Lync Online](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。
  
  有关如何使用 Skype for Business Online PowerShell 模块的详细信息，请参阅 [使用 Windows PowerShell 管理 Lync Online](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。

  - 您的 Lync Online 必须已针对共享 SIP 地址空间进行了配置。为此，首先启动 Powershell 与 Lync Online 的远程会话。然后运行以下 cmdlet：
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

完成这些步骤后，即可转到 [将 Lync Online 用户迁移至本地 Lync](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md)。

