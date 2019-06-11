---
title: Lync Server 2013：创建或编辑 XMPP 合作伙伴配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or edit XMPP partner configuration
ms:assetid: 362dbe5e-8ee9-4aba-8c26-5907312b4a60
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552447(v=OCS.15)
ms:contentKeyID: 48679558
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 488fa84a3f24133c6ebcde4467cacdbdcffe7ff8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-xmpp-partner-configuration-in-lync-server-2013"></a><span data-ttu-id="3808a-102">在 Lync Server 2013 中创建或编辑 XMPP 合作伙伴配置</span><span class="sxs-lookup"><span data-stu-id="3808a-102">Create or edit XMPP partner configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3808a-103">_**主题上次修改时间:** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="3808a-103">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="3808a-104">Microsoft Lync Server 2013 集成了边缘服务器上的可扩展消息和状态协议 (XMPP) 代理和前端服务器或前端池中的 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="3808a-104">Microsoft Lync Server 2013 integrates an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="3808a-105">若要允许来自其他 XMPP 部署的连接, 必须在 Lync Server 控制面板中配置 XMPP。</span><span class="sxs-lookup"><span data-stu-id="3808a-105">To allow connections from other XMPP deployments, you must configure XMPP in the Lync Server Control Panel.</span></span> <span data-ttu-id="3808a-106">您可以在 XMPP 域基础上配置设置。</span><span class="sxs-lookup"><span data-stu-id="3808a-106">You configure settings on an XMPP domain basis.</span></span> <span data-ttu-id="3808a-107">若要创建新的合作伙伴关联, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="3808a-107">To create a new partner association, you do the following:</span></span>

<div>

## <a name="to-create-a-new-federated-partner-or-edit-an-existing-configuration"></a><span data-ttu-id="3808a-108">创建新联盟合作伙伴或编辑现有配置</span><span class="sxs-lookup"><span data-stu-id="3808a-108">To create a new federated partner or edit an existing configuration</span></span>

1.  <span data-ttu-id="3808a-109">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="3808a-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3808a-110">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="3808a-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3808a-111">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="3808a-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3808a-112">在左侧导航栏中, 单击 "**联盟和外部访问**", 然后单击 " **XMPP 联盟合作伙伴**"。</span><span class="sxs-lookup"><span data-stu-id="3808a-112">In the left navigation bar, click **Federation and External Access**, and then click **XMPP Federated Partners**.</span></span>

4.  <span data-ttu-id="3808a-113">若要创建新配置, 请单击 "**新建**"</span><span class="sxs-lookup"><span data-stu-id="3808a-113">To create a new configuration, click **New**</span></span>

5.  <span data-ttu-id="3808a-114">若要编辑现有配置, 请选择配置, 然后单击 "**编辑**"</span><span class="sxs-lookup"><span data-stu-id="3808a-114">To edit an existing configuration, select the configuration and click **Edit**</span></span>

6.  <span data-ttu-id="3808a-115">若要创建或编辑**XMPP 联盟合作伙伴**的配置, 请定义以下设置:</span><span class="sxs-lookup"><span data-stu-id="3808a-115">To create or edit configurations for **XMPP Federated Partners**, you define the following settings:</span></span>

7.  <span data-ttu-id="3808a-116">**主要域**(必需)。</span><span class="sxs-lookup"><span data-stu-id="3808a-116">**Primary domain** (Required).</span></span> <span data-ttu-id="3808a-117">主要域是 XMPP 合作伙伴的基础域。</span><span class="sxs-lookup"><span data-stu-id="3808a-117">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="3808a-118">例如, 你可以为 XMPP 合作伙伴域名输入**fabrikam.com** 。</span><span class="sxs-lookup"><span data-stu-id="3808a-118">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="3808a-119">这是一个必需的条目。</span><span class="sxs-lookup"><span data-stu-id="3808a-119">This is a required entry.</span></span>

8.  <span data-ttu-id="3808a-120">**说明**。</span><span class="sxs-lookup"><span data-stu-id="3808a-120">**Description**.</span></span> <span data-ttu-id="3808a-121">说明适用于此特定配置的注释或其他标识信息。</span><span class="sxs-lookup"><span data-stu-id="3808a-121">The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="3808a-122">此条目是可选的。</span><span class="sxs-lookup"><span data-stu-id="3808a-122">This entry is optional.</span></span>

