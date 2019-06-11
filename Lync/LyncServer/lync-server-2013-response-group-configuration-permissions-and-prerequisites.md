---
title: Lync Server 2013：响应组配置权限和先决条件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response Group configuration permissions and prerequisites
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48183972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1360a6dee8dbbf169fa0ceda1ee1b2f215ff09b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823271"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a><span data-ttu-id="7cd96-102">Lync Server 2013 中的响应组配置权限和先决条件</span><span class="sxs-lookup"><span data-stu-id="7cd96-102">Response Group configuration permissions and prerequisites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7cd96-103">_**主题上次修改时间:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="7cd96-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="7cd96-104">响应组是企业语音呼叫管理功能。</span><span class="sxs-lookup"><span data-stu-id="7cd96-104">Response Group is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="7cd96-105">本主题介绍了在可以配置响应组以及执行配置任务所需的管理凭据和权限之前需要具备的准备工作。</span><span class="sxs-lookup"><span data-stu-id="7cd96-105">This topic describes what you need to have in place before you can configure Response Group and the administrative credentials and permissions you need to perform configuration tasks.</span></span>

<span data-ttu-id="7cd96-106">本部分假设你已阅读与响应组相关的计划文档。</span><span class="sxs-lookup"><span data-stu-id="7cd96-106">This section assumes that you have read the planning documentation related to Response Group.</span></span> <span data-ttu-id="7cd96-107">有关详细信息, 请参阅规划文档中[Lync Server 2013 中的 "规划呼叫管理功能](lync-server-2013-planning-for-call-management-features.md)"。</span><span class="sxs-lookup"><span data-stu-id="7cd96-107">For details, see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) in the Planning documentation.</span></span>

<div>

## <a name="configuration-tools-and-administrative-roles"></a><span data-ttu-id="7cd96-108">配置工具和管理角色</span><span class="sxs-lookup"><span data-stu-id="7cd96-108">Configuration Tools and Administrative Roles</span></span>

<span data-ttu-id="7cd96-109">可以使用以下管理工具配置响应组:</span><span class="sxs-lookup"><span data-stu-id="7cd96-109">You can use the following administrative tools to configure Response Group:</span></span>

  - <span data-ttu-id="7cd96-110">Lync Server 控制面板</span><span class="sxs-lookup"><span data-stu-id="7cd96-110">Lync Server Control Panel</span></span>

  - <span data-ttu-id="7cd96-111">响应组配置工具</span><span class="sxs-lookup"><span data-stu-id="7cd96-111">Response Group Configuration Tool</span></span>

  - <span data-ttu-id="7cd96-112">Lync Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="7cd96-112">Lync Server Management Shell</span></span>

