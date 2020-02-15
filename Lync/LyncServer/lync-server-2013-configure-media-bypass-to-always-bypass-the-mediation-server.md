---
title: Lync Server 2013：配置媒体旁路以始终绕过中介服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass to always bypass the Mediation Server
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48183819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 376ce5c00b4d326f283d1fde204d6c1bd17dd1de
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a><span data-ttu-id="7ae56-102">在 Lync Server 2013 中配置媒体旁路以始终绕过中介服务器</span><span class="sxs-lookup"><span data-stu-id="7ae56-102">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ae56-103">_**上次修改的主题：** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="7ae56-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7ae56-104">本主题假定，对于希望媒体绕过中介服务器的特定站点或特定服务，已为连接到对等方（Internet 电话服务提供商 (ITSP) 的公用电话交换网 (PSTN) 网关、IP-PBX 或会话边界控制器）的所有中继连接配置媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="7ae56-104">This topic assumes that you have already configured media bypass for any trunk connections to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider (ITSP)) for a specific site or service for which you want media to bypass the Mediation Server.</span></span><BR><span data-ttu-id="7ae56-105">如果启用了呼叫允许控制，则无法将媒体配置为始终绕过中介服务器。</span><span class="sxs-lookup"><span data-stu-id="7ae56-105">You cannot configure media to always bypass the Mediation Server while also enabling call admission control.</span></span> <span data-ttu-id="7ae56-106">这些设置不兼容，因此在 Lync Server 控制面板用户界面中的设置不兼容，因此是相互排斥的设置。</span><span class="sxs-lookup"><span data-stu-id="7ae56-106">These settings are incompatible and are therefore mutually exclusive settings in the Lync Server Control Panel user interface.</span></span>



</div>

<span data-ttu-id="7ae56-107">除了为与中介服务器的对等方相关联的各个中继连接启用媒体旁路功能外，还必须配置全局媒体旁路设置。</span><span class="sxs-lookup"><span data-stu-id="7ae56-107">In addition to enabling media bypass for individual trunk connections associated with a peer to the Mediation Server, you must also configure global settings for media bypass.</span></span> <span data-ttu-id="7ae56-108">如果您使用本主题中的步骤来配置媒体绕过的全局设置，则假设您在 Lync 终结点和任何对等方之间具有很好的连接，在中继连接上配置了媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="7ae56-108">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Lync endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>

<span data-ttu-id="7ae56-109">如果在 Lync Server 终结点和所有对等方之间没有足够的连接，且其各自的中继连接已启用媒体旁路，则必须将全局媒体旁路设置配置为使用网站和区域信息采用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="7ae56-109">If you do not have good connectivity between Lync Server endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="7ae56-110">这可以在媒体绕过中介服务器时，提供更为细化的控制。</span><span class="sxs-lookup"><span data-stu-id="7ae56-110">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="7ae56-111">为此，请按照 "[在 Lync server 2013 中配置媒体旁路全局设置" 中的步骤操作，以使用站点和区域信息](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)，并改为[在 lync Server 2013 中将子网与网络站点关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)。</span><span class="sxs-lookup"><span data-stu-id="7ae56-111">To do this, use the steps in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) and [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) instead.</span></span>

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="7ae56-112">在全局范围启用媒体旁路以始终绕过中介服务器</span><span class="sxs-lookup"><span data-stu-id="7ae56-112">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1.  <span data-ttu-id="7ae56-113">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="7ae56-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7ae56-114">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="7ae56-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="7ae56-115">在左侧导航栏中，单击“网络配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7ae56-115">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="7ae56-116">双击列表中的“全局”\*\*\*\* 配置。</span><span class="sxs-lookup"><span data-stu-id="7ae56-116">Double-click the **Global** configuration in the list.</span></span>

4.  <span data-ttu-id="7ae56-117">在“编辑全局设置”\*\*\*\* 页上，选中“启用媒体旁路”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="7ae56-117">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>

5.  <span data-ttu-id="7ae56-118">单击“始终绕过”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7ae56-118">Click **Always bypass**.</span></span>

6.  <span data-ttu-id="7ae56-119">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7ae56-119">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7ae56-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ae56-120">See Also</span></span>


[<span data-ttu-id="7ae56-121">在 Lync Server 2013 中配置媒体旁路</span><span class="sxs-lookup"><span data-stu-id="7ae56-121">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="7ae56-122">Lync Server 2013 中的全局媒体旁路选项</span><span class="sxs-lookup"><span data-stu-id="7ae56-122">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
[<span data-ttu-id="7ae56-123">Lync Server 2013 中的媒体旁路和中介服务器</span><span class="sxs-lookup"><span data-stu-id="7ae56-123">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  


[<span data-ttu-id="7ae56-124">在 Lync Server 2013 中规划媒体旁路</span><span class="sxs-lookup"><span data-stu-id="7ae56-124">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

