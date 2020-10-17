---
title: Lync Server 2013：为用户注册智能卡身份验证
description: Lync Server 2013：为用户注册智能卡身份验证。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enrolling users for smart card authentication
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308570(v=OCS.15)
ms:contentKeyID: 54973691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d67994d2152ac344934d093a1b6f7d482a7933a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558468"
---
# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="861be-103">在 Lync Server 2013 中为用户注册智能卡身份验证</span><span class="sxs-lookup"><span data-stu-id="861be-103">Enrolling users for smart card authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="861be-104">_**上次修改的主题：** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="861be-104">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="861be-105">为用户注册智能卡身份验证的方法通常有两种。</span><span class="sxs-lookup"><span data-stu-id="861be-105">There are generally two methods for enrolling users for smart card authentication.</span></span> <span data-ttu-id="861be-106">更简单的方法是让用户使用 web 注册直接注册智能卡身份验证，而更复杂的方法涉及使用注册代理。</span><span class="sxs-lookup"><span data-stu-id="861be-106">The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent.</span></span> <span data-ttu-id="861be-107">本主题重点介绍了智能卡证书的自注册。</span><span class="sxs-lookup"><span data-stu-id="861be-107">This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="861be-108">有关作为注册代理代表用户注册的详细信息，请参阅在上代表其他用户注册证书 [https://go.microsoft.com/fwlink/p/?LinkID=313367](https://go.microsoft.com/fwlink/p/?linkid=313367) 。</span><span class="sxs-lookup"><span data-stu-id="861be-108">For more information on enrolling on behalf of users as an enrollment agent, see Enroll for Certificates on Behalf of Other Users at [https://go.microsoft.com/fwlink/p/?LinkID=313367](https://go.microsoft.com/fwlink/p/?linkid=313367).</span></span>

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="861be-109">为用户注册智能卡身份验证</span><span class="sxs-lookup"><span data-stu-id="861be-109">To Enroll Users for Smart Card Authentication</span></span>

1.  <span data-ttu-id="861be-110">使用启用了 Lync 的用户的凭据登录到 Windows 8 工作站。</span><span class="sxs-lookup"><span data-stu-id="861be-110">Log in to the Windows 8 workstation using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="861be-111">启动 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="861be-111">Launch Internet Explorer.</span></span>

