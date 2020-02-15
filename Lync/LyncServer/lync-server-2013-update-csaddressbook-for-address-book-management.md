---
title: Lync Server 2013：用于通讯簿管理的 CsAddressBook 更新程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Update-CsAddressBook for Address Book management
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429695(v=OCS.15)
ms:contentKeyID: 48183428
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffc956465d4ebc1da95289897a7eb81b0f8f8e68
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a>Lync Server 2013 中的 CsAddressBook for Address Book management

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 Update-CsAddressBook cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

Update-CsAddressBook cmdlet 可替代 Office Communications Server 中的 **abserver.exe –syncNow** 命令。该 cmdlet 的用途是立即启动同步，而不是等到安排的时间才启动。第一个示例命令更新组织中的所有通讯簿。第二个示例命令仅更新与定义的服务器关联的通讯簿。

<div>


> [!NOTE]  
> 在 Lync Server 2013 中，Lync Server 用户复制器将从 Active Directory 中获取更改，并根据配置的间隔更新 Lync Server 用户数据库。 Lync Server 用户复制程序还会快速将更改传播到 RTCab 数据库，而管理员必须运行更新-CSAddressBook。 只有在启用了通讯簿文件下载时，管理员才需要运行 CSAddressBook 更新。



</div>

例如：

   ```PowerShell
    Update-CsAddressBook
   ```

   ```PowerShell
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a>请参阅


[更新-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

