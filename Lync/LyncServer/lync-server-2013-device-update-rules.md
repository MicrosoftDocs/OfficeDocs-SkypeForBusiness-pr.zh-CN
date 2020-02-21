---
title: Lync Server 2013：设备更新规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Update rules
ms:assetid: a2f7e293-3342-4566-9605-410cb95f3b3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994062(v=OCS.15)
ms:contentKeyID: 51803973
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1ec593c264a1630274e83e8a7de1d193b8e5cbf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197917"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="device-update-rules-in-lync-server-2013"></a><span data-ttu-id="4a34c-102">Lync Server 2013 中的设备更新规则</span><span class="sxs-lookup"><span data-stu-id="4a34c-102">Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a34c-103">_**上次修改的主题：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="4a34c-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="4a34c-104">Microsoft 会定期为 Lync Phone Edition 发布一组新的设备固件更新。</span><span class="sxs-lookup"><span data-stu-id="4a34c-104">Periodically, Microsoft releases a new set of device firmware updates for Lync Phone Edition.</span></span> <span data-ttu-id="4a34c-105">*设备更新规则*将固件更新与硬件设备（电话和其他运行 Lync Phone Edition 的设备）相关联。</span><span class="sxs-lookup"><span data-stu-id="4a34c-105">*Device update rules* associate firmware updates with hardware devices—phones and other devices running Lync Phone Edition.</span></span>

<span data-ttu-id="4a34c-106">若要获取最新的设备更新规则集，请转到 Microsoft 网站上的 "帮助和支持" 页，并搜索 "Phone Edition"。</span><span class="sxs-lookup"><span data-stu-id="4a34c-106">To get the latest set of device update rules, go to the Help and Support page on the Microsoft website, and search for "Phone Edition."</span></span> <span data-ttu-id="4a34c-107">下载更新程序包，并将文件解压缩到要上载更新的计算机上的某个文件夹中。</span><span class="sxs-lookup"><span data-stu-id="4a34c-107">Download the update package, and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="4a34c-108">提取文件后，导入在提取的中找到的设备更新规则。CAB 文件（其名称为为 ucupdates-r2.）。</span><span class="sxs-lookup"><span data-stu-id="4a34c-108">After the files have been extracted, import the device update rules found in the extracted .CAB file (which have the name UCUpdates.cab).</span></span> <span data-ttu-id="4a34c-109">然后，使用 Lync Server 控制面板或 Windows PowerShell cmdlet 查看和管理组织设备的这些规则。</span><span class="sxs-lookup"><span data-stu-id="4a34c-109">Then, use the Lync Server Control Panel or Windows PowerShell cmdlets to view and manage these rules for your organization’s devices.</span></span>

<span data-ttu-id="4a34c-110">以下主题介绍如何导入、查看和管理设备更新规则。</span><span class="sxs-lookup"><span data-stu-id="4a34c-110">The following topics tell you how to import, view, and manage device update rules.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4a34c-111">本部分内容</span><span class="sxs-lookup"><span data-stu-id="4a34c-111">In This Section</span></span>

  - [<span data-ttu-id="4a34c-112">在 Lync Server 2013 中查看有关设备更新规则的信息</span><span class="sxs-lookup"><span data-stu-id="4a34c-112">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)

  - [<span data-ttu-id="4a34c-113">在 Lync Server 2013 中导入设备更新规则</span><span class="sxs-lookup"><span data-stu-id="4a34c-113">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)

  - [<span data-ttu-id="4a34c-114">在 Lync Server 2013 中审批设备更新规则</span><span class="sxs-lookup"><span data-stu-id="4a34c-114">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)

  - [<span data-ttu-id="4a34c-115">在 Lync Server 2013 中删除设备更新规则</span><span class="sxs-lookup"><span data-stu-id="4a34c-115">Remove a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-remove-a-device-update-rule.md)

  - [<span data-ttu-id="4a34c-116">在 Lync Server 2013 中重置设备更新规则</span><span class="sxs-lookup"><span data-stu-id="4a34c-116">Reset a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-reset-a-device-update-rule.md)

  - [<span data-ttu-id="4a34c-117">在 Lync Server 2013 中还原设备更新规则</span><span class="sxs-lookup"><span data-stu-id="4a34c-117">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

