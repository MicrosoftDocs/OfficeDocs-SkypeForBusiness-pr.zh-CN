---
title: Lync Server 2013：正在准备 Active Directory 域服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing Active Directory Domain Services
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48184583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b6e0e44367af86ea42099241ef3d9bbfa750133
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a><span data-ttu-id="ca77b-102">在 Lync Server 2013 中准备 Active Directory 域服务</span><span class="sxs-lookup"><span data-stu-id="ca77b-102">Preparing Active Directory Domain Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca77b-103">_**上次修改的主题：** 2014-02-19_</span><span class="sxs-lookup"><span data-stu-id="ca77b-103">_**Topic Last Modified:** 2014-02-19_</span></span>

<span data-ttu-id="ca77b-104">在 Lync Server 2013 中，可以使用 Lync Server 部署向导来准备 Active Directory 域服务，也可以直接使用 Lync Server Management Shell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ca77b-104">In Lync Server 2013, you can use the Lync Server Deployment Wizard to prepare Active Directory Domain Services, or you can use Lync Server Management Shell cmdlets directly.</span></span> <span data-ttu-id="ca77b-105">也可以直接在域控制器上使用 ldifde.exe 命令行工具，相关信息将在本主题后面的内容中进行介绍。</span><span class="sxs-lookup"><span data-stu-id="ca77b-105">You can also use the ldifde.exe command line tool directly on your domain controllers, as described later in this topic.</span></span>

<span data-ttu-id="ca77b-106">Lync Server 部署向导将指导您完成每个 Active Directory 准备任务。</span><span class="sxs-lookup"><span data-stu-id="ca77b-106">The Lync Server Deployment Wizard guides you through each Active Directory preparation task.</span></span> <span data-ttu-id="ca77b-107">部署向导运行 Lync Server 命令行管理程序 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ca77b-107">The Deployment Wizard runs Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="ca77b-108">对于单域、单林拓扑或其他类似拓扑的环境，此工具很有用。</span><span class="sxs-lookup"><span data-stu-id="ca77b-108">This tool is useful for environments with a single domain and single forest topology, or other similar topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ca77b-109">您可以在域控制器运行32位版本的操作系统的林或域中部署 Lync Server （有关详细信息，请参阅<A href="lync-server-2013-active-directory-infrastructure-requirements.md">Lync Server 2013 的 Active Directory 基础结构要求</A>）。</span><span class="sxs-lookup"><span data-stu-id="ca77b-109">You can deploy Lync Server in a forest or domain where domain controllers run 32-bit versions of some operating systems (for details, see <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory infrastructure requirements for Lync Server 2013</A>).</span></span> <span data-ttu-id="ca77b-110">但是，不能使用 Lync Server 部署向导在这些环境中运行架构、林和域的准备工作，因为部署向导和支持文件仅为64位。</span><span class="sxs-lookup"><span data-stu-id="ca77b-110">However, you cannot use the Lync Server Deployment Wizard to run schema, forest, and domain preparation in these environments because the Deployment Wizard and supporting files are 64-bit only.</span></span> <span data-ttu-id="ca77b-111">可以改为在 32 位域控制器上使用 ldifde.exe 和 associated .ldf 文件来准备架构、林和域。</span><span class="sxs-lookup"><span data-stu-id="ca77b-111">Instead, you can use ldifde.exe and the associated .ldf files on a 32-bit domain controller to prepare the schema, forest and domain.</span></span> <span data-ttu-id="ca77b-112">请参阅本主题稍后的“使用 Cmdlet 和 Ldifde.exe”一节。</span><span class="sxs-lookup"><span data-stu-id="ca77b-112">See the section “Using Cmdlets and Ldifde.exe” later in this topic.</span></span>



</div>

<span data-ttu-id="ca77b-113">您可以使用 Lync Server 命令行管理程序 cmdlet 远程运行任务，也可以使用更复杂的环境运行任务。</span><span class="sxs-lookup"><span data-stu-id="ca77b-113">You can use Lync Server Management Shell cmdlets to run tasks remotely or for more complex environments.</span></span>

