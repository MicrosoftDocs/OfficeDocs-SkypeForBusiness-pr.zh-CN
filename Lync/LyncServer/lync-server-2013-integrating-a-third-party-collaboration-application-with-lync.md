---
title: 将第三方协作应用程序与 Lync 集成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Integrating a third-party collaboration application with Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398068(v=OCS.15)
ms:contentKeyID: 48183224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0b56fabbc1bd341e3ba2c5fe535d147c09335b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a><span data-ttu-id="749b0-102">将第三方协作应用程序与 Lync Server 2013 集成</span><span class="sxs-lookup"><span data-stu-id="749b0-102">Integrating a third-party collaboration application with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="749b0-103">_**主题上次修改时间:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="749b0-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="749b0-104">你可以通过向注册表添加有关应用程序的信息, 将 Lync 2013 与任何第三方联机协作应用程序集成。</span><span class="sxs-lookup"><span data-stu-id="749b0-104">You can integrate Lync 2013 with any third-party online collaboration application by adding information about the application to the registry.</span></span> <span data-ttu-id="749b0-105">您可以使用 Lync 2013 启动在内部服务器、基于 Internet 的服务或两者之间托管的数据会议会话。</span><span class="sxs-lookup"><span data-stu-id="749b0-105">You can use Lync 2013 to start data conferencing sessions hosted on an in-house server, an Internet-based service, or both.</span></span> <span data-ttu-id="749b0-106">可以从 "联系人" 列表或从现有即时消息、语音或视频会话启动协作或数据会议会话。</span><span class="sxs-lookup"><span data-stu-id="749b0-106">The collaboration or data conferencing session can be started from the Contacts list or from an existing instant messaging, voice, or video session.</span></span> <span data-ttu-id="749b0-107">Lync 2013 仅用作启动应用程序的工具。</span><span class="sxs-lookup"><span data-stu-id="749b0-107">Lync 2013 acts only as the vehicle for starting the application.</span></span> <span data-ttu-id="749b0-108">联机协作会话开始后, 任何现有 Lync 2013 对话都将保持活动状态。</span><span class="sxs-lookup"><span data-stu-id="749b0-108">Any existing Lync 2013 conversations remain active after the online collaboration session has begun.</span></span>

<span data-ttu-id="749b0-109">以下各部分介绍了如何将 Lync 2013 与基于 Internet 和基于服务器的协作应用程序集成。</span><span class="sxs-lookup"><span data-stu-id="749b0-109">The following sections describe how to integrate Lync 2013 with Internet-based and server-based collaboration applications.</span></span>

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="749b0-110">将基于 Internet 的协作应用程序集成到 Lync 2013</span><span class="sxs-lookup"><span data-stu-id="749b0-110">Integrating an Internet-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="749b0-111">通常情况下, 集成第三方协作应用程序涉及的步骤如下所示:</span><span class="sxs-lookup"><span data-stu-id="749b0-111">Generally, the steps involved in integrating a third-party collaboration application are as follows:</span></span>

1.  <span data-ttu-id="749b0-112">有关应用程序的信息将添加到注册表中。</span><span class="sxs-lookup"><span data-stu-id="749b0-112">Information about the application is added to the registry.</span></span>

2.  <span data-ttu-id="749b0-113">组织者登录 Lync 2013 并选择联系人进行数据共享和协作。</span><span class="sxs-lookup"><span data-stu-id="749b0-113">The organizer signs in to Lync 2013 and selects contacts for data sharing and collaboration.</span></span> <span data-ttu-id="749b0-114">或者, 组织者可能已经在对话中, 并且决定添加数据会议。</span><span class="sxs-lookup"><span data-stu-id="749b0-114">Or, the organizer may already be in a conversation and decide to add data conferencing.</span></span>

3.  <span data-ttu-id="749b0-115">Lync 2013 读取注册表, 启动协作应用程序, 然后将自定义 SIP 消息 (appINVITE) 发送给所选参与者。</span><span class="sxs-lookup"><span data-stu-id="749b0-115">Lync 2013 reads the registry, starts the collaboration application, and then sends a custom SIP message—an appINVITE—to the selected participants.</span></span>

