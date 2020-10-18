---
title: Lync Server 2013：用于通讯簿管理的 New-CsAddressBookConfiguration
description: Lync Server 2013：用于通讯簿管理的 New-CsAddressBookConfiguration。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsAddressBookConfiguration for Address Book management
ms:assetid: a58ddc8c-ae04-4141-b69e-e45374a67d72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429718(v=OCS.15)
ms:contentKeyID: 48184985
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c85d85fefe701456ad253f1afc69b73093b30996
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578948"
---
# <a name="new-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="f4f88-103">Lync Server 2013 中的通讯簿管理 New-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="f4f88-103">New-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4f88-104">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f4f88-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f4f88-p101">谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 New-CsAddressBookConfiguration cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f4f88-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsAddressBookConfiguration"}

<span data-ttu-id="f4f88-p102">New-CsAddressBookConfiguration cmdlet 会创建新的配置以管理通讯簿的行为。此 cmdlet 特定的功能是定义通讯簿服务是否创建客户端下载文件、是否以及如何使用规范化规则、保留增量文件和压缩增量文件的时间长度、融入新的完全文件创建之前的增量文件大小、创建完全文件通讯簿的时间，以及用户数据库中信息同步的内部内容。</span><span class="sxs-lookup"><span data-stu-id="f4f88-p102">The New-CsAddressBookConfiguration cmdlet creates a new configuration to manage the behavior of the Address book. Specific to this cmdlet is the ability to define if the Address Book Service creates the client download files, how and if normalization rules are used, how long to retain delta and compact delta files, delta file size before incorporating a new full file creation, what time of day the full file Address Book is created, and what the internal should be for synchronization of information in the User database.</span></span>

<span data-ttu-id="f4f88-109">例如：</span><span class="sxs-lookup"><span data-stu-id="f4f88-109">For example:</span></span>

    New-CsAddressBookConfiguration -Identity site:Redmond -KeepDuration 15 -SynchronizePollingInterval 00:10:00

<div>

## <a name="see-also"></a><span data-ttu-id="f4f88-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="f4f88-110">See Also</span></span>


[<span data-ttu-id="f4f88-111">新 CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="f4f88-111">New-CsAddressBookConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

