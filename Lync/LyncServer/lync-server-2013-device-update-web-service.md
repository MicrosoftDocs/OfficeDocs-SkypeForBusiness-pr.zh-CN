---
title: Lync Server 2013：设备更新 Web 服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device Update Web service
ms:assetid: 036f473d-a131-431f-8051-76ccadc5cfba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994015(v=OCS.15)
ms:contentKeyID: 51803921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d2b258b7a088f0deeee029be482f1ed63bc00ef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-update-web-service-in-lync-server-2013"></a><span data-ttu-id="fe1b6-102">Lync Server 2013 中的设备更新 Web 服务</span><span class="sxs-lookup"><span data-stu-id="fe1b6-102">Device Update Web service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe1b6-103">_**主题上次修改时间:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="fe1b6-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="fe1b6-104">Lync 服务器包括 "设备更新" Web 服务, 该服务将作为 Web 服务角色的一部分自动安装。</span><span class="sxs-lookup"><span data-stu-id="fe1b6-104">Lync Server includes the Device Update Web service, which is automatically installed as part of the Web Services role.</span></span> <span data-ttu-id="fe1b6-105">此服务允许你从 Microsoft 下载更新, 测试这些更新, 然后将更新部署到你的组织中的 IP 电话。</span><span class="sxs-lookup"><span data-stu-id="fe1b6-105">This service lets you download updates from Microsoft, test them, and then deploy the updates to IP phones in your organization.</span></span> <span data-ttu-id="fe1b6-106">你还可以使用 "设备更新" Web 服务将设备回退到以前的软件版本。</span><span class="sxs-lookup"><span data-stu-id="fe1b6-106">You can also use Device Update Web service to roll back devices to previous software versions.</span></span>

<span data-ttu-id="fe1b6-107">本部分提供了有关如何使用设备更新日志管理设备更新 Web 服务和部署更新的详细信息, 规则 (Lync Phone Edition 使用*规则*将固件版本更新与硬件设备相关联) 和配置设置。</span><span class="sxs-lookup"><span data-stu-id="fe1b6-107">This section provides details about how to manage the Device Update Web service and deployed updates by using device update logs, rules (Lync Phone Edition uses *rules* to associate firmware version updates with hardware devices), and configuration settings.</span></span>

<span data-ttu-id="fe1b6-108">有关设备更新 Web 服务流程和功能的详细信息, 请参阅在 Lync Server 2010 中[更新设备](http://technet.microsoft.com/en-us/library/gg412864\(v=ocs.14\).aspx)TechNet 库。</span><span class="sxs-lookup"><span data-stu-id="fe1b6-108">For details about the Device Update Web service process and features, see [Updating Devices](http://technet.microsoft.com/en-us/library/gg412864\(v=ocs.14\).aspx) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="fe1b6-109">(请注意, 设备更新 Web 服务 (如所有 Lync Phone 版组件) 的工作方式与 lync server 2013 相同, 与 Lync Server 2010 相同。)</span><span class="sxs-lookup"><span data-stu-id="fe1b6-109">(Note that the Device Update Web service, like all Lync Phone Edition components, works the same way with Lync Server 2013 as it does with Lync Server 2010.)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fe1b6-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="fe1b6-110">In This Section</span></span>

  - [<span data-ttu-id="fe1b6-111">Lync Server 2013 中的设备更新日志和文件</span><span class="sxs-lookup"><span data-stu-id="fe1b6-111">Device Update logs and files in Lync Server 2013</span></span>](lync-server-2013-device-update-logs-and-files.md)

  - [<span data-ttu-id="fe1b6-112">Lync Server 2013 中的设备更新规则</span><span class="sxs-lookup"><span data-stu-id="fe1b6-112">Device Update rules in Lync Server 2013</span></span>](lync-server-2013-device-update-rules.md)

  - [<span data-ttu-id="fe1b6-113">Lync Server 2013 中的设备更新配置设置</span><span class="sxs-lookup"><span data-stu-id="fe1b6-113">Device Update configuration settings in Lync Server 2013</span></span>](lync-server-2013-device-update-configuration-settings.md)

  - [<span data-ttu-id="fe1b6-114">在 Lync Server 2013 中查看设备的软件更新</span><span class="sxs-lookup"><span data-stu-id="fe1b6-114">View software updates for devices in Lync Server 2013</span></span>](lync-server-2013-view-software-updates-for-devices-in-your-organization.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fe1b6-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe1b6-115">See Also</span></span>


<span data-ttu-id="fe1b6-116">[用于管理设备和排除设备故障的工具和服务](http://technet.microsoft.com/en-us/library/gg425800\(v=ocs.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="fe1b6-116">[Tools and Services for Managing and Troubleshooting Devices](http://technet.microsoft.com/en-us/library/gg425800\(v=ocs.14\).aspx)</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

