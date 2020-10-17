---
title: 为即时消息 (IM) 配置文件传输和 URL 筛选
description: 为即时消息 (IM) 配置文件传输和 URL 筛选。
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
ms.openlocfilehash: 92f11c3f3bb924c1d92361c2635bfb37e1f03175
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548348"
---
# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a><span data-ttu-id="255f8-103">在 Lync Server 2013 中配置即时消息 (IM) 的文件传输和 URL 筛选</span><span class="sxs-lookup"><span data-stu-id="255f8-103">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="255f8-104">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="255f8-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="255f8-105">智能 IM 筛选器工具可帮助保护您的 Lync Server 2013 部署不受最常见的病毒的传播，并降低用户体验的程度。</span><span class="sxs-lookup"><span data-stu-id="255f8-105">The Intelligent IM Filter tool helps protect your Lync Server 2013 deployment against the spread of the most common forms of viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="255f8-106">使用智能 IM 筛选器可以对筛选器进行配置，以阻止来自企业防火墙外部的未知终结点的未经请求或可能有害的即时消息。</span><span class="sxs-lookup"><span data-stu-id="255f8-106">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="255f8-107">通过指定用于确定要阻止的内容（例如，包含带有特定前缀的超链接的即时消息和具有特定扩展名的文件）的条件来配置筛选器。</span><span class="sxs-lookup"><span data-stu-id="255f8-107">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks with specific prefixes and files with specific extensions.</span></span>

<span data-ttu-id="255f8-108">智能 IM 筛选器提供下列功能：</span><span class="sxs-lookup"><span data-stu-id="255f8-108">Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="255f8-109">增强的 URL 筛选功能。</span><span class="sxs-lookup"><span data-stu-id="255f8-109">Enhanced URL filtering.</span></span>

  - <span data-ttu-id="255f8-110">增强的文件传输筛选功能。</span><span class="sxs-lookup"><span data-stu-id="255f8-110">Enhanced file transfer filtering.</span></span>

<span data-ttu-id="255f8-111">配置智能 IM 筛选器包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="255f8-111">Configuring Intelligent IM Filter includes the following:</span></span>

  - <span data-ttu-id="255f8-112">配置 URL 筛选功能。</span><span class="sxs-lookup"><span data-stu-id="255f8-112">Configuring URL filtering.</span></span>

  - <span data-ttu-id="255f8-113">配置文件传输筛选功能。</span><span class="sxs-lookup"><span data-stu-id="255f8-113">Configuring file transfer filtering.</span></span>

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a><span data-ttu-id="255f8-114">如何将筛选选项应用于即时消息</span><span class="sxs-lookup"><span data-stu-id="255f8-114">How Filtering Options Are Applied to Instant Messages</span></span>

<span data-ttu-id="255f8-115">在部署智能 IM 邮件筛选器工具之前，您需要了解在将邮件从一个 Lync Server 2013 服务器路由到另一个时如何应用筛选选项。</span><span class="sxs-lookup"><span data-stu-id="255f8-115">Before you deploy the Intelligent IM Message Filter tool, you need to understand how filtering options are applied as messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="255f8-116">应用这些筛选选项的方式是一致的，不管服务器是位于单个组织中还是跨越多个组织。</span><span class="sxs-lookup"><span data-stu-id="255f8-116">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="255f8-117">在消息中插入自定义通知和警告文本以及在服务器之间发送这些消息的方式也是一致的。</span><span class="sxs-lookup"><span data-stu-id="255f8-117">This consistency applies to the way that the customized notice and warning texts are inserted into messages and sent across servers.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="255f8-118">即时消息筛选器使得处理消息中的 URL 所需的 CPU 资源量增加。</span><span class="sxs-lookup"><span data-stu-id="255f8-118">The instant message filter increases the amount of CPU resources required to process URLs in a message.</span></span> <span data-ttu-id="255f8-119">这一增长的 CPU 需求也会影响 Lync Server 的性能。</span><span class="sxs-lookup"><span data-stu-id="255f8-119">This increase in CPU demand also affects the performance of Lync Server.</span></span>



