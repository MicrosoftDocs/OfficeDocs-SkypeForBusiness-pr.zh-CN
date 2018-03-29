---
title: 在 Skype for Business Server 2015 中编辑拓扑
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: 完成初始的访谈式问题后，即可编辑站点的完全限定的域名 (FQDN) 和 IP 地址。 为此，请在全局拓扑结构页上，双击您要编辑的网站。
ms.openlocfilehash: 7de778c9aed8594df4fc70f9a6635bd0c21c6db4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a><span data-ttu-id="fc00a-104">在 Skype for Business Server 2015 中编辑拓扑</span><span class="sxs-lookup"><span data-stu-id="fc00a-104">Edit the topology in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="fc00a-p102">完成初始的访谈式问题后，即可编辑站点的完全限定的域名 (FQDN) 和 IP 地址。为此，请在“**全局拓扑**”页上双击要编辑的站点。</span><span class="sxs-lookup"><span data-stu-id="fc00a-p102">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site. To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>
  
<span data-ttu-id="fc00a-107">规划工具显示所选站点的站点拓扑。</span><span class="sxs-lookup"><span data-stu-id="fc00a-107">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="fc00a-108">在站点页面的底部有四个选项卡：</span><span class="sxs-lookup"><span data-stu-id="fc00a-108">At the bottom of the site page are four tabs:</span></span>
  
![规划工具 - 站点拓扑](../../media/Planning_Tool_Site_Topology.png)
  
- <span data-ttu-id="fc00a-110">站点拓扑的建议的拓扑可视化概述当前显示的页面。</span><span class="sxs-lookup"><span data-stu-id="fc00a-110">Site Topology - The currently displayed page with a visual overview of the topology as recommended.</span></span>
    
- <span data-ttu-id="fc00a-111">边缘网络图的边缘网络图页是工作的在设计器完成大部分中规划工具。</span><span class="sxs-lookup"><span data-stu-id="fc00a-111">Edge Network Diagram - The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="fc00a-112">关系图显示了业务服务器 2015年拓扑建议使用 Skype 的网络配置，可编辑项的 IP 地址和服务器、 池，并同时硬件的 Fqdn 和域名系统 (DNS) 负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="fc00a-112">The diagram displays the network configuration for a recommended Skype for Business Server 2015 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>
    
- <span data-ttu-id="fc00a-113">边缘管理报告-边缘管理报告中包含四个报表总计：</span><span class="sxs-lookup"><span data-stu-id="fc00a-113">Edge Admin Report - The Edge Admin Report contains a total of four reports:</span></span>
    
     ![“边缘管理报告”页](../../media/Planning_Tool_Summary_Report.png)
  
  - <span data-ttu-id="fc00a-115">摘要报告-边缘网络配置设置的常规报告。</span><span class="sxs-lookup"><span data-stu-id="fc00a-115">Summary Report - A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="fc00a-116">如果将“**边缘网络图**”页上的值编辑为将在实际部署中使用的拓扑 TCP/IP 和 FQDN 值，则会在此处显示那些地址和名称。</span><span class="sxs-lookup"><span data-stu-id="fc00a-116">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="fc00a-117">否则将显示默认文本。</span><span class="sxs-lookup"><span data-stu-id="fc00a-117">Otherwise, the default text will appear.</span></span>
    
  - <span data-ttu-id="fc00a-118">报告证书的证书报表将列出的主题名称和主题备用名称的证书所需的拓扑结构。</span><span class="sxs-lookup"><span data-stu-id="fc00a-118">Certificate Report - The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>
    
  - <span data-ttu-id="fc00a-119">防火墙报告-防火墙报告列出了基础结构中配置外围防火墙所必需的信息。</span><span class="sxs-lookup"><span data-stu-id="fc00a-119">Firewall Report - The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="fc00a-120">其中包括 IP 地址（默认值或编辑的值）、服务器角色、源 IP 和端口、目标 IP 和端口、传输协议、应用程序协议和相关的说明。</span><span class="sxs-lookup"><span data-stu-id="fc00a-120">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>
    
  - <span data-ttu-id="fc00a-121">DNS 报告-DNS 报告列出必须创建 DNS 条目的相关信息。</span><span class="sxs-lookup"><span data-stu-id="fc00a-121">DNS Report - The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="fc00a-122">其中包括相应操作所需的记录类型、FQDN、IP 地址和备注。</span><span class="sxs-lookup"><span data-stu-id="fc00a-122">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>
    
- <span data-ttu-id="fc00a-123">站点摘要-站点摘要综述了通过初始面试回答或填写**设计网站**中的值所做的选择。</span><span class="sxs-lookup"><span data-stu-id="fc00a-123">Site Summary - The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="fc00a-124">此外，还显示容量信息。</span><span class="sxs-lookup"><span data-stu-id="fc00a-124">Capacity information is also presented.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="fc00a-125">“站点摘要”页上的信息可针对每个设计进行自定义，可能不包含此处详细介绍的所有内容或信息。</span><span class="sxs-lookup"><span data-stu-id="fc00a-125">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span> 
  
