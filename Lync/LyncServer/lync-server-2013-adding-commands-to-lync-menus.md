---
title: Lync Server 2013：将命令添加到 Lync 菜单
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding commands to Lync menus
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412788(v=OCS.15)
ms:contentKeyID: 48185091
ms.date: 04/11/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b6377824a7d96e6bb7b0ae6c60c79f3ee4c05b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a><span data-ttu-id="26dea-102">在 Lync Server 2013 中向 Lync 菜单添加命令</span><span class="sxs-lookup"><span data-stu-id="26dea-102">Adding commands to Lync menus in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26dea-103">_**上次修改的主题：** 2016-04-11_</span><span class="sxs-lookup"><span data-stu-id="26dea-103">_**Topic Last Modified:** 2016-04-11_</span></span>

<span data-ttu-id="26dea-104">您可以向 Lync 2013 菜单中添加自定义命令，并将当前用户和所选联系人的 SIP 统一资源标识符（URI）传递给应用程序，自定义命令将启动。</span><span class="sxs-lookup"><span data-stu-id="26dea-104">You can add custom commands to Lync 2013 menus and pass the SIP Uniform Resource Identifier (URI) of the current user and selected contacts to the application that the custom command starts.</span></span>

<span data-ttu-id="26dea-105">您添加的自定义命令可以出现在以下一个或多个菜单上：</span><span class="sxs-lookup"><span data-stu-id="26dea-105">The custom commands that you add can appear on one or more of the following menus:</span></span>

  - <span data-ttu-id="26dea-106">Lync 主窗口中的菜单栏上的 "工具" 菜单</span><span class="sxs-lookup"><span data-stu-id="26dea-106">The Tools menu, on the menu bar in the Lync main window</span></span>

  - <span data-ttu-id="26dea-107">"联系人" 列表中联系人的快捷菜单</span><span class="sxs-lookup"><span data-stu-id="26dea-107">The shortcut menu for contacts in the Contacts list</span></span>

  - <span data-ttu-id="26dea-108">对话窗口中的 "更多选项" 菜单</span><span class="sxs-lookup"><span data-stu-id="26dea-108">The More Options menu, in the Conversation window</span></span>

  - <span data-ttu-id="26dea-109">对话窗口参与者列表中列出的人员的快捷菜单</span><span class="sxs-lookup"><span data-stu-id="26dea-109">The shortcut menu for people listed in the Conversation window participant list</span></span>

  - <span data-ttu-id="26dea-110">联系人卡片中的 "选项" 菜单</span><span class="sxs-lookup"><span data-stu-id="26dea-110">The options menu in a contact card</span></span>

<span data-ttu-id="26dea-111">您可以为两种类型的应用程序定义自定义命令，即执行下列操作之一的应用程序：</span><span class="sxs-lookup"><span data-stu-id="26dea-111">You can define custom commands for two types of applications—applications that do either of the following:</span></span>

  - <span data-ttu-id="26dea-112">仅应用于当前用户并在本地计算机上启动。</span><span class="sxs-lookup"><span data-stu-id="26dea-112">Apply only to the current user and are started on the local computer.</span></span>

  - <span data-ttu-id="26dea-113">涉及其他用户（如联机协作计划），并且必须在每个用户的计算机上启动。</span><span class="sxs-lookup"><span data-stu-id="26dea-113">Involve additional users, such as an online collaboration program, and must be started on each user's computer.</span></span>

<span data-ttu-id="26dea-114">可以通过以下方式调用自定义命令：</span><span class="sxs-lookup"><span data-stu-id="26dea-114">The custom command can be invoked in the following ways:</span></span>

  - <span data-ttu-id="26dea-115">选择一个或多个用户，然后选择 "自定义" 命令。</span><span class="sxs-lookup"><span data-stu-id="26dea-115">Select one or more users, and then choose the custom command.</span></span>

  - <span data-ttu-id="26dea-116">启动两方或多方对话，然后选择 "自定义" 命令。</span><span class="sxs-lookup"><span data-stu-id="26dea-116">Start a two-party or multiparty conversation, and then choose the custom command.</span></span>

<div>

## <a name="to-add-a-custom-command"></a><span data-ttu-id="26dea-117">添加自定义命令</span><span class="sxs-lookup"><span data-stu-id="26dea-117">To add a custom command</span></span>

