---
title: Lync Server 2013：将双重身份验证与 Lync 客户端结合使用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using two-factor authentication with Lync client
ms:assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn338071(v=OCS.15)
ms:contentKeyID: 55115593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c90183d13581387d444301278d4c1c1125e5dc91
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a><span data-ttu-id="5a82e-102">对 Lync 客户端和 Lync Server 2013 使用双重身份验证</span><span class="sxs-lookup"><span data-stu-id="5a82e-102">Using two-factor authentication with Lync client and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a82e-103">_**上次修改的主题：** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="5a82e-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="5a82e-104">本主题介绍了如何利用 Lync 2013 客户端的双重身份验证。</span><span class="sxs-lookup"><span data-stu-id="5a82e-104">This topic described how to take advantage of two-factor authentication with Lync 2013 client.</span></span>

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a><span data-ttu-id="5a82e-105">首次登录到 Lync 2013</span><span class="sxs-lookup"><span data-stu-id="5a82e-105">Sign in to Lync 2013 for the first time</span></span>

<span data-ttu-id="5a82e-106">在安装 Lync 2013 时，通常会自动配置你的 Lync 登录信息。</span><span class="sxs-lookup"><span data-stu-id="5a82e-106">Your Lync sign-in information is usually configured automatically when Lync 2013 is installed.</span></span> <span data-ttu-id="5a82e-107">但首次使用 Lync 时，您可能必须手动启动客户端。</span><span class="sxs-lookup"><span data-stu-id="5a82e-107">But the first time you use Lync, you might have to manually start the client.</span></span>

<span data-ttu-id="5a82e-108">**首次登录 Lync**</span><span class="sxs-lookup"><span data-stu-id="5a82e-108">**To sign in to Lync for the first time**</span></span>

1.  <span data-ttu-id="5a82e-109">登录到您的组织的网络。</span><span class="sxs-lookup"><span data-stu-id="5a82e-109">Log on to your organization’s network.</span></span>

2.  <span data-ttu-id="5a82e-110">选择 "**启动** \> **所有程序** \> **Microsoft \> Lync lync 2013**"。</span><span class="sxs-lookup"><span data-stu-id="5a82e-110">Select **Start** \> **All Programs** \> **Microsoft Lync \> Lync 2013**.</span></span>
    
    <span data-ttu-id="5a82e-111">您应该会看到 Lync 登录屏幕。</span><span class="sxs-lookup"><span data-stu-id="5a82e-111">You should see the Lync sign-in screen.</span></span>
    
      - <span data-ttu-id="5a82e-112">如果已填写 "登录地址" 框，请确认显示的地址正确无误。</span><span class="sxs-lookup"><span data-stu-id="5a82e-112">If the sign-in address box is already filled in, confirm that the address shown is correct.</span></span>
    
      - <span data-ttu-id="5a82e-113">如果不正确，或者如果该框为空，请输入你的 Lync 登录地址（这通常与你的电子邮件地址相同）。</span><span class="sxs-lookup"><span data-stu-id="5a82e-113">If it’s not correct, or if the box is empty, enter your Lync sign-in address (this is usually the same as your email address).</span></span>
    
      - <span data-ttu-id="5a82e-114">如果显示 "空密码" 框，请添加您的密码。</span><span class="sxs-lookup"><span data-stu-id="5a82e-114">If an empty password box is displayed, add your password.</span></span>

3.  <span data-ttu-id="5a82e-115">选择 **"登录"**。</span><span class="sxs-lookup"><span data-stu-id="5a82e-115">Select **Sign-in**.</span></span>

</div>

<div>

## <a name="sign-out-of-lync"></a><span data-ttu-id="5a82e-116">注销 Lync</span><span class="sxs-lookup"><span data-stu-id="5a82e-116">Sign out of Lync</span></span>

