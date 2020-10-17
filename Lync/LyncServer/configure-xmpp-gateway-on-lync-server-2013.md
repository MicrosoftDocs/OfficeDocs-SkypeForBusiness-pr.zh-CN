---
title: 在 Lync Server 2013 上配置 XMPP 网关
description: 在 Lync Server 2013 上配置 XMPP 网关。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: c70282e0-b502-47e2-a0be-a32eb1faf99d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721881(v=OCS.15)
ms:contentKeyID: 49733816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78765237e737dea29d77230d6b0eecdb0348cb41
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542948"
---
# <a name="configure-xmpp-gateway-on-lync-server-2013"></a><span data-ttu-id="46fa7-103">在 Lync Server 2013 上配置 XMPP 网关</span><span class="sxs-lookup"><span data-stu-id="46fa7-103">Configure XMPP gateway on Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46fa7-104">_**上次修改的主题：** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="46fa7-104">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="46fa7-105">迁移 XMPP 网关的最后一步是为 Lync Server 2013 Edge 服务器配置证书，部署 Lync Server 2013 XMPP 网关，并更新 XMPP 网关的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="46fa7-105">The final steps for migrating your XMPP Gateway are to configure certificates for the Lync Server 2013 Edge Server, deploy the Lync Server 2013 XMPP Gateway, and update the DNS records for the XMPP Gateway.</span></span> <span data-ttu-id="46fa7-106">这些步骤应该并行执行，以尽可能缩短 XMPP 网关的停机时间。</span><span class="sxs-lookup"><span data-stu-id="46fa7-106">These steps should be performed in parallel to minimize the down time of your XMPP Gateway.</span></span> <span data-ttu-id="46fa7-107">在执行这些步骤之前，必须将所有用户移到 Microsoft Lync Server 2013 部署中。</span><span class="sxs-lookup"><span data-stu-id="46fa7-107">All users must be moved to your Microsoft Lync Server 2013 deployment before performing these steps.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="46fa7-108">对于驻留在 survivable 分支设备上的用户，不支持 XMPP 联盟。</span><span class="sxs-lookup"><span data-stu-id="46fa7-108">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="46fa7-109">这适用于查看状态信息和交换 IM 消息。</span><span class="sxs-lookup"><span data-stu-id="46fa7-109">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="46fa7-110">在 Lync Server 2013 边缘服务器上配置 XMPP 网关证书。</span><span class="sxs-lookup"><span data-stu-id="46fa7-110">Configure XMPP Gateway Certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="46fa7-111">在边缘服务器上，单击部署向导中“步骤 3：请求、安装或分配证书”\*\*\*\* 旁边的“再次运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="46fa7-111">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="46fa7-112">如果您第一次部署边缘服务器，您将看到“运行”而不是“再次运行”。</span><span class="sxs-lookup"><span data-stu-id="46fa7-112">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