3.  <span data-ttu-id="861be-112">浏览到 " **证书颁发机构 Web 注册** " 页 (https://MyCA.contoso.com/certsrv) 例如，</span><span class="sxs-lookup"><span data-stu-id="861be-112">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="861be-113">如果使用的是 Internet Explorer 10，则可能需要在兼容模式下查看此网站。</span><span class="sxs-lookup"><span data-stu-id="861be-113">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

4.  <span data-ttu-id="861be-114">在 " **欢迎** " 页面上，选择 " **申请证书**"。</span><span class="sxs-lookup"><span data-stu-id="861be-114">On the **Welcome** Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="861be-115">接下来，选择 " **高级请求**"。</span><span class="sxs-lookup"><span data-stu-id="861be-115">Next, select **Advanced Request**.</span></span>

6.  <span data-ttu-id="861be-116">选择 " **创建并向此 CA 提交一个请求**"。</span><span class="sxs-lookup"><span data-stu-id="861be-116">Select **Create and submit a request to this CA**.</span></span>

7.  <span data-ttu-id="861be-117">在 "**证书模板**" 部分下选择 "**智能卡用户**"，并使用以下值完成高级证书请求：</span><span class="sxs-lookup"><span data-stu-id="861be-117">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>
    
      - <span data-ttu-id="861be-118">**主要选项** 确认他的以下设置：</span><span class="sxs-lookup"><span data-stu-id="861be-118">**Key Options** confirm he following settings:</span></span>
        
          - <span data-ttu-id="861be-119">选择 " **创建新密钥集** " 单选按钮</span><span class="sxs-lookup"><span data-stu-id="861be-119">Select the **Create new key set** radio button</span></span>
        
          - <span data-ttu-id="861be-120">对于 **CSP**，选择 **Microsoft 基本智能卡加密提供程序**</span><span class="sxs-lookup"><span data-stu-id="861be-120">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>
        
          - <span data-ttu-id="861be-121">若要 **使用密钥**，请选择 " **Exchange** (这是唯一可) 的选项。</span><span class="sxs-lookup"><span data-stu-id="861be-121">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>
        
          - <span data-ttu-id="861be-122">对于 **密钥大小**，请输入 **2048**</span><span class="sxs-lookup"><span data-stu-id="861be-122">For **Key Size**, enter **2048**</span></span>
        
          - <span data-ttu-id="861be-123">确认已选择 " **自动密钥容器名称** "</span><span class="sxs-lookup"><span data-stu-id="861be-123">Confirm that **Automatic key container name** is selected</span></span>
        
          - <span data-ttu-id="861be-124">将其他框保留为未选中状态。</span><span class="sxs-lookup"><span data-stu-id="861be-124">Leave the other boxes unchecked.</span></span>
    
      - <span data-ttu-id="861be-125">在 " **其他选项** " 下，确认以下值：</span><span class="sxs-lookup"><span data-stu-id="861be-125">Under **Additional Options** confirm the following values:</span></span>
        
          - <span data-ttu-id="861be-126">对于 **请求格式** ，请选择 **CMC**。</span><span class="sxs-lookup"><span data-stu-id="861be-126">For **Request Format** select **CMC**.</span></span>
        
          - <span data-ttu-id="861be-127">对于 **哈希算法** ，请选择 " **sha1**"。</span><span class="sxs-lookup"><span data-stu-id="861be-127">For **Hash Algorithm** select **sha1**.</span></span>
        
          - <span data-ttu-id="861be-128">对于 **友好名称** ，请输入 **Smardcard 证书**。</span><span class="sxs-lookup"><span data-stu-id="861be-128">For **Friendly Name** enter **Smardcard Certificate**.</span></span>

8.  <span data-ttu-id="861be-129">如果使用的是物理智能卡读取器，请将智能卡插入设备中。</span><span class="sxs-lookup"><span data-stu-id="861be-129">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9.  <span data-ttu-id="861be-130">单击 " **提交** " 以提交证书请求。</span><span class="sxs-lookup"><span data-stu-id="861be-130">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="861be-131">出现提示时，请输入用于创建虚拟智能卡的 PIN。</span><span class="sxs-lookup"><span data-stu-id="861be-131">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="861be-132">默认的虚拟智能卡 PIN 值为 "12345678"。</span><span class="sxs-lookup"><span data-stu-id="861be-132">The default virtual smart card PIN value is ‘12345678’.</span></span>

    
    </div>

11. <span data-ttu-id="861be-133">颁发证书后，单击 " **安装此证书** " 以完成注册过程。</span><span class="sxs-lookup"><span data-stu-id="861be-133">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="861be-134">如果您的证书请求失败，并出现错误 "此 Web 浏览器不支持生成证书请求"，则有三种可能的方法可以解决此问题：</span><span class="sxs-lookup"><span data-stu-id="861be-134">If your certificate request fails with the error “This Web browser does not support the generation of certificate requests,” there are three possible ways to resolve the issue:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="861be-135">在 Internet Explorer 中启用兼容性视图</span><span class="sxs-lookup"><span data-stu-id="861be-135">Enable Compatibility View in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="861be-136">启用 Internet Explorer 中的 "打开 Intranet 设置" 选项</span><span class="sxs-lookup"><span data-stu-id="861be-136">Enable the Turn on Intranet settings option in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="861be-137">在 "Internet Explorer 选项" 菜单中的 "安全" 选项卡下，选择 "将所有区域重置为默认级别" 设置。</span><span class="sxs-lookup"><span data-stu-id="861be-137">Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.</span></span></P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

