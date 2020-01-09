---
title: Lync Server 2013：更新-通讯簿管理的 CsAddressBook
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Update-CsAddressBook for Address Book management
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429695(v=OCS.15)
ms:contentKeyID: 48183428
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7e10f9d52d9e4090601330cad44d5da03e69540
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="b6443-102">CsAddressBook-Lync Server 2013 中的通讯簿管理的更新</span><span class="sxs-lookup"><span data-stu-id="b6443-102">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6443-103">_**主题上次修改时间：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b6443-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b6443-104">哪些人可以运行此 cmdlet：默认情况下，以下组的成员授权在本地运行 CsAddressBook cmdlet： RTCUniversalUserAdmins、RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="b6443-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Update-CsAddressBook cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span> <span data-ttu-id="b6443-105">若要返回此 cmdlet 已分配到的所有基于角色的访问控制（RBAC）角色的列表（包括你自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="b6443-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

<span data-ttu-id="b6443-106">CsAddressBook cmdlet 替换 Office 通信服务器中的**abserver-syncNow**命令。</span><span class="sxs-lookup"><span data-stu-id="b6443-106">The Update-CsAddressBook cmdlet replaces the **abserver.exe –syncNow** command from Office Communications Server.</span></span> <span data-ttu-id="b6443-107">该 cmdlet 的用途是立即启动同步，而不是等待计划的时间。</span><span class="sxs-lookup"><span data-stu-id="b6443-107">The cmdlet’s purpose is to initiate a synchronization immediately rather than waiting for the scheduled time.</span></span> <span data-ttu-id="b6443-108">第一个示例命令将更新组织中的所有通讯簿。</span><span class="sxs-lookup"><span data-stu-id="b6443-108">The first example command updates all Address Books in the organization.</span></span> <span data-ttu-id="b6443-109">第二个更新仅更新与已定义服务器相关联的通讯簿。</span><span class="sxs-lookup"><span data-stu-id="b6443-109">The second updates only the Address Book associated with the defined server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b6443-110">在 Lync Server 2013 中，Lync Server 用户复制程序将从 Active Directory 中获取更改，并根据配置的间隔更新 Lync Server 用户数据库。</span><span class="sxs-lookup"><span data-stu-id="b6443-110">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="b6443-111">Lync Server 用户复制程序还将在无需运行 CSAddressBook 的情况下快速将更改传播到 RTCab 数据库。</span><span class="sxs-lookup"><span data-stu-id="b6443-111">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="b6443-112">只有当通讯簿文件下载已启用时，管理员才需要运行 CSAddressBook 更新。</span><span class="sxs-lookup"><span data-stu-id="b6443-112">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>



</div>

<span data-ttu-id="b6443-113">例如：</span><span class="sxs-lookup"><span data-stu-id="b6443-113">For example:</span></span>

   ```PowerShell
    Update-CsAddressBook
   ```

   ```PowerShell
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a><span data-ttu-id="b6443-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6443-114">See Also</span></span>


[<span data-ttu-id="b6443-115">Update-CsAddressBook</span><span class="sxs-lookup"><span data-stu-id="b6443-115">Update-CsAddressBook</span></span>](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

