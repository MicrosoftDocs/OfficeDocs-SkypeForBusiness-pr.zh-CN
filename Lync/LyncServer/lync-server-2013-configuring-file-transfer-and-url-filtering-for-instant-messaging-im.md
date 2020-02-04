---
title: 为即时消息（IM）配置文件传输和 URL 筛选
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring file transfer and URL filtering for instant messaging (IM)
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520952(v=OCS.15)
ms:contentKeyID: 48183440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6c5a6053118b14b68c49a7fdaa6f444aca7ad23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729022"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a><span data-ttu-id="1654c-102">在 Lync Server 2013 中为即时消息（IM）配置文件传输和 URL 筛选</span><span class="sxs-lookup"><span data-stu-id="1654c-102">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1654c-103">_**主题上次修改时间：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1654c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1654c-104">智能 IM 筛选器工具可帮助保护 Lync Server 2013 部署，使其不受最常见的病毒形式的传播，最大程度地降低用户体验。</span><span class="sxs-lookup"><span data-stu-id="1654c-104">The Intelligent IM Filter tool helps protect your Lync Server 2013 deployment against the spread of the most common forms of viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="1654c-105">使用智能 IM 筛选器配置筛选器，阻止来自公司防火墙外的未知终结点的未经请求或可能有害的即时消息。</span><span class="sxs-lookup"><span data-stu-id="1654c-105">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="1654c-106">通过指定用于确定应阻止的条件的条件来配置筛选器，例如包含带有特定前缀的超链接的即时消息和具有特定扩展名的文件。</span><span class="sxs-lookup"><span data-stu-id="1654c-106">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks with specific prefixes and files with specific extensions.</span></span>

<span data-ttu-id="1654c-107">智能 IM 筛选器提供以下内容：</span><span class="sxs-lookup"><span data-stu-id="1654c-107">Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="1654c-108">增强的 URL 筛选。</span><span class="sxs-lookup"><span data-stu-id="1654c-108">Enhanced URL filtering.</span></span>

  - <span data-ttu-id="1654c-109">增强的文件传输筛选。</span><span class="sxs-lookup"><span data-stu-id="1654c-109">Enhanced file transfer filtering.</span></span>

<span data-ttu-id="1654c-110">配置智能 IM 筛选器包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="1654c-110">Configuring Intelligent IM Filter includes the following:</span></span>

  - <span data-ttu-id="1654c-111">配置 URL 筛选。</span><span class="sxs-lookup"><span data-stu-id="1654c-111">Configuring URL filtering.</span></span>

  - <span data-ttu-id="1654c-112">配置文件传输筛选。</span><span class="sxs-lookup"><span data-stu-id="1654c-112">Configuring file transfer filtering.</span></span>

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a><span data-ttu-id="1654c-113">如何对即时消息应用筛选选项</span><span class="sxs-lookup"><span data-stu-id="1654c-113">How Filtering Options Are Applied to Instant Messages</span></span>

<span data-ttu-id="1654c-114">在部署智能 IM 邮件筛选器工具之前，需要了解如何应用筛选选项，因为邮件是从一个 Lync Server 2013 服务器路由到另一个。</span><span class="sxs-lookup"><span data-stu-id="1654c-114">Before you deploy the Intelligent IM Message Filter tool, you need to understand how filtering options are applied as messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="1654c-115">应用这些筛选选项的方式是一致的，无论服务器位于单个组织还是跨组织边界。</span><span class="sxs-lookup"><span data-stu-id="1654c-115">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="1654c-116">此一致性适用于将自定义通知和警告文本插入到邮件并跨服务器发送的方式。</span><span class="sxs-lookup"><span data-stu-id="1654c-116">This consistency applies to the way that the customized notice and warning texts are inserted into messages and sent across servers.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="1654c-117">即时消息筛选器增加了处理消息中的 Url 所需的 CPU 资源量。</span><span class="sxs-lookup"><span data-stu-id="1654c-117">The instant message filter increases the amount of CPU resources required to process URLs in a message.</span></span> <span data-ttu-id="1654c-118">这种 CPU 需求的增加也会影响 Lync Server 的性能。</span><span class="sxs-lookup"><span data-stu-id="1654c-118">This increase in CPU demand also affects the performance of Lync Server.</span></span>



