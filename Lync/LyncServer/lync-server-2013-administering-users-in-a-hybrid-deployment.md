---
title: Lync Server 2013：在混合部署中管理用户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a82cb5ae505db5db3bbd8dd216ad61256368814e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "41998737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a>在混合 Lync Server 2013 部署中管理用户

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-05-29_

您可以使用 Microsoft Office 365 Online 门户中提供的用户管理功能来管理迁移到 Lync Online 的用户的用户设置和策略。 必须使用租户管理员帐户登录才能执行管理任务。

<div>

## <a name="moving-users-back-to-on-premises"></a>将用户移回本地部署

<div class="">


> [!IMPORTANT]  
> 此部分仅适用于为本地 Lync 创建和启用的用户，然后将从本地部署移动到 Lync Online。 如果要移动在 Lync Online 中创建的用户（在本地部署中未启用 Lync），请参阅 Lync Server 2013 中的将<A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">用户从 Lync Online 迁移到 Lync 本地</A>。



</div>

  - 运行以下 cmdlet 以将用户从 Lync Online 移动回本地 Lync：
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

为**HostedMigrationOverrideUrl**参数指定的 url 的格式必须是运行托管迁移服务的池的 url，格式如下：

Https://\<池 FQDN\>/hostedmigration/hostedmigrationservice.svc。 您可以通过查看适用于 Office 365 租户帐户的 Lync Online 控制面板的 URL 来确定托管迁移服务的 URL。

**确定 Office 365 租户的托管迁移服务 URL**

1.  以管理员身份登录到 Office 365 租户。

2.  打开**Lync 管理中心**。

3.  在 " **Lync 管理中心**" 显示的情况下，选择并将地址栏中的 URL 复制到**lync.com**。 示例 URL 的外观类似于以下内容：
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  将 URL 中的**webdir**替换为**admin**，从而产生以下结果：
    
    `https://admin0a.online.lync.com`

5.  将以下字符串追加到 URL： **/HostedMigration/hostedmigrationservice.svc**。
    
    生成的 URL （ **HostedMigrationOverrideUrl**的值）应如下所示：
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