4.  <span data-ttu-id="749b0-116">参与者接受邀请, 并在每个人的计算机上启动协作应用程序。</span><span class="sxs-lookup"><span data-stu-id="749b0-116">Participants accept the invitation, and the collaboration application is started on each person’s computer.</span></span> <span data-ttu-id="749b0-117">Lync 2013 使用注册表确定要使用的协作应用程序, 然后使用 appINVITE 消息中包含的参数启动该应用程序。</span><span class="sxs-lookup"><span data-stu-id="749b0-117">Lync 2013 uses the registry to determine which collaboration application to use, and then starts that application by using the parameters included in the appINVITE message.</span></span>

<span data-ttu-id="749b0-118">下表介绍了将基于 Internet 的协作应用程序与 Lync 2013 集成所需的注册表项。</span><span class="sxs-lookup"><span data-stu-id="749b0-118">The following table describes the registry entries required to integrate an Internet-based collaboration application with Lync 2013.</span></span> <span data-ttu-id="749b0-119">这些条目放置在注册表中的以下位置:</span><span class="sxs-lookup"><span data-stu-id="749b0-119">These entries are placed in the registry in the following location:</span></span>

  - <span data-ttu-id="749b0-120">HKEY\_LOCAL\_MACHINE\\软件\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\参数</span><span class="sxs-lookup"><span data-stu-id="749b0-120">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="749b0-121">基于 Internet 的协作应用程序的注册表项</span><span class="sxs-lookup"><span data-stu-id="749b0-121">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="749b0-122">名称</span><span class="sxs-lookup"><span data-stu-id="749b0-122">Name</span></span></th>
