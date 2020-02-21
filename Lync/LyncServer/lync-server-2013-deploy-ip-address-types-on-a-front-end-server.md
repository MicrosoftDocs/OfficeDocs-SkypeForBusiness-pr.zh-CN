---
title: Lync Server 2013：在前端服务器上部署 IP 地址类型
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Front End Server
ms:assetid: b6c8e0f9-ec8e-4a4e-a525-756f9cd6b9d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205191(v=OCS.15)
ms:contentKeyID: 48185193
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e9c2f59cd3ee07e565a984ebb6f19d8ff07f50e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-front-end-server-for-lync-server-2013"></a><span data-ttu-id="a21a1-102">在 Lync Server 2013 的前端服务器上部署 IP 地址类型</span><span class="sxs-lookup"><span data-stu-id="a21a1-102">Deploy IP address types on a Front End Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a21a1-103">_**上次修改的主题：** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="a21a1-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="a21a1-104">使用拓扑生成器，执行以下过程中的步骤，以在前端服务器上部署 IP 地址类型。</span><span class="sxs-lookup"><span data-stu-id="a21a1-104">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="a21a1-105">在前端服务器上部署 IP 地址类型</span><span class="sxs-lookup"><span data-stu-id="a21a1-105">To deploy IP address types on a Front End Server</span></span>

1.  <span data-ttu-id="a21a1-p101">在“Enterprise Edition 前端池”\*\*\*\* 下，右键单击池中的服务器，然后选择“编辑属性”\*\*\*\*。（也可以选择服务器，然后单击“操作”\*\*\*\* 菜单中的“编辑属性”\*\*\*\*。）</span><span class="sxs-lookup"><span data-stu-id="a21a1-p101">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**. (Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2.  <span data-ttu-id="a21a1-p102">在“编辑属性”\*\*\*\* 对话框中，选择您要配置的 IP 地址类型。对于双协议栈配置，则选择“启用 IPv4”\*\*\*\* 和“启用 IPv6”\*\*\*\*，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="a21a1-p102">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="a21a1-110">**前端服务器池的“编辑属性”对话框**</span><span class="sxs-lookup"><span data-stu-id="a21a1-110">**Edit Properties dialog box for the Front End Server pool**</span></span>
    
    <span data-ttu-id="a21a1-111">![前端服务器的 "编辑属性" 对话框](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "前端服务器的 "编辑属性" 对话框")</span><span class="sxs-lookup"><span data-stu-id="a21a1-111">![Front End Server Edit Properties dialog box](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "Front End Server Edit Properties dialog box")</span></span>
    
      - <span data-ttu-id="a21a1-p103">**使用所有配置 IP 地址**。如果您希望允许使用计算机上定义的任何 IP 地址，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="a21a1-p103">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a21a1-114">这是针对 IP 版本 6 (IPv6) 配置的建议选项。</span><span class="sxs-lookup"><span data-stu-id="a21a1-114">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

        
        </div>
    
      - <span data-ttu-id="a21a1-p104">**服务仅供选定 IP 地址使用**。选择此选项可指定要在新服务器上使用的特定地址。如果选择此选项，则必须输入“主 IP 地址”\*\*\*\* 的值。</span><span class="sxs-lookup"><span data-stu-id="a21a1-p104">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for **Primary IP address**.</span></span>
    
      - <span data-ttu-id="a21a1-p105">**主 IP 地址**。输入用于除公用电话交换网 (PSTN) 之外的所有通信的 IP 地址。所输入的 IP 地址必须符合选择的地址类型的格式。</span><span class="sxs-lookup"><span data-stu-id="a21a1-p105">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>
    
      - <span data-ttu-id="a21a1-121">**PSTN IP 地址**。</span><span class="sxs-lookup"><span data-stu-id="a21a1-121">**PSTN IP address**.</span></span> <span data-ttu-id="a21a1-122">并置中介服务器角色不支持安装额外的网络接口卡（NIC） s 来支持 Lync Server 2013 的 PSTN IP 地址配置。</span><span class="sxs-lookup"><span data-stu-id="a21a1-122">The installation of additional network interface cards (NIC)s to support the PSTN IP address configuration for Lync Server 2013 is not supported on collocated Mediation Server roles.</span></span> <span data-ttu-id="a21a1-123">有关 Lync Server 2013 支持的 NIC 配置的详细信息，请参阅[Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)。</span><span class="sxs-lookup"><span data-stu-id="a21a1-123">For more information about supported NIC configurations for Lync Server 2013, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

