---
title: 在 Skype for Business Server 2015 中编辑拓扑
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: 完成初始访谈问题后，可以编辑站点的 FQDN (和 IP) 的完全限定域名。 要执行此操作，请在“全局拓扑”页上双击要编辑的站点。
ms.openlocfilehash: ba18070b21494028d31b4167ab92a622794c5e51
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834882"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a><span data-ttu-id="7bed7-104">在 Skype for Business Server 2015 中编辑拓扑</span><span class="sxs-lookup"><span data-stu-id="7bed7-104">Edit the topology in Skype for Business Server 2015</span></span>

<span data-ttu-id="7bed7-105">完成初始访谈问题后，可以编辑站点的 FQDN (和 IP) 的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="7bed7-105">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site.</span></span> <span data-ttu-id="7bed7-106">要执行此操作，请在 **“全局拓扑”** 页上双击要编辑的站点。</span><span class="sxs-lookup"><span data-stu-id="7bed7-106">To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="7bed7-107">规划工具显示所选站点的站点拓扑。</span><span class="sxs-lookup"><span data-stu-id="7bed7-107">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="7bed7-108">在站点页面的底部有四个选项卡：</span><span class="sxs-lookup"><span data-stu-id="7bed7-108">At the bottom of the site page are four tabs:</span></span>

![规划工具站点拓扑](../../media/Planning_Tool_Site_Topology.png)

- <span data-ttu-id="7bed7-110">站点拓扑 - 当前显示的页面，其中按建议直观概述了拓扑。</span><span class="sxs-lookup"><span data-stu-id="7bed7-110">Site Topology - The currently displayed page with a visual overview of the topology as recommended.</span></span>

- <span data-ttu-id="7bed7-111">边缘网络图 - "边缘网络图"页是设计人员在规划工具中执行大部分工作的位置。</span><span class="sxs-lookup"><span data-stu-id="7bed7-111">Edge Network Diagram - The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="7bed7-112">该图显示了建议的 Skype for Business Server 2015 拓扑的网络配置，以及服务器、池以及硬件和域名系统 (DNS) 负载平衡器中的 IP 地址和 FQDN 的可编辑条目。</span><span class="sxs-lookup"><span data-stu-id="7bed7-112">The diagram displays the network configuration for a recommended Skype for Business Server 2015 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

- <span data-ttu-id="7bed7-113">边缘管理员报告 - 边缘管理员报告共包含四个报告：</span><span class="sxs-lookup"><span data-stu-id="7bed7-113">Edge Admin Report - The Edge Admin Report contains a total of four reports:</span></span>

     ![边缘管理员报告页](../../media/Planning_Tool_Summary_Report.png)

  - <span data-ttu-id="7bed7-115">摘要报告 - 边缘网络配置的常规设置报告。</span><span class="sxs-lookup"><span data-stu-id="7bed7-115">Summary Report - A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="7bed7-116">如果将"边缘网络图"页上的值编辑为将在实际部署中使用的拓扑 TCP/IP 和 FQDN 值，则此处将表示这些地址和名称。</span><span class="sxs-lookup"><span data-stu-id="7bed7-116">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="7bed7-117">否则，将显示默认文本。</span><span class="sxs-lookup"><span data-stu-id="7bed7-117">Otherwise, the default text will appear.</span></span>

  - <span data-ttu-id="7bed7-118">证书报告 - 证书报告将列出拓扑所需的证书的主题名称和主题备用名称。</span><span class="sxs-lookup"><span data-stu-id="7bed7-118">Certificate Report - The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>

  - <span data-ttu-id="7bed7-119">防火墙报告 - 防火墙报告列出了在基础结构中配置外围防火墙所必需的信息。</span><span class="sxs-lookup"><span data-stu-id="7bed7-119">Firewall Report - The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="7bed7-120">这包括默认或 (的 IP 地址) 、服务器角色、源 IP 和端口、目标 IP 和端口、传输协议、应用程序协议和相关注释。</span><span class="sxs-lookup"><span data-stu-id="7bed7-120">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>

  - <span data-ttu-id="7bed7-121">DNS 报告 - DNS 报告列出了您必须创建的 DNS 条目的相关信息。</span><span class="sxs-lookup"><span data-stu-id="7bed7-121">DNS Report - The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="7bed7-122">其中包括相应操作所需的记录类型、FQDN、IP 地址和备注。</span><span class="sxs-lookup"><span data-stu-id="7bed7-122">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

- <span data-ttu-id="7bed7-123">网站摘要 - 网站摘要概述了通过回答初始访谈式问题或填写设计网站中的值而 **做出的选择**。</span><span class="sxs-lookup"><span data-stu-id="7bed7-123">Site Summary - The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="7bed7-124">还显示容量信息。</span><span class="sxs-lookup"><span data-stu-id="7bed7-124">Capacity information is also presented.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7bed7-125">“站点摘要”页上的信息可针对每个设计进行自定义，可能不包含此处详细介绍的所有内容或信息。</span><span class="sxs-lookup"><span data-stu-id="7bed7-125">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

