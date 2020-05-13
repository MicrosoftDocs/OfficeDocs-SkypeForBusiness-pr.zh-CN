---
title: Lync Server 2013：创建或编辑托管的 SIP 联合提供程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit hosted SIP federated providers
ms:assetid: 0dd6dcb6-a88d-46b8-9c96-b35967309bcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552445(v=OCS.15)
ms:contentKeyID: 48679556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b78e9be0f3b885a40fcf313173a1281ac5489936
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a><span data-ttu-id="79e1f-102">创建或编辑托管的 SIP 联合提供商 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79e1f-102">Create or edit hosted SIP federated providers Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79e1f-103">_**上次修改的主题：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="79e1f-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="79e1f-104">托管提供程序即时消息（IM）连接使组织中的用户能够使用 IM 与托管提供商（包括 Microsoft 365 和 Lync Online）提供的 IM 服务的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="79e1f-104">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers, including Microsoft 365 and Lync Online.</span></span>

<span data-ttu-id="79e1f-105">使用提供程序的边缘服务器的完全限定域名以及默认验证级别**仅允许用户与其联系人列表上使用此提供程序的人员进行通信**来配置每个托管提供程序。</span><span class="sxs-lookup"><span data-stu-id="79e1f-105">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="79e1f-106">使用以下过程创建或编辑托管提供程序：</span><span class="sxs-lookup"><span data-stu-id="79e1f-106">Use the following procedure to create or edit Hosted providers:</span></span>

<div>

## <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="79e1f-107">创建或编辑托管提供程序</span><span class="sxs-lookup"><span data-stu-id="79e1f-107">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="79e1f-108">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="79e1f-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="79e1f-109">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="79e1f-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="79e1f-110">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="79e1f-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="79e1f-111">在左侧导航栏中，单击“联盟和外部访问”\*\*\*\*，然后单击“SIP 联盟提供程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="79e1f-111">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="79e1f-112">如果您需要创建一个新的托管提供程序，请单击“新建”\*\*\*\*，然后单击“托管提供程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="79e1f-112">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="79e1f-113">如果您需要编辑托管提供程序列表上的一个条目，请选择一个托管提供程序，单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="79e1f-113">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="79e1f-114">在“编辑 SIP 联盟提供程序”\*\*\*\* 页面上，您可以键入或编辑下列设置：</span><span class="sxs-lookup"><span data-stu-id="79e1f-114">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="79e1f-115">**启用与此提供程序**     的通信选择此设置将启用与此提供商的用户的通信。</span><span class="sxs-lookup"><span data-stu-id="79e1f-115">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="79e1f-116">**提供程序名称：**    一个必需属性，请键入提供程序的名称，因为它将反映在 SIP 联合提供程序的列表中。</span><span class="sxs-lookup"><span data-stu-id="79e1f-116">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="79e1f-117">**访问边缘服务（FQDN）：**    一个必需属性，请键入您要配置的托管提供程序的访问边缘服务的完全限定的域名称。</span><span class="sxs-lookup"><span data-stu-id="79e1f-117">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="79e1f-118">此信息应由托管提供程序提供，并且仅当托管提供程序对托管提供程序的访问边缘服务的 FQDN 进行更改时，才应更改此信息。</span><span class="sxs-lookup"><span data-stu-id="79e1f-118">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="79e1f-119">**默认验证级别：**    默认设置是，**允许用户与其 "联系人" 列表中使用此提供商的人员进行通信**，以将通信限制为您已接受且位于您的联系人列表中的联系人。</span><span class="sxs-lookup"><span data-stu-id="79e1f-119">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="79e1f-p103">选择“允许用户与所有使用此提供程序的人员通信”\*\*\*\* 可取消您必须收到并接受联系人邀请的限制。此设置不限制可从托管提供程序的网络与您联系的人。</span><span class="sxs-lookup"><span data-stu-id="79e1f-p103">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="79e1f-122">当您配置完设置后，单击“提交”\*\*\*\* 进行保存，或单击“取消”\*\*\*\* 放弃所做的更改。</span><span class="sxs-lookup"><span data-stu-id="79e1f-122">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="79e1f-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79e1f-123">See Also</span></span>


[<span data-ttu-id="79e1f-124">配置策略以控制 Lync Server 2013 中的公共用户访问</span><span class="sxs-lookup"><span data-stu-id="79e1f-124">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="79e1f-125">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="79e1f-125">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