9.  <span data-ttu-id="3808a-123">**其他域**。</span><span class="sxs-lookup"><span data-stu-id="3808a-123">**Additional domains**.</span></span> <span data-ttu-id="3808a-124">其他域是 XMPP 合作伙伴的域的一部分, 应包括在允许的 XMPP 通信中。</span><span class="sxs-lookup"><span data-stu-id="3808a-124">Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="3808a-125">例如, 如果主域是**fabrikam.com**, 则会列出您将通过 XMPP 进行通信的 fabrikam.com 下的所有其他域。</span><span class="sxs-lookup"><span data-stu-id="3808a-125">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span> <span data-ttu-id="3808a-126">例如, 你可以在 fabrikam 的主 XMPP 域下为企业 XMPP 域和信息技术 XMPP 域输入**corp.fabrikam.com**和**it.fabrikam.com** 。</span><span class="sxs-lookup"><span data-stu-id="3808a-126">For example, you might enter **corp.fabrikam.com** and **it.fabrikam.com** for the Corporate XMPP domain and the Information Technologies XMPP domain under fabrikam.com’s main XMPP domain.</span></span>

10. <span data-ttu-id="3808a-127">**合作伙伴类型**。</span><span class="sxs-lookup"><span data-stu-id="3808a-127">**Partner type**.</span></span> <span data-ttu-id="3808a-128">**合作伙伴类型**是所需的设置, 可在下拉菜单中选择三个选项。</span><span class="sxs-lookup"><span data-stu-id="3808a-128">The **Partner type** is a required setting and gives you a selection of three choices in a drop-down menu.</span></span> <span data-ttu-id="3808a-129">您必须选择下列内容之一来描述和强制执行哪些联系人可以添加。</span><span class="sxs-lookup"><span data-stu-id="3808a-129">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="3808a-130">您可以选择:</span><span class="sxs-lookup"><span data-stu-id="3808a-130">You can select from:</span></span>
    
      - <span data-ttu-id="3808a-131">**联盟**。</span><span class="sxs-lookup"><span data-stu-id="3808a-131">**Federated**.</span></span> <span data-ttu-id="3808a-132">**联盟**伙伴类型是 Lync Server 或 Office 通信服务器 2007 R2 合作伙伴部署之间的受信任连接。</span><span class="sxs-lookup"><span data-stu-id="3808a-132">A **Federated** partner type is a trusted connection between a Lync Server or Office Communications Server 2007 R2 partner deployment.</span></span>
    
      - <span data-ttu-id="3808a-133">**已验证公共**。</span><span class="sxs-lookup"><span data-stu-id="3808a-133">**Public verified**.</span></span> <span data-ttu-id="3808a-134">已**验证的公共**合作伙伴是指由提供商验证的部署中的联系人可以添加到用户的联系人列表。</span><span class="sxs-lookup"><span data-stu-id="3808a-134">A **Public verified** partner is when contacts that are part of a deployment that are verified by the provider can be added to your user’s list of contacts.</span></span> <span data-ttu-id="3808a-135">可以从 Lync 用户发送邀请, 或者 Lync 用户可以接受来自合作伙伴联系人的邀请。</span><span class="sxs-lookup"><span data-stu-id="3808a-135">Invites can be sent from the Lync user or the Lync user can accept invites from the partner contact.</span></span>
    
      - <span data-ttu-id="3808a-136">**公共未验证**。</span><span class="sxs-lookup"><span data-stu-id="3808a-136">**Public unverified**.</span></span> <span data-ttu-id="3808a-137">公共的未**验证**关系表示两个部署之间没有已建立且可验证的状态。</span><span class="sxs-lookup"><span data-stu-id="3808a-137">A **Public unverified** relationship implies that there is no established and verifiable status between the two deployments.</span></span> <span data-ttu-id="3808a-138">Lync 用户必须邀请该联系人的未验证联系人能够将 Lync 用户添加到其联系人列表。</span><span class="sxs-lookup"><span data-stu-id="3808a-138">A Lync user must invite the unverified contact for that contact to be able to add the Lync user to his contact list.</span></span> <span data-ttu-id="3808a-139">例如, Google GTalk 不是一个公共验证的 XMPP 服务, 因为它与 Lync 服务器相关。</span><span class="sxs-lookup"><span data-stu-id="3808a-139">For example, Google GTalk is not a public verified XMPP service as it relates to Lync Server.</span></span> <span data-ttu-id="3808a-140">GTalk 用户将无法将 Lync 用户添加为联系人, 除非有直接从 Lync 用户发送的邀请。</span><span class="sxs-lookup"><span data-stu-id="3808a-140">A GTalk user will not be able to add the Lync user as a contact unless there is an explicit invite sent from the Lync user.</span></span>

