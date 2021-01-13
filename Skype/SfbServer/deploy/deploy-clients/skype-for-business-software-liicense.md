---
title: Skype 会议室系统 Skype for Business 软件许可证
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: 阅读本主题，了解如何检查你是否拥有 Skype for Business 软件批量许可证。
ms.openlocfilehash: 20e04f69ba5a931bae6ac8598567165a7a6043a4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833922"
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="f6b48-103">Skype 会议室系统：Skype for Business 软件许可证</span><span class="sxs-lookup"><span data-stu-id="f6b48-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="f6b48-104">阅读本主题，了解如何检查你是否拥有 Skype for Business 软件批量许可证。</span><span class="sxs-lookup"><span data-stu-id="f6b48-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="f6b48-105">Skype 会议室系统使用已安装的 Skype for Business 客户端，这需要软件批量许可证。</span><span class="sxs-lookup"><span data-stu-id="f6b48-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="f6b48-106">部署第一个 Skype 会议室系统之前，请了解部署的批量许可证状态 - 使用密钥管理服务器 (KMS) 或 MAK (多次激活密钥) 。</span><span class="sxs-lookup"><span data-stu-id="f6b48-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="f6b48-107">密钥管理服务器 (KMS) </span><span class="sxs-lookup"><span data-stu-id="f6b48-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="f6b48-108">如果 KMS 已就位并将分发 Skype for Business 批量许可证激活，Skype 会议室系统将自动激活 Skype for Business 客户端。</span><span class="sxs-lookup"><span data-stu-id="f6b48-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="f6b48-109">若要了解 KMS 是否就位：</span><span class="sxs-lookup"><span data-stu-id="f6b48-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="f6b48-110">在命令提示符下，运行：  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="f6b48-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="f6b48-111">有关详细信息，请参阅如何通过 DNS 发现 Office 和 [Windows KMS 主机并删除未经授权的实例](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx)。</span><span class="sxs-lookup"><span data-stu-id="f6b48-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="f6b48-112">若要设置 KMS，请参阅 [Office 2013](https://technet.microsoft.com/library/ee624357.aspx) 的 KMS 激活和用于 KMS 的 [VLKs 和 Office 2013 的 Active Directory 激活](https://technet.microsoft.com/library/dn385360.aspx)</span><span class="sxs-lookup"><span data-stu-id="f6b48-112">To set up a KMS, see [KMS activation of Office 2013](https://technet.microsoft.com/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span></span>
  
<span data-ttu-id="f6b48-113">适用于 Lync 的 Office 2013 通用批量许可证密钥：2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (此密钥会导致 Skype 会议室系统查找网络上 KMS。) </span><span class="sxs-lookup"><span data-stu-id="f6b48-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="f6b48-114">批量许可 () VLSC (MAK 密钥) </span><span class="sxs-lookup"><span data-stu-id="f6b48-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="f6b48-115">如果客户使用任何其他批量许可软件，IT 部门将使用 VLSC (VLA) 软件激活和批量许可协议。</span><span class="sxs-lookup"><span data-stu-id="f6b48-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="f6b48-116">这也将使公司能够购买 Skype for Business VL 激活，之后公司可以获取 MAK 以在 Skype 会议室系统管理控制台中输入。</span><span class="sxs-lookup"><span data-stu-id="f6b48-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="f6b48-117">具有 VLA 的客户必须知道其 VLSC 凭据，这些凭据将用于管理协议并获取 MAK。</span><span class="sxs-lookup"><span data-stu-id="f6b48-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="f6b48-118">如果不确定，客户的财务部门应能够确认客户是否支付 VLA 费用。</span><span class="sxs-lookup"><span data-stu-id="f6b48-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="f6b48-119">若要获取 MAK，访问批量许可服务中心以查看协议，并下载 MAK (产品) 。</span><span class="sxs-lookup"><span data-stu-id="f6b48-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="f6b48-120">有关详细信息，请转到 [批量许可服务中心](https://www.microsoft.com/Licensing/servicecenter/default.aspx)。</span><span class="sxs-lookup"><span data-stu-id="f6b48-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a><span data-ttu-id="f6b48-121">没有 VLSC 访问权限的 MICROSOFT 365 或 Office 365 MAK</span><span class="sxs-lookup"><span data-stu-id="f6b48-121">MAK for Microsoft 365 or Office 365 without VLSC access</span></span>

<span data-ttu-id="f6b48-122">如果客户没有批量许可协议，Skype for Business 激活将更加难以管理。</span><span class="sxs-lookup"><span data-stu-id="f6b48-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="f6b48-123">但是，没有 VLSC 访问权限的 Microsoft 365 和 Office 365 客户可以通过向销售 Skype 会议室系统的 OEM 提供以下信息来获取促销 MAK：</span><span class="sxs-lookup"><span data-stu-id="f6b48-123">However, Microsoft 365 and Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="f6b48-124">公司名称</span><span class="sxs-lookup"><span data-stu-id="f6b48-124">Company name</span></span>
    
- <span data-ttu-id="f6b48-125">部署联系人姓名、电子邮件和电话号码</span><span class="sxs-lookup"><span data-stu-id="f6b48-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="f6b48-126">已部署的系统数</span><span class="sxs-lookup"><span data-stu-id="f6b48-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="f6b48-127">部署日期</span><span class="sxs-lookup"><span data-stu-id="f6b48-127">Deployment date</span></span>
    
- <span data-ttu-id="f6b48-128">如果客户有 Microsoft 技术客户经理，则 TAM 的姓名和联系信息</span><span class="sxs-lookup"><span data-stu-id="f6b48-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
    

