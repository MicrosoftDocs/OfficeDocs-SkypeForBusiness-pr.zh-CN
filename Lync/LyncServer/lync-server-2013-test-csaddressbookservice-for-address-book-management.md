---
title: 'Lync Server 2013: 针对通讯簿管理的测试 CsAddressBookService'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test-CsAddressBookService for Address Book management
ms:assetid: b88cea74-41fd-4c0e-9284-7135bff27a27
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429720(v=OCS.15)
ms:contentKeyID: 48185206
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 120a61ff03957a25cb7e6e0d09b8d3bccb11343c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-csaddressbookservice-for-address-book-management-in-lync-server-2013"></a>CsAddressBookService 在 Lync Server 2013 中的通讯簿管理的测试

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

哪些人可以运行此 cmdlet: 默认情况下, 已授权以下组的成员运行 CsAddressBookService cmdlet: RTCUniversalServerAdmins。 若要返回此 cmdlet 已分配到的所有基于角色的访问控制 (RBAC) 角色的列表 (包括你自己创建的任何自定义 RBAC 角色), 请从 Windows PowerShell 提示符处运行以下命令:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

Lync Server 2013 包含许多用于启动合成命令的 cmdlet, 用于确认特定的函数或功能是否正常工作。 Test-CsAddressBookService 确认已定义的用户可以通过通讯簿 Web 服务连接和请求本地文件。

例如：

    Test-CsAddressBookService -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a>另请参阅


[Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

