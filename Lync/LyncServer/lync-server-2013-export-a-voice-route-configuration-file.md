---
title: Lync Server 2013：导出语音路由配置文件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export a voice route configuration file
ms:assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398081(v=OCS.15)
ms:contentKeyID: 48183248
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55ecc35d2724fa8c635b9d4099764c25e76874c9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-a-voice-route-configuration-file-in-lync-server-2013"></a><span data-ttu-id="04cff-102">在 Lync Server 2013 中导出语音路由配置文件</span><span class="sxs-lookup"><span data-stu-id="04cff-102">Export a voice route configuration file in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04cff-103">_**主题上次修改时间：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="04cff-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="04cff-104">如果要在不发布的情况下保存语音路由配置，请按照以下步骤使用 Lync Server 控制面板配置导出和导入命令来保存和检索你的语音路由配置的快照。</span><span class="sxs-lookup"><span data-stu-id="04cff-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="04cff-105">当您导入一个语音路由配置文件（vcfg），但同时在服务器上对 "语音路由配置" 进行了更改时，"Lync Server 控制面板" 中的 "**语音路由**" 组中的页面将显示 "语音路由" 有未提交的更改。</span><span class="sxs-lookup"><span data-stu-id="04cff-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="04cff-106">这些未提交的更改是两种需要调节的配置之间的差异。</span><span class="sxs-lookup"><span data-stu-id="04cff-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<span data-ttu-id="04cff-107">如果你对组内任何页面上的设置进行了任何未提交的更改，则所做的更改将保存在导出的语音配置文件（vcfg）中。</span><span class="sxs-lookup"><span data-stu-id="04cff-107">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="04cff-108">这使你可以在发布更改之前在多个会话期间进行语音路由配置更改。</span><span class="sxs-lookup"><span data-stu-id="04cff-108">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span>

<div>

## <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="04cff-109">导出语音路由配置</span><span class="sxs-lookup"><span data-stu-id="04cff-109">To export a voice routing configuration</span></span>

1.  <span data-ttu-id="04cff-110">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="04cff-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="04cff-111">有关详细信息，请参阅[在 Lync Server 2013 中委派设置权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="04cff-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="04cff-112">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="04cff-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="04cff-113">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="04cff-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="04cff-114">在左侧导航栏中，单击“语音路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="04cff-114">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="04cff-115">在“操作”\*\*\*\* 菜单上，单击“导出配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="04cff-115">On the **Actions** menu, click **Export configuration**.</span></span>

5.  <span data-ttu-id="04cff-116">指定位置和文件名，然后单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="04cff-116">Specify a location and file name, and then click **Save**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="04cff-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04cff-117">See Also</span></span>


[<span data-ttu-id="04cff-118">在 Lync Server 2013 中导入语音路由配置文件</span><span class="sxs-lookup"><span data-stu-id="04cff-118">Import a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-import-a-voice-route-configuration-file.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

