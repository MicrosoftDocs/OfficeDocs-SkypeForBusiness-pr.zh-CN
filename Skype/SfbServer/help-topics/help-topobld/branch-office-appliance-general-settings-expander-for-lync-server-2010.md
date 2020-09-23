---
title: Lync Server 2010 分支机构设备常规设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a41754a-4653-4845-afb6-4a74b2edfeb4
description: 若要编辑 Survivable Branch 装置或 Survivable 分支服务器的属性，请在 "常规" 下配置：
ms.openlocfilehash: 5bdcc283ce9f503af307e37a7c2f76c922d5facb
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216153"
---
# <a name="branch-office-appliance-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="f227f-103">Lync Server 2010 分支机构设备常规设置扩展器</span><span class="sxs-lookup"><span data-stu-id="f227f-103">Branch Office Appliance General Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="f227f-104">若要编辑 Survivable Branch 装置或 Survivable 分支服务器的属性，请在 " **常规**" 下配置：</span><span class="sxs-lookup"><span data-stu-id="f227f-104">To edit properties for Survivable Branch Appliance or Survivable Branch Server , under **General**, you configure:</span></span>
  
- <span data-ttu-id="f227f-105">**FQDN**：键入 Survivable 分支设备或 Survivable 分支服务器的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="f227f-105">**FQDN**: You type the fully qualified domain name of the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <span data-ttu-id="f227f-106">**使用所有已配置的 ip 地址** 使用 Survivable 分支设备或 Survivable 分支服务器上配置的 ip 地址来实现所有目的。</span><span class="sxs-lookup"><span data-stu-id="f227f-106">**Use all configured IP addresses** uses the IP addresses configured on the Survivable Branch Appliance or Survivable Branch Server for all purposes.</span></span>
    
    <span data-ttu-id="f227f-107">**将服务用途限制为所选 IP 地址** 配置定义服务器的不同地址和要用于 PSTN 的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="f227f-107">**Limit service usage to selected IP addresses** You configure the distinct address that define the server and the IP address to be used for PSTN.</span></span>
    
    <span data-ttu-id="f227f-108">**主 IP 地址**：除了 PSTN 关联的功能，针对所有用途定义和配置此 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="f227f-108">**Primary IP address**: The IP address is defined and configured for all purposes, except for PSTN-associated functions.</span></span>
    
    <span data-ttu-id="f227f-109">**PSTN IP 地址**：与公用电话交换网 (PSTN) 功能关联的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="f227f-109">**PSTN IP address**: The IP address associated with the public switched telephone network (PSTN) functions.</span></span>
    
- <span data-ttu-id="f227f-110">您可以配置 **关联** 以确保配置了其他服务器角色，并将其与 Survivable 分支设备或 Survivable 分支服务器相关联。</span><span class="sxs-lookup"><span data-stu-id="f227f-110">You configure **Associations** to ensure that other server roles are configured and associated with the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <span data-ttu-id="f227f-111">**关联存档服务器** 从列表中选择要与 Survivable 分支装置或 Survivable 分支服务器相关联的存档服务器</span><span class="sxs-lookup"><span data-stu-id="f227f-111">**Associate Archiving Server** Select from the list the Archiving Server that you want to associate with the Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="f227f-112">如果尚未创建要与此 Survivable 分支设备或 Survivable 分支服务器关联的存档服务器，请单击 " **新建** "。</span><span class="sxs-lookup"><span data-stu-id="f227f-112">Click **New** if you have not created the Archiving Server that you want to associate with this Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="f227f-113">**关联监视服务器** 从列表中选择要与 Survivable 分支设备或 Survivable 分支服务器关联的监视服务器</span><span class="sxs-lookup"><span data-stu-id="f227f-113">**Associate Monitoring Server** Select from the list the Monitoring Server that you want to associate with the Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="f227f-114">如果尚未创建要与此 Survivable 分支设备或 Survivable 分支服务器关联的监视服务器，请单击 " **新建** "。</span><span class="sxs-lookup"><span data-stu-id="f227f-114">Click **New** if you have not created the Monitoring Server that you want to associate with this Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="f227f-115">\*\*将媒体组件的边缘池 (关联) \*\* 从列表中选择要与 Survivable 分支设备或 Survivable 分支服务器关联的边缘服务器或边缘池</span><span class="sxs-lookup"><span data-stu-id="f227f-115">**Associate Edge pool (for media components)** Select from the list the Edge Server or Edge pool that you want to associate with the Survivable Branch Appliance or Survivable Branch Server</span></span>
    
  <span data-ttu-id="f227f-116">**确定** 接受更改并通过对话框提交更改。</span><span class="sxs-lookup"><span data-stu-id="f227f-116">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="f227f-117">**取消** 放弃更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="f227f-117">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="f227f-118">**帮助** 显示此帮助屏幕。</span><span class="sxs-lookup"><span data-stu-id="f227f-118">**Help** Displays this help screen.</span></span>
  

