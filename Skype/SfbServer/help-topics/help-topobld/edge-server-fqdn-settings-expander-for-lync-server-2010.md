---
title: Lync Server 2010 的边缘服务器 FQDN 设置扩展器
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 若要定义的属性外部设置下，配置以下设置：
ms.openlocfilehash: d925da792e2c2c296707a99d6a4ae6b29c0545a9
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375606"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="8f49a-103">Lync Server 2010 的边缘服务器 FQDN 设置扩展器</span><span class="sxs-lookup"><span data-stu-id="8f49a-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="8f49a-104">若要定义的属性**外部设置**下，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="8f49a-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="8f49a-105">选择**启用单独的 FQDN 和 IP 地址的 web 会议和 A / V**复选框，如果您想要定义不同池 FQDN 和 IP 地址的 web 会议和音频/视频。</span><span class="sxs-lookup"><span data-stu-id="8f49a-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8f49a-106">如果您选择不选中单独的 FQDN 和 IP 地址的复选框，您必须为每个边缘服务器所提供的三个服务提供不同的端口。</span><span class="sxs-lookup"><span data-stu-id="8f49a-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="8f49a-107">是配置的唯一完全限定的域名称是与访问边缘服务相关联的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="8f49a-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="8f49a-108">选择**A / V 边缘服务启用 NAT**复选框，如果您希望 A / V 边缘服务使用网络地址转换 (NAT) IP 地址和配置。</span><span class="sxs-lookup"><span data-stu-id="8f49a-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="8f49a-109">对于已启用的边缘服务，键入一个**池 FQDN**和端口**端口**下</span><span class="sxs-lookup"><span data-stu-id="8f49a-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="8f49a-110">定义**访问边缘服务**的池 FQDN 和唯一标识服务的端口。</span><span class="sxs-lookup"><span data-stu-id="8f49a-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="8f49a-111">定义**Web 会议边缘服务**的池 FQDN (如果启用单独的 FQDN 和 IP 地址的 web 会议和 A / V 未选中) 和唯一标识服务的端口。</span><span class="sxs-lookup"><span data-stu-id="8f49a-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="8f49a-112">定义**A / V 边缘服务**池 FQDN (如果启用单独的 FQDN 和 IP 地址的 web 会议和 A / V 未选中) 和唯一标识服务的端口。</span><span class="sxs-lookup"><span data-stu-id="8f49a-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
  <span data-ttu-id="8f49a-113">**确定** 接受更改并通过对话框提交更改。</span><span class="sxs-lookup"><span data-stu-id="8f49a-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="8f49a-114">**取消** 放弃更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="8f49a-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="8f49a-115">**帮助** 显示此帮助屏幕。</span><span class="sxs-lookup"><span data-stu-id="8f49a-115">**Help** Displays this help screen.</span></span>
  

