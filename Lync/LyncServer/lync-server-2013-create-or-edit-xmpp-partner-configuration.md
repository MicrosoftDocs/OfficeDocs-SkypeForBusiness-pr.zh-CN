---
title: Lync Server 2013：创建或编辑 XMPP 合作伙伴配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit XMPP partner configuration
ms:assetid: 362dbe5e-8ee9-4aba-8c26-5907312b4a60
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552447(v=OCS.15)
ms:contentKeyID: 48679558
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4410444d1565e61fa80ef8b8db29aad63b4401de
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42032488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-xmpp-partner-configuration-in-lync-server-2013"></a><span data-ttu-id="d0e9a-102">在 Lync Server 2013 中创建或编辑 XMPP 合作伙伴配置</span><span class="sxs-lookup"><span data-stu-id="d0e9a-102">Create or edit XMPP partner configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0e9a-103">_**上次修改的主题：** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="d0e9a-103">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="d0e9a-104">Microsoft Lync Server 2013 集成了边缘服务器上的可扩展消息和状态协议（XMPP）代理，以及前端服务器或前端池上的 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-104">Microsoft Lync Server 2013 integrates an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="d0e9a-105">若要允许来自其他 XMPP 部署的连接，必须在 Lync Server 控制面板中配置 XMPP。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-105">To allow connections from other XMPP deployments, you must configure XMPP in the Lync Server Control Panel.</span></span> <span data-ttu-id="d0e9a-106">您可以基于 XMPP 域配置相关设置。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-106">You configure settings on an XMPP domain basis.</span></span> <span data-ttu-id="d0e9a-107">若要创建新的合作伙伴关联，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d0e9a-107">To create a new partner association, you do the following:</span></span>

<div>

## <a name="to-create-a-new-federated-partner-or-edit-an-existing-configuration"></a><span data-ttu-id="d0e9a-108">创建新的联盟伙伴或编辑现有配置</span><span class="sxs-lookup"><span data-stu-id="d0e9a-108">To create a new federated partner or edit an existing configuration</span></span>

1.  <span data-ttu-id="d0e9a-109">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d0e9a-110">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d0e9a-111">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d0e9a-112">在左侧导航栏中，单击“联盟和外部访问”\*\*\*\*，然后单击“XMPP 联盟伙伴”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-112">In the left navigation bar, click **Federation and External Access**, and then click **XMPP Federated Partners**.</span></span>

4.  <span data-ttu-id="d0e9a-113">若要创建新配置，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-113">To create a new configuration, click **New**</span></span>

5.  <span data-ttu-id="d0e9a-114">若要编辑现有配置，请选择相应的配置，然后单击“编辑”\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="d0e9a-114">To edit an existing configuration, select the configuration and click **Edit**</span></span>

6.  <span data-ttu-id="d0e9a-115">若要为“XMPP 联盟伙伴”\*\*\*\* 创建或编辑配置，请定义以下设置：</span><span class="sxs-lookup"><span data-stu-id="d0e9a-115">To create or edit configurations for **XMPP Federated Partners**, you define the following settings:</span></span>

7.  <span data-ttu-id="d0e9a-116">**主域**（必需）。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-116">**Primary domain** (Required).</span></span> <span data-ttu-id="d0e9a-117">主域是 XMPP 合作伙伴的基本域。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-117">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="d0e9a-118">例如，可为 XMPP 合作伙伴域名输入 **fabrikam.com**。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-118">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="d0e9a-119">这是必填项。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-119">This is a required entry.</span></span>

8.  <span data-ttu-id="d0e9a-120">**说明**。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-120">**Description**.</span></span> <span data-ttu-id="d0e9a-121">该说明针对此特定配置的注释或其他标识信息。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-121">The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="d0e9a-122">此条目是可选的。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-122">This entry is optional.</span></span>

