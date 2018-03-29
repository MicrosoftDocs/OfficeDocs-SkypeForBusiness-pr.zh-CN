---
title: 在 Skype for Business 中配置 IP 地址类型
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 7/22/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 摘要： Skype 实现业务服务器 2015年前检查 IP 地址类型下面的注意事项。
ms.openlocfilehash: facfff432cfcde74af737b5a7c5db87d36f3eb41
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-ip-address-types-in-skype-for-business"></a><span data-ttu-id="d56d8-103">在 Skype for Business 中配置 IP 地址类型</span><span class="sxs-lookup"><span data-stu-id="d56d8-103">Configure IP address types in Skype for Business</span></span>
 
<span data-ttu-id="d56d8-104">**摘要：**Skype 实现业务服务器 2015年之前，请查看下面的 IP 地址类型注意事项。</span><span class="sxs-lookup"><span data-stu-id="d56d8-104">**Summary:** Review the IP Address type considerations below before implementing Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="d56d8-105">您可以通过使用配置拓扑生成器中的拓扑结构设置部署的 IP 地址类型。</span><span class="sxs-lookup"><span data-stu-id="d56d8-105">You deploy IP address types by using topology settings that you configure in Topology Builder.</span></span> <span data-ttu-id="d56d8-106">本部分介绍如何部署前端服务器、 中介服务器和边缘服务器上的 IP 地址类型。</span><span class="sxs-lookup"><span data-stu-id="d56d8-106">This section describes how to deploy IP address types on Front End Servers, Mediation Servers, and Edge Servers.</span></span>
  
## <a name="deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="d56d8-107">在前端服务器上部署 IP 地址类型</span><span class="sxs-lookup"><span data-stu-id="d56d8-107">Deploy IP address types on a Front End Server</span></span>

<span data-ttu-id="d56d8-108">使用拓扑生成器，在下面的过程来部署前端服务器的 IP 地址类型中执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="d56d8-108">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>
  
### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="d56d8-109">在前端服务器上部署 IP 地址类型</span><span class="sxs-lookup"><span data-stu-id="d56d8-109">To deploy IP address types on a Front End Server</span></span>

