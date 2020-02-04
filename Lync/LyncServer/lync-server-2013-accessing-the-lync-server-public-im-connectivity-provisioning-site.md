---
title: 访问 Lync Server 公共 IM 连接设置站点
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing the Lync Server public IM connectivity provisioning site
ms:assetid: 77a08234-6bcf-4f59-b43b-ee5fc1926585
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440174(v=OCS.15)
ms:contentKeyID: 57793364
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbcb2e46380e7ed4bbd8499e83f638cb314844e9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a><span data-ttu-id="010d8-102">从 Lync Server 2013 访问 Lync Server 公共 IM 连接设置站点</span><span class="sxs-lookup"><span data-stu-id="010d8-102">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="010d8-103">_**主题上次修改时间：** 2019-03-22_</span><span class="sxs-lookup"><span data-stu-id="010d8-103">_**Topic Last Modified:** 2019-03-22_</span></span>

<span data-ttu-id="010d8-104">与以前的 PIC 预配方法相比，Lync-Skype 连接的预配过程已发生更改。</span><span class="sxs-lookup"><span data-stu-id="010d8-104">The provisioning process for Lync-Skype connectivity has changed, as compared to previous PIC provisioning methods.</span></span> <span data-ttu-id="010d8-105">完成此预配过程最多需要30天。</span><span class="sxs-lookup"><span data-stu-id="010d8-105">This provisioning process can take up to thirty days to complete.</span></span> <span data-ttu-id="010d8-106">建议您在完成文档中的其余步骤之前先开始此过程。</span><span class="sxs-lookup"><span data-stu-id="010d8-106">We recommend that you start this process first, prior to completing the remaining steps in this document.</span></span> <span data-ttu-id="010d8-107">为你的帐户完成 Lync-Skype 预配过程后，将激活该帐户，并为你的符合条件的用户启用公用 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="010d8-107">After the Lync-Skype provisioning process is completed for your account, the account is activated and your eligible users are enabled for public IM connectivity.</span></span>

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a><span data-ttu-id="010d8-108">若要设置 Lync-Skype 连接，您需要以下信息：</span><span class="sxs-lookup"><span data-stu-id="010d8-108">To provision Lync-Skype connectivity, you need the following information:</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><span data-ttu-id="010d8-109">Microsoft 协议编号</span><span class="sxs-lookup"><span data-stu-id="010d8-109">Microsoft Agreement Number</span></span></p></li>
<li><p><span data-ttu-id="010d8-110">访问边缘服务完全限定的域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="010d8-110">Access Edge service fully qualified domain name (FQDN)</span></span></p></li>
<li><p><span data-ttu-id="010d8-111">会话初始协议 (SIP) 域</span><span class="sxs-lookup"><span data-stu-id="010d8-111">Session Initiation Protocol (SIP) domain(s)</span></span></p></li>
<li><p><span data-ttu-id="010d8-112">任何其他访问边缘服务 FQDN</span><span class="sxs-lookup"><span data-stu-id="010d8-112">Any additional Access Edge service FQDNs</span></span></p></li>
<li><p><span data-ttu-id="010d8-113">联系信息</span><span class="sxs-lookup"><span data-stu-id="010d8-113">Contact information</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>

<span data-ttu-id="010d8-114">从2019年4月起，我们将停止通过 pic.lync.com 网站为 Skype Federation 预配的客户的联系人信息的收集和保留。</span><span class="sxs-lookup"><span data-stu-id="010d8-114">Beginning in April 2019, we will stop the collection and retention of contact information for customers who are provisioned for Skype Federation via the pic.lync.com website.</span></span> <span data-ttu-id="010d8-115">进行此更改是为了确保 pic.lync.com 预配系统遵守 Microsoft 隐私策略。</span><span class="sxs-lookup"><span data-stu-id="010d8-115">This change is being made to ensure that the pic.lync.com provisioning system adheres to Microsoft privacy policies.</span></span> 

