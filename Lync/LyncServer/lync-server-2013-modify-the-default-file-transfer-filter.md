---
title: 'Lync Server 2013: 修改默认文件传输筛选器'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the default file transfer filter
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521017(v=OCS.15)
ms:contentKeyID: 48184584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 475f6e9b599af9ba6db80fdb174d3b38e5df6b00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a><span data-ttu-id="3a7e6-102">在 Lync Server 2013 中修改默认文件传输筛选器</span><span class="sxs-lookup"><span data-stu-id="3a7e6-102">Modify the default file transfer filter in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a7e6-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3a7e6-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3a7e6-104">Lync Server 2013 提供了全局文件传输筛选器, 可在 Lync Server 2013 部署中的以下与文件相关的活动期间阻止特定类型的文件:</span><span class="sxs-lookup"><span data-stu-id="3a7e6-104">Lync Server 2013 provides a global file transfer filter that blocks specific types of files during the following file-related activities within your Lync Server 2013 deployment:</span></span>

  - <span data-ttu-id="3a7e6-105">即时消息 (IM) 对话期间的文件传输请求</span><span class="sxs-lookup"><span data-stu-id="3a7e6-105">File transfer requests during instant messaging (IM) conversations</span></span>

  - <span data-ttu-id="3a7e6-106">使用 Office Live Meeting 2007 客户端中的讲义功能时的文件上载和下载</span><span class="sxs-lookup"><span data-stu-id="3a7e6-106">File uploads and downloads while using the handout feature in the Office Live Meeting 2007 client</span></span>

  - <span data-ttu-id="3a7e6-107">在会议期间播放多媒体</span><span class="sxs-lookup"><span data-stu-id="3a7e6-107">Multimedia playback during conferences</span></span>

<span data-ttu-id="3a7e6-108">根据要阻止或允许的文件类型, 您可以使用 Lync Server "控制面板" 修改全局筛选器。</span><span class="sxs-lookup"><span data-stu-id="3a7e6-108">Depending on the types of files you want to block or allow, you can use Lync Server Control Panel to modify the global filter.</span></span> <span data-ttu-id="3a7e6-109">有关文件传输筛选的详细信息, 请参阅[在 Lync Server 2013 中为即时消息 (IM) 配置文件传输和 URL 筛选](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)。</span><span class="sxs-lookup"><span data-stu-id="3a7e6-109">For details about file transfer filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a><span data-ttu-id="3a7e6-110">修改默认文件传输筛选器</span><span class="sxs-lookup"><span data-stu-id="3a7e6-110">To modify the default file transfer filter</span></span>

1.  <span data-ttu-id="3a7e6-111">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="3a7e6-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3a7e6-112">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="3a7e6-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3a7e6-113">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="3a7e6-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3a7e6-114">在左侧导航栏中, 单击 " **IM 和状态**", 然后单击 "**文件筛选器**"。</span><span class="sxs-lookup"><span data-stu-id="3a7e6-114">In the left navigation bar, click **IM and Presence** and then click **File Filter**.</span></span>

4.  <span data-ttu-id="3a7e6-115">在 "**文件筛选器**" 页面上, 双击 "**全局**" 筛选器。</span><span class="sxs-lookup"><span data-stu-id="3a7e6-115">On the **File Filter** page, double-click the **Global** filter.</span></span>

5.  <span data-ttu-id="3a7e6-116">在 "**编辑文件筛选器**" 中, 选中 "**启用文件筛选器**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="3a7e6-116">In **Edit File Filter**, select the **Enable file filter** check box.</span></span>

6.  <span data-ttu-id="3a7e6-117">在 "**文件传送**" 下拉列表框中, 单击 "**阻止全部**" 或 "**阻止特定文件类型**"。</span><span class="sxs-lookup"><span data-stu-id="3a7e6-117">In the **File transfer** drop-down list box, click **Block All** or **Block specific file types**.</span></span>

7.  <span data-ttu-id="3a7e6-118">如果单击 "**全部阻止**", 请跳到步骤9。</span><span class="sxs-lookup"><span data-stu-id="3a7e6-118">If you clicked **Block All**, skip to step 9.</span></span>

8.  <span data-ttu-id="3a7e6-119">如果单击了 "**阻止特定文件类型**", 请执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="3a7e6-119">If you clicked **Block specific file types**, do the following:</span></span>
    
    1.  <span data-ttu-id="3a7e6-120">单击 "**选择**" 以修改要阻止的文件类型扩展名的默认列表。</span><span class="sxs-lookup"><span data-stu-id="3a7e6-120">Click **Select** to modify the default list of file type extensions that you want to block.</span></span>
    
    2.  <span data-ttu-id="3a7e6-121">在 "**选择文件类型**" 中, 从 "**文件类型扩展**" 下的类别中添加或删除扩展名, 选择要阻止或允许的文件类型。</span><span class="sxs-lookup"><span data-stu-id="3a7e6-121">In **Select File Type**, select the file types that you want to block or allow by adding or removing their extensions from the categories under **File type extensions**.</span></span>
    
    3.  <span data-ttu-id="3a7e6-122">如果看不到要阻止的文件类型的扩展名, 请在文本框中的 "**向列表添加文件类型扩展名**" 下键入扩展名, 然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="3a7e6-122">If you do not see the extension for a file type that you want to block, type the extension in the text box under **Add file type extensions to the list**, and then click **Add**.</span></span>
    
    4.  <span data-ttu-id="3a7e6-123">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="3a7e6-123">Click **OK**.</span></span>

9.  <span data-ttu-id="3a7e6-124">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="3a7e6-124">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3a7e6-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a7e6-125">See Also</span></span>


[<span data-ttu-id="3a7e6-126">在 Lync Server 2013 中为即时消息 (IM) 配置文件传输和 URL 筛选</span><span class="sxs-lookup"><span data-stu-id="3a7e6-126">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="3a7e6-127">在 Lync Server 2013 中为特定网站创建新的文件传输筛选器</span><span class="sxs-lookup"><span data-stu-id="3a7e6-127">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="3a7e6-128">在 Lync Server 2013 中创建新的 URL 筛选器以处理即时消息对话中的超链接</span><span class="sxs-lookup"><span data-stu-id="3a7e6-128">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[<span data-ttu-id="3a7e6-129">在 Lync Server 2013 中修改默认 URL 筛选器</span><span class="sxs-lookup"><span data-stu-id="3a7e6-129">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

