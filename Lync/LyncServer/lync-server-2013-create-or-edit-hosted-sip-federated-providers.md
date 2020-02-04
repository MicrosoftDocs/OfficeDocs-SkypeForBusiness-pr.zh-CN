---
title: Lync Server 2013：创建或编辑托管的 SIP 联盟提供程序
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
ms.openlocfilehash: d6c97255ce1dc9fce00d9eca6f358f4c68e1ff8a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a><span data-ttu-id="afcbf-102">在 Lync Server 2013 中创建或编辑托管的 SIP 联盟提供程序</span><span class="sxs-lookup"><span data-stu-id="afcbf-102">Create or edit hosted SIP federated providers Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afcbf-103">_**主题上次修改时间：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="afcbf-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="afcbf-104">托管提供商即时消息（IM）连接使组织中的用户能够使用 IM 与托管提供商（包括 Microsoft Office 365 和 Lync Online）提供的 IM 服务的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="afcbf-104">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers, including the Microsoft Office 365 and Lync Online.</span></span>

<span data-ttu-id="afcbf-105">每个托管提供程序均使用提供程序的边缘服务器完全限定的域名进行配置，默认验证级别**允许用户仅与其 "联系人" 列表中使用此提供程序的人员进行通信**。</span><span class="sxs-lookup"><span data-stu-id="afcbf-105">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="afcbf-106">使用以下过程创建或编辑托管提供程序：</span><span class="sxs-lookup"><span data-stu-id="afcbf-106">Use the following procedure to create or edit Hosted providers:</span></span>

<div>

## <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="afcbf-107">创建或编辑托管提供商</span><span class="sxs-lookup"><span data-stu-id="afcbf-107">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="afcbf-108">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="afcbf-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="afcbf-109">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="afcbf-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="afcbf-110">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="afcbf-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="afcbf-111">在左侧导航栏中，单击 "**联盟和外部访问**"，然后单击 " **SIP 联合提供商**"。</span><span class="sxs-lookup"><span data-stu-id="afcbf-111">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="afcbf-112">如果需要创建新的托管提供商，请单击 "**新建**"，然后单击 "**托管提供商**"。</span><span class="sxs-lookup"><span data-stu-id="afcbf-112">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="afcbf-113">如果需要从托管提供商列表中编辑条目，请选择托管提供商，单击 "**编辑**"，然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="afcbf-113">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="afcbf-114">在 "**编辑 SIP 联合提供商**" 页面上，您可以键入或编辑以下设置：</span><span class="sxs-lookup"><span data-stu-id="afcbf-114">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="afcbf-115">**启用与此提供商**   的通信选择此设置可启用与此提供商的用户的通信。</span><span class="sxs-lookup"><span data-stu-id="afcbf-115">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="afcbf-116">**提供程序名称：**   "必需" 属性键入提供程序的名称，因为它将反映在 SIP 联合提供程序的列表中。</span><span class="sxs-lookup"><span data-stu-id="afcbf-116">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="afcbf-117">**Access edge 服务（FQDN）：**   一个必需的属性，键入你要配置的托管提供程序的访问边缘服务的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="afcbf-117">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="afcbf-118">此信息应由托管提供程序提供，并且仅当托管提供程序对托管提供程序的访问边缘服务的 FQDN 进行更改时，才应更改此信息。</span><span class="sxs-lookup"><span data-stu-id="afcbf-118">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="afcbf-119">**默认验证级别：**   默认设置，**允许用户与使用此提供商的联系人列表中的人员进行通信**，将对您已接受的联系人和您的联系人列表中的联系人进行通信。</span><span class="sxs-lookup"><span data-stu-id="afcbf-119">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="afcbf-120">选择 "**允许用户通过此提供商与所有人通信**"，将删除您必须收到并接受的联系人邀请的限制。</span><span class="sxs-lookup"><span data-stu-id="afcbf-120">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="afcbf-121">此设置不限制可以通过托管提供商的网络与您联系的人员。</span><span class="sxs-lookup"><span data-stu-id="afcbf-121">This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="afcbf-122">配置设置完成后，单击 "**提交**" 以保存，或单击 "**取消**" 放弃更改。</span><span class="sxs-lookup"><span data-stu-id="afcbf-122">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="afcbf-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="afcbf-123">See Also</span></span>


[<span data-ttu-id="afcbf-124">在 Lync Server 2013 中配置策略以控制公共用户访问</span><span class="sxs-lookup"><span data-stu-id="afcbf-124">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="afcbf-125">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="afcbf-125">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

