---
title: 在 Lync Server 2013 上配置 XMPP 网关
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
ms.openlocfilehash: 30dc21ddbbfd5d65d6834ffa5a6181c5e4a13b1c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503179"
---
# <a name="configure-xmpp-gateway-on-lync-server-2013"></a><span data-ttu-id="49640-102">在 Lync Server 2013 上配置 XMPP 网关</span><span class="sxs-lookup"><span data-stu-id="49640-102">Configure XMPP gateway on Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49640-103">_**上次修改的主题：** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="49640-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="49640-104">迁移 XMPP 网关的最后一步是为 Lync Server 2013 Edge 服务器配置证书，部署 Lync Server 2013 XMPP 网关，并更新 XMPP 网关的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="49640-104">The final steps for migrating your XMPP Gateway are to configure certificates for the Lync Server 2013 Edge Server, deploy the Lync Server 2013 XMPP Gateway, and update the DNS records for the XMPP Gateway.</span></span> <span data-ttu-id="49640-105">这些步骤应该并行执行，以尽可能缩短 XMPP 网关的停机时间。</span><span class="sxs-lookup"><span data-stu-id="49640-105">These steps should be performed in parallel to minimize the down time of your XMPP Gateway.</span></span> <span data-ttu-id="49640-106">在执行这些步骤之前，必须将所有用户移到 Microsoft Lync Server 2013 部署中。</span><span class="sxs-lookup"><span data-stu-id="49640-106">All users must be moved to your Microsoft Lync Server 2013 deployment before performing these steps.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="49640-107">对于驻留在 survivable 分支设备上的用户，不支持 XMPP 联盟。</span><span class="sxs-lookup"><span data-stu-id="49640-107">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="49640-108">这适用于查看状态信息和交换 IM 消息。</span><span class="sxs-lookup"><span data-stu-id="49640-108">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="49640-109">在 Lync Server 2013 边缘服务器上配置 XMPP 网关证书。</span><span class="sxs-lookup"><span data-stu-id="49640-109">Configure XMPP Gateway Certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="49640-110">在边缘服务器上，单击部署向导中“步骤 3：请求、安装或分配证书”\*\*\*\* 旁边的“再次运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="49640-110">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="49640-111">如果您第一次部署边缘服务器，您将看到“运行”而不是“再次运行”。</span><span class="sxs-lookup"><span data-stu-id="49640-111">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

2.  <span data-ttu-id="49640-112">在“可用的证书任务”\*\*\*\* 页上，单击“创建新的证书请求”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="49640-112">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="49640-113">在“证书请求”\*\*\*\* 页上，单击“外部边缘证书”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="49640-113">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="49640-114">在“延迟的请求或即时请求”\*\*\*\* 页上，选中“立即准备请求，但是稍后发送”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="49640-114">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="49640-115">在 " **证书请求文件** " 页上，键入要将请求保存到的文件的完整路径和文件名 (例如，c： \\ cert \_ 外部 \_ edge) 。</span><span class="sxs-lookup"><span data-stu-id="49640-115">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="49640-116">在“指定替代证书模板”\*\*\*\* 页上，要使用除默认 WebServer 模板之外的模板，请选中“对选定的证书颁发机构使用替代证书模板”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="49640-116">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="49640-117">在“名称和安全设置”\*\*\*\* 页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="49640-117">On the **Name and Security Settings** page, do the following:</span></span>
    
    1.  <span data-ttu-id="49640-118">在“友好名称”\*\*\*\* 中，键入证书的显示名称。</span><span class="sxs-lookup"><span data-stu-id="49640-118">In **Friendly name**, type a display name for the certificate.</span></span>
    
    2.  <span data-ttu-id="49640-119">在“位长度”\*\*\*\* 中，指定位长度（通常默认值为 2048）。</span><span class="sxs-lookup"><span data-stu-id="49640-119">In **Bit length**, specify the bit length (typically, the default of 2048).</span></span>
    
    3.  <span data-ttu-id="49640-120">验证是否选中了“将证书私钥标记为可导出”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="49640-120">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="49640-121">在“组织信息”\*\*\*\* 页上，键入组织和组织单位（例如分部或部门）的名称。</span><span class="sxs-lookup"><span data-stu-id="49640-121">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="49640-122">在“地理信息”\*\*\*\* 页上，指定位置信息。</span><span class="sxs-lookup"><span data-stu-id="49640-122">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="49640-p103">在“使用者名称/使用者替代名称”\*\*\*\* 页上，将显示向导自动填充的信息。如果需要其他使用者替代名称，可以在接下来的两个步骤中指定。</span><span class="sxs-lookup"><span data-stu-id="49640-p103">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="49640-125">在 " \*\*使用者替代名称 (SANs) \*\* " 页上的 "SIP 域设置" 中，选中 "域" 复选框以添加 SIP。\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="49640-125">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\></span></span> <span data-ttu-id="49640-126">"主题备用名称" 列表中的条目。</span><span class="sxs-lookup"><span data-stu-id="49640-126">entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="49640-127">在“配置其他使用者替代名称”\*\*\*\* 页上，指定所需的任何其他使用者替代名称。</span><span class="sxs-lookup"><span data-stu-id="49640-127">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="49640-p105">如果安装了 XMPP 代理，则默认情况下域名（如 contoso.com）填充在 SAN 条目中。如果您需要更多条目，请在此步骤中添加它们。</span><span class="sxs-lookup"><span data-stu-id="49640-p105">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries. If you require more entries, add them in this step.</span></span>

    
    </div>