9.  <span data-ttu-id="d0e9a-123">**其他域**。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-123">**Additional domains**.</span></span> <span data-ttu-id="d0e9a-124">其他域是作为 XMPP 合作伙伴的域一部分的域，应作为允许的 XMPP 通信的一部分包括在内。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-124">Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="d0e9a-125">例如，如果主域为**fabrikam.com**，则将列出位于 fabrikam.com 中的所有其他域，您将使用 XMPP 的方式进行通信。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-125">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span> <span data-ttu-id="d0e9a-126">例如，可以在 fabrikam .com 的主 XMPP 域下输入公司 XMPP 域和信息技术 XMPP 域的**corp.fabrikam.com**和**it.fabrikam.com** 。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-126">For example, you might enter **corp.fabrikam.com** and **it.fabrikam.com** for the Corporate XMPP domain and the Information Technologies XMPP domain under fabrikam.com’s main XMPP domain.</span></span>

10. <span data-ttu-id="d0e9a-127">**合作伙伴类型**。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-127">**Partner type**.</span></span> <span data-ttu-id="d0e9a-128">"**合作伙伴类型**" 是必需的设置，可让您选择下拉菜单中的三个选项。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-128">The **Partner type** is a required setting and gives you a selection of three choices in a drop-down menu.</span></span> <span data-ttu-id="d0e9a-129">您必须选择以下项之一来描述和强制添加可添加的联系人。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-129">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="d0e9a-130">您可以从以下选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="d0e9a-130">You can select from:</span></span>
    
      - <span data-ttu-id="d0e9a-131">**联合**。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-131">**Federated**.</span></span> <span data-ttu-id="d0e9a-132">**联合**合作伙伴类型是 Lync Server 或 Office 通信服务器 2007 R2 合作伙伴部署之间的受信任连接。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-132">A **Federated** partner type is a trusted connection between a Lync Server or Office Communications Server 2007 R2 partner deployment.</span></span>
    
      - <span data-ttu-id="d0e9a-133">**公共验证**。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-133">**Public verified**.</span></span> <span data-ttu-id="d0e9a-134">已**验证公众**的合作伙伴是指由提供商验证的部署中的联系人可以添加到用户的联系人列表中。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-134">A **Public verified** partner is when contacts that are part of a deployment that are verified by the provider can be added to your user’s list of contacts.</span></span> <span data-ttu-id="d0e9a-135">可以从 Lync 用户发送邀请，也可以通过 Lync 用户接受来自合作伙伴联系人的邀请。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-135">Invites can be sent from the Lync user or the Lync user can accept invites from the partner contact.</span></span>
    
      - <span data-ttu-id="d0e9a-136">**公共未验证**。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-136">**Public unverified**.</span></span> <span data-ttu-id="d0e9a-137">**公共未验证**关系表示两个部署之间没有已建立且可验证的状态。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-137">A **Public unverified** relationship implies that there is no established and verifiable status between the two deployments.</span></span> <span data-ttu-id="d0e9a-138">Lync 用户必须邀请该联系人的未验证联系人能够将 Lync 用户添加到其联系人列表。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-138">A Lync user must invite the unverified contact for that contact to be able to add the Lync user to his contact list.</span></span> <span data-ttu-id="d0e9a-139">例如，Google GTalk 不是一个公开验证的 XMPP 服务，因为它与 Lync Server 相关。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-139">For example, Google GTalk is not a public verified XMPP service as it relates to Lync Server.</span></span> <span data-ttu-id="d0e9a-140">除非从 Lync 用户发送了明确的邀请，否则 GTalk 用户将无法将 Lync 用户添加为联系人。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-140">A GTalk user will not be able to add the Lync user as a contact unless there is an explicit invite sent from the Lync user.</span></span>

