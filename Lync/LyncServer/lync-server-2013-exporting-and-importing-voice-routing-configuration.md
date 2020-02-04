---
title: Lync Server 2013：导出和导入语音路由配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exporting and importing voice routing configuration
ms:assetid: c9b78622-5725-43b0-9ee1-5b82b1e1c8eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398836(v=OCS.15)
ms:contentKeyID: 48185398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23ca3642204e4097f5345f879c704dcfcb4d8c9a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exporting-and-importing-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="dbedd-102">在 Lync Server 2013 中导出和导入语音路由配置</span><span class="sxs-lookup"><span data-stu-id="dbedd-102">Exporting and importing voice routing configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbedd-103">_**主题上次修改时间：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="dbedd-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="dbedd-104">如果要在不发布的情况下保存语音路由配置，请按照以下步骤使用 Lync Server 控制面板配置导出和导入命令来保存和检索你的语音路由配置的快照。</span><span class="sxs-lookup"><span data-stu-id="dbedd-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="dbedd-105">当您导入一个语音路由配置文件（vcfg），但同时在服务器上对 "语音路由配置" 进行了更改时，"Lync Server 控制面板" 中的 "**语音路由**" 组中的页面将显示 "语音路由" 有未提交的更改。</span><span class="sxs-lookup"><span data-stu-id="dbedd-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="dbedd-106">这些未提交的更改是两种需要调节的配置之间的差异。</span><span class="sxs-lookup"><span data-stu-id="dbedd-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="dbedd-107">如果你对 "<STRONG>语音路由</STRONG>" 组内任何页面上的设置进行了任何未提交的更改，则所做的更改将保存在导出的语音配置文件（vcfg）中。</span><span class="sxs-lookup"><span data-stu-id="dbedd-107">If you have made any uncommitted changes to the settings on any page within the <STRONG>Voice Routing</STRONG> group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="dbedd-108">这使你可以在发布更改之前，在多个 Lync Server 控制面板会话期间进行语音路由配置更改。</span><span class="sxs-lookup"><span data-stu-id="dbedd-108">This enables you to make voice routing configuration changes during multiple Lync Server Control Panel sessions before you publish the changes.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dbedd-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="dbedd-109">In This Section</span></span>

  - [<span data-ttu-id="dbedd-110">在 Lync Server 2013 中导出语音路由配置文件</span><span class="sxs-lookup"><span data-stu-id="dbedd-110">Export a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-export-a-voice-route-configuration-file.md)

  - [<span data-ttu-id="dbedd-111">在 Lync Server 2013 中导入语音路由配置文件</span><span class="sxs-lookup"><span data-stu-id="dbedd-111">Import a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-import-a-voice-route-configuration-file.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="dbedd-112">相关部分</span><span class="sxs-lookup"><span data-stu-id="dbedd-112">Related Sections</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

