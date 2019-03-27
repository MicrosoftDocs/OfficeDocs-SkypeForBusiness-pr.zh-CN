---
title: 在 Skype for Business 中配置 IP 地址类型
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 摘要： 实现 Skype 业务服务器之前查看下面的 IP 地址类型注意事项。
ms.openlocfilehash: 82c2cac46efe2513c6506bf57ab5c181c7a32202
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892121"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a><span data-ttu-id="07185-103">在 Skype for Business 中配置 IP 地址类型</span><span class="sxs-lookup"><span data-stu-id="07185-103">Configure IP address types in Skype for Business</span></span>

<span data-ttu-id="07185-104">**摘要：** 实现 Skype 业务服务器之前查看下面的 IP 地址类型注意事项。</span><span class="sxs-lookup"><span data-stu-id="07185-104">**Summary:** Review the IP Address type considerations below before implementing Skype for Business Server.</span></span>

<span data-ttu-id="07185-105">使用拓扑生成器中配置的拓扑设置部署 IP 地址类型。</span><span class="sxs-lookup"><span data-stu-id="07185-105">You deploy IP address types by using topology settings that you configure in Topology Builder.</span></span> <span data-ttu-id="07185-106">本节介绍如何部署前端服务器、 中介服务器和边缘服务器上的 IP 地址类型。</span><span class="sxs-lookup"><span data-stu-id="07185-106">This section describes how to deploy IP address types on Front End Servers, Mediation Servers, and Edge Servers.</span></span>

## <a name="deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="07185-107">在前端服务器上部署 IP 地址类型</span><span class="sxs-lookup"><span data-stu-id="07185-107">Deploy IP address types on a Front End Server</span></span>

<span data-ttu-id="07185-108">使用拓扑生成器，请执行以下过程可部署前端服务器上的 IP 地址类型中的步骤。</span><span class="sxs-lookup"><span data-stu-id="07185-108">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="07185-109">在前端服务器上部署 IP 地址类型</span><span class="sxs-lookup"><span data-stu-id="07185-109">To deploy IP address types on a Front End Server</span></span>