<div>

## <a name="active-directory-preparation-prerequisites"></a><span data-ttu-id="ca77b-114">Active Directory 准备先决条件</span><span class="sxs-lookup"><span data-stu-id="ca77b-114">Active Directory Preparation Prerequisites</span></span>

<span data-ttu-id="ca77b-115">您必须在运行 Windows Server 2012、Windows Server 2012 R2 或 Windows Server 2008 R2 SP1 （64）的计算机上运行 Active Directory 准备步骤。</span><span class="sxs-lookup"><span data-stu-id="ca77b-115">You must run Active Directory preparation steps on a computer running Windows Server 2012, Windows Server 2012 R2, or Windows Server 2008 R2 with SP1 (64-bit).</span></span> <span data-ttu-id="ca77b-116">Active Directory 准备需要 Lync Server 命令行管理程序和 OCSCore。</span><span class="sxs-lookup"><span data-stu-id="ca77b-116">Active Directory preparation requires Lync Server Management Shell and OCSCore.</span></span>

<span data-ttu-id="ca77b-117">运行 Active Directory 准备任务需要以下组件：</span><span class="sxs-lookup"><span data-stu-id="ca77b-117">The following components are required to run Active Directory preparation tasks:</span></span>

  - <span data-ttu-id="ca77b-118">Lync Server 核心组件（OCScore）</span><span class="sxs-lookup"><span data-stu-id="ca77b-118">Lync Server Core components (OCScore.msi)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ca77b-119">如果您计划使用 Lync Server 命令行管理程序进行 Active Directory 准备，则必须首先运行 Lync Server 部署向导来安装核心组件。</span><span class="sxs-lookup"><span data-stu-id="ca77b-119">If you plan to use Lync Server Management Shell for Active Directory preparation, you must run the Lync Server Deployment Wizard first to install Core components.</span></span>

    
    </div>

  - <span data-ttu-id="ca77b-120">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="ca77b-120">Microsoft .NET Framework 4.5</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ca77b-121">对于 Windows Server 2012 和 Windows Server 2012 R2，请使用服务器管理器安装和激活 .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="ca77b-121">For Windows Server 2012 and Windows Server 2012 R2, you install and activate .NET Framework 4.5 by using Server Manager.</span></span> <span data-ttu-id="ca77b-122">有关详细信息，请参阅<A href="lync-server-2013-additional-software-requirements.md">Lync Server 2013 的其他软件要求</A>中的 "Microsoft .net Framework 4.5"。</span><span class="sxs-lookup"><span data-stu-id="ca77b-122">For details, see "Microsoft .NET Framework 4.5" in <A href="lync-server-2013-additional-software-requirements.md">Additional software requirements for Lync Server 2013</A>.</span></span> <span data-ttu-id="ca77b-123">对于 Windows Server&nbsp;2008&nbsp;R2，请从 Microsoft 网站下载并安装<A href="https://www.microsoft.com/download/details.aspx?id=30653">.net Framework 4.5</A> 。</span><span class="sxs-lookup"><span data-stu-id="ca77b-123">For Windows Server&nbsp;2008&nbsp;R2, download and install <A href="https://www.microsoft.com/download/details.aspx?id=30653">.Net Framework 4.5</A> from the Microsoft web site.</span></span>

    
    </div>

  - <span data-ttu-id="ca77b-124">远程服务器管理工具 (RSAT)</span><span class="sxs-lookup"><span data-stu-id="ca77b-124">Remote Server Administration Tools (RSAT)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ca77b-125">如果在成员服务器而不是域控制器上运行 Active Directory 准备步骤，则需要使用某些 RSAT 工具。</span><span class="sxs-lookup"><span data-stu-id="ca77b-125">Some RSAT tools are required if you run Active Directory preparation steps on a member server rather than on a domain controller.</span></span> <span data-ttu-id="ca77b-126">从 "服务器管理器" 中的 "AD DS" 和 "AD LDS 工具" 节点安装 AD DS 管理单元和命令行工具以及 Active Directory Module for Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="ca77b-126">Install the AD DS snap-ins and command-line tools and the Active Directory Module for Windows PowerShell from the AD DS and AD LDS Tools node in Server Manager.</span></span>

    
    </div>

  - <span data-ttu-id="ca77b-127">Microsoft Visual c + + 11 可再发行组件</span><span class="sxs-lookup"><span data-stu-id="ca77b-127">Microsoft Visual C++ 11 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ca77b-p107">如果计算机中尚未安装此必备软件，安装程序会提示您进行安装。将为您提供此软件包，不需要单独购买。</span><span class="sxs-lookup"><span data-stu-id="ca77b-p107">Setup prompts you to install this prerequisite if it is not already installed on the computer. The package is supplied for you, and you will not have to acquire it separately.</span></span>

    
    </div>

  - <span data-ttu-id="ca77b-130">Windows PowerShell 3.0 （64-位）</span><span class="sxs-lookup"><span data-stu-id="ca77b-130">Windows PowerShell 3.0 (64-bit)</span></span>
    
    <span data-ttu-id="ca77b-131">对于 Windows Server 2012 和 Windows Server 2012 R2，Windows PowerShell 3.0 应包含在 Lync Server 2013 安装中。</span><span class="sxs-lookup"><span data-stu-id="ca77b-131">For Windows Server 2012 and Windows Server 2012 R2, Windows PowerShell 3.0 should be included with your Lync Server 2013 installation.</span></span> <span data-ttu-id="ca77b-132">对于 Windows Server 2008 R2，您需要安装或升级到 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="ca77b-132">For Windows Server 2008 R2, you need to install or upgrade to Windows PowerShell 3.0.</span></span> <span data-ttu-id="ca77b-133">有关详细信息，请参阅[安装适用于 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)</span><span class="sxs-lookup"><span data-stu-id="ca77b-133">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)</span></span>

