---
title: 将第三方协作应用程序与 Lync 集成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating a third-party collaboration application with Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398068(v=OCS.15)
ms:contentKeyID: 48183224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ae021735f5fec25cfaba625bd61460e9f58abb4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145411"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a><span data-ttu-id="243b8-102">将第三方协作应用程序与 Lync Server 2013 集成</span><span class="sxs-lookup"><span data-stu-id="243b8-102">Integrating a third-party collaboration application with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="243b8-103">_**上次修改的主题：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="243b8-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="243b8-104">您可以通过向注册表添加有关应用程序的信息，将 Lync 2013 与任何第三方在线协作应用程序集成。</span><span class="sxs-lookup"><span data-stu-id="243b8-104">You can integrate Lync 2013 with any third-party online collaboration application by adding information about the application to the registry.</span></span> <span data-ttu-id="243b8-105">您可以使用 Lync 2013 启动在内部服务器上托管的数据会议会话、基于 Internet 的服务或同时在这两者上启动。</span><span class="sxs-lookup"><span data-stu-id="243b8-105">You can use Lync 2013 to start data conferencing sessions hosted on an in-house server, an Internet-based service, or both.</span></span> <span data-ttu-id="243b8-106">可以从联系人列表或者从现有的即时消息、语音或视频会话中启动协作或数据会议会话。</span><span class="sxs-lookup"><span data-stu-id="243b8-106">The collaboration or data conferencing session can be started from the Contacts list or from an existing instant messaging, voice, or video session.</span></span> <span data-ttu-id="243b8-107">Lync 2013 仅用作启动应用程序的工具。</span><span class="sxs-lookup"><span data-stu-id="243b8-107">Lync 2013 acts only as the vehicle for starting the application.</span></span> <span data-ttu-id="243b8-108">联机协作会话开始后，任何现有的 Lync 2013 对话仍处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="243b8-108">Any existing Lync 2013 conversations remain active after the online collaboration session has begun.</span></span>

<span data-ttu-id="243b8-109">以下各节介绍如何将 Lync 2013 与基于 Internet 的协作应用程序和基于服务器的协作应用程序集成。</span><span class="sxs-lookup"><span data-stu-id="243b8-109">The following sections describe how to integrate Lync 2013 with Internet-based and server-based collaboration applications.</span></span>

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="243b8-110">将基于 Internet 的协作应用程序与 Lync 2013 集成</span><span class="sxs-lookup"><span data-stu-id="243b8-110">Integrating an Internet-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="243b8-111">一般而言，集成第三方协作应用程序的步骤如下：</span><span class="sxs-lookup"><span data-stu-id="243b8-111">Generally, the steps involved in integrating a third-party collaboration application are as follows:</span></span>

1.  <span data-ttu-id="243b8-112">将有关该应用程序的信息添加到注册表中。</span><span class="sxs-lookup"><span data-stu-id="243b8-112">Information about the application is added to the registry.</span></span>

2.  <span data-ttu-id="243b8-113">组织者登录到 Lync 2013 并选择联系人进行数据共享和协作。</span><span class="sxs-lookup"><span data-stu-id="243b8-113">The organizer signs in to Lync 2013 and selects contacts for data sharing and collaboration.</span></span> <span data-ttu-id="243b8-114">或者，组织者可能已经处于对话中，决定添加数据会议。</span><span class="sxs-lookup"><span data-stu-id="243b8-114">Or, the organizer may already be in a conversation and decide to add data conferencing.</span></span>

3.  <span data-ttu-id="243b8-115">Lync 2013 读取注册表，启动协作应用程序，然后向所选参与者发送自定义 SIP 消息（appINVITE）。</span><span class="sxs-lookup"><span data-stu-id="243b8-115">Lync 2013 reads the registry, starts the collaboration application, and then sends a custom SIP message—an appINVITE—to the selected participants.</span></span>

4.  <span data-ttu-id="243b8-116">参与者接受邀请，每个人的计算机上将启动协作应用程序。</span><span class="sxs-lookup"><span data-stu-id="243b8-116">Participants accept the invitation, and the collaboration application is started on each person’s computer.</span></span> <span data-ttu-id="243b8-117">Lync 2013 使用注册表确定要使用的协作应用程序，然后使用 appINVITE 邮件中包含的参数启动该应用程序。</span><span class="sxs-lookup"><span data-stu-id="243b8-117">Lync 2013 uses the registry to determine which collaboration application to use, and then starts that application by using the parameters included in the appINVITE message.</span></span>

