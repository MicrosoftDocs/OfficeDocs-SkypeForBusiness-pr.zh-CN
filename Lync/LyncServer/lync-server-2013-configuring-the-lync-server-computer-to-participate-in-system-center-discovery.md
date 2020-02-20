---
title: 将 Lync Server 计算机配置为参与 System Center 发现
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computer to participate in System Center discovery
ms:assetid: 2f9c9cb0-3120-4571-9cd2-657c2123fe21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204776(v=OCS.15)
ms:contentKeyID: 48183731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b8e95ead01c89f33346a66a8212245c2350894f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154264"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a><span data-ttu-id="d087f-102">将 Lync Server 2013 计算机配置为参与 System Center 发现</span><span class="sxs-lookup"><span data-stu-id="d087f-102">Configuring the Lync Server 2013 computer to participate in System Center discovery</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d087f-103">_**上次修改的主题：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="d087f-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="d087f-104">若要确保新的 Lync Server 代理参与了 System Center Operations Manager 的发现过程，必须在安装了 System Center Operations Manager 控制台的每台计算机上完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="d087f-104">To make sure that your new Lync Server agent participates in discovery process for System Center Operations Manager, you must complete the following procedure on each computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="d087f-105">在“管理”\*\*\*\* 选项卡上，单击“代理托管”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d087f-105">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="d087f-p101">右键单击计算机的名称，然后单击“属性”\*\*\*\*。在“属性”\*\*\*\* 对话框中的“安全性”\*\*\*\* 选项卡上，选择“允许此代理充当代理并发现其他计算机上的托管对象”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d087f-p101">Right-click the name of the computer, and then click **Properties**. In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="d087f-p102">完成步骤 2 后，重新启动健康代理服务。（重新启动该服务将“强制”发现新计算机。如果您没有重新启动该服务，则 System Center Operations Manager 可能需要长达 4 小时的时间才能发现新计算机。）在重新启动该服务后，验证该计算机上的 Operations Manager 事件日志中是否记录了任何错误事件。</span><span class="sxs-lookup"><span data-stu-id="d087f-p102">After completing step 2, reboot the Health Agent service. (Rebooting the service will “force” discovery of the new machine. If you do not reboot the service, it could take as long as 4 hours before the new machine is discovered by System Center Operations Manager.). After the service has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

