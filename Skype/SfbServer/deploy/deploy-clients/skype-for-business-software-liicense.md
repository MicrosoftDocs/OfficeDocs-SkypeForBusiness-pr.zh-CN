---
title: Skype 会议室系统 Skype 业务软件许可证
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: 阅读本主题，了解如何检查你是否拥有 Skype for Business 软件批量许可证。
ms.openlocfilehash: e4ba03dacdce0056cb130299f551921042a6790d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207929"
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="0c879-103">Skype 会议室系统：Skype for Business 软件许可证</span><span class="sxs-lookup"><span data-stu-id="0c879-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="0c879-104">阅读本主题，了解如何检查你是否拥有 Skype for Business 软件批量许可证。</span><span class="sxs-lookup"><span data-stu-id="0c879-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="0c879-105">Skype 会议室系统使用业务的客户端，需要使用软件的批量许可证已安装的 Skype。</span><span class="sxs-lookup"><span data-stu-id="0c879-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="0c879-106">部署第一个 Skype 会议室系统之前, 查找出部署-使用密钥管理服务器 (KMS) 或者多次激活密钥 (MAK) 批量许可证状态。</span><span class="sxs-lookup"><span data-stu-id="0c879-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="0c879-107">密钥管理服务器 (KMS)</span><span class="sxs-lookup"><span data-stu-id="0c879-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="0c879-108">如果 KMS 措施，并将分发 Skype 的业务批量许可激活，Skype 会议室系统将自动激活业务客户端 Skype。</span><span class="sxs-lookup"><span data-stu-id="0c879-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="0c879-109">要了解 KMS 是否准备就绪，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0c879-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="0c879-110">从命令提示符处运行：`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="0c879-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="0c879-111">有关详细信息，请参阅[How to 发现 DNS 通过 Office 和 Windows KMS 主机，并删除未经授权的实例](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0c879-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="0c879-112">若要设置 KMS，请参阅[KMS activation of Office 2013](https://technet.microsoft.com/library/ee624357.aspx)和[Office 2013 的 KMS 和 Active Directory 激活的 Gvlk](https://technet.microsoft.com/library/dn385360.aspx)</span><span class="sxs-lookup"><span data-stu-id="0c879-112">To set up a KMS, see [KMS activation of Office 2013](https://technet.microsoft.com/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span></span>
  
<span data-ttu-id="0c879-113">Lync 的 office 2013 通用批量许可证密钥： 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R （此项将使 Skype 会议室系统，以查找网络上 KMS）。</span><span class="sxs-lookup"><span data-stu-id="0c879-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="0c879-114">来自批量许可服务中心 (VLSC) 的多次激活密钥 (MAK)</span><span class="sxs-lookup"><span data-stu-id="0c879-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="0c879-115">如果客户使用任何其他批量许可证软件，则 IT 部门将使用 VLSC 管理软件激活和批量许可协议 (VLA)。</span><span class="sxs-lookup"><span data-stu-id="0c879-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="0c879-116">这样也会启用，公司可以购买业务 VL 激活，公司可以其后获取的 Skype 会议室系统管理控制台中输入 MAK Skype。</span><span class="sxs-lookup"><span data-stu-id="0c879-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="0c879-117">具有 VLA 的客户必须知道其 VLSC 凭据，将使用这些凭据来管理协议和获取 MAK。</span><span class="sxs-lookup"><span data-stu-id="0c879-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="0c879-118">如果不确定的则客户的财务部门应能够确认客户如果已支付的 VLA。</span><span class="sxs-lookup"><span data-stu-id="0c879-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="0c879-119">要获得 MAK，请访问批量许可服务中心以查看协议并下载产品密钥 (MAK)。</span><span class="sxs-lookup"><span data-stu-id="0c879-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="0c879-120">有关详细信息，转到[批量许可服务中心](https://www.microsoft.com/Licensing/servicecenter/default.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0c879-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-office-365-without-vlsc-access"></a><span data-ttu-id="0c879-121">适用于 Office 365、不含 VLSC 访问的 MAK</span><span class="sxs-lookup"><span data-stu-id="0c879-121">MAK for Office 365 without VLSC access</span></span>

<span data-ttu-id="0c879-122">如果客户没有批量许可证协议，业务激活的 Skype 将更难管理。</span><span class="sxs-lookup"><span data-stu-id="0c879-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="0c879-123">但是，没有 VLSC 访问 Office 365 客户可以获取促销 MAK 通过为 OEM 提供以下信息销售 Skype 会议室系统：</span><span class="sxs-lookup"><span data-stu-id="0c879-123">However, Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="0c879-124">公司名称</span><span class="sxs-lookup"><span data-stu-id="0c879-124">Company name</span></span>
    
- <span data-ttu-id="0c879-125">部署联系人姓名、电子邮件和电话号码</span><span class="sxs-lookup"><span data-stu-id="0c879-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="0c879-126">部署系统数</span><span class="sxs-lookup"><span data-stu-id="0c879-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="0c879-127">部署日期</span><span class="sxs-lookup"><span data-stu-id="0c879-127">Deployment date</span></span>
    
- <span data-ttu-id="0c879-128">如果客户有 Microsoft 技术帐户管理器中，TAM 的姓名和联系人信息</span><span class="sxs-lookup"><span data-stu-id="0c879-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
    

