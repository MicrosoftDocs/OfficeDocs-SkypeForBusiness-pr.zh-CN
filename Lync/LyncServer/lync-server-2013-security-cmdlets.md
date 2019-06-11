---
title: 'Lync Server 2013: 安全 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Security cmdlets
ms:assetid: 9a6c654d-287d-434e-8d93-409f0d623f5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398799(v=OCS.15)
ms:contentKeyID: 48184968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31ede87f55754528fc7164c6d7d828eaada662e7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822130"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-cmdlets-in-lync-server-2013"></a><span data-ttu-id="c486b-102">Lync Server 2013 中的安全 cmdlet</span><span class="sxs-lookup"><span data-stu-id="c486b-102">Security cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c486b-103">_**主题上次修改时间:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="c486b-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="c486b-104">Microsoft Lync Server 2013 中包含的安全 cmdlet 主要用于管理身份验证以及用户权利和权限。</span><span class="sxs-lookup"><span data-stu-id="c486b-104">The security cmdlets included in Microsoft Lync Server 2013 are primarily used to manage authentication, and user rights and permissions.</span></span> <span data-ttu-id="c486b-105">多种 cmdlet 可用于管理身份验证，包括用于证书和个人标识号 (PIN) 身份验证的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c486b-105">A wide variety of cmdlets are available for managing authentication, including cmdlets for certificate and personal identification number (PIN) authentication.</span></span> <span data-ttu-id="c486b-106">此外, 您可以使用多个 cmdlet 来使用新的基于角色的访问控制 (RBAC) 功能来委派 Lync 服务器的管理控制。</span><span class="sxs-lookup"><span data-stu-id="c486b-106">In addition, a number of cmdlets enable you to use the new role-based access control (RBAC) feature to delegate administrative control of Lync Server.</span></span>

<div>

## <a name="security-cmdlets"></a><span data-ttu-id="c486b-107">安全 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c486b-107">Security Cmdlets</span></span>

<span data-ttu-id="c486b-108">可从 Lync Server 控制面板执行许多适用于安全设置的管理任务。</span><span class="sxs-lookup"><span data-stu-id="c486b-108">Many management tasks that apply to security settings can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="c486b-109">一个主要例外是用户权限 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c486b-109">One major exception is the user permission cmdlets.</span></span> <span data-ttu-id="c486b-110">但是, 可以使用 Lync Server 命令行管理程序或脚本中的 cmdlet 执行所有安全管理任务;使用脚本可以自动执行某些任务。</span><span class="sxs-lookup"><span data-stu-id="c486b-110">However, all security management tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script; using a script enables you to automate certain tasks.</span></span> <span data-ttu-id="c486b-111">以下是与管理安全设置直接相关的 cmdlet 的列表:</span><span class="sxs-lookup"><span data-stu-id="c486b-111">The following is a list of cmdlets that relate directly to managing security settings:</span></span>

