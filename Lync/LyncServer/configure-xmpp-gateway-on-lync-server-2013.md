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
ms.openlocfilehash: 2910766dbb2147fa5d1c51235f10ab2e80826bda
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723212"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a><span data-ttu-id="0b110-102">在 Lync Server 2013 上配置 XMPP 网关</span><span class="sxs-lookup"><span data-stu-id="0b110-102">Configure XMPP gateway on Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b110-103">_**主题上次修改时间：** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="0b110-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="0b110-104">迁移 XMPP 网关的最终步骤是配置 Lync Server 2013 Edge 服务器的证书，部署 Lync Server 2013 XMPP 网关，并更新 XMPP 网关的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="0b110-104">The final steps for migrating your XMPP Gateway are to configure certificates for the Lync Server 2013 Edge Server, deploy the Lync Server 2013 XMPP Gateway, and update the DNS records for the XMPP Gateway.</span></span> <span data-ttu-id="0b110-105">这些步骤应并行执行，以最大限度地减少 XMPP 网关的停机时间。</span><span class="sxs-lookup"><span data-stu-id="0b110-105">These steps should be performed in parallel to minimize the down time of your XMPP Gateway.</span></span> <span data-ttu-id="0b110-106">在执行这些步骤之前，必须将所有用户移到 Microsoft Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="0b110-106">All users must be moved to your Microsoft Lync Server 2013 deployment before performing these steps.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="0b110-107">对于托管在 survivable 分支设备上的用户，不支持 XMPP 联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="0b110-107">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="0b110-108">这适用于查看状态信息和交换 IM 消息。</span><span class="sxs-lookup"><span data-stu-id="0b110-108">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="0b110-109">在 Lync Server 2013 Edge 服务器上配置 XMPP 网关证书</span><span class="sxs-lookup"><span data-stu-id="0b110-109">Configure XMPP Gateway Certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="0b110-110">在边缘服务器上的 "部署向导" 中，在 "**步骤3：请求、安装或分配证书**" 旁边，再次单击 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="0b110-110">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="0b110-111">如果你是首次部署 Edge 服务器，你将看到 "运行"，而不是再次运行。</span><span class="sxs-lookup"><span data-stu-id="0b110-111">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

2.  <span data-ttu-id="0b110-112">在“**可用的证书任务**”页上，单击“**创建新的证书请求**”。</span><span class="sxs-lookup"><span data-stu-id="0b110-112">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="0b110-113">在 "**证书请求**" 页面上，单击 "**外部边缘证书**"。</span><span class="sxs-lookup"><span data-stu-id="0b110-113">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="0b110-114">在 "**延迟或立即请求**" 页面上，选中 "**立即准备请求，但稍后发送"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="0b110-114">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="0b110-115">在 "**证书请求文件**" 页面上，键入要保存请求的文件的完整路径和文件名（例如，c：\\cert\_外部\_edge）。</span><span class="sxs-lookup"><span data-stu-id="0b110-115">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="0b110-116">在 "**指定备用证书模板**" 页面上，若要使用默认 web 台模板之外的模板，请选中 "**为所选证书颁发机构使用备用证书模板**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="0b110-116">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="0b110-117">在 "**名称和安全设置**" 页面上，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="0b110-117">On the **Name and Security Settings** page, do the following:</span></span>
    
    1.  <span data-ttu-id="0b110-118">在 "**友好名称**" 中，键入证书的显示名称。</span><span class="sxs-lookup"><span data-stu-id="0b110-118">In **Friendly name**, type a display name for the certificate.</span></span>
    
    2.  <span data-ttu-id="0b110-119">在 "**位长度**" 中，指定位长度（通常为默认值2048）。</span><span class="sxs-lookup"><span data-stu-id="0b110-119">In **Bit length**, specify the bit length (typically, the default of 2048).</span></span>
    
    3.  <span data-ttu-id="0b110-120">验证 "将**证书私钥标记为可导出**" 复选框是否已选中。</span><span class="sxs-lookup"><span data-stu-id="0b110-120">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="0b110-121">在 "**组织信息**" 页面上，键入组织和组织单位的名称（例如，"部门" 或 "部门"）。</span><span class="sxs-lookup"><span data-stu-id="0b110-121">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="0b110-122">在 "**地理信息**" 页面上，指定位置信息。</span><span class="sxs-lookup"><span data-stu-id="0b110-122">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="0b110-123">在 "**主题名称/主题备用名称**" 页面上，将显示要由向导自动填充的信息。</span><span class="sxs-lookup"><span data-stu-id="0b110-123">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="0b110-124">如果需要其他主题备用名称，请在接下来的两个步骤中进行指定。</span><span class="sxs-lookup"><span data-stu-id="0b110-124">If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="0b110-125">在 "**主题备用名称（san）** " 页面上的 "SIP 域设置" 中，选中 "域" 复选框以添加 SIP。\<sipdomain\>条目到 "主题备用名称" 列表。</span><span class="sxs-lookup"><span data-stu-id="0b110-125">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="0b110-126">在 "**配置其他主题备用名称**" 页面上，指定所需的任何其他主题备用名称。</span><span class="sxs-lookup"><span data-stu-id="0b110-126">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="0b110-127">如果 XMPP 代理已安装，则默认情况下会在 SAN 条目中填充域名（如 contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="0b110-127">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries.</span></span> <span data-ttu-id="0b110-128">如果需要更多条目，请在此步骤中添加这些条目。</span><span class="sxs-lookup"><span data-stu-id="0b110-128">If you require more entries, add them in this step.</span></span>

    
    </div>