<span data-ttu-id="5a82e-117">使用 Lync 完成后，可以从 "文件" 菜单中关闭 "显示"、"注销会话" 或 "退出程序"。</span><span class="sxs-lookup"><span data-stu-id="5a82e-117">When you’re finished using Lync, you can close the display, sign out of your session, or exit from the program, all from the File menu.</span></span> <span data-ttu-id="5a82e-118">下表说明了这些选项之间的差异。</span><span class="sxs-lookup"><span data-stu-id="5a82e-118">The following table explains the differences in the options.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5a82e-119">方法</span><span class="sxs-lookup"><span data-stu-id="5a82e-119">Option</span></span></th>
<th><span data-ttu-id="5a82e-120">功能</span><span class="sxs-lookup"><span data-stu-id="5a82e-120">What it does</span></span></th>
<th><span data-ttu-id="5a82e-121">如何执行</span><span class="sxs-lookup"><span data-stu-id="5a82e-121">How to perform it</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5a82e-122">关闭</span><span class="sxs-lookup"><span data-stu-id="5a82e-122">Close</span></span></p></td>
<td><p><span data-ttu-id="5a82e-123">关闭你的 Lync 显示，但允许使用你的用户 ID 标识的 Lync 会话继续运行。</span><span class="sxs-lookup"><span data-stu-id="5a82e-123">Closes your Lync display but lets the Lync session identified with your user ID continue to run.</span></span> <span data-ttu-id="5a82e-124">这样，你就可以继续获取通知并与其他人进行交互。</span><span class="sxs-lookup"><span data-stu-id="5a82e-124">This is so you can continue to get notifications and interact with others.</span></span></p>
<p><span data-ttu-id="5a82e-125">您可以通过单击任务栏上的 Lync 图标或屏幕底部的通知区域随时获取显示。</span><span class="sxs-lookup"><span data-stu-id="5a82e-125">You can get the display back at any time by clicking the Lync icon on the taskbar or the notification area at the bottom of your screen.</span></span></p></td>
<td><p><span data-ttu-id="5a82e-126">在 "Lync 主" 窗口中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="5a82e-126">On the Lync main window, do one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="5a82e-127">选择 "<strong>选项</strong>" 按钮，然后选择 "<strong>文件</strong> &gt; <strong>关闭</strong>"。</span><span class="sxs-lookup"><span data-stu-id="5a82e-127">Select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Close</strong>.</span></span></p></li>
<li><p><span data-ttu-id="5a82e-128">单击窗口右上角的 "<strong>关闭</strong>" 按钮（X）。</span><span class="sxs-lookup"><span data-stu-id="5a82e-128">Click the <strong>Close</strong> button (X) in the upper-right corner of the window.</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a82e-129">注销</span><span class="sxs-lookup"><span data-stu-id="5a82e-129">Sign out</span></span></p></td>
<td><p><span data-ttu-id="5a82e-130">结束与您的用户 ID 关联的 Lync 会话，但 Lync 将继续在后台运行。</span><span class="sxs-lookup"><span data-stu-id="5a82e-130">Ends the Lync session associated with your user ID, but Lync continues to run in the background.</span></span> <span data-ttu-id="5a82e-131">当您注销时，将会出现登录窗口。</span><span class="sxs-lookup"><span data-stu-id="5a82e-131">When you sign out, the sign-in window will appear.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="5a82e-132">在注销时选择 "<STRONG>删除我的登录信息</STRONG>"，从计算机中删除您的登录 ID 和密码记录。</span><span class="sxs-lookup"><span data-stu-id="5a82e-132">Select <STRONG>Delete my sign-in information</STRONG> when you sign out to remove the record of your logon ID and password from the computer.</span></span> <span data-ttu-id="5a82e-133">这样做可能会使支持人员更轻松地解决登录问题。</span><span class="sxs-lookup"><span data-stu-id="5a82e-133">Doing this might make it easier for support people to troubleshoot sign-in issues.</span></span> <span data-ttu-id="5a82e-134">它还可以通过让未经授权的用户难以使用您的凭据登录，从而帮助确保您的登录信息更安全。</span><span class="sxs-lookup"><span data-stu-id="5a82e-134">It can also help ensure your sign-in information is more secure by making it difficult for unauthorized users to log on with your credentials.</span></span>


</div></td>
<td><p><span data-ttu-id="5a82e-135">在 "Lync 主" 窗口中，选择 "<strong>选项</strong>" 按钮，然后选择 "<strong>文件</strong> &gt; <strong>注销</strong>"。</span><span class="sxs-lookup"><span data-stu-id="5a82e-135">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Sign Out</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a82e-136">Exit</span><span class="sxs-lookup"><span data-stu-id="5a82e-136">Exit</span></span></p></td>
<td><p><span data-ttu-id="5a82e-137">结束 Lync 会话并关闭计算机上的 Lync。</span><span class="sxs-lookup"><span data-stu-id="5a82e-137">Ends your Lync session and shuts down Lync on your computer.</span></span> <span data-ttu-id="5a82e-138">退出后，如果要重新启动 Lync，请选择 "<strong>启动</strong> &gt; <strong>所有程序</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>lync 2013</strong>"。</span><span class="sxs-lookup"><span data-stu-id="5a82e-138">After exiting, if you want to restart Lync, select <strong>Start</strong> &gt; <strong>All Programs</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</span></span></p></td>
<td><p><span data-ttu-id="5a82e-139">在 "Lync 主" 窗口中，选择 "<strong>选项</strong>" 按钮，然后选择 "<strong>文件</strong> &gt; <strong>退出</strong>"。</span><span class="sxs-lookup"><span data-stu-id="5a82e-139">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Exit</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a><span data-ttu-id="5a82e-140">使用智能卡登录 Lync</span><span class="sxs-lookup"><span data-stu-id="5a82e-140">Sign in to Lync with a Smart Card</span></span>