</div>

<span data-ttu-id="1654c-119">通过使用 Lync Server 控制面板中 " **IM 和联机状态**" 组中的**URL 筛选器**页面，你可以阻止部分或所有超链接或配置警告。</span><span class="sxs-lookup"><span data-stu-id="1654c-119">By using the **URL Filter** page in the **IM and Presence** group in Lync Server Control Panel, you can block some or all hyperlinks or configure a warning.</span></span> <span data-ttu-id="1654c-120">当选择 "**超链接前缀**选项**发送警告消息**" 时，将在包含超链接的即时消息的开头插入警告。</span><span class="sxs-lookup"><span data-stu-id="1654c-120">The warning is inserted at the beginning of an instant message that contains a hyperlink when you choose the **Hyperlink prefix** option **Send warning message**.</span></span>

<span data-ttu-id="1654c-121">当即时消息从一台服务器传播到另一台服务器时，请遵循以下一般指南：</span><span class="sxs-lookup"><span data-stu-id="1654c-121">When an instant message travels from one server to another, the following general guidelines apply:</span></span>

  - <span data-ttu-id="1654c-122">如果服务器阻止即时消息（因为已选中 " **URL 筛选器**" 页面上的 "**阻止带有文件扩展名的 url** " 复选框，或者选择了**超链接前缀**选项**块超链接**），则会向客户端返回一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="1654c-122">If a server blocks an instant message (because you selected the **Block URLs with file extension** check box on the **URL Filter** page or because you chose the **Hyperlink prefix** option **Block hyperlinks**), an error message is returned to the client.</span></span> <span data-ttu-id="1654c-123">后续服务器不会收到此即时消息。</span><span class="sxs-lookup"><span data-stu-id="1654c-123">Subsequent servers do not receive this instant message.</span></span>

  - <span data-ttu-id="1654c-124">如果服务器（Server1）将警告添加到包含活动超链接的即时消息中，则接收此即时消息的后续服务器（Server2）仍可根据此即时消息中显示的此活动超链接采取不同的操作，并阻止即时消息或添加警告。</span><span class="sxs-lookup"><span data-stu-id="1654c-124">If a server (Server1) adds a warning to an instant message that contains an active hyperlink, a subsequent server (Server2) that receives this instant message can still take a different action based on this active hyperlink present in the instant message and block the instant message or add a warning.</span></span> <span data-ttu-id="1654c-125">如果将 Server2 配置为仅为此 URL 添加警告，则将删除 Server1 添加的较早警告，并将在 Server2 上配置的警告添加到即时消息的开头。</span><span class="sxs-lookup"><span data-stu-id="1654c-125">If Server2 is configured only to add a warning for this URL, the earlier warning added by Server1 is removed, and the warning configured on Server2 is added to the beginning of the instant message.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="1654c-126">如果在混合环境中运行 Lync Server 2013，则使用该智能 IM 筛选器应用程序所需的最小版本是使用 SP1 的实时通信服务器2005。</span><span class="sxs-lookup"><span data-stu-id="1654c-126">If you are running Lync Server 2013 in a mixed environment, Live Communications Server 2005 with SP1 is the minimum version required to use the Intelligent IM Filter application.</span></span> <span data-ttu-id="1654c-127">没有 SP1 的实时通信服务器2005上不支持智能 IM 筛选器。</span><span class="sxs-lookup"><span data-stu-id="1654c-127">The Intelligent IM Filter is not supported on Live Communications Server 2005 without SP1.</span></span>



</div>

<div>

## <a name="url-filtering"></a><span data-ttu-id="1654c-128">URL 筛选</span><span class="sxs-lookup"><span data-stu-id="1654c-128">URL Filtering</span></span>