</div>

<span data-ttu-id="255f8-120">通过使用 "Lync Server 控制面板" 中的 " **IM 和状态**" 组中的 " **URL 筛选器**" 页，可以阻止部分或全部超链接或配置警告。</span><span class="sxs-lookup"><span data-stu-id="255f8-120">By using the **URL Filter** page in the **IM and Presence** group in Lync Server Control Panel, you can block some or all hyperlinks or configure a warning.</span></span> <span data-ttu-id="255f8-121">选择“超链接前缀”\*\*\*\* 选项“发送警告消息”\*\*\*\* 后，警告将插入到包含超链接的即时消息的开头。</span><span class="sxs-lookup"><span data-stu-id="255f8-121">The warning is inserted at the beginning of an instant message that contains a hyperlink when you choose the **Hyperlink prefix** option **Send warning message**.</span></span>

<span data-ttu-id="255f8-122">当即时消息从一台服务器传输到另一台服务器时，将适用下面的一般准则：</span><span class="sxs-lookup"><span data-stu-id="255f8-122">When an instant message travels from one server to another, the following general guidelines apply:</span></span>

  - <span data-ttu-id="255f8-p105">如果服务器阻止即时消息（因为选中了“URL 筛选器”\*\*\*\* 页面上的“阻止带文件扩展名的 URL”\*\*\*\* 复选框，或因为选择了“超链接前缀”\*\*\*\* 选项“阻止超链接”\*\*\*\*），客户端将收到一条错误消息。后续服务器将不会接收此即时消息。</span><span class="sxs-lookup"><span data-stu-id="255f8-p105">If a server blocks an instant message (because you selected the **Block URLs with file extension** check box on the **URL Filter** page or because you chose the **Hyperlink prefix** option **Block hyperlinks**), an error message is returned to the client. Subsequent servers do not receive this instant message.</span></span>

  - <span data-ttu-id="255f8-p106">如果服务器 (Server1) 将警告添加到包含活动超链接的即时消息，则接收此即时消息的后续服务器 (Server2) 仍然可以基于该即时消息中存在的这个活动超链接来采取不同的操作，并阻止该即时消息或添加警告。如果 Server2 配置为仅为此 URL 添加警告，则以前由 Server1 添加的警告将被删除，在 Server2 上配置的警告将添加到该即时消息的开头。</span><span class="sxs-lookup"><span data-stu-id="255f8-p106">If a server (Server1) adds a warning to an instant message that contains an active hyperlink, a subsequent server (Server2) that receives this instant message can still take a different action based on this active hyperlink present in the instant message and block the instant message or add a warning. If Server2 is configured only to add a warning for this URL, the earlier warning added by Server1 is removed, and the warning configured on Server2 is added to the beginning of the instant message.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="255f8-127">如果在混合环境中运行 Lync Server 2013，则使用智能 IM 筛选器应用程序所需的 Live 通信服务器2005（SP1）是最低版本。</span><span class="sxs-lookup"><span data-stu-id="255f8-127">If you are running Lync Server 2013 in a mixed environment, Live Communications Server 2005 with SP1 is the minimum version required to use the Intelligent IM Filter application.</span></span> <span data-ttu-id="255f8-128">不带 SP1 的 Live Communications Server 2005 不支持智能 IM 筛选器。</span><span class="sxs-lookup"><span data-stu-id="255f8-128">The Intelligent IM Filter is not supported on Live Communications Server 2005 without SP1.</span></span>



</div>

<div>

## <a name="url-filtering"></a><span data-ttu-id="255f8-129">URL 筛选</span><span class="sxs-lookup"><span data-stu-id="255f8-129">URL Filtering</span></span>

