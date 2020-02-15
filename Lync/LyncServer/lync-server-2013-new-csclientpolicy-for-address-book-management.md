---
title: Lync Server 2013： Set-csclientpolicy for Address Book management
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
ms.openlocfilehash: f84ef03f782263ed9f82b1667418c907087f5d5c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-csclientpolicy-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="ebc5e-102">Lync Server 2013 中的 Set-csclientpolicy for Address Book management</span><span class="sxs-lookup"><span data-stu-id="ebc5e-102">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebc5e-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ebc5e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ebc5e-104">谁能运行此 cmdlet：默认情况下，以下各组的成员有权运行 New-CsClientPolicy cmdlet：RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="ebc5e-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsClientPolicy cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="ebc5e-105">要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="ebc5e-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

<span data-ttu-id="ebc5e-106">Cmdlet Set-csclientpolicy 定义了大量设置，用于为 Lync Server 2013 中提供的功能设置客户端。</span><span class="sxs-lookup"><span data-stu-id="ebc5e-106">The cmdlet New-CsClientPolicy defines a large number of settings for provisioning clients for features that are available in Lync Server 2013.</span></span> <span data-ttu-id="ebc5e-107">对于通讯簿服务，参数 AddressBookAvailability 很重要。</span><span class="sxs-lookup"><span data-stu-id="ebc5e-107">For the Address Book Service, the parameter AddressBookAvailability is of interest.</span></span> <span data-ttu-id="ebc5e-108">此参数会直接影响可用于客户端的选项，具有三个可能的选项：</span><span class="sxs-lookup"><span data-stu-id="ebc5e-108">This parameter, which directly impacts the options available to clients, has three possible options:</span></span>

  - <span data-ttu-id="ebc5e-109">WebSearchAndFileDownload</span><span class="sxs-lookup"><span data-stu-id="ebc5e-109">WebSearchAndFileDownload</span></span>

  - <span data-ttu-id="ebc5e-110">WebSearchOnly</span><span class="sxs-lookup"><span data-stu-id="ebc5e-110">WebSearchOnly</span></span>

  - <span data-ttu-id="ebc5e-111">FileDownloadOnly</span><span class="sxs-lookup"><span data-stu-id="ebc5e-111">FileDownloadOnly</span></span>

<span data-ttu-id="ebc5e-p103">在定义此参数时，便确定了客户端访问通讯簿的方式。如果定义此参数，必须定义以上选项之一。如果不修改此设置，则仍将使用默认值 WebSearchAndFileDownload。</span><span class="sxs-lookup"><span data-stu-id="ebc5e-p103">When defined, it determines how the Address Book is accessed by clients. If you define this parameter, you must define one of the options. If you do not modify this setting, the default WebSearchAndFileDownload remains in effect.</span></span>

<span data-ttu-id="ebc5e-115">例如：</span><span class="sxs-lookup"><span data-stu-id="ebc5e-115">For example:</span></span>

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

<div>

## <a name="see-also"></a><span data-ttu-id="ebc5e-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="ebc5e-116">See Also</span></span>


[<span data-ttu-id="ebc5e-117">新 Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="ebc5e-117">New-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

