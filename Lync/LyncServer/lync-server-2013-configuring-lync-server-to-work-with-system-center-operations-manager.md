---
title: 将 Lync Server 配置为与 System Center Operations Manager 配合使用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server to work with System Center Operations Manager
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205188(v=OCS.15)
ms:contentKeyID: 48185179
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88eeae2c08020aacb142bbceb6c2637ae4d55b63
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-system-center-operations-manager"></a><span data-ttu-id="4381d-102">配置 Lync Server 2013 以使用 System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="4381d-102">Configuring Lync Server 2013 to work with System Center Operations Manager</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4381d-103">_**上次修改的主题：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="4381d-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="4381d-104">为了将 Microsoft Lync Server 2013 基础结构配置为与 System Center Operations Manager 配合使用，您必须执行以下三项操作：</span><span class="sxs-lookup"><span data-stu-id="4381d-104">In order to configure your Microsoft Lync Server 2013 infrastructure to work with System Center Operations Manager you must do three things:</span></span>

  - <span data-ttu-id="4381d-105">确定并配置您的主 System Center Operations Manager 管理服务器。</span><span class="sxs-lookup"><span data-stu-id="4381d-105">Identify and configure your primary System Center Operations Manager management server.</span></span> <span data-ttu-id="4381d-106">配置管理服务器包括安装 System Center Operations Manager 2012 或 System Center Operations Manager 2007 R2，以及使用 SQL Server 设置后端数据库。</span><span class="sxs-lookup"><span data-stu-id="4381d-106">Configuring the management server includes installing System Center Operations Manager 2012 or System Center Operations Manager 2007 R2, as well as setting up a back-end database using SQL Server.</span></span> <span data-ttu-id="4381d-107">您需要使用的 SQL Server 的实际版本取决于所使用的 System Center Operations Manager 的版本。</span><span class="sxs-lookup"><span data-stu-id="4381d-107">The actual version of SQL Server that you need to be use depends on the version of System Center Operations Manager you are using.</span></span> <span data-ttu-id="4381d-108">有关详细信息，请参阅[在 Lync server 2013 中配置主管理服务器](lync-server-2013-configuring-the-primary-management-server.md)。</span><span class="sxs-lookup"><span data-stu-id="4381d-108">For details, see [Configuring the primary management server in Lync Server 2013](lync-server-2013-configuring-the-primary-management-server.md).</span></span>

  - <span data-ttu-id="4381d-109">确定并配置要监视的 Lync Server 计算机。</span><span class="sxs-lookup"><span data-stu-id="4381d-109">Identify and configure the Lync Server computers that you want to monitor.</span></span> <span data-ttu-id="4381d-110">若要使用 System Center Operations Manager 监视 Lync Server 计算机，必须安装 System Center Operations Manager 代理文件，并将每台服务器配置为充当代理。</span><span class="sxs-lookup"><span data-stu-id="4381d-110">To monitor a Lync Server computer by using System Center Operations Manager you must install the System Center Operations Manager agent files, and configure each server to act as a proxy.</span></span>

  - <span data-ttu-id="4381d-111">确定并配置要充当 Lync Server*观察程序节点*的计算机。</span><span class="sxs-lookup"><span data-stu-id="4381d-111">Identify and configure the computers that you want to act as Lync Server *watcher nodes*.</span></span> <span data-ttu-id="4381d-112">观察程序节点是定期运行 Lync Server 合成事务的计算机，这些 cmdlet 是验证关键 Lync Server 组件（如登录到系统或 exchange 即时消息的能力）的 Windows PowerShell cmdlet。按预期工作。</span><span class="sxs-lookup"><span data-stu-id="4381d-112">Watcher nodes are computers that periodically run Lync Server synthetic transactions, which are Windows PowerShell cmdlets that verify that key Lync Server components, such as the ability to log on to the system or the ability to exchange instant messages are working as expected.</span></span>

<span data-ttu-id="4381d-113">本节中的主题包含执行其中每项任务的说明。</span><span class="sxs-lookup"><span data-stu-id="4381d-113">The topics in this section contain instructions for carrying out each of these tasks.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4381d-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="4381d-114">In This Section</span></span>

  - [<span data-ttu-id="4381d-115">在 Lync Server 2013 中配置主管理服务器</span><span class="sxs-lookup"><span data-stu-id="4381d-115">Configuring the primary management server in Lync Server 2013</span></span>](lync-server-2013-configuring-the-primary-management-server.md)

  - [<span data-ttu-id="4381d-116">安装 Lync Server 2013 管理包</span><span class="sxs-lookup"><span data-stu-id="4381d-116">Installing the Lync Server 2013 management packs</span></span>](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [<span data-ttu-id="4381d-117">配置将在 Lync Server 2013 中监视的 Lync Server 计算机</span><span class="sxs-lookup"><span data-stu-id="4381d-117">Configuring the Lync Server computers that will be monitored in Lync Server 2013</span></span>](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [<span data-ttu-id="4381d-118">在 Lync Server 2013 中安装和配置观察程序节点</span><span class="sxs-lookup"><span data-stu-id="4381d-118">Installing and configuring watcher nodes in Lync Server 2013</span></span>](lync-server-2013-installing-and-configuring-watcher-nodes.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

