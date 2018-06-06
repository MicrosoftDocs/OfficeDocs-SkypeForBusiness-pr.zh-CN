---
title: 在 Skype for Business 中配置 IP 地址类型
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 7/22/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 摘要： 为业务服务器 2015年实现 Skype 之前查看下面的 IP 地址类型注意事项。
ms.openlocfilehash: adebab15a0c10310b25af30f6e933625df61dc3d
ms.sourcegitcommit: a612ebe25e06c2cb090f776325712caf3cf3b943
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/06/2018
ms.locfileid: "19630145"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a><span data-ttu-id="ca73b-103">在 Skype for Business 中配置 IP 地址类型</span><span class="sxs-lookup"><span data-stu-id="ca73b-103">Configure IP address types in Skype for Business</span></span>
 
<span data-ttu-id="ca73b-104">**摘要：** 为业务服务器 2015年实现 Skype 之前查看下面的 IP 地址类型注意事项。</span><span class="sxs-lookup"><span data-stu-id="ca73b-104">**Summary:** Review the IP Address type considerations below before implementing Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ca73b-105">使用拓扑生成器中配置的拓扑设置部署 IP 地址类型。</span><span class="sxs-lookup"><span data-stu-id="ca73b-105">You deploy IP address types by using topology settings that you configure in Topology Builder.</span></span> <span data-ttu-id="ca73b-106">本节介绍如何部署前端服务器、 中介服务器和边缘服务器上的 IP 地址类型。</span><span class="sxs-lookup"><span data-stu-id="ca73b-106">This section describes how to deploy IP address types on Front End Servers, Mediation Servers, and Edge Servers.</span></span>
  
## <a name="deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="ca73b-107">在前端服务器上部署 IP 地址类型</span><span class="sxs-lookup"><span data-stu-id="ca73b-107">Deploy IP address types on a Front End Server</span></span>

<span data-ttu-id="ca73b-108">使用拓扑生成器，请执行以下过程可部署前端服务器上的 IP 地址类型中的步骤。</span><span class="sxs-lookup"><span data-stu-id="ca73b-108">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>
  
### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="ca73b-109">在前端服务器上部署 IP 地址类型</span><span class="sxs-lookup"><span data-stu-id="ca73b-109">To deploy IP address types on a Front End Server</span></span>

