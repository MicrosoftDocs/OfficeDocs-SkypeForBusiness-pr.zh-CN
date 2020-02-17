---
title: Lync Server 2013： Lync 2013 的新增和更改设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New and changed settings for Lync 2013
ms:assetid: bb13789c-7eda-461c-a387-02ea8ca4dabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205204(v=OCS.15)
ms:contentKeyID: 48185241
ms.date: 12/08/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45282476beac35df7248c4ef6bd04c6642a0f1e2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-and-changed-settings-for-lync-2013"></a><span data-ttu-id="49ea1-102">Lync 2013 的新增和更改设置</span><span class="sxs-lookup"><span data-stu-id="49ea1-102">New and changed settings for Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49ea1-103">_**上次修改的主题：** 2014-12-05_</span><span class="sxs-lookup"><span data-stu-id="49ea1-103">_**Topic Last Modified:** 2014-12-05_</span></span>

<span data-ttu-id="49ea1-104">本主题讨论与直接与客户端管理相关的 Lync Server 命令行管理程序 cmdlet 的更改。</span><span class="sxs-lookup"><span data-stu-id="49ea1-104">This topic discusses changes to Lync Server Management Shell cmdlets that relate directly to client management.</span></span> <span data-ttu-id="49ea1-105">Lync Server 2013 引入了几个新参数，并为可以通过其他方式配置的功能 deprecates 参数。</span><span class="sxs-lookup"><span data-stu-id="49ea1-105">Lync Server 2013 introduces several new parameters, and deprecates parameters for features that can be configured through other means.</span></span>

<div>