13. <span data-ttu-id="0b110-129">在 "**请求摘要**" 页面上，查看要用于生成请求的证书信息。</span><span class="sxs-lookup"><span data-stu-id="0b110-129">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="0b110-130">命令完成运行后，您可以**查看日志**，或单击 "下一步" 继续。</span><span class="sxs-lookup"><span data-stu-id="0b110-130">After the commands finish running, you can **View Log**, or click Next to continue.</span></span>

15. <span data-ttu-id="0b110-131">在 "**证书请求文件**" 页面上，您可以通过单击 "**查看**或退出证书向导" 查看生成的证书签名请求（CSR）文件，方法是单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="0b110-131">On the **Certificate Request File** page, you can view the generated certificate signing request (CSR) file by clicking **View** or exit the Certificate Wizard by clicking **Finish**.</span></span>

16. <span data-ttu-id="0b110-132">将请求文件复制并提交到公共证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="0b110-132">Copy the request file and submit to your public certification authority.</span></span>

17. <span data-ttu-id="0b110-133">接收、导入和分配公共证书后，必须停止并重新启动 Edge 服务器服务。</span><span class="sxs-lookup"><span data-stu-id="0b110-133">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services.</span></span> <span data-ttu-id="0b110-134">可通过在 Lync Server 管理控制台中键入以下内容来执行此操作：</span><span class="sxs-lookup"><span data-stu-id="0b110-134">You do this by typing in the Lync Server Management console:</span></span>
    
        Stop-CsWindowsService

      &nbsp;
    
        Start-CsWindowsService

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="0b110-135">配置新的 Lync Server 2013 XMPP 网关</span><span class="sxs-lookup"><span data-stu-id="0b110-135">Configure a new Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="0b110-136">打开“Lync Server 控制面板”。</span><span class="sxs-lookup"><span data-stu-id="0b110-136">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="0b110-137">在左侧导航栏中，单击 "**联盟和外部访问**"，然后单击 " **XMPP 联盟合作伙伴**"。</span><span class="sxs-lookup"><span data-stu-id="0b110-137">In the left navigation bar, click **Federation and External Access** and then click **XMPP Federated Partners**.</span></span>

3.  <span data-ttu-id="0b110-138">若要创建新配置，请单击 "**新建**"。</span><span class="sxs-lookup"><span data-stu-id="0b110-138">To create a new configuration, click **New**.</span></span>

4.  <span data-ttu-id="0b110-139">定义以下设置：</span><span class="sxs-lookup"><span data-stu-id="0b110-139">Define the following settings:</span></span>