<span data-ttu-id="26dea-118">使用下表中的注册表设置将命令添加到菜单中。</span><span class="sxs-lookup"><span data-stu-id="26dea-118">Use the registry settings in the following table to add a command to the menus.</span></span> <span data-ttu-id="26dea-119">这些条目放置在注册表中的以下位置之一：</span><span class="sxs-lookup"><span data-stu-id="26dea-119">These entries are placed in the registry at one of the following locations:</span></span>

  - <span data-ttu-id="26dea-120">对于32位 OS：\_HKEY\_LOCAL\\MACHINE\\SOFTWARE\\Microsoft\\Office\\15.0\\Lync\\SessionManager Apps</span><span class="sxs-lookup"><span data-stu-id="26dea-120">For 32bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

  - <span data-ttu-id="26dea-121">对于64位 OS：\_HKEY\_LOCAL\\MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync\\SessionManager Apps</span><span class="sxs-lookup"><span data-stu-id="26dea-121">For 64bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

### <a name="custom-command-registry-entries"></a><span data-ttu-id="26dea-122">自定义命令注册表项</span><span class="sxs-lookup"><span data-stu-id="26dea-122">Custom Command Registry Entries</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="26dea-123">名称</span><span class="sxs-lookup"><span data-stu-id="26dea-123">Name</span></span></th>
<th><span data-ttu-id="26dea-124">类型</span><span class="sxs-lookup"><span data-stu-id="26dea-124">Type</span></span></th>
<th><span data-ttu-id="26dea-125">Data</span><span class="sxs-lookup"><span data-stu-id="26dea-125">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="26dea-126">名称</span><span class="sxs-lookup"><span data-stu-id="26dea-126">Name</span></span></p></td>
<td><p><span data-ttu-id="26dea-127">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="26dea-127">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="26dea-128">显示在菜单上的应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="26dea-128">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26dea-129">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="26dea-129">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="26dea-130">DWORD</span><span class="sxs-lookup"><span data-stu-id="26dea-130">DWORD</span></span></p></td>
<td><p><span data-ttu-id="26dea-131">0 = 可执行文件（默认值）</span><span class="sxs-lookup"><span data-stu-id="26dea-131">0 = Executable (default)</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="26dea-132">需要 ApplicationInstallPath。</span><span class="sxs-lookup"><span data-stu-id="26dea-132">Requires ApplicationInstallPath.</span></span>