<span data-ttu-id="5a82e-141">有些组织现在使用一个称为双重身份验证的多步骤登录过程来提高 Lync 2013 用户的安全性。</span><span class="sxs-lookup"><span data-stu-id="5a82e-141">Some organizations now use a multi-step sign-in process, called two-factor authentication, to increase security for their Lync 2013 users.</span></span> <span data-ttu-id="5a82e-142">如果您希望使用此选项，则需要 "智能卡" 才能登录 Lync。</span><span class="sxs-lookup"><span data-stu-id="5a82e-142">If you’re expected to use this option, you’ll need a “smart card” to sign in to Lync.</span></span> <span data-ttu-id="5a82e-143">智能卡分为两种种类，物理和虚拟：</span><span class="sxs-lookup"><span data-stu-id="5a82e-143">Smart cards come in two varieties, physical and virtual:</span></span>

  - <span data-ttu-id="5a82e-144">\*\*\*\*   有关信用卡大小的物理信息。</span><span class="sxs-lookup"><span data-stu-id="5a82e-144">**Physical**   About the size of a credit card.</span></span> <span data-ttu-id="5a82e-145">您在登录时将其插入到智能卡读取器中。</span><span class="sxs-lookup"><span data-stu-id="5a82e-145">You insert it into a smart card reader when you log in.</span></span>

  - <span data-ttu-id="5a82e-146">**虚拟**   不是物理对象，而是写入计算机上的特殊芯片的电子标识符，这实际上是将智能卡构建到计算机中的。</span><span class="sxs-lookup"><span data-stu-id="5a82e-146">**Virtual**   Not a physical object, but an electronic identifier that gets written to a special chip on your computer, which in essence builds the smart card into your computer.</span></span> <span data-ttu-id="5a82e-147">仅可用于包含 TPM （受信任的平台模块）芯片的 Windows 8 计算机。</span><span class="sxs-lookup"><span data-stu-id="5a82e-147">Available only for use with Windows 8 computers that contain the TPM (Trusted Platform Module) chip.</span></span>

<div>

## <a name="enroll-your-smart-card"></a><span data-ttu-id="5a82e-148">注册智能卡</span><span class="sxs-lookup"><span data-stu-id="5a82e-148">Enroll your smart card</span></span>

<span data-ttu-id="5a82e-149">在使用智能卡登录之前，必须对卡进行 "注册"，即您的用户凭据必须用卡片标识。</span><span class="sxs-lookup"><span data-stu-id="5a82e-149">Before you can sign in with a smart card, the card must be “enrolled”—that is, your user credentials have to be identified with the card.</span></span> <span data-ttu-id="5a82e-150">无论是物理卡还是虚拟卡都是如此。</span><span class="sxs-lookup"><span data-stu-id="5a82e-150">This is the case whether the card is physical or virtual.</span></span> <span data-ttu-id="5a82e-151">此过程可能已被你的 Lync Server 管理员执行。</span><span class="sxs-lookup"><span data-stu-id="5a82e-151">This process may already been carried out by your Lync Server administrator.</span></span> <span data-ttu-id="5a82e-152">如果你不确定是否已完成，请与他们进行检查。</span><span class="sxs-lookup"><span data-stu-id="5a82e-152">Check with them if you’re not sure whether that has been done.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5a82e-153">由于每个虚拟智能卡仅与安装它的设备相关联，因此需要为您使用的每个 Windows 8 计算机注册一个单独的卡。</span><span class="sxs-lookup"><span data-stu-id="5a82e-153">Since each virtual smart card is associated only with the device it’s installed on, a separate card will need to be enrolled for each Windows 8 computer you use.</span></span>



</div>

<span data-ttu-id="5a82e-154">**手动注册智能卡**</span><span class="sxs-lookup"><span data-stu-id="5a82e-154">**To manually enroll your smart card**</span></span>