5.  <span data-ttu-id="0b110-140">**主域**    （必需）。</span><span class="sxs-lookup"><span data-stu-id="0b110-140">**Primary domain**    (Required).</span></span> <span data-ttu-id="0b110-141">主要域是 XMPP 合作伙伴的基础域。</span><span class="sxs-lookup"><span data-stu-id="0b110-141">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="0b110-142">例如，你可以为 XMPP 合作伙伴域名输入**fabrikam.com** 。</span><span class="sxs-lookup"><span data-stu-id="0b110-142">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="0b110-143">这是一个必需的条目。</span><span class="sxs-lookup"><span data-stu-id="0b110-143">This is a required entry.</span></span>

6.  <span data-ttu-id="0b110-144">**说明**   此说明适用于此特定配置的注释或其他标识信息。</span><span class="sxs-lookup"><span data-stu-id="0b110-144">**Description**   The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="0b110-145">此条目是可选的。</span><span class="sxs-lookup"><span data-stu-id="0b110-145">This entry is optional.</span></span>

7.  <span data-ttu-id="0b110-146">**其他域**   其他域是 XMPP 合作伙伴所在域的一部分的域，应包括在允许的 XMPP 通信中。</span><span class="sxs-lookup"><span data-stu-id="0b110-146">**Additional domains**   Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="0b110-147">例如，如果主域是**fabrikam.com**，则会列出您将通过 XMPP 进行通信的 fabrikam.com 下的所有其他域。</span><span class="sxs-lookup"><span data-stu-id="0b110-147">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span>

8.  <span data-ttu-id="0b110-148">**合作伙伴类型**   **合作伙伴类型**是必需的设置。</span><span class="sxs-lookup"><span data-stu-id="0b110-148">**Partner type**   The **Partner type** is a required setting.</span></span> <span data-ttu-id="0b110-149">您必须选择下列内容之一来描述和强制执行哪些联系人可以添加。</span><span class="sxs-lookup"><span data-stu-id="0b110-149">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="0b110-150">您可以选择：</span><span class="sxs-lookup"><span data-stu-id="0b110-150">You can select from:</span></span>
    
      - <span data-ttu-id="0b110-151">**联合**   **联盟**合作伙伴类型表示 Lync Server 部署与 XMPP 合作伙伴之间的高信任级别。</span><span class="sxs-lookup"><span data-stu-id="0b110-151">**Federated**   A **Federated** partner type represents a high level of trust between the Lync Server deployment and the XMPP partner.</span></span><span data-ttu-id="0b110-152">若要与同一企业内的 XMPP 服务器联盟或已建立的业务关系，建议使用此类合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="0b110-152">  This partner type is recommended for federating with XMPP servers within the same enterprise or where there is an established business relationship.</span></span><span data-ttu-id="0b110-153">联盟合作伙伴中的 XMPP 联系人可以：</span><span class="sxs-lookup"><span data-stu-id="0b110-153">  XMPP contacts in Federated partners can:</span></span>
        
        1.  <span data-ttu-id="0b110-154">添加 Lync 联系人并在不通过 Lync 用户快速授权的情况下查看其状态。</span><span class="sxs-lookup"><span data-stu-id="0b110-154">Add Lync contacts and view their presence without express authorization from the Lync user.</span></span>
        
        2.  <span data-ttu-id="0b110-155">向 Lync 联系人发送即时消息，无论 Lync 用户是否已将其添加到其联系人列表中。</span><span class="sxs-lookup"><span data-stu-id="0b110-155">Send instant messages to Lync contacts whether or not the Lync user has added them into their contact list.</span></span>
        
        3.  <span data-ttu-id="0b110-156">查看 Lync 用户的状态笔记。</span><span class="sxs-lookup"><span data-stu-id="0b110-156">See a Lync user’s status notes.</span></span>
    
      - <span data-ttu-id="0b110-157">**公共验证**   的**公共验证合作伙伴是**受信任的公共 XMPP 提供商，可用于验证其用户的身份。</span><span class="sxs-lookup"><span data-stu-id="0b110-157">**Public verified**   A **Public verified** partner is a public XMPP provider that is trusted to verify the identity of its users.</span></span><span data-ttu-id="0b110-158">XMPP 公共验证网络中的联系人可以添加 Lync 联系人并查看其状态，并向他们发送即时消息，而无需从 Lync 用户进行快速授权。</span><span class="sxs-lookup"><span data-stu-id="0b110-158">  XMPP contacts in Public Verified networks can add Lync contacts and view their presence and send instant messages to them without express authorization from the Lync users.</span></span><span data-ttu-id="0b110-159">公共验证网络中的 XMPP 联系人永远不会看到 Lync 用户的状态笔记。</span><span class="sxs-lookup"><span data-stu-id="0b110-159">  XMPP contacts in public verified networks never see a Lync users’ status notes.</span></span><span data-ttu-id="0b110-160">不建议使用此设置。</span><span class="sxs-lookup"><span data-stu-id="0b110-160">  This setting is not recommended.</span></span>
    
      - <span data-ttu-id="0b110-161">**公共**   未验证**公共未经**验证的合作伙伴是不受信任的公共 XMPP 提供程序，无法验证其用户的身份。</span><span class="sxs-lookup"><span data-stu-id="0b110-161">**Public unverified**   A **Public unverified** partner is a public XMPP provider that is not trusted to verify the identity of its users.</span></span><span data-ttu-id="0b110-162">XMPP 公共未经验证的网络上的用户无法与 Lync 用户通信，除非 Lync 用户已通过将其添加到联系人列表中进行了明确授权。</span><span class="sxs-lookup"><span data-stu-id="0b110-162">  XMPP users on Public Unverified networks cannot communicate with Lync users unless the Lync user has expressly authorized them by adding them to the contact list.</span></span><span data-ttu-id="0b110-163">公共未经验证的网络上的 XMPP 用户永远不会看到 Lync 用户的状态笔记。</span><span class="sxs-lookup"><span data-stu-id="0b110-163">  XMPP users on public unverified networks never see Lync users’ status notes.</span></span><span data-ttu-id="0b110-164">对于具有公共 XMPP 提供商（如 Google 通话）的任何联盟，建议使用此设置。</span><span class="sxs-lookup"><span data-stu-id="0b110-164">  This setting is recommended for any federation with public XMPP providers such as Google Talk.</span></span>