</div>
<p><span data-ttu-id="26dea-133">1 = 协议</span><span class="sxs-lookup"><span data-stu-id="26dea-133">1 = Protocol</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26dea-134">ApplicationInstallPath</span><span class="sxs-lookup"><span data-stu-id="26dea-134">ApplicationInstallPath</span></span></p></td>
<td><p><span data-ttu-id="26dea-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="26dea-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="26dea-136">可执行文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="26dea-136">Full path of the executable.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="26dea-137">如果 ApplicationType 为0（可执行文件），则必须指定。</span><span class="sxs-lookup"><span data-stu-id="26dea-137">Must be specified if ApplicationType is 0 (Executable).</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26dea-138">Path</span><span class="sxs-lookup"><span data-stu-id="26dea-138">Path</span></span></p></td>
<td><p><span data-ttu-id="26dea-139">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="26dea-139">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="26dea-140">要与任何参数一起启动的完整路径，包括默认参数<em>% user id</em> % 和<em>% contact id%</em>。</span><span class="sxs-lookup"><span data-stu-id="26dea-140">Full path to be started along with any parameters, including the default parameters <em>%user-id%</em> and <em>%contact-id%</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26dea-141">SessionType</span><span class="sxs-lookup"><span data-stu-id="26dea-141">SessionType</span></span></p></td>
<td><p><span data-ttu-id="26dea-142">DWORD</span><span class="sxs-lookup"><span data-stu-id="26dea-142">DWORD</span></span></p></td>
<td><p><span data-ttu-id="26dea-p102">0 = 本地会话。应用程序在本地计算机上启动。</span><span class="sxs-lookup"><span data-stu-id="26dea-p102">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="26dea-145">1 = 两方会话（默认）。</span><span class="sxs-lookup"><span data-stu-id="26dea-145">1 = Two-party session (default).</span></span> <span data-ttu-id="26dea-146">Lync 2013 在本地启动应用程序，然后将桌面通知发送给其他用户。</span><span class="sxs-lookup"><span data-stu-id="26dea-146">Lync 2013 starts the application locally and then sends a desktop notification to the other user.</span></span> <span data-ttu-id="26dea-147">另一个用户单击通知以在其计算机上启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="26dea-147">The other user clicks the notification to start the application on their computer.</span></span></p>
<p><span data-ttu-id="26dea-148">2 = 多方会话。</span><span class="sxs-lookup"><span data-stu-id="26dea-148">2 = Multiparty session.</span></span> <span data-ttu-id="26dea-149">Lync 2013 在本地启动应用程序，然后将桌面通知发送给其他用户。</span><span class="sxs-lookup"><span data-stu-id="26dea-149">Lync 2013 starts the application locally and then sends desktop notifications to the other users.</span></span> <span data-ttu-id="26dea-150">另一个用户单击通知以在其计算机上启动指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="26dea-150">The other user clicks the notification to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26dea-151">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="26dea-151">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="26dea-152">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="26dea-152">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="26dea-153">将显示此命令的菜单列表，用分号分隔。</span><span class="sxs-lookup"><span data-stu-id="26dea-153">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="26dea-154">可能的值为：</span><span class="sxs-lookup"><span data-stu-id="26dea-154">Possible values are:</span></span></p>
<p><span data-ttu-id="26dea-155">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="26dea-155">MainWindowActions</span></span></p>
<p><span data-ttu-id="26dea-156">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="26dea-156">MainWindowRightClick</span></span></p>
<p><span data-ttu-id="26dea-157">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="26dea-157">ConversationWindowActions</span></span></p>
<p><span data-ttu-id="26dea-158">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="26dea-158">ConversationWindowRightClick</span></span></p>
<p><span data-ttu-id="26dea-159">ContactCardMenu</span><span class="sxs-lookup"><span data-stu-id="26dea-159">ContactCardMenu</span></span></p>
<p><span data-ttu-id="26dea-160">如果未定义 ExtensibleMenu，则使用 MainWindowRightClick 和 ConversationWindowActions 的默认值。</span><span class="sxs-lookup"><span data-stu-id="26dea-160">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="26dea-161">例如，下面的注册表编辑器（。REG）文件显示在对话窗口中向 "操作" 菜单添加 Contoso Sales Contact Manager 菜单项的结果：</span><span class="sxs-lookup"><span data-stu-id="26dea-161">For example, the following Registry Editor (.REG) file shows the results of adding a Contoso Sales Contact Manager menu item to Actions menu in the Conversation window:</span></span>

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Office\15.0\Lync\SessionManager\Apps\{1F9F07C6-7E0B-462B-AAD7-98C6DBEA8F69}]
    "Name"="Contoso Sales Contact Manager"
    "HelpMessage"="The Contoso Sales Contact Manager is not installed. Contact the Help Desk for more information."
    "ApplicationType"=dword:00000000
    "ApplicationInstallPath"="C:\\cscm.exe"
    "Path"="C:\\cscm.exe %user-id% %contact-id%"
    "SessionType"=dword:00000001
    "ExtensibleMenu"="ConversationWindowActions;MainWindowRightClick"

</div>

<div>

## <a name="to-access-a-custom-command"></a><span data-ttu-id="26dea-162">访问自定义命令</span><span class="sxs-lookup"><span data-stu-id="26dea-162">To access a custom command</span></span>

<span data-ttu-id="26dea-163">若要在添加自定义命令后对其进行访问，请执行下列操作之一，具体取决于您定义的 ExtensibleMenu 值：</span><span class="sxs-lookup"><span data-stu-id="26dea-163">To access a custom command after it is added, do one of the following, depending on the ExtensibleMenu values that you define:</span></span>

  - <span data-ttu-id="26dea-164">**MainWindowActions**   在 Lync 主窗口中，单击 "**工具**"，然后单击您的自定义命令。</span><span class="sxs-lookup"><span data-stu-id="26dea-164">**MainWindowActions**   In the Lync main window, click **Tools**, and then click your custom command.</span></span>

  - <span data-ttu-id="26dea-165">**MainWindowRightClick**   在 Lync 主窗口中，右键单击某个联系人，然后单击您的自定义命令。</span><span class="sxs-lookup"><span data-stu-id="26dea-165">**MainWindowRightClick**   In the Lync main window, right-click a contact, and then click your custom command.</span></span>

  - <span data-ttu-id="26dea-166">**ConversationWindowActions**   在对话窗口中，单击 "**更多选项**" 图标，然后单击您的自定义命令。</span><span class="sxs-lookup"><span data-stu-id="26dea-166">**ConversationWindowActions**   In the Conversation window, click the **More Options** icon, and then click your custom command.</span></span>

  - <span data-ttu-id="26dea-167">**ConversationWindowRightClick**   在对话窗口中，右键单击某个联系人名称，然后单击您的自定义命令。</span><span class="sxs-lookup"><span data-stu-id="26dea-167">**ConversationWindowRightClick**   In the Conversation window, right-click a contact name, and then click your custom command.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