## <a name="edit-the-network-configuration-diagram"></a><span data-ttu-id="7bed7-126">编辑网络配置图</span><span class="sxs-lookup"><span data-stu-id="7bed7-126">Edit the network configuration diagram</span></span>
<span data-ttu-id="7bed7-127"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="7bed7-127"><a name="Edit_Network_diagram"> </a></span></span>

<span data-ttu-id="7bed7-128">设计人员在 Skype for Business Server 2015 规划工具中执行大部分工作，包括为网络图上的条目定义 IP 地址和完全限定域名 (FQDN) 条目。</span><span class="sxs-lookup"><span data-stu-id="7bed7-128">Most of the work that a designer does in the Skype for Business Server 2015 Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="7bed7-129">在此页面上输入的信息将进入报告以及规划工具中包含的其他信息。</span><span class="sxs-lookup"><span data-stu-id="7bed7-129">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

![规划工具网络图](../../media/Planning_Tool_Network_Diagram.png)

<span data-ttu-id="7bed7-131">规划工具为 IP 地址和 FQDN 创建包含默认文本的网络图。</span><span class="sxs-lookup"><span data-stu-id="7bed7-131">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="7bed7-132">编辑网络图和输入值：</span><span class="sxs-lookup"><span data-stu-id="7bed7-132">To edit the network diagram and input values:</span></span>

1. <span data-ttu-id="7bed7-133">选择起始网络段。</span><span class="sxs-lookup"><span data-stu-id="7bed7-133">Choose a section of the network to begin working on.</span></span> <span data-ttu-id="7bed7-134">例如，双击文本 **，access1.contoso.com。**</span><span class="sxs-lookup"><span data-stu-id="7bed7-134">For example, double-click the text, **access1.contoso.com**.</span></span> <span data-ttu-id="7bed7-135">在打开的对话框中，键入服务器 access1.contoso.com 的实际 FQDN 和实际的 IP 地址，以替换 131.107.155.3。</span><span class="sxs-lookup"><span data-stu-id="7bed7-135">In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2. <span data-ttu-id="7bed7-136">单击 **“确定”** 以保存条目。</span><span class="sxs-lookup"><span data-stu-id="7bed7-136">Click **OK** to save the entries.</span></span>

3. <span data-ttu-id="7bed7-137">继续编辑 IP 地址和 FQDN，从而为硬件负载平衡器提供虚拟 IP 地址或者为池中服务器的域名系统 (DNS) 负载平衡提供服务器条目。</span><span class="sxs-lookup"><span data-stu-id="7bed7-137">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="7bed7-p111">规划工具的一个有用功能是可以递增地分配一系列 IP 地址和服务器主机名称，而不是要求设计师编辑池中的单台服务器。例如：</span><span class="sxs-lookup"><span data-stu-id="7bed7-p111">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool. For example:</span></span>

1. <span data-ttu-id="7bed7-140">双击池化的前端服务器。</span><span class="sxs-lookup"><span data-stu-id="7bed7-140">Double-click the pooled Front End Servers.</span></span> <span data-ttu-id="7bed7-141">对话框打开后，选中 **“是否要将 IP 和 FQDN 用作此群集中所有等效服务器的起始点?”**。</span><span class="sxs-lookup"><span data-stu-id="7bed7-141">When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2. <span data-ttu-id="7bed7-142">例如，第一台服务器的起始值为 fe0101.contoso.com IP 地址为 192.168.21.122。</span><span class="sxs-lookup"><span data-stu-id="7bed7-142">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3. <span data-ttu-id="7bed7-143">在前端fe0.contoso.com **FQDN** 中键入内容，在前端服务器 **IP** 地址中键入 192.168.21.131，然后单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="7bed7-143">Type fe0.contoso.com in **Front End Server FQDN**, type 192.168.21.131 in **Front End Server IP address**, and then click **OK**.</span></span>

4. <span data-ttu-id="7bed7-144">自动递增功能将池中的所有服务器更新为 fe01 到 fe06，将所有 IP 地址从 192.168.21.131 更新为 136。</span><span class="sxs-lookup"><span data-stu-id="7bed7-144">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="7bed7-145">完成所有编辑后，通过完成以下步骤保存拓扑：</span><span class="sxs-lookup"><span data-stu-id="7bed7-145">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="7bed7-146">若要保存规划工具设计，**请单击"文件**"，然后单击"保存 **拓扑**"或"另存 **为"。**</span><span class="sxs-lookup"><span data-stu-id="7bed7-146">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="7bed7-147">如果出现 **“将规划工具另存为”** 对话框，请在 **“文件名”** 中键入文件的名称，然后单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="7bed7-147">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="7bed7-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7bed7-148">See also</span></span>
<span data-ttu-id="7bed7-149"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="7bed7-149"><a name="Edit_Network_diagram"> </a></span></span>

[<span data-ttu-id="7bed7-150">编辑设计</span><span class="sxs-lookup"><span data-stu-id="7bed7-150">Editing the Design</span></span>](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
