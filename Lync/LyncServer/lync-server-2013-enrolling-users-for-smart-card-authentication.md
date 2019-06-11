---
title: 'Lync Server 2013: 注册智能卡身份验证的用户'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enrolling users for smart card authentication
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308570(v=OCS.15)
ms:contentKeyID: 54973691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11e74f35119a083aacd8440aec53594b8091b8e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="05a33-102">在 Lync Server 2013 中注册智能卡身份验证的用户</span><span class="sxs-lookup"><span data-stu-id="05a33-102">Enrolling users for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05a33-103">_**主题上次修改时间:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="05a33-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="05a33-p101">通常，可通过两种方法为用户注册智能卡身份验证。较为轻松的方法涉及使用 Web 注册直接为用户注册智能卡身份验证，而较为复杂的方法涉及使用注册代理。本主题着重介绍自动注册智能卡证书。</span><span class="sxs-lookup"><span data-stu-id="05a33-p101">There are generally two methods for enrolling users for smart card authentication. The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent. This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="05a33-107">有关作为注册代理代表用户进行注册的详细信息, 请参阅在[http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367)上代表其他用户注册证书。</span><span class="sxs-lookup"><span data-stu-id="05a33-107">For more information on enrolling on behalf of users as an enrollment agent, see Enroll for Certificates on Behalf of Other Users at [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367).</span></span>

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="05a33-108">为用户注册智能卡身份验证</span><span class="sxs-lookup"><span data-stu-id="05a33-108">To Enroll Users for Smart Card Authentication</span></span>

1.  <span data-ttu-id="05a33-109">使用启用了 Lync 的用户的凭据登录到 Windows 8 工作站。</span><span class="sxs-lookup"><span data-stu-id="05a33-109">Log in to the Windows 8 workstation using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="05a33-110">启动 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="05a33-110">Launch Internet Explorer.</span></span>

3.  <span data-ttu-id="05a33-111">浏览到**证书颁发机构 Web 注册**页面 (例如https://MyCA.contoso.com/certsrv),</span><span class="sxs-lookup"><span data-stu-id="05a33-111">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="05a33-112">如果您正在使用 Internet Explorer 10，则可能需要在兼容模式下查看此网站。</span><span class="sxs-lookup"><span data-stu-id="05a33-112">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

4.  <span data-ttu-id="05a33-113">在“欢迎”\*\*\*\* 页面上，选择“申请证书”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="05a33-113">On the **Welcome** Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="05a33-114">下一步，选择“高级申请”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="05a33-114">Next, select **Advanced Request**.</span></span>

6.  <span data-ttu-id="05a33-115">单击“创建并向此 CA 提交一个申请”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="05a33-115">Select **Create and submit a request to this CA**.</span></span>

7.  <span data-ttu-id="05a33-116">在“证书模板”\*\*\*\* 部分下方选择“智能卡用户”\*\*\*\*，并使用以下值完成高级证书申请：</span><span class="sxs-lookup"><span data-stu-id="05a33-116">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>
    
      - <span data-ttu-id="05a33-117">“密钥选项”\*\*\*\* 确认以下设置：</span><span class="sxs-lookup"><span data-stu-id="05a33-117">**Key Options** confirm he following settings:</span></span>
        
          - <span data-ttu-id="05a33-118">选择“创建新密钥集”\*\*\*\* 单选按钮</span><span class="sxs-lookup"><span data-stu-id="05a33-118">Select the **Create new key set** radio button</span></span>
        
          - <span data-ttu-id="05a33-119">对于“CSP”\*\*\*\*，选择“Microsoft 基本智能卡加密提供程序”\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="05a33-119">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>
        
          - <span data-ttu-id="05a33-120">对于“密钥用法”\*\*\*\*，选择“Exchange”\*\*\*\*（这是唯一可用选项）。</span><span class="sxs-lookup"><span data-stu-id="05a33-120">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>
        
          - <span data-ttu-id="05a33-121">对于“密码大小”\*\*\*\*，输入 **2048**</span><span class="sxs-lookup"><span data-stu-id="05a33-121">For **Key Size**, enter **2048**</span></span>
        
          - <span data-ttu-id="05a33-122">确认已选中“自动密钥容器名称”\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="05a33-122">Confirm that **Automatic key container name** is selected</span></span>
        
          - <span data-ttu-id="05a33-123">取消选中其他框。</span><span class="sxs-lookup"><span data-stu-id="05a33-123">Leave the other boxes unchecked.</span></span>
    
      - <span data-ttu-id="05a33-124">在“其他选项”\*\*\*\* 下方，确认以下值：</span><span class="sxs-lookup"><span data-stu-id="05a33-124">Under **Additional Options** confirm the following values:</span></span>
        
          - <span data-ttu-id="05a33-125">对于“申请格式”\*\*\*\*，选择“CMC”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="05a33-125">For **Request Format** select **CMC**.</span></span>
        
          - <span data-ttu-id="05a33-126">对于“哈希算法”\*\*\*\*，选择“sha1”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="05a33-126">For **Hash Algorithm** select **sha1**.</span></span>
        
          - <span data-ttu-id="05a33-127">对于“友好名称”\*\*\*\*，输入**Smardcard Certificate**。</span><span class="sxs-lookup"><span data-stu-id="05a33-127">For **Friendly Name** enter **Smardcard Certificate**.</span></span>

8.  <span data-ttu-id="05a33-128">如果您正在使用物理智能卡读取器，请将智能卡插入设备中。</span><span class="sxs-lookup"><span data-stu-id="05a33-128">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9.  <span data-ttu-id="05a33-129">单击“提交”\*\*\*\* 提交证书申请。</span><span class="sxs-lookup"><span data-stu-id="05a33-129">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="05a33-130">出现提示时，输入用于创建虚拟智能卡的 PIN。</span><span class="sxs-lookup"><span data-stu-id="05a33-130">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="05a33-131">默认虚拟智能卡 PIN 值是“12345678”。</span><span class="sxs-lookup"><span data-stu-id="05a33-131">The default virtual smart card PIN value is ‘12345678’.</span></span>

    
    </div>

11. <span data-ttu-id="05a33-132">颁发证书后，单击“安装此证书”\*\*\*\* 完成注册过程。</span><span class="sxs-lookup"><span data-stu-id="05a33-132">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="05a33-133">如果证书申请失败并出现错误“Web 浏览器不支持生成证书申请”，可通过三种可能的方法解决该问题：</span><span class="sxs-lookup"><span data-stu-id="05a33-133">If your certificate request fails with the error “This Web browser does not support the generation of certificate requests,” there are three possible ways to resolve the issue:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="05a33-134">在 Internet Explorer 中启用兼容性视图</span><span class="sxs-lookup"><span data-stu-id="05a33-134">Enable Compatibility View in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="05a33-135">在 Internet Explorer 中启用“启用 Intranet 设置”选项</span><span class="sxs-lookup"><span data-stu-id="05a33-135">Enable the Turn on Intranet settings option in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="05a33-136">在“Internet Explorer 选项”菜单的“安全”选项卡下方选择“将所有区域重置为默认级别”。</span><span class="sxs-lookup"><span data-stu-id="05a33-136">Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.</span></span></P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