<span data-ttu-id="7cd96-113">若要配置响应组，您必须至少成为以下管理角色之一的成员：</span><span class="sxs-lookup"><span data-stu-id="7cd96-113">To configure response groups, you must be a member of at least one of the following administrative roles:</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7cd96-114"><strong>Active Directory 安全组 (1)</strong></span><span class="sxs-lookup"><span data-stu-id="7cd96-114"><strong>Active Directory Security Group (1)</strong></span></span></p></td>
<td><p><span data-ttu-id="7cd96-115">创建工作流</span><span class="sxs-lookup"><span data-stu-id="7cd96-115">Create Workflow</span></span></p></td>
<td><p><span data-ttu-id="7cd96-116">分派管理者</span><span class="sxs-lookup"><span data-stu-id="7cd96-116">Assign Manager</span></span></p></td>
<td><p><span data-ttu-id="7cd96-117">创建/分派代理、队列</span><span class="sxs-lookup"><span data-stu-id="7cd96-117">Create /assign agents, queues</span></span></p></td>
<td><p><span data-ttu-id="7cd96-118">创建/管理假日和工作时间</span><span class="sxs-lookup"><span data-stu-id="7cd96-118">Create / manage holiday and business hours</span></span></p></td>
<td><p><span data-ttu-id="7cd96-119">激活/停用工作流</span><span class="sxs-lookup"><span data-stu-id="7cd96-119">Activate / deactivate workflow</span></span></p></td>
<td><p><span data-ttu-id="7cd96-120">配置工作流（IVR 或智能寻线）</span><span class="sxs-lookup"><span data-stu-id="7cd96-120">Configure workflow (IVR or Hunt Group)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cd96-121"><strong>CsResponseGroupAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="7cd96-121"><strong>CsResponseGroupAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="7cd96-122">√</span><span class="sxs-lookup"><span data-stu-id="7cd96-122">√</span></span></p></td>
<td><p><span data-ttu-id="7cd96-123">√</span><span class="sxs-lookup"><span data-stu-id="7cd96-123">√</span></span></p></td>
<td><p><span data-ttu-id="7cd96-124">√</span><span class="sxs-lookup"><span data-stu-id="7cd96-124">√</span></span></p></td>
<td><p><span data-ttu-id="7cd96-125">√</span><span class="sxs-lookup"><span data-stu-id="7cd96-125">√</span></span></p></td>
<td><p><span data-ttu-id="7cd96-126">√</span><span class="sxs-lookup"><span data-stu-id="7cd96-126">√</span></span></p></td>
<td><p><span data-ttu-id="7cd96-127">√</span><span class="sxs-lookup"><span data-stu-id="7cd96-127">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cd96-128"><strong>CsResponseGroupManager</strong></span><span class="sxs-lookup"><span data-stu-id="7cd96-128"><strong>CsResponseGroupManager</strong></span></span></p></td>
<td> </td>
<td><p><span data-ttu-id="7cd96-129">√(2)</span><span class="sxs-lookup"><span data-stu-id="7cd96-129">√(2)</span></span></p></td>
<td><p><span data-ttu-id="7cd96-130">√(3)</span><span class="sxs-lookup"><span data-stu-id="7cd96-130">√(3)</span></span></p></td>
<td><p><span data-ttu-id="7cd96-131">√(3)</span><span class="sxs-lookup"><span data-stu-id="7cd96-131">√(3)</span></span></p></td>
<td><p><span data-ttu-id="7cd96-132">√(3)</span><span class="sxs-lookup"><span data-stu-id="7cd96-132">√(3)</span></span></p></td>
<td><p><span data-ttu-id="7cd96-133">√(3)</span><span class="sxs-lookup"><span data-stu-id="7cd96-133">√(3)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cd96-134"><strong>CsVoiceAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="7cd96-134"><strong>CsVoiceAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="7cd96-135">√</span><span class="sxs-lookup"><span data-stu-id="7cd96-135">√</span></span></p></td>
<td><p><span data-ttu-id="7cd96-136">√</span><span class="sxs-lookup"><span data-stu-id="7cd96-136">√</span></span></p></td>
<td><p><span data-ttu-id="7cd96-137">√</span><span class="sxs-lookup"><span data-stu-id="7cd96-137">√</span></span></p></td>
<td><p><span data-ttu-id="7cd96-138">√</span><span class="sxs-lookup"><span data-stu-id="7cd96-138">√</span></span></p></td>
<td><p><span data-ttu-id="7cd96-139">√</span><span class="sxs-lookup"><span data-stu-id="7cd96-139">√</span></span></p></td>
<td><p><span data-ttu-id="7cd96-140">√</span><span class="sxs-lookup"><span data-stu-id="7cd96-140">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cd96-141"><strong>CsServerAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="7cd96-141"><strong>CsServerAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="7cd96-142">√</span><span class="sxs-lookup"><span data-stu-id="7cd96-142">√</span></span></p></td>
<td><p><span data-ttu-id="7cd96-143">√</span><span class="sxs-lookup"><span data-stu-id="7cd96-143">√</span></span></p></td>
<td><p><span data-ttu-id="7cd96-144">√</span><span class="sxs-lookup"><span data-stu-id="7cd96-144">√</span></span></p></td>
<td><p><span data-ttu-id="7cd96-145">√</span><span class="sxs-lookup"><span data-stu-id="7cd96-145">√</span></span></p></td>
<td><p><span data-ttu-id="7cd96-146">√</span><span class="sxs-lookup"><span data-stu-id="7cd96-146">√</span></span></p></td>
<td><p><span data-ttu-id="7cd96-147">√</span><span class="sxs-lookup"><span data-stu-id="7cd96-147">√</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cd96-148"><strong>CsAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="7cd96-148"><strong>CsAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="7cd96-149">√</span><span class="sxs-lookup"><span data-stu-id="7cd96-149">√</span></span></p></td>
<td><p><span data-ttu-id="7cd96-150">√</span><span class="sxs-lookup"><span data-stu-id="7cd96-150">√</span></span></p></td>
<td><p><span data-ttu-id="7cd96-151">√</span><span class="sxs-lookup"><span data-stu-id="7cd96-151">√</span></span></p></td>
<td><p><span data-ttu-id="7cd96-152">√</span><span class="sxs-lookup"><span data-stu-id="7cd96-152">√</span></span></p></td>
<td><p><span data-ttu-id="7cd96-153">√</span><span class="sxs-lookup"><span data-stu-id="7cd96-153">√</span></span></p></td>
<td><p><span data-ttu-id="7cd96-154">√</span><span class="sxs-lookup"><span data-stu-id="7cd96-154">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cd96-155"><strong>CsViewOnlyAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="7cd96-155"><strong>CsViewOnlyAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="7cd96-156">√(4)</span><span class="sxs-lookup"><span data-stu-id="7cd96-156">√(4)</span></span></p></td>
<td><p><span data-ttu-id="7cd96-157">√(4)</span><span class="sxs-lookup"><span data-stu-id="7cd96-157">√(4)</span></span></p></td>
<td><p><span data-ttu-id="7cd96-158">√(4)</span><span class="sxs-lookup"><span data-stu-id="7cd96-158">√(4)</span></span></p></td>
<td><p><span data-ttu-id="7cd96-159">√(4)</span><span class="sxs-lookup"><span data-stu-id="7cd96-159">√(4)</span></span></p></td>
<td><p><span data-ttu-id="7cd96-160">√(4)</span><span class="sxs-lookup"><span data-stu-id="7cd96-160">√(4)</span></span></p></td>
<td><p><span data-ttu-id="7cd96-161">√(4)</span><span class="sxs-lookup"><span data-stu-id="7cd96-161">√(4)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="7cd96-162"><STRONG>(1)</STRONG> Active Directory 域服务用户对象必须是所列的指定 Active directory 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="7cd96-162"><STRONG>(1)</STRONG> An Active Directory Domain Services user object must be a member of the specified Active Directory security group listed.</span></span> <span data-ttu-id="7cd96-163">具有将用户添加到安全组的相应权限的管理员或其他委派的 Active Directory 组成员 (例如管理员、帐户操作员) 必须将用户对象添加到列出的安全组或组中, 以便用户能够执行列出的函数。</span><span class="sxs-lookup"><span data-stu-id="7cd96-163">An administrator or other delegated Active Directory group member with appropriate permissions to add users to a security group (For example, Administrator, Account Operators) must add a user object to the listed security group or group for the user to be able to perform the functions listed.</span></span> <span data-ttu-id="7cd96-164"><STRONG>(2)</STRONG>仅适用于 CsResponseGroupAdministrator 分配给 CsResponseGroupManager 的工作流。</span><span class="sxs-lookup"><span data-stu-id="7cd96-164"><STRONG>(2)</STRONG> Only for workflows that the CsResponseGroupAdministrator has assigned to the CsResponseGroupManager.</span></span> <span data-ttu-id="7cd96-165"><STRONG>(3)</STRONG>响应组管理器可以将 CsResponseGroupManager 的另一个成员分配给当前管理器已管理的工作流。</span><span class="sxs-lookup"><span data-stu-id="7cd96-165"><STRONG>(3)</STRONG> A Response Group Manager can assign another member of CsResponseGroupManager to a workflow that the current manager already manages.</span></span> <span data-ttu-id="7cd96-166"><STRONG>(4)</STRONG> CsViewOnlyAdministrator 仅可运行动词 "Get" Lync Server Management Shell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7cd96-166"><STRONG>(4)</STRONG> CsViewOnlyAdministrator can only run verb "Get" Lync Server Management Shell cmdlets.</span></span>



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a><span data-ttu-id="7cd96-167">响应组配置先决条件</span><span class="sxs-lookup"><span data-stu-id="7cd96-167">Response Group Configuration Prerequisites</span></span>