1.  <span data-ttu-id="5a82e-155">登录到您将在其上运行 Lync 的计算机。</span><span class="sxs-lookup"><span data-stu-id="5a82e-155">Log on to the computer you’ll be running Lync on.</span></span>

2.  <span data-ttu-id="5a82e-156">使用 Internet Explorer，浏览到您的组织的 "证书颁发机构 Web 注册" 页。</span><span class="sxs-lookup"><span data-stu-id="5a82e-156">Using Internet Explorer, browse to your organization’s Certificate Authority Web Enrollment page.</span></span>
    
    <span data-ttu-id="5a82e-157">如果你还没有此资源的 web 地址，请向你的 Lync Server 管理员咨询。</span><span class="sxs-lookup"><span data-stu-id="5a82e-157">Ask your Lync Server administrator for the web address of this resource if you don’t already have it.</span></span> <span data-ttu-id="5a82e-158">该 URL 将如下所示： https://MyCA.\[yourcompanyname\]/certsrv。</span><span class="sxs-lookup"><span data-stu-id="5a82e-158">The URL will look something like this: https://MyCA.\[yourcompanyname\].com/certsrv.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5a82e-159">如果您使用的是 Internet Explorer 10，则可能需要在兼容模式下查看此网站。</span><span class="sxs-lookup"><span data-stu-id="5a82e-159">If you’re using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

3.  <span data-ttu-id="5a82e-160">当系统提示您登录到证书页时，请使用您的域帐户（而不是计算机的管理员）登录。</span><span class="sxs-lookup"><span data-stu-id="5a82e-160">When you’re prompted to log on to the certification page, log on using your domain account (rather than as administrator of your computer).</span></span>

4.  <span data-ttu-id="5a82e-161">在 "网站" "欢迎" 页上，选择 "**申请证书**"。</span><span class="sxs-lookup"><span data-stu-id="5a82e-161">On the website Welcome Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="5a82e-162">选择 "**高级请求**"。</span><span class="sxs-lookup"><span data-stu-id="5a82e-162">Select **Advanced Request**.</span></span>

6.  <span data-ttu-id="5a82e-163">选择 "**创建并向此 CA 提交一个请求**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5a82e-163">Select **Create and submit a request to this CA**, then click **Next**.</span></span>

7.  <span data-ttu-id="5a82e-164">现在，你将看到一个名为 "智能卡注册站" 的页面。</span><span class="sxs-lookup"><span data-stu-id="5a82e-164">Now you’ll see a page called Smart Card Enrollment Station.</span></span> <span data-ttu-id="5a82e-165">批准安装 ActiveX 控件的请求，然后完成 "高级证书请求" 表单，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5a82e-165">Approve the request to install the ActiveX control, and then complete the Advanced Certificate Request form as follows:</span></span>
    
    1.  <span data-ttu-id="5a82e-166">从 "**证书模板**" 下拉列表中选择 "**智能卡用户**"。</span><span class="sxs-lookup"><span data-stu-id="5a82e-166">Select **Smartcard user** from the **Certificate Template** dropdown list.</span></span>
    
    2.  <span data-ttu-id="5a82e-167">选择 "**创建新密钥集**"。</span><span class="sxs-lookup"><span data-stu-id="5a82e-167">Select **Create new key set**.</span></span>
    
    3.  <span data-ttu-id="5a82e-168">查找智能卡标签上的制造商信息，并从**CSP**下拉列表中选择该制造商。</span><span class="sxs-lookup"><span data-stu-id="5a82e-168">Find the manufacturer information on the label of your smart card and select that manufacturer from the **CSP** dropdown list.</span></span>
    
    4.  <span data-ttu-id="5a82e-169">选择 " **CSP** " 作为请求格式（如果尚未选中）。</span><span class="sxs-lookup"><span data-stu-id="5a82e-169">Select **CSP** as the Request Format, if it’s not already selected.</span></span>
    
    5.  <span data-ttu-id="5a82e-170">从 "哈希算法" 下拉列表中选择 " **sha1** " （如果尚未选中）。</span><span class="sxs-lookup"><span data-stu-id="5a82e-170">Select **sha1** from the Hash Algorithm dropdown list, if it’s not already selected.</span></span>
    
    6.  <span data-ttu-id="5a82e-171">为您的证书指定一个名称，然后单击 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="5a82e-171">Give your certificate a name you’ll recognize, and click **Submit**.</span></span>

8.  <span data-ttu-id="5a82e-172">现在，将空白智能卡插入到连接到注册站的读卡器中，然后单击 "**注册**"。</span><span class="sxs-lookup"><span data-stu-id="5a82e-172">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