<span data-ttu-id="243b8-118">下表介绍了将基于 Internet 的协作应用程序与 Lync 2013 集成所需的注册表项。</span><span class="sxs-lookup"><span data-stu-id="243b8-118">The following table describes the registry entries required to integrate an Internet-based collaboration application with Lync 2013.</span></span> <span data-ttu-id="243b8-119">这些项放置在注册表中的以下位置：</span><span class="sxs-lookup"><span data-stu-id="243b8-119">These entries are placed in the registry in the following location:</span></span>

  - <span data-ttu-id="243b8-120">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span><span class="sxs-lookup"><span data-stu-id="243b8-120">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="243b8-121">基于 Internet 的协作应用程序的注册表项</span><span class="sxs-lookup"><span data-stu-id="243b8-121">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="243b8-122">名称</span><span class="sxs-lookup"><span data-stu-id="243b8-122">Name</span></span></th>
<th><span data-ttu-id="243b8-123">类型</span><span class="sxs-lookup"><span data-stu-id="243b8-123">Type</span></span></th>
<th><span data-ttu-id="243b8-124">Data</span><span class="sxs-lookup"><span data-stu-id="243b8-124">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="243b8-125">名称</span><span class="sxs-lookup"><span data-stu-id="243b8-125">Name</span></span></p></td>
<td><p><span data-ttu-id="243b8-126">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="243b8-126">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="243b8-127">Lync 2013 菜单的应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="243b8-127">The application name for Lync 2013 menus.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="243b8-128">SmallIcon</span><span class="sxs-lookup"><span data-stu-id="243b8-128">SmallIcon</span></span></p></td>
<td><p><span data-ttu-id="243b8-129">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="243b8-129">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="243b8-130">16 像素 x 16 像素的图标（BMP 或 PNG 格式）的路径。</span><span class="sxs-lookup"><span data-stu-id="243b8-130">Path to 16-pixel x 16-pixel icon, BMP or PNG.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="243b8-131">Path</span><span class="sxs-lookup"><span data-stu-id="243b8-131">Path</span></span></p></td>
<td><p><span data-ttu-id="243b8-132">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="243b8-132">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="243b8-133">用于启动联机协作应用程序的参与者路径。</span><span class="sxs-lookup"><span data-stu-id="243b8-133">Participant path for starting the online collaboration application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="243b8-134">OriginatorPath</span><span class="sxs-lookup"><span data-stu-id="243b8-134">OriginatorPath</span></span></p></td>
<td><p><span data-ttu-id="243b8-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="243b8-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="243b8-136">用于启动联机协作应用程序的组织者路径。</span><span class="sxs-lookup"><span data-stu-id="243b8-136">Organizer path for starting the online collaboration application.</span></span> <span data-ttu-id="243b8-137">此路径可以包含如同 Parameters 子项中定义的一个或多个自定义参数。</span><span class="sxs-lookup"><span data-stu-id="243b8-137">This path can contain one or more custom parameters as defined in the Parameters subkey.</span></span> <span data-ttu-id="243b8-138">例如，<code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span><span class="sxs-lookup"><span data-stu-id="243b8-138">For example, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="243b8-139">SessionType</span><span class="sxs-lookup"><span data-stu-id="243b8-139">SessionType</span></span></p></td>
<td><p><span data-ttu-id="243b8-140">DWORD</span><span class="sxs-lookup"><span data-stu-id="243b8-140">DWORD</span></span></p></td>
<td><p><span data-ttu-id="243b8-p106">0 = 本地会话。应用程序在本地计算机上启动。</span><span class="sxs-lookup"><span data-stu-id="243b8-p106">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="243b8-143">1 = 两方会话（默认）。</span><span class="sxs-lookup"><span data-stu-id="243b8-143">1 = Two-party session (default).</span></span> <span data-ttu-id="243b8-144">Lync 2013 在本地启动应用程序，然后将系统通知发送给其他用户。</span><span class="sxs-lookup"><span data-stu-id="243b8-144">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="243b8-145">其他用户单击该通知，并在其计算机上启动指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="243b8-145">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="243b8-146">2 = 多方会话。</span><span class="sxs-lookup"><span data-stu-id="243b8-146">2 = Multiparty session.</span></span> <span data-ttu-id="243b8-147">Lync 2013 在本地启动应用程序，然后向其他用户发送系统通知，提示他们在自己的计算机上启动指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="243b8-147">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their own computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="243b8-148">ExensibleMenu</span><span class="sxs-lookup"><span data-stu-id="243b8-148">ExensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="243b8-149">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="243b8-149">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="243b8-p109">将显示此命令的菜单列表，用分号分隔。可能的值为：</span><span class="sxs-lookup"><span data-stu-id="243b8-p109">A list of the menus where this command will appear, separated by semi-colons. Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="243b8-152">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="243b8-152">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="243b8-153">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="243b8-153">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="243b8-154">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="243b8-154">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="243b8-155">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="243b8-155">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="243b8-156">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="243b8-156">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="243b8-157">如果未定义 ExtensibleMenu，则使用 MainWindowRightClick 和 ConversationWindowActions 的默认值。</span><span class="sxs-lookup"><span data-stu-id="243b8-157">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="243b8-158">下表介绍参数的注册表项。</span><span class="sxs-lookup"><span data-stu-id="243b8-158">The following table describes the registry entries for parameters.</span></span> <span data-ttu-id="243b8-159">这些条目放置\_在 HKEY 当前\_用户\\软件\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\参数中。</span><span class="sxs-lookup"><span data-stu-id="243b8-159">These entries are place at HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters.</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="243b8-160">基于 Internet 的协作应用程序的注册表项</span><span class="sxs-lookup"><span data-stu-id="243b8-160">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="243b8-161">名称</span><span class="sxs-lookup"><span data-stu-id="243b8-161">Name</span></span></th>
<th><span data-ttu-id="243b8-162">类型</span><span class="sxs-lookup"><span data-stu-id="243b8-162">Type</span></span></th>
<th><span data-ttu-id="243b8-163">Data</span><span class="sxs-lookup"><span data-stu-id="243b8-163">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="243b8-164">Param1</span><span class="sxs-lookup"><span data-stu-id="243b8-164">Param1</span></span></p></td>
<td><p><span data-ttu-id="243b8-165">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="243b8-165">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="243b8-166">在标记化格式中<code>%Parm1%</code>使用（）将特定于用户的值添加到 OriginatorPath 注册表项。</span><span class="sxs-lookup"><span data-stu-id="243b8-166">Used in tokenized format (<code>%Parm1%</code>) to add user-specific values to the OriginatorPath registry key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="243b8-167">Param2</span><span class="sxs-lookup"><span data-stu-id="243b8-167">Param2</span></span></p></td>
<td><p><span data-ttu-id="243b8-168">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="243b8-168">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="243b8-169">请参见 Param1。</span><span class="sxs-lookup"><span data-stu-id="243b8-169">See Param1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="243b8-170">Param3</span><span class="sxs-lookup"><span data-stu-id="243b8-170">Param3</span></span></p></td>
<td><p><span data-ttu-id="243b8-171">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="243b8-171">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="243b8-172">请参见 Param1。</span><span class="sxs-lookup"><span data-stu-id="243b8-172">See Param1.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="243b8-173">以下示例注册表设置将 ADatum 协作客户端与 Lync 2013 集成：</span><span class="sxs-lookup"><span data-stu-id="243b8-173">The following example registry settings integrate ADatum Collaboration Client with Lync 2013:</span></span>

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

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="243b8-174">将基于服务器的协作应用程序与 Lync 2013 集成</span><span class="sxs-lookup"><span data-stu-id="243b8-174">Integrating a Server-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="243b8-175">用于从 Lync 2013 中添加用于启动基于服务器的协作应用程序的命令的设置与上一节中所述，将基于 Internet 的协作应用程序与 Lync 2013 集成在一起。</span><span class="sxs-lookup"><span data-stu-id="243b8-175">The settings to add commands for starting a server-based collaboration application from within Lync 2013 are similar to those described in the previous section, Integrating an Internet-Based Collaboration Application with Lync 2013.</span></span> <span data-ttu-id="243b8-176">但是，不需要 OriginatorPath，且更改了某些值。</span><span class="sxs-lookup"><span data-stu-id="243b8-176">However, the OriginatorPath is not required, and some values are changed.</span></span> <span data-ttu-id="243b8-177">注册表项放置在以下位置：</span><span class="sxs-lookup"><span data-stu-id="243b8-177">Registry entries are placed in the following location:</span></span>

  - <span data-ttu-id="243b8-178">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span><span class="sxs-lookup"><span data-stu-id="243b8-178">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-a-server-based-collaboration-application"></a><span data-ttu-id="243b8-179">基于服务器的协作应用程序的注册表项</span><span class="sxs-lookup"><span data-stu-id="243b8-179">Registry Entries for a Server-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="243b8-180">名称</span><span class="sxs-lookup"><span data-stu-id="243b8-180">Name</span></span></th>