13. <span data-ttu-id="49640-130">在“请求摘要”\*\*\*\* 页上，检查要用于生成请求的证书信息。</span><span class="sxs-lookup"><span data-stu-id="49640-130">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="49640-131">在命令运行完毕后，您可以“查看日志”\*\*\*\*，或单击“下一步”继续操作。</span><span class="sxs-lookup"><span data-stu-id="49640-131">After the commands finish running, you can **View Log**, or click Next to continue.</span></span>

15. <span data-ttu-id="49640-132">在“证书请求文件”\*\*\*\* 页上，您可以通过单击“查看”\*\*\*\* 来查看生成的证书签名请求 (CSR) 文件，或通过单击“完成”\*\*\*\* 来退出证书向导。</span><span class="sxs-lookup"><span data-stu-id="49640-132">On the **Certificate Request File** page, you can view the generated certificate signing request (CSR) file by clicking **View** or exit the Certificate Wizard by clicking **Finish**.</span></span>

16. <span data-ttu-id="49640-133">复制请求文件并提交至公共证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="49640-133">Copy the request file and submit to your public certification authority.</span></span>

17. <span data-ttu-id="49640-p106">在接收、导入和分配公共证书后，您必须停止边缘服务器服务，然后重新启动它。为此，请在 Lync Server 管理控制台中键入：</span><span class="sxs-lookup"><span data-stu-id="49640-p106">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services. You do this by typing in the Lync Server Management console:</span></span>
    
        Stop-CsWindowsService

      &nbsp;
    
        Start-CsWindowsService

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="49640-136">配置新的 Lync Server 2013 XMPP 网关</span><span class="sxs-lookup"><span data-stu-id="49640-136">Configure a new Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="49640-137">打开“Lync Server 控制面板”。</span><span class="sxs-lookup"><span data-stu-id="49640-137">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="49640-138">在左侧导航栏中，单击“联盟和外部访问”\*\*\*\*，然后单击“XMPP 联盟伙伴”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="49640-138">In the left navigation bar, click **Federation and External Access** and then click **XMPP Federated Partners**.</span></span>

3.  <span data-ttu-id="49640-139">要创建新配置，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="49640-139">To create a new configuration, click **New**.</span></span>

4.  <span data-ttu-id="49640-140">定义以下设置：</span><span class="sxs-lookup"><span data-stu-id="49640-140">Define the following settings:</span></span>

