---
title: Lync Server 2013：删除公共的区域电话联系人对象
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a common area phone Contact object
ms:assetid: f4c139dc-f07c-4c75-9345-e291aea41173
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994087(v=OCS.15)
ms:contentKeyID: 51803999
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a3088150c882a5ebca99318f7c85ddbddddc333
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="849fb-102">在 Lync Server 2013 中删除公用的 "区域电话联系人" 对象</span><span class="sxs-lookup"><span data-stu-id="849fb-102">Delete a common area phone Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="849fb-103">_**主题上次修改时间：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="849fb-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="849fb-104">您可能希望删除与普通的区域电话相关联的联系人对象。</span><span class="sxs-lookup"><span data-stu-id="849fb-104">You might want to delete the contact object associated with a common area phone.</span></span> <span data-ttu-id="849fb-105">例如，如果您从员工的工作人员那里删除手机，则无需具有与该电话关联的 contact 对象。</span><span class="sxs-lookup"><span data-stu-id="849fb-105">For example, if you remove the phone from an employee lounge, there’s no need to have a contact object associated with that phone.</span></span> <span data-ttu-id="849fb-106">**CsCommonAreaPhone** cmdlet 提供了一种删除公共区域电话帐户的方法。</span><span class="sxs-lookup"><span data-stu-id="849fb-106">The **Remove-CsCommonAreaPhone** cmdlet provides a way for you to delete common area phone accounts.</span></span> <span data-ttu-id="849fb-107">当你运行此 cmdlet 时，将从**CsCommonAreaPhone**返回的常用区域电话列表中删除手机。</span><span class="sxs-lookup"><span data-stu-id="849fb-107">When you run this cmdlet, the phone is deleted from the list of common area phones returned by **Get-CsCommonAreaPhone**.</span></span> <span data-ttu-id="849fb-108">此外，还会从 Active Directory 域服务中删除与该电话相关联的联系人对象。</span><span class="sxs-lookup"><span data-stu-id="849fb-108">In addition, the contact object associated with that phone is deleted from Active Directory Domain Services.</span></span>

<span data-ttu-id="849fb-109">使用 "**删除-CsCommonAreaPhone** " 删除一个通用区域电话或所有具有公共元素（如显示名称或国家/地区代码）的通用区域电话。</span><span class="sxs-lookup"><span data-stu-id="849fb-109">Use **Remove-CsCommonAreaPhone** to remove one common area phone or all common area phones that have a common element, such as a display name or country and area code.</span></span> <span data-ttu-id="849fb-110">你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="849fb-110">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="849fb-111">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="849fb-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a><span data-ttu-id="849fb-112">删除指定的公共区域电话</span><span class="sxs-lookup"><span data-stu-id="849fb-112">Removing a Specified Common Area Phone</span></span>

  - <span data-ttu-id="849fb-113">以下命令将删除带有 SIP 地址 sip:mainlobby@litwareinc.com 的公共区域电话：</span><span class="sxs-lookup"><span data-stu-id="849fb-113">The following command removes the common area phone with the SIP address sip:mainlobby@litwareinc.com:</span></span>
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a><span data-ttu-id="849fb-114">根据其显示名称删除公共的区域电话</span><span class="sxs-lookup"><span data-stu-id="849fb-114">Removing Common Area Phones Based on Their Display Name</span></span>

  - <span data-ttu-id="849fb-115">此命令将删除显示名称包括字符串值 "建筑物 14" 的所有公共区域电话：</span><span class="sxs-lookup"><span data-stu-id="849fb-115">This command removes all the common area phones where the display name includes the string value "Building 14":</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a><span data-ttu-id="849fb-116">根据国家和地区代码删除公共的区域电话</span><span class="sxs-lookup"><span data-stu-id="849fb-116">Removing Common Area Phones Based on Their Country and Area Codes</span></span>

  - <span data-ttu-id="849fb-117">此命令将删除美国的所有通用区域电话（国家码1）和区号425：</span><span class="sxs-lookup"><span data-stu-id="849fb-117">This command removes all the common area phones for the United States (country code 1) and the area code 425:</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

<span data-ttu-id="849fb-118">有关详细信息，请参阅[CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) Cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="849fb-118">For details, see the Help topic for the [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="849fb-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="849fb-119">See Also</span></span>


[<span data-ttu-id="849fb-120">Get-CsCommonAreaPhone</span><span class="sxs-lookup"><span data-stu-id="849fb-120">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