<span data-ttu-id="c486b-112">**[Lync Server 2013 中的证书和身份验证 cmdlet](lync-server-2013-certificate-and-authentication-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="c486b-112">**[Certificate and authentication cmdlets in Lync Server 2013](lync-server-2013-certificate-and-authentication-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-113">[Get-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398227(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-113">[Get-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398227(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-114">[Import-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398688(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-114">[Import-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398688(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-115">[Remove-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-115">[Remove-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-116">[请求-CsCertificate](https://technet.microsoft.com/en-us/library/Gg425723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-116">[Request-CsCertificate](https://technet.microsoft.com/en-us/library/Gg425723(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-117">[Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-117">[Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c486b-118">[Test-CsCertificateConfiguration](https://technet.microsoft.com/en-us/library/Gg398647(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-118">[Test-CsCertificateConfiguration](https://technet.microsoft.com/en-us/library/Gg398647(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c486b-119">[CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg398143(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-119">[Get-CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg398143(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-120">[Revoke-CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg425748(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-120">[Revoke-CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg425748(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c486b-121">[Lock-CsClientPin](https://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-121">[Lock-CsClientPin](https://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-122">[Set-CsClientPin](https://technet.microsoft.com/en-us/library/Gg398929(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-122">[Set-CsClientPin](https://technet.microsoft.com/en-us/library/Gg398929(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-123">[解锁-CsClientPin](unhttps://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-123">[Unlock-CsClientPin](unhttps://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c486b-124">[CsClientPinInfo](https://technet.microsoft.com/en-us/library/Gg425947(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-124">[Get-CsClientPinInfo](https://technet.microsoft.com/en-us/library/Gg425947(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c486b-125">[New-CsKerberosAccount](https://technet.microsoft.com/en-us/library/Gg398485(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-125">[New-CsKerberosAccount](https://technet.microsoft.com/en-us/library/Gg398485(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c486b-126">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398526(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-126">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398526(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-127">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398074(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-127">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398074(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-128">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg413052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-128">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg413052(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-129">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-129">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398232(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-130">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-130">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c486b-131">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-131">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c486b-132">[Get-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398262(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-132">[Get-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398262(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-133">[Grant-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398871(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-133">[Grant-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398871(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-134">[New-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398935(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-134">[New-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398935(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-135">[Remove-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398431(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-135">[Remove-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398431(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-136">[Set-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg412997(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-136">[Set-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg412997(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c486b-137">[CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg399011(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-137">[Get-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg399011(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-138">[新-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398335(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-138">[New-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398335(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-139">[Remove-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398553(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-139">[Remove-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398553(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-140">[Set-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg425796(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-140">[Set-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg425796(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c486b-141">[Get-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398701(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-141">[Get-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398701(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-142">[New-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg425857(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-142">[New-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg425857(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-143">[Remove-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398865(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-143">[Remove-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398865(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-144">[Set-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg412949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-144">[Set-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg412949(v=OCS.15))</span></span>

<span data-ttu-id="c486b-145">**[Lync Server 2013 中的用户权利和权限 cmdlet](lync-server-2013-user-rights-and-permissions-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="c486b-145">**[User rights and permissions cmdlets in Lync Server 2013](lync-server-2013-user-rights-and-permissions-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-146">[CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399050(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-146">[Get-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399050(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-147">[新-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg398271(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-147">[New-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg398271(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-148">[Remove-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg413036(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-148">[Remove-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg413036(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-149">[Set-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399066(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-149">[Set-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399066(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-150">[Update-CsAdminRole](https://technet.microsoft.com/en-us/library/JJ204851(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-150">[Update-CsAdminRole](https://technet.microsoft.com/en-us/library/JJ204851(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c486b-151">[Get-CsAdminRoleAssignment](https://technet.microsoft.com/en-us/library/Gg398434(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-151">[Get-CsAdminRoleAssignment](https://technet.microsoft.com/en-us/library/Gg398434(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c486b-152">[授权-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg425739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-152">[Grant-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg425739(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-153">[Revoke-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398977(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-153">[Revoke-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398977(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-154">[Test-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398787(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-154">[Test-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398787(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c486b-155">[授权-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398569(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-155">[Grant-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398569(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-156">[Revoke-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg425834(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-156">[Revoke-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg425834(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c486b-157">[Test-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398428(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-157">[Test-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398428(v=OCS.15))</span></span>

<span data-ttu-id="c486b-158">**[Lync Server 2013 中的互操作性 cmdlet](lync-server-2013-interoperability-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="c486b-158">**[Interoperability cmdlets in Lync Server 2013](lync-server-2013-interoperability-cmdlets.md)**</span></span>

  - <span data-ttu-id="c486b-159">[Get-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ205155(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-159">[Get-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ205155(v=OCS.15))</span></span>

  - <span data-ttu-id="c486b-160">[Set-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ204841(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-160">[Set-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ204841(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="c486b-161">[Get-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205238(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-161">[Get-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205238(v=OCS.15))</span></span>

  - <span data-ttu-id="c486b-162">[New-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205206(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-162">[New-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205206(v=OCS.15))</span></span>

  - <span data-ttu-id="c486b-163">[Remove-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205408(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-163">[Remove-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205408(v=OCS.15))</span></span>

  - <span data-ttu-id="c486b-164">[Set-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ204896(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-164">[Set-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ204896(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="c486b-165">[Get-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ205128(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-165">[Get-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ205128(v=OCS.15))</span></span>

  - <span data-ttu-id="c486b-166">[New-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-166">[New-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15))</span></span>

  - <span data-ttu-id="c486b-167">[Remove-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204820(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-167">[Remove-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204820(v=OCS.15))</span></span>

  - <span data-ttu-id="c486b-168">[Set-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204755(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c486b-168">[Set-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204755(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c486b-169">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c486b-169">See Also</span></span>


[<span data-ttu-id="c486b-170">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="c486b-170">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