2.  <span data-ttu-id="46fa7-113">在“可用的证书任务”\*\*\*\* 页上，单击“创建新的证书请求”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="46fa7-113">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="46fa7-114">在“证书请求”\*\*\*\* 页上，单击“外部边缘证书”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="46fa7-114">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="46fa7-115">在“延迟的请求或即时请求”\*\*\*\* 页上，选中“立即准备请求，但是稍后发送”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="46fa7-115">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="46fa7-116">在 " **证书请求文件** " 页上，键入要将请求保存到的文件的完整路径和文件名 (例如，c： \\ cert \_ 外部 \_ edge) 。</span><span class="sxs-lookup"><span data-stu-id="46fa7-116">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="46fa7-117">在“指定替代证书模板”\*\*\*\* 页上，要使用除默认 WebServer 模板之外的模板，请选中“对选定的证书颁发机构使用替代证书模板”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="46fa7-117">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="46fa7-118">在“名称和安全设置”\*\*\*\* 页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="46fa7-118">On the **Name and Security Settings** page, do the following:</span></span>
    
    1.  <span data-ttu-id="46fa7-119">在“友好名称”\*\*\*\* 中，键入证书的显示名称。</span><span class="sxs-lookup"><span data-stu-id="46fa7-119">In **Friendly name**, type a display name for the certificate.</span></span>
    
    2.  <span data-ttu-id="46fa7-120">在“位长度”\*\*\*\* 中，指定位长度（通常默认值为 2048）。</span><span class="sxs-lookup"><span data-stu-id="46fa7-120">In **Bit length**, specify the bit length (typically, the default of 2048).</span></span>
    
    3.  <span data-ttu-id="46fa7-121">验证是否选中了“将证书私钥标记为可导出”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="46fa7-121">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="46fa7-122">在“组织信息”\*\*\*\* 页上，键入组织和组织单位（例如分部或部门）的名称。</span><span class="sxs-lookup"><span data-stu-id="46fa7-122">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="46fa7-123">在“地理信息”\*\*\*\* 页上，指定位置信息。</span><span class="sxs-lookup"><span data-stu-id="46fa7-123">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="46fa7-p103">在“使用者名称/使用者替代名称”\*\*\*\* 页上，将显示向导自动填充的信息。如果需要其他使用者替代名称，可以在接下来的两个步骤中指定。</span><span class="sxs-lookup"><span data-stu-id="46fa7-p103">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="46fa7-126">在 " \*\*使用者替代名称 (SANs) \*\* " 页上的 "SIP 域设置" 中，选中 "域" 复选框以添加 SIP。\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="46fa7-126">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\></span></span> <span data-ttu-id="46fa7-127">"主题备用名称" 列表中的条目。</span><span class="sxs-lookup"><span data-stu-id="46fa7-127">entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="46fa7-128">在“配置其他使用者替代名称”\*\*\*\* 页上，指定所需的任何其他使用者替代名称。</span><span class="sxs-lookup"><span data-stu-id="46fa7-128">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="46fa7-p105">如果安装了 XMPP 代理，则默认情况下域名（如 contoso.com）填充在 SAN 条目中。如果您需要更多条目，请在此步骤中添加它们。</span><span class="sxs-lookup"><span data-stu-id="46fa7-p105">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries. If you require more entries, add them in this step.</span></span>

    
    </div>

13. <span data-ttu-id="46fa7-131">在“请求摘要”\*\*\*\* 页上，检查要用于生成请求的证书信息。</span><span class="sxs-lookup"><span data-stu-id="46fa7-131">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="46fa7-132">在命令运行完毕后，您可以“查看日志”\*\*\*\*，或单击“下一步”继续操作。</span><span class="sxs-lookup"><span data-stu-id="46fa7-132">After the commands finish running, you can **View Log**, or click Next to continue.</span></span>

15. <span data-ttu-id="46fa7-133">在“证书请求文件”\*\*\*\* 页上，您可以通过单击“查看”\*\*\*\* 来查看生成的证书签名请求 (CSR) 文件，或通过单击“完成”\*\*\*\* 来退出证书向导。</span><span class="sxs-lookup"><span data-stu-id="46fa7-133">On the **Certificate Request File** page, you can view the generated certificate signing request (CSR) file by clicking **View** or exit the Certificate Wizard by clicking **Finish**.</span></span>

16. <span data-ttu-id="46fa7-134">复制请求文件并提交至公共证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="46fa7-134">Copy the request file and submit to your public certification authority.</span></span>

17. <span data-ttu-id="46fa7-p106">在接收、导入和分配公共证书后，您必须停止边缘服务器服务，然后重新启动它。为此，请在 Lync Server 管理控制台中键入：</span><span class="sxs-lookup"><span data-stu-id="46fa7-p106">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services. You do this by typing in the Lync Server Management console:</span></span>
    
        Stop-CsWindowsService

      &nbsp;
    
        Start-CsWindowsService

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="46fa7-137">配置新的 Lync Server 2013 XMPP 网关</span><span class="sxs-lookup"><span data-stu-id="46fa7-137">Configure a new Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="46fa7-138">打开“Lync Server 控制面板”。</span><span class="sxs-lookup"><span data-stu-id="46fa7-138">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="46fa7-139">在左侧导航栏中，单击“联盟和外部访问”\*\*\*\*，然后单击“XMPP 联盟伙伴”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="46fa7-139">In the left navigation bar, click **Federation and External Access** and then click **XMPP Federated Partners**.</span></span>

3.  <span data-ttu-id="46fa7-140">要创建新配置，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="46fa7-140">To create a new configuration, click **New**.</span></span>

4.  <span data-ttu-id="46fa7-141">定义以下设置：</span><span class="sxs-lookup"><span data-stu-id="46fa7-141">Define the following settings:</span></span>

