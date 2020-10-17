---
title: 将第三方协作应用程序与 Lync 集成
description: 将第三方协作应用程序与 Lync 集成。
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
ms.openlocfilehash: 7adbe1abab83a569f581af034fc46abfef4cf819
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552648"
---
# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a><span data-ttu-id="fad74-103">将第三方协作应用程序与 Lync Server 2013 集成</span><span class="sxs-lookup"><span data-stu-id="fad74-103">Integrating a third-party collaboration application with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fad74-104">_**上次修改的主题：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="fad74-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="fad74-105">您可以通过向注册表添加有关应用程序的信息，将 Lync 2013 与任何第三方在线协作应用程序集成。</span><span class="sxs-lookup"><span data-stu-id="fad74-105">You can integrate Lync 2013 with any third-party online collaboration application by adding information about the application to the registry.</span></span> <span data-ttu-id="fad74-106">您可以使用 Lync 2013 启动在内部服务器上托管的数据会议会话、基于 Internet 的服务或同时在这两者上启动。</span><span class="sxs-lookup"><span data-stu-id="fad74-106">You can use Lync 2013 to start data conferencing sessions hosted on an in-house server, an Internet-based service, or both.</span></span> <span data-ttu-id="fad74-107">可以从联系人列表或者从现有的即时消息、语音或视频会话中启动协作或数据会议会话。</span><span class="sxs-lookup"><span data-stu-id="fad74-107">The collaboration or data conferencing session can be started from the Contacts list or from an existing instant messaging, voice, or video session.</span></span> <span data-ttu-id="fad74-108">Lync 2013 仅用作启动应用程序的工具。</span><span class="sxs-lookup"><span data-stu-id="fad74-108">Lync 2013 acts only as the vehicle for starting the application.</span></span> <span data-ttu-id="fad74-109">联机协作会话开始后，任何现有的 Lync 2013 对话仍处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="fad74-109">Any existing Lync 2013 conversations remain active after the online collaboration session has begun.</span></span>

<span data-ttu-id="fad74-110">以下各节介绍如何将 Lync 2013 与基于 Internet 的协作应用程序和基于服务器的协作应用程序集成。</span><span class="sxs-lookup"><span data-stu-id="fad74-110">The following sections describe how to integrate Lync 2013 with Internet-based and server-based collaboration applications.</span></span>

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="fad74-111">将 Internet-Based 协作应用程序与 Lync 2013 集成</span><span class="sxs-lookup"><span data-stu-id="fad74-111">Integrating an Internet-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="fad74-112">一般而言，集成第三方协作应用程序的步骤如下：</span><span class="sxs-lookup"><span data-stu-id="fad74-112">Generally, the steps involved in integrating a third-party collaboration application are as follows:</span></span>

1.  <span data-ttu-id="fad74-113">将有关该应用程序的信息添加到注册表中。</span><span class="sxs-lookup"><span data-stu-id="fad74-113">Information about the application is added to the registry.</span></span>

2.  <span data-ttu-id="fad74-114">组织者登录到 Lync 2013 并选择联系人进行数据共享和协作。</span><span class="sxs-lookup"><span data-stu-id="fad74-114">The organizer signs in to Lync 2013 and selects contacts for data sharing and collaboration.</span></span> <span data-ttu-id="fad74-115">或者，组织者可能已经处于对话中，决定添加数据会议。</span><span class="sxs-lookup"><span data-stu-id="fad74-115">Or, the organizer may already be in a conversation and decide to add data conferencing.</span></span>

3.  <span data-ttu-id="fad74-116">Lync 2013 读取注册表，启动协作应用程序，然后向所选参与者发送自定义 SIP 消息（appINVITE）。</span><span class="sxs-lookup"><span data-stu-id="fad74-116">Lync 2013 reads the registry, starts the collaboration application, and then sends a custom SIP message—an appINVITE—to the selected participants.</span></span>

4.  <span data-ttu-id="fad74-117">参与者接受邀请，每个人的计算机上将启动协作应用程序。</span><span class="sxs-lookup"><span data-stu-id="fad74-117">Participants accept the invitation, and the collaboration application is started on each person’s computer.</span></span> <span data-ttu-id="fad74-118">Lync 2013 使用注册表确定要使用的协作应用程序，然后使用 appINVITE 邮件中包含的参数启动该应用程序。</span><span class="sxs-lookup"><span data-stu-id="fad74-118">Lync 2013 uses the registry to determine which collaboration application to use, and then starts that application by using the parameters included in the appINVITE message.</span></span>

