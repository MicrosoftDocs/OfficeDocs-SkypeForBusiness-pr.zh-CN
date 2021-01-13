---
title: 查看 Skype for Business Server 2015 中的管理员报告
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22d480ea-cd64-4d09-99fe-96e997570844
description: 管理员报告是有关部署和操作的详细信息。 报告基于设计网站中标记的选择生成。 设计师可通过编辑网络图，并为服务器、池和负载平衡器定义完整的 IP 地址和完全限定域名 (FQDN)，来进一步向管理报告中添加值。
ms.openlocfilehash: b8c18dcfef28ac93e8c2036fee7f7b105f5c69bd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823342"
---
# <a name="review-the-administrator-reports-in-skype-for-business-server-2015"></a><span data-ttu-id="25d09-105">查看 Skype for Business Server 2015 中的管理员报告</span><span class="sxs-lookup"><span data-stu-id="25d09-105">Review the Administrator Reports in Skype for Business Server 2015</span></span>

<span data-ttu-id="25d09-106">管理员报告是有关部署和操作的详细信息。</span><span class="sxs-lookup"><span data-stu-id="25d09-106">The Administrator Reports are detailed information for deployment and operations.</span></span> <span data-ttu-id="25d09-107">报告基于设计网站中标记 **的选择生成**。</span><span class="sxs-lookup"><span data-stu-id="25d09-107">The reports are generated based on the selections marked in **Design Sites**.</span></span> <span data-ttu-id="25d09-108">设计师可通过编辑网络图，并为服务器、池和负载平衡器定义完整的 IP 地址和完全限定域名 (FQDN)，来进一步向管理报告中添加值。</span><span class="sxs-lookup"><span data-stu-id="25d09-108">The designer can further add value to the Administrator Reports by editing the network diagrams and defining the complete IP addresses and fully qualified domain names (FQDNs) for servers, pools, and load balancers.</span></span>

<span data-ttu-id="25d09-109">管理员报告功能允许您：</span><span class="sxs-lookup"><span data-stu-id="25d09-109">The Administrator reports feature allows you to:</span></span>