9.  <span data-ttu-id="5a82e-173">出现提示时，输入您的个人识别码（PIN），然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="5a82e-173">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5a82e-174">如果你的技术支持人员未向你提供用于注册智能卡的专用 PIN，请使用默认智能卡 PIN 值为12345678。</span><span class="sxs-lookup"><span data-stu-id="5a82e-174">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

10. <span data-ttu-id="5a82e-175">选择此选项可强制用户（你）在首次使用智能卡时更改 PIN。</span><span class="sxs-lookup"><span data-stu-id="5a82e-175">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

11. <span data-ttu-id="5a82e-176">现在，将空白智能卡插入到连接到注册站的读卡器中，然后单击 "**注册**"。</span><span class="sxs-lookup"><span data-stu-id="5a82e-176">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

12. <span data-ttu-id="5a82e-177">出现提示时，输入您的个人识别码（PIN），然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="5a82e-177">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5a82e-178">如果你的技术支持人员未向你提供用于注册智能卡的专用 PIN，请使用默认智能卡 PIN 值为12345678。</span><span class="sxs-lookup"><span data-stu-id="5a82e-178">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

13. <span data-ttu-id="5a82e-179">选择此选项可强制用户（你）在首次使用智能卡时更改 PIN。</span><span class="sxs-lookup"><span data-stu-id="5a82e-179">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

14. <span data-ttu-id="5a82e-180">单击 **"确定**" 以确认显示的证书是否包含您的信息。</span><span class="sxs-lookup"><span data-stu-id="5a82e-180">Click **OK** to confirm that the certificate displayed has your information on it.</span></span>

15. <span data-ttu-id="5a82e-181">在发现证书已颁发的情况下，单击 "**安装此证书**" 以完成注册过程。</span><span class="sxs-lookup"><span data-stu-id="5a82e-181">Once you see the notice that the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a><span data-ttu-id="5a82e-182">使用智能卡凭据登录到 Lync</span><span class="sxs-lookup"><span data-stu-id="5a82e-182">Sign in to Lync with your smart card credentials</span></span>

<span data-ttu-id="5a82e-183">在首次使用智能卡之前，建议您在 Lync 登录页面上单击 "**删除我的登录信息**"。</span><span class="sxs-lookup"><span data-stu-id="5a82e-183">Before you use your smart card for the first time, it’s recommended that you click **Delete my sign-in info** on the Lync sign-in page.</span></span> <span data-ttu-id="5a82e-184">执行此操作将清除存储在计算机上的任何登录凭据，并消除可能的错误源。</span><span class="sxs-lookup"><span data-stu-id="5a82e-184">Doing this clears any sign-in credentials stored on your computer, and eliminates a possible source of error.</span></span>

<span data-ttu-id="5a82e-185">**使用智能卡凭据登录 Lync**</span><span class="sxs-lookup"><span data-stu-id="5a82e-185">**To sign in to Lync with your smart card credentials**</span></span>

1.  <span data-ttu-id="5a82e-186">启动 Lync 客户端。</span><span class="sxs-lookup"><span data-stu-id="5a82e-186">Start the Lync client.</span></span>

2.  <span data-ttu-id="5a82e-187">在 "登录" 屏幕上，在 "**登录地址**" 框中键入您的登录用户帐户名，然后单击 "**登录**"。</span><span class="sxs-lookup"><span data-stu-id="5a82e-187">On the Sign in screen, type your sign in user account name in the **Sign-in address** box, and then click **Sign In**.</span></span>

3.  <span data-ttu-id="5a82e-188">如果使用的是虚拟智能卡，请跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="5a82e-188">If you are using a virtual smart card, skip this step.</span></span>
    
    <span data-ttu-id="5a82e-189">如果使用的是物理智能卡，请将智能卡插入智能卡读卡器中，并提示您执行此操作，然后在检测到卡时单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="5a82e-189">If you are using a physical smart card, insert the smart card into your smart card reader and prompted to do so, and then click **OK** when the card is detected.</span></span>

4.  <span data-ttu-id="5a82e-190">键入您的智能卡的 PIN 号码，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="5a82e-190">Type in the PIN number you for your smart card and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5a82e-191">如果你的支持人员未向你分配智能卡 PIN 号码，请使用默认值12345678。</span><span class="sxs-lookup"><span data-stu-id="5a82e-191">If you were not assigned a smart card PIN number by your support person, use the default value, which is 12345678.</span></span>

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

