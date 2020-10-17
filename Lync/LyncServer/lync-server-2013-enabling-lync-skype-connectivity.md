---
title: Lync Server 2013：启用 Lync-Skype 连接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Lync-Skype connectivity
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440170(v=OCS.15)
ms:contentKeyID: 57793361
ms.date: 12/16/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43e26e54d0704ed009af1ef528e60979b759eb69
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528579"
---
# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="7baea-102">在 Lync Server 2013 中启用 Lync-Skype 连接</span><span class="sxs-lookup"><span data-stu-id="7baea-102">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7baea-103">_**上次修改的主题：** 2014-12-16_</span><span class="sxs-lookup"><span data-stu-id="7baea-103">_**Topic Last Modified:** 2014-12-16_</span></span>

<span data-ttu-id="7baea-104">提交设置请求后，您可以将精力集中在配置 Lync-Skype 连接所需的 Lync Server 环境和管理任务上。</span><span class="sxs-lookup"><span data-stu-id="7baea-104">After you have submitted the provisioning request, you can focus on the Lync Server environment and administrative tasks required to configure Lync-Skype connectivity.</span></span> <span data-ttu-id="7baea-105">在本节中，我们假定 Lync Server 管理员已部署 Lync Server 并配置了外部访问权限。</span><span class="sxs-lookup"><span data-stu-id="7baea-105">In this section, we assume that the Lync Server administrator has deployed Lync Server and configured external access.</span></span> <span data-ttu-id="7baea-106">有关为 Lync Server 配置外部访问的其他信息，请参阅在 lync server [2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md) 和 [在 lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="7baea-106">For additional information on configuring external access for Lync Server, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

<span data-ttu-id="7baea-107">若要准备 Lync Server 环境以进行 Lync-Skype 连接，Lync Server 管理员必须完成以下三个任务：</span><span class="sxs-lookup"><span data-stu-id="7baea-107">To prepare the Lync Server environment for Lync-Skype connectivity, the Lync Server administrator must complete the following three tasks:</span></span>

<div>

## <a name="1-configure-federation-and-pic"></a><span data-ttu-id="7baea-108">1\.</span><span class="sxs-lookup"><span data-stu-id="7baea-108">1\.</span></span> <span data-ttu-id="7baea-109">配置联盟和 PIC</span><span class="sxs-lookup"><span data-stu-id="7baea-109">Configure Federation and PIC</span></span>

<span data-ttu-id="7baea-110">若要使 Skype 用户能够与组织中的 Lync 用户进行通信，需要联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="7baea-110">Federation is required to enable Skype users to communicate with Lync users in your organization.</span></span> <span data-ttu-id="7baea-111">公共即时消息连接 (PIC) 是一种联盟类别，必须将其配置为使 Lync 用户能够与 Skype 用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="7baea-111">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Lync users to communicate with Skype users.</span></span> <span data-ttu-id="7baea-112">联盟和 PIC 是使用 Lync Server 控制面板配置的，如下所示。</span><span class="sxs-lookup"><span data-stu-id="7baea-112">Federation and PIC are configured by using the Lync Server Control Panel, shown below.</span></span>

<span data-ttu-id="7baea-113">![显示 PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "显示 PIC")</span><span class="sxs-lookup"><span data-stu-id="7baea-113">![Showing PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Showing PIC")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7baea-114">Live Communication Server 2005 SP1 或 Office 通信服务器2007不再支持 PIC 联盟。</span><span class="sxs-lookup"><span data-stu-id="7baea-114">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007.</span></span> <span data-ttu-id="7baea-115">PIC 联合的受支持平台包括 Lync Server 2013、Lync Server 2010 和 Office 通信服务器 2007 R2。</span><span class="sxs-lookup"><span data-stu-id="7baea-115">The supported platforms for PIC federation include Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span>



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="7baea-116">2\.</span><span class="sxs-lookup"><span data-stu-id="7baea-116">2\.</span></span> <span data-ttu-id="7baea-117">至少配置一个用于支持联合用户访问的策略</span><span class="sxs-lookup"><span data-stu-id="7baea-117">Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="7baea-118">使用 Lync Server 控制面板，管理员必须配置一个或多个外部用户访问策略，以控制 Skype 用户是否可以与内部 Lync Server 用户进行协作。</span><span class="sxs-lookup"><span data-stu-id="7baea-118">Using the Lync Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Lync Server users.</span></span>

<span data-ttu-id="7baea-119">![策略](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "策略")</span><span class="sxs-lookup"><span data-stu-id="7baea-119">![Policies](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Policies")</span></span>

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a><span data-ttu-id="7baea-120">3\.</span><span class="sxs-lookup"><span data-stu-id="7baea-120">3\.</span></span> <span data-ttu-id="7baea-121">为 Lync 配置 Skype PIC 提供程序设置</span><span class="sxs-lookup"><span data-stu-id="7baea-121">Configure the Skype PIC provider setting for Lync</span></span>

<span data-ttu-id="7baea-122">通过使用 Lync Server 命令行管理程序，管理员必须将 Lync 客户端策略配置为将 Skype 显示为其他 PIC 提供程序。</span><span class="sxs-lookup"><span data-stu-id="7baea-122">Using the Lync Server Management Shell, an administrator must configure the Lync client policy to display Skype as an additional PIC provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7baea-123"> (PIC) 服务提供程序的公共即时消息连接的用户在您的组织中无法加入 IM 或音频或视频会议，除非您在此过程的前面部分中至少配置了一个策略 (第2步，) 以支持公用 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="7baea-123">Users of the Public Instant Messaging Connectivity (PIC) service providers can’t participate in IM or audio or video conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span>



</div>

1.  <span data-ttu-id="7baea-124">若要配置联盟和 PIC，请参阅中的 "启用或禁用联盟和公共 IM 连接" [https://go.microsoft.com/fwlink/p/?LinkId=306063](https://go.microsoft.com/fwlink/p/?linkid=306063) 。</span><span class="sxs-lookup"><span data-stu-id="7baea-124">To configure federation and PIC, see "Enable or Disable Federation and Public IM Connectivity" at [https://go.microsoft.com/fwlink/p/?LinkId=306063](https://go.microsoft.com/fwlink/p/?linkid=306063).</span></span>

2.  <span data-ttu-id="7baea-125">若要至少配置一个策略来支持联合用户访问，请参阅中的 "配置控制公用用户访问的策略" [https://go.microsoft.com/fwlink/p/?LinkId=306064](https://go.microsoft.com/fwlink/p/?linkid=306064) 。</span><span class="sxs-lookup"><span data-stu-id="7baea-125">To configure at least one policy to support federated user access, see "Configure Policies to Control Public User Access" at [https://go.microsoft.com/fwlink/p/?LinkId=306064](https://go.microsoft.com/fwlink/p/?linkid=306064).</span></span>

<span data-ttu-id="7baea-126">**编辑现有 Messenger 或 Skype PIC 提供商并为其配置 Skype**</span><span class="sxs-lookup"><span data-stu-id="7baea-126">**To edit an existing Messenger or Skype PIC provider and configure it for Skype**</span></span>

1.  <span data-ttu-id="7baea-127">从 Lync Server 前端服务器，打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="7baea-127">From a Lync Server Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="7baea-128">运行以下两个命令：</span><span class="sxs-lookup"><span data-stu-id="7baea-128">Run the following two commands:</span></span>
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7baea-129">如果您的环境中尚未安装 PIC 提供程序，并且要创建新的 PIC 提供程序，则无需运行 <STRONG>CsPublicProvider</STRONG> cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7baea-129">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the <STRONG>Remove-CsPublicProvider</STRONG> cmdlet.</span></span>

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7baea-130">在 Lync Server 2013 CU5 &amp; lync desktop client In Office 2013 SP1 中，NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList 改进了 Lync 用户在其中添加需要 "装饰" 非 Microsoft 域的 skype 联系人以标识并将其路由到 skype (的的情况。) 的格式：用户 (contoso.com) @msn .com。</span><span class="sxs-lookup"><span data-stu-id="7baea-130">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to “decorate” non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="7baea-131">这些新设置将允许使用 NameDecorationRoutingDomain (自动设置地址用户在 "添加 Skype 联系人" 对话框中输入的格式，如果不包含 (NameDecorationExcludedDomainList 中的域，则应将其设置为 msn.com) 如果当前可以支持 msn.com、live.com、Hotmail.com、outlook.com) 。</span><span class="sxs-lookup"><span data-stu-id="7baea-131">These new settings will allow automatic formatting of the address user’s enter in the “Add Skype contact” dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span>

    
    </div>

3.  <span data-ttu-id="7baea-132">在 Lync 客户端中，你现在可以选择 Skype 作为 PIC 提供程序，并通过指定其 Microsoft 帐户来添加 Skype 客户端。</span><span class="sxs-lookup"><span data-stu-id="7baea-132">From a Lync client, you can now select Skype as the PIC provider, and add a Skype client by specifying their Microsoft account.</span></span> <span data-ttu-id="7baea-133">此外，已使用 Microsoft 帐户进行合并和登录的 Skype 用户可以向 Lync 用户发送联系人请求。</span><span class="sxs-lookup"><span data-stu-id="7baea-133">In addition, a Skype user who has merged and logged in with their Microsoft account can send contact request to Lync users.</span></span> <span data-ttu-id="7baea-134">有关 Microsoft 帐户的详细信息，请参阅 [什么是 microsoft 帐户？](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account)。</span><span class="sxs-lookup"><span data-stu-id="7baea-134">For more information about Microsoft accounts, see [What is a Microsoft account?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span></span> <span data-ttu-id="7baea-135">有关向 Lync 添加客户端的其他信息，请参阅 [在 Lync Server 2013 中使用 Lync-Skype 连接作为最终用户](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)。</span><span class="sxs-lookup"><span data-stu-id="7baea-135">For additional information on adding clients to Lync, see [Using Lync-Skype connectivity in Lync Server 2013 as an end user](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span></span>
    
    <span data-ttu-id="7baea-136">![添加 Skype 联系人](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "添加 Skype 联系人")</span><span class="sxs-lookup"><span data-stu-id="7baea-136">![Add Skype Contact](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Add Skype Contact")</span></span>

4.  <span data-ttu-id="7baea-137">有关修改承载的提供程序的详细信息，请参阅处的 "创建或编辑托管的 SIP 联合提供程序" [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065) 。</span><span class="sxs-lookup"><span data-stu-id="7baea-137">For detailed information on modifying hosted providers, see "Create or Edit Hosted SIP Federated Providers" at [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065).</span></span>

<span data-ttu-id="7baea-138">这将完成必须在服务器上执行的管理任务。</span><span class="sxs-lookup"><span data-stu-id="7baea-138">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="7baea-139">您现在已设置 Lync-Skype 连接。</span><span class="sxs-lookup"><span data-stu-id="7baea-139">You are now set up for Lync-Skype connectivity.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

