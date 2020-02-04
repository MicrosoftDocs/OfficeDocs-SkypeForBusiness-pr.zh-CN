---
title: Lync Server 2013：设置 Kerberos 身份验证帐户密码
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication account passwords
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48185167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c156e26a54e9762b1b57d1513f37cb7d7088cee
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a>在 Lync Server 2013 中设置 Kerberos 身份验证帐户密码

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2010-11-03_

为 Kerberos 身份验证帐户创建计算机对象后，您可以为该帐户设置密码。 在一台服务器上运行用于设置 Kerberos 帐户密码的 Windows PowerShell cmdlet。 你可以在为 Kerberos 身份验证创建的对象上设置密码。 密码可以设置为已知值，但默认情况下是随机密码。 密码可用于使用该帐户的所有 Kerberos 身份验证源。 你可以使用 Windows PowerShell cmdlet 设置和管理 Kerberos 帐户密码。

<div>


> [!NOTE]  
> Kerberos 帐户对象是一个计算机对象，但对所引用的 Windows PowerShell cmdlet 中的操作使用 UserAccount 参数。 请注意，这不是错误，但在与 Kerberos 帐户创建和维护一起使用时，该 cmdlet 的预期行为。



</div>

<div>

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 中在服务器上设置 Kerberos 身份验证帐户密码](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [在 Lync Server 2013 中将 Kerberos 身份验证帐户密码同步到 IIS](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