<span data-ttu-id="1654c-129">根据 Url 的超链接前缀对其进行筛选。</span><span class="sxs-lookup"><span data-stu-id="1654c-129">URLs are filtered according to their hyperlink prefix.</span></span> <span data-ttu-id="1654c-130">以下示例是有效的前缀：</span><span class="sxs-lookup"><span data-stu-id="1654c-130">The following examples are valid prefixes:</span></span>

  - <span data-ttu-id="1654c-131">www\*。</span><span class="sxs-lookup"><span data-stu-id="1654c-131">www\*.</span></span>

  - <span data-ttu-id="1654c-132">ftp.</span><span class="sxs-lookup"><span data-stu-id="1654c-132">ftp.</span></span>

  - <span data-ttu-id="1654c-133">http</span><span class="sxs-lookup"><span data-stu-id="1654c-133">http:</span></span>

<span data-ttu-id="1654c-134">如果未将即时消息筛选器配置为执行任何 URL 筛选，则即时消息中包含的所有 Url 都将通过服务器未修改。</span><span class="sxs-lookup"><span data-stu-id="1654c-134">If you do not configure the instant message filter to perform any URL filtering, all URLs contained in instant messages are passed unmodified through the server.</span></span> <span data-ttu-id="1654c-135">如果将即时消息筛选器配置为执行 URL 筛选，则会根据你在 "**编辑 URL 筛选**" 或 "**新建 url 筛选器**" 对话框中选择的选项筛选即时消息中的 url。</span><span class="sxs-lookup"><span data-stu-id="1654c-135">If you configure the instant message filter to perform URL filtering, URLs in instant messages are filtered according to the options that you select in the **Edit URL Filter** or **New URL Filter** dialog box.</span></span>

  - <span data-ttu-id="1654c-136">**启用 url 筛选器**   此选项为全局部署或你选择的网站启用 url 筛选。</span><span class="sxs-lookup"><span data-stu-id="1654c-136">**Enable URL filter**   This option enables URL filtering for the global deployment or for the site that you select.</span></span>

  - <span data-ttu-id="1654c-137">**使用文件扩展名**   阻止 url 即时消息筛选器阻止所有活动 intranet 或 Internet URL，其中包含在 "**编辑文件筛选器**" 对话框中 "**要阻止的文件类型扩展**" 下列出的扩展名的文件。</span><span class="sxs-lookup"><span data-stu-id="1654c-137">**Block URLs with file extension**   The instant message filter blocks any active intranet or Internet URL that contains a file with an extension listed under **File type extensions to block** in the **Edit File Filter** dialog box.</span></span> <span data-ttu-id="1654c-138">当某个 URL 被阻止时，会向发件人显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="1654c-138">When a URL is blocked, an error message is displayed to the sender.</span></span> <span data-ttu-id="1654c-139">选中此选项后，此选项将优先于 "**文件类型扩展**" 下定义的任何文件扩展名的所有其他筛选选项。</span><span class="sxs-lookup"><span data-stu-id="1654c-139">When selected, this option takes precedence over all other filtering options for any file extensions defined under **File type extensions to block**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="1654c-140">对文件扩展名的筛选仅限于标准文件名称。</span><span class="sxs-lookup"><span data-stu-id="1654c-140">Filtering of file extensions is limited to standard file names.</span></span> <span data-ttu-id="1654c-141">筛选可能无法处理嵌入在其他名称中的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="1654c-141">Filtering may not work with file extensions embedded in other names.</span></span>

    
    </div>