1. <span data-ttu-id="ca73b-p102">在“**Enterprise Edition 前端池**”下，右键单击池中的服务器，然后选择“**编辑属性**”。（也可以选择服务器，然后单击“**操作**”菜单中的“**编辑属性**”。）</span><span class="sxs-lookup"><span data-stu-id="ca73b-p102">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**. (Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>
    
2. <span data-ttu-id="ca73b-p103">在“**编辑属性**”对话框中，选择您要配置的 IP 地址类型。对于双协议栈配置，则选择“**启用 IPv4**”和“**启用 IPv6**”，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="ca73b-p103">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
   <span data-ttu-id="ca73b-114">**编辑前端服务器池的属性对话框**</span><span class="sxs-lookup"><span data-stu-id="ca73b-114">**Edit Properties dialog box for the Front End Server pool**</span></span>

  - <span data-ttu-id="ca73b-p104">**使用所有配置 IP 地址**。如果您希望允许使用计算机上定义的任何 IP 地址，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="ca73b-p104">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ca73b-117">这是针对 IP 版本 6 (IPv6) 配置的建议选项。</span><span class="sxs-lookup"><span data-stu-id="ca73b-117">This is the recommended option for IP version 6 (IPv6) configurations.</span></span> 
  
  - <span data-ttu-id="ca73b-p105">**将服务用途限制为所选 IP 地址**。选择此选项可指定要在新服务器上使用的特定地址。如果选择此选项，则必须输入“**主 IP 地址**”的值。</span><span class="sxs-lookup"><span data-stu-id="ca73b-p105">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for **Primary IP address**.</span></span>
    
  - <span data-ttu-id="ca73b-p106">**主 IP 地址**。输入用于除公用电话交换网 (PSTN) 之外的所有通信的 IP 地址。所输入的 IP 地址必须符合选择的地址类型的格式。</span><span class="sxs-lookup"><span data-stu-id="ca73b-p106">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>
    
  - <span data-ttu-id="ca73b-p107">**PSTN IP 地址**。在前端服务器上并置中介服务器时定义一个 PSTN IP 地址。该地址必须符合选择的地址类型的格式。</span><span class="sxs-lookup"><span data-stu-id="ca73b-p107">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ca73b-127">不支持其他网络接口卡 (Nic) 以支持的 PSTN IP 地址配置前端服务器上安装。</span><span class="sxs-lookup"><span data-stu-id="ca73b-127">The installation of additional network interface cards (NICs) to support the PSTN IP address configuration on Front End Servers is not supported.</span></span> <span data-ttu-id="ca73b-128">有关支持的 Skype 业务服务器的 NIC 配置的详细信息，请参阅[Lync Server 2013 的硬件与 Server hardware platforms](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ca73b-128">For more information about supported NIC configurations for Skype for Business Server, see [Server hardware platforms for Lync Server 2013](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span></span> 
  
## <a name="deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="ca73b-129">在中介服务器上部署 IP 地址类型</span><span class="sxs-lookup"><span data-stu-id="ca73b-129">Deploy IP address types on a Mediation Server</span></span>

<span data-ttu-id="ca73b-130">使用拓扑生成器，请执行以下过程可部署中介服务器上的 IP 地址类型中的步骤。</span><span class="sxs-lookup"><span data-stu-id="ca73b-130">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>
  
### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="ca73b-131">在中介服务器上部署 IP 地址类型</span><span class="sxs-lookup"><span data-stu-id="ca73b-131">To deploy IP address types on a Mediation Server</span></span>

- <span data-ttu-id="ca73b-132">在拓扑生成器，**中介池**，右键单击池内的服务器，然后选择**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="ca73b-132">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="ca73b-133">（或者，选择服务器，，然后单击从**操作**菜单的**编辑属性**。）</span><span class="sxs-lookup"><span data-stu-id="ca73b-133">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>
    
- <span data-ttu-id="ca73b-p110">在“**编辑属性**”对话框中，选择您要配置的 IP 地址类型。对于双协议栈配置，则选择“**启用 IPv4**”和“**启用 IPv6**”，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="ca73b-p110">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
   <span data-ttu-id="ca73b-136">**编辑中介服务器池的属性对话框**</span><span class="sxs-lookup"><span data-stu-id="ca73b-136">**Edit Properties dialog box for the Mediation Server pool**</span></span>

  - <span data-ttu-id="ca73b-p111">**使用所有配置 IP 地址**。如果您希望允许使用计算机上定义的任何 IP 地址，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="ca73b-p111">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ca73b-139">这是针对 IP 版本 6 (IPv6) 配置的建议选项。</span><span class="sxs-lookup"><span data-stu-id="ca73b-139">This is the recommended option for IP version 6 (IPv6) configurations.</span></span> 
  
  - <span data-ttu-id="ca73b-p112">**将服务用途限制为所选 IP 地址**。选择此选项可指定要在新服务器上使用的特定地址。如果选择此选项，则必须输入主 IP 地址的值。</span><span class="sxs-lookup"><span data-stu-id="ca73b-p112">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for Primary IP address.</span></span>
    
  - <span data-ttu-id="ca73b-p113">**主 IP 地址**。输入用于除公用电话交换网 (PSTN) 之外的所有通信的 IP 地址。所输入的 IP 地址必须符合选择的地址类型的格式。</span><span class="sxs-lookup"><span data-stu-id="ca73b-p113">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>
    
  - <span data-ttu-id="ca73b-p114">**PSTN IP 地址**。在前端服务器上并置中介服务器时定义一个 PSTN IP 地址。该地址必须符合选择的地址类型的格式。</span><span class="sxs-lookup"><span data-stu-id="ca73b-p114">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ca73b-149">不支持其他的 Nic 来支持的 PSTN IP 地址配置独立的中介服务器上安装。</span><span class="sxs-lookup"><span data-stu-id="ca73b-149">The installation of additional NICs to support the PSTN IP address configuration on stand-alone Mediation Servers is not supported.</span></span> <span data-ttu-id="ca73b-150">有关支持的 Skype 业务服务器的 NIC 配置的详细信息，请参阅[Lync Server 2013 的硬件与 Server hardware platforms](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ca73b-150">For more information about supported NIC configurations for Skype for Business Server, see [Server hardware platforms for Lync Server 2013](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span></span> 
  
## <a name="deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="ca73b-151">在边缘服务器上部署 IP 地址类型</span><span class="sxs-lookup"><span data-stu-id="ca73b-151">Deploy IP address types on an Edge Server</span></span>

<span data-ttu-id="ca73b-152">使用拓扑生成器，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ca73b-152">Using Topology Builder, perform the following steps:</span></span>
  
### <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="ca73b-153">在边缘服务器上部署 IP 地址类型</span><span class="sxs-lookup"><span data-stu-id="ca73b-153">To deploy IP address types on an Edge Server</span></span>

1. <span data-ttu-id="ca73b-154">在拓扑生成器，**边缘池**，右键单击池内的服务器，然后选择**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="ca73b-154">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="ca73b-155">（或者，选择服务器，，然后单击从**操作**菜单的**编辑属性**。）</span><span class="sxs-lookup"><span data-stu-id="ca73b-155">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>
    
2. <span data-ttu-id="ca73b-156">在“**编辑属性**”窗口中，选择要支持的 IP 地址配置。</span><span class="sxs-lookup"><span data-stu-id="ca73b-156">In the **Edit Properties** window, select the IP address configuration that you want to support.</span></span>    

3. <span data-ttu-id="ca73b-157">对于您选择的每个地址类型，必须提供适当的内部和外部地址。</span><span class="sxs-lookup"><span data-stu-id="ca73b-157">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>
    