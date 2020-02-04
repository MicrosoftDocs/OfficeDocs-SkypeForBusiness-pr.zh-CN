---
title: Lync Server 2013：用于通讯簿管理的 Windows PowerShell cmdlet
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
ms.openlocfilehash: 5ec10f3e3d3d58a790ddc60fd1af1d1b09765685
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-cmdlets-for-address-book-services-in-lync-server-2013"></a><span data-ttu-id="52e3d-102">Lync Server 2013 中的 "通讯簿" 服务的 Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="52e3d-102">Windows PowerShell cmdlets for Address Book Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52e3d-103">_**主题上次修改时间：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="52e3d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="52e3d-104">Lync 服务器提供了许多 Windows PowerShell 命令行界面 cmdlet 来管理和配置通讯簿服务。</span><span class="sxs-lookup"><span data-stu-id="52e3d-104">Lync Server provides a number of Windows PowerShell command-line interface cmdlets to manage and configure the Address Book service.</span></span> <span data-ttu-id="52e3d-105">某些 cmdlet 是以前版本的 Office 通信服务器中使用的 ABServer 命令的替换部分。</span><span class="sxs-lookup"><span data-stu-id="52e3d-105">Some of these cmdlets are replacements for the ABServer.exe commands used in previous versions of Office Communications Server.</span></span> <span data-ttu-id="52e3d-106">在以下主题中，用于设置、创建和检索有关通讯簿服务的的 cmdlet、其配置和有关当客户端检索通讯簿服务时，通讯簿服务使用的 Web 服务的相关信息文件和设置。</span><span class="sxs-lookup"><span data-stu-id="52e3d-106">In the following topics are the cmdlets that are used to set, create, and retrieve information about the Address Book service, its configuration and information about the Web services that the Address Book service uses when clients retrieve Address Book service files and settings.</span></span>

<span data-ttu-id="52e3d-107">所有这些 cmdlet 均通过在安装了管理工具的服务器或工作站上的 Lync server 工具中找到的 Lync Server Management Shell 发出。</span><span class="sxs-lookup"><span data-stu-id="52e3d-107">All of these cmdlets are issued through the Lync Server Management Shell found in the Lync Server tools on a server or workstation where the administration tools have been installed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="52e3d-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="52e3d-108">In This Section</span></span>

  - [<span data-ttu-id="52e3d-109">Lync Server 2013 中的通讯簿管理的新 CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="52e3d-109">New-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsAddressBookConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="52e3d-110">CsAddressBookConfiguration Lync Server 2013 中的通讯簿管理设置</span><span class="sxs-lookup"><span data-stu-id="52e3d-110">Set-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="52e3d-111">Lync Server 2013 中的 CsAddressBookConfiguration 管理通讯簿</span><span class="sxs-lookup"><span data-stu-id="52e3d-111">Get-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="52e3d-112">CsAddressBookConfiguration 在 Lync Server 2013 中删除通讯簿管理</span><span class="sxs-lookup"><span data-stu-id="52e3d-112">Remove-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="52e3d-113">CsAddressBookService 在 Lync Server 2013 中的通讯簿管理的测试</span><span class="sxs-lookup"><span data-stu-id="52e3d-113">Test-CsAddressBookService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookservice-for-address-book-management.md)

  - [<span data-ttu-id="52e3d-114">CsAddressBookWebQuery 在 Lync Server 2013 中的通讯簿管理的测试</span><span class="sxs-lookup"><span data-stu-id="52e3d-114">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookwebquery-for-address-book-management.md)

  - [<span data-ttu-id="52e3d-115">CsAddressBook-Lync Server 2013 中的通讯簿管理的更新</span><span class="sxs-lookup"><span data-stu-id="52e3d-115">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>](lync-server-2013-update-csaddressbook-for-address-book-management.md)

  - [<span data-ttu-id="52e3d-116">Lync Server 2013 中的通讯簿管理的新 Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="52e3d-116">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-new-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="52e3d-117">Set-csclientpolicy Lync Server 2013 中的通讯簿管理设置</span><span class="sxs-lookup"><span data-stu-id="52e3d-117">Set-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="52e3d-118">Lync Server 2013 中的 CsService 管理通讯簿</span><span class="sxs-lookup"><span data-stu-id="52e3d-118">Get-CsService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csservice-for-address-book-management.md)

  - [<span data-ttu-id="52e3d-119">Lync Server 2013 中的通讯簿管理的新 CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="52e3d-119">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsWebServiceConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="52e3d-120">Lync Server 2013 中的 CsWebServiceConfiguration 管理通讯簿</span><span class="sxs-lookup"><span data-stu-id="52e3d-120">Get-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="52e3d-121">CsWebServiceConfiguration Lync Server 2013 中的通讯簿管理设置</span><span class="sxs-lookup"><span data-stu-id="52e3d-121">Set-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="52e3d-122">CsWebServiceConfiguration 在 Lync Server 2013 中删除通讯簿管理</span><span class="sxs-lookup"><span data-stu-id="52e3d-122">Remove-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-cswebserviceconfiguration-for-address-book-management.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="52e3d-123">相关部分</span><span class="sxs-lookup"><span data-stu-id="52e3d-123">Related Sections</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="52e3d-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52e3d-124">See Also</span></span>


[http://go.microsoft.com/fwlink/p/?linkId=205826](http://go.microsoft.com/fwlink/p/?linkid=205826)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

