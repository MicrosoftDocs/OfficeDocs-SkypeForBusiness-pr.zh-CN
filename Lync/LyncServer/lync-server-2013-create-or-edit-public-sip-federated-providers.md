---
title: Lync Server 2013：创建或编辑公共 SIP 联合提供程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit public SIP federated providers
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398349(v=OCS.15)
ms:contentKeyID: 48184167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58b0ffdc009d48ef82d1bdf3ba8662cd4072ea1c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514849"
---
# <a name="create-or-edit-public-sip-federated-providers-in-lync-server-2013"></a><span data-ttu-id="764e5-102">在 Lync Server 2013 中创建或编辑公共 SIP 联合提供程序</span><span class="sxs-lookup"><span data-stu-id="764e5-102">Create or edit public SIP federated providers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="764e5-103">_**上次修改的主题：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="764e5-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="764e5-104">公共即时消息 (IM) 连接使组织中的用户能够使用 IM 与公共 IM 服务提供商（包括 Windows Live Messenger、Yahoo 和 AOL）提供的 IM 服务的用户进行通信 \! 。</span><span class="sxs-lookup"><span data-stu-id="764e5-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live Messenger, Yahoo\!, and AOL.</span></span>

<span data-ttu-id="764e5-105">Lync Server 2013 具有适用于北美在线、Windows Live 和 Yahoo 的公共提供程序配置\!</span><span class="sxs-lookup"><span data-stu-id="764e5-105">Lync Server 2013 has public provider configurations for America Online, Windows Live and Yahoo\!</span></span> <span data-ttu-id="764e5-106">即时消息的公共提供程序配置。</span><span class="sxs-lookup"><span data-stu-id="764e5-106">instant messaging.</span></span> <span data-ttu-id="764e5-107">每个公共提供程序均使用提供程序的边缘服务器完全限定域名和默认验证级别“仅允许用户与其联系人列表中使用此提供程序的人员进行通信”\*\*\*\* 进行配置。</span><span class="sxs-lookup"><span data-stu-id="764e5-107">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="764e5-108">作为默认设置，将不启用任何公共提供程序。</span><span class="sxs-lookup"><span data-stu-id="764e5-108">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="764e5-109">您应先完成许可协议和设置工作，然后再启用公共提供程序。</span><span class="sxs-lookup"><span data-stu-id="764e5-109">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="764e5-110">您可以先启用提供程序，然后再完成许可和设置工作。</span><span class="sxs-lookup"><span data-stu-id="764e5-110">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="764e5-111">在完成首要工作之前，用户将无法与这些提供程序的联系人进行通信。</span><span class="sxs-lookup"><span data-stu-id="764e5-111">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="764e5-112">有关授权和预配公共提供商的详细信息，请参阅 [在 Lync Server 2013 中配置控制公用用户访问的策略](lync-server-2013-configure-policies-to-control-public-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="764e5-112">For details on licensing and provisioning of public providers, see [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="764e5-113">使用以下过程可创建或编辑公共提供程序：</span><span class="sxs-lookup"><span data-stu-id="764e5-113">Use the following procedure to create or edit Public providers:</span></span>

<div>

## <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="764e5-114">创建或编辑公共提供程序</span><span class="sxs-lookup"><span data-stu-id="764e5-114">To create or edit public providers</span></span>

1.  <span data-ttu-id="764e5-115">从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="764e5-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="764e5-116">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="764e5-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="764e5-117">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="764e5-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="764e5-118">在左侧导航栏中，单击“联盟和外部访问”\*\*\*\*，然后单击“SIP 联盟提供程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="764e5-118">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="764e5-119">如果您需要创建新的公共提供程序，请单击“新建”\*\*\*\*，然后单击“公共提供程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="764e5-119">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="764e5-120">如果您需要编辑公共提供程序列表中的条目，请选择一个公共提供程序，单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="764e5-120">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="764e5-121">在“编辑 SIP 联盟提供程序”\*\*\*\* 页上，可以键入或编辑以下设置：</span><span class="sxs-lookup"><span data-stu-id="764e5-121">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="764e5-122">**启用与此提供程序**     的通信选择此设置将启用与此提供商的用户的即时消息。</span><span class="sxs-lookup"><span data-stu-id="764e5-122">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="764e5-123">**提供程序名称：**    一个必需属性，请键入提供程序的名称，因为它将反映在 SIP 联合提供程序的列表中。</span><span class="sxs-lookup"><span data-stu-id="764e5-123">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="764e5-124">**访问边缘服务 (FQDN) ：**    一个必需属性，请键入您要配置的提供程序的访问边缘服务的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="764e5-124">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="764e5-125">此信息作为默认项目提供，仅当公用提供程序对公共提供商的访问边缘服务的 FQDN 进行更改时，才应更改此信息。</span><span class="sxs-lookup"><span data-stu-id="764e5-125">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="764e5-126">**默认验证级别：**    默认设置是，**允许用户与其 "联系人" 列表中使用此提供商的人员进行通信**，以将通信限制为您已接受且位于您的联系人列表中的联系人。</span><span class="sxs-lookup"><span data-stu-id="764e5-126">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="764e5-p105">选择“允许用户与使用此提供程序的每个人通信”\*\*\*\* 将去除您必须接收和接受联系人邀请的限制。此设置不会对可从公共提供程序网络与您联系的人员进行限制。</span><span class="sxs-lookup"><span data-stu-id="764e5-p105">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="764e5-129">配置完这些设置后，请单击“提交”\*\*\*\* 以进行保存，或单击“取消”\*\*\*\* 以放弃更改。</span><span class="sxs-lookup"><span data-stu-id="764e5-129">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="764e5-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="764e5-130">See Also</span></span>


[<span data-ttu-id="764e5-131">配置策略以控制 Lync Server 2013 中的公共用户访问</span><span class="sxs-lookup"><span data-stu-id="764e5-131">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="764e5-132">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="764e5-132">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

