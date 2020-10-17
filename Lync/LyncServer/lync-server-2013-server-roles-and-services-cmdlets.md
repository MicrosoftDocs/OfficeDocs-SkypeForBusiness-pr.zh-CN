---
title: Lync Server 2013：服务器角色和服务 cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server roles and services cmdlets
ms:assetid: ff3561de-043e-4071-88f7-8de3cded52f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415683(v=OCS.15)
ms:contentKeyID: 48185971
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41b8d2de39f3aa6cce5b192147c2844e5d0f0f81
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510249"
---
# <a name="server-roles-and-services-cmdlets-in-lync-server-2013"></a><span data-ttu-id="65283-102">Lync Server 2013 中的服务器角色和服务 cmdlet</span><span class="sxs-lookup"><span data-stu-id="65283-102">Server roles and services cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65283-103">_**上次修改的主题：** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="65283-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="65283-104">许多 Microsoft Lync Server 2013 组件作为服务器角色或服务运行。</span><span class="sxs-lookup"><span data-stu-id="65283-104">Many Microsoft Lync Server 2013 components run as server roles or as services.</span></span> <span data-ttu-id="65283-105">Lync Server 2013 随附了许多 cmdlet，使您能够管理这些服务器角色和服务。</span><span class="sxs-lookup"><span data-stu-id="65283-105">Lync Server 2013 ships with a number of cmdlets that enable you to manage these server roles and services.</span></span>

<div>

## <a name="server-roles-and-services-cmdlets"></a><span data-ttu-id="65283-106">服务器角色和服务 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="65283-106">Server Roles and Services Cmdlets</span></span>

<span data-ttu-id="65283-107">许多 (（但不是所有适用于服务器和服务角色的管理任务) 都可以从 Lync Server 控制面板中执行。</span><span class="sxs-lookup"><span data-stu-id="65283-107">Many (but not all) of the management tasks that apply to servers and service roles can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="65283-108">例如，可以使用 Lync Server 控制面板管理存档服务器设置，但不能管理通讯簿服务器设置。</span><span class="sxs-lookup"><span data-stu-id="65283-108">For example, you can manage Archiving Server settings but not Address Book Server settings by using Lync Server Control Panel.</span></span> <span data-ttu-id="65283-109">但是，可以使用 Lync Server 命令行管理程序或脚本中的 cmdlet 执行所有这些任务;使用脚本，可以自动执行某些任务。</span><span class="sxs-lookup"><span data-stu-id="65283-109">However, all these tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script; using a script enables you to automate certain tasks.</span></span> <span data-ttu-id="65283-110">以下是与管理服务器角色和服务直接相关的 cmdlet 的列表：</span><span class="sxs-lookup"><span data-stu-id="65283-110">The following is a list of cmdlets that relate directly to managing server roles and services:</span></span>

