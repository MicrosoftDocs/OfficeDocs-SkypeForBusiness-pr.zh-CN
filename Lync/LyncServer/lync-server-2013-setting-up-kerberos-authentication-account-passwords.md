---
title: Lync Server 2013：设置 Kerberos 身份验证帐户密码
description: Lync Server 2013：设置 Kerberos 身份验证帐户密码。
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
ms.openlocfilehash: 614b1411f9454c39843f4e69cabbfc3b02986e51
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577218"
---
# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a>在 Lync Server 2013 中设置 Kerberos 身份验证帐户密码

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2010-11-03_

为 Kerberos 身份验证帐户创建计算机对象后，即可设置该帐户的密码。 运行 Windows PowerShell cmdlet 以在一台服务器上设置 Kerberos 帐户密码。 可以在为 Kerberos 身份验证所创建的对象上设置密码。 可将密码设置为已知值，但默认情况下为随机密码。 该密码可用于所有使用该帐户的 Kerberos 身份验证源。 您可以使用 Windows PowerShell cmdlet 来设置和管理 Kerberos 帐户密码。

<div>


> [!NOTE]  
> Kerberos 帐户对象是一个计算机对象，但对 Windows PowerShell cmdlet 中所引用的操作使用 UserAccount 参数。 请注意，这并非错误，而是 cmdlet 在与 Kerberos 帐户创建和维护结合使用时的预期行为。



</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 中的服务器上设置 Kerberos 身份验证帐户密码](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [在 Lync Server 2013 中将 Kerberos 身份验证帐户密码同步到 IIS](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

