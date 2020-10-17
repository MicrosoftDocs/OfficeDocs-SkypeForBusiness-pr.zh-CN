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
ms.openlocfilehash: 26f9d13ee352ba344684deafe3d7a380beb7c8bb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528099"
---
# <a name="import-a-voice-route-configuration-file-in-lync-server-2013"></a><span data-ttu-id="a8d1b-102">在 Lync Server 2013 中导入语音路由配置文件</span><span class="sxs-lookup"><span data-stu-id="a8d1b-102">Import a voice route configuration file in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8d1b-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a8d1b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a8d1b-104">如果要在不发布的情况下保存语音路由配置，请按照以下步骤使用 Lync Server 控制面板的 "导出" 和 "导入" 命令来保存和检索语音路由配置的快照。</span><span class="sxs-lookup"><span data-stu-id="a8d1b-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="a8d1b-105">在将语音路由配置文件导入 () ，但同时对服务器上的语音路由配置进行了更改，则 vcfg Server 控制面板中的 " **语音路由** " 组中的页面将指示语音路由存在未提交的更改。</span><span class="sxs-lookup"><span data-stu-id="a8d1b-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="a8d1b-106">这些未提交的更改是两种需要调节的配置之间的差异。</span><span class="sxs-lookup"><span data-stu-id="a8d1b-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<span data-ttu-id="a8d1b-107">如果对组中任何页面上的设置进行了任何未提交的更改，则所做的更改会保存在导出的语音配置文件中 (。 vcfg) 。</span><span class="sxs-lookup"><span data-stu-id="a8d1b-107">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="a8d1b-108">这使您可以在发布更改之前在多个会话期间进行语音路由配置更改。</span><span class="sxs-lookup"><span data-stu-id="a8d1b-108">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span>

<div>

## <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="a8d1b-109">导入语音路由配置</span><span class="sxs-lookup"><span data-stu-id="a8d1b-109">To import a voice routing configuration</span></span>

1.  <span data-ttu-id="a8d1b-110">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="a8d1b-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="a8d1b-111">有关详细信息，请参阅 [Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="a8d1b-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="a8d1b-112">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="a8d1b-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a8d1b-113">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="a8d1b-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a8d1b-114">在左侧导航栏中，单击“语音路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a8d1b-114">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="a8d1b-115">在“操作”\*\*\*\* 菜单上，单击“导入配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a8d1b-115">On the **Actions** menu, click **Import configuration**.</span></span>

5.  <span data-ttu-id="a8d1b-116">找到要导入的配置文件，然后单击“打开”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a8d1b-116">Find the configuration file you want to import and then click **Open**.</span></span>

6.  <span data-ttu-id="a8d1b-117">单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a8d1b-117">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a8d1b-118">任何时候导入语音配置文件，都必须运行“全部提交”<STRONG></STRONG>命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="a8d1b-118">Whenever you import a voice configuration file, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="a8d1b-119">有关详细信息，请参阅操作文档中的在 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中发布待处理的语音路由配置的更改</A> 。</span><span class="sxs-lookup"><span data-stu-id="a8d1b-119">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a8d1b-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8d1b-120">See Also</span></span>


[<span data-ttu-id="a8d1b-121">在 Lync Server 2013 中导出语音路由配置文件</span><span class="sxs-lookup"><span data-stu-id="a8d1b-121">Export a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-export-a-voice-route-configuration-file.md)  
[<span data-ttu-id="a8d1b-122">在 Lync Server 2013 中发布对语音路由配置所做的挂起更改</span><span class="sxs-lookup"><span data-stu-id="a8d1b-122">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