<th><span data-ttu-id="749b0-123">类型</span><span class="sxs-lookup"><span data-stu-id="749b0-123">Type</span></span></th>
<th><span data-ttu-id="749b0-124">数据</span><span class="sxs-lookup"><span data-stu-id="749b0-124">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="749b0-125">名称</span><span class="sxs-lookup"><span data-stu-id="749b0-125">Name</span></span></p></td>
<td><p><span data-ttu-id="749b0-126">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="749b0-126">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="749b0-127">Lync 2013 菜单的应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="749b0-127">The application name for Lync 2013 menus.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="749b0-128">SmallIcon</span><span class="sxs-lookup"><span data-stu-id="749b0-128">SmallIcon</span></span></p></td>
<td><p><span data-ttu-id="749b0-129">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="749b0-129">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="749b0-130">指向16像素 x 16 像素图标、BMP 或 PNG 的路径。</span><span class="sxs-lookup"><span data-stu-id="749b0-130">Path to 16-pixel x 16-pixel icon, BMP or PNG.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="749b0-131">路径</span><span class="sxs-lookup"><span data-stu-id="749b0-131">Path</span></span></p></td>
<td><p><span data-ttu-id="749b0-132">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="749b0-132">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="749b0-133">用于启动联机协作应用程序的参与者路径。</span><span class="sxs-lookup"><span data-stu-id="749b0-133">Participant path for starting the online collaboration application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="749b0-134">OriginatorPath</span><span class="sxs-lookup"><span data-stu-id="749b0-134">OriginatorPath</span></span></p></td>
<td><p><span data-ttu-id="749b0-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="749b0-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="749b0-136">用于启动联机协作应用程序的组织者路径。</span><span class="sxs-lookup"><span data-stu-id="749b0-136">Organizer path for starting the online collaboration application.</span></span> <span data-ttu-id="749b0-137">此路径可以包含 "参数" 子项中定义的一个或多个自定义参数。</span><span class="sxs-lookup"><span data-stu-id="749b0-137">This path can contain one or more custom parameters as defined in the Parameters subkey.</span></span> <span data-ttu-id="749b0-138">例如,<code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span><span class="sxs-lookup"><span data-stu-id="749b0-138">For example, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="749b0-139">SessionType</span><span class="sxs-lookup"><span data-stu-id="749b0-139">SessionType</span></span></p></td>
<td><p><span data-ttu-id="749b0-140">长</span><span class="sxs-lookup"><span data-stu-id="749b0-140">DWORD</span></span></p></td>
<td><p><span data-ttu-id="749b0-141">0 = 本地会话。</span><span class="sxs-lookup"><span data-stu-id="749b0-141">0 = Local session.</span></span> <span data-ttu-id="749b0-142">在本地计算机上启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="749b0-142">The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="749b0-143">1 = 两方会话 (默认值)。</span><span class="sxs-lookup"><span data-stu-id="749b0-143">1 = Two-party session (default).</span></span> <span data-ttu-id="749b0-144">Lync 2013 在本地启动应用程序, 然后将系统通知发送给另一个用户。</span><span class="sxs-lookup"><span data-stu-id="749b0-144">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="749b0-145">其他用户单击通知并在其计算机上启动指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="749b0-145">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="749b0-146">2 = 多方会话。</span><span class="sxs-lookup"><span data-stu-id="749b0-146">2 = Multiparty session.</span></span> <span data-ttu-id="749b0-147">Lync 2013 在本地启动应用程序, 然后向其他用户发送系统通知, 提示用户在其自己的计算机上启动指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="749b0-147">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their own computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="749b0-148">ExensibleMenu</span><span class="sxs-lookup"><span data-stu-id="749b0-148">ExensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="749b0-149">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="749b0-149">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="749b0-150">将显示此命令的菜单的列表, 用分号分隔。</span><span class="sxs-lookup"><span data-stu-id="749b0-150">A list of the menus where this command will appear, separated by semi-colons.</span></span> <span data-ttu-id="749b0-151">可能的值：</span><span class="sxs-lookup"><span data-stu-id="749b0-151">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="749b0-152">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="749b0-152">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="749b0-153">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="749b0-153">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="749b0-154">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="749b0-154">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="749b0-155">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="749b0-155">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="749b0-156">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="749b0-156">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="749b0-157">如果未定义 ExtensibleMenu, 则使用 MainWindowRightClick 和 ConversationWindowActions 的默认值。</span><span class="sxs-lookup"><span data-stu-id="749b0-157">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="749b0-158">下表描述了参数的注册表项。</span><span class="sxs-lookup"><span data-stu-id="749b0-158">The following table describes the registry entries for parameters.</span></span> <span data-ttu-id="749b0-159">这些条目\_位于 HKEY 当前\_用户\\软件\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\应用\\参数中。</span><span class="sxs-lookup"><span data-stu-id="749b0-159">These entries are place at HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters.</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="749b0-160">基于 Internet 的协作应用程序的注册表项</span><span class="sxs-lookup"><span data-stu-id="749b0-160">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="749b0-161">名称</span><span class="sxs-lookup"><span data-stu-id="749b0-161">Name</span></span></th>
<th><span data-ttu-id="749b0-162">类型</span><span class="sxs-lookup"><span data-stu-id="749b0-162">Type</span></span></th>
<th><span data-ttu-id="749b0-163">数据</span><span class="sxs-lookup"><span data-stu-id="749b0-163">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="749b0-164">Param1</span><span class="sxs-lookup"><span data-stu-id="749b0-164">Param1</span></span></p></td>
<td><p><span data-ttu-id="749b0-165">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="749b0-165">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="749b0-166">在标记化格式 (<code>%Parm1%</code>) 中使用, 用于将特定于用户的值添加到 OriginatorPath 注册表项。</span><span class="sxs-lookup"><span data-stu-id="749b0-166">Used in tokenized format (<code>%Parm1%</code>) to add user-specific values to the OriginatorPath registry key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="749b0-167">Param2</span><span class="sxs-lookup"><span data-stu-id="749b0-167">Param2</span></span></p></td>
<td><p><span data-ttu-id="749b0-168">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="749b0-168">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="749b0-169">请参阅 Param1。</span><span class="sxs-lookup"><span data-stu-id="749b0-169">See Param1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="749b0-170">Param3</span><span class="sxs-lookup"><span data-stu-id="749b0-170">Param3</span></span></p></td>
<td><p><span data-ttu-id="749b0-171">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="749b0-171">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="749b0-172">请参阅 Param1。</span><span class="sxs-lookup"><span data-stu-id="749b0-172">See Param1.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="749b0-173">以下示例注册表设置将 ADatum 协作客户端与 Lync 2013 集成:</span><span class="sxs-lookup"><span data-stu-id="749b0-173">The following example registry settings integrate ADatum Collaboration Client with Lync 2013:</span></span>

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Path"="https://meetingservice.adatum.com/cc/%param1%/meet/%param2%"
    "OriginatorPath"="https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&role=present&pw=%param3%"
    "SessionType"=dword:00000002
    "ApplicationType"=dword:00000001
    "LiveServerIntegration"=dword:00000000
    "Name"="ADatum Online Collaboration Service"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"
    
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Param1"="meetserv"
    "Param2"="admin"
    "Param3"="abcdefg123"

