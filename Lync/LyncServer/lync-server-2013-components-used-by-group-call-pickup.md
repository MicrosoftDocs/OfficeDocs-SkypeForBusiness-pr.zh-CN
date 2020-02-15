---
title: Lync Server 2013：组间呼叫应答使用的组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Group Call Pickup
ms:assetid: 45db2f23-d486-4b20-a8cf-7b48a1f9fd3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945625(v=OCS.15)
ms:contentKeyID: 51541470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a05bf0b6a55eb3d8d3d322061947ac43f6295c63
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007922"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="e4090-102">由 Lync Server 2013 中的组呼叫应答使用的组件</span><span class="sxs-lookup"><span data-stu-id="e4090-102">Components used by Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4090-103">_**上次修改的主题：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="e4090-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="e4090-104">当您部署企业语音和呼叫寄存应用程序时，将自动部署组间呼叫应答。</span><span class="sxs-lookup"><span data-stu-id="e4090-104">Group Call Pickup is automatically deployed when you deploy Enterprise Voice and the Call Park application.</span></span> <span data-ttu-id="e4090-105">您可以通过将呼叫寄存通道表配置为指定为呼叫应答组号码的不同号码区域，然后将用户分配给呼叫应答组并为用户启用组内呼叫应答，从而启用组呼叫装货。</span><span class="sxs-lookup"><span data-stu-id="e4090-105">You enable Group Call Pickup by configuring the Call Park orbit table with separate ranges of numbers designated as call pickup group numbers, and then by assigning users to call pickup groups and enabling the users for Group Call Pickup.</span></span> <span data-ttu-id="e4090-106">以下 Lync Server 组件支持组呼叫装货：</span><span class="sxs-lookup"><span data-stu-id="e4090-106">The following Lync Server components support Group Call Pickup:</span></span>

  - <span data-ttu-id="e4090-107">**Application service**   Application service 提供用于部署、托管和管理统一通信应用程序（如呼叫寄存应用程序）的平台。</span><span class="sxs-lookup"><span data-stu-id="e4090-107">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="e4090-108">应用程序服务将自动安装在前端池和每个 Standard Edition 服务器上的每台前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="e4090-108">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="e4090-109">**呼叫寄存应用**   程序呼叫寄存应用程序是由应用程序服务托管的统一通信应用程序之一。</span><span class="sxs-lookup"><span data-stu-id="e4090-109">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="e4090-110">组呼叫应答基于呼叫寄存应用程序。</span><span class="sxs-lookup"><span data-stu-id="e4090-110">Group Call Pickup is based on the Call Park application.</span></span>

  - <span data-ttu-id="e4090-111">**Lync server 命令行**   管理程序使用 lync server 命令行管理程序管理组呼叫应答组。</span><span class="sxs-lookup"><span data-stu-id="e4090-111">**Lync Server Management Shell**   You use Lync Server Management Shell to manage Group Call Pickup groups.</span></span>

  - <span data-ttu-id="e4090-112">**SEFAUtil 资源工具包工具**   使用辅助扩展功能激活实用程序（SEFAUtil）将用户分配到呼叫应答组，并为用户启用或禁用呼叫应答。</span><span class="sxs-lookup"><span data-stu-id="e4090-112">**SEFAUtil resource kit tool**   You use the secondary extension feature activation utility (SEFAUtil) to assign users to a call pickup group and to enable or disable call pickup for users.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