- [<span data-ttu-id="25d09-110">查看摘要报告</span><span class="sxs-lookup"><span data-stu-id="25d09-110">Review the Summary Report</span></span>](review-the-administrator-reports.md#Summary_report)

- [<span data-ttu-id="25d09-111">查看证书报告</span><span class="sxs-lookup"><span data-stu-id="25d09-111">Review the Certificates Report</span></span>](review-the-administrator-reports.md#Certificates_Report)

- [<span data-ttu-id="25d09-112">查看防火墙报告</span><span class="sxs-lookup"><span data-stu-id="25d09-112">Review the Firewall Report</span></span>](review-the-administrator-reports.md#Firewall_report)

- [<span data-ttu-id="25d09-113">查看 DNS 报告</span><span class="sxs-lookup"><span data-stu-id="25d09-113">Review the DNS Report</span></span>](review-the-administrator-reports.md#DNS_Report)

## <a name="review-the-summary-report"></a><span data-ttu-id="25d09-114">查看摘要报告</span><span class="sxs-lookup"><span data-stu-id="25d09-114">Review the Summary Report</span></span>
<span data-ttu-id="25d09-115"><a name="Summary_report"> </a></span><span class="sxs-lookup"><span data-stu-id="25d09-115"><a name="Summary_report"> </a></span></span>

<span data-ttu-id="25d09-116">Skype for Business 管理员报告是详细记录设计的四个有价值的报告中的第一个报告。</span><span class="sxs-lookup"><span data-stu-id="25d09-116">The Skype for Business Administrator Report is the first of four valuable reports that document your design in detail.</span></span> <span data-ttu-id="25d09-117">此报告和其他三个相关报告中的信息对信息技术团队很有用：</span><span class="sxs-lookup"><span data-stu-id="25d09-117">The information in this report, and the other three associated reports, is useful for your Information Technology Teams:</span></span>

![一般摘要管理报告](../../media/General_Summary_Report_Admin_Report.png)

<span data-ttu-id="25d09-119">摘要报告列出了与边缘网络关联的常规配置信息。</span><span class="sxs-lookup"><span data-stu-id="25d09-119">The Summary Report lists general configuration information associated with your Edge network.</span></span> <span data-ttu-id="25d09-120">记录了位置、完全限定域名 (FQDN) IP 地址、网络类型和特定于给定角色的注释。</span><span class="sxs-lookup"><span data-stu-id="25d09-120">The location, fully qualified domain name (FQDN) and IP address, type of network, and comments specific to a given role are documented.</span></span>

<span data-ttu-id="25d09-121">将部署、管理和维护基础结构的设计人员和每个团队应检查摘要报告的准确性并确保错误最少。</span><span class="sxs-lookup"><span data-stu-id="25d09-121">The designer and each of the teams that will deploy, manage, and maintain the infrastructure should review the summary report for accuracy and to make sure that errors are at a minimum.</span></span>

<span data-ttu-id="25d09-122">还可以查看更详细的报告：</span><span class="sxs-lookup"><span data-stu-id="25d09-122">You can also view more detailed reports:</span></span>

- <span data-ttu-id="25d09-123">证书报告</span><span class="sxs-lookup"><span data-stu-id="25d09-123">Certificates Report</span></span>

- <span data-ttu-id="25d09-124">防火墙报告</span><span class="sxs-lookup"><span data-stu-id="25d09-124">Firewall Report</span></span>

- <span data-ttu-id="25d09-125">DNS 报告</span><span class="sxs-lookup"><span data-stu-id="25d09-125">DNS Report</span></span>

## <a name="review-the-certificates-report"></a><span data-ttu-id="25d09-126">查看证书报告</span><span class="sxs-lookup"><span data-stu-id="25d09-126">Review the Certificates Report</span></span>
<span data-ttu-id="25d09-127"><a name="Certificates_Report"> </a></span><span class="sxs-lookup"><span data-stu-id="25d09-127"><a name="Certificates_Report"> </a></span></span>

<span data-ttu-id="25d09-128">证书报告包含建议的 Skype for Business Server 2015 部署中所需的所有证书。</span><span class="sxs-lookup"><span data-stu-id="25d09-128">The Certificates Report contains all certificates that are required in the recommended Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="25d09-129">规划工具会考虑输入的主题名称和主题替代名称。</span><span class="sxs-lookup"><span data-stu-id="25d09-129">The Planning Tool accounts for the subject names and subject alternative names that are entered.</span></span> <span data-ttu-id="25d09-130">对于负责请求和颁发证书的团队来说，未编辑的默认文本可能会带来挑战。</span><span class="sxs-lookup"><span data-stu-id="25d09-130">Default text that is left unedited may represent a potential challenge for the team responsible for requesting and issuing the certificates.</span></span> <span data-ttu-id="25d09-131">证书信息还包含通常可以从何处颁发证书的信息。</span><span class="sxs-lookup"><span data-stu-id="25d09-131">Certificate information also contains information about where the certificate can typically be issued from.</span></span> <span data-ttu-id="25d09-132">如果基础结构中没有内部公钥基础结构 (PKI)，则可以通过公共证书提供商请求所有证书。</span><span class="sxs-lookup"><span data-stu-id="25d09-132">If the infrastructure does not have an internal public key infrastructure (PKI) in place, all certificates can be requested through a public certificate provider.</span></span> <span data-ttu-id="25d09-133">该报告中的“扩展密钥用法 (EKU)”和“分配给”字段非常有助于理解每个证书应有的用途和应处的位置。</span><span class="sxs-lookup"><span data-stu-id="25d09-133">Extended key usages (EKU) and Assign To fields in the report are very helpful in understanding what the purpose and location for each certificate should be.</span></span>

![证书管理员报告](../../media/Certificates_Report_Admin_Report.png)

<span data-ttu-id="25d09-135">仔细检查部署中每个证书的用途和用途，并确保了解。</span><span class="sxs-lookup"><span data-stu-id="25d09-135">Carefully review, and be sure to understand, the use and purpose of each certificate in the deployment.</span></span> <span data-ttu-id="25d09-136">如果对证书执行哪些操作存在疑问，请确定与哪些服务器或服务通信。</span><span class="sxs-lookup"><span data-stu-id="25d09-136">If there is a question about what a certificate does, determine which server or service is talking to what.</span></span> <span data-ttu-id="25d09-137">Skype for Business Server 2015 中的证书主要用于两个目的：</span><span class="sxs-lookup"><span data-stu-id="25d09-137">Certificates in Skype for Business Server 2015 are used for two primary purposes:</span></span>

- <span data-ttu-id="25d09-138">相互传输层安全性 (MTLS) - 通信中涉及的每台计算机都提供一个向另一台计算机证明其身份的证书。</span><span class="sxs-lookup"><span data-stu-id="25d09-138">Mutual Transport Layer Security (MTLS) - The computers involved in the communication each present a certificate that proves their identity to another computer.</span></span> <span data-ttu-id="25d09-139">这称为服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="25d09-139">This is known as server authentication.</span></span> <span data-ttu-id="25d09-140">在每个计算机信任另一台计算机的标识之前，通信无法开始。</span><span class="sxs-lookup"><span data-stu-id="25d09-140">Communication cannot begin until each computer trusts the other computer's identity.</span></span>

- <span data-ttu-id="25d09-141">加密 - 加密 (安全套接字层、SSL、传输层安全性或 TLS) 是帮助保护通信、帮助确保隐私以及创建受信任的通信和协作系统的关键方法。</span><span class="sxs-lookup"><span data-stu-id="25d09-141">Encryption - Encryption (Secure Sockets Layer, or SSL, and Transport Layer Security, or TLS) is a critical means to help secure communications, help ensure privacy, and to create a trusted communications and collaboration system.</span></span>

## <a name="review-the-firewall-report"></a><span data-ttu-id="25d09-142">查看防火墙报告</span><span class="sxs-lookup"><span data-stu-id="25d09-142">Review the Firewall Report</span></span>
<span data-ttu-id="25d09-143"><a name="Firewall_report"> </a></span><span class="sxs-lookup"><span data-stu-id="25d09-143"><a name="Firewall_report"> </a></span></span>

<span data-ttu-id="25d09-144">Skype for Business Server 2015 具有一组可能复杂的防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="25d09-144">Skype for Business Server 2015 has a potentially complex set of firewall rules.</span></span> <span data-ttu-id="25d09-145">规划工具通过生成报告来基于设计器的输入条件详细定义所有防火墙要求，从而降低此复杂性。</span><span class="sxs-lookup"><span data-stu-id="25d09-145">The Planning Tool reduces this complexity by generating a report that defines in detail all firewall requirements, based on the designer's input criteria.</span></span> <span data-ttu-id="25d09-146">IT 防火墙管理员将可以使用此报告配置和定义所需的规则。</span><span class="sxs-lookup"><span data-stu-id="25d09-146">The IT firewall administrator will be able to use this report to configure and define the necessary rules.</span></span>

<span data-ttu-id="25d09-147">从防火墙管理的角度来看，应仔细审阅报告，以确保与退出防火墙规则没有冲突，并且没有违反的策略或过程。</span><span class="sxs-lookup"><span data-stu-id="25d09-147">From the standpoint of firewall management, the report should be carefully reviewed to make sure that there are no conflicts with exiting firewall rules and that there are no policies or procedures that might be violated.</span></span>

![防火墙管理员报告](../../media/Firewall_Report_Admin_Report.png)

## <a name="review-the-dns-report"></a><span data-ttu-id="25d09-149">查看 DNS 报告</span><span class="sxs-lookup"><span data-stu-id="25d09-149">Review the DNS Report</span></span>
<span data-ttu-id="25d09-150"><a name="DNS_Report"> </a></span><span class="sxs-lookup"><span data-stu-id="25d09-150"><a name="DNS_Report"> </a></span></span>

<span data-ttu-id="25d09-151">DNS 报告是管理员报告的一部分，它详细说明了内部、外围和外部网络中域名系统 (DNS) 的所有推荐条目和已知条目。</span><span class="sxs-lookup"><span data-stu-id="25d09-151">The DNS Report, which is part of the Administrator Report, details all of the recommended and known entries for the Domain Name System (DNS) in the internal, perimeter, and external networks.</span></span> <span data-ttu-id="25d09-152">如果设计器已完成对网络图的编辑，并且所有 IP 地址和完全限定域名 (FQDN) 都定义为其生产值，则 DNS 报告将提供出色的配置资源。</span><span class="sxs-lookup"><span data-stu-id="25d09-152">If the designer has completed the edits to the network diagram, and all IP addresses and fully qualified domain names (FQDNs) are defined to their production values, the DNS Report provides an excellent configuration resource.</span></span> <span data-ttu-id="25d09-153">此报告还可以作为操作疑难解答文档。</span><span class="sxs-lookup"><span data-stu-id="25d09-153">This report can also serve as an operational troubleshooting document.</span></span>

![DNS 管理员报告](../../media/DNS_Report_Admin_Report.png)

<span data-ttu-id="25d09-155">您应该让 DNS 管理团队全面查看 DNS 报告，以确保在部署过程中没有可能导致问题的错误，或可能导致疑难解答会话复杂化的错误。</span><span class="sxs-lookup"><span data-stu-id="25d09-155">You should have your DNS management team review the DNS Report thoroughly to make sure that there are no errors that may cause difficulty during deployment or that may complicate a troubleshooting session.</span></span>

## <a name="see-also"></a><span data-ttu-id="25d09-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25d09-156">See also</span></span>
<span data-ttu-id="25d09-157"><a name="DNS_Report"> </a></span><span class="sxs-lookup"><span data-stu-id="25d09-157"><a name="DNS_Report"> </a></span></span>

[<span data-ttu-id="25d09-158">查看管理员报告</span><span class="sxs-lookup"><span data-stu-id="25d09-158">Reviewing the Administrator Reports</span></span>](https://technet.microsoft.com/library/1dee56a9-a033-4201-9765-e3469bd7d3e3.aspx)