## <a name="new-client-management-parameters"></a><span data-ttu-id="49ea1-106">新的客户端管理参数</span><span class="sxs-lookup"><span data-stu-id="49ea1-106">New Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="49ea1-107">New</span><span class="sxs-lookup"><span data-stu-id="49ea1-107">New</span></span></th>
<th><span data-ttu-id="49ea1-108">Lync Server 命令行管理程序 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="49ea1-108">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="49ea1-109">描述</span><span class="sxs-lookup"><span data-stu-id="49ea1-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="49ea1-110">TracingLevel</span><span class="sxs-lookup"><span data-stu-id="49ea1-110">TracingLevel</span></span></p></td>
<td><p><span data-ttu-id="49ea1-111">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="49ea1-111">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="49ea1-112">如果设置为 True，将在 Lync 中启用软件跟踪;如果设置为 False，软件跟踪将被禁用。</span><span class="sxs-lookup"><span data-stu-id="49ea1-112">When set to True, software tracing will be enabled in Lync; when set to False, software tracing will be disabled.</span></span> <span data-ttu-id="49ea1-113">软件跟踪涉及对程序执行的所有操作（包括跟踪 API 调用）的详细记录进行维护。</span><span class="sxs-lookup"><span data-stu-id="49ea1-113">Software tracing involves keeping a detailed record of everything that a program does (including tracking API calls).</span></span> <span data-ttu-id="49ea1-114">跟踪主要适用于开发人员和应用程序支持人员。此设置等效于通信服务器 2007 R2 组策略设置&quot;启用对 Communicator 的跟踪。&quot;设置如下所示：</span><span class="sxs-lookup"><span data-stu-id="49ea1-114">Tracing is mostly useful to developers and to application support personnel.This setting is equivalent to the Communications Server 2007 R2 Group Policy setting &quot;Turn on tracing for Communicator.&quot; The settings are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="49ea1-115">关闭 = 禁用跟踪，用户无法更改此设置。</span><span class="sxs-lookup"><span data-stu-id="49ea1-115">Off = Tracing is disabled and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="49ea1-116">简略 = 执行最低限度的跟踪，用户无法更改此设置。</span><span class="sxs-lookup"><span data-stu-id="49ea1-116">Light = Minimal tracing is performed, and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="49ea1-117">开启 = 执行详细跟踪，用户无法更改此设置。</span><span class="sxs-lookup"><span data-stu-id="49ea1-117">On = Verbose tracing is performed, and the user cannot change this setting.</span></span></p></li>
</ul>
<p><span data-ttu-id="49ea1-p103">默认情况下，TracingLevel 会设置为空值。这意味着将执行最低限度的跟踪，但是用户可以启用或禁用此最低限度的跟踪。</span><span class="sxs-lookup"><span data-stu-id="49ea1-p103">By default TracingLevel is set to a null value. That means that minimal tracing is performed, but the user can enable or disable this minimal tracing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49ea1-120">EnableMediaRedirection</span><span class="sxs-lookup"><span data-stu-id="49ea1-120">EnableMediaRedirection</span></span></p></td>
<td><p><span data-ttu-id="49ea1-121">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="49ea1-121">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="49ea1-p104">设置为 True ($True) 时，允许音频流和视频流与其他网络流量分隔开。进而，允许客户端设备在本地对视频和音频执行编码和解码。与类似的技术（如设备远程处理或编解码器压缩）相比，媒体重定向通常带来较低的带宽使用率、较高的服务器可伸缩性，以及更佳的用户体验。</span><span class="sxs-lookup"><span data-stu-id="49ea1-p104">When set to True ($True) allows audio and video streams to be separated from other network traffic, In turn, this allows client devices to do encoding and decoding of audio and video locally. Media redirection typically results in lower bandwidth usage, higher server scalability, and a more-optimal user experience compared to similar techniques such as device remoting or codec compression.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49ea1-124">AllowLargeMeetings</span><span class="sxs-lookup"><span data-stu-id="49ea1-124">AllowLargeMeetings</span></span></p></td>
<td><p><span data-ttu-id="49ea1-125">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="49ea1-125">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="49ea1-126">如果设置为 True，则所有 Lync 会议将被&quot;视为大型会议。&quot;在大型会议中，对发送给参与者的通知数以及默认情况下传输的会议名单的大小进行了限制。</span><span class="sxs-lookup"><span data-stu-id="49ea1-126">When set to True, all Lync Meetings are treated as &quot;large meetings.&quot; With a large meeting, restrictions are placed on the number of notifications that are sent to participants, in addition to the size of the meeting roster that is transmitted by default.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49ea1-127">DisablePowerPointAnnotations</span><span class="sxs-lookup"><span data-stu-id="49ea1-127">DisablePowerPointAnnotations</span></span></p></td>
<td><p><span data-ttu-id="49ea1-128">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="49ea1-128">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="49ea1-p105">设置为 True ($True) 时，用户无法向会议中使用的 PowerPoint 幻灯片添加注释。但是（根据 AllowAnnotations 属性的值），用户仍能访问其他白板功能。默认值为 False，表示允许 PowerPoint 注释。</span><span class="sxs-lookup"><span data-stu-id="49ea1-p105">When set to True ($True) users won’t be able to add annotations to PowerPoint slides used in a conference. However (depending on the value of the AllowAnnotations property), users will still have access to other whiteboarding features. The default value is False, meaning that PowerPoint annotations are allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49ea1-132">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="49ea1-132">AllowSharedNotes</span></span></p></td>
<td><p><span data-ttu-id="49ea1-133">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="49ea1-133">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="49ea1-134">设置为 True（默认值）时，将使用诸如会议参与者之类的信息以及有关在会议过程中共享的内容的详细信息，自动更新链接到会议的任何打开的 OneNote 笔记本。</span><span class="sxs-lookup"><span data-stu-id="49ea1-134">When set to True (the default value) any open OneNote notebooks linked to the conference will automatically be updated with information such as conference participants and details about content shared during the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49ea1-135">EnableInviteCustomization</span><span class="sxs-lookup"><span data-stu-id="49ea1-135">EnableInviteCustomization</span></span></p></td>
<td><p><span data-ttu-id="49ea1-136">Get-csmeetingconfiguration</span><span class="sxs-lookup"><span data-stu-id="49ea1-136">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="49ea1-137">与其他新 Get-csmeetingconfiguration 参数一起使用，自定义由 Lync 2013 的联机会议外接程序生成的会议邀请。</span><span class="sxs-lookup"><span data-stu-id="49ea1-137">Used along with the other new CsMeetingConfiguration parameters to customize the meeting invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49ea1-138">LogoURL</span><span class="sxs-lookup"><span data-stu-id="49ea1-138">LogoURL</span></span></p></td>
<td><p><span data-ttu-id="49ea1-139">Get-csmeetingconfiguration</span><span class="sxs-lookup"><span data-stu-id="49ea1-139">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="49ea1-140">将组织的徽标添加到由 Lync 2013 的联机会议外接程序生成的所有邀请中。</span><span class="sxs-lookup"><span data-stu-id="49ea1-140">Adds your organization’s logo to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="49ea1-141">可以指定 GIF 或 JPG 图像的 URL。</span><span class="sxs-lookup"><span data-stu-id="49ea1-141">You specify the URL of a GIF or JPG image.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49ea1-142">HelpURL</span><span class="sxs-lookup"><span data-stu-id="49ea1-142">HelpURL</span></span></p></td>
<td><p><span data-ttu-id="49ea1-143">Get-csmeetingconfiguration</span><span class="sxs-lookup"><span data-stu-id="49ea1-143">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="49ea1-144">将组织的帮助或支持 URL 添加到由 Lync 2013 的联机会议外接程序生成的所有邀请中。</span><span class="sxs-lookup"><span data-stu-id="49ea1-144">Adds your organization’s help or support URL to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49ea1-145">LegalURL</span><span class="sxs-lookup"><span data-stu-id="49ea1-145">LegalURL</span></span></p></td>
<td><p><span data-ttu-id="49ea1-146">Get-csmeetingconfiguration</span><span class="sxs-lookup"><span data-stu-id="49ea1-146">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="49ea1-147">将法律文本或免责声明文本添加到由 Lync 2013 的联机会议外接程序生成的所有邀请中。</span><span class="sxs-lookup"><span data-stu-id="49ea1-147">Adds legal text or disclaimer text to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="49ea1-148">可以指定文本位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="49ea1-148">You specify the URL for the location of the text.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49ea1-149">CustomFooterText</span><span class="sxs-lookup"><span data-stu-id="49ea1-149">CustomFooterText</span></span></p></td>
<td><p><span data-ttu-id="49ea1-150">Get-csmeetingconfiguration</span><span class="sxs-lookup"><span data-stu-id="49ea1-150">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="49ea1-151">将自定义页脚添加到由 Lync 2013 的联机会议外接程序生成的所有邀请中。</span><span class="sxs-lookup"><span data-stu-id="49ea1-151">Adds a custom footer to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="49ea1-152">可以指定自定义页脚文本位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="49ea1-152">You specify the URL for the location of the custom footer text.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a><span data-ttu-id="49ea1-153">废弃的客户端管理参数</span><span class="sxs-lookup"><span data-stu-id="49ea1-153">Deprecated Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="49ea1-154">参数</span><span class="sxs-lookup"><span data-stu-id="49ea1-154">Parameter</span></span></th>
<th><span data-ttu-id="49ea1-155">Lync Server 命令行管理程序 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="49ea1-155">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="49ea1-156">描述</span><span class="sxs-lookup"><span data-stu-id="49ea1-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="49ea1-157">CustomizedHelpUrl</span><span class="sxs-lookup"><span data-stu-id="49ea1-157">CustomizedHelpUrl</span></span></p></td>
<td><p><span data-ttu-id="49ea1-158">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="49ea1-158">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="49ea1-159">此参数已弃用，可用于 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="49ea1-159">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="49ea1-160">在与 EnableEnterpriseCustomizedHelp 结合使用时，此参数使组织能够指定 URL，以便在用户单击 Lync 中的 "帮助" 菜单时，自定义 "帮助" 将会显示。</span><span class="sxs-lookup"><span data-stu-id="49ea1-160">When used in conjunction with EnableEnterpriseCustomizedHelp, this parameter enabled an organization to specify a URL so that when users clicked the Help menu in Lync, customized help would display.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49ea1-161">EnableEnterpriseCustomizedHelp</span><span class="sxs-lookup"><span data-stu-id="49ea1-161">EnableEnterpriseCustomizedHelp</span></span></p></td>
<td><p><span data-ttu-id="49ea1-162">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="49ea1-162">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="49ea1-163">此参数已弃用，可用于 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="49ea1-163">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="49ea1-164">在与 CustomizedHelpUrl 结合使用时，此参数启用组织以显示自定义帮助。</span><span class="sxs-lookup"><span data-stu-id="49ea1-164">When used in conjunction with CustomizedHelpUrl, this parameter enabled organizations to display customized help.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49ea1-165">EnableSQMData</span><span class="sxs-lookup"><span data-stu-id="49ea1-165">EnableSQMData</span></span></p></td>
<td><p><span data-ttu-id="49ea1-166">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="49ea1-166">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="49ea1-167">已在 Lync Server 2013 中删除 Set-csclientpolicy cmdlet 的 EnableSQMData 参数。</span><span class="sxs-lookup"><span data-stu-id="49ea1-167">The EnableSQMData parameter of the Set-CSClientPolicy cmdlet has been removed in Lync Server 2013.</span></span> <span data-ttu-id="49ea1-168">可以改为使用软件质量管理 (SQM) 数据的共享组策略设置，来确定 Lync 客户端“常规选项”页面中“客户体验改善”选项的用户界面：</span><span class="sxs-lookup"><span data-stu-id="49ea1-168">Instead, you can use the shared Group Policy setting for Software Quality Management (SQM) data to determine the user interface for the Customer Experience Improvement option in the Lync client General options page:</span></span></p>
<p><span data-ttu-id="49ea1-169">HKEY_CURRENT_USER \Software\Policies\Microsoft\Office\Common\QMEnable</span><span class="sxs-lookup"><span data-stu-id="49ea1-169">HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</span></span></p>
<p><span data-ttu-id="49ea1-170">值</span><span class="sxs-lookup"><span data-stu-id="49ea1-170">Values:</span></span></p>
<p><span data-ttu-id="49ea1-171">1 = 显示并选中复选框（用户可以清除该复选框）</span><span class="sxs-lookup"><span data-stu-id="49ea1-171">1 = Display and select the check box (the user can clear the check box)</span></span></p>
<p><span data-ttu-id="49ea1-172">0 = 关闭并禁用复选框（用户无法覆盖）</span><span class="sxs-lookup"><span data-stu-id="49ea1-172">0 = Turn off and disable the check box (user can't override)</span></span></p>
<p><span data-ttu-id="49ea1-173">Null = 该值由 Office 设置确定，并且会向用户显示该复选框，以按照他们的选择进行设置</span><span class="sxs-lookup"><span data-stu-id="49ea1-173">Null = The value is determined by Office setup, and the check box is displayed for users to set as they choose</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49ea1-174">AllowExchangeContactStore</span><span class="sxs-lookup"><span data-stu-id="49ea1-174">AllowExchangeContactStore</span></span></p></td>
<td><p><span data-ttu-id="49ea1-175">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="49ea1-175">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="49ea1-176">已删除此参数。</span><span class="sxs-lookup"><span data-stu-id="49ea1-176">This parameter has been removed.</span></span> <span data-ttu-id="49ea1-177">相反，当您部署 Lync Server 2013 并发布拓扑时，默认情况下会为所有用户启用统一联系人存储。</span><span class="sxs-lookup"><span data-stu-id="49ea1-177">Instead, when you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="49ea1-178">这意味着用户的所有联系人均保留在 Exchange 中并且在 Lync、Outlook 和 Outlook Web Access 中可用。</span><span class="sxs-lookup"><span data-stu-id="49ea1-178">This means that all a user’s contacts are kept in Exchange and are available in Lync, Outlook, and Outlook Web Access.</span></span> <span data-ttu-id="49ea1-179">您可以使用 Set-CsUserServicesPolicy cmdlet 来自定义哪些用户具有可用的统一联系人存储。</span><span class="sxs-lookup"><span data-stu-id="49ea1-179">You can use the Set-CsUserServicesPolicy cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="49ea1-180">可以全局、依站点、依租户或依个人或个人组为用户启用。</span><span class="sxs-lookup"><span data-stu-id="49ea1-180">You can enable users globally, by site, by tenant, or by individuals or groups of individuals.</span></span> <span data-ttu-id="49ea1-181">有关详细信息，请参阅<a href="lync-server-2013-enable-users-for-unified-contact-store.md">在 Lync Server 2013 中为统一联系人存储启用用户</a>。</span><span class="sxs-lookup"><span data-stu-id="49ea1-181">For details, see <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Enable users for unified contact store in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49ea1-182">MAPIPollInterval</span><span class="sxs-lookup"><span data-stu-id="49ea1-182">MAPIPollInterval</span></span></p></td>
<td><p><span data-ttu-id="49ea1-183">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="49ea1-183">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="49ea1-184">Lync 2013 不使用此参数。</span><span class="sxs-lookup"><span data-stu-id="49ea1-184">This parameter is not used by Lync 2013.</span></span> <span data-ttu-id="49ea1-185">在以前的版本中，此参数指定客户端从 Exchange 公用文件夹中检索 MAPI 数据的频率</span><span class="sxs-lookup"><span data-stu-id="49ea1-185">In previous releases, this parameter specified how often the client retrieved MAPI data from Exchange public folders</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49ea1-186">DisableICE</span><span class="sxs-lookup"><span data-stu-id="49ea1-186">DisableICE</span></span></p></td>
<td><p><span data-ttu-id="49ea1-187">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="49ea1-187">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="49ea1-188">在 Lync 2013 中已弃用此参数。</span><span class="sxs-lookup"><span data-stu-id="49ea1-188">This parameter was deprecated in Lync 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