<span data-ttu-id="65283-111">**[Lync Server 2013 中的通讯簿服务器 cmdlet](lync-server-2013-address-book-server-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="65283-111">**[Address Book Server cmdlets in Lync Server 2013](lync-server-2013-address-book-server-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="65283-112">[CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-112">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-113">[新 CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-113">[New-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-114">[CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-114">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-115">[CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-115">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-116">[更新-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-116">[Update-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-117">[调试-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-117">[Debug-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-118">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-118">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-119">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-119">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span></span>

<span data-ttu-id="65283-120">**[Lync Server 2013 中的存档和监控 cmdlet](lync-server-2013-archiving-and-monitoring-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="65283-120">**[Archiving and Monitoring cmdlets in Lync Server 2013](lync-server-2013-archiving-and-monitoring-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="65283-121">[Set-csarchivingconfiguration](https://technet.microsoft.com/library/Gg399012(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-121">[Get-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg399012(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-122">[新 Set-csarchivingconfiguration](https://technet.microsoft.com/library/Gg398471(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-122">[New-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg398471(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-123">[Set-csarchivingconfiguration](https://technet.microsoft.com/library/Gg398951(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-123">[Remove-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg398951(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-124">[Set-csarchivingconfiguration](https://technet.microsoft.com/library/Gg413030(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-124">[Set-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg413030(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-125">[Export-Export-csarchivingdata](https://technet.microsoft.com/library/Gg398452(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-125">[Export-CsArchivingData](https://technet.microsoft.com/library/Gg398452(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-126">[调用 Invoke-csarchivingdatabasepurge](https://technet.microsoft.com/library/JJ204627(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-126">[Invoke-CsArchivingDatabasePurge](https://technet.microsoft.com/library/JJ204627(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-127">[New-csarchivingpolicy](https://technet.microsoft.com/library/Gg425731(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-127">[Get-CsArchivingPolicy](https://technet.microsoft.com/library/Gg425731(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-128">[Grant-New-csarchivingpolicy](https://technet.microsoft.com/library/Gg398475(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-128">[Grant-CsArchivingPolicy](https://technet.microsoft.com/library/Gg398475(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-129">[新 New-csarchivingpolicy](https://technet.microsoft.com/library/Gg399032(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-129">[New-CsArchivingPolicy](https://technet.microsoft.com/library/Gg399032(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-130">[New-csarchivingpolicy](https://technet.microsoft.com/library/Gg425924(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-130">[Remove-CsArchivingPolicy](https://technet.microsoft.com/library/Gg425924(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-131">[New-csarchivingpolicy](https://technet.microsoft.com/library/Gg398294(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-131">[Set-CsArchivingPolicy](https://technet.microsoft.com/library/Gg398294(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-132">[CsArchivingServer](https://technet.microsoft.com/library/Gg398923(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-132">[Set-CsArchivingServer](https://technet.microsoft.com/library/Gg398923(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-133">[Set-cscdrconfiguration](https://technet.microsoft.com/library/Gg398298(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-133">[Get-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398298(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-134">[新 Set-cscdrconfiguration](https://technet.microsoft.com/library/Gg399018(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-134">[New-CsCdrConfiguration](https://technet.microsoft.com/library/Gg399018(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-135">[Set-cscdrconfiguration](https://technet.microsoft.com/library/Gg398451(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-135">[Remove-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398451(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-136">[Set-cscdrconfiguration](https://technet.microsoft.com/library/Gg398774(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-136">[Set-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398774(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-137">[CsMonitoringServer](https://technet.microsoft.com/library/Gg425776(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-137">[Set-CsMonitoringServer](https://technet.microsoft.com/library/Gg425776(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-138">[New-csqoeconfiguration](https://technet.microsoft.com/library/Gg399004(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-138">[Get-CsQoEConfiguration](https://technet.microsoft.com/library/Gg399004(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-139">[新 New-csqoeconfiguration](https://technet.microsoft.com/library/Gg398325(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-139">[New-CsQoEConfiguration](https://technet.microsoft.com/library/Gg398325(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-140">[New-csqoeconfiguration](https://technet.microsoft.com/library/Gg425879(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-140">[Remove-CsQoEConfiguration](https://technet.microsoft.com/library/Gg425879(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-141">[New-csqoeconfiguration](https://technet.microsoft.com/library/Gg398245(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-141">[Set-CsQoEConfiguration](https://technet.microsoft.com/library/Gg398245(v=OCS.15))</span></span>

<span data-ttu-id="65283-142">[调用 Invoke-cscdrdatabasepurge](https://technet.microsoft.com/library/JJ205113(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-142">[Invoke-CsCdrDatabasePurge](https://technet.microsoft.com/library/JJ205113(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-143">[Export-Export-csarchivingdata](https://technet.microsoft.com/library/Gg398452(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-143">[Export-CsArchivingData](https://technet.microsoft.com/library/Gg398452(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-144">[调用 CsQoEDatabasePurge](https://technet.microsoft.com/library/JJ205247(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-144">[Invoke-CsQoEDatabasePurge](https://technet.microsoft.com/library/JJ205247(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-145">[CsReportingConfiguration](https://technet.microsoft.com/library/JJ205356(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-145">[Get-CsReportingConfiguration](https://technet.microsoft.com/library/JJ205356(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-146">[新 CsReportingConfiguration](https://technet.microsoft.com/library/JJ204787(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-146">[New-CsReportingConfiguration](https://technet.microsoft.com/library/JJ204787(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-147">[CsReportingConfiguration](https://technet.microsoft.com/library/JJ204711(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-147">[Remove-CsReportingConfiguration](https://technet.microsoft.com/library/JJ204711(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-148">[CsReportingConfiguration](https://technet.microsoft.com/library/JJ205075(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-148">[Set-CsReportingConfiguration](https://technet.microsoft.com/library/JJ205075(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-149">[CsTestUserCredential](https://technet.microsoft.com/library/JJ204759(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-149">[Get-CsTestUserCredential](https://technet.microsoft.com/library/JJ204759(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-150">[CsTestUserCredential](https://technet.microsoft.com/library/JJ204870(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-150">[Remove-CsTestUserCredential](https://technet.microsoft.com/library/JJ204870(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-151">[CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-151">[Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-152">[New-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-152">[Get-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204739(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-153">[新 New-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ205254(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-153">[New-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ205254(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-154">[New-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-154">[Remove-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204926(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-155">[New-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204620(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-155">[Set-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204620(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-156">[Test-New-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204652(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-156">[Test-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204652(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-157">[新 CsExtendedTest](https://technet.microsoft.com/library/JJ205275(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-157">[New-CsExtendedTest](https://technet.microsoft.com/library/JJ205275(v=OCS.15))</span></span>

<span data-ttu-id="65283-158">**[Lync Server 2013 中的数据库和管理服务器 cmdlet](lync-server-2013-database-and-management-server-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="65283-158">**[Database and Management Server cmdlets in Lync Server 2013](lync-server-2013-database-and-management-server-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="65283-159">[CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg412814(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-159">[Get-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg412814(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-160">[CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398214(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-160">[Remove-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398214(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-161">[CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398258(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-161">[Set-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398258(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-162">[Install-CsDatabase](https://technet.microsoft.com/library/Gg399044(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-162">[Install-CsDatabase](https://technet.microsoft.com/library/Gg399044(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-163">[Test-CsDatabase](https://technet.microsoft.com/library/JJ204839(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-163">[Test-CsDatabase](https://technet.microsoft.com/library/JJ204839(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-164">[卸载-CsDatabase](unhttps://technet.microsoft.com/library/Gg399044(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-164">[Uninstall-CsDatabase](unhttps://technet.microsoft.com/library/Gg399044(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="65283-165">[调用 CsDatabaseFailover](https://technet.microsoft.com/library/JJ204744(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-165">[Invoke-CsDatabaseFailover](https://technet.microsoft.com/library/JJ204744(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="65283-166">[CsDatabaseMirrorState](https://technet.microsoft.com/library/JJ204845(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-166">[Get-CsDatabaseMirrorState](https://technet.microsoft.com/library/JJ204845(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="65283-167">[Install-CsMirrorDatabase](https://technet.microsoft.com/library/JJ204986(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-167">[Install-CsMirrorDatabase](https://technet.microsoft.com/library/JJ204986(v=OCS.15))</span></span>

  - <span data-ttu-id="65283-168">[卸载-CsMirrorDatabase](unhttps://technet.microsoft.com/library/JJ204986(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-168">[Uninstall-CsMirrorDatabase](unhttps://technet.microsoft.com/library/JJ204986(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-169">[CsUserDatabaseState](https://technet.microsoft.com/library/Gg398831(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-169">[Get-CsUserDatabaseState](https://technet.microsoft.com/library/Gg398831(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-170">[CsUserDatabaseState](https://technet.microsoft.com/library/Gg412973(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-170">[Set-CsUserDatabaseState](https://technet.microsoft.com/library/Gg412973(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-171">[更新-CsUserDatabase](https://technet.microsoft.com/library/Gg398682(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-171">[Update-CsUserDatabase](https://technet.microsoft.com/library/Gg398682(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-172">[移动-Move-csmanagementserver](https://technet.microsoft.com/library/Gg412921(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-172">[Move-CsManagementServer](https://technet.microsoft.com/library/Gg412921(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-173">[Move-csmanagementserver](https://technet.microsoft.com/library/Gg398465(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-173">[Set-CsManagementServer](https://technet.microsoft.com/library/Gg398465(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="65283-174">[调用 CsManagementServerFailover](https://technet.microsoft.com/library/JJ204647(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-174">[Invoke-CsManagementServerFailover](https://technet.microsoft.com/library/JJ204647(v=OCS.15))</span></span>

<span data-ttu-id="65283-175">**[Lync Server 2013 中的边缘服务器 cmdlet](lync-server-2013-edge-server-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="65283-175">**[Edge Server cmdlets in Lync Server 2013](lync-server-2013-edge-server-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="65283-176">[Set-csaccessedgeconfiguration](https://technet.microsoft.com/library/Gg398574(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-176">[Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg398574(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-177">[Set-csaccessedgeconfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-177">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-178">[CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-178">[Get-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-179">[新 CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-179">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-180">[CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-180">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-181">[CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-181">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-182">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/library/JJ205138(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-182">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/library/JJ205138(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-183">[CsEdgeServer](https://technet.microsoft.com/library/Gg398859(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-183">[Set-CsEdgeServer](https://technet.microsoft.com/library/Gg398859(v=OCS.15))</span></span>

<span data-ttu-id="65283-184">**[Lync Server 2013 中的其他服务器角色 cmdlet](lync-server-2013-other-server-role-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="65283-184">**[Other server role cmdlets in Lync Server 2013](lync-server-2013-other-server-role-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="65283-185">[CsConferenceServer](https://technet.microsoft.com/library/Gg398738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-185">[Set-CsConferenceServer](https://technet.microsoft.com/library/Gg398738(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-186">[CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-186">[Set-CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))</span></span>

<span data-ttu-id="65283-187">**[Lync Server 2013 中的注册器和控制器 cmdlet](lync-server-2013-registrar-and-director-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="65283-187">**[Registrar and Director cmdlets in Lync Server 2013](lync-server-2013-registrar-and-director-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="65283-188">[CsDirector](https://technet.microsoft.com/library/Gg398565(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-188">[Set-CsDirector](https://technet.microsoft.com/library/Gg398565(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-189">[Reset-CsPoolRegistrarState](https://technet.microsoft.com/library/JJ619172(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-189">[Reset-CsPoolRegistrarState](https://technet.microsoft.com/library/JJ619172(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-190">[CsRegistrar](https://technet.microsoft.com/library/Gg398993(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-190">[Set-CsRegistrar](https://technet.microsoft.com/library/Gg398993(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-191">[CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398483(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-191">[Get-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398483(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-192">[新 CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg425893(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-192">[New-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg425893(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-193">[CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398482(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-193">[Remove-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398482(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-194">[CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-194">[Set-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398764(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-195">[Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-195">[Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15))</span></span>

<span data-ttu-id="65283-196">**[Lync Server 2013 中的服务 cmdlet](lync-server-2013-services-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="65283-196">**[Services cmdlets in Lync Server 2013](lync-server-2013-services-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="65283-197">[Get-csservice](https://technet.microsoft.com/library/Gg413038(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-197">[Get-CsService](https://technet.microsoft.com/library/Gg413038(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-198">[Start-cswindowsservice](https://technet.microsoft.com/library/Gg398803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-198">[Get-CsWindowsService](https://technet.microsoft.com/library/Gg398803(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-199">[启动-Start-cswindowsservice](https://technet.microsoft.com/library/Gg398561(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-199">[Start-CsWindowsService](https://technet.microsoft.com/library/Gg398561(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-200">[Start-cswindowsservice](https://technet.microsoft.com/library/Gg398426(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-200">[Stop-CsWindowsService](https://technet.microsoft.com/library/Gg398426(v=OCS.15))</span></span>

<span data-ttu-id="65283-201">**[在 Lync Server 2013 中排除服务器角色和服务 cmdlet 的故障](lync-server-2013-troubleshooting-server-roles-and-services-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="65283-201">**[Troubleshooting server roles and services cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-server-roles-and-services-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="65283-202">[CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg412984(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-202">[Get-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg412984(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-203">[CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg398907(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-203">[Set-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg398907(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-204">[CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg398667(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-204">[Get-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg398667(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-205">[新 CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg398718(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-205">[New-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg398718(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-206">[CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg425794(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-206">[Remove-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg425794(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-207">[CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg425847(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-207">[Set-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg425847(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-208">[CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg413034(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-208">[Get-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg413034(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-209">[新 CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg398733(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-209">[New-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg398733(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-210">[CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg412853(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-210">[Remove-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg412853(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-211">[CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg425734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-211">[Set-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg425734(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-212">[新 CsDiagnosticsFilter](https://technet.microsoft.com/library/Gg413009(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-212">[New-CsDiagnosticsFilter](https://technet.microsoft.com/library/Gg413009(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-213">[CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg412774(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-213">[Get-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg412774(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-214">[新 CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg398350(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-214">[New-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg398350(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-215">[CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg398941(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-215">[Remove-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg398941(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-216">[CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg399045(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-216">[Set-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg399045(v=OCS.15))</span></span>

<span data-ttu-id="65283-217">**[Lync Server 2013 中的 Web 服务器和服务 cmdlet](lync-server-2013-web-server-and-services-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="65283-217">**[Web server and services cmdlets in Lync Server 2013](lync-server-2013-web-server-and-services-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="65283-218">[新 CsSimpleUrl](https://technet.microsoft.com/library/Gg398180(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-218">[New-CsSimpleUrl](https://technet.microsoft.com/library/Gg398180(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-219">[CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398392(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-219">[Get-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398392(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-220">[新 CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg425813(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-220">[New-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg425813(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-221">[CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398515(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-221">[Remove-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398515(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-222">[CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg412991(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-222">[Set-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg412991(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-223">[新 CsSimpleUrlEntry](https://technet.microsoft.com/library/Gg425902(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-223">[New-CsSimpleUrlEntry](https://technet.microsoft.com/library/Gg425902(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-224">[CsWebServer](https://technet.microsoft.com/library/Gg398759(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-224">[Set-CsWebServer](https://technet.microsoft.com/library/Gg398759(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-225">[CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg425751(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-225">[Get-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg425751(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-226">[新 CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398440(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-226">[New-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398440(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-227">[CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398266(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-227">[Remove-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398266(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-228">[CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398396(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-228">[Set-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398396(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-229">[新 CsWebTrustedCACertificate](https://technet.microsoft.com/library/Gg412746(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-229">[New-CsWebTrustedCACertificate](https://technet.microsoft.com/library/Gg412746(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-230">[新 CsKerberosAccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-230">[New-CsKerberosAccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-231">[CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-231">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-232">[新 CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-232">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-233">[CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-233">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-234">[CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-234">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="65283-235">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-235">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="65283-236">[CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-236">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="65283-237">[Test-CsWebApp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-237">[Test-CsWebApp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))</span></span>

  - <span data-ttu-id="65283-238">[Test-CsWebAppAnonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="65283-238">[Test-CsWebAppAnonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="65283-239">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65283-239">See Also</span></span>


[<span data-ttu-id="65283-240">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="65283-240">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

