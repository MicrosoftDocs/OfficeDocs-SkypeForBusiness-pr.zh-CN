---
title: Lync Server 2013：创建或修改公用区域电话联系人对象
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a common area phone Contact object
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994083(v=OCS.15)
ms:contentKeyID: 51803995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 418001642f387caf67277f408d4eb19109c98936
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="bed27-102">在 Lync Server 2013 中创建或修改公用区域电话联系人对象</span><span class="sxs-lookup"><span data-stu-id="bed27-102">Create or modify a common area phone Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bed27-103">_**上次修改的主题：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="bed27-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="bed27-104">若要为所有公用区域电话创建 Active Directory 域服务联系人对象，请使用**CsCommonAreaPhone** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bed27-104">To create Active Directory Domain Services contact objects for all your common area phones, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="bed27-105">此 cmdlet 可以创建新的 contact 对象以与公用区域电话一起使用，也可以将现有联系人对象与新的公用区域电话相关联。</span><span class="sxs-lookup"><span data-stu-id="bed27-105">This cmdlet can either create new contact objects for use with common area phones, or it can associate existing contact objects with a new common area phone.</span></span> <span data-ttu-id="bed27-106">若要修改与公用区域电话相关联的 contact 对象的属性，请使用**CsCommonAreaPhone** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bed27-106">To modify the properties of the contact objects associated with common area phones, use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="bed27-107">**CsCommonAreaPhone**的可选参数使您能够更改项目，例如联系人的 Active Directory 显示名称或与电话关联的行统一资源标识符（URI），并启用和禁用与 Lync Server 一起使用的帐户。</span><span class="sxs-lookup"><span data-stu-id="bed27-107">Optional parameters for **Set-CsCommonAreaPhone** enable you to change items, such as the contact’s Active Directory display name or the line Uniform Resource Identifier (URI) associated with the phone, and enable and disable the account for use with Lync Server.</span></span> <span data-ttu-id="bed27-108">有关所有可用修改的详细信息，请参阅[CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone)的 Parameters 部分。</span><span class="sxs-lookup"><span data-stu-id="bed27-108">For details about all the available modifications, see the Parameters section at [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone).</span></span> <span data-ttu-id="bed27-109">有关**CsCommonAreaPhone**参数的详细信息，请参阅[CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone)。</span><span class="sxs-lookup"><span data-stu-id="bed27-109">For details about **New-CsCommonAreaPhone** parameters, see [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).</span></span>

<span data-ttu-id="bed27-110">您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话运行这两个 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bed27-110">You can run these two cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="bed27-111">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="bed27-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a><span data-ttu-id="bed27-112">创建公用区域电话联系人对象</span><span class="sxs-lookup"><span data-stu-id="bed27-112">Creating a common area phone contact object</span></span>

  - <span data-ttu-id="bed27-113">若要创建新的公共区域电话联系人对象，请使用**CsCommonAreaPhone** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bed27-113">To create a new common area phone contact object, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="bed27-114">在创建 contact 对象时，至少必须提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="bed27-114">At a minimum, you must supply the following information when creating a contact object:</span></span>
    
      - <span data-ttu-id="bed27-115">**LineUri**：分配给公共区域电话的电话号码。</span><span class="sxs-lookup"><span data-stu-id="bed27-115">**LineUri**: The telephone number assigned to the common area phone.</span></span> <span data-ttu-id="bed27-116">请注意，在指定电话号码时，您必须使用. 164 格式。</span><span class="sxs-lookup"><span data-stu-id="bed27-116">Note that you must use the E.164 format when specifying the phone number.</span></span>
    
      - <span data-ttu-id="bed27-117">**RegistrarPool**：将承载 contact 对象的注册器池的完全限定域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="bed27-117">**RegistrarPool**: The fully qualified domain name (FQDN) of the Registrar pool that will host the contact object.</span></span>
    
      - <span data-ttu-id="bed27-118">**OU**：将在其中创建 contact 对象的 Active Directory 容器的可分辨名称。</span><span class="sxs-lookup"><span data-stu-id="bed27-118">**OU**: Distinguished name of the Active Directory container where the contact object will be created.</span></span>
    
    <span data-ttu-id="bed27-119">此外，我们还建议您提供一个 Active Directory 域服务的显示名称。</span><span class="sxs-lookup"><span data-stu-id="bed27-119">We also recommend that you provide an Active Directory Domain Services display name.</span></span> <span data-ttu-id="bed27-120">否则，您将需要使用 GUID 来指定电话标识。</span><span class="sxs-lookup"><span data-stu-id="bed27-120">Otherwise, you will need to use a GUID to specify the phone Identity.</span></span> <span data-ttu-id="bed27-121">例如：</span><span class="sxs-lookup"><span data-stu-id="bed27-121">For example:</span></span>
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a><span data-ttu-id="bed27-122">修改公用区域电话联系人对象</span><span class="sxs-lookup"><span data-stu-id="bed27-122">Modifying a common area phone contact object</span></span>

  - <span data-ttu-id="bed27-123">若要修改现有公用区域电话的属性，contact 对象使用**CsCommonAreaPhone** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bed27-123">To modify the properties of an existing common area phone, contact object use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="bed27-124">例如，以下命令使用 DisplayName 大厅配置公用区域电话的 SIP 地址：</span><span class="sxs-lookup"><span data-stu-id="bed27-124">For example, this command configures the SIP address for the common area phone with the DisplayName Lobby:</span></span>
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

<span data-ttu-id="bed27-125">有关详细信息，请参阅[CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) Cmdlet 和[CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="bed27-125">For details, see the Help topics for the [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) cmdlet and the [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