5.  <span data-ttu-id="46fa7-142">**主域**     (必需的) 。</span><span class="sxs-lookup"><span data-stu-id="46fa7-142">**Primary domain**    (Required).</span></span> <span data-ttu-id="46fa7-143">主域是 XMPP 合作伙伴的基本域。</span><span class="sxs-lookup"><span data-stu-id="46fa7-143">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="46fa7-144">例如，可为 XMPP 合作伙伴域名输入 **fabrikam.com**。</span><span class="sxs-lookup"><span data-stu-id="46fa7-144">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="46fa7-145">这是必填项。</span><span class="sxs-lookup"><span data-stu-id="46fa7-145">This is a required entry.</span></span>

6.  <span data-ttu-id="46fa7-146">**说明**    该说明针对此特定配置的注释或其他标识信息。</span><span class="sxs-lookup"><span data-stu-id="46fa7-146">**Description**   The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="46fa7-147">此条目是可选的。</span><span class="sxs-lookup"><span data-stu-id="46fa7-147">This entry is optional.</span></span>

7.  <span data-ttu-id="46fa7-148">**其他域**    其他域是作为 XMPP 合作伙伴的域一部分的域，应作为允许的 XMPP 通信的一部分包括在内。</span><span class="sxs-lookup"><span data-stu-id="46fa7-148">**Additional domains**   Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="46fa7-149">例如，如果主域为 **fabrikam.com**，则将列出位于 fabrikam.com 中的所有其他域，您将使用 XMPP 的方式进行通信。</span><span class="sxs-lookup"><span data-stu-id="46fa7-149">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span>

8.  <span data-ttu-id="46fa7-150">**合作伙伴类型**    "**合作伙伴类型**" 是必需的设置。</span><span class="sxs-lookup"><span data-stu-id="46fa7-150">**Partner type**   The **Partner type** is a required setting.</span></span> <span data-ttu-id="46fa7-151">您必须选择以下项之一来描述和强制添加可添加的联系人。</span><span class="sxs-lookup"><span data-stu-id="46fa7-151">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="46fa7-152">您可以从以下选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="46fa7-152">You can select from:</span></span>
    
      - <span data-ttu-id="46fa7-153">**联合**    **联合**合作伙伴类型表示 Lync Server 部署与 XMPP 合作伙伴之间的高信任级别。</span><span class="sxs-lookup"><span data-stu-id="46fa7-153">**Federated**   A **Federated** partner type represents a high level of trust between the Lync Server deployment and the XMPP partner.</span></span><span data-ttu-id="46fa7-154">建议使用此合作伙伴类型与同一企业内的 XMPP 服务器进行联盟，或者存在已建立的业务关系。</span><span class="sxs-lookup"><span data-stu-id="46fa7-154">  This partner type is recommended for federating with XMPP servers within the same enterprise or where there is an established business relationship.</span></span><span data-ttu-id="46fa7-155">联盟伙伴中的 XMPP 联系人可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="46fa7-155">  XMPP contacts in Federated partners can:</span></span>
        
        1.  <span data-ttu-id="46fa7-156">添加 Lync 联系人并查看其状态，而无需明确的 Lync 用户授权。</span><span class="sxs-lookup"><span data-stu-id="46fa7-156">Add Lync contacts and view their presence without express authorization from the Lync user.</span></span>
        
        2.  <span data-ttu-id="46fa7-157">向 Lync 联系人发送即时消息，无论 Lync 用户是否已将他们添加到其联系人列表。</span><span class="sxs-lookup"><span data-stu-id="46fa7-157">Send instant messages to Lync contacts whether or not the Lync user has added them into their contact list.</span></span>
        
        3.  <span data-ttu-id="46fa7-158">查看 Lync 用户的状态注释。</span><span class="sxs-lookup"><span data-stu-id="46fa7-158">See a Lync user’s status notes.</span></span>
    
      - <span data-ttu-id="46fa7-159">**公共验证**    **公共验证**合作伙伴是一个公开的公共 XMPP 提供程序，可信任它来验证其用户的身份。</span><span class="sxs-lookup"><span data-stu-id="46fa7-159">**Public verified**   A **Public verified** partner is a public XMPP provider that is trusted to verify the identity of its users.</span></span><span data-ttu-id="46fa7-160">公共验证的网络中的 XMPP 联系人可以添加 Lync 联系人并查看它们的状态，并向其发送即时消息，而无需通过 Lync 用户的认证。</span><span class="sxs-lookup"><span data-stu-id="46fa7-160">  XMPP contacts in Public Verified networks can add Lync contacts and view their presence and send instant messages to them without express authorization from the Lync users.</span></span><span data-ttu-id="46fa7-161">公共验证的网络中的 XMPP 联系人永远不会看到 Lync 用户的状态笔记。</span><span class="sxs-lookup"><span data-stu-id="46fa7-161">  XMPP contacts in public verified networks never see a Lync users’ status notes.</span></span><span data-ttu-id="46fa7-162">建议不要使用此设置。</span><span class="sxs-lookup"><span data-stu-id="46fa7-162">  This setting is not recommended.</span></span>
    
      - <span data-ttu-id="46fa7-163">**公共未验证**    未经验证的**公共**合作伙伴是一个公共 XMPP 提供程序，它不受信任，无法验证其用户的身份。</span><span class="sxs-lookup"><span data-stu-id="46fa7-163">**Public unverified**   A **Public unverified** partner is a public XMPP provider that is not trusted to verify the identity of its users.</span></span><span data-ttu-id="46fa7-164">公共未验证网络上的 XMPP 用户无法与 Lync 用户通信，除非 Lync 用户已通过将其添加到联系人列表中进行了明确授权。</span><span class="sxs-lookup"><span data-stu-id="46fa7-164">  XMPP users on Public Unverified networks cannot communicate with Lync users unless the Lync user has expressly authorized them by adding them to the contact list.</span></span><span data-ttu-id="46fa7-165">公共未验证网络上的 XMPP 用户永远不会看到 Lync 用户的状态说明。</span><span class="sxs-lookup"><span data-stu-id="46fa7-165">  XMPP users on public unverified networks never see Lync users’ status notes.</span></span><span data-ttu-id="46fa7-166">对于具有公共 XMPP 提供商（如 Google 谈话）的任何联盟，建议使用此设置。</span><span class="sxs-lookup"><span data-stu-id="46fa7-166">  This setting is recommended for any federation with public XMPP providers such as Google Talk.</span></span>

