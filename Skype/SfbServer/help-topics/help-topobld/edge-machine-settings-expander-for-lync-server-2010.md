---
title: Lync Server 2010 的边缘计算机设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 若要将边缘服务器计算机的属性编辑为单个边缘服务器或边缘池中的成员计算机，请配置服务器名称和 IP 地址配置设置：
ms.openlocfilehash: eb2135391791fdb915578fe9938329b56c85908c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218923"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a><span data-ttu-id="d62e4-103">Lync Server 2010 的边缘计算机设置扩展器</span><span class="sxs-lookup"><span data-stu-id="d62e4-103">Edge Machine Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="d62e4-104">若要将边缘服务器计算机的属性编辑为单个边缘服务器或边缘池中的成员计算机，请配置 **服务器名称和 IP 地址配置** 设置：</span><span class="sxs-lookup"><span data-stu-id="d62e4-104">To edit the properties for Edge Server computers as an single Edge Server or as member computers in an Edge pool, you configure **Server name and IP address configuration** settings:</span></span>
  
- <span data-ttu-id="d62e4-105">**内部名称或 FQDN**：键入在域名系统 (DNS) 中引用的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="d62e4-105">**Internal name or FQDN**: Type the name of the computer as it is referenced in the domain name system (DNS).</span></span> 
    
- <span data-ttu-id="d62e4-106">**内部 IPv4 地址**：键入该计算机内部网络接口卡 (NIC) 的 IPv4 地址。</span><span class="sxs-lookup"><span data-stu-id="d62e4-106">**Internal IPv4 address**: Type the IPv4 address of the internal network interface card (NIC) for this computer.</span></span>
    
- <span data-ttu-id="d62e4-107">配置与此计算机关联的**访问边缘服务\*\*\*\*外部 IPv4 地址**</span><span class="sxs-lookup"><span data-stu-id="d62e4-107">You configure the **Access Edge service** **External IPv4 address** associated with this computer</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d62e4-108">如果选择将单个 IP 地址用于边缘服务器配置，则只能编辑访问边缘服务的外部 IPv4 地址。</span><span class="sxs-lookup"><span data-stu-id="d62e4-108">If you selected to use a single IP address for the Edge Server configuration, you will only be able to edit the external IPv4 address for the Access Edge service.</span></span> <span data-ttu-id="d62e4-109">其他边缘服务将与访问边缘服务共享相同的 IPv4 地址。</span><span class="sxs-lookup"><span data-stu-id="d62e4-109">The other Edge services will share the same IPv4 address as the Access Edge service.</span></span> 
  
- <span data-ttu-id="d62e4-110">如果可编辑，请配置与此计算机关联的**Web 会议服务\*\*\*\*外部 IPv4 地址**</span><span class="sxs-lookup"><span data-stu-id="d62e4-110">If available to edit, you configure the **Web Conferencing service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="d62e4-111">如果可编辑，则配置**A/V 边缘服务**与此计算机关联的**外部 IPv4 地址**</span><span class="sxs-lookup"><span data-stu-id="d62e4-111">If available to edit, you configure the **A/V Edge service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="d62e4-112">如果可供编辑，则配置与该计算机关联的“启用 NAT 的公共 IPv4 地址”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d62e4-112">If available to edit, you configure the **NAT-enabled public IPv4 address** associated with this computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d62e4-113">如果选择为 A/V 边缘服务提供网络地址转换 (NAT) ，则 **启用 NAT 的公用 IPv4 地址** 的 configuration 属性将仅可供编辑。</span><span class="sxs-lookup"><span data-stu-id="d62e4-113">The configuration property for **NAT-enabled public IPv4 address** will only be available to edit if you chose to provide network address translation (NAT) for the A/V Edge service</span></span>
  
  <span data-ttu-id="d62e4-114">**确定** 接受更改并通过对话框提交更改。</span><span class="sxs-lookup"><span data-stu-id="d62e4-114">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="d62e4-115">**取消** 放弃更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="d62e4-115">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="d62e4-116">**帮助** 显示此帮助屏幕。</span><span class="sxs-lookup"><span data-stu-id="d62e4-116">**Help** Displays this help screen.</span></span>
  