<span data-ttu-id="255f8-p108">将根据超链接前缀来筛选 URL。下面是有效前缀示例：</span><span class="sxs-lookup"><span data-stu-id="255f8-p108">URLs are filtered according to their hyperlink prefix. The following examples are valid prefixes:</span></span>

  - <span data-ttu-id="255f8-132">www \* 。</span><span class="sxs-lookup"><span data-stu-id="255f8-132">www\*.</span></span>

  - <span data-ttu-id="255f8-133">ftp.</span><span class="sxs-lookup"><span data-stu-id="255f8-133">ftp.</span></span>

  - <span data-ttu-id="255f8-134">http.sys</span><span class="sxs-lookup"><span data-stu-id="255f8-134">http:</span></span>

<span data-ttu-id="255f8-p109">如果您没有将即时消息筛选器配置为执行任何 URL 筛选，则包含在即时消息中的所有 URL 未经修改就可通过服务器。如果将即时消息筛选器配置为执行 URL 筛选，则将根据“编辑 URL 筛选器”\*\*\*\* 或“新建 URL 筛选器”\*\*\*\* 对话框中选择的选项来筛选即时消息中的 URL。</span><span class="sxs-lookup"><span data-stu-id="255f8-p109">If you do not configure the instant message filter to perform any URL filtering, all URLs contained in instant messages are passed unmodified through the server. If you configure the instant message filter to perform URL filtering, URLs in instant messages are filtered according to the options that you select in the **Edit URL Filter** or **New URL Filter** dialog box.</span></span>

  - <span data-ttu-id="255f8-137">**启用 URL 筛选器**    此选项为全局部署或您选择的网站启用 URL 筛选。</span><span class="sxs-lookup"><span data-stu-id="255f8-137">**Enable URL filter**   This option enables URL filtering for the global deployment or for the site that you select.</span></span>

  - <span data-ttu-id="255f8-138">**使用文件扩展名**     阻止 url即时消息筛选器阻止任何活动 intranet 或 Internet URL，其中包含在 "**编辑文件筛选器**" 对话框中的 "**要阻止的文件类型扩展**" 下列出的扩展名的文件。</span><span class="sxs-lookup"><span data-stu-id="255f8-138">**Block URLs with file extension**   The instant message filter blocks any active intranet or Internet URL that contains a file with an extension listed under **File type extensions to block** in the **Edit File Filter** dialog box.</span></span> <span data-ttu-id="255f8-139">当阻止某个 URL 时，会向发件人显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="255f8-139">When a URL is blocked, an error message is displayed to the sender.</span></span> <span data-ttu-id="255f8-140">如果选择此选项，则对于在 " **文件类型扩展**" 下定义的任何文件扩展名，此选项优先于所有其他筛选选项。</span><span class="sxs-lookup"><span data-stu-id="255f8-140">When selected, this option takes precedence over all other filtering options for any file extensions defined under **File type extensions to block**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="255f8-p111">文件扩展名筛选仅限于标准文件名。筛选对于嵌入在其他名称中的文件扩展名不起作用。</span><span class="sxs-lookup"><span data-stu-id="255f8-p111">Filtering of file extensions is limited to standard file names. Filtering may not work with file extensions embedded in other names.</span></span>

    
    </div>