<span data-ttu-id="1654c-142">若要配置在即时消息对话中如何处理超链接，请在 "**超链接前缀**" 下选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="1654c-142">To configure how hyperlinks are handled in instant message conversations, select one of the following options under **Hyperlink prefix**:</span></span>

  - <span data-ttu-id="1654c-143">**不筛选**   邮件中的 url 通过服务器发送。</span><span class="sxs-lookup"><span data-stu-id="1654c-143">**Do not filter**   URLs in messages are sent through the server.</span></span> <span data-ttu-id="1654c-144">选择此选项时，将显示 "**允许" 消息**框。</span><span class="sxs-lookup"><span data-stu-id="1654c-144">When you choose this option, the **Allow message** box appears.</span></span> <span data-ttu-id="1654c-145">在 "**允许消息**" 框中，指定要在包含超链接的每条即时消息的开头插入的通知。</span><span class="sxs-lookup"><span data-stu-id="1654c-145">In the **Allow message** box, specify the notice that you want to insert at the beginning of each instant message containing hyperlinks.</span></span> <span data-ttu-id="1654c-146">此通知包含的字符数不超过65535。</span><span class="sxs-lookup"><span data-stu-id="1654c-146">This notice can consist of no more than 65535 characters.</span></span>

  - <span data-ttu-id="1654c-147">**阻止超链接**   包含活动超链接的即时消息的传递被 Lync Server 阻止，并且向发件人显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="1654c-147">**Block hyperlinks**   Delivery of instant messages containing active hyperlinks is blocked by Lync Server, and an error message is displayed to the sender.</span></span>

  - <span data-ttu-id="1654c-148">**发送警告消息**   Lync Server 允许即时消息中的活动超链接，但包含警告。</span><span class="sxs-lookup"><span data-stu-id="1654c-148">**Send warning message**   Lync Server permits active hyperlinks in instant messages, but it includes a warning.</span></span> <span data-ttu-id="1654c-149">选择此选项时，将显示 "**警告消息**" 框。</span><span class="sxs-lookup"><span data-stu-id="1654c-149">When you choose this option, the **Warning message** box appears.</span></span> <span data-ttu-id="1654c-150">在 "**警告消息**" 框中，必须键入要包含在包含有效超链接的即时消息中的警告。</span><span class="sxs-lookup"><span data-stu-id="1654c-150">In the **Warning message** box, you must type the warning that you want to include with instant messages containing valid hyperlinks.</span></span> <span data-ttu-id="1654c-151">例如，此警告可能会声明单击未知链接的潜在危险，或者它可能会引用你组织的相关策略和要求。</span><span class="sxs-lookup"><span data-stu-id="1654c-151">For example, this warning might state the potential dangers of clicking an unknown link, or it might refer to your organization’s relevant policies and requirements.</span></span> <span data-ttu-id="1654c-152">警告不能超过65535个字符。</span><span class="sxs-lookup"><span data-stu-id="1654c-152">The warning can be no more than 65535 characters.</span></span>

<span data-ttu-id="1654c-153">如果选择 "**阻止超链接**" 或 "**发送警告消息**"，则可以使用以下选项：</span><span class="sxs-lookup"><span data-stu-id="1654c-153">If you select **Block hyperlinks** or **Send warning message**, the following options are available:</span></span>

  - <span data-ttu-id="1654c-154">**排除本地 intranet 超链接**   即时消息筛选器仅阻止 Internet url。</span><span class="sxs-lookup"><span data-stu-id="1654c-154">**Exclude local intranet hyperlinks**   The instant message filter blocks only Internet URLs.</span></span> <span data-ttu-id="1654c-155">Intranet 内的位置的 Url 通过服务器进行未修改的传递。</span><span class="sxs-lookup"><span data-stu-id="1654c-155">URLs for locations within your intranet are passed unmodified through the server.</span></span> <span data-ttu-id="1654c-156">但是，运行 Lync Server 的单个服务器通过的 intranet Url 取决于本地网站的哪些类型被视为其 intranet 区域的一部分。</span><span class="sxs-lookup"><span data-stu-id="1654c-156">However, the intranet URLs that individual servers running Lync Server pass depend on which types of local websites are considered part of their intranet zone.</span></span> <span data-ttu-id="1654c-157">若要检查服务器的 intranet 区域设置，请参阅在[Lync server 2013 中修改默认 URL 筛选器](lync-server-2013-modify-the-default-url-filter.md)中的 "在 Internet Explorer 中配置 intranet 设置" 过程。</span><span class="sxs-lookup"><span data-stu-id="1654c-157">To check a server’s intranet zone settings, see the “To configure your intranet settings in Internet Explorer” procedure in [Modify the default URL filter in Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md).</span></span>

  - <span data-ttu-id="1654c-158">**筛选这些超链接前缀**   若要选择要阻止的前缀，请单击 "**选择**"，然后在 "**选择超链接前缀**" 中，将前缀添加到 "**超链接前缀**" 列表。</span><span class="sxs-lookup"><span data-stu-id="1654c-158">**Filter these hyperlink prefixes**   To choose which prefixes you want to block, click **Select**, and then, in **Select Hyperlink Prefix**, add the prefixes to the **Hyperlink prefixes** list.</span></span>
    
    <span data-ttu-id="1654c-159">除**href**之外的所有前缀必须以句点或冒号结尾，或星号后跟句点。</span><span class="sxs-lookup"><span data-stu-id="1654c-159">All prefixes except **href** must end with a period or a colon, or an asterisk followed by a period.</span></span> <span data-ttu-id="1654c-160">有效的前缀可以包含有效 URL 字符组中除星号（\*）之外的任何字符。</span><span class="sxs-lookup"><span data-stu-id="1654c-160">Valid prefixes can contain any characters in the set of valid URL characters except the asterisk (\*).</span></span> <span data-ttu-id="1654c-161">有效的 URL 字符集\# \*为： +/0123456789 = @ABCDEFGHIJKLMNOPQRSTUVWXYZ ^\_ \` ABCDEFGHIJKLMNOPQRSTUVWXYZ | ~</span><span class="sxs-lookup"><span data-stu-id="1654c-161">The set of valid URL characters is: \#\*+/0123456789=@ABCDEFGHIJKLMNOPQRSTUVWXYZ^\_\` abcdefghijklmnopqrstuvwxyz|~</span></span>

