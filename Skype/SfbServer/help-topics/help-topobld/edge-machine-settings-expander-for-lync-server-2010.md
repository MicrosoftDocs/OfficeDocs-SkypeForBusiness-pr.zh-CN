---
title: 适合于 Lync Server 2010 的 Edge 机器设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: '若要将 Edge 服务器计算机的属性作为单个边缘服务器或边缘池中的成员计算机进行编辑, 请配置服务器名称和 IP 地址配置设置:'
ms.openlocfilehash: c9201cfde9f19391e1cee351de6d4efac00be9dd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302334"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a><span data-ttu-id="1f2c4-103">适合于 Lync Server 2010 的 Edge 机器设置</span><span class="sxs-lookup"><span data-stu-id="1f2c4-103">Edge Machine Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="1f2c4-104">若要将 Edge 服务器计算机的属性作为单个边缘服务器或边缘池中的成员计算机进行编辑, 请配置**服务器名称和 IP 地址配置**设置:</span><span class="sxs-lookup"><span data-stu-id="1f2c4-104">To edit the properties for Edge Server computers as an single Edge Server or as member computers in an Edge pool, you configure **Server name and IP address configuration** settings:</span></span>
  
- <span data-ttu-id="1f2c4-105">**内部名称或 FQDN**: 键入在域名系统 (DNS) 中引用的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="1f2c4-105">**Internal name or FQDN**: Type the name of the computer as it is referenced in the domain name system (DNS).</span></span> 
    
- <span data-ttu-id="1f2c4-106">**内部 IPv4 地址**: 键入此计算机的内部网络接口卡 (NIC) 的 IPv4 地址。</span><span class="sxs-lookup"><span data-stu-id="1f2c4-106">**Internal IPv4 address**: Type the IPv4 address of the internal network interface card (NIC) for this computer.</span></span>
    
- <span data-ttu-id="1f2c4-107">配置与此计算机关联的**外部 IPv4 地址**的**访问边缘服务**</span><span class="sxs-lookup"><span data-stu-id="1f2c4-107">You configure the **Access Edge service** **External IPv4 address** associated with this computer</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1f2c4-108">如果您选择将单个 IP 地址用于边缘服务器配置, 则只能编辑访问边缘服务的外部 IPv4 地址。</span><span class="sxs-lookup"><span data-stu-id="1f2c4-108">If you selected to use a single IP address for the Edge Server configuration, you will only be able to edit the external IPv4 address for the Access Edge service.</span></span> <span data-ttu-id="1f2c4-109">其他边缘服务将与访问边缘服务共享相同的 IPv4 地址。</span><span class="sxs-lookup"><span data-stu-id="1f2c4-109">The other Edge services will share the same IPv4 address as the Access Edge service.</span></span> 
  
- <span data-ttu-id="1f2c4-110">如果可编辑, 请配置**Web 会议服务**与此计算机关联的**外部 IPv4 地址**</span><span class="sxs-lookup"><span data-stu-id="1f2c4-110">If available to edit, you configure the **Web Conferencing service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="1f2c4-111">如果可编辑, 则配置**A/V 边缘服务**与此计算机关联的**外部 IPv4 地址**</span><span class="sxs-lookup"><span data-stu-id="1f2c4-111">If available to edit, you configure the **A/V Edge service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="1f2c4-112">如果可编辑, 请配置与此计算机关联的**支持 NAT 的公共 IPv4 地址**。</span><span class="sxs-lookup"><span data-stu-id="1f2c4-112">If available to edit, you configure the **NAT-enabled public IPv4 address** associated with this computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1f2c4-113">如果您选择为 A/V 边缘服务提供网络地址转换 (NAT), 则**启用 NAT 的公共 IPv4 地址**的配置属性将仅可供编辑。</span><span class="sxs-lookup"><span data-stu-id="1f2c4-113">The configuration property for **NAT-enabled public IPv4 address** will only be available to edit if you chose to provide network address translation (NAT) for the A/V Edge service</span></span>
  
  <span data-ttu-id="1f2c4-114">**确定** 接受更改并通过对话框提交更改。</span><span class="sxs-lookup"><span data-stu-id="1f2c4-114">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="1f2c4-115">**取消** 放弃更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="1f2c4-115">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="1f2c4-116">**帮助** 显示此帮助屏幕。</span><span class="sxs-lookup"><span data-stu-id="1f2c4-116">**Help** Displays this help screen.</span></span>
  