11. <span data-ttu-id="3808a-141">有关流协商和安全方法传输层安全 (TLS) 和软件身份验证和安全层 (SASL) 的说明:</span><span class="sxs-lookup"><span data-stu-id="3808a-141">Notes on stream negotiation and the security methods Transport Layer Security (TLS) and Software Authentication and Security Layer (SASL):</span></span>
    
    <span data-ttu-id="3808a-142">**XMPP 标准基金会**(XSF) 和**Internet 工程任务**组 (IETF) 定义一组用于使用和管理 tls 客户端证书、TLS 服务器证书和 SASL 机制的规则和标准。</span><span class="sxs-lookup"><span data-stu-id="3808a-142">The **XMPP Standards Foundation** (XSF) and the **Internet Engineering Task Force** (IETF) define a set of rules and standards for using and managing TLS client certificates, TLS server certificates, and the SASL mechanism.</span></span> <span data-ttu-id="3808a-143">使用 TLS 和 SASL 是保护 XMPP 流所需的过程。</span><span class="sxs-lookup"><span data-stu-id="3808a-143">Using TLS and SASL is the required process for securing the XMPP stream.</span></span> <span data-ttu-id="3808a-144">从 XMPP 标准文档**XEP-0178**中, "指定推荐的协议流, 用于使用具有 PKIX 证书的 SASL 外部机制, 特别是当 XMPP 服务指示 TLS 必须协商时。"</span><span class="sxs-lookup"><span data-stu-id="3808a-144">From the XMPP Standards document **XEP-0178**, “specifies a recommended protocol flow for use of the SASL EXTERNAL mechanism with PKIX certificates, especially when an XMPP service indicates that TLS is mandatory-to-negotiate.”</span></span> <span data-ttu-id="3808a-145">PKIX (如 XSF 文档中所述), 指公钥基础结构, 也称为 PKI。</span><span class="sxs-lookup"><span data-stu-id="3808a-145">PKIX, as stated in the XSF documentation, refers to public key infrastructure, also known as PKI.</span></span>
    
    <span data-ttu-id="3808a-146">有关 XMPP 要求的详细信息, 请参阅 XSF 文档 XEP-0178。</span><span class="sxs-lookup"><span data-stu-id="3808a-146">Refer to the XSF document XEP-0178 for more details on the XMPP requirements.</span></span> <span data-ttu-id="3808a-147">有关详细信息, 请参阅 "XEP-0178: 使用 SASL 外部证书的最佳做法"。</span><span class="sxs-lookup"><span data-stu-id="3808a-147">For details, refer to “XEP-0178: Best Practices for Use of SASL EXTERNAL with Certificates”.</span></span> <http://xmpp.org/extensions/xep-0178.html>
    
    <span data-ttu-id="3808a-148">请参阅 IETF 文档 "可扩展消息和状态协议 (XMPP): Core", Section 5.0, STARTTLS 协商<http://tools.ietf.org/html/rfc6120>。</span><span class="sxs-lookup"><span data-stu-id="3808a-148">Refer to the IETF document “Extensible Messaging and Presence Protocol (XMPP): Core“, Section 5.0, STARTTLS Negotiation <http://tools.ietf.org/html/rfc6120>.</span></span>
    
      - <span data-ttu-id="3808a-149">**TLS 协商**。</span><span class="sxs-lookup"><span data-stu-id="3808a-149">**TLS Negotiation**.</span></span> <span data-ttu-id="3808a-150">定义 TLS 协商规则。</span><span class="sxs-lookup"><span data-stu-id="3808a-150">Defines the TLS negotiation rules.</span></span> <span data-ttu-id="3808a-151">XMPP 服务可能需要 TLS, 可以使 TLS 可选, 也可以定义不支持 TLS。</span><span class="sxs-lookup"><span data-stu-id="3808a-151">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="3808a-152">选择 "可选" 将对 XMPP 服务的要求留给必要的协商决策。</span><span class="sxs-lookup"><span data-stu-id="3808a-152">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="3808a-153">若要查看有关 SASL、TLS 和回拨协商的所有可能设置和详细信息-包括无效的已知错误配置, 请参阅[Lync Server 2013 中 XMPP 联盟合作伙伴的协商设置](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)。</span><span class="sxs-lookup"><span data-stu-id="3808a-153">To view all possible settings and details for SASL, TLS and Dialback negotiation –including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span></span>
        
          - <span></span>  
            <span data-ttu-id="3808a-154">**必需**。</span><span class="sxs-lookup"><span data-stu-id="3808a-154">**Required**.</span></span> <span data-ttu-id="3808a-155">XMPP 服务需要 TLS 协商。</span><span class="sxs-lookup"><span data-stu-id="3808a-155">The XMPP service requires TLS negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="3808a-156">**可选**。</span><span class="sxs-lookup"><span data-stu-id="3808a-156">**Optional**.</span></span> <span data-ttu-id="3808a-157">XMPP 服务指示 TLS 必须进行协商。</span><span class="sxs-lookup"><span data-stu-id="3808a-157">The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="3808a-158">**不受支持**。</span><span class="sxs-lookup"><span data-stu-id="3808a-158">**Not Supported**.</span></span> <span data-ttu-id="3808a-159">XMPP 服务不支持 TLS。</span><span class="sxs-lookup"><span data-stu-id="3808a-159">The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="3808a-160">**SASL 协商**。</span><span class="sxs-lookup"><span data-stu-id="3808a-160">**SASL negotiation**.</span></span> <span data-ttu-id="3808a-161">定义 SASL 协商规则。</span><span class="sxs-lookup"><span data-stu-id="3808a-161">Defines the SASL negotiation rules.</span></span> <span data-ttu-id="3808a-162">XMPP 服务可能需要 SASL, 可以使 SASL 成为可选的, 也可以定义不支持 SASL。</span><span class="sxs-lookup"><span data-stu-id="3808a-162">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="3808a-163">选择 "可选" 将要求提供给合作伙伴 XMPP 服务, 以便进行强制性的协商决策。</span><span class="sxs-lookup"><span data-stu-id="3808a-163">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="3808a-164">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="3808a-164">SASL requires TLS.</span></span> <span data-ttu-id="3808a-165">若要使用 SASL, TLS 必须是必需的或可选的。</span><span class="sxs-lookup"><span data-stu-id="3808a-165">To use SASL, TLS must either be required or optional.</span></span> <span data-ttu-id="3808a-166">将 SASL 定义为 "必需" 或 "可选" 的任何配置都必须具有 TLS 支持。</span><span class="sxs-lookup"><span data-stu-id="3808a-166">Any configuration that defines SASL as either required or optional must have TLS support.</span></span> <span data-ttu-id="3808a-167">单击 "<STRONG>提交</STRONG>" 以保存所做的更改时, 如果未将 tls 设置为 "必需" 或 "可选", 则系统会警告 SASL 必须具有 TLS 支持, 并且不会保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="3808a-167">When clicking <STRONG>Commit</STRONG> to save your changes, if you have not set TLS to required or optional, you will be warned that SASL must have TLS support and your changes are not saved.</span></span> <span data-ttu-id="3808a-168">若要解决此错误, 请将 TLS 设置为<STRONG>必需</STRONG>或<STRONG>可选</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="3808a-168">To resolve the error, set TLS to <STRONG>Required</STRONG> or <STRONG>Optional</STRONG>.</span></span> <span data-ttu-id="3808a-169">如果使用 SASL 是可选的, 并且不可能支持 TLS 协商支持, 则必须将 SASL 协商设置为<STRONG>不受支持</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="3808a-169">If use of SASL is optional and TLS negotiation support is not possible, you must set SASL negotiation to <STRONG>Not Supported</STRONG>.</span></span> <span data-ttu-id="3808a-170">通过 XMPP 服务确认哪些正确的协商流必须用于 TLS 和 SASL, 否则将出现服务中断。</span><span class="sxs-lookup"><span data-stu-id="3808a-170">Confirm with the XMPP service what the proper negotiation streams must be for TLS and SASL or service interruption will occur.</span></span>

        
        </div>
        
          - <span></span>  
            <span data-ttu-id="3808a-171">**必需**。</span><span class="sxs-lookup"><span data-stu-id="3808a-171">**Required**.</span></span> <span data-ttu-id="3808a-172">XMPP 服务需要 SASL 协商。</span><span class="sxs-lookup"><span data-stu-id="3808a-172">The XMPP service requires SASL negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="3808a-173">**可选**。</span><span class="sxs-lookup"><span data-stu-id="3808a-173">**Optional**.</span></span> <span data-ttu-id="3808a-174">XMPP 服务指示 SASL 必须进行协商。</span><span class="sxs-lookup"><span data-stu-id="3808a-174">The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="3808a-175">**不受支持**。</span><span class="sxs-lookup"><span data-stu-id="3808a-175">**Not Supported**.</span></span> <span data-ttu-id="3808a-176">XMPP 服务不支持 SASL。</span><span class="sxs-lookup"><span data-stu-id="3808a-176">The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="3808a-177">**回拨协商**。</span><span class="sxs-lookup"><span data-stu-id="3808a-177">**Dialback negotiation**.</span></span> <span data-ttu-id="3808a-178">回拨协商由文档 XEP 中的 XSF 定义 **-220: 服务器回拨** <http://xmpp.org/extensions/xep-0220.html>。</span><span class="sxs-lookup"><span data-stu-id="3808a-178">Dialback negotiation is defined by the XSF in document **XEP-220 : Server Dialback** <http://xmpp.org/extensions/xep-0220.html>.</span></span> <span data-ttu-id="3808a-179">服务器回拨进程使用域名系统 (DNS) 和权威服务器验证请求是否来自有效的 XMPP 合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="3808a-179">The server dialback process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="3808a-180">为此, 始发服务器使用生成的回拨密钥创建一个特定类型的消息, 并在 DNS 中查找接收服务器。</span><span class="sxs-lookup"><span data-stu-id="3808a-180">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="3808a-181">始发服务器将 XML 流中的密钥发送到生成的 DNS 查找, 这是接收服务器。</span><span class="sxs-lookup"><span data-stu-id="3808a-181">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="3808a-182">在通过 XML 流接收密钥时, 接收服务器不会响应始发服务器, 而是将密钥发送到已知的权威服务器。</span><span class="sxs-lookup"><span data-stu-id="3808a-182">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="3808a-183">授权服务器验证密钥是否有效或无效。</span><span class="sxs-lookup"><span data-stu-id="3808a-183">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="3808a-184">如果无效, 接收方服务器不会响应始发服务器。</span><span class="sxs-lookup"><span data-stu-id="3808a-184">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="3808a-185">如果密钥有效, 接收方服务器将通知发起服务器标识和密钥有效且可以开始对话。</span><span class="sxs-lookup"><span data-stu-id="3808a-185">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="3808a-186">**回拨协商**有两个有效状态:</span><span class="sxs-lookup"><span data-stu-id="3808a-186">There are two valid states for **Dialback negotiation**:</span></span>
        
          - <span></span>  
            <span data-ttu-id="3808a-187">**True**。</span><span class="sxs-lookup"><span data-stu-id="3808a-187">**True**.</span></span> <span data-ttu-id="3808a-188">如果应收到来自发起服务器的请求, 则将 XMPP 服务器配置为使用回拨协商</span><span class="sxs-lookup"><span data-stu-id="3808a-188">The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server</span></span>
        
          - <span></span>  
            <span data-ttu-id="3808a-189">**False**。</span><span class="sxs-lookup"><span data-stu-id="3808a-189">**False**.</span></span> <span data-ttu-id="3808a-190">XMPP 服务器未配置为使用回拨协商, 如果应收到来自发起服务器的请求, 则会忽略它</span><span class="sxs-lookup"><span data-stu-id="3808a-190">The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

