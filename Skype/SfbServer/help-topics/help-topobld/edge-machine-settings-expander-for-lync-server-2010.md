---
title: Lync Server 2010 的边缘计算机设置扩展器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 若要将边缘服务器计算机的属性编辑为单个边缘服务器或作为边缘池中的成员计算机，请配置服务器名称和 IP 地址配置设置：
ms.openlocfilehash: e25f68ec510cf15cd58872a8c584dc71aa939f48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807132"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a><span data-ttu-id="c1ad8-103">Lync Server 2010 的边缘计算机设置扩展器</span><span class="sxs-lookup"><span data-stu-id="c1ad8-103">Edge Machine Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="c1ad8-104">若要将边缘服务器计算机的属性编辑为单个边缘服务器或作为边缘池中的成员计算机，请配置服务器名称和 **IP 地址配置** 设置：</span><span class="sxs-lookup"><span data-stu-id="c1ad8-104">To edit the properties for Edge Server computers as an single Edge Server or as member computers in an Edge pool, you configure **Server name and IP address configuration** settings:</span></span>
  
- <span data-ttu-id="c1ad8-105">**内部名称或 FQDN**：键入在域名系统 (DNS) 中引用的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="c1ad8-105">**Internal name or FQDN**: Type the name of the computer as it is referenced in the domain name system (DNS).</span></span> 
    
- <span data-ttu-id="c1ad8-106">**内部 IPv4 地址**：键入该计算机内部网络接口卡 (NIC) 的 IPv4 地址。</span><span class="sxs-lookup"><span data-stu-id="c1ad8-106">**Internal IPv4 address**: Type the IPv4 address of the internal network interface card (NIC) for this computer.</span></span>
    
- <span data-ttu-id="c1ad8-107">配置与此 **计算机关联的访问** 边缘服务外部 **IPv4** 地址</span><span class="sxs-lookup"><span data-stu-id="c1ad8-107">You configure the **Access Edge service** **External IPv4 address** associated with this computer</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c1ad8-108">如果选择将单个 IP 地址用于边缘服务器配置，则只能编辑访问边缘服务的外部 IPv4 地址。</span><span class="sxs-lookup"><span data-stu-id="c1ad8-108">If you selected to use a single IP address for the Edge Server configuration, you will only be able to edit the external IPv4 address for the Access Edge service.</span></span> <span data-ttu-id="c1ad8-109">其他边缘服务将共享与访问边缘服务相同的 IPv4 地址。</span><span class="sxs-lookup"><span data-stu-id="c1ad8-109">The other Edge services will share the same IPv4 address as the Access Edge service.</span></span> 
  
- <span data-ttu-id="c1ad8-110">如果可供编辑，则配置与此计算机关联的 **Web** 会议服务外部 **IPv4** 地址</span><span class="sxs-lookup"><span data-stu-id="c1ad8-110">If available to edit, you configure the **Web Conferencing service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="c1ad8-111">如果可供编辑，请配置与此计算机关联的 **A/V 边缘** 服务外部 **IPv4** 地址</span><span class="sxs-lookup"><span data-stu-id="c1ad8-111">If available to edit, you configure the **A/V Edge service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="c1ad8-112">如果可供编辑，则配置与该计算机关联的“启用 NAT 的公共 IPv4 地址”。</span><span class="sxs-lookup"><span data-stu-id="c1ad8-112">If available to edit, you configure the **NAT-enabled public IPv4 address** associated with this computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c1ad8-113">只有选择为 A/V 边缘服务提供网络地址转换 (NAT) ，启用 NAT 的公共 **IPv4** 地址的配置属性才可供编辑</span><span class="sxs-lookup"><span data-stu-id="c1ad8-113">The configuration property for **NAT-enabled public IPv4 address** will only be available to edit if you chose to provide network address translation (NAT) for the A/V Edge service</span></span>
  
  <span data-ttu-id="c1ad8-114">**确定** 接受更改并通过对话框提交更改。</span><span class="sxs-lookup"><span data-stu-id="c1ad8-114">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="c1ad8-115">**取消** 放弃更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="c1ad8-115">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="c1ad8-116">**帮助** 显示此帮助屏幕。</span><span class="sxs-lookup"><span data-stu-id="c1ad8-116">**Help** Displays this help screen.</span></span>
  