</div>

<div>

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="749b0-174">将基于服务器的协作应用程序与 Lync 2013 集成</span><span class="sxs-lookup"><span data-stu-id="749b0-174">Integrating a Server-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="749b0-175">用于从 Lync 2013 中添加用于启动基于服务器的协作应用程序的命令的设置与上一节中所述, 将基于 Internet 的协作应用程序集成到 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="749b0-175">The settings to add commands for starting a server-based collaboration application from within Lync 2013 are similar to those described in the previous section, Integrating an Internet-Based Collaboration Application with Lync 2013.</span></span> <span data-ttu-id="749b0-176">但是, OriginatorPath 不是必需的, 并且某些值已更改。</span><span class="sxs-lookup"><span data-stu-id="749b0-176">However, the OriginatorPath is not required, and some values are changed.</span></span> <span data-ttu-id="749b0-177">注册表项放置在以下位置:</span><span class="sxs-lookup"><span data-stu-id="749b0-177">Registry entries are placed in the following location:</span></span>

  - <span data-ttu-id="749b0-178">HKEY\_LOCAL\_MACHINE\\软件\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\参数</span><span class="sxs-lookup"><span data-stu-id="749b0-178">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-a-server-based-collaboration-application"></a><span data-ttu-id="749b0-179">基于服务器的协作应用程序的注册表项</span><span class="sxs-lookup"><span data-stu-id="749b0-179">Registry Entries for a Server-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="749b0-180">名称</span><span class="sxs-lookup"><span data-stu-id="749b0-180">Name</span></span></th>
