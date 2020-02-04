---
title: Lync Server 2013：更新-通讯簿管理的 CsAddressBook
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
ms.openlocfilehash: f03fe225b2eae508870220e278d7bfc3373dad22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a>CsAddressBook-Lync Server 2013 中的通讯簿管理的更新

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-11-01_

哪些人可以运行此 cmdlet：默认情况下，以下组的成员授权在本地运行 CsAddressBook cmdlet： RTCUniversalUserAdmins、RTCUniversalServerAdmins。 若要返回此 cmdlet 已分配到的所有基于角色的访问控制（RBAC）角色的列表（包括你自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

CsAddressBook cmdlet 替换 Office 通信服务器中的**abserver-syncNow**命令。 该 cmdlet 的用途是立即启动同步，而不是等待计划的时间。 第一个示例命令将更新组织中的所有通讯簿。 第二个更新仅更新与已定义服务器相关联的通讯簿。

<div>


> [!NOTE]  
> 在 Lync Server 2013 中，Lync Server 用户复制程序将从 Active Directory 中获取更改，并根据配置的间隔更新 Lync Server 用户数据库。 Lync Server 用户复制程序还将在无需运行 CSAddressBook 的情况下快速将更改传播到 RTCab 数据库。 只有当通讯簿文件下载已启用时，管理员才需要运行 CSAddressBook 更新。



</div>

例如：

   ```PowerShell
    Update-CsAddressBook
   ```

   ```PowerShell
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a>另请参阅


[Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