5.  <span data-ttu-id="49640-141">**主域**     (必需的) 。</span><span class="sxs-lookup"><span data-stu-id="49640-141">**Primary domain**    (Required).</span></span> <span data-ttu-id="49640-142">主域是 XMPP 合作伙伴的基本域。</span><span class="sxs-lookup"><span data-stu-id="49640-142">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="49640-143">例如，可为 XMPP 合作伙伴域名输入 **fabrikam.com**。</span><span class="sxs-lookup"><span data-stu-id="49640-143">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="49640-144">这是必填项。</span><span class="sxs-lookup"><span data-stu-id="49640-144">This is a required entry.</span></span>

6.  <span data-ttu-id="49640-145">**说明**    该说明针对此特定配置的注释或其他标识信息。</span><span class="sxs-lookup"><span data-stu-id="49640-145">**Description**   The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="49640-146">此条目是可选的。</span><span class="sxs-lookup"><span data-stu-id="49640-146">This entry is optional.</span></span>

7.  <span data-ttu-id="49640-147">**其他域**    其他域是作为 XMPP 合作伙伴的域一部分的域，应作为允许的 XMPP 通信的一部分包括在内。</span><span class="sxs-lookup"><span data-stu-id="49640-147">**Additional domains**   Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="49640-148">例如，如果主域为 **fabrikam.com**，则将列出位于 fabrikam.com 中的所有其他域，您将使用 XMPP 的方式进行通信。</span><span class="sxs-lookup"><span data-stu-id="49640-148">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span>

8.  <span data-ttu-id="49640-149">**合作伙伴类型**    "**合作伙伴类型**" 是必需的设置。</span><span class="sxs-lookup"><span data-stu-id="49640-149">**Partner type**   The **Partner type** is a required setting.</span></span> <span data-ttu-id="49640-150">您必须选择以下项之一来描述和强制添加可添加的联系人。</span><span class="sxs-lookup"><span data-stu-id="49640-150">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="49640-151">您可以从以下选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="49640-151">You can select from:</span></span>
    
      - <span data-ttu-id="49640-152">**联合**    **联合**合作伙伴类型表示 Lync Server 部署与 XMPP 合作伙伴之间的高信任级别。</span><span class="sxs-lookup"><span data-stu-id="49640-152">**Federated**   A **Federated** partner type represents a high level of trust between the Lync Server deployment and the XMPP partner.</span></span><span data-ttu-id="49640-153">建议使用此合作伙伴类型与同一企业内的 XMPP 服务器进行联盟，或者存在已建立的业务关系。</span><span class="sxs-lookup"><span data-stu-id="49640-153">  This partner type is recommended for federating with XMPP servers within the same enterprise or where there is an established business relationship.</span></span><span data-ttu-id="49640-154">联盟伙伴中的 XMPP 联系人可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="49640-154">  XMPP contacts in Federated partners can:</span></span>
        
        1.  <span data-ttu-id="49640-155">添加 Lync 联系人并查看其状态，而无需明确的 Lync 用户授权。</span><span class="sxs-lookup"><span data-stu-id="49640-155">Add Lync contacts and view their presence without express authorization from the Lync user.</span></span>
        
        2.  <span data-ttu-id="49640-156">向 Lync 联系人发送即时消息，无论 Lync 用户是否已将他们添加到其联系人列表。</span><span class="sxs-lookup"><span data-stu-id="49640-156">Send instant messages to Lync contacts whether or not the Lync user has added them into their contact list.</span></span>
        
        3.  <span data-ttu-id="49640-157">查看 Lync 用户的状态注释。</span><span class="sxs-lookup"><span data-stu-id="49640-157">See a Lync user’s status notes.</span></span>
    
      - <span data-ttu-id="49640-158">**公共验证**    **公共验证**合作伙伴是一个公开的公共 XMPP 提供程序，可信任它来验证其用户的身份。</span><span class="sxs-lookup"><span data-stu-id="49640-158">**Public verified**   A **Public verified** partner is a public XMPP provider that is trusted to verify the identity of its users.</span></span><span data-ttu-id="49640-159">公共验证的网络中的 XMPP 联系人可以添加 Lync 联系人并查看它们的状态，并向其发送即时消息，而无需通过 Lync 用户的认证。</span><span class="sxs-lookup"><span data-stu-id="49640-159">  XMPP contacts in Public Verified networks can add Lync contacts and view their presence and send instant messages to them without express authorization from the Lync users.</span></span><span data-ttu-id="49640-160">公共验证的网络中的 XMPP 联系人永远不会看到 Lync 用户的状态笔记。</span><span class="sxs-lookup"><span data-stu-id="49640-160">  XMPP contacts in public verified networks never see a Lync users’ status notes.</span></span><span data-ttu-id="49640-161">建议不要使用此设置。</span><span class="sxs-lookup"><span data-stu-id="49640-161">  This setting is not recommended.</span></span>
    
      - <span data-ttu-id="49640-162">**公共未验证**    未经验证的**公共**合作伙伴是一个公共 XMPP 提供程序，它不受信任，无法验证其用户的身份。</span><span class="sxs-lookup"><span data-stu-id="49640-162">**Public unverified**   A **Public unverified** partner is a public XMPP provider that is not trusted to verify the identity of its users.</span></span><span data-ttu-id="49640-163">公共未验证网络上的 XMPP 用户无法与 Lync 用户通信，除非 Lync 用户已通过将其添加到联系人列表中进行了明确授权。</span><span class="sxs-lookup"><span data-stu-id="49640-163">  XMPP users on Public Unverified networks cannot communicate with Lync users unless the Lync user has expressly authorized them by adding them to the contact list.</span></span><span data-ttu-id="49640-164">公共未验证网络上的 XMPP 用户永远不会看到 Lync 用户的状态说明。</span><span class="sxs-lookup"><span data-stu-id="49640-164">  XMPP users on public unverified networks never see Lync users’ status notes.</span></span><span data-ttu-id="49640-165">对于具有公共 XMPP 提供商（如 Google 谈话）的任何联盟，建议使用此设置。</span><span class="sxs-lookup"><span data-stu-id="49640-165">  This setting is recommended for any federation with public XMPP providers such as Google Talk.</span></span>