9.  <span data-ttu-id="46fa7-167">**连接类型：** 定义各种规则和回拨设置。</span><span class="sxs-lookup"><span data-stu-id="46fa7-167">**Connection Type:** Defines the various rules and dialback settings.</span></span>
    
      - <span data-ttu-id="46fa7-168">**TLS 协商**    定义 TLS 协商规则。</span><span class="sxs-lookup"><span data-stu-id="46fa7-168">**TLS Negotiation**   Defines the TLS negotiation rules.</span></span> <span data-ttu-id="46fa7-169">XMPP 服务可能需要 TLS，可以使 TLS 成为可选的，也可以定义不支持 TLS。</span><span class="sxs-lookup"><span data-stu-id="46fa7-169">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="46fa7-170">选择 "可选" 将要求留给 XMPP 服务进行强制性协商决策。</span><span class="sxs-lookup"><span data-stu-id="46fa7-170">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="46fa7-171">若要查看所有可能的设置和有关 SASL、TLS 和回拨的详细信息（包括无效和已知的错误配置），请参阅 [Lync Server 2013 中的 XMPP 联盟伙伴的协商设置](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)。</span><span class="sxs-lookup"><span data-stu-id="46fa7-171">To view all possible settings and details for SASL, TLS and Dialback negotiation –including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span></span>
        
          - <span></span>  
            <span data-ttu-id="46fa7-172">**必需**    XMPP 服务需要 TLS 协商。</span><span class="sxs-lookup"><span data-stu-id="46fa7-172">**Required**   The XMPP service requires TLS negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="46fa7-173">**可选**    XMPP 服务指示 TLS 是强制性的协商。</span><span class="sxs-lookup"><span data-stu-id="46fa7-173">**Optional**   The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="46fa7-174">**不支持**    XMPP 服务不支持 TLS。</span><span class="sxs-lookup"><span data-stu-id="46fa7-174">**Not Supported**   The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="46fa7-175">**SASL 协商**    定义 SASL 协商规则。</span><span class="sxs-lookup"><span data-stu-id="46fa7-175">**SASL negotiation**   Defines the SASL negotiation rules.</span></span> <span data-ttu-id="46fa7-176">XMPP 服务可能需要 SASL，可以使 SASL 成为可选的，也可以定义不支持 SASL。</span><span class="sxs-lookup"><span data-stu-id="46fa7-176">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="46fa7-177">选择 "可选" 将要求留给合作伙伴 XMPP 服务进行强制性的协商决策。</span><span class="sxs-lookup"><span data-stu-id="46fa7-177">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
          - <span></span>  
            <span data-ttu-id="46fa7-178">**必需**    XMPP 服务需要 SASL 协商。</span><span class="sxs-lookup"><span data-stu-id="46fa7-178">**Required**   The XMPP service requires SASL negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="46fa7-179">**可选**    XMPP 服务指示 SASL 是强制性的协商。</span><span class="sxs-lookup"><span data-stu-id="46fa7-179">**Optional**   The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="46fa7-180">**不支持**    XMPP 服务不支持 SASL。</span><span class="sxs-lookup"><span data-stu-id="46fa7-180">**Not Supported**   The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="46fa7-181">**支持服务器回拨协商** 支持服务器回拨协商进程使用域名系统 (DNS) 和权威服务器来验证请求是否来自有效的 XMPP 合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="46fa7-181">**Support server dialback negotiation** The support server dialback negotiation process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="46fa7-182">若要执行此操作，起始服务器将使用生成的回拨密钥创建特定类型的邮件，并在 DNS 中查找接收服务器。</span><span class="sxs-lookup"><span data-stu-id="46fa7-182">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="46fa7-183">源服务器将 XML 流中的密钥发送到生成的 DNS 查找，大概是接收服务器。</span><span class="sxs-lookup"><span data-stu-id="46fa7-183">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="46fa7-184">在 XML 流上收到密钥后，接收服务器不会响应原始服务器，但会将密钥发送到已知的权威服务器。</span><span class="sxs-lookup"><span data-stu-id="46fa7-184">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="46fa7-185">权威服务器验证密钥有效或无效。</span><span class="sxs-lookup"><span data-stu-id="46fa7-185">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="46fa7-186">如果无效，则接收服务器不会对原始服务器做出响应。</span><span class="sxs-lookup"><span data-stu-id="46fa7-186">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="46fa7-187">如果密钥有效，则接收服务器会通知发起服务器标识和密钥有效，并且会话可以开始。</span><span class="sxs-lookup"><span data-stu-id="46fa7-187">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="46fa7-188">**回拨协商**具有两种有效状态：</span><span class="sxs-lookup"><span data-stu-id="46fa7-188">There are two valid states for **Dialback negotiation**:</span></span>
        
          - <span></span>  
            <span data-ttu-id="46fa7-189">**True**    如果应收到来自发起服务器的请求，则将 XMPP 服务器配置为使用回拨协商。</span><span class="sxs-lookup"><span data-stu-id="46fa7-189">**True**   The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server.</span></span>
        
          - <span></span>  
            <span data-ttu-id="46fa7-190">**False**    未将 XMPP 服务器配置为使用回拨协商，如果应收到来自发起服务器的请求，则将忽略该请求。</span><span class="sxs-lookup"><span data-stu-id="46fa7-190">**False**   The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored.</span></span>

10. <span data-ttu-id="46fa7-191">单击“提交”\*\*\*\* 保存对站点或用户策略的更改。</span><span class="sxs-lookup"><span data-stu-id="46fa7-191">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="46fa7-192">更新 Lync Server 2013 XMPP 网关的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="46fa7-192">Update DNS Records for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="46fa7-193">若要为 XMPP 联合配置 DNS，请将以下 SRV 记录添加到外部 DNS： \_ XMPP-server。 \_rdp-tcp.\<domain name\></span><span class="sxs-lookup"><span data-stu-id="46fa7-193">To configure DNS for XMPP federation, you add the following SRV record to your external DNS:\_xmpp-server.\_tcp.\<domain name\></span></span> <span data-ttu-id="46fa7-194">SRV 记录将解析为边缘服务器的访问边缘 FQDN，端口值为5269。</span><span class="sxs-lookup"><span data-stu-id="46fa7-194">The SRV record will resolve to the Access Edge FQDN of the Edge server, with a port value of 5269.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