</div>

<div>

## <a name="administrator-rights-and-roles"></a><span data-ttu-id="ca77b-134">管理员权限和角色</span><span class="sxs-lookup"><span data-stu-id="ca77b-134">Administrator Rights and Roles</span></span>

<span data-ttu-id="ca77b-135">下表显示了每个 Active Directory 准备任务需要的管理权限和角色。</span><span class="sxs-lookup"><span data-stu-id="ca77b-135">The following table shows the administrative rights and roles required for each Active Directory preparation task.</span></span>

### <a name="user-rights-required-for-active-directory-preparation"></a><span data-ttu-id="ca77b-136">Active Directory 准备任务需要的用户权限</span><span class="sxs-lookup"><span data-stu-id="ca77b-136">User Rights Required for Active Directory Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca77b-137">Procedure</span><span class="sxs-lookup"><span data-stu-id="ca77b-137">Procedure</span></span></th>
<th><span data-ttu-id="ca77b-138">权限或角色</span><span class="sxs-lookup"><span data-stu-id="ca77b-138">Rights or roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca77b-139">架构准备</span><span class="sxs-lookup"><span data-stu-id="ca77b-139">Schema preparation</span></span></p></td>
<td><p><span data-ttu-id="ca77b-140">架构主机上林根域的 Schema Admins 组成员和管理员权限</span><span class="sxs-lookup"><span data-stu-id="ca77b-140">Member of Schema Admins group for the forest root domain and administrator rights on the schema master</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca77b-141">林准备</span><span class="sxs-lookup"><span data-stu-id="ca77b-141">Forest preparation</span></span></p></td>
<td><p><span data-ttu-id="ca77b-142">林的 Enterprise Admins 组成员</span><span class="sxs-lookup"><span data-stu-id="ca77b-142">Member of Enterprise Admins group for the forest</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca77b-143">域准备</span><span class="sxs-lookup"><span data-stu-id="ca77b-143">Domain preparation</span></span></p></td>
<td><p><span data-ttu-id="ca77b-144">指定域的 Enterprise Admins 或 Domain Admins 组成员</span><span class="sxs-lookup"><span data-stu-id="ca77b-144">Member of Enterprise Admins or Domain Admins group for the specified domain</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a><span data-ttu-id="ca77b-145">Active Directory 准备 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="ca77b-145">Active Directory Preparation Cmdlets</span></span>

