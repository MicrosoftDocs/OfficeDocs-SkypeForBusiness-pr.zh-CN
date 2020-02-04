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
ms.openlocfilehash: 4912497f1c8481d44b02a0213e01a0e8908ebfa2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-update-rules-in-lync-server-2013"></a><span data-ttu-id="ff48a-102">Lync Server 2013 中的设备更新规则</span><span class="sxs-lookup"><span data-stu-id="ff48a-102">Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff48a-103">_**主题上次修改时间：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="ff48a-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="ff48a-104">Microsoft 会定期为 Lync Phone 版本发布一组新的设备固件更新。</span><span class="sxs-lookup"><span data-stu-id="ff48a-104">Periodically, Microsoft releases a new set of device firmware updates for Lync Phone Edition.</span></span> <span data-ttu-id="ff48a-105">*设备更新规则*将固件更新与硬件设备（电话和其他运行 Lync Phone 版本的设备）相关联。</span><span class="sxs-lookup"><span data-stu-id="ff48a-105">*Device update rules* associate firmware updates with hardware devices—phones and other devices running Lync Phone Edition.</span></span>

<span data-ttu-id="ff48a-106">若要获取最新的设备更新规则集，请转到 Microsoft 网站上的 "帮助和支持" 页，然后搜索 "电话版本"。</span><span class="sxs-lookup"><span data-stu-id="ff48a-106">To get the latest set of device update rules, go to the Help and Support page on the Microsoft website, and search for "Phone Edition."</span></span> <span data-ttu-id="ff48a-107">下载更新程序包，并将文件解压缩到要上载更新的计算机上的某个文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ff48a-107">Download the update package, and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="ff48a-108">提取文件后，导入在解压缩中找到的设备更新规则。CAB 文件（其名称为 UCUpdates）。</span><span class="sxs-lookup"><span data-stu-id="ff48a-108">After the files have been extracted, import the device update rules found in the extracted .CAB file (which have the name UCUpdates.cab).</span></span> <span data-ttu-id="ff48a-109">然后，使用 Lync Server 控制面板或 Windows PowerShell cmdlet 查看和管理组织设备的这些规则。</span><span class="sxs-lookup"><span data-stu-id="ff48a-109">Then, use the Lync Server Control Panel or Windows PowerShell cmdlets to view and manage these rules for your organization’s devices.</span></span>

<span data-ttu-id="ff48a-110">以下主题将告诉你如何导入、查看和管理设备更新规则。</span><span class="sxs-lookup"><span data-stu-id="ff48a-110">The following topics tell you how to import, view, and manage device update rules.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ff48a-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="ff48a-111">In This Section</span></span>

  - [<span data-ttu-id="ff48a-112">查看有关 Lync Server 2013 中的设备更新规则的信息</span><span class="sxs-lookup"><span data-stu-id="ff48a-112">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)

  - [<span data-ttu-id="ff48a-113">在 Lync Server 2013 中导入设备更新规则</span><span class="sxs-lookup"><span data-stu-id="ff48a-113">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)

  - [<span data-ttu-id="ff48a-114">在 Lync Server 2013 中批准设备更新规则</span><span class="sxs-lookup"><span data-stu-id="ff48a-114">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)

  - [<span data-ttu-id="ff48a-115">在 Lync Server 2013 中删除设备更新规则</span><span class="sxs-lookup"><span data-stu-id="ff48a-115">Remove a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-remove-a-device-update-rule.md)

  - [<span data-ttu-id="ff48a-116">重置 Lync Server 2013 中的设备更新规则</span><span class="sxs-lookup"><span data-stu-id="ff48a-116">Reset a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-reset-a-device-update-rule.md)

  - [<span data-ttu-id="ff48a-117">在 Lync Server 2013 中还原设备更新规则</span><span class="sxs-lookup"><span data-stu-id="ff48a-117">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

