---
title: Lync Server 2013：（可选）验证电话拨入式会议
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify dial-in conferencing
ms:assetid: 3e2b4220-8fb3-442f-98b1-78447adb321f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425905(v=OCS.15)
ms:contentKeyID: 48183941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1b5f078ccd5e95df708012b7be1527736133392
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755696"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-dial-in-conferencing-in-lync-server-2013"></a>（可选）在 Lync Server 2013 中验证电话拨入式会议

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2011-01-21_

要验证“电话拨入式会议设置”网页和拨入访问号码是否工作正常，您需要执行以下操作：

  - 通过登录简单 URL 来测试“电话拨入式会议设置”网页。

  - 通过运行本主题后面的脚本来测试该访问号码在特定池中是否工作正常。此脚本模拟对访问号码的呼叫。要使用此脚本，需要提供该特定池承载的一个统一通信 (UC) 客户端的 SIP 地址和凭据。

此步骤是可选的。

<div>

## <a name="to-test-access-numbers-for-a-specific-pool"></a>测试特定池的访问号码

1.  以 RTCUniversalServerAdmins 组成员的身份登录计算机，或者作为**Cs-ServerAdministrator**或**CsAdministrator**角色的成员登录到计算机。

2.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

3.  在命令提示符下，运行以下内容：
    
        $credentials = Get-Credential
           User name:  testuser1@contoso.com
           Password:   ********
        Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
    
    得出的报告将显示 Success 或 Failure，以及具体的诊断信息。–Verbose 标志提供有关查找到的访问号码数目及其详细信息的更多详情。

</div>

</div>

<span> </span>

</div>

</div>

</div>