1. <span data-ttu-id="07185-p102">在“**Enterprise Edition 前端池**”下，右键单击池中的服务器，然后选择“**编辑属性**”。（也可以选择服务器，然后单击“**操作**”菜单中的“**编辑属性**”。）</span><span class="sxs-lookup"><span data-stu-id="07185-p102">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**. (Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="07185-112">在“**编辑属性**”对话框中，选择您要配置的 IP 地址类型。</span><span class="sxs-lookup"><span data-stu-id="07185-112">In the **Edit Properties** dialog box, select the IP address type that you want to configure.</span></span> <span data-ttu-id="07185-113">对于双协议栈配置中，选择**启用 IPv4**和**启用 IPv6**。</span><span class="sxs-lookup"><span data-stu-id="07185-113">For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**.</span></span>

   <span data-ttu-id="07185-114">**前端服务器池的“编辑属性”对话框**</span><span class="sxs-lookup"><span data-stu-id="07185-114">**Edit Properties dialog box for the Front End Server pool**</span></span>

   - <span data-ttu-id="07185-p104">**使用所有配置 IP 地址**。如果您希望允许使用计算机上定义的任何 IP 地址，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="07185-p104">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

     > [!NOTE]
     > <span data-ttu-id="07185-117">这是针对 IP 版本 6 (IPv6) 配置的建议选项。</span><span class="sxs-lookup"><span data-stu-id="07185-117">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

   - <span data-ttu-id="07185-p105">**将服务用途限制为所选 IP 地址**。选择此选项可指定要在新服务器上使用的特定地址。如果选择此选项，则必须输入“**主 IP 地址**”的值。</span><span class="sxs-lookup"><span data-stu-id="07185-p105">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for **Primary IP address**.</span></span>

   - <span data-ttu-id="07185-p106">**主 IP 地址**。输入用于除公用电话交换网 (PSTN) 之外的所有通信的 IP 地址。所输入的 IP 地址必须符合选择的地址类型的格式。</span><span class="sxs-lookup"><span data-stu-id="07185-p106">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>

   - <span data-ttu-id="07185-p107">**PSTN IP 地址**。在前端服务器上并置中介服务器时定义一个 PSTN IP 地址。该地址必须符合选择的地址类型的格式。</span><span class="sxs-lookup"><span data-stu-id="07185-p107">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>

> [!NOTE]
> <span data-ttu-id="07185-127">不支持其他网络接口卡 (Nic) 以支持的 PSTN IP 地址配置前端服务器上安装。</span><span class="sxs-lookup"><span data-stu-id="07185-127">The installation of additional network interface cards (NICs) to support the PSTN IP address configuration on Front End Servers is not supported.</span></span> <span data-ttu-id="07185-128">有关支持的 Skype 业务服务器的 NIC 配置的详细信息，请参阅[Lync Server 2013 的硬件与 Server hardware platforms](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)。</span><span class="sxs-lookup"><span data-stu-id="07185-128">For more information about supported NIC configurations for Skype for Business Server, see [Server hardware platforms for Lync Server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span></span>

## <a name="deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="07185-129">在中介服务器上部署 IP 地址类型</span><span class="sxs-lookup"><span data-stu-id="07185-129">Deploy IP address types on a Mediation Server</span></span>

<span data-ttu-id="07185-130">使用拓扑生成器，请执行以下过程可部署中介服务器上的 IP 地址类型中的步骤。</span><span class="sxs-lookup"><span data-stu-id="07185-130">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="07185-131">在中介服务器上部署 IP 地址类型</span><span class="sxs-lookup"><span data-stu-id="07185-131">To deploy IP address types on a Mediation Server</span></span>

- <span data-ttu-id="07185-132">在拓扑生成器，**中介池**，右键单击池内的服务器，然后选择**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="07185-132">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="07185-133">（或者，选择服务器，，然后单击从**操作**菜单的**编辑属性**。）</span><span class="sxs-lookup"><span data-stu-id="07185-133">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

- <span data-ttu-id="07185-p110">在“**编辑属性**”对话框中，选择您要配置的 IP 地址类型。对于双协议栈配置，则选择“**启用 IPv4**”和“**启用 IPv6**”，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="07185-p110">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>

   <span data-ttu-id="07185-136">**用于中介服务器池的“编辑属性”对话框**</span><span class="sxs-lookup"><span data-stu-id="07185-136">**Edit Properties dialog box for the Mediation Server pool**</span></span>

  - <span data-ttu-id="07185-p111">**使用所有配置 IP 地址**。如果您希望允许使用计算机上定义的任何 IP 地址，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="07185-p111">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

    > [!NOTE]
    > <span data-ttu-id="07185-139">这是针对 IP 版本 6 (IPv6) 配置的建议选项。</span><span class="sxs-lookup"><span data-stu-id="07185-139">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

  - <span data-ttu-id="07185-p112">**将服务用途限制为所选 IP 地址**。选择此选项可指定要在新服务器上使用的特定地址。如果选择此选项，则必须输入主 IP 地址的值。</span><span class="sxs-lookup"><span data-stu-id="07185-p112">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for Primary IP address.</span></span>

  - <span data-ttu-id="07185-p113">**主 IP 地址**。输入用于除公用电话交换网 (PSTN) 之外的所有通信的 IP 地址。所输入的 IP 地址必须符合选择的地址类型的格式。</span><span class="sxs-lookup"><span data-stu-id="07185-p113">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>

  - <span data-ttu-id="07185-p114">**PSTN IP 地址**。在前端服务器上并置中介服务器时定义一个 PSTN IP 地址。该地址必须符合选择的地址类型的格式。</span><span class="sxs-lookup"><span data-stu-id="07185-p114">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="07185-149">仅在*专用*中介服务器支持两个网卡。</span><span class="sxs-lookup"><span data-stu-id="07185-149">We only support two network cards on *dedicated* Mediation Servers.</span></span> <span data-ttu-id="07185-150">如果在前端并置的中介 Sserver 角色，然后不支持双网卡。</span><span class="sxs-lookup"><span data-stu-id="07185-150">If the Mediation Sserver role is collocated on the Front End, then dual network cards are not supported.</span></span> 

> [!NOTE]
> - <span data-ttu-id="07185-151">有关支持的 Skype 的业务服务器 2015年的 NIC 配置的详细信息，请参阅[业务服务器 2015年的 Skype 的硬件](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="07185-151">For more information about supported NIC configurations for Skype for Business Server 2015, see [Hardware for Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)</span></span>
> - <span data-ttu-id="07185-152">有关支持的 Skype 的业务服务器 2019年的 NIC 配置的详细信息，请参阅[业务服务器 2019年的 Skype 的硬件](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)</span><span class="sxs-lookup"><span data-stu-id="07185-152">For more information about supported NIC configurations for Skype for Business Server 2019, see [Hardware for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)</span></span>



## <a name="deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="07185-153">在边缘服务器上部署 IP 地址类型</span><span class="sxs-lookup"><span data-stu-id="07185-153">Deploy IP address types on an Edge Server</span></span>

<span data-ttu-id="07185-154">使用拓扑生成器，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="07185-154">Using Topology Builder, perform the following steps:</span></span>

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="07185-155">在边缘服务器上部署 IP 地址类型</span><span class="sxs-lookup"><span data-stu-id="07185-155">To deploy IP address types on an Edge Server</span></span>

1. <span data-ttu-id="07185-156">在拓扑生成器，**边缘池**，右键单击池内的服务器，然后选择**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="07185-156">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="07185-157">（或者，选择服务器，，然后单击从**操作**菜单的**编辑属性**。）</span><span class="sxs-lookup"><span data-stu-id="07185-157">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="07185-158">在“**编辑属性**”窗口中，选择要支持的 IP 地址配置。</span><span class="sxs-lookup"><span data-stu-id="07185-158">In the **Edit Properties** window, select the IP address configuration that you want to support.</span></span>

3. <span data-ttu-id="07185-159">对于您选择的每个地址类型，必须提供适当的内部和外部地址。</span><span class="sxs-lookup"><span data-stu-id="07185-159">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>
