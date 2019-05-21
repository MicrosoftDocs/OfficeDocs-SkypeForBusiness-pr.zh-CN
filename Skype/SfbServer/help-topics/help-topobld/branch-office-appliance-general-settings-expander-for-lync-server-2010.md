---
title: Lync Server 2010 分支机构设备常规设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a41754a-4653-4845-afb6-4a74b2edfeb4
description: '若要编辑 Survivable 分支装置或 Survivable 分支服务器的属性, 请在 "常规" 下配置:'
ms.openlocfilehash: e0c2aba5998b2eb4288c63fd50f47e8e8bb75033
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301580"
---
# <a name="branch-office-appliance-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="b9cba-103">Lync Server 2010 分支机构设备常规设置扩展器</span><span class="sxs-lookup"><span data-stu-id="b9cba-103">Branch Office Appliance General Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="b9cba-104">若要编辑 Survivable 分支装置或 Survivable 分支服务器的属性, 请在 "**常规**" 下配置:</span><span class="sxs-lookup"><span data-stu-id="b9cba-104">To edit properties for Survivable Branch Appliance or Survivable Branch Server , under **General**, you configure:</span></span>
  
- <span data-ttu-id="b9cba-105">**FQDN**: 键入 Survivable 分支装置或 Survivable 分支服务器的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="b9cba-105">**FQDN**: You type the fully qualified domain name of the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <span data-ttu-id="b9cba-106">**使用所有已配置的 ip 地址**使用 Survivable 分支装置或 Survivable 分支服务器上配置的 ip 地址进行所有用途。</span><span class="sxs-lookup"><span data-stu-id="b9cba-106">**Use all configured IP addresses** uses the IP addresses configured on the Survivable Branch Appliance or Survivable Branch Server for all purposes.</span></span>
    
    <span data-ttu-id="b9cba-107">**将服务用途限制为所选 IP 地址** 配置定义服务器的不同地址和要用于 PSTN 的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="b9cba-107">**Limit service usage to selected IP addresses** You configure the distinct address that define the server and the IP address to be used for PSTN.</span></span>
    
    <span data-ttu-id="b9cba-108">**主 IP 地址**：除了 PSTN 关联的功能，针对所有用途定义和配置此 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="b9cba-108">**Primary IP address**: The IP address is defined and configured for all purposes, except for PSTN-associated functions.</span></span>
    
    <span data-ttu-id="b9cba-109">**PSTN IP 地址**：与公用电话交换网 (PSTN) 功能关联的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="b9cba-109">**PSTN IP address**: The IP address associated with the public switched telephone network (PSTN) functions.</span></span>
    
- <span data-ttu-id="b9cba-110">配置**关联**以确保其他服务器角色已配置并与 Survivable 分支装置或 Survivable 分支服务器相关联。</span><span class="sxs-lookup"><span data-stu-id="b9cba-110">You configure **Associations** to ensure that other server roles are configured and associated with the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <span data-ttu-id="b9cba-111">**关联存档服务器**从列表中选择要与 Survivable 分支装置或 Survivable 分支服务器相关联的存档服务器</span><span class="sxs-lookup"><span data-stu-id="b9cba-111">**Associate Archiving Server** Select from the list the Archiving Server that you want to associate with the Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="b9cba-112">如果尚未创建要与此 Survivable 分支装置或 Survivable 分支服务器相关联的存档服务器, 请单击 "**新建**"。</span><span class="sxs-lookup"><span data-stu-id="b9cba-112">Click **New** if you have not created the Archiving Server that you want to associate with this Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="b9cba-113">**关联监视服务器**从列表中选择要与 Survivable 分支装置或 Survivable 分支服务器相关联的监视服务器</span><span class="sxs-lookup"><span data-stu-id="b9cba-113">**Associate Monitoring Server** Select from the list the Monitoring Server that you want to associate with the Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="b9cba-114">如果尚未创建要与此 Survivable 分支装置或 Survivable 分支服务器相关联的监视服务器, 请单击 "**新建**"。</span><span class="sxs-lookup"><span data-stu-id="b9cba-114">Click **New** if you have not created the Monitoring Server that you want to associate with this Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="b9cba-115">**关联边界池 (适用于媒体组件)** 从列表中选择要与 Survivable 分支装置或 Survivable 分支服务器相关联的边缘服务器或边缘池</span><span class="sxs-lookup"><span data-stu-id="b9cba-115">**Associate Edge pool (for media components)** Select from the list the Edge Server or Edge pool that you want to associate with the Survivable Branch Appliance or Survivable Branch Server</span></span>
    
  <span data-ttu-id="b9cba-116">**确定** 接受更改并通过对话框提交更改。</span><span class="sxs-lookup"><span data-stu-id="b9cba-116">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="b9cba-117">**取消** 放弃更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="b9cba-117">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="b9cba-118">**帮助** 显示此帮助屏幕。</span><span class="sxs-lookup"><span data-stu-id="b9cba-118">**Help** Displays this help screen.</span></span>
  

