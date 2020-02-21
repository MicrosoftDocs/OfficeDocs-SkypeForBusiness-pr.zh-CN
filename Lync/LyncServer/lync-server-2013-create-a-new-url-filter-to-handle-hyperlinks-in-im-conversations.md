---
title: 创建新的 URL 筛选器以处理 IM 对话中的超链接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new URL filter to handle hyperlinks in IM conversations
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182590(v=OCS.15)
ms:contentKeyID: 48185426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 889ba5f0582c96fc43445d28bcb669150cfff961
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204638"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a><span data-ttu-id="956b7-102">在 Lync Server 2013 中创建一个新的 URL 筛选器，以处理 IM 对话中的超链接</span><span class="sxs-lookup"><span data-stu-id="956b7-102">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="956b7-103">_**上次修改的主题：** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="956b7-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="956b7-104">除了修改全局 URL 筛选器之外，还可以为 Lync Server 2013 部署中的各个网站配置自定义 URL 筛选器。</span><span class="sxs-lookup"><span data-stu-id="956b7-104">In addition to modifying the global URL filter, you can configure custom URL filters for individual sites within your Lync Server 2013 deployment.</span></span> <span data-ttu-id="956b7-105">有关 URL 筛选的详细信息，请参阅[Lync Server 2013 中的为即时消息（IM）配置文件传输和 URL 筛选](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)。</span><span class="sxs-lookup"><span data-stu-id="956b7-105">For details about URL filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-create-a-new-url-filter"></a><span data-ttu-id="956b7-106">创建新的 URL 筛选器</span><span class="sxs-lookup"><span data-stu-id="956b7-106">To create a new URL filter</span></span>

1.  <span data-ttu-id="956b7-107">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="956b7-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="956b7-108">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="956b7-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="956b7-109">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="956b7-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="956b7-110">在左侧导航栏中，单击“IM 和状态”\*\*\*\*，然后单击“URL 筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="956b7-110">In the left navigation bar, click **IM and Presence**, and then click **URL Filter**.</span></span>

4.  <span data-ttu-id="956b7-111">在“URL 筛选器”\*\*\*\* 页上，单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="956b7-111">On the **URL Filter** page, click **New**.</span></span>

5.  <span data-ttu-id="956b7-112">在“选择站点”\*\*\*\* 中，单击要为其创建 URL 筛选器的站点，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="956b7-112">In **Select a Site**, click the site for which you want to create the URL filter, and then click **OK**.</span></span>

6.  <span data-ttu-id="956b7-113">在“新建 URL 筛选器”\*\*\*\* 对话框中，选中“启用 URL 筛选器”\*\*\*\* 复选框以启用站点的 URL 筛选。</span><span class="sxs-lookup"><span data-stu-id="956b7-113">In the **New URL Filter** dialog box, select the **Enable URL Filter** check box to enable URL filtering for the site.</span></span>

7.  <span data-ttu-id="956b7-114">要阻止包含具有“编辑文件筛选器”\*\*\*\* 中“要阻止的文件类型扩展名”\*\*\*\* 下所列扩展名的文件的任何活动 URL，请选中“阻止带文件扩展名的 URL”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="956b7-114">To block any active URL that contains a file with an extension listed under **File type extensions to block** in **Edit File Filter**, select the **Block URLs with file extension** check box.</span></span>

8.  <span data-ttu-id="956b7-115">在“超链接前缀”\*\*\*\* 下拉列表框中，单击与希望的即时消息对话中的 URL 处理方式对应的选项。</span><span class="sxs-lookup"><span data-stu-id="956b7-115">In the **Hyperlink prefix** drop-down list box, click the option that corresponds to how you want to handle URLs in instant message conversations.</span></span>
    
    <span data-ttu-id="956b7-116">当用户发送允许发送的超链接时，将通过“允许消息”\*\*\*\* 框向其发送警告消息。</span><span class="sxs-lookup"><span data-stu-id="956b7-116">The **Allow message** box enables a warning message to be sent to the user when sending hyperlinks that are allowed to be sent.</span></span>

9.  <span data-ttu-id="956b7-117">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="956b7-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="956b7-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="956b7-118">See Also</span></span>


[<span data-ttu-id="956b7-119">在 Lync Server 2013 中为即时消息（IM）配置文件传输和 URL 筛选</span><span class="sxs-lookup"><span data-stu-id="956b7-119">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="956b7-120">在 Lync Server 2013 for a 特定网站中创建新的文件传输筛选器</span><span class="sxs-lookup"><span data-stu-id="956b7-120">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="956b7-121">在 Lync Server 2013 中修改默认文件传输筛选器</span><span class="sxs-lookup"><span data-stu-id="956b7-121">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[<span data-ttu-id="956b7-122">在 Lync Server 2013 中修改默认 URL 筛选器</span><span class="sxs-lookup"><span data-stu-id="956b7-122">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

