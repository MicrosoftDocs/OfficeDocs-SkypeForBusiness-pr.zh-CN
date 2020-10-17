---
title: Lync Server 2013：用于通讯簿管理的 Update-CsAddressBook
description: Lync Server 2013：用于通讯簿管理的 Update-CsAddressBook。
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
ms.openlocfilehash: 4adc7f94e2f31f64f6517b8cdf9bbcb0649f6c8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546238"
---
# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="39cee-103">Lync Server 2013 中的通讯簿管理 Update-CsAddressBook</span><span class="sxs-lookup"><span data-stu-id="39cee-103">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39cee-104">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="39cee-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="39cee-p101">谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 Update-CsAddressBook cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="39cee-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Update-CsAddressBook cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

<span data-ttu-id="39cee-p102">Update-CsAddressBook cmdlet 可替代 Office Communications Server 中的 **abserver.exe –syncNow** 命令。该 cmdlet 的用途是立即启动同步，而不是等到安排的时间才启动。第一个示例命令更新组织中的所有通讯簿。第二个示例命令仅更新与定义的服务器关联的通讯簿。</span><span class="sxs-lookup"><span data-stu-id="39cee-p102">The Update-CsAddressBook cmdlet replaces the **abserver.exe –syncNow** command from Office Communications Server. The cmdlet’s purpose is to initiate a synchronization immediately rather than waiting for the scheduled time. The first example command updates all Address Books in the organization. The second updates only the Address Book associated with the defined server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="39cee-111">在 Lync Server 2013 中，Lync Server 用户复制器将从 Active Directory 中获取更改，并根据配置的间隔更新 Lync Server 用户数据库。</span><span class="sxs-lookup"><span data-stu-id="39cee-111">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="39cee-112">Lync Server 用户复制程序还会快速将更改传播到 RTCab 数据库，而管理员必须运行更新-CSAddressBook。</span><span class="sxs-lookup"><span data-stu-id="39cee-112">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="39cee-113">只有在启用了通讯簿文件下载时，管理员才需要运行 CSAddressBook 更新。</span><span class="sxs-lookup"><span data-stu-id="39cee-113">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>



</div>

<span data-ttu-id="39cee-114">例如：</span><span class="sxs-lookup"><span data-stu-id="39cee-114">For example:</span></span>

   ```PowerShell
    Update-CsAddressBook
   ```

   ```PowerShell
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a><span data-ttu-id="39cee-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="39cee-115">See Also</span></span>


[<span data-ttu-id="39cee-116">更新-CsAddressBook</span><span class="sxs-lookup"><span data-stu-id="39cee-116">Update-CsAddressBook</span></span>](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

