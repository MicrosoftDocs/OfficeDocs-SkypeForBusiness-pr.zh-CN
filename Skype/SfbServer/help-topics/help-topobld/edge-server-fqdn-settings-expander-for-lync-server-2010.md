---
title: Lync Server 2010 中的边缘服务器 FQDN 设置扩展
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 要定义在外部设置下面的属性，请进行以下配置：
ms.openlocfilehash: 2954c9add818e67f471cfb97893fef42e862bea3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="fef67-103">Lync Server 2010 中的边缘服务器 FQDN 设置扩展</span><span class="sxs-lookup"><span data-stu-id="fef67-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="fef67-104">要定义在**外部设置**下面的属性，请进行以下配置：</span><span class="sxs-lookup"><span data-stu-id="fef67-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="fef67-105">选择**启用单独的 FQDN 和 IP 地址的 web 会议和 A / V**复选框如果您希望定义不同的池的 FQDN 和 IP 地址的 web 会议、 音频/视频。</span><span class="sxs-lookup"><span data-stu-id="fef67-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fef67-106">如果您选择不选择独立的 FQDN 和 IP 地址的复选框，必须为每个边缘服务器提供的三种服务提供不同的端口。</span><span class="sxs-lookup"><span data-stu-id="fef67-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="fef67-107">只是配置的完全合格的域名名称是与访问边缘服务相关联的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fef67-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="fef67-108">选择**A / V 边缘服务是启用 NAT**复选框如果您希望将 A / V 边缘服务使用网络地址转换 (NAT) 的 IP 地址和配置。</span><span class="sxs-lookup"><span data-stu-id="fef67-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="fef67-109">对于已启用的边缘服务，键入**池的 FQDN**和**端口**下的端口。</span><span class="sxs-lookup"><span data-stu-id="fef67-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="fef67-110">定义**访问边缘服务**池的 FQDN，并唯一地标识该服务的端口。</span><span class="sxs-lookup"><span data-stu-id="fef67-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="fef67-111">定义**Web 会议边缘服务**池的 FQDN (如果启用单独的 FQDN 和 IP 地址的 web 会议和 A / V 未被选中) 唯一地标识该服务的端口。</span><span class="sxs-lookup"><span data-stu-id="fef67-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="fef67-112">定义**A / V 边缘服务**池的 FQDN (如果启用单独的 FQDN 和 IP 地址的 web 会议和 A / V 未被选中) 唯一地标识该服务的端口。</span><span class="sxs-lookup"><span data-stu-id="fef67-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
 <span data-ttu-id="fef67-113">**确定** 接受更改并通过对话框提交更改。</span><span class="sxs-lookup"><span data-stu-id="fef67-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="fef67-114">**取消** 放弃更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="fef67-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="fef67-115">**帮助** 显示此帮助屏幕。</span><span class="sxs-lookup"><span data-stu-id="fef67-115">**Help** Displays this help screen.</span></span>
  