9.  <span data-ttu-id="49640-166">**连接类型：** 定义各种规则和回拨设置。</span><span class="sxs-lookup"><span data-stu-id="49640-166">**Connection Type:** Defines the various rules and dialback settings.</span></span>
    
      - <span data-ttu-id="49640-167">**TLS 协商**    定义 TLS 协商规则。</span><span class="sxs-lookup"><span data-stu-id="49640-167">**TLS Negotiation**   Defines the TLS negotiation rules.</span></span> <span data-ttu-id="49640-168">XMPP 服务可能需要 TLS，可以使 TLS 成为可选的，也可以定义不支持 TLS。</span><span class="sxs-lookup"><span data-stu-id="49640-168">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="49640-169">选择 "可选" 将要求留给 XMPP 服务进行强制性协商决策。</span><span class="sxs-lookup"><span data-stu-id="49640-169">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="49640-170">若要查看所有可能的设置和有关 SASL、TLS 和回拨的详细信息（包括无效和已知的错误配置），请参阅 [Lync Server 2013 中的 XMPP 联盟伙伴的协商设置](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)。</span><span class="sxs-lookup"><span data-stu-id="49640-170">To view all possible settings and details for SASL, TLS and Dialback negotiation –including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span></span>
        
          - <span></span>  
            <span data-ttu-id="49640-171">**必需**    XMPP 服务需要 TLS 协商。</span><span class="sxs-lookup"><span data-stu-id="49640-171">**Required**   The XMPP service requires TLS negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="49640-172">**可选**    XMPP 服务指示 TLS 是强制性的协商。</span><span class="sxs-lookup"><span data-stu-id="49640-172">**Optional**   The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="49640-173">**不支持**    XMPP 服务不支持 TLS。</span><span class="sxs-lookup"><span data-stu-id="49640-173">**Not Supported**   The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="49640-174">**SASL 协商**    定义 SASL 协商规则。</span><span class="sxs-lookup"><span data-stu-id="49640-174">**SASL negotiation**   Defines the SASL negotiation rules.</span></span> <span data-ttu-id="49640-175">XMPP 服务可能需要 SASL，可以使 SASL 成为可选的，也可以定义不支持 SASL。</span><span class="sxs-lookup"><span data-stu-id="49640-175">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="49640-176">选择 "可选" 将要求留给合作伙伴 XMPP 服务进行强制性的协商决策。</span><span class="sxs-lookup"><span data-stu-id="49640-176">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
          - <span></span>  
            <span data-ttu-id="49640-177">**必需**    XMPP 服务需要 SASL 协商。</span><span class="sxs-lookup"><span data-stu-id="49640-177">**Required**   The XMPP service requires SASL negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="49640-178">**可选**    XMPP 服务指示 SASL 是强制性的协商。</span><span class="sxs-lookup"><span data-stu-id="49640-178">**Optional**   The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="49640-179">**不支持**    XMPP 服务不支持 SASL。</span><span class="sxs-lookup"><span data-stu-id="49640-179">**Not Supported**   The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="49640-180">**支持服务器回拨协商** 支持服务器回拨协商进程使用域名系统 (DNS) 和权威服务器来验证请求是否来自有效的 XMPP 合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="49640-180">**Support server dialback negotiation** The support server dialback negotiation process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="49640-181">若要执行此操作，起始服务器将使用生成的回拨密钥创建特定类型的邮件，并在 DNS 中查找接收服务器。</span><span class="sxs-lookup"><span data-stu-id="49640-181">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="49640-182">源服务器将 XML 流中的密钥发送到生成的 DNS 查找，大概是接收服务器。</span><span class="sxs-lookup"><span data-stu-id="49640-182">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="49640-183">在 XML 流上收到密钥后，接收服务器不会响应原始服务器，但会将密钥发送到已知的权威服务器。</span><span class="sxs-lookup"><span data-stu-id="49640-183">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="49640-184">权威服务器验证密钥有效或无效。</span><span class="sxs-lookup"><span data-stu-id="49640-184">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="49640-185">如果无效，则接收服务器不会对原始服务器做出响应。</span><span class="sxs-lookup"><span data-stu-id="49640-185">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="49640-186">如果密钥有效，则接收服务器会通知发起服务器标识和密钥有效，并且会话可以开始。</span><span class="sxs-lookup"><span data-stu-id="49640-186">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="49640-187">**回拨协商**具有两种有效状态：</span><span class="sxs-lookup"><span data-stu-id="49640-187">There are two valid states for **Dialback negotiation**:</span></span>
        
          - <span></span>  
            <span data-ttu-id="49640-188">**True**    如果应收到来自发起服务器的请求，则将 XMPP 服务器配置为使用回拨协商。</span><span class="sxs-lookup"><span data-stu-id="49640-188">**True**   The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server.</span></span>
        
          - <span></span>  
            <span data-ttu-id="49640-189">**False**    未将 XMPP 服务器配置为使用回拨协商，如果应收到来自发起服务器的请求，则将忽略该请求。</span><span class="sxs-lookup"><span data-stu-id="49640-189">**False**   The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored.</span></span>

10. <span data-ttu-id="49640-190">单击“提交”\*\*\*\* 保存对站点或用户策略的更改。</span><span class="sxs-lookup"><span data-stu-id="49640-190">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="49640-191">更新 Lync Server 2013 XMPP 网关的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="49640-191">Update DNS Records for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="49640-192">若要为 XMPP 联合配置 DNS，请将以下 SRV 记录添加到外部 DNS： \_ XMPP-server。 \_rdp-tcp.\<domain name\></span><span class="sxs-lookup"><span data-stu-id="49640-192">To configure DNS for XMPP federation, you add the following SRV record to your external DNS:\_xmpp-server.\_tcp.\<domain name\></span></span> <span data-ttu-id="49640-193">SRV 记录将解析为边缘服务器的访问边缘 FQDN，端口值为5269。</span><span class="sxs-lookup"><span data-stu-id="49640-193">The SRV record will resolve to the Access Edge FQDN of the Edge server, with a port value of 5269.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

