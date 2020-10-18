---
title: Lync Server 2013：用于通讯簿管理的 New-CsClientPolicy
description: Lync Server 2013：用于通讯簿管理的 New-CsClientPolicy。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsClientPolicy for Address Book management
ms:assetid: ef4415fc-82c4-4dc8-97d1-37a084553343
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429726(v=OCS.15)
ms:contentKeyID: 48185771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12c14534c7af447f30a01b1bbbd1679a8375c705
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578928"
---
# <a name="new-csclientpolicy-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="3d215-103">Lync Server 2013 中的通讯簿管理 New-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="3d215-103">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d215-104">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3d215-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3d215-105">谁能运行此 cmdlet：默认情况下，以下各组的成员有权运行 New-CsClientPolicy cmdlet：RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="3d215-105">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsClientPolicy cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="3d215-106">要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="3d215-106">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

<span data-ttu-id="3d215-107">Cmdlet New-CsClientPolicy 定义大量设置，用于为 Lync Server 2013 中提供的功能设置客户端。</span><span class="sxs-lookup"><span data-stu-id="3d215-107">The cmdlet New-CsClientPolicy defines a large number of settings for provisioning clients for features that are available in Lync Server 2013.</span></span> <span data-ttu-id="3d215-108">对于通讯簿服务，参数 AddressBookAvailability 很重要。</span><span class="sxs-lookup"><span data-stu-id="3d215-108">For the Address Book Service, the parameter AddressBookAvailability is of interest.</span></span> <span data-ttu-id="3d215-109">此参数会直接影响可用于客户端的选项，具有三个可能的选项：</span><span class="sxs-lookup"><span data-stu-id="3d215-109">This parameter, which directly impacts the options available to clients, has three possible options:</span></span>

  - <span data-ttu-id="3d215-110">WebSearchAndFileDownload</span><span class="sxs-lookup"><span data-stu-id="3d215-110">WebSearchAndFileDownload</span></span>

  - <span data-ttu-id="3d215-111">WebSearchOnly</span><span class="sxs-lookup"><span data-stu-id="3d215-111">WebSearchOnly</span></span>

  - <span data-ttu-id="3d215-112">FileDownloadOnly</span><span class="sxs-lookup"><span data-stu-id="3d215-112">FileDownloadOnly</span></span>

<span data-ttu-id="3d215-p103">在定义此参数时，便确定了客户端访问通讯簿的方式。如果定义此参数，必须定义以上选项之一。如果不修改此设置，则仍将使用默认值 WebSearchAndFileDownload。</span><span class="sxs-lookup"><span data-stu-id="3d215-p103">When defined, it determines how the Address Book is accessed by clients. If you define this parameter, you must define one of the options. If you do not modify this setting, the default WebSearchAndFileDownload remains in effect.</span></span>

<span data-ttu-id="3d215-116">例如：</span><span class="sxs-lookup"><span data-stu-id="3d215-116">For example:</span></span>

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

<div>

## <a name="see-also"></a><span data-ttu-id="3d215-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d215-117">See Also</span></span>


[<span data-ttu-id="3d215-118">新 Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="3d215-118">New-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