11. <span data-ttu-id="d0e9a-141">有关流协商和安全机制传输层安全性 (TLS) 及软件身份验证和安全层 (SASL) 的说明：</span><span class="sxs-lookup"><span data-stu-id="d0e9a-141">Notes on stream negotiation and the security methods Transport Layer Security (TLS) and Software Authentication and Security Layer (SASL):</span></span>
    
    <span data-ttu-id="d0e9a-p110">**XMPP Standards Foundation** (XSF) 和 **Internet 工程任务组** (IETF) 定义了一组使用和管理 TLS 客户端证书、TLS 服务器证书和 SASL 机制的规则和标准。使用 TLS 和 SASL 是保护 XMPP 流所必需的过程。根据 XMPP Standards 文档 **XEP-0178**，“指定将 SASL EXTERNAL 机制用于 PKIX 证书的建议的协议流，尤其是当 XMPP 服务指示将强制进行 TLS 协商时。”如 XSF 文档中所述，PKIX 是指公钥基础结构，又称 PKI。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-p110">The **XMPP Standards Foundation** (XSF) and the **Internet Engineering Task Force** (IETF) define a set of rules and standards for using and managing TLS client certificates, TLS server certificates, and the SASL mechanism. Using TLS and SASL is the required process for securing the XMPP stream. From the XMPP Standards document **XEP-0178**, “specifies a recommended protocol flow for use of the SASL EXTERNAL mechanism with PKIX certificates, especially when an XMPP service indicates that TLS is mandatory-to-negotiate.” PKIX, as stated in the XSF documentation, refers to public key infrastructure, also known as PKI.</span></span>
    
    <span data-ttu-id="d0e9a-146">有关 XMPP 要求的详细信息，请参阅 XSF 文档 XEP-0178。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-146">Refer to the XSF document XEP-0178 for more details on the XMPP requirements.</span></span> <span data-ttu-id="d0e9a-147">有关详细信息，请参阅 "XEP-0178：使用 SASL EXTERNAL with 证书" 的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-147">For details, refer to “XEP-0178: Best Practices for Use of SASL EXTERNAL with Certificates”.</span></span> <http://xmpp.org/extensions/xep-0178.html>
    
    <span data-ttu-id="d0e9a-148">请参阅 IETF document "可扩展消息和状态协议（XMPP）： Core"，5.0 节，STARTTLS 协商<http://tools.ietf.org/html/rfc6120>。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-148">Refer to the IETF document “Extensible Messaging and Presence Protocol (XMPP): Core“, Section 5.0, STARTTLS Negotiation <http://tools.ietf.org/html/rfc6120>.</span></span>
    
      - <span data-ttu-id="d0e9a-149">**TLS 协商**。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-149">**TLS Negotiation**.</span></span> <span data-ttu-id="d0e9a-150">定义 TLS 协商规则。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-150">Defines the TLS negotiation rules.</span></span> <span data-ttu-id="d0e9a-151">XMPP 服务可能需要 TLS，可以使 TLS 成为可选的，也可以定义不支持 TLS。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-151">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="d0e9a-152">选择 "可选" 将要求留给 XMPP 服务进行强制性协商决策。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-152">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="d0e9a-153">若要查看所有可能的设置和有关 SASL、TLS 和回拨的详细信息（包括无效和已知的错误配置），请参阅[Lync Server 2013 中的 XMPP 联盟伙伴的协商设置](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-153">To view all possible settings and details for SASL, TLS and Dialback negotiation –including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span></span>
        
          - <span></span>  
            <span data-ttu-id="d0e9a-154">**必需**。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-154">**Required**.</span></span> <span data-ttu-id="d0e9a-155">XMPP 服务需要 TLS 协商。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-155">The XMPP service requires TLS negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="d0e9a-156">**可选**。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-156">**Optional**.</span></span> <span data-ttu-id="d0e9a-157">XMPP 服务指示将强制进行 TLS 协商。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-157">The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="d0e9a-158">**不支持**。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-158">**Not Supported**.</span></span> <span data-ttu-id="d0e9a-159">XMPP 服务不支持 TLS。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-159">The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="d0e9a-160">**SASL 协商**。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-160">**SASL negotiation**.</span></span> <span data-ttu-id="d0e9a-161">定义 SASL 协商规则。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-161">Defines the SASL negotiation rules.</span></span> <span data-ttu-id="d0e9a-162">XMPP 服务可能需要 SASL，可以使 SASL 成为可选的，也可以定义不支持 SASL。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-162">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="d0e9a-163">选择 "可选" 将要求留给合作伙伴 XMPP 服务进行强制性的协商决策。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-163">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="d0e9a-p117">SASL 需要 TLS。若要使用 SASL，TLS 必须为必需或可选项。任何将 SASL 定义为“必需”或“可选”的配置都必须提供 TLS 支持。当单击“提交”<STRONG></STRONG>保存更改时，如果未将 TLS 设为“必需”或“可选”，将警告您 SASL 必须提供 TLS 支持且无法保存您的更改。若要处理该错误，请将 TLS 设为“必需”<STRONG></STRONG>或“可选”<STRONG></STRONG>。如果 SASL 的使用是可选的且无法实现 TLS 协商支持，则您必须将 SASL 协商设为“不支持”<STRONG></STRONG>。通过 XMPP 服务确认必须建立哪些适当的 TLS 和 SASL 协商流，否则将发生服务中断。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-p117">SASL requires TLS. To use SASL, TLS must either be required or optional. Any configuration that defines SASL as either required or optional must have TLS support. When clicking <STRONG>Commit</STRONG> to save your changes, if you have not set TLS to required or optional, you will be warned that SASL must have TLS support and your changes are not saved. To resolve the error, set TLS to <STRONG>Required</STRONG> or <STRONG>Optional</STRONG>. If use of SASL is optional and TLS negotiation support is not possible, you must set SASL negotiation to <STRONG>Not Supported</STRONG>. Confirm with the XMPP service what the proper negotiation streams must be for TLS and SASL or service interruption will occur.</span></span>

        
        </div>
        
          - <span></span>  
            <span data-ttu-id="d0e9a-171">**必需**。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-171">**Required**.</span></span> <span data-ttu-id="d0e9a-172">XMPP 服务需要 SASL 协商。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-172">The XMPP service requires SASL negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="d0e9a-173">**可选**。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-173">**Optional**.</span></span> <span data-ttu-id="d0e9a-174">XMPP 服务指示将强制进行 SASL 协商。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-174">The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="d0e9a-175">**不支持**。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-175">**Not Supported**.</span></span> <span data-ttu-id="d0e9a-176">XMPP 服务不支持 SASL。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-176">The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="d0e9a-177">**回拨协商**。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-177">**Dialback negotiation**.</span></span> <span data-ttu-id="d0e9a-178">回拨协商由 document **XEP-220： Server 回拨** <http://xmpp.org/extensions/xep-0220.html>中的 XSF 定义。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-178">Dialback negotiation is defined by the XSF in document **XEP-220 : Server Dialback** <http://xmpp.org/extensions/xep-0220.html>.</span></span> <span data-ttu-id="d0e9a-179">服务器回拨进程使用域名系统（DNS）和权威服务器来验证请求是否来自有效的 XMPP 合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-179">The server dialback process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="d0e9a-180">若要执行此操作，起始服务器将使用生成的回拨密钥创建特定类型的邮件，并在 DNS 中查找接收服务器。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-180">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="d0e9a-181">源服务器将 XML 流中的密钥发送到生成的 DNS 查找，大概是接收服务器。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-181">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="d0e9a-182">在 XML 流上收到密钥后，接收服务器不会响应原始服务器，但会将密钥发送到已知的权威服务器。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-182">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="d0e9a-183">权威服务器验证密钥有效或无效。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-183">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="d0e9a-184">如果无效，则接收服务器不会对原始服务器做出响应。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-184">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="d0e9a-185">如果密钥有效，则接收服务器会通知发起服务器标识和密钥有效，并且会话可以开始。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-185">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="d0e9a-186">**回拨协商**具有两种有效状态：</span><span class="sxs-lookup"><span data-stu-id="d0e9a-186">There are two valid states for **Dialback negotiation**:</span></span>
        
          - <span></span>  
            <span data-ttu-id="d0e9a-187">**True**。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-187">**True**.</span></span> <span data-ttu-id="d0e9a-188">如果应收到来自发起服务器的请求，则将 XMPP 服务器配置为使用回拨协商。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-188">The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server</span></span>
        
          - <span></span>  
            <span data-ttu-id="d0e9a-189">**False**。</span><span class="sxs-lookup"><span data-stu-id="d0e9a-189">**False**.</span></span> <span data-ttu-id="d0e9a-190">XMPP 服务器不配置为使用回拨协商，并且如果应从发起服务器接收请求，将忽略该状态</span><span class="sxs-lookup"><span data-stu-id="d0e9a-190">The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

