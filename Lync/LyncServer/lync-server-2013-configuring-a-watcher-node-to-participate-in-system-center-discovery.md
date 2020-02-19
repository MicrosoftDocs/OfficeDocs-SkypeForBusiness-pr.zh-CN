---
title: 配置观察程序节点以参与 System Center 发现
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to participate in System Center discovery
ms:assetid: 15c5dcfd-603b-47ea-af1b-8714c2ec08af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204704(v=OCS.15)
ms:contentKeyID: 48183500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b0d1fe5f2865f5c8797b2018ab8493bfb4d830c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42133755"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a><span data-ttu-id="caea4-102">在 Lync Server 2013 中配置观察程序节点以参与 System Center 发现</span><span class="sxs-lookup"><span data-stu-id="caea4-102">Configuring a watcher node in Lync Server 2013 to participate in System Center discovery</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="caea4-103">_**上次修改的主题：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="caea4-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="caea4-104">若要确保您的观察程序节点参与到 System Center Operations Manager 的发现过程，必须在已安装 System Center Operations Manager 控制台的计算机上完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="caea4-104">To make sure that your watcher node participates in the discovery process for System Center Operations Manager, you must complete the following procedure on a computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="caea4-105">在“管理”\*\*\*\* 选项卡上，单击“代理托管”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="caea4-105">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="caea4-p101">右键单击观察程序节点计算机的名称，然后单击“属性”\*\*\*\*。在“属性”\*\*\*\* 对话框的“安全性”\*\*\*\* 选项卡上，选择“允许此代理充当代理并发现其他计算机上的托管对象”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="caea4-p101">Right-click the name of the watcher node computer, and then click **Properties**. In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="caea4-108">在将观察程序节点配置为充当代理之后，重新启动观察程序节点计算机。</span><span class="sxs-lookup"><span data-stu-id="caea4-108">After configuring the watcher node to act as a proxy, reboot the watcher node computer.</span></span> <span data-ttu-id="caea4-109">重新启动计算机后，验证该计算机上的 Operations Manager 事件日志中未记录任何错误事件。</span><span class="sxs-lookup"><span data-stu-id="caea4-109">After the computer has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span> <span data-ttu-id="caea4-110">在计算机运行15分钟或更长时间后，请使用 Operations Manager 控制台验证 lync Server 计算机是否列在**lync**类别下。</span><span class="sxs-lookup"><span data-stu-id="caea4-110">After the computer has been running for 15 minutes or so, use the Operations Manager console to verify that your Lync Server computers are listed under the **Lync** category.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