<span data-ttu-id="255f8-143">要配置即时消息对话中处理超链接的方式，请选择“超链接前缀”\*\*\*\* 下的以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="255f8-143">To configure how hyperlinks are handled in instant message conversations, select one of the following options under **Hyperlink prefix**:</span></span>

  - <span data-ttu-id="255f8-144">不**筛选**    邮件中的 Url 通过服务器发送。</span><span class="sxs-lookup"><span data-stu-id="255f8-144">**Do not filter**   URLs in messages are sent through the server.</span></span> <span data-ttu-id="255f8-145">选择此选项时，将显示 " **允许" 消息** 框。</span><span class="sxs-lookup"><span data-stu-id="255f8-145">When you choose this option, the **Allow message** box appears.</span></span> <span data-ttu-id="255f8-146">在 " **允许消息** " 框中，指定要在包含超链接的每个即时消息的开头插入的通知。</span><span class="sxs-lookup"><span data-stu-id="255f8-146">In the **Allow message** box, specify the notice that you want to insert at the beginning of each instant message containing hyperlinks.</span></span> <span data-ttu-id="255f8-147">此通知包含的字符数不超过65535。</span><span class="sxs-lookup"><span data-stu-id="255f8-147">This notice can consist of no more than 65535 characters.</span></span>

  - <span data-ttu-id="255f8-148">**阻止超链接**    传递包含活动超链接的即时消息将被 Lync Server 阻止，并向发件人显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="255f8-148">**Block hyperlinks**   Delivery of instant messages containing active hyperlinks is blocked by Lync Server, and an error message is displayed to the sender.</span></span>

  - <span data-ttu-id="255f8-149">**发送警告消息**    Lync Server 允许在即时消息中使用活动超链接，但它包含警告。</span><span class="sxs-lookup"><span data-stu-id="255f8-149">**Send warning message**   Lync Server permits active hyperlinks in instant messages, but it includes a warning.</span></span> <span data-ttu-id="255f8-150">选择此选项后，将显示“警告消息”\*\*\*\* 框。</span><span class="sxs-lookup"><span data-stu-id="255f8-150">When you choose this option, the **Warning message** box appears.</span></span> <span data-ttu-id="255f8-151">在“警告消息”\*\*\*\* 框中，必须键入希望在包含有效超链接的即时消息中包含的警告。</span><span class="sxs-lookup"><span data-stu-id="255f8-151">In the **Warning message** box, you must type the warning that you want to include with instant messages containing valid hyperlinks.</span></span> <span data-ttu-id="255f8-152">例如，此警告可以声明单击未知链接的潜在危险，或者引用您所在组织的相关策略和要求。</span><span class="sxs-lookup"><span data-stu-id="255f8-152">For example, this warning might state the potential dangers of clicking an unknown link, or it might refer to your organization’s relevant policies and requirements.</span></span> <span data-ttu-id="255f8-153">此警告最多可包含 65535 个字符。</span><span class="sxs-lookup"><span data-stu-id="255f8-153">The warning can be no more than 65535 characters.</span></span>

<span data-ttu-id="255f8-154">如果选择“阻止超链接”\*\*\*\* 或“发送警告消息”\*\*\*\*，则下列选项可用：</span><span class="sxs-lookup"><span data-stu-id="255f8-154">If you select **Block hyperlinks** or **Send warning message**, the following options are available:</span></span>

  - <span data-ttu-id="255f8-155">**排除本地 intranet 超链接**    即时消息筛选器仅阻止 Internet Url。</span><span class="sxs-lookup"><span data-stu-id="255f8-155">**Exclude local intranet hyperlinks**   The instant message filter blocks only Internet URLs.</span></span> <span data-ttu-id="255f8-156">Intranet 内的位置 Url 通过服务器未修改。</span><span class="sxs-lookup"><span data-stu-id="255f8-156">URLs for locations within your intranet are passed unmodified through the server.</span></span> <span data-ttu-id="255f8-157">但是，运行 Lync Server 的各个服务器传递的 intranet Url 取决于将哪些类型的本地网站视为其 intranet 区域的一部分。</span><span class="sxs-lookup"><span data-stu-id="255f8-157">However, the intranet URLs that individual servers running Lync Server pass depend on which types of local websites are considered part of their intranet zone.</span></span> <span data-ttu-id="255f8-158">若要检查服务器的 intranet 区域设置，请参阅 [修改 Lync server 2013 中的默认 URL 筛选器](lync-server-2013-modify-the-default-url-filter.md)中的 "在 Internet Explorer 中配置 intranet 设置" 过程。</span><span class="sxs-lookup"><span data-stu-id="255f8-158">To check a server’s intranet zone settings, see the “To configure your intranet settings in Internet Explorer” procedure in [Modify the default URL filter in Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md).</span></span>

  - <span data-ttu-id="255f8-159">**筛选这些超链接前缀**    若要选择要阻止的前缀，请单击 "**选择**"，然后在 "**选择超链接前缀**" 中，将前缀添加到 "**超链接前缀**" 列表中。</span><span class="sxs-lookup"><span data-stu-id="255f8-159">**Filter these hyperlink prefixes**   To choose which prefixes you want to block, click **Select**, and then, in **Select Hyperlink Prefix**, add the prefixes to the **Hyperlink prefixes** list.</span></span>
    
    <span data-ttu-id="255f8-160">除了 **href** 之外，所有前缀都必须以句点或冒号结尾，或以星号后面跟一个句点结尾。</span><span class="sxs-lookup"><span data-stu-id="255f8-160">All prefixes except **href** must end with a period or a colon, or an asterisk followed by a period.</span></span> <span data-ttu-id="255f8-161">有效前缀可以包含一组有效 URL 字符（星号 () 除外）中的任何字符 \* 。</span><span class="sxs-lookup"><span data-stu-id="255f8-161">Valid prefixes can contain any characters in the set of valid URL characters except the asterisk (\*).</span></span> <span data-ttu-id="255f8-162">有效的 URL 字符集为： \# \* +/0123456789 = @ABCDEFGHIJKLMNOPQRSTUVWXYZ ^ \_ \` ABCDEFGHIJKLMNOPQRSTUVWXYZ | ~</span><span class="sxs-lookup"><span data-stu-id="255f8-162">The set of valid URL characters is: \#\*+/0123456789=@ABCDEFGHIJKLMNOPQRSTUVWXYZ^\_\` abcdefghijklmnopqrstuvwxyz|~</span></span>