</div>

<div>

## <a name="file-transfer-filtering"></a><span data-ttu-id="1654c-162">文件传输筛选</span><span class="sxs-lookup"><span data-stu-id="1654c-162">File Transfer Filtering</span></span>

<span data-ttu-id="1654c-163">筛选器传输筛选会影响即时消息和会议。</span><span class="sxs-lookup"><span data-stu-id="1654c-163">Filter transfer filtering affects both instant messages and conferences.</span></span> <span data-ttu-id="1654c-164">对于会议，这些设置影响 Office Live Meeting 2007 客户端和多媒体播放功能中的讲义功能。</span><span class="sxs-lookup"><span data-stu-id="1654c-164">For conferences, these settings affect the handout feature in the Office Live Meeting 2007 client and multimedia playback features.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="1654c-165">Lync 服务器还提供文件传输设置选项。</span><span class="sxs-lookup"><span data-stu-id="1654c-165">Lync Server also offers file transfer setting options.</span></span> <span data-ttu-id="1654c-166">除了 Lync Server 中提供的客户端控件之外，还提供此服务器端选项。</span><span class="sxs-lookup"><span data-stu-id="1654c-166">This server-side option is offered in addition to the client-side controls available in Lync Server.</span></span>



</div>

<span data-ttu-id="1654c-167">当你使用 Office Live Meeting 2007 客户端中的讲义功能时，你可以在即时消息对话中筛选文件传输，以及针对所有文件类型使用多媒体播放功能。</span><span class="sxs-lookup"><span data-stu-id="1654c-167">You can filter file transfers during instant message conversations, when you are using the handout feature in the Office Live Meeting 2007 client, and for multimedia playback features for all file types.</span></span> <span data-ttu-id="1654c-168">你可以设置以下选项来控制文件传输：</span><span class="sxs-lookup"><span data-stu-id="1654c-168">You can set the following options to control file transfers:</span></span>

  - <span data-ttu-id="1654c-169">**启用文件筛选器**   此选项为全局部署或你选择的网站启用文件筛选。</span><span class="sxs-lookup"><span data-stu-id="1654c-169">**Enable file filter**   This option enables file filtering for the global deployment or for the site that you select.</span></span>
    
    <span data-ttu-id="1654c-170">启用文件筛选器时，可以在 "**文件传输**" 中选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="1654c-170">When you enable the file filter, you can choose one of the following options in **File transfer**:</span></span>
    
      - <span data-ttu-id="1654c-171">**阻止特定文件类型**   通过指定要阻止的文件扩展名的列表，指定由服务器筛选的文件传输请求。</span><span class="sxs-lookup"><span data-stu-id="1654c-171">**Block specific file types**   You specify which file transfer requests are filtered by the server by specifying a list of file extensions to block.</span></span> <span data-ttu-id="1654c-172">列表中的条目可以包含所有标准字符，但不能包含通配符（\*）。</span><span class="sxs-lookup"><span data-stu-id="1654c-172">Entries in the list can contain all standard characters, but not the wildcard character (\*).</span></span> <span data-ttu-id="1654c-173">在 Office Live Meeting 2007 客户端中启用讲义功能，但不能上载或下载具有此扩展名的任何文件。</span><span class="sxs-lookup"><span data-stu-id="1654c-173">In the Office Live Meeting 2007 client the handout feature is enabled, but any file with this extension cannot be uploaded or downloaded.</span></span> <span data-ttu-id="1654c-174">如果在 " **Url 筛选器**" 选项卡上列出的 url 筛选器的设置中选中 "**阻止文件扩展名的 url** " 复选框，则 url 筛选器将使用此相同列表来阻止包含这些文件扩展名的活动超链接。</span><span class="sxs-lookup"><span data-stu-id="1654c-174">If you select the **Block URLs with file extension** check box on the settings for a URL filter listed on the **URL Filter** tab, the URL filter uses this same list to block active hyperlinks that contain any of these file extensions.</span></span> <span data-ttu-id="1654c-175">若要选择要阻止的文件类型，请单击 "**选择**"，然后在 "**选择文件类型**" 中，将文件类型扩展名添加到**所选文件类型扩展名**列表。</span><span class="sxs-lookup"><span data-stu-id="1654c-175">To choose which file types you want to block, click **Select**, and then, in **Select File Type**, add the file type extensions to the **Selected file type extensions** list.</span></span>
    
      - <span data-ttu-id="1654c-176">**"阻止所有**   服务器" 将丢弃所有包含文件传输请求的即时消息，并向请求的发件人返回一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="1654c-176">**Block All**   The server drops all instant messages that contain file transfer requests and returns an error message to the sender of the request.</span></span> <span data-ttu-id="1654c-177">Office Live Meeting 2007 客户端中的讲义功能被禁用。</span><span class="sxs-lookup"><span data-stu-id="1654c-177">The handout feature in the Office Live Meeting 2007 client is disabled.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="1654c-178">对文件扩展名的筛选仅限于标准文件名称。</span><span class="sxs-lookup"><span data-stu-id="1654c-178">Filtering of file extensions is limited to standard file names.</span></span> <span data-ttu-id="1654c-179">筛选可能无法处理嵌入在其他名称中的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="1654c-179">Filtering may not work with file extensions embedded in other names.</span></span>



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1654c-180">本节内容</span><span class="sxs-lookup"><span data-stu-id="1654c-180">In This Section</span></span>

  - [<span data-ttu-id="1654c-181">在 Lync Server 2013 中修改默认文件传输筛选器</span><span class="sxs-lookup"><span data-stu-id="1654c-181">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [<span data-ttu-id="1654c-182">在 Lync Server 2013 中为特定网站创建新的文件传输筛选器</span><span class="sxs-lookup"><span data-stu-id="1654c-182">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [<span data-ttu-id="1654c-183">在 Lync Server 2013 中修改默认 URL 筛选器</span><span class="sxs-lookup"><span data-stu-id="1654c-183">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)

  - [<span data-ttu-id="1654c-184">在 Lync Server 2013 中创建新的 URL 筛选器以处理即时消息对话中的超链接</span><span class="sxs-lookup"><span data-stu-id="1654c-184">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1654c-185">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1654c-185">See Also</span></span>


[<span data-ttu-id="1654c-186">在 Lync Server 2013 中管理 IM 和状态设置</span><span class="sxs-lookup"><span data-stu-id="1654c-186">Managing IM and presence settings in Lync Server 2013</span></span>](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

