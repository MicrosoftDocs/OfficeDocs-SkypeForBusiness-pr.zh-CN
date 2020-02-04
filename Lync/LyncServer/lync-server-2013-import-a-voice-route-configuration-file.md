---
title: Lync Server 2013：导入语音路由配置文件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import a voice route configuration file
ms:assetid: 4bac05e5-ed8b-4f10-96b0-b8a65ff356ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398301(v=OCS.15)
ms:contentKeyID: 48184049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f00b1eb3406c1a3d425727820da8686f96f1dae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763856"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-a-voice-route-configuration-file-in-lync-server-2013"></a><span data-ttu-id="8c379-102">在 Lync Server 2013 中导入语音路由配置文件</span><span class="sxs-lookup"><span data-stu-id="8c379-102">Import a voice route configuration file in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c379-103">_**主题上次修改时间：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8c379-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8c379-104">如果要在不发布的情况下保存语音路由配置，请按照以下步骤使用 Lync Server 控制面板配置导出和导入命令来保存和检索你的语音路由配置的快照。</span><span class="sxs-lookup"><span data-stu-id="8c379-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="8c379-105">当您导入一个语音路由配置文件（vcfg），但同时在服务器上对 "语音路由配置" 进行了更改时，"Lync Server 控制面板" 中的 "**语音路由**" 组中的页面将显示 "语音路由" 有未提交的更改。</span><span class="sxs-lookup"><span data-stu-id="8c379-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="8c379-106">这些未提交的更改是两种需要调节的配置之间的差异。</span><span class="sxs-lookup"><span data-stu-id="8c379-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<span data-ttu-id="8c379-107">如果你对组内任何页面上的设置进行了任何未提交的更改，则所做的更改将保存在导出的语音配置文件（vcfg）中。</span><span class="sxs-lookup"><span data-stu-id="8c379-107">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="8c379-108">这使你可以在发布更改之前在多个会话期间进行语音路由配置更改。</span><span class="sxs-lookup"><span data-stu-id="8c379-108">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span>

<div>

## <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="8c379-109">导入语音路由配置</span><span class="sxs-lookup"><span data-stu-id="8c379-109">To import a voice routing configuration</span></span>

1.  <span data-ttu-id="8c379-110">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="8c379-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="8c379-111">有关详细信息，请参阅[在 Lync Server 2013 中委派设置权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="8c379-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="8c379-112">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="8c379-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8c379-113">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="8c379-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8c379-114">在左侧导航栏中，单击“语音路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8c379-114">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="8c379-115">在“操作”\*\*\*\* 菜单上，单击“导入配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8c379-115">On the **Actions** menu, click **Import configuration**.</span></span>

5.  <span data-ttu-id="8c379-116">找到要导入的配置文件，然后单击“打开”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8c379-116">Find the configuration file you want to import and then click **Open**.</span></span>

6.  <span data-ttu-id="8c379-117">单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8c379-117">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8c379-118">任何时候导入语音配置文件，都必须运行“全部提交”<STRONG></STRONG>命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="8c379-118">Whenever you import a voice configuration file, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="8c379-119">有关详细信息，请参阅操作文档中的<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中的 "发布待处理的语音路由配置更改"</A> 。</span><span class="sxs-lookup"><span data-stu-id="8c379-119">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8c379-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c379-120">See Also</span></span>


[<span data-ttu-id="8c379-121">在 Lync Server 2013 中导出语音路由配置文件</span><span class="sxs-lookup"><span data-stu-id="8c379-121">Export a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-export-a-voice-route-configuration-file.md)  
[<span data-ttu-id="8c379-122">将挂起的更改发布到 Lync Server 2013 中的语音路由配置</span><span class="sxs-lookup"><span data-stu-id="8c379-122">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