<span data-ttu-id="010d8-116">此更改生效后，我们将不再能够在挂起的预配更改上提供电子邮件更新。</span><span class="sxs-lookup"><span data-stu-id="010d8-116">Once this change goes live, we will no longer be able to provide email updates on pending provisioning changes.</span></span> <span data-ttu-id="010d8-117">PIC 预配更改通常在输入后的24-48 小时内完成。</span><span class="sxs-lookup"><span data-stu-id="010d8-117">PIC provisioning changes typically complete within 24-48 hours after being entered.</span></span> <span data-ttu-id="010d8-118">如果你在提交预配请求后48小时仍遇到 Skype 联合身份验证问题，请与 Microsoft 技术支持人员联系以进一步调查。</span><span class="sxs-lookup"><span data-stu-id="010d8-118">If you are still experiencing Skype Federation issues 48 hours after submitting a provisioning request, please engage Microsoft Technical Support to investigate further.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="010d8-119">作为此更改的一部分，所有以前输入的联系人信息将在2019年4月结束后从系统中清除。</span><span class="sxs-lookup"><span data-stu-id="010d8-119">As part of this change, all previously entered contact information will be purged from our system by the end of April, 2019.</span></span>

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a><span data-ttu-id="010d8-120">要启动 Lync-Skype 连接的预配过程，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="010d8-120">To initiate the provisioning process for Lync-Skype connectivity:</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><span data-ttu-id="010d8-121">使用您的 Microsoft Windows Live <strong>https://pic.lync.com</strong>ID 登录到网站。</span><span class="sxs-lookup"><span data-stu-id="010d8-121">Sign in to the website, <strong>https://pic.lync.com</strong>, using your Microsoft Windows Live ID.</span></span></p></li>
<li><p><span data-ttu-id="010d8-122">选择 Microsoft 许可协议类型。</span><span class="sxs-lookup"><span data-stu-id="010d8-122">Select the Microsoft licensing agreement type.</span></span></p></li>
<li><p><span data-ttu-id="010d8-123">选中复选框，验证您是否已阅读并接受 "Lync Server 的产品使用权限"。</span><span class="sxs-lookup"><span data-stu-id="010d8-123">Select the check box, verifying that you have read and accept the Product Use Rights for Lync Server.</span></span></p></li>
<li><p><span data-ttu-id="010d8-124">在 "<strong>启动预配请求</strong>" 页面上，单击相应链接以启动设置请求：</span><span class="sxs-lookup"><span data-stu-id="010d8-124">On the <strong>Initiate a Provisioning Request</strong> page, click the appropriate link to initiate a provisioning request:</span></span></p></li>
<li><p><span data-ttu-id="010d8-125">在 "<strong>指定设置信息</strong>" 页面上，输入 "<strong>访问边缘服务" FQDN</strong>。</span><span class="sxs-lookup"><span data-stu-id="010d8-125">On the <strong>Specify Provisioning Information</strong> page, enter the <strong>Access Edge service FQDN</strong>.</span></span> <span data-ttu-id="010d8-126">例如， <strong>sip.contoso.com</strong>。</span><span class="sxs-lookup"><span data-stu-id="010d8-126">For example, <strong>sip.contoso.com</strong>.</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="010d8-127">2017年7月1日之后，Microsoft 还将进一步要求客户为公共 IM 连接部署的联合身份验证 DNS SRV 记录才能继续工作。</span><span class="sxs-lookup"><span data-stu-id="010d8-127">After July 1st, 2017 Microsoft will additionally require customers have the Federation DNS SRV record deployed for Public IM connectivity to continue to work.</span></span>

</li>
<li><p><span data-ttu-id="010d8-128">至少输入一个或多个 SIP 域名，然后单击 "<strong>添加</strong>"。</span><span class="sxs-lookup"><span data-stu-id="010d8-128">Enter at least one or more SIP domain names, and then click <strong>Add</strong>.</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="010d8-129">必须至少有一个访问边缘服务器和一个 SIP 域才能完成预配过程。</span><span class="sxs-lookup"><span data-stu-id="010d8-129">At least one Access Edge server and one SIP domain are required to complete the provisioning process.</span></span> <span data-ttu-id="010d8-130">SIP 域和访问边缘服务器必须处于活动状态、正在运行，并且在网络上可访问。</span><span class="sxs-lookup"><span data-stu-id="010d8-130">The SIP domain and the Access Edge server must be active, functioning, and reachable on the network.</span></span>

</li>
<li><p><span data-ttu-id="010d8-131">在<strong>公用 IM 服务提供商</strong>列表中，选择 " <strong>Skype"，</strong>然后单击 "<strong>下一步</strong>" 添加联系人信息，并提交预配请求。</span><span class="sxs-lookup"><span data-stu-id="010d8-131">In the list of <strong>Public IM Service providers</strong>, select <strong>Skype,</strong> and click <strong>Next</strong> to add contact information, and submit the provisioning request.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


<span data-ttu-id="010d8-132">提交预配请求后，最多可能需要30天才能激活该帐户，并为用户启用公用 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="010d8-132">After the provisioning request has been submitted, it can take up to 30 days for the account to activate and for users to be enabled for public IM connectivity.</span></span>

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a><span data-ttu-id="010d8-133">启用联盟和公共 IM 连接 (PIC)</span><span class="sxs-lookup"><span data-stu-id="010d8-133">Enabling Federation and Public IM Connectivity (PIC)</span></span>