9.  <span data-ttu-id="0b110-165">**连接类型：** 定义各种规则和回拨设置。</span><span class="sxs-lookup"><span data-stu-id="0b110-165">**Connection Type:** Defines the various rules and dialback settings.</span></span>
    
      - <span data-ttu-id="0b110-166">**Tls 协商**   定义 tls 协商规则。</span><span class="sxs-lookup"><span data-stu-id="0b110-166">**TLS Negotiation**   Defines the TLS negotiation rules.</span></span> <span data-ttu-id="0b110-167">XMPP 服务可能需要 TLS，可以使 TLS 可选，也可以定义不支持 TLS。</span><span class="sxs-lookup"><span data-stu-id="0b110-167">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="0b110-168">选择 "可选" 将对 XMPP 服务的要求留给必要的协商决策。</span><span class="sxs-lookup"><span data-stu-id="0b110-168">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="0b110-169">若要查看有关 SASL、TLS 和回拨协商的所有可能设置和详细信息-包括无效的已知错误配置，请参阅[Lync Server 2013 中 XMPP 联盟合作伙伴的协商设置](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)。</span><span class="sxs-lookup"><span data-stu-id="0b110-169">To view all possible settings and details for SASL, TLS and Dialback negotiation –including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span></span>
        
          - <span></span>  
            <span data-ttu-id="0b110-170">**必需**   的 XMPP 服务需要 TLS 协商。</span><span class="sxs-lookup"><span data-stu-id="0b110-170">**Required**   The XMPP service requires TLS negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="0b110-171">**可选**   ： XMPP 服务指示 TLS 必须进行协商。</span><span class="sxs-lookup"><span data-stu-id="0b110-171">**Optional**   The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="0b110-172">**不支持**   XMPP 服务不支持 TLS。</span><span class="sxs-lookup"><span data-stu-id="0b110-172">**Not Supported**   The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="0b110-173">**Sasl 协商**   定义 sasl 协商规则。</span><span class="sxs-lookup"><span data-stu-id="0b110-173">**SASL negotiation**   Defines the SASL negotiation rules.</span></span> <span data-ttu-id="0b110-174">XMPP 服务可能需要 SASL，可以使 SASL 成为可选的，也可以定义不支持 SASL。</span><span class="sxs-lookup"><span data-stu-id="0b110-174">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="0b110-175">选择 "可选" 将要求提供给合作伙伴 XMPP 服务，以便进行强制性的协商决策。</span><span class="sxs-lookup"><span data-stu-id="0b110-175">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
          - <span></span>  
            <span data-ttu-id="0b110-176">**必需**   的 XMPP 服务需要 SASL 协商。</span><span class="sxs-lookup"><span data-stu-id="0b110-176">**Required**   The XMPP service requires SASL negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="0b110-177">**可选**   ： XMPP 服务指示 SASL 必须进行协商。</span><span class="sxs-lookup"><span data-stu-id="0b110-177">**Optional**   The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="0b110-178">**不支持**   XMPP 服务不支持 SASL。</span><span class="sxs-lookup"><span data-stu-id="0b110-178">**Not Supported**   The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="0b110-179">**支持服务器回拨协商**支持服务器回拨协商进程使用域名系统（DNS）和权威服务器验证请求是否来自有效的 XMPP 合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="0b110-179">**Support server dialback negotiation** The support server dialback negotiation process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="0b110-180">为此，始发服务器使用生成的回拨密钥创建一个特定类型的消息，并在 DNS 中查找接收服务器。</span><span class="sxs-lookup"><span data-stu-id="0b110-180">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="0b110-181">始发服务器将 XML 流中的密钥发送到生成的 DNS 查找，这是接收服务器。</span><span class="sxs-lookup"><span data-stu-id="0b110-181">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="0b110-182">在通过 XML 流接收密钥时，接收服务器不会响应始发服务器，而是将密钥发送到已知的权威服务器。</span><span class="sxs-lookup"><span data-stu-id="0b110-182">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="0b110-183">授权服务器验证密钥是否有效或无效。</span><span class="sxs-lookup"><span data-stu-id="0b110-183">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="0b110-184">如果无效，接收方服务器不会响应始发服务器。</span><span class="sxs-lookup"><span data-stu-id="0b110-184">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="0b110-185">如果密钥有效，接收方服务器将通知发起服务器标识和密钥有效且可以开始对话。</span><span class="sxs-lookup"><span data-stu-id="0b110-185">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="0b110-186">**回拨协商**有两个有效状态：</span><span class="sxs-lookup"><span data-stu-id="0b110-186">There are two valid states for **Dialback negotiation**:</span></span>
        
          - <span></span>  
            <span data-ttu-id="0b110-187">\*\*\*\*   如果应从发起服务器接收请求，则将 XMPP 服务器配置为使用回拨协商。</span><span class="sxs-lookup"><span data-stu-id="0b110-187">**True**   The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server.</span></span>
        
          - <span></span>  
            <span data-ttu-id="0b110-188">**False**   未将 XMPP 服务器配置为使用回拨协商，如果应收到来自发起服务器的请求，则会忽略它。</span><span class="sxs-lookup"><span data-stu-id="0b110-188">**False**   The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored.</span></span>

10. <span data-ttu-id="0b110-189">单击 "**提交**" 将更改保存到 "网站" 或 "用户策略"。</span><span class="sxs-lookup"><span data-stu-id="0b110-189">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="0b110-190">更新 Lync Server 2013 XMPP 网关的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="0b110-190">Update DNS Records for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="0b110-191">若要为 XMPP 联盟配置 DNS，请将以下 SRV 记录添加到外部 DNS：\_XMPP-server。\_tcp。\<域名 SRV 记录将解析为 Edge 服务器的访问边缘 FQDN，其端口值为\> 5269。</span><span class="sxs-lookup"><span data-stu-id="0b110-191">To configure DNS for XMPP federation, you add the following SRV record to your external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the Access Edge FQDN of the Edge server, with a port value of 5269.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