<span data-ttu-id="fad74-119">下表介绍了将基于 Internet 的协作应用程序与 Lync 2013 集成所需的注册表项。</span><span class="sxs-lookup"><span data-stu-id="fad74-119">The following table describes the registry entries required to integrate an Internet-based collaboration application with Lync 2013.</span></span> <span data-ttu-id="fad74-120">这些项放置在注册表中的以下位置：</span><span class="sxs-lookup"><span data-stu-id="fad74-120">These entries are placed in the registry in the following location:</span></span>

  - <span data-ttu-id="fad74-121">HKEY \_ LOCAL \_ MACHINE \\ Software \\ Microsoft \\ Office \\ 15.0 \\ Lync \\ SessionManager \\ Apps \\ Parameters</span><span class="sxs-lookup"><span data-stu-id="fad74-121">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="fad74-122">基于 Internet 的协作应用程序的注册表项</span><span class="sxs-lookup"><span data-stu-id="fad74-122">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fad74-123">名称</span><span class="sxs-lookup"><span data-stu-id="fad74-123">Name</span></span></th>
<th><span data-ttu-id="fad74-124">类型</span><span class="sxs-lookup"><span data-stu-id="fad74-124">Type</span></span></th>
<th><span data-ttu-id="fad74-125">Data</span><span class="sxs-lookup"><span data-stu-id="fad74-125">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fad74-126">名称</span><span class="sxs-lookup"><span data-stu-id="fad74-126">Name</span></span></p></td>
<td><p><span data-ttu-id="fad74-127">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="fad74-127">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="fad74-128">Lync 2013 菜单的应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="fad74-128">The application name for Lync 2013 menus.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fad74-129">SmallIcon</span><span class="sxs-lookup"><span data-stu-id="fad74-129">SmallIcon</span></span></p></td>
<td><p><span data-ttu-id="fad74-130">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="fad74-130">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="fad74-131">16 像素 x 16 像素的图标（BMP 或 PNG 格式）的路径。</span><span class="sxs-lookup"><span data-stu-id="fad74-131">Path to 16-pixel x 16-pixel icon, BMP or PNG.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fad74-132">Path</span><span class="sxs-lookup"><span data-stu-id="fad74-132">Path</span></span></p></td>
<td><p><span data-ttu-id="fad74-133">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="fad74-133">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="fad74-134">用于启动联机协作应用程序的参与者路径。</span><span class="sxs-lookup"><span data-stu-id="fad74-134">Participant path for starting the online collaboration application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fad74-135">OriginatorPath</span><span class="sxs-lookup"><span data-stu-id="fad74-135">OriginatorPath</span></span></p></td>
<td><p><span data-ttu-id="fad74-136">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="fad74-136">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="fad74-137">用于启动联机协作应用程序的组织者路径。</span><span class="sxs-lookup"><span data-stu-id="fad74-137">Organizer path for starting the online collaboration application.</span></span> <span data-ttu-id="fad74-138">此路径可以包含如同 Parameters 子项中定义的一个或多个自定义参数。</span><span class="sxs-lookup"><span data-stu-id="fad74-138">This path can contain one or more custom parameters as defined in the Parameters subkey.</span></span> <span data-ttu-id="fad74-139">例如，<code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span><span class="sxs-lookup"><span data-stu-id="fad74-139">For example, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fad74-140">SessionType</span><span class="sxs-lookup"><span data-stu-id="fad74-140">SessionType</span></span></p></td>
<td><p><span data-ttu-id="fad74-141">DWORD</span><span class="sxs-lookup"><span data-stu-id="fad74-141">DWORD</span></span></p></td>
<td><p><span data-ttu-id="fad74-p106">0 = 本地会话。应用程序在本地计算机上启动。</span><span class="sxs-lookup"><span data-stu-id="fad74-p106">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="fad74-144">1 = 两方会话（默认）。</span><span class="sxs-lookup"><span data-stu-id="fad74-144">1 = Two-party session (default).</span></span> <span data-ttu-id="fad74-145">Lync 2013 在本地启动应用程序，然后将系统通知发送给其他用户。</span><span class="sxs-lookup"><span data-stu-id="fad74-145">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="fad74-146">其他用户单击该通知，并在其计算机上启动指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="fad74-146">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="fad74-147">2 = 多方会话。</span><span class="sxs-lookup"><span data-stu-id="fad74-147">2 = Multiparty session.</span></span> <span data-ttu-id="fad74-148">Lync 2013 在本地启动应用程序，然后向其他用户发送系统通知，提示他们在自己的计算机上启动指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="fad74-148">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their own computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fad74-149">ExensibleMenu</span><span class="sxs-lookup"><span data-stu-id="fad74-149">ExensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="fad74-150">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="fad74-150">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="fad74-p109">将显示此命令的菜单列表，用分号分隔。可能的值为：</span><span class="sxs-lookup"><span data-stu-id="fad74-p109">A list of the menus where this command will appear, separated by semi-colons. Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="fad74-153">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="fad74-153">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="fad74-154">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="fad74-154">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="fad74-155">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="fad74-155">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="fad74-156">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="fad74-156">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="fad74-157">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="fad74-157">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="fad74-158">如果未定义 ExtensibleMenu，则使用 MainWindowRightClick 和 ConversationWindowActions 的默认值。</span><span class="sxs-lookup"><span data-stu-id="fad74-158">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fad74-159">下表介绍参数的注册表项。</span><span class="sxs-lookup"><span data-stu-id="fad74-159">The following table describes the registry entries for parameters.</span></span> <span data-ttu-id="fad74-160">这些条目放置在 HKEY \_ 当前 \_ 用户 \\ 软件 \\ Microsoft \\ Office \\ 15.0 \\ Lync \\ SessionManager \\ Apps 参数中 \\ 。</span><span class="sxs-lookup"><span data-stu-id="fad74-160">These entries are place at HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters.</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="fad74-161">基于 Internet 的协作应用程序的注册表项</span><span class="sxs-lookup"><span data-stu-id="fad74-161">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fad74-162">名称</span><span class="sxs-lookup"><span data-stu-id="fad74-162">Name</span></span></th>
<th><span data-ttu-id="fad74-163">类型</span><span class="sxs-lookup"><span data-stu-id="fad74-163">Type</span></span></th>
<th><span data-ttu-id="fad74-164">Data</span><span class="sxs-lookup"><span data-stu-id="fad74-164">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fad74-165">Param1</span><span class="sxs-lookup"><span data-stu-id="fad74-165">Param1</span></span></p></td>
<td><p><span data-ttu-id="fad74-166">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="fad74-166">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="fad74-167">在标记化格式中使用 (<code>%Parm1%</code>) 将特定于用户的值添加到 OriginatorPath 注册表项。</span><span class="sxs-lookup"><span data-stu-id="fad74-167">Used in tokenized format (<code>%Parm1%</code>) to add user-specific values to the OriginatorPath registry key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fad74-168">Param2</span><span class="sxs-lookup"><span data-stu-id="fad74-168">Param2</span></span></p></td>
<td><p><span data-ttu-id="fad74-169">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="fad74-169">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="fad74-170">请参见 Param1。</span><span class="sxs-lookup"><span data-stu-id="fad74-170">See Param1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fad74-171">Param3</span><span class="sxs-lookup"><span data-stu-id="fad74-171">Param3</span></span></p></td>
<td><p><span data-ttu-id="fad74-172">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="fad74-172">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="fad74-173">请参见 Param1。</span><span class="sxs-lookup"><span data-stu-id="fad74-173">See Param1.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fad74-174">以下示例注册表设置将 ADatum 协作客户端与 Lync 2013 集成：</span><span class="sxs-lookup"><span data-stu-id="fad74-174">The following example registry settings integrate ADatum Collaboration Client with Lync 2013:</span></span>

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

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="fad74-175">将 Server-Based 协作应用程序与 Lync 2013 集成</span><span class="sxs-lookup"><span data-stu-id="fad74-175">Integrating a Server-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="fad74-176">用于从 Lync 2013 中添加用于启动基于服务器的协作应用程序的命令的设置与上一节中所述，将 Internet-Based 协作应用程序与 Lync 2013 集成在一起。</span><span class="sxs-lookup"><span data-stu-id="fad74-176">The settings to add commands for starting a server-based collaboration application from within Lync 2013 are similar to those described in the previous section, Integrating an Internet-Based Collaboration Application with Lync 2013.</span></span> <span data-ttu-id="fad74-177">但是，不需要 OriginatorPath，且更改了某些值。</span><span class="sxs-lookup"><span data-stu-id="fad74-177">However, the OriginatorPath is not required, and some values are changed.</span></span> <span data-ttu-id="fad74-178">注册表项放置在以下位置：</span><span class="sxs-lookup"><span data-stu-id="fad74-178">Registry entries are placed in the following location:</span></span>

  - <span data-ttu-id="fad74-179">HKEY \_ LOCAL \_ MACHINE \\ Software \\ Microsoft \\ Office \\ 15.0 \\ Lync \\ SessionManager \\ Apps \\ Parameters</span><span class="sxs-lookup"><span data-stu-id="fad74-179">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-a-server-based-collaboration-application"></a><span data-ttu-id="fad74-180">基于服务器的协作应用程序的注册表项</span><span class="sxs-lookup"><span data-stu-id="fad74-180">Registry Entries for a Server-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fad74-181">名称</span><span class="sxs-lookup"><span data-stu-id="fad74-181">Name</span></span></th>