1. <span data-ttu-id="d56d8-p102">在“**Enterprise Edition 前端池**”下，右键单击池中的服务器，然后选择“**编辑属性**”。（也可以选择服务器，然后单击“**操作**”菜单中的“**编辑属性**”。）</span><span class="sxs-lookup"><span data-stu-id="d56d8-p102">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**. (Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>
    
2. <span data-ttu-id="d56d8-p103">在“**编辑属性**”对话框中，选择您要配置的 IP 地址类型。对于双协议栈配置，则选择“**启用 IPv4**”和“**启用 IPv6**”，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="d56d8-p103">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
   <span data-ttu-id="d56d8-114">**编辑为前端服务器池的属性对话框**</span><span class="sxs-lookup"><span data-stu-id="d56d8-114">**Edit Properties dialog box for the Front End Server pool**</span></span>

  - <span data-ttu-id="d56d8-p104">**使用所有配置 IP 地址**。如果您希望允许使用计算机上定义的任何 IP 地址，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="d56d8-p104">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="d56d8-117">这是针对 IP 版本 6 (IPv6) 配置的建议选项。</span><span class="sxs-lookup"><span data-stu-id="d56d8-117">This is the recommended option for IP version 6 (IPv6) configurations.</span></span> 
  
  - <span data-ttu-id="d56d8-p105">**将服务用途限制为所选 IP 地址**。选择此选项可指定要在新服务器上使用的特定地址。如果选择此选项，则必须输入“**主 IP 地址**”的值。</span><span class="sxs-lookup"><span data-stu-id="d56d8-p105">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for **Primary IP address**.</span></span>
    
  - <span data-ttu-id="d56d8-p106">**主 IP 地址**。输入用于除公用电话交换网 (PSTN) 之外的所有通信的 IP 地址。所输入的 IP 地址必须符合选择的地址类型的格式。</span><span class="sxs-lookup"><span data-stu-id="d56d8-p106">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>
    
  - <span data-ttu-id="d56d8-p107">**PSTN IP 地址**。在前端服务器上并置中介服务器时定义一个 PSTN IP 地址。该地址必须符合选择的地址类型的格式。</span><span class="sxs-lookup"><span data-stu-id="d56d8-p107">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d56d8-127">不支持安装的附加网络接口卡 (Nic) 在前端服务器上支持的 PSTN IP 地址配置。</span><span class="sxs-lookup"><span data-stu-id="d56d8-127">The installation of additional network interface cards (NICs) to support the PSTN IP address configuration on Front End Servers is not supported.</span></span> <span data-ttu-id="d56d8-128">有关所支持的 Skype 业务服务器的 NIC 配置的详细信息，请参阅[Lync Server 2013 的服务器硬件平台](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d56d8-128">For more information about supported NIC configurations for Skype for Business Server, see [Server hardware platforms for Lync Server 2013](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span></span> 
  
## <a name="deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="d56d8-129">在中介服务器上部署 IP 地址类型</span><span class="sxs-lookup"><span data-stu-id="d56d8-129">Deploy IP address types on a Mediation Server</span></span>

<span data-ttu-id="d56d8-130">使用拓扑生成器，在下面的过程来部署中介服务器的 IP 地址类型中执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="d56d8-130">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>
  
### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="d56d8-131">在中介服务器上部署 IP 地址类型</span><span class="sxs-lookup"><span data-stu-id="d56d8-131">To deploy IP address types on a Mediation Server</span></span>

- <span data-ttu-id="d56d8-132">在拓扑生成器中，在**中介池**，右键单击在池中的服务器，然后选择**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="d56d8-132">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="d56d8-133">（或者，选择服务器，然后从**操作**菜单上单击**编辑属性**。）</span><span class="sxs-lookup"><span data-stu-id="d56d8-133">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>
    
- <span data-ttu-id="d56d8-p110">在“**编辑属性**”对话框中，选择您要配置的 IP 地址类型。对于双协议栈配置，则选择“**启用 IPv4**”和“**启用 IPv6**”，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="d56d8-p110">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
   <span data-ttu-id="d56d8-136">**编辑为中介服务器池的属性对话框**</span><span class="sxs-lookup"><span data-stu-id="d56d8-136">**Edit Properties dialog box for the Mediation Server pool**</span></span>

  - <span data-ttu-id="d56d8-p111">**使用所有配置 IP 地址**。如果您希望允许使用计算机上定义的任何 IP 地址，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="d56d8-p111">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="d56d8-139">这是针对 IP 版本 6 (IPv6) 配置的建议选项。</span><span class="sxs-lookup"><span data-stu-id="d56d8-139">This is the recommended option for IP version 6 (IPv6) configurations.</span></span> 
  
  - <span data-ttu-id="d56d8-p112">**将服务用途限制为所选 IP 地址**。选择此选项可指定要在新服务器上使用的特定地址。如果选择此选项，则必须输入主 IP 地址的值。</span><span class="sxs-lookup"><span data-stu-id="d56d8-p112">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for Primary IP address.</span></span>
    
  - <span data-ttu-id="d56d8-p113">**主 IP 地址**。输入用于除公用电话交换网 (PSTN) 之外的所有通信的 IP 地址。所输入的 IP 地址必须符合选择的地址类型的格式。</span><span class="sxs-lookup"><span data-stu-id="d56d8-p113">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>
    
  - <span data-ttu-id="d56d8-p114">**PSTN IP 地址**。在前端服务器上并置中介服务器时定义一个 PSTN IP 地址。该地址必须符合选择的地址类型的格式。</span><span class="sxs-lookup"><span data-stu-id="d56d8-p114">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d56d8-149">不支持其他 Nic 在独立的中介服务器上支持的 PSTN IP 地址配置的安装。</span><span class="sxs-lookup"><span data-stu-id="d56d8-149">The installation of additional NICs to support the PSTN IP address configuration on stand-alone Mediation Servers is not supported.</span></span> <span data-ttu-id="d56d8-150">有关所支持的 Skype 业务服务器的 NIC 配置的详细信息，请参阅[Lync Server 2013 的服务器硬件平台](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d56d8-150">For more information about supported NIC configurations for Skype for Business Server, see [Server hardware platforms for Lync Server 2013](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span></span> 
  
## <a name="deploy-ip-address-types-on-a-edge-server"></a><span data-ttu-id="d56d8-151">在边缘服务器上部署 IP 地址类型</span><span class="sxs-lookup"><span data-stu-id="d56d8-151">Deploy IP address types on a Edge Server</span></span>

<span data-ttu-id="d56d8-152">使用拓扑生成器，在下面的过程来部署边缘服务器上的 IP 地址类型中执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="d56d8-152">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on an Edge Server.</span></span>
  
### <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="d56d8-153">在边缘服务器上部署 IP 地址类型</span><span class="sxs-lookup"><span data-stu-id="d56d8-153">To deploy IP address types on an Edge Server</span></span>

1. <span data-ttu-id="d56d8-154">在拓扑生成器中，在**边缘池**，右键单击在池中的服务器，然后选择**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="d56d8-154">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="d56d8-155">（或者，选择服务器，然后从**操作**菜单上单击**编辑属性**。）</span><span class="sxs-lookup"><span data-stu-id="d56d8-155">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>
    
2. <span data-ttu-id="d56d8-p117">在“**编辑属性**”窗口中，选择要支持的 IP 地址配置。下图显示用于内部接口和外部接口的双协议栈配置。</span><span class="sxs-lookup"><span data-stu-id="d56d8-p117">In the **Edit Properties** window, select the IP address configuration that you want to support. The following figures show a dual stack configuration for the internal interface and the external interface.</span></span>
    
   <span data-ttu-id="d56d8-158">**双堆积边缘服务器的内部接口**</span><span class="sxs-lookup"><span data-stu-id="d56d8-158">**Dual stacked Edge Server internal interface**</span></span>

   <span data-ttu-id="d56d8-159">**双堆积的边缘服务器外部接口**</span><span class="sxs-lookup"><span data-stu-id="d56d8-159">**Dual stacked Edge Server external interface**</span></span>

3. <span data-ttu-id="d56d8-160">对于您选择的每个地址类型，必须提供适当的内部和外部地址。</span><span class="sxs-lookup"><span data-stu-id="d56d8-160">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>
    