<span data-ttu-id="010d8-134">提交预配请求后，你可以专注于 Lync Server 环境和配置 Lync-Skype 连接所需的管理任务。</span><span class="sxs-lookup"><span data-stu-id="010d8-134">After you have submitted the provisioning request, you can focus on the Lync Server environment and administrative tasks required to configure Lync-Skype connectivity.</span></span> <span data-ttu-id="010d8-135">在此部分中，我们假设 Lync Server 管理员已部署 Lync Server 和配置的外部访问权限。</span><span class="sxs-lookup"><span data-stu-id="010d8-135">In this section, we assume that the Lync Server administrator has deployed Lync Server and configured external access.</span></span> <span data-ttu-id="010d8-136">有关配置 Lync Server 的外部访问的其他信息，请参阅中的 "规划外部用户访问[https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) " 和 "部署外部用户访问" [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378)。</span><span class="sxs-lookup"><span data-stu-id="010d8-136">For additional information on configuring external access for Lync Server, see "Planning for External User Access" at [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) and "Deploying External User Access" at [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378).</span></span>

<span data-ttu-id="010d8-137">要准备 lync Server 环境以实现 Lync-Skype 连接，Lync Server 管理员必须完成以下三个任务：</span><span class="sxs-lookup"><span data-stu-id="010d8-137">To prepare the Lync Server environment for Lync-Skype connectivity, the Lync Server administrator must complete the following three tasks:</span></span>

<div>

## <a name="1-configure-federation-and-pic"></a><span data-ttu-id="010d8-138">1 \。</span><span class="sxs-lookup"><span data-stu-id="010d8-138">1\.</span></span> <span data-ttu-id="010d8-139">配置联盟和 PIC</span><span class="sxs-lookup"><span data-stu-id="010d8-139">Configure Federation and PIC</span></span>

<span data-ttu-id="010d8-140">必须使用联盟才能使 Skype 用户能够与组织中的 Lync 用户通信。</span><span class="sxs-lookup"><span data-stu-id="010d8-140">Federation is required to enable Skype users to communicate with Lync users in your organization.</span></span> <span data-ttu-id="010d8-141">公共即时消息连接（PIC）是一种联盟类，必须将其配置为使 Lync 用户能够与 Skype 用户通信。</span><span class="sxs-lookup"><span data-stu-id="010d8-141">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Lync users to communicate with Skype users.</span></span> <span data-ttu-id="010d8-142">联盟和 PIC 是使用 Lync Server 控制面板配置的，如下所示。</span><span class="sxs-lookup"><span data-stu-id="010d8-142">Federation and PIC are configured by using the Lync Server Control Panel, shown below.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="010d8-143">Live Communication Server 2005 SP1 或 Office Communications Server 2007 不再支持 PIC 联盟。</span><span class="sxs-lookup"><span data-stu-id="010d8-143">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007.</span></span> <span data-ttu-id="010d8-144">PIC 联盟支持的平台包括 Lync Server 2013、Lync Server 2010 和 Office 通信服务器 2007 R2。</span><span class="sxs-lookup"><span data-stu-id="010d8-144">The supported platforms for PIC federation include Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span>



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="010d8-145">2 \。</span><span class="sxs-lookup"><span data-stu-id="010d8-145">2\.</span></span> <span data-ttu-id="010d8-146">配置至少一个策略以支持联盟的用户访问</span><span class="sxs-lookup"><span data-stu-id="010d8-146">Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="010d8-147">使用 Lync Server 控制面板，管理员必须配置一个或多个外部用户访问策略，以控制 Skype 用户是否可以与内部 Lync Server 用户进行协作。</span><span class="sxs-lookup"><span data-stu-id="010d8-147">Using the Lync Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Lync Server users.</span></span>

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a><span data-ttu-id="010d8-148">3。</span><span class="sxs-lookup"><span data-stu-id="010d8-148">3\.</span></span> <span data-ttu-id="010d8-149">配置 Lync 的 Skype PIC 提供商设置</span><span class="sxs-lookup"><span data-stu-id="010d8-149">Configure the Skype PIC provider setting for Lync</span></span>

<span data-ttu-id="010d8-150">使用 Lync Server 命令行管理程序，管理员必须将 Lync 客户端策略配置为将 Skype 显示为其他 PIC 提供商。</span><span class="sxs-lookup"><span data-stu-id="010d8-150">Using the Lync Server Management Shell, an administrator must configure the Lync client policy to display Skype as an additional PIC provider.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="010d8-151">只有至少再配置一个策略（步骤 2，此过程前面所述）以支持公共 IM 连接，公共即时消息连接 (PIC) 服务提供商的用户才能参与组织中的 IM 或会议。</span><span class="sxs-lookup"><span data-stu-id="010d8-151">Users of the Public Instant Messaging Connectivity (PIC) service providers can’t participate in IM or conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span><BR><span data-ttu-id="010d8-152">若要配置联盟和 PIC，请参阅 "启用或禁用联盟和公用 IM 连接<A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>"。</span><span class="sxs-lookup"><span data-stu-id="010d8-152">To configure federation and PIC, see "Enable or Disable Federation and Public IM Connectivity" at <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>.</span></span><BR><span data-ttu-id="010d8-153">若要配置至少一个策略以支持联合用户访问，请参阅 "配置用于控制公共用户访问的策略<A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>"。</span><span class="sxs-lookup"><span data-stu-id="010d8-153">To configure at least one policy to support federated user access, see "Configure Policies to Control Public User Access" at <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>.</span></span>