<th><span data-ttu-id="fad74-182">类型</span><span class="sxs-lookup"><span data-stu-id="fad74-182">Type</span></span></th>
<th><span data-ttu-id="fad74-183">Data</span><span class="sxs-lookup"><span data-stu-id="fad74-183">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fad74-184">名称</span><span class="sxs-lookup"><span data-stu-id="fad74-184">Name</span></span></p></td>
<td><p><span data-ttu-id="fad74-185">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="fad74-185">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="fad74-186">显示在菜单上的应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="fad74-186">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fad74-187">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="fad74-187">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="fad74-188">DWORD</span><span class="sxs-lookup"><span data-stu-id="fad74-188">DWORD</span></span></p></td>
<td><p><span data-ttu-id="fad74-189">值 = 1。</span><span class="sxs-lookup"><span data-stu-id="fad74-189">Value = 1.</span></span> <span data-ttu-id="fad74-190">将应用程序类型设置为协议。</span><span class="sxs-lookup"><span data-stu-id="fad74-190">Sets the application type to protocol.</span></span> <span data-ttu-id="fad74-191">其他可能值在此情况下不适用。</span><span class="sxs-lookup"><span data-stu-id="fad74-191">The other possible values do not apply in this case.</span></span> <span data-ttu-id="fad74-192">如果不存在，则 ApplicationType 设置为 0 (可执行) 。</span><span class="sxs-lookup"><span data-stu-id="fad74-192">If not present, ApplicationType is set to 0 (executable).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fad74-193">Path</span><span class="sxs-lookup"><span data-stu-id="fad74-193">Path</span></span></p></td>
<td><p><span data-ttu-id="fad74-194">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="fad74-194">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="fad74-195">用于启动该协作应用程序的协议。</span><span class="sxs-lookup"><span data-stu-id="fad74-195">Protocol used to start the collaboration application.</span></span> <span data-ttu-id="fad74-196">对于 Live Meeting 2007，Path 的值设置为 <code>meet:%conf-uri%</code> 。</span><span class="sxs-lookup"><span data-stu-id="fad74-196">For Live Meeting 2007, the value of Path is set to <code>meet:%conf-uri%</code>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fad74-197">SessionType</span><span class="sxs-lookup"><span data-stu-id="fad74-197">SessionType</span></span></p></td>
<td><p><span data-ttu-id="fad74-198">DWORD</span><span class="sxs-lookup"><span data-stu-id="fad74-198">DWORD</span></span></p></td>
<td><p><span data-ttu-id="fad74-p114">0 = 本地会话。应用程序在本地计算机上启动。</span><span class="sxs-lookup"><span data-stu-id="fad74-p114">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="fad74-201">1 = 两方会话（默认）。</span><span class="sxs-lookup"><span data-stu-id="fad74-201">1 = Two-party session (default).</span></span> <span data-ttu-id="fad74-202">Lync 2013 在本地启动应用程序，然后将系统通知发送给其他用户。</span><span class="sxs-lookup"><span data-stu-id="fad74-202">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="fad74-203">其他用户单击该通知，并在其计算机上启动指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="fad74-203">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="fad74-204">2 = 多方会话。</span><span class="sxs-lookup"><span data-stu-id="fad74-204">2 = Multiparty session.</span></span> <span data-ttu-id="fad74-205">Lync 2013 在本地启动应用程序，然后向其他用户发送系统通知，提示他们在其计算机上启动指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="fad74-205">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fad74-206">MCUType</span><span class="sxs-lookup"><span data-stu-id="fad74-206">MCUType</span></span></p></td>
<td><p><span data-ttu-id="fad74-207">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="fad74-207">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="fad74-208">DATA = 服务器的类型。</span><span class="sxs-lookup"><span data-stu-id="fad74-208">DATA = The type of server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fad74-209">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="fad74-209">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="fad74-210">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="fad74-210">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="fad74-211">将显示此命令的菜单列表，用分号分隔。</span><span class="sxs-lookup"><span data-stu-id="fad74-211">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="fad74-212">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="fad74-212">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="fad74-213">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="fad74-213">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="fad74-214">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="fad74-214">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="fad74-215">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="fad74-215">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="fad74-216">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="fad74-216">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="fad74-217">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="fad74-217">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="fad74-218">如果未定义 ExtensibleMenu，则使用 MainWindowRightClick 和 ConversationWindowActions 的默认值。</span><span class="sxs-lookup"><span data-stu-id="fad74-218">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fad74-219">下面的示例添加了从 Lync 2013 中启动 ADatum 协作客户端的命令：</span><span class="sxs-lookup"><span data-stu-id="fad74-219">The following example adds commands to start ADatum Collaboration Client from within Lync 2013:</span></span>

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

