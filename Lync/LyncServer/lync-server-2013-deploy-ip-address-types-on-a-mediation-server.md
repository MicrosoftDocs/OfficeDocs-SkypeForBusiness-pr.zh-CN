---
title: Lync Server 2013：在中介服务器上部署 IP 地址类型
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Mediation Server
ms:assetid: 689ebed5-96ee-4cd4-b7ae-ee2a86a1d9b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204964(v=OCS.15)
ms:contentKeyID: 48184376
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c76dcde03d2a85eb45f7b2c28d6b7c7d99b41b20
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531479"
---
# <a name="deploy-ip-address-types-on-a-mediation-server-for-lync-server-2013"></a><span data-ttu-id="5ddfb-102">在 Lync server 2013 的中介服务器上部署 IP 地址类型</span><span class="sxs-lookup"><span data-stu-id="5ddfb-102">Deploy IP address types on a Mediation Server for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ddfb-103">_**上次修改的主题：** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="5ddfb-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="5ddfb-104">使用拓扑生成器，执行以下过程中的步骤，以在中介服务器上部署 IP 地址类型。</span><span class="sxs-lookup"><span data-stu-id="5ddfb-104">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="5ddfb-105">在中介服务器上部署 IP 地址类型</span><span class="sxs-lookup"><span data-stu-id="5ddfb-105">To deploy IP address types on a Mediation Server</span></span>

  - <span data-ttu-id="5ddfb-106">在拓扑生成器中，在 " **中介池**" 下，右键单击池内的服务器，然后选择 " **编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="5ddfb-106">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="5ddfb-107"> (或者，选择服务器，然后从 "**操作**" 菜单中单击 "**编辑属性**"。 ) </span><span class="sxs-lookup"><span data-stu-id="5ddfb-107">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

  - <span data-ttu-id="5ddfb-p102">在“编辑属性”\*\*\*\* 对话框中，选择您要配置的 IP 地址类型。对于双协议栈配置，则选择“启用 IPv4”\*\*\*\* 和“启用 IPv6”\*\*\*\*，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="5ddfb-p102">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="5ddfb-110">**用于中介服务器池的“编辑属性”对话框**</span><span class="sxs-lookup"><span data-stu-id="5ddfb-110">**Edit Properties dialog box for the Mediation Server pool**</span></span>
    
    <span data-ttu-id="5ddfb-111">![具有 FQDN 的 "Lync Server 常规属性" 页](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "具有 FQDN 的 "Lync Server 常规属性" 页")</span><span class="sxs-lookup"><span data-stu-id="5ddfb-111">![Lync Server general properties page with FQDN](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Lync Server general properties page with FQDN")</span></span>
    
      - <span data-ttu-id="5ddfb-p103">**使用所有配置 IP 地址**。如果您希望允许使用计算机上定义的任何 IP 地址，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="5ddfb-p103">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="5ddfb-114">这是用于 IP 版本 6 (IPv6) 配置的建议选项。</span><span class="sxs-lookup"><span data-stu-id="5ddfb-114">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

        
        </div>
    
      - <span data-ttu-id="5ddfb-p104">**将服务用途限制为所选 IP 地址**。选择此选项可指定要在新服务器上使用的特定地址。如果选择此选项，则必须为主 IP 地址输入值。</span><span class="sxs-lookup"><span data-stu-id="5ddfb-p104">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for Primary IP address.</span></span>
    
      - <span data-ttu-id="5ddfb-p105">**主 IP 地址**。输入服务器将用于除公用电话交换网 (PSTN) 之外的所有通信的 IP 地址。输入的 IP 地址必须与选定地址类型的格式匹配。</span><span class="sxs-lookup"><span data-stu-id="5ddfb-p105">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>
    
      - <span data-ttu-id="5ddfb-121">**PSTN IP 地址**。</span><span class="sxs-lookup"><span data-stu-id="5ddfb-121">**PSTN IP address**.</span></span> <span data-ttu-id="5ddfb-122">当中介服务器是独立的时，定义 PSTN IP 地址。</span><span class="sxs-lookup"><span data-stu-id="5ddfb-122">Define a PSTN IP address when a Mediation Server is standalone.</span></span> <span data-ttu-id="5ddfb-123">该地址必须符合选择的地址类型的格式。</span><span class="sxs-lookup"><span data-stu-id="5ddfb-123">This address must match the format of the selected address type.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="5ddfb-124">并置中介服务器角色不支持安装其他网络接口卡 (NIC) s 以支持 Lync Server 2013 的 PSTN IP 地址配置。</span><span class="sxs-lookup"><span data-stu-id="5ddfb-124">The installation of additional network interface cards (NIC)s to support the PSTN IP address configuration for Lync Server 2013 is not supported on collocated Mediation Server roles.</span></span> <span data-ttu-id="5ddfb-125">有关 Lync Server 2013 支持的 NIC 配置的详细信息，请参阅 <A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013 的服务器硬件平台</A>。</span><span class="sxs-lookup"><span data-stu-id="5ddfb-125">For more information about supported NIC configurations for Lync Server 2013, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

