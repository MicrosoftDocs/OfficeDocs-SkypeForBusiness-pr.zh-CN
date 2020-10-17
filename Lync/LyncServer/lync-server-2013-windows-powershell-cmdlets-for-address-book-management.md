---
title: Lync Server 2013：用于通讯簿管理的 Windows PowerShell cmdlet
description: Lync Server 2013：用于通讯簿管理的 Windows PowerShell cmdlet。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell cmdlets for Address Book management
ms:assetid: 73bfa949-5628-4156-ad20-fe07a0dc6216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429708(v=OCS.15)
ms:contentKeyID: 48184512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b598d91a4d1a29a67d8f8ceb2477f2d9b96f1319
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546018"
---
# <a name="windows-powershell-cmdlets-for-address-book-services-in-lync-server-2013"></a><span data-ttu-id="24882-103">Lync Server 2013 中的通讯簿服务的 Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="24882-103">Windows PowerShell cmdlets for Address Book Services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24882-104">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="24882-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="24882-105">Lync Server 提供了许多 Windows PowerShell 命令行接口 cmdlet 来管理和配置通讯簿服务。</span><span class="sxs-lookup"><span data-stu-id="24882-105">Lync Server provides a number of Windows PowerShell command-line interface cmdlets to manage and configure the Address Book service.</span></span> <span data-ttu-id="24882-106">这些 cmdlet 中的一些将替换早期版本的 Office 通信服务器中使用的 ABServer.exe 命令。</span><span class="sxs-lookup"><span data-stu-id="24882-106">Some of these cmdlets are replacements for the ABServer.exe commands used in previous versions of Office Communications Server.</span></span> <span data-ttu-id="24882-107">以下主题中的 cmdlet 用于设置、创建和检索有关通讯簿服务及其配置的信息，以及有关当客户端检索通讯簿服务文件和设置时通讯簿服务使用的 Web 服务的信息。</span><span class="sxs-lookup"><span data-stu-id="24882-107">In the following topics are the cmdlets that are used to set, create, and retrieve information about the Address Book service, its configuration and information about the Web services that the Address Book service uses when clients retrieve Address Book service files and settings.</span></span>

<span data-ttu-id="24882-108">所有这些 cmdlet 都是通过在安装了管理工具的服务器或工作站上的 Lync server 工具中找到的 Lync Server 命令行管理程序来颁发的。</span><span class="sxs-lookup"><span data-stu-id="24882-108">All of these cmdlets are issued through the Lync Server Management Shell found in the Lync Server tools on a server or workstation where the administration tools have been installed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="24882-109">本部分内容</span><span class="sxs-lookup"><span data-stu-id="24882-109">In This Section</span></span>

  - [<span data-ttu-id="24882-110">Lync Server 2013 中的 CsAddressBookConfiguration for Address Book management</span><span class="sxs-lookup"><span data-stu-id="24882-110">New-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsAddressBookConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="24882-111">Lync Server 2013 中的通讯簿管理的 CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="24882-111">Set-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="24882-112">Lync Server 2013 中的 CsAddressBookConfiguration for Address Book management</span><span class="sxs-lookup"><span data-stu-id="24882-112">Get-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="24882-113">CsAddressBookConfiguration for Address Book management in Lync Server 2013 中的 Remove</span><span class="sxs-lookup"><span data-stu-id="24882-113">Remove-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="24882-114">Lync Server 2013 中的 CsAddressBookService for Address Book management</span><span class="sxs-lookup"><span data-stu-id="24882-114">Test-CsAddressBookService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookservice-for-address-book-management.md)

  - [<span data-ttu-id="24882-115">Lync Server 2013 中的 CsAddressBookWebQuery for Address Book management</span><span class="sxs-lookup"><span data-stu-id="24882-115">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookwebquery-for-address-book-management.md)

  - [<span data-ttu-id="24882-116">Lync Server 2013 中的 CsAddressBook for Address Book management</span><span class="sxs-lookup"><span data-stu-id="24882-116">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>](lync-server-2013-update-csaddressbook-for-address-book-management.md)

  - [<span data-ttu-id="24882-117">Lync Server 2013 中的 Set-csclientpolicy for Address Book management</span><span class="sxs-lookup"><span data-stu-id="24882-117">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-new-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="24882-118">Lync Server 2013 中的通讯簿管理的 Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="24882-118">Set-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="24882-119">Lync Server 2013 中的 Get-csservice for Address Book management</span><span class="sxs-lookup"><span data-stu-id="24882-119">Get-CsService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csservice-for-address-book-management.md)

  - [<span data-ttu-id="24882-120">Lync Server 2013 中的 CsWebServiceConfiguration for Address Book management</span><span class="sxs-lookup"><span data-stu-id="24882-120">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsWebServiceConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="24882-121">Lync Server 2013 中的 CsWebServiceConfiguration for Address Book management</span><span class="sxs-lookup"><span data-stu-id="24882-121">Get-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="24882-122">Lync Server 2013 中的通讯簿管理的 CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="24882-122">Set-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="24882-123">CsWebServiceConfiguration for Address Book management in Lync Server 2013 中的 Remove</span><span class="sxs-lookup"><span data-stu-id="24882-123">Remove-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-cswebserviceconfiguration-for-address-book-management.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="24882-124">相关章节</span><span class="sxs-lookup"><span data-stu-id="24882-124">Related Sections</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="24882-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24882-125">See Also</span></span>


[https://go.microsoft.com/fwlink/p/?linkId=205826](https://go.microsoft.com/fwlink/p/?linkid=205826)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