<span data-ttu-id="ca77b-146">下表将用于准备 AD DS 的 Lync Server 命令行管理程序 cmdlet 与用于在 Microsoft Office 通信服务器 2007 R2 中准备 AD DS 的 LcsCmd 命令进行比较。</span><span class="sxs-lookup"><span data-stu-id="ca77b-146">The following table compares the Lync Server Management Shell cmdlets used to prepare AD DS to the LcsCmd commands used to prepare AD DS in Microsoft Office Communications Server 2007 R2.</span></span>

### <a name="cmdlets-compared-to-lcscmd"></a><span data-ttu-id="ca77b-147">Cmdlet 与 LcsCmd 比较</span><span class="sxs-lookup"><span data-stu-id="ca77b-147">Cmdlets Compared to LcsCmd</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca77b-148">cmdlet</span><span class="sxs-lookup"><span data-stu-id="ca77b-148">Cmdlets</span></span></th>
<th><span data-ttu-id="ca77b-149">确认</span><span class="sxs-lookup"><span data-stu-id="ca77b-149">LcsCmd</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca77b-150">Install-CsAdServerSchema</span><span class="sxs-lookup"><span data-stu-id="ca77b-150">Install-CsAdServerSchema</span></span></p></td>
<td><p><span data-ttu-id="ca77b-151">Lcscmd /forest /action:SchemaPrep /SchemaType:Server</span><span class="sxs-lookup"><span data-stu-id="ca77b-151">Lcscmd /forest /action:SchemaPrep /SchemaType:Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca77b-152">CsAdServerSchema</span><span class="sxs-lookup"><span data-stu-id="ca77b-152">Get-CsAdServerSchema</span></span></p></td>
<td><p><span data-ttu-id="ca77b-153">Lcscmd /forest /action:CheckSchemaPrepState</span><span class="sxs-lookup"><span data-stu-id="ca77b-153">Lcscmd /forest /action:CheckSchemaPrepState</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca77b-154">Enable-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="ca77b-154">Enable-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="ca77b-155">Lcscmd /forest /action:ForestPrep</span><span class="sxs-lookup"><span data-stu-id="ca77b-155">Lcscmd /forest /action:ForestPrep</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca77b-156">Disable-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="ca77b-156">Disable-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="ca77b-157">Lcscmd /forest /action:ForestUnprep</span><span class="sxs-lookup"><span data-stu-id="ca77b-157">Lcscmd /forest /action:ForestUnprep</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca77b-158">CsAdForest</span><span class="sxs-lookup"><span data-stu-id="ca77b-158">Get-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="ca77b-159">Lcscmd /forest /action:CheckForestPrepState</span><span class="sxs-lookup"><span data-stu-id="ca77b-159">Lcscmd /forest /action:CheckForestPrepState</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca77b-160">Enable-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="ca77b-160">Enable-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="ca77b-161">Lcscmd /domain /action:DomainPrep</span><span class="sxs-lookup"><span data-stu-id="ca77b-161">Lcscmd /domain /action:DomainPrep</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca77b-162">Disable-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="ca77b-162">Disable-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="ca77b-163">Lcscmd /domain /action:DomainUnprep</span><span class="sxs-lookup"><span data-stu-id="ca77b-163">Lcscmd /domain /action: DomainUnprep</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca77b-164">CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="ca77b-164">Get-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="ca77b-165">Lcscmd /domain /action:CheckDomainPrepState</span><span class="sxs-lookup"><span data-stu-id="ca77b-165">Lcscmd /domain /action:CheckDomainPrepState</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a><span data-ttu-id="ca77b-166">锁定的 Active Directory 要求</span><span class="sxs-lookup"><span data-stu-id="ca77b-166">Locked Down Active Directory Requirements</span></span>

