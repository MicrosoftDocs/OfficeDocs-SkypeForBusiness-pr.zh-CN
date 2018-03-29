---
title: Lync Server 2010 中的边缘机设置扩展器
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 若要为单个的边缘服务器或池中边缘成员计算机编辑边缘服务器计算机的属性，您配置服务器名称和 IP 地址配置设置：
ms.openlocfilehash: d1bc35683ff70e1666a46d478aa97b3bcc3d5593
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a><span data-ttu-id="650e8-103">Lync Server 2010 中的边缘机设置扩展器</span><span class="sxs-lookup"><span data-stu-id="650e8-103">Edge Machine Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="650e8-104">若要为单个的边缘服务器或池中边缘成员计算机编辑边缘服务器计算机的属性，您可以配置**服务器名称和 IP 地址配置**设置：</span><span class="sxs-lookup"><span data-stu-id="650e8-104">To edit the properties for Edge Server computers as an single Edge Server or as member computers in an Edge pool, you configure **Server name and IP address configuration** settings:</span></span>
  
- <span data-ttu-id="650e8-105">**内部名称或 FQDN**： 键入计算机的名称，如域名系统 (DNS) 中引用它。</span><span class="sxs-lookup"><span data-stu-id="650e8-105">**Internal name or FQDN**: Type the name of the computer as it is referenced in the domain name system (DNS).</span></span> 
    
- <span data-ttu-id="650e8-106">**内部的 IPv4 地址**： 键入这台计算机的内部网络接口卡 (NIC) 的 IPv4 地址。</span><span class="sxs-lookup"><span data-stu-id="650e8-106">**Internal IPv4 address**: Type the IPv4 address of the internal network interface card (NIC) for this computer.</span></span>
    
- <span data-ttu-id="650e8-107">配置与该计算机关联的**访问边缘服务****外部的 IPv4 地址**</span><span class="sxs-lookup"><span data-stu-id="650e8-107">You configure the **Access Edge service** **External IPv4 address** associated with this computer</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="650e8-108">如果选择了要用于边缘服务器配置的单个 IP 地址，您将只能编辑访问边缘服务外部的 IPv4 地址。</span><span class="sxs-lookup"><span data-stu-id="650e8-108">If you selected to use a single IP address for the Edge Server configuration, you will only be able to edit the external IPv4 address for the Access Edge service.</span></span> <span data-ttu-id="650e8-109">其他边缘服务将共享相同的 IPv4 地址访问边缘服务。</span><span class="sxs-lookup"><span data-stu-id="650e8-109">The other Edge services will share the same IPv4 address as the Access Edge service.</span></span> 
  
- <span data-ttu-id="650e8-110">如果可编辑，则配置与该计算机关联的**Web 会议服务****外部的 IPv4 地址**</span><span class="sxs-lookup"><span data-stu-id="650e8-110">If available to edit, you configure the **Web Conferencing service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="650e8-111">如果可编辑，则配置**A / V 边缘服务****外部的 IPv4 地址**与这台计算机</span><span class="sxs-lookup"><span data-stu-id="650e8-111">If available to edit, you configure the **A/V Edge service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="650e8-112">如果可编辑，则配置与该计算机关联的**启用 NAT 的公用 IPv4 地址**。</span><span class="sxs-lookup"><span data-stu-id="650e8-112">If available to edit, you configure the **NAT-enabled public IPv4 address** associated with this computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="650e8-113">**启用 NAT 的公用 IPv4 地址**的配置属性将只能编辑如果您选择了提供网络地址转换 (NAT) 的 A / V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="650e8-113">The configuration property for **NAT-enabled public IPv4 address** will only be available to edit if you chose to provide network address translation (NAT) for the A/V Edge service</span></span>
  
 <span data-ttu-id="650e8-114">**确定** 接受更改并通过对话框提交更改。</span><span class="sxs-lookup"><span data-stu-id="650e8-114">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="650e8-115">**取消** 放弃更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="650e8-115">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="650e8-116">**帮助** 显示此帮助屏幕。</span><span class="sxs-lookup"><span data-stu-id="650e8-116">**Help** Displays this help screen.</span></span>
  