<th><span data-ttu-id="749b0-181">类型</span><span class="sxs-lookup"><span data-stu-id="749b0-181">Type</span></span></th>
<th><span data-ttu-id="749b0-182">数据</span><span class="sxs-lookup"><span data-stu-id="749b0-182">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="749b0-183">名称</span><span class="sxs-lookup"><span data-stu-id="749b0-183">Name</span></span></p></td>
<td><p><span data-ttu-id="749b0-184">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="749b0-184">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="749b0-185">显示在菜单上的应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="749b0-185">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="749b0-186">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="749b0-186">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="749b0-187">长</span><span class="sxs-lookup"><span data-stu-id="749b0-187">DWORD</span></span></p></td>
<td><p><span data-ttu-id="749b0-188">值 = 1。</span><span class="sxs-lookup"><span data-stu-id="749b0-188">Value = 1.</span></span> <span data-ttu-id="749b0-189">将应用程序类型设置为 "协议"。</span><span class="sxs-lookup"><span data-stu-id="749b0-189">Sets the application type to protocol.</span></span> <span data-ttu-id="749b0-190">在此情况下, 其他可能的值不适用。</span><span class="sxs-lookup"><span data-stu-id="749b0-190">The other possible values do not apply in this case.</span></span> <span data-ttu-id="749b0-191">如果不存在, 则将 ApplicationType 设置为 0 (可执行文件)。</span><span class="sxs-lookup"><span data-stu-id="749b0-191">If not present, ApplicationType is set to 0 (executable).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="749b0-192">路径</span><span class="sxs-lookup"><span data-stu-id="749b0-192">Path</span></span></p></td>
<td><p><span data-ttu-id="749b0-193">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="749b0-193">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="749b0-194">用于启动协作应用程序的协议。</span><span class="sxs-lookup"><span data-stu-id="749b0-194">Protocol used to start the collaboration application.</span></span> <span data-ttu-id="749b0-195">对于 Live Meeting 2007, Path 的值设置为<code>meet:%conf-uri%</code>。</span><span class="sxs-lookup"><span data-stu-id="749b0-195">For Live Meeting 2007, the value of Path is set to <code>meet:%conf-uri%</code>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="749b0-196">SessionType</span><span class="sxs-lookup"><span data-stu-id="749b0-196">SessionType</span></span></p></td>
<td><p><span data-ttu-id="749b0-197">长</span><span class="sxs-lookup"><span data-stu-id="749b0-197">DWORD</span></span></p></td>
<td><p><span data-ttu-id="749b0-198">0 = 本地会话。</span><span class="sxs-lookup"><span data-stu-id="749b0-198">0 = Local session.</span></span> <span data-ttu-id="749b0-199">在本地计算机上启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="749b0-199">The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="749b0-200">1 = 两方会话 (默认值)。</span><span class="sxs-lookup"><span data-stu-id="749b0-200">1 = Two-party session (default).</span></span> <span data-ttu-id="749b0-201">Lync 2013 在本地启动应用程序, 然后将系统通知发送给另一个用户。</span><span class="sxs-lookup"><span data-stu-id="749b0-201">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="749b0-202">其他用户单击通知并在其计算机上启动指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="749b0-202">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="749b0-203">2 = 多方会话。</span><span class="sxs-lookup"><span data-stu-id="749b0-203">2 = Multiparty session.</span></span> <span data-ttu-id="749b0-204">Lync 2013 在本地启动应用程序, 然后向其他用户发送系统通知, 提示用户在其计算机上启动指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="749b0-204">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="749b0-205">MCUType</span><span class="sxs-lookup"><span data-stu-id="749b0-205">MCUType</span></span></p></td>
<td><p><span data-ttu-id="749b0-206">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="749b0-206">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="749b0-207">DATA = 服务器的类型。</span><span class="sxs-lookup"><span data-stu-id="749b0-207">DATA = The type of server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="749b0-208">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="749b0-208">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="749b0-209">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="749b0-209">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="749b0-210">将显示此命令的菜单的列表, 用分号分隔。</span><span class="sxs-lookup"><span data-stu-id="749b0-210">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="749b0-211">可能的值：</span><span class="sxs-lookup"><span data-stu-id="749b0-211">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="749b0-212">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="749b0-212">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="749b0-213">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="749b0-213">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="749b0-214">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="749b0-214">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="749b0-215">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="749b0-215">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="749b0-216">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="749b0-216">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="749b0-217">如果未定义 ExtensibleMenu, 则使用 MainWindowRightClick 和 ConversationWindowActions 的默认值。</span><span class="sxs-lookup"><span data-stu-id="749b0-217">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="749b0-218">以下示例添加了从 Lync 2013 中启动 ADatum 协作客户端的命令:</span><span class="sxs-lookup"><span data-stu-id="749b0-218">The following example adds commands to start ADatum Collaboration Client from within Lync 2013:</span></span>

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{27877e66-615c-4582-ab88-0cb2ca05d951}]
    "Path"="meet:%conf-uri%"
    "SessionType"=dword:00000002
    "LiveServerIntegration"=dword:00000001
    "ApplicationType"=dword:00000001
    "Name"="ADatum Collaboration Client"
    "MCUType"="Data"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"

</div>

</div>

<span> </span>

</div>

</div>

</div>