<span data-ttu-id="ca77b-167">如果在组织中禁用了权限继承，或者必须禁用通过身份验证的用户权限，则在域准备期间还必须执行其他步骤。</span><span class="sxs-lookup"><span data-stu-id="ca77b-167">If permissions inheritance is disabled or authenticated user permissions must be disabled in your organization, you must perform additional steps during domain preparation.</span></span> <span data-ttu-id="ca77b-168">有关详细信息，请参阅[在 Lync Server 2013 中准备锁定的 Active Directory 域服务](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)。</span><span class="sxs-lookup"><span data-stu-id="ca77b-168">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span></span>

</div>

<div>

## <a name="custom-container-permissions"></a><span data-ttu-id="ca77b-169">自定义容器权限</span><span class="sxs-lookup"><span data-stu-id="ca77b-169">Custom Container Permissions</span></span>

<span data-ttu-id="ca77b-170">如果组织使用自定义容器代替三个内置容器（即“用户”、“计算机”和“域控制器”），则必须为 Authenticated Users 组授予自定义容器的读取权限。</span><span class="sxs-lookup"><span data-stu-id="ca77b-170">If your organization uses custom containers instead of the three built-in containers (that is, Users, Computers, and Domain Controllers), you must grant read access to the custom containers for the Authenticated Users group.</span></span> <span data-ttu-id="ca77b-171">域准备需要具有容器的读取权限。</span><span class="sxs-lookup"><span data-stu-id="ca77b-171">Read access to the containers is required for domain preparation.</span></span> <span data-ttu-id="ca77b-172">有关详细信息，请参阅[为 Lync Server 2013 准备域](lync-server-2013-preparing-domains.md)。</span><span class="sxs-lookup"><span data-stu-id="ca77b-172">For details, see [Preparing domains for Lync Server 2013](lync-server-2013-preparing-domains.md).</span></span>

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a><span data-ttu-id="ca77b-173">使用 Cmdlet 和 Ldifde.exe</span><span class="sxs-lookup"><span data-stu-id="ca77b-173">Using Cmdlets and Ldifde.exe</span></span>

<span data-ttu-id="ca77b-174">Lync Server 部署向导中的 "**准备架构**" 步骤和**CsAdServerSchema** cmdlet 将在运行64位操作系统的域控制器上扩展 Active Directory 架构。</span><span class="sxs-lookup"><span data-stu-id="ca77b-174">The **Prepare Schema** step in the Lync Server Deployment Wizard and the **Install-CsAdServerSchema** cmdlet extend the Active Directory schema on domain controllers running a 64-bit operating system.</span></span> <span data-ttu-id="ca77b-175">如果需要在运行 32 位操作系统的域控制器上扩展 Active Directory 架构，可以从成员服务器远程运行 **Install-CsAdServerSchema** cmdlet（推荐方法）。</span><span class="sxs-lookup"><span data-stu-id="ca77b-175">If you need to extend the Active Directory schema on a domain controller running a 32-bit operating system, you can run the **Install-CsAdServerSchema** cmdlet remotely from a member server (recommended approach).</span></span> <span data-ttu-id="ca77b-176">但是，如果需要直接在域控制器上运行架构准备，可以使用 Ldifde.exe 工具导入架构文件。</span><span class="sxs-lookup"><span data-stu-id="ca77b-176">If you need to run schema preparation directly on the domain controller, however, you can use the Ldifde.exe tool to import the schema files.</span></span> <span data-ttu-id="ca77b-177">Windows 操作系统的大多数版本均附带 Ldifde.exe 工具。</span><span class="sxs-lookup"><span data-stu-id="ca77b-177">The Ldifde.exe tool comes with most versions of the Windows operating system.</span></span>