<th><span data-ttu-id="243b8-181">类型</span><span class="sxs-lookup"><span data-stu-id="243b8-181">Type</span></span></th>
<th><span data-ttu-id="243b8-182">Data</span><span class="sxs-lookup"><span data-stu-id="243b8-182">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="243b8-183">名称</span><span class="sxs-lookup"><span data-stu-id="243b8-183">Name</span></span></p></td>
<td><p><span data-ttu-id="243b8-184">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="243b8-184">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="243b8-185">显示在菜单上的应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="243b8-185">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="243b8-186">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="243b8-186">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="243b8-187">DWORD</span><span class="sxs-lookup"><span data-stu-id="243b8-187">DWORD</span></span></p></td>
<td><p><span data-ttu-id="243b8-188">值 = 1。</span><span class="sxs-lookup"><span data-stu-id="243b8-188">Value = 1.</span></span> <span data-ttu-id="243b8-189">将应用程序类型设置为协议。</span><span class="sxs-lookup"><span data-stu-id="243b8-189">Sets the application type to protocol.</span></span> <span data-ttu-id="243b8-190">其他可能值在此情况下不适用。</span><span class="sxs-lookup"><span data-stu-id="243b8-190">The other possible values do not apply in this case.</span></span> <span data-ttu-id="243b8-191">如果不存在，则 ApplicationType 设置为0（可执行文件）。</span><span class="sxs-lookup"><span data-stu-id="243b8-191">If not present, ApplicationType is set to 0 (executable).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="243b8-192">Path</span><span class="sxs-lookup"><span data-stu-id="243b8-192">Path</span></span></p></td>
<td><p><span data-ttu-id="243b8-193">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="243b8-193">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="243b8-194">用于启动该协作应用程序的协议。</span><span class="sxs-lookup"><span data-stu-id="243b8-194">Protocol used to start the collaboration application.</span></span> <span data-ttu-id="243b8-195">对于 Live Meeting 2007，Path 的值设置为<code>meet:%conf-uri%</code>。</span><span class="sxs-lookup"><span data-stu-id="243b8-195">For Live Meeting 2007, the value of Path is set to <code>meet:%conf-uri%</code>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="243b8-196">SessionType</span><span class="sxs-lookup"><span data-stu-id="243b8-196">SessionType</span></span></p></td>
<td><p><span data-ttu-id="243b8-197">DWORD</span><span class="sxs-lookup"><span data-stu-id="243b8-197">DWORD</span></span></p></td>
<td><p><span data-ttu-id="243b8-p114">0 = 本地会话。应用程序在本地计算机上启动。</span><span class="sxs-lookup"><span data-stu-id="243b8-p114">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="243b8-200">1 = 两方会话（默认）。</span><span class="sxs-lookup"><span data-stu-id="243b8-200">1 = Two-party session (default).</span></span> <span data-ttu-id="243b8-201">Lync 2013 在本地启动应用程序，然后将系统通知发送给其他用户。</span><span class="sxs-lookup"><span data-stu-id="243b8-201">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="243b8-202">其他用户单击该通知，并在其计算机上启动指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="243b8-202">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="243b8-203">2 = 多方会话。</span><span class="sxs-lookup"><span data-stu-id="243b8-203">2 = Multiparty session.</span></span> <span data-ttu-id="243b8-204">Lync 2013 在本地启动应用程序，然后向其他用户发送系统通知，提示他们在其计算机上启动指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="243b8-204">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="243b8-205">MCUType</span><span class="sxs-lookup"><span data-stu-id="243b8-205">MCUType</span></span></p></td>
<td><p><span data-ttu-id="243b8-206">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="243b8-206">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="243b8-207">DATA = 服务器的类型。</span><span class="sxs-lookup"><span data-stu-id="243b8-207">DATA = The type of server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="243b8-208">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="243b8-208">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="243b8-209">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="243b8-209">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="243b8-210">将显示此命令的菜单列表，用分号分隔。</span><span class="sxs-lookup"><span data-stu-id="243b8-210">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="243b8-211">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="243b8-211">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="243b8-212">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="243b8-212">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="243b8-213">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="243b8-213">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="243b8-214">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="243b8-214">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="243b8-215">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="243b8-215">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="243b8-216">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="243b8-216">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="243b8-217">如果未定义 ExtensibleMenu，则使用 MainWindowRightClick 和 ConversationWindowActions 的默认值。</span><span class="sxs-lookup"><span data-stu-id="243b8-217">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="243b8-218">下面的示例添加了从 Lync 2013 中启动 ADatum 协作客户端的命令：</span><span class="sxs-lookup"><span data-stu-id="243b8-218">The following example adds commands to start ADatum Collaboration Client from within Lync 2013:</span></span>

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

