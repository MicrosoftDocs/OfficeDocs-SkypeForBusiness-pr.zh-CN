---
title: Lync Server 2013：创建注册器配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Registrar configuration settings
ms:assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182601(v=OCS.15)
ms:contentKeyID: 48185758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6167e82679aa0124b2ae8833be9d4a9a56df2009
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="624ac-102">在 Lync Server 2013 中创建注册器配置设置</span><span class="sxs-lookup"><span data-stu-id="624ac-102">Create Registrar configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="624ac-103">_**上次修改的主题：** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="624ac-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="624ac-p101">可以使用注册器配置代理服务器身份验证方法。指定的身份验证协议确定池中的服务器向客户端发出的质询类型。可以选择以下协议：</span><span class="sxs-lookup"><span data-stu-id="624ac-p101">You can use the Registrar to configure proxy server authentication methods. The authentication protocol you specify determines which type of challenges the servers in the pool issue to clients. The available protocols are:</span></span>

  - <span data-ttu-id="624ac-107">**Kerberos**   这是可用于客户端的最强大的基于密码的身份验证方案，但通常仅对企业客户端可用，因为它需要客户端与密钥分发中心（Kerberos 域控制器）的连接。</span><span class="sxs-lookup"><span data-stu-id="624ac-107">**Kerberos**   This is the strongest password-based authentication scheme available to clients, but it is normally available only to enterprise clients because it requires client connection to a Key Distribution Center (Kerberos domain controller).</span></span> <span data-ttu-id="624ac-108">如果服务器仅对企业客户端进行身份验证，则此设置适用。</span><span class="sxs-lookup"><span data-stu-id="624ac-108">This setting is appropriate if the server authenticates only enterprise clients.</span></span>

  - <span data-ttu-id="624ac-109">**NTLM**   这是一种基于密码的身份验证，对密码使用质询响应哈希方案的客户端可用。</span><span class="sxs-lookup"><span data-stu-id="624ac-109">**NTLM**   This is the password-based authentication available to clients that use a challenge-response hashing scheme on the password.</span></span> <span data-ttu-id="624ac-110">这是在没有与密钥分发中心（Kerberos 域控制器）（如远程用户）连接的情况下，客户端可以使用的唯一身份验证形式。</span><span class="sxs-lookup"><span data-stu-id="624ac-110">This is the only form of authentication available to clients without connectivity to a Key Distribution Center (Kerberos domain controller), such as remote users.</span></span> <span data-ttu-id="624ac-111">如果服务器仅对远程用户进行身份验证，则应选择 "NTLM"。</span><span class="sxs-lookup"><span data-stu-id="624ac-111">If a server authenticates only remote users, you should choose NTLM.</span></span>

  - <span data-ttu-id="624ac-112">**证书身份验证**   当服务器需要从 Lync Phone Edition 客户端、公共区域电话、lync 2013 和 lync Windows 应用商店应用获取证书时，这是一种新的身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="624ac-112">**Certificate authentication**   This is the new authentication method when the server needs to obtain certificates from Lync Phone Edition clients, common area phones, Lync 2013 and the Lync Windows Store app.</span></span> <span data-ttu-id="624ac-113">在 Lync Phone Edition 客户端上，用户登录并通过提供个人标识号（PIN）成功进行身份验证后，Lync Server 2013 将 SIP URI 设置为电话，并设置将 Joe （Ex： SN=joe@contoso.com）标识为电话的 Lync Server 签名证书或用户证书。</span><span class="sxs-lookup"><span data-stu-id="624ac-113">On Lync Phone Edition clients, after a user signs in and is successfully authenticated by providing a personal identification number (PIN), Lync Server 2013 then provisions the SIP URI to the phone and provisions a Lync Server signed certificate or a user certificate that identifies Joe (Ex: SN=joe@contoso.com ) to the phone.</span></span> <span data-ttu-id="624ac-114">此证书用于对注册器和 Web 服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="624ac-114">This certificate is used for authenticating with the Registrar and Web Services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="624ac-p105">如果服务器支持对远程客户端和企业客户端进行身份验证，我们建议您同时启用 Kerberos 和 NTLM。边缘服务器与内部服务器通信，以确保只向远程客户端提供 NTLM 身份验证。如果在这些服务器上只启用 Kerberos，则无法对远程用户进行身份验证。如果该服务器也对企业用户进行身份验证，则会使用 Kerberos。</span><span class="sxs-lookup"><span data-stu-id="624ac-p105">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span><BR><span data-ttu-id="624ac-119">如果您将使用 Lync Windows 应用商店应用程序客户端，则必须启用证书身份验证。</span><span class="sxs-lookup"><span data-stu-id="624ac-119">If you will use Lync Windows Store app clients, you must enable certificate authentication.</span></span>



</div>

<span data-ttu-id="624ac-120">按照以下步骤创建新的注册器。</span><span class="sxs-lookup"><span data-stu-id="624ac-120">Follow these steps to create a new Registrar.</span></span>

<div>

## <a name="to-create-new-registrar-configuration-settings"></a><span data-ttu-id="624ac-121">创建新的注册器配置设置</span><span class="sxs-lookup"><span data-stu-id="624ac-121">To create new Registrar configuration settings</span></span>

1.  <span data-ttu-id="624ac-122">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户，登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="624ac-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="624ac-123">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="624ac-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="624ac-124">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="624ac-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="624ac-125">在左侧导航栏中，单击“安全性”\*\*\*\*，然后单击“注册器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="624ac-125">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="624ac-126">在“注册器”\*\*\*\* 页上，单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="624ac-126">On the **Registrar** page, click **New**</span></span>

5.  <span data-ttu-id="624ac-127">在“选择服务”\*\*\*\* 中，单击将应用此注册器的服务，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="624ac-127">In **Select a Service**, click the service to which the Registrar is to be applied and then click **OK**.</span></span>

6.  <span data-ttu-id="624ac-128">在“新建注册器设置”\*\*\*\* 中，根据客户端的功能和环境支持，选择下列一项或多项：</span><span class="sxs-lookup"><span data-stu-id="624ac-128">In **New Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="624ac-129">**启用 Kerberos 身份验证**，可使池中的服务器使用 Kerberos 身份验证发出质询。</span><span class="sxs-lookup"><span data-stu-id="624ac-129">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
      - <span data-ttu-id="624ac-130">**启用 NTLM 身份验证**，可使池中的服务器使用 NTLM 发出质询。</span><span class="sxs-lookup"><span data-stu-id="624ac-130">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
      - <span data-ttu-id="624ac-131">**启用证书身份验证**，可使池中的服务器向客户端颁发证书。</span><span class="sxs-lookup"><span data-stu-id="624ac-131">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>

7.  <span data-ttu-id="624ac-132">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="624ac-132">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

