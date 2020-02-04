---
title: Lync Server 2013：编辑网络配置图表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the network configuration diagram
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558643(v=OCS.15)
ms:contentKeyID: 51541469
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc199098d27364c3bc5f512a48d2e512c7c9d984
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-network-configuration-diagram-in-lync-server-2013"></a><span data-ttu-id="4d86a-102">在 Lync Server 2013 中编辑网络配置图</span><span class="sxs-lookup"><span data-stu-id="4d86a-102">Editing the network configuration diagram in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d86a-103">_**主题上次修改时间：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="4d86a-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="4d86a-104">设计器在 Lync Server 2013 中所执行的大部分工作都包含为网络图上的条目定义 IP 地址和完全限定域名（Fqdn）的条目。</span><span class="sxs-lookup"><span data-stu-id="4d86a-104">Most of the work that a designer does in the Lync Server 2013, Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="4d86a-105">在此页面上输入的信息将传递到 "规划工具" 中包含的报表和其他信息中。</span><span class="sxs-lookup"><span data-stu-id="4d86a-105">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

<span data-ttu-id="4d86a-106">![规划工具 - 网络图](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "规划工具 - 网络图")</span><span class="sxs-lookup"><span data-stu-id="4d86a-106">![Planning Tool Network diagram](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Planning Tool Network diagram")</span></span>

<span data-ttu-id="4d86a-107">规划工具使用 IP 地址和 Fqdn 的默认文本创建网络图。</span><span class="sxs-lookup"><span data-stu-id="4d86a-107">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="4d86a-108">编辑网络图和输入值：</span><span class="sxs-lookup"><span data-stu-id="4d86a-108">To edit the network diagram and input values:</span></span>

1.  <span data-ttu-id="4d86a-p102">选择起始网络段。例如，双击文本 **access1.contoso.com**。在打开的对话框中，键入服务器 access1.contoso.com 的实际 FQDN，并输入实际的 IP 地址以替换 131.107.155.3。</span><span class="sxs-lookup"><span data-stu-id="4d86a-p102">Choose a section of the network to begin working on. For example, double-click the text, **access1.contoso.com**. In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2.  <span data-ttu-id="4d86a-112">单击“**确定**”以保存条目。</span><span class="sxs-lookup"><span data-stu-id="4d86a-112">Click **OK** to save the entries.</span></span>

3.  <span data-ttu-id="4d86a-113">继续编辑 IP 地址和 FQDN，从而为硬件负载平衡器提供虚拟 IP 地址或者为池中服务器的域名系统 (DNS) 负载平衡提供服务器条目。</span><span class="sxs-lookup"><span data-stu-id="4d86a-113">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="4d86a-p103">规划工具的一个有用功能是可以递增地分配一系列 IP 地址和服务器主机名称，而不是要求设计师编辑池中的单台服务器。例如：</span><span class="sxs-lookup"><span data-stu-id="4d86a-p103">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool. For example:</span></span>

1.  <span data-ttu-id="4d86a-p104">双击池化的前端服务器。对话框打开后，选中“**是否要将这些 IP 地址和 FQDN 用作此群集中所有对等服务器的起点？**”。</span><span class="sxs-lookup"><span data-stu-id="4d86a-p104">Double-click the pooled Front End Servers. When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2.  <span data-ttu-id="4d86a-118">例如，第一台服务器的起始值是 fe0101.contoso.com，IP 地址是 192.168.21.122。</span><span class="sxs-lookup"><span data-stu-id="4d86a-118">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3.  <span data-ttu-id="4d86a-119">在“**前端服务器 FQDN**”中键入 **fe0.contoso.com**，在“**前端服务器 IP 地址**”中键入 **192.168.21.131**，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="4d86a-119">Type **fe0.contoso.com** in **Front End Server FQDN**, type **192.168.21.131** in **Front End Server IP address**, and then click **OK**.</span></span>

4.  <span data-ttu-id="4d86a-120">自动增量功能会将池中的所有服务器更新为 fe01 到 fe06，将所有 IP 地址更新为 192.168.21.131 到 192.168.21.136。</span><span class="sxs-lookup"><span data-stu-id="4d86a-120">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="4d86a-121">完成所有编辑后，执行以下步骤以保存拓扑：</span><span class="sxs-lookup"><span data-stu-id="4d86a-121">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="4d86a-122">若要保存规划工具设计，请单击 "**文件**"，然后单击 "**保存拓扑**" 或 "**将拓扑另存为**"。</span><span class="sxs-lookup"><span data-stu-id="4d86a-122">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="4d86a-123">如果出现“**将规划工具另存为**”对话框，请在“**文件名**”中键入文件的名称，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="4d86a-123">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4d86a-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d86a-124">See Also</span></span>


[<span data-ttu-id="4d86a-125">在 Lync Server 2013 中编辑设计</span><span class="sxs-lookup"><span data-stu-id="4d86a-125">Editing the design in Lync Server 2013</span></span>](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