<span data-ttu-id="ca77b-p112">如果使用 Ldifde.exe 导入架构文件，则不管是从以前的版本迁移还是执行全新安装，都必须导入所有四个文件。必须按以下顺序导入这些文件：</span><span class="sxs-lookup"><span data-stu-id="ca77b-p112">If you use Ldifde.exe to import the schema files, you must import all four files, regardless of whether you are migrating from a previous version or performing a clean installation. You must import them in the following sequence:</span></span>

1.  <span data-ttu-id="ca77b-180">ExternalSchema</span><span class="sxs-lookup"><span data-stu-id="ca77b-180">ExternalSchema.ldf</span></span>

2.  <span data-ttu-id="ca77b-181">ServerSchema</span><span class="sxs-lookup"><span data-stu-id="ca77b-181">ServerSchema.ldf</span></span>

3.  <span data-ttu-id="ca77b-182">BackCompatSchema</span><span class="sxs-lookup"><span data-stu-id="ca77b-182">BackCompatSchema.ldf</span></span>

4.  <span data-ttu-id="ca77b-183">VersionSchema</span><span class="sxs-lookup"><span data-stu-id="ca77b-183">VersionSchema.ldf</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ca77b-184">这四个 .ldf 文件位于安装介质或下载的 \Support\Schema 目录中。</span><span class="sxs-lookup"><span data-stu-id="ca77b-184">The four .ldf files are located in \Support\Schema directory of your installation media or download.</span></span>



</div>

<span data-ttu-id="ca77b-185">要在充当架构主机的域控制器上使用 Ldifde.exe 导入这四个架构文件，请使用以下格式：</span><span class="sxs-lookup"><span data-stu-id="ca77b-185">To use Ldifde.exe to import the four schema files on a domain controller that is the schema master, use the following format:</span></span>

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

<span data-ttu-id="ca77b-186">例如：</span><span class="sxs-lookup"><span data-stu-id="ca77b-186">For example:</span></span>

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> <span data-ttu-id="ca77b-p113">仅当以其他用户身份登录时才使用 b 参数。有关所需用户权限的详细信息，请参阅本主题前面的“管理员权限和角色”一节。</span><span class="sxs-lookup"><span data-stu-id="ca77b-p113">Use the b parameter only if you are logged in as a different user. For details about the required user rights, see the "Administrator Rights and Roles" section earlier in this topic.</span></span>



</div>

<span data-ttu-id="ca77b-189">要在架构主机以外的域控制器上使用 Ldifde.exe 导入这四个架构文件，请使用以下格式：</span><span class="sxs-lookup"><span data-stu-id="ca77b-189">To use Ldifde.exe to import the four schema files on a domain controller that is not the schema master, use the following format:</span></span>

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

<span data-ttu-id="ca77b-190">有关使用 Ldifde 的详细信息，请参阅 Microsoft 知识库文章 237677 "使用 LDIFDE 将目录对象导入和导出到 Active Directory" [https://go.microsoft.com/fwlink/p/?linkId=132204](https://go.microsoft.com/fwlink/p/?linkid=132204)。</span><span class="sxs-lookup"><span data-stu-id="ca77b-190">For details about using Ldifde, see Microsoft Knowledge Base article 237677, "Using LDIFDE to import and export directory objects to Active Directory," at [https://go.microsoft.com/fwlink/p/?linkId=132204](https://go.microsoft.com/fwlink/p/?linkid=132204).</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ca77b-191">本部分内容</span><span class="sxs-lookup"><span data-stu-id="ca77b-191">In This Section</span></span>

  - [<span data-ttu-id="ca77b-192">在 Lync Server 2013 中准备 Active Directory 架构</span><span class="sxs-lookup"><span data-stu-id="ca77b-192">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)

  - [<span data-ttu-id="ca77b-193">准备 Lync Server 2013 的林</span><span class="sxs-lookup"><span data-stu-id="ca77b-193">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)

  - [<span data-ttu-id="ca77b-194">准备 Lync Server 2013 的域</span><span class="sxs-lookup"><span data-stu-id="ca77b-194">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

