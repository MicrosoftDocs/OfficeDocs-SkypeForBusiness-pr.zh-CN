---
title: Lync Server 2013：设置 Kerberos 身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication
ms:assetid: dd8009ef-6265-4cc0-b2c7-e474cd1f4b09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398976(v=OCS.15)
ms:contentKeyID: 48185601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c644dd613b3186b314e8fc78b42197709286200
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732212"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a>在 Lync Server 2013 中设置 Kerberos 身份验证

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-21_

Lync Server 2013 支持针对 Web 服务的 NTLM 和 Kerberos 身份验证。 Office 通信服务器2007和 Office 通信服务器 2007 R2 使用默认的 RTCComponentService 和 RTCService 作为运行 Web 服务应用程序池的用户帐户，从而允许将服务主体名称（SPN）分配给用户帐户并充当身份验证主体。 Lync Server 使用 NetworkService 运行 Web 服务，并且 NetworkService 无法为其分配 Spn。

为了解决没有 Active Directory 对象保留 Spn 的问题，Lync Server 控制面板可以使用计算机帐户对象来实现此目的。 计算机帐户对象可以保留 Spn，并且不受密码过期的限制，这是使用以前版本中的用户帐户时遇到的问题。

使用 Windows PowerShell cmdlet 配置计算机对象以提供 Kerberos 身份验证。

<div>

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 中启用 Kerberos 身份验证的先决条件](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [在 Lync Server 2013 中创建 Kerberos 身份验证帐户](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [在 Lync Server 2013 中将 Kerberos 身份验证帐户分配给站点](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [在 Lync Server 2013 中设置 Kerberos 身份验证帐户密码](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [在 Lync Server 2013 中向其他站点添加 Kerberos 身份验证](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [在 Lync Server 2013 中将 Kerberos 身份验证从站点中删除](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [在 Lync Server 2013 中测试和报告 Kerberos 身份验证的状态和分配](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

