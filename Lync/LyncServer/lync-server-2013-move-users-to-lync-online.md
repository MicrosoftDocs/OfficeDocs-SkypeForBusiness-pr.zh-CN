---
title: Lync Server 2013：将用户移至 Lync Online
TOCTitle: 将用户移至 Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204969(v=OCS.15)
ms:contentKeyID: 49313127
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中将用户移至 Lync Online

 

_**上一次修改主题：** 2014-05-29_

在开始将用户迁移至 Lync Online 之前，应备份与要移动的帐户关联的用户数据。并非所有用户数据都会与用户帐户一并移动。有关详细信息，请参阅 [备份和还原要求：数据](lync-server-2013-backup-and-restoration-requirements-data.md)。

## 将用户设置迁移至 Lync Online

用户设置随用户帐户一起移动。一些本地设置不随用户帐户一起移动。

## 将试验用户移至 Lync Online

在开始将用户移至 Lync Online 之前，您可能需要移动一些试验用户来确认正确配置了环境。然后，您可以在尝试移动其他用户之前验证 Lync 功能和服务是否按预期运行。

若要将本地用户移至您的 Skype for Business Online 租户，请在 Lync Server 命令行管理程序中使用您的 Microsoft Office 365 租户的管理员凭据运行以下 cmdlet。使用要移动的用户的信息替换“username@contoso.com”。

    $creds=Get-Credential

   &nbsp;

    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

为 **HostedMigrationOverrideUrl** 参数指定的 URL 的格式必须为托管迁移服务在其中运行的池的 URL，格式如下：*Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc*。

您可以通过查看 Office 365 租户帐户的 Lync Online 控制面板的 URL 来确定托管迁移服务的 URL。

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

## 将用户移至 Lync Online

您可以通过使用带有 –Filter 参数的 [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) cmdlet 选择具有分配给用户帐户的特定属性（例如 RegistrarPool）的用户来移动多个用户。然后，您可以将返回的用户通过管道传递到 [Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Move-CsUser) cmdlet，如下面的示例所示。

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

您还可以使用 –OU 参数检索指定 OU 中的所有用户，如下面的示例所示。

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

## 验证 Lync Online 用户设置和功能

可通过以下方式验证用户是否已成功移动：

  - 在 Lync Online 控制面板中查看用户的状态。用于内部用户和联机用户的可视指示器不同。

  - 运行以下 cmdlet：
    
        Get-CsUser -Identity

