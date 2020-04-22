---
title: Lync Server 2013：将用户移动到 Lync Online
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5106d4e27921d9407b2663410cc0872892479ebb
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a>在 Lync Server 2013 中将用户移动到 Lync Online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-05-29_

在开始将用户迁移到 Lync Online 之前，应备份与要移动的帐户关联的用户数据。 并不是所有用户数据都与用户帐户一起移动。 有关信息，请参阅[Lync Server 2013： data 中的备份和还原要求](lync-server-2013-backup-and-restoration-requirements-data.md)。

<div>

## <a name="migrate-user-settings-to-lync-online"></a>将用户设置迁移至 Lync Online

用户设置随用户帐户一起移动。 某些本地设置不会随用户帐户一起移动。

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a>将试点用户移动到 Lync Online

在开始将用户移动到 Lync Online 之前，您可能需要移动几个试点用户，以确认您的环境已正确配置。 然后，您可以在尝试移动其他用户之前验证 Lync 功能和服务是否按预期方式运行。

若要将本地用户移动到 Lync Online 租户，请使用 Microsoft Office 365 组织的管理员凭据在 Lync Server 命令行管理程序中运行以下 cmdlet。 将 "username@contoso.com" 替换为要移动的用户的信息。

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

为**HostedMigrationOverrideUrl**参数指定的 url 的格式必须是运行托管迁移服务的池的 url，格式如下： HTTPS://\<池 FQDN/hostedmigration/hostedmigrationservice.svc。\>

您可以通过查看 Office 365 组织帐户的 Lync Online 控制面板的 URL 来确定托管迁移服务的 URL。

**确定 Office 365 组织的托管迁移服务 URL**

1.  以管理员身份登录到 Office 365 组织。

2.  打开**Lync 管理中心**。

3.  在 " **Lync 管理中心**" 显示的情况下，选择并将地址栏中的 URL 复制到**lync.com**。 示例 URL 的外观类似于以下内容：
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  将 URL 中的**webdir**替换为**admin**，从而产生以下结果：
    
    `https://admin0a.online.lync.com`

5.  将以下字符串追加到 URL： **/HostedMigration/hostedmigrationservice.svc**。
    
    生成的 URL （ **HostedMigrationOverrideUrl**的值）应如下所示：
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a>将用户移动到 Lync Online

您可以使用带有– Filter 参数的[get-csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet 来移动多个用户，以选择具有分配给用户帐户的特定属性的用户，如 RegistrarPool。 然后，您可以通过管道将返回的用户通过管道传递到[get-csuser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) cmdlet，如以下示例所示。

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

您还可以使用– OU 参数检索指定 OU 中的所有用户，如下面的示例所示。

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a>验证 Lync Online 用户设置和功能

可通过以下方式验证用户是否已成功移动：

  - 在 Lync Online 控制面板中查看用户的状态。用于内部用户和联机用户的可视指示器不同。

  - 运行以下 cmdlet：
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