## <a name="edit-the-network-configuration-diagram"></a><span data-ttu-id="fc00a-126">编辑网络配置图</span><span class="sxs-lookup"><span data-stu-id="fc00a-126">Edit the network configuration diagram</span></span>
<span data-ttu-id="fc00a-127"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="fc00a-127"></span></span>

<span data-ttu-id="fc00a-128">在网络图上定义的 IP 地址和完全限定的域名称 (Fqdn) 的项的项包含大部分业务服务器 2015年规划工具设计的作用在 Skype 的工作。</span><span class="sxs-lookup"><span data-stu-id="fc00a-128">Most of the work that a designer does in the Skype for Business Server 2015 Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="fc00a-129">在此页输入的信息可延伸到的报告，并在规划工具中包含的其他信息。</span><span class="sxs-lookup"><span data-stu-id="fc00a-129">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span> 
  
![规划工具 - 网络图](../../media/Planning_Tool_Network_Diagram.png)
  
<span data-ttu-id="fc00a-131">规划工具创建网络图与 IP 地址和 Fqdn 的默认文本。</span><span class="sxs-lookup"><span data-stu-id="fc00a-131">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span> 
  
<span data-ttu-id="fc00a-132">编辑网络图和输入值：</span><span class="sxs-lookup"><span data-stu-id="fc00a-132">To edit the network diagram and input values:</span></span>
  
1. <span data-ttu-id="fc00a-p110">选择起始网络段。例如，双击文本 **access1.contoso.com**。在打开的对话框中，键入服务器 access1.contoso.com 的实际 FQDN，并输入实际的 IP 地址以替换 131.107.155.3。</span><span class="sxs-lookup"><span data-stu-id="fc00a-p110">Choose a section of the network to begin working on. For example, double-click the text, **access1.contoso.com**. In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>
    
2. <span data-ttu-id="fc00a-135">单击“**确定**”以保存条目。</span><span class="sxs-lookup"><span data-stu-id="fc00a-135">Click **OK** to save the entries.</span></span>
    
3. <span data-ttu-id="fc00a-136">继续编辑 IP 地址和 FQDN，从而为硬件负载平衡器提供虚拟 IP 地址或者为池中服务器的域名系统 (DNS) 负载平衡提供服务器条目。</span><span class="sxs-lookup"><span data-stu-id="fc00a-136">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>
    
<span data-ttu-id="fc00a-p111">规划工具的一个有用功能是可以递增地分配一系列 IP 地址和服务器主机名称，而不是要求设计师编辑池中的单台服务器。例如：</span><span class="sxs-lookup"><span data-stu-id="fc00a-p111">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool. For example:</span></span>
  
1. <span data-ttu-id="fc00a-p112">双击池化的前端服务器。对话框打开后，选中“**是否要将这些 IP 地址和 FQDN 用作此群集中所有对等服务器的起点？**”。</span><span class="sxs-lookup"><span data-stu-id="fc00a-p112">Double-click the pooled Front End Servers. When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span> 
    
2. <span data-ttu-id="fc00a-141">例如，第一台服务器的起始值是 fe0101.contoso.com，IP 地址是 192.168.21.122。</span><span class="sxs-lookup"><span data-stu-id="fc00a-141">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>
    
3. <span data-ttu-id="fc00a-142">键入 fe0.contoso.com**前结束服务器 FQDN**、**前结束服务器 IP 地址**，键入 192.168.21.131，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fc00a-142">Type fe0.contoso.com in **Front End Server FQDN**, type 192.168.21.131 in **Front End Server IP address**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="fc00a-143">自动增量功能会将池中的所有服务器更新为 fe01 到 fe06，将所有 IP 地址更新为 192.168.21.131 到 192.168.21.136。</span><span class="sxs-lookup"><span data-stu-id="fc00a-143">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>
    
<span data-ttu-id="fc00a-144">完成所有编辑后，执行以下步骤以保存拓扑：</span><span class="sxs-lookup"><span data-stu-id="fc00a-144">After you have completed all edits, save the topology by completing the following steps:</span></span> 
  
<span data-ttu-id="fc00a-145">若要保存规划工具设计，单击**文件**，然后单击**保存拓扑结构**或**拓扑另存为**。</span><span class="sxs-lookup"><span data-stu-id="fc00a-145">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="fc00a-146">如果出现“**将规划工具另存为**”对话框，请在“**文件名**”中键入文件的名称，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="fc00a-146">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="fc00a-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc00a-147">See also</span></span>
<span data-ttu-id="fc00a-148"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="fc00a-148"></span></span>

#### 

[<span data-ttu-id="fc00a-149">编辑设计</span><span class="sxs-lookup"><span data-stu-id="fc00a-149">Editing the Design</span></span>](http://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)