</div>

1.  <span data-ttu-id="010d8-154">从 Lync Server 前端服务器，打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="010d8-154">From a Lync Server Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="010d8-155">运行以下两个命令：</span><span class="sxs-lookup"><span data-stu-id="010d8-155">Run the following two commands:</span></span>
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="010d8-156">如果你的环境中尚未安装 PIC 提供程序，而是创建新的 PIC 提供商，则无需运行<STRONG>CsPublicProvider</STRONG> cmdlet。</span><span class="sxs-lookup"><span data-stu-id="010d8-156">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the <STRONG>Remove-CsPublicProvider</STRONG> cmdlet.</span></span>

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="010d8-157">在 Lync Server 2013 CU5 &amp;中添加了 OFFICE 2013 SP1 中的 lync 桌面客户端，NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList 改进了 Lync 用户添加了 "装饰" 非 Microsoft 域所需的 Skype 联系人以标识和将其路由到 Skype 的情况（格式为： user （contoso） @msn .com）。</span><span class="sxs-lookup"><span data-stu-id="010d8-157">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to “decorate” non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="010d8-158">这些新设置可自动格式化用户通过 NameDecorationRoutingDomain（应设为 msn.com）在“添加 Skype 联系人”对话框中输入的地址（如果其不包含 NameDecorationExcludedDomainList 中的域）（我们当前支持 msn.com、live.com、Hotmail.com、outlook.com）。</span><span class="sxs-lookup"><span data-stu-id="010d8-158">These new settings will allow automatic formatting of the address user’s enter in the “Add Skype contact” dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span>

        
        </div>

3.  <span data-ttu-id="010d8-159">通过 Lync 客户端，您现在可以选择 Skype 作为 PIC 提供商，并通过指定其 Microsoft 帐户来添加 Skype 客户端。</span><span class="sxs-lookup"><span data-stu-id="010d8-159">From a Lync client, you can now select Skype as the PIC provider, and add a Skype client by specifying their Microsoft account.</span></span> <span data-ttu-id="010d8-160">此外，已使用其 Microsoft 帐户合并和登录的 Skype 用户可以向 Lync 用户发送联系人请求。</span><span class="sxs-lookup"><span data-stu-id="010d8-160">In addition, a Skype user who has merged and logged in with their Microsoft account can send contact request to Lync users.</span></span> <span data-ttu-id="010d8-161">有关 Microsoft 帐户的详细信息，请参阅[什么是 microsoft 帐户？](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account)。</span><span class="sxs-lookup"><span data-stu-id="010d8-161">For more information about Microsoft accounts, see [What is a Microsoft account?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span></span> <span data-ttu-id="010d8-162">有关将客户端添加到 Lync 的其他信息，请参阅[在 Lync Server 2013 中使用 lync-Skype 连接作为最终用户](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)。</span><span class="sxs-lookup"><span data-stu-id="010d8-162">For additional information on adding clients to Lync, see [Using Lync-Skype connectivity in Lync Server 2013 as an end user](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span></span>

4.  <span data-ttu-id="010d8-163">有关修改托管提供商的详细信息，请参阅 "创建或编辑托管的 SIP 联合[https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065)提供商"。</span><span class="sxs-lookup"><span data-stu-id="010d8-163">For detailed information on modifying hosted providers, see "Create or Edit Hosted SIP Federated Providers" at [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065).</span></span>

<span data-ttu-id="010d8-164">这将完成必须在服务器上执行的管理任务。</span><span class="sxs-lookup"><span data-stu-id="010d8-164">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="010d8-165">您现在已为 Lync-Skype 连接设置。</span><span class="sxs-lookup"><span data-stu-id="010d8-165">You are now set up for Lync-Skype connectivity.</span></span>

</div>

</div>

<div>

## <a name="additional-resources"></a><span data-ttu-id="010d8-166">其他资源</span><span class="sxs-lookup"><span data-stu-id="010d8-166">Additional Resources</span></span>

[<span data-ttu-id="010d8-167">在 Lync Server 2013 中使用 Lync-Skype 连接作为最终用户</span><span class="sxs-lookup"><span data-stu-id="010d8-167">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[<span data-ttu-id="010d8-168">Lync Server 2013 中的 Lync-Skype 连接设置指南</span><span class="sxs-lookup"><span data-stu-id="010d8-168">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