<span data-ttu-id="7cd96-168">响应组需要以下组件:</span><span class="sxs-lookup"><span data-stu-id="7cd96-168">Response Group requires the following components:</span></span>

  - <span data-ttu-id="7cd96-169">应用程序服务</span><span class="sxs-lookup"><span data-stu-id="7cd96-169">Application service</span></span>

  - <span data-ttu-id="7cd96-170">响应组应用程序</span><span class="sxs-lookup"><span data-stu-id="7cd96-170">Response Group application</span></span>

  - <span data-ttu-id="7cd96-171">语言包</span><span class="sxs-lookup"><span data-stu-id="7cd96-171">Language packs</span></span>

  - <span data-ttu-id="7cd96-172">文件存储（用于保存音频文件）</span><span class="sxs-lookup"><span data-stu-id="7cd96-172">File store (to hold audio files)</span></span>

  - <span data-ttu-id="7cd96-173">Web 服务 (包括响应组配置工具和代理的登录和注销控制台)</span><span class="sxs-lookup"><span data-stu-id="7cd96-173">Web Services (includes the Response Group Configuration Tool and the agents' sign-in and sign-out console)</span></span>

<span data-ttu-id="7cd96-174">在部署企业语音时, 默认情况下会安装所有这些组件。</span><span class="sxs-lookup"><span data-stu-id="7cd96-174">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

<span data-ttu-id="7cd96-175">在配置响应组之前, 可能需要执行以下任务:</span><span class="sxs-lookup"><span data-stu-id="7cd96-175">You might need to perform the following tasks before configuring Response Group:</span></span>

  - <span data-ttu-id="7cd96-176">为 Lync Server 2013 和企业语音启用用户。</span><span class="sxs-lookup"><span data-stu-id="7cd96-176">Enable users for Lync Server 2013 and Enterprise Voice.</span></span>

  - <span data-ttu-id="7cd96-177">修改配置文件以符合联邦信息处理标准 (FIPS)。</span><span class="sxs-lookup"><span data-stu-id="7cd96-177">Modify a configuration file to be compliant with Federal Information Processing Standards (FIPS).</span></span>

  - <span data-ttu-id="7cd96-178">修改数据库排序规则以支持队列名称和代理组名称的 Yi、Meng 和 Zang 字符。</span><span class="sxs-lookup"><span data-stu-id="7cd96-178">Modify the database collation to support Yi, Meng, and Zang characters for queue names and agent group names.</span></span>

<div>

## <a name="enabling-users"></a><span data-ttu-id="7cd96-179">启用用户</span><span class="sxs-lookup"><span data-stu-id="7cd96-179">Enabling Users</span></span>

<span data-ttu-id="7cd96-180">配置响应组的第一步是创建代理组。</span><span class="sxs-lookup"><span data-stu-id="7cd96-180">The first step in configuring Response Group is to create agent groups.</span></span> <span data-ttu-id="7cd96-181">在创建代理组之前, 必须启用将用作 Lync Server 2013 和企业语音的 "响应" 组的代理用户。</span><span class="sxs-lookup"><span data-stu-id="7cd96-181">Before you can create an agent group, you must enable the users who will be agents for Response Group for Lync Server 2013 and Enterprise Voice.</span></span> <span data-ttu-id="7cd96-182">为 Lync Server 2013 启用用户通常是企业版 server 或标准版服务器部署中的一个步骤。</span><span class="sxs-lookup"><span data-stu-id="7cd96-182">Enabling users for Lync Server 2013 is typically a step in the Enterprise Edition server or Standard Edition server deployment.</span></span> <span data-ttu-id="7cd96-183">有关为 Lync Server 2013 启用用户的详细信息, 请参阅[禁用或重新启用 Lync server 2013 的用户帐户](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)。</span><span class="sxs-lookup"><span data-stu-id="7cd96-183">For details about enabling users for Lync Server 2013, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span></span> <span data-ttu-id="7cd96-184">为企业语音启用用户通常是企业语音部署中的一个步骤。</span><span class="sxs-lookup"><span data-stu-id="7cd96-184">Enabling users for Enterprise Voice is typically a step in the Enterprise Voice deployment.</span></span> <span data-ttu-id="7cd96-185">有关详细信息, 请参阅[在 Lync Server 2013 中启用企业语音用户](lync-server-2013-enable-users-for-enterprise-voice.md)。</span><span class="sxs-lookup"><span data-stu-id="7cd96-185">For details, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>

</div>

<div>

## <a name="complying-with-fips-requirements"></a><span data-ttu-id="7cd96-186">符合 FIPS 要求</span><span class="sxs-lookup"><span data-stu-id="7cd96-186">Complying with FIPS requirements</span></span>

<span data-ttu-id="7cd96-187">仅当您的组织需要符合联邦信息处理标准 (FIPS) 时，本节才适用。</span><span class="sxs-lookup"><span data-stu-id="7cd96-187">This section applies to you only if your organization needs to comply with Federal Information Processing Standards (FIPS).</span></span>

<span data-ttu-id="7cd96-188">要符合 FIPS，安装 Web 服务后需要修改应用程序级别 Web.config 文件，以使用不同的加密算法。</span><span class="sxs-lookup"><span data-stu-id="7cd96-188">To be compliant with FIPS, you need to modify the application-level Web.config file to use a different cryptography algorithm after you install Web Services.</span></span> <span data-ttu-id="7cd96-189">需要指定 ASP.NET 使用三重数据加密标准 (3DES) 算法，来处理视图状态数据。</span><span class="sxs-lookup"><span data-stu-id="7cd96-189">You need to specify that ASP.NET use the Triple Data Encryption Standard (3DES) algorithm to process view state data.</span></span> <span data-ttu-id="7cd96-190">对于响应组应用程序, 此要求适用于响应组配置工具和代理登录和注销控制台。</span><span class="sxs-lookup"><span data-stu-id="7cd96-190">For the Response Group application, this requirement applies to the Response Group Configuration Tool and the agent sign-in and sign-out console.</span></span> <span data-ttu-id="7cd96-191">有关此要求的详细信息, 请参阅 Microsoft 知识库文章 911722, 当你访问在从 ASP.NET 1.1 升级到 ASP.NET 2.0 后启用了 ViewState 的 ASP.NET 网页时, 你可能会收到错误消息[http://go.microsoft.com/fwlink/p/?linkId=196183](http://go.microsoft.com/fwlink/p/?linkid=196183)。</span><span class="sxs-lookup"><span data-stu-id="7cd96-191">For details about this requirement, see Microsoft Knowledge Base article 911722, "You may receive an error message when you access ASP.NET webpages that have ViewState enabled after you upgrade from ASP.NET 1.1 to ASP.NET 2.0," at [http://go.microsoft.com/fwlink/p/?linkId=196183](http://go.microsoft.com/fwlink/p/?linkid=196183).</span></span>

<span data-ttu-id="7cd96-192">若要修改 Web.config 文件，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7cd96-192">To modify the Web.config file, do the following:</span></span>

1.  <span data-ttu-id="7cd96-193">在文本编辑器（如记事本）中，打开应用程序级别 Web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="7cd96-193">In a text editor such as Notepad, open the application-level Web.config file.</span></span>

2.  <span data-ttu-id="7cd96-194">在 web.config 文件中, 找到相应的`<system.web>`部分。</span><span class="sxs-lookup"><span data-stu-id="7cd96-194">In the Web.config file, locate the `<system.web>` section.</span></span>

3.  <span data-ttu-id="7cd96-195">将以下`<machineKey>`部分添加到 "" `<system.web>`部分中:</span><span class="sxs-lookup"><span data-stu-id="7cd96-195">Add the following `<machineKey>` section to in the `<system.web>` section:</span></span>
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  <span data-ttu-id="7cd96-196">保存 Web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="7cd96-196">Save the Web.config file.</span></span>

5.  <span data-ttu-id="7cd96-197">通过在命令提示符处运行以下命令, 重启 Internet 信息服务 (IIS) 服务:</span><span class="sxs-lookup"><span data-stu-id="7cd96-197">Restart the Internet Information Services (IIS) service by running the following command at a command prompt:</span></span>
    
        iisreset

</div>

<div>

## <a name="supporting-yi-meng-and-zang-characters"></a><span data-ttu-id="7cd96-198">支持 Yi、Meng 和 Zang 字符</span><span class="sxs-lookup"><span data-stu-id="7cd96-198">Supporting Yi, Meng, and Zang Characters</span></span>

<span data-ttu-id="7cd96-199">仅当您的组织需要支持 Yi、Meng 或 Zang 字符时，本节才适用。</span><span class="sxs-lookup"><span data-stu-id="7cd96-199">This section applies to you only if your organization needs to support Yi, Meng, or Zang characters.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7cd96-200">有关 Yi、Meng 和 Zang 字符的内容以及它们对部署很重要的原因的信息, 请参阅 GB18030 字符集<A href="http://go.microsoft.com/fwlink/p/?linkid=240223">http://go.microsoft.com/fwlink/p/?linkId=240223</A>的相关信息。</span><span class="sxs-lookup"><span data-stu-id="7cd96-200">For information on what the Yi, Meng, and Zang characters are and why they may be important to your deployment, see the information on the GB18030 character sets <A href="http://go.microsoft.com/fwlink/p/?linkid=240223">http://go.microsoft.com/fwlink/p/?linkId=240223</A>.</span></span>



</div>

<span data-ttu-id="7cd96-p106">要支持 Yi、Meng 或 Zang 字符，需要修改 Rgsconfig 数据库的排序规则。在每个 Rgsconfig 数据库的下列各表中更改“Name”\*\*\*\* 列的排序规则：</span><span class="sxs-lookup"><span data-stu-id="7cd96-p106">To support Yi, Meng, or Zang characters, you need to modify the collation for the Rgsconfig database. Change the collation of the **Name** column in the following tables in each Rgsconfig database:</span></span>

  - <span data-ttu-id="7cd96-203">dbo.AgentGroups</span><span class="sxs-lookup"><span data-stu-id="7cd96-203">dbo.AgentGroups</span></span>

  - <span data-ttu-id="7cd96-204">dbo.BusinessHours</span><span class="sxs-lookup"><span data-stu-id="7cd96-204">dbo.BusinessHours</span></span>

  - <span data-ttu-id="7cd96-205">dbo.HolidaySets</span><span class="sxs-lookup"><span data-stu-id="7cd96-205">dbo.HolidaySets</span></span>

  - <span data-ttu-id="7cd96-206">dbo.Queues</span><span class="sxs-lookup"><span data-stu-id="7cd96-206">dbo.Queues</span></span>

  - <span data-ttu-id="7cd96-207">dbo.Workflows</span><span class="sxs-lookup"><span data-stu-id="7cd96-207">dbo.Workflows</span></span>

<span data-ttu-id="7cd96-208">对于 SQL Server 2008 R2 和 SQL Server 2012, 请使用拉丁文\_常规\_100 (区分重音) 排序规则。</span><span class="sxs-lookup"><span data-stu-id="7cd96-208">For SQL Server 2008 R2 and SQL Server 2012, use the Latin\_General\_100 (Accent Sensitive) collation.</span></span> <span data-ttu-id="7cd96-209">如果使用此排序规则，则所有对象名称不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="7cd96-209">If you use this collation, all object names are not case-sensitive.</span></span>

<span data-ttu-id="7cd96-210">可以使用 Microsoft SQL Server Management Studio 来更改排序规则。</span><span class="sxs-lookup"><span data-stu-id="7cd96-210">You can change the collation by using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="7cd96-211">有关使用此工具的详细信息, 请参阅 "使用 SQL Server Management Studio [http://go.microsoft.com/fwlink/p/?linkId=196184](http://go.microsoft.com/fwlink/p/?linkid=196184)"。</span><span class="sxs-lookup"><span data-stu-id="7cd96-211">For details about using this tool, see "Using SQL Server Management Studio" at [http://go.microsoft.com/fwlink/p/?linkId=196184](http://go.microsoft.com/fwlink/p/?linkid=196184).</span></span> <span data-ttu-id="7cd96-212">执行下列步骤可更改排序规则：</span><span class="sxs-lookup"><span data-stu-id="7cd96-212">Follow these steps to change the collation:</span></span>

1.  <span data-ttu-id="7cd96-213">确保 SQL Server Management Studio 配置为允许要求重新创建表的更改。</span><span class="sxs-lookup"><span data-stu-id="7cd96-213">Be sure that SQL Server Management Studio is configured to allow changes that require tables to be recreated.</span></span> <span data-ttu-id="7cd96-214">有关详细信息, 请参阅 "保存 (不允许)" 对话框[http://go.microsoft.com/fwlink/p/?linkId=196186](http://go.microsoft.com/fwlink/p/?linkid=196186)。</span><span class="sxs-lookup"><span data-stu-id="7cd96-214">For details, see "Save (Not Permitted) Dialog Box" at [http://go.microsoft.com/fwlink/p/?linkId=196186](http://go.microsoft.com/fwlink/p/?linkid=196186).</span></span> <span data-ttu-id="7cd96-215">有关设置列排序规则的详细信息, 请参阅 "如何: 设置列排序规则 (可视化数据库工具) [http://go.microsoft.com/fwlink/p/?linkId=196185](http://go.microsoft.com/fwlink/p/?linkid=196185)"。</span><span class="sxs-lookup"><span data-stu-id="7cd96-215">For details about setting a column collation, see "How to: Set Column Collation (Visual Database Tools)" at [http://go.microsoft.com/fwlink/p/?linkId=196185](http://go.microsoft.com/fwlink/p/?linkid=196185).</span></span>

2.  <span data-ttu-id="7cd96-216">使用 Microsoft SQL Server Management Studio 连接到 Rgsconfig 数据库。</span><span class="sxs-lookup"><span data-stu-id="7cd96-216">Using Microsoft SQL Server Management Studio, connect to the Rgsconfig database.</span></span>

3.  <span data-ttu-id="7cd96-217">在 Rgsconfig 数据库中查找要更改的表，右键单击该表，然后单击“设计”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7cd96-217">Find the table you want to change in the Rgsconfig database, right-click the table, and click **Design**.</span></span>

4.  <span data-ttu-id="7cd96-218">更改“名称”列\*\*\*\* 的排序规则并保存该表。</span><span class="sxs-lookup"><span data-stu-id="7cd96-218">Change the collation of the **Name** column and save the table.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

