---
title: Lync Server 2013：管理混合部署中的用户
TOCTitle: 管理混合部署中的用户
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204967(v=OCS.15)
ms:contentKeyID: 49313140
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 管理混合 Lync Server 2013 部署中的用户

 

_**上一次修改主题：** 2014-05-29_

可以使用 Microsoft Office 365 联机门户中提供的“用户管理”功能，管理迁移到 Lync Online 的用户的用户设置和策略。您必须使用租户管理员帐户登录才能执行管理任务。

## 将用户移回本地部署

> [!IMPORTANT]  
> 本节仅适用于最初为本地 Lync 创建和启用，随后从本地部署迁移到 Lync Online 的用户。如果您希望迁移先前在 Lync Online 中创建的用户（但并未为 Lync 本地部署启用），请参阅 <a href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">在 Lync Server 2013 中将 Lync Online 用户迁移至本地 Lync</a>。


  - 运行以下 cmdlet，将用户从 Lync Online 移回本地 Lync：
    
        $cred=Get-Credential

       &nbsp;
    
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>

为 **HostedMigrationOverrideUrl** 参数指定的 URL 的格式必须为托管迁移服务在其中运行的池的 URL，格式如下：

*Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc*。您可以通过查看 Office 365 租户帐户的 Lync Online 控制面板的 URL 来确定托管迁移服务的 URL。

**确定 Office 365 租户的托管迁移服务 URL**

1.  以管理员身份登录到 Office 365 租户。

2.  打开“Lync 管理中心”。

3.  显示“Lync 管理中心”后，选中并复制地址栏中一直到 **lync.com** 的 URL。示例 URL 如下所示：
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  将 URL 中的 **webdir** 替换为 **admin**，得到以下 URL：
    
    `https://admin0a.online.lync.com`

5.  向 URL 附加以下字符串：**/HostedMigration/hostedmigrationservice.svc**。
    
    得到的 URL 是 **HostedMigrationOverrideUrl** 的值，应类似于以下形式：
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

