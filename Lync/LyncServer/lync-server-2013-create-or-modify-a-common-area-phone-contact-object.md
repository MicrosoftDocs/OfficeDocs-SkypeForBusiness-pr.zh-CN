---
title: Lync Server 2013：创建或修改公用区域电话联系人对象
description: Lync Server 2013：创建或修改公用区域电话联系人对象。
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
ms.openlocfilehash: adc5ede23f495a63b2d556b556817d4171a08723
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578228"
---
# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="fdd77-103">在 Lync Server 2013 中创建或修改公用区域电话联系人对象</span><span class="sxs-lookup"><span data-stu-id="fdd77-103">Create or modify a common area phone Contact object in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fdd77-104">_**上次修改的主题：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="fdd77-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="fdd77-105">若要为所有公用区域电话创建 Active Directory 域服务联系人对象，请使用 **CsCommonAreaPhone** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fdd77-105">To create Active Directory Domain Services contact objects for all your common area phones, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="fdd77-106">此 cmdlet 可以创建新的 contact 对象以与公用区域电话一起使用，也可以将现有联系人对象与新的公用区域电话相关联。</span><span class="sxs-lookup"><span data-stu-id="fdd77-106">This cmdlet can either create new contact objects for use with common area phones, or it can associate existing contact objects with a new common area phone.</span></span> <span data-ttu-id="fdd77-107">若要修改与公用区域电话相关联的 contact 对象的属性，请使用 **CsCommonAreaPhone** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fdd77-107">To modify the properties of the contact objects associated with common area phones, use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="fdd77-108">**CsCommonAreaPhone**的可选参数使您能够更改项目，如联系人的 Active Directory 显示名称或行统一资源标识符 (URI) 与电话关联，并启用和禁用与 Lync Server 一起使用的帐户。</span><span class="sxs-lookup"><span data-stu-id="fdd77-108">Optional parameters for **Set-CsCommonAreaPhone** enable you to change items, such as the contact’s Active Directory display name or the line Uniform Resource Identifier (URI) associated with the phone, and enable and disable the account for use with Lync Server.</span></span> <span data-ttu-id="fdd77-109">有关所有可用修改的详细信息，请参阅 [CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone)的 Parameters 部分。</span><span class="sxs-lookup"><span data-stu-id="fdd77-109">For details about all the available modifications, see the Parameters section at [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone).</span></span> <span data-ttu-id="fdd77-110">有关 **CsCommonAreaPhone** 参数的详细信息，请参阅 [CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone)。</span><span class="sxs-lookup"><span data-stu-id="fdd77-110">For details about **New-CsCommonAreaPhone** parameters, see [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).</span></span>

<span data-ttu-id="fdd77-111">您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话运行这两个 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fdd77-111">You can run these two cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fdd77-112">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="fdd77-112">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a><span data-ttu-id="fdd77-113">创建公用区域电话联系人对象</span><span class="sxs-lookup"><span data-stu-id="fdd77-113">Creating a common area phone contact object</span></span>

  - <span data-ttu-id="fdd77-114">若要创建新的公共区域电话联系人对象，请使用 **CsCommonAreaPhone** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fdd77-114">To create a new common area phone contact object, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="fdd77-115">在创建 contact 对象时，至少必须提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="fdd77-115">At a minimum, you must supply the following information when creating a contact object:</span></span>
    
      - <span data-ttu-id="fdd77-116">**LineUri**：分配给公共区域电话的电话号码。</span><span class="sxs-lookup"><span data-stu-id="fdd77-116">**LineUri**: The telephone number assigned to the common area phone.</span></span> <span data-ttu-id="fdd77-117">请注意，在指定电话号码时，您必须使用. 164 格式。</span><span class="sxs-lookup"><span data-stu-id="fdd77-117">Note that you must use the E.164 format when specifying the phone number.</span></span>
    
      - <span data-ttu-id="fdd77-118">**RegistrarPool**：将承载 contact 对象的注册器池 (FQDN) 的完全限定的域名称。</span><span class="sxs-lookup"><span data-stu-id="fdd77-118">**RegistrarPool**: The fully qualified domain name (FQDN) of the Registrar pool that will host the contact object.</span></span>
    
      - <span data-ttu-id="fdd77-119">**OU**：将在其中创建 contact 对象的 Active Directory 容器的可分辨名称。</span><span class="sxs-lookup"><span data-stu-id="fdd77-119">**OU**: Distinguished name of the Active Directory container where the contact object will be created.</span></span>
    
    <span data-ttu-id="fdd77-120">此外，我们还建议您提供一个 Active Directory 域服务的显示名称。</span><span class="sxs-lookup"><span data-stu-id="fdd77-120">We also recommend that you provide an Active Directory Domain Services display name.</span></span> <span data-ttu-id="fdd77-121">否则，您将需要使用 GUID 来指定电话标识。</span><span class="sxs-lookup"><span data-stu-id="fdd77-121">Otherwise, you will need to use a GUID to specify the phone Identity.</span></span> <span data-ttu-id="fdd77-122">例如：</span><span class="sxs-lookup"><span data-stu-id="fdd77-122">For example:</span></span>
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a><span data-ttu-id="fdd77-123">修改公用区域电话联系人对象</span><span class="sxs-lookup"><span data-stu-id="fdd77-123">Modifying a common area phone contact object</span></span>

  - <span data-ttu-id="fdd77-124">若要修改现有公用区域电话的属性，contact 对象使用 **CsCommonAreaPhone** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fdd77-124">To modify the properties of an existing common area phone, contact object use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="fdd77-125">例如，以下命令使用 DisplayName 大厅配置公用区域电话的 SIP 地址：</span><span class="sxs-lookup"><span data-stu-id="fdd77-125">For example, this command configures the SIP address for the common area phone with the DisplayName Lobby:</span></span>
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

<span data-ttu-id="fdd77-126">有关详细信息，请参阅 [CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) Cmdlet 和 [CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="fdd77-126">For details, see the Help topics for the [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) cmdlet and the [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