</div>

<div>

## <a name="file-transfer-filtering"></a><span data-ttu-id="255f8-163">文件传输筛选</span><span class="sxs-lookup"><span data-stu-id="255f8-163">File Transfer Filtering</span></span>

<span data-ttu-id="255f8-p116">文件传输筛选既影响即时消息，又影响会议。对于会议来说，这些设置影响 Office Live Meeting 2007 客户端中的讲义功能和多媒体播放功能。</span><span class="sxs-lookup"><span data-stu-id="255f8-p116">Filter transfer filtering affects both instant messages and conferences. For conferences, these settings affect the handout feature in the Office Live Meeting 2007 client and multimedia playback features.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="255f8-166">Lync Server 还提供文件传输设置选项。</span><span class="sxs-lookup"><span data-stu-id="255f8-166">Lync Server also offers file transfer setting options.</span></span> <span data-ttu-id="255f8-167">除了在 Lync Server 中提供的客户端控件之外，还提供了此服务器端选项。</span><span class="sxs-lookup"><span data-stu-id="255f8-167">This server-side option is offered in addition to the client-side controls available in Lync Server.</span></span>



</div>

<span data-ttu-id="255f8-p118">可以在即时消息对话过程中、使用 Office Live Meeting 2007 客户端的讲义功能以及多媒体播放功能时，针对所有文件类型筛选文件传输。可以设置以下选项来控制文件传输：</span><span class="sxs-lookup"><span data-stu-id="255f8-p118">You can filter file transfers during instant message conversations, when you are using the handout feature in the Office Live Meeting 2007 client, and for multimedia playback features for all file types. You can set the following options to control file transfers:</span></span>

  - <span data-ttu-id="255f8-170">**启用文件筛选器**    此选项为全局部署或您选择的网站启用文件筛选。</span><span class="sxs-lookup"><span data-stu-id="255f8-170">**Enable file filter**   This option enables file filtering for the global deployment or for the site that you select.</span></span>
    
    <span data-ttu-id="255f8-171">启用文件筛选器后，可以在“文件传输”\*\*\*\* 中选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="255f8-171">When you enable the file filter, you can choose one of the following options in **File transfer**:</span></span>
    
      - <span data-ttu-id="255f8-172">**阻止特定的文件类型**    通过指定要阻止的文件扩展名的列表，指定由服务器筛选的文件传输请求。</span><span class="sxs-lookup"><span data-stu-id="255f8-172">**Block specific file types**   You specify which file transfer requests are filtered by the server by specifying a list of file extensions to block.</span></span> <span data-ttu-id="255f8-173">列表中的条目可包含所有标准字符，但不能包含通配符 (\*) 。</span><span class="sxs-lookup"><span data-stu-id="255f8-173">Entries in the list can contain all standard characters, but not the wildcard character (\*).</span></span> <span data-ttu-id="255f8-174">在 Office Live Meeting 2007 客户端中，讲义功能处于启用状态，但不能上载或下载任何具有此扩展名的文件。</span><span class="sxs-lookup"><span data-stu-id="255f8-174">In the Office Live Meeting 2007 client the handout feature is enabled, but any file with this extension cannot be uploaded or downloaded.</span></span> <span data-ttu-id="255f8-175">如果在 " **Url 筛选器**" 选项卡上列出的 url 筛选器的设置中选中 "**阻止带文件扩展名的 url** " 复选框，则 url 筛选器将使用此相同列表来阻止包含这些文件扩展名的活动超链接。</span><span class="sxs-lookup"><span data-stu-id="255f8-175">If you select the **Block URLs with file extension** check box on the settings for a URL filter listed on the **URL Filter** tab, the URL filter uses this same list to block active hyperlinks that contain any of these file extensions.</span></span> <span data-ttu-id="255f8-176">若要选择要阻止的文件类型，请单击 " **选择**"，然后在 " **选择文件类型**" 中，将文件类型扩展名添加到 " **选定的文件类型扩展名** " 列表中。</span><span class="sxs-lookup"><span data-stu-id="255f8-176">To choose which file types you want to block, click **Select**, and then, in **Select File Type**, add the file type extensions to the **Selected file type extensions** list.</span></span>
    
      - <span data-ttu-id="255f8-177">**阻止所有**    服务器将丢弃包含文件传输请求的所有即时消息，并向请求的发件人返回一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="255f8-177">**Block All**   The server drops all instant messages that contain file transfer requests and returns an error message to the sender of the request.</span></span> <span data-ttu-id="255f8-178">Office Live Meeting 2007 客户端中的讲义功能被禁用。</span><span class="sxs-lookup"><span data-stu-id="255f8-178">The handout feature in the Office Live Meeting 2007 client is disabled.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="255f8-p121">文件扩展名筛选仅限于标准文件名。筛选对于嵌入在其他名称中的文件扩展名不起作用。</span><span class="sxs-lookup"><span data-stu-id="255f8-p121">Filtering of file extensions is limited to standard file names. Filtering may not work with file extensions embedded in other names.</span></span>



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="255f8-181">本节内容</span><span class="sxs-lookup"><span data-stu-id="255f8-181">In This Section</span></span>

  - [<span data-ttu-id="255f8-182">在 Lync Server 2013 中修改默认文件传输筛选器</span><span class="sxs-lookup"><span data-stu-id="255f8-182">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [<span data-ttu-id="255f8-183">在 Lync Server 2013 for a 特定网站中创建新的文件传输筛选器</span><span class="sxs-lookup"><span data-stu-id="255f8-183">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [<span data-ttu-id="255f8-184">在 Lync Server 2013 中修改默认 URL 筛选器</span><span class="sxs-lookup"><span data-stu-id="255f8-184">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)

  - [<span data-ttu-id="255f8-185">在 Lync Server 2013 中创建一个新的 URL 筛选器，以处理 IM 对话中的超链接</span><span class="sxs-lookup"><span data-stu-id="255f8-185">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="255f8-186">另请参阅</span><span class="sxs-lookup"><span data-stu-id="255f8-186">See Also</span></span>


[<span data-ttu-id="255f8-187">在 Lync Server 2013 中管理 IM 和状态设置</span><span class="sxs-lookup"><span data-stu-id="255f8-187">Managing IM and presence settings in Lync Server 2013</span></span>](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

