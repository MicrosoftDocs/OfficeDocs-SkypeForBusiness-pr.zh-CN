---
title: Lync Server 2013：设备更新日志和文件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Update logs and files
ms:assetid: f7f822b8-0a62-4ff2-a4cb-1ab1ed7503eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994090(v=OCS.15)
ms:contentKeyID: 51804004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23dd149a16a89e3ffbb11f5553cda3ab6e4530b8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501469"
---
# <a name="device-update-logs-and-files-in-lync-server-2013"></a><span data-ttu-id="d652a-102">Lync Server 2013 中的设备更新日志和文件</span><span class="sxs-lookup"><span data-stu-id="d652a-102">Device Update logs and files in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d652a-103">_**上次修改的主题：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="d652a-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="d652a-104">设备更新日志包含可用于管理设备更新 Web 服务并对其进行故障排除的重要信息。</span><span class="sxs-lookup"><span data-stu-id="d652a-104">Device update logs contain important information that you can use to manage and troubleshoot the Device Update Web service.</span></span> <span data-ttu-id="d652a-105">您可以更改记录的内容，并删除不需要或不再需要的设备日志和更新。</span><span class="sxs-lookup"><span data-stu-id="d652a-105">You can change what is logged and remove device logs and updates that you don’t want or no longer need.</span></span> <span data-ttu-id="d652a-106">本节介绍如何使用 Lync Server 控制面板或 Lync Server 命令行管理程序修改日志记录设置、清除设备更新日志或删除服务器中的日志文件。</span><span class="sxs-lookup"><span data-stu-id="d652a-106">This section describes how you can use Lync Server Control Panel or Lync Server Management Shell to modify logging settings, clear the device update log, or remove log files from the server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d652a-107">有关设备更新日志文件的详细信息，请参阅 Lync Server 2010 TechNet 库中的 <A href="https://technet.microsoft.com/library/gg398250(v=ocs.14).aspx">日志文件类型和位置</A> 。</span><span class="sxs-lookup"><span data-stu-id="d652a-107">For details about device update log files, see <A href="https://technet.microsoft.com/library/gg398250(v=ocs.14).aspx">Log File Types and Locations</A> in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="d652a-108"> (请注意，与 lync Server 2010 一样，设备更新 Web 服务（如所有 Lync Phone Edition 组件）的工作方式与 lync server 2013 相同。 ) </span><span class="sxs-lookup"><span data-stu-id="d652a-108">(Note that the Device Update Web service, like all Lync Phone Edition components, works the same way with Lync Server 2013 as it does with Lync Server 2010.)</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d652a-109">本部分内容</span><span class="sxs-lookup"><span data-stu-id="d652a-109">In This Section</span></span>

  - [<span data-ttu-id="d652a-110">在 Lync Server 2013 中修改设备更新日志文件的设置</span><span class="sxs-lookup"><span data-stu-id="d652a-110">Modify settings for Device Update log files in Lync Server 2013</span></span>](lync-server-2013-modify-settings-for-device-update-log-files.md)

  - [<span data-ttu-id="d652a-111">在 Lync Server 2013 中删除设备更新日志文件</span><span class="sxs-lookup"><span data-stu-id="d652a-111">Delete Device Update log files in Lync Server 2013</span></span>](lync-server-2013-delete-device-update-log-files.md)

  - [<span data-ttu-id="d652a-112">删除与 Lync Server 2013 中与设备不关联的删除设备更新文件中未与设备关联的设备更新文件</span><span class="sxs-lookup"><span data-stu-id="d652a-112">Remove Device Update files not associated with a device in Remove Device Update files not associated with a device in Lync Server 2013</span></span>](lync-server-2013-remove-device-update-files-not-associated-with-a-device.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

