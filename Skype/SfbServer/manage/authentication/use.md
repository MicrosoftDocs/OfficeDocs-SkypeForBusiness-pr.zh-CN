---
title: 对 Skype for Business 客户端 和 Skype for Business Server 2015 使用双重身份验证
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: 摘要： 使用双因素身份验证 Skype 业务服务器 2015年和 Skype 的业务。
ms.openlocfilehash: 6bb2133533b640cd573730ca608f5845164ea282
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server-2015"></a><span data-ttu-id="994ac-103">对 Skype for Business 客户端 和 Skype for Business Server 2015 使用双重身份验证</span><span class="sxs-lookup"><span data-stu-id="994ac-103">Use two-factor authentication with Skype for Business client and Skype for Business Server 2015</span></span>
 
<span data-ttu-id="994ac-104">**摘要：**使用 Skype 业务服务器 2015年和 Skype 业务两因素身份验证。</span><span class="sxs-lookup"><span data-stu-id="994ac-104">**Summary:** Use two-factor authentication with Skype for Business Server 2015 and Skype for Business.</span></span>
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a><span data-ttu-id="994ac-105">首次登录 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="994ac-105">Sign in to Skype for Business for the first time</span></span>

<span data-ttu-id="994ac-106">安装 Skype 业务时，您的登录信息是通常自动配置。</span><span class="sxs-lookup"><span data-stu-id="994ac-106">Your sign-in information is usually configured automatically when Skype for Business is installed.</span></span> <span data-ttu-id="994ac-107">但第一次使用 Skype 业务，您可能需要手动启动客户端。</span><span class="sxs-lookup"><span data-stu-id="994ac-107">But the first time you use Skype for Business, you might have to manually start the client.</span></span>
  
### <a name="to-sign-in-for-the-first-time"></a><span data-ttu-id="994ac-108">首次登录</span><span class="sxs-lookup"><span data-stu-id="994ac-108">To sign in for the first time</span></span>

1. <span data-ttu-id="994ac-109">登录到您的组织的网络。</span><span class="sxs-lookup"><span data-stu-id="994ac-109">Log on to your organization's network.</span></span>
    
2. <span data-ttu-id="994ac-110">选择**开始** > **所有程序** > **业务的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="994ac-110">Select **Start** > **All Programs** > **Skype for Business**.</span></span>
    
    <span data-ttu-id="994ac-111">您应该会看到登录屏幕。</span><span class="sxs-lookup"><span data-stu-id="994ac-111">You should see the sign-in screen.</span></span>
    
    - <span data-ttu-id="994ac-112">如果登录地址框已经填充，请确认显示的地址是否正确。</span><span class="sxs-lookup"><span data-stu-id="994ac-112">If the sign-in address box is already filled in, confirm that the address shown is correct.</span></span>
    
    - <span data-ttu-id="994ac-113">如果不正确，或者如果此框为空，请输入登录地址 （这通常是您的电子邮件地址相同）。</span><span class="sxs-lookup"><span data-stu-id="994ac-113">If it's not correct, or if the box is empty, enter your sign-in address (this is usually the same as your email address).</span></span>
    
    - <span data-ttu-id="994ac-114">如果显示空密码框，请添加您的密码。</span><span class="sxs-lookup"><span data-stu-id="994ac-114">If an empty password box is displayed, add your password.</span></span>
    
3. <span data-ttu-id="994ac-115">选择“登录”****。</span><span class="sxs-lookup"><span data-stu-id="994ac-115">Select **Sign-in**.</span></span>
    
## <a name="sign-out-of-skype-for-business"></a><span data-ttu-id="994ac-116">注销 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="994ac-116">Sign out of Skype for Business</span></span>

<span data-ttu-id="994ac-117">使用 Skype 业务操作完成后，您可以关闭显示器，登录到您的会话，或退出程序，请从文件菜单。</span><span class="sxs-lookup"><span data-stu-id="994ac-117">When you're finished using Skype for Business, you can close the display, sign out of your session, or exit from the program, all from the File menu.</span></span> <span data-ttu-id="994ac-118">下表说明了这些选项之间的差异。</span><span class="sxs-lookup"><span data-stu-id="994ac-118">The following table explains the differences in the options.</span></span>
  
|<span data-ttu-id="994ac-119">**选项**</span><span class="sxs-lookup"><span data-stu-id="994ac-119">**Option**</span></span>|<span data-ttu-id="994ac-120">**它的作用**</span><span class="sxs-lookup"><span data-stu-id="994ac-120">**What it does**</span></span>|<span data-ttu-id="994ac-121">**如何执行它**</span><span class="sxs-lookup"><span data-stu-id="994ac-121">**How to perform it**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="994ac-122">关闭</span><span class="sxs-lookup"><span data-stu-id="994ac-122">Close</span></span>  <br/> |<span data-ttu-id="994ac-123">关闭显示器，但让 Skype 业务会话标识与用户 ID 继续运行。</span><span class="sxs-lookup"><span data-stu-id="994ac-123">Closes your display but lets the Skype for Business session identified with your user ID continue to run.</span></span> <span data-ttu-id="994ac-124">因此，您可以继续接收通知并与其他人互动。</span><span class="sxs-lookup"><span data-stu-id="994ac-124">This is so you can continue to get notifications and interact with others.</span></span> <br/> <br/> <span data-ttu-id="994ac-125">您可以随时重新显示通过单击 Skype 业务通知区域位于屏幕底部任务栏上的图标。</span><span class="sxs-lookup"><span data-stu-id="994ac-125">You can get the display back at any time by clicking the Skype for Business icon on the taskbar or the notification area at the bottom of your screen.</span></span>  <br/> | <span data-ttu-id="994ac-126">在 Skype 业务主窗口中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="994ac-126">On the Skype for Business main window, do one of the following:</span></span> <br/> <span data-ttu-id="994ac-127">1.选择**选项**按钮，然后选择**文件** > **关闭**。</span><span class="sxs-lookup"><span data-stu-id="994ac-127">1. Select the **Options** button, then select **File** > **Close**.</span></span>  <br/> <span data-ttu-id="994ac-128">2.单击窗口右上角的**关闭**按钮 (X)。</span><span class="sxs-lookup"><span data-stu-id="994ac-128">2. Click the **Close** button (X) in the upper-right corner of the window.</span></span> <br/> |
|<span data-ttu-id="994ac-129">注销</span><span class="sxs-lookup"><span data-stu-id="994ac-129">Sign out</span></span>  <br/> |<span data-ttu-id="994ac-130">结束与您的用户 ID，但 Skype 业务关联的会话将会继续在后台运行。</span><span class="sxs-lookup"><span data-stu-id="994ac-130">Ends the session associated with your user ID, but Skype for Business continues to run in the background.</span></span> <span data-ttu-id="994ac-131">注销时，登录窗口将会出现。</span><span class="sxs-lookup"><span data-stu-id="994ac-131">When you sign out, the sign-in window will appear.</span></span>  <br/> <span data-ttu-id="994ac-132">**提示：**退出来从计算机中删除您的登录 ID 和密码的记录后，请选择**删除我的登录信息**。</span><span class="sxs-lookup"><span data-stu-id="994ac-132">**Tip:** Select **Delete my sign-in information** when you sign out to remove the record of your logon ID and password from the computer.</span></span> <span data-ttu-id="994ac-133">这样做使支持人员可以更轻松地解决登录问题。</span><span class="sxs-lookup"><span data-stu-id="994ac-133">Doing this might make it easier for support people to troubleshoot sign-in issues.</span></span> <span data-ttu-id="994ac-134">还通过使未经授权的用户难以使用您的凭据登录来帮助确保您的登录信息更安全。</span><span class="sxs-lookup"><span data-stu-id="994ac-134">It can also help ensure your sign-in information is more secure by making it difficult for unauthorized users to log on with your credentials.</span></span> <br/> |<span data-ttu-id="994ac-135">在 Skype 业务主窗口中，选择**选项**按钮，然后选择**文件** > **签出**。</span><span class="sxs-lookup"><span data-stu-id="994ac-135">On the Skype for Business main window, select the **Options** button, then select **File** > **Sign Out**.</span></span>  <br/> |
|<span data-ttu-id="994ac-136">退出</span><span class="sxs-lookup"><span data-stu-id="994ac-136">Exit</span></span>  <br/> |<span data-ttu-id="994ac-137">业务会话结束您 Skype 和关闭您的计算机上的 Skype 业务。</span><span class="sxs-lookup"><span data-stu-id="994ac-137">Ends your Skype for Business session and shuts down Skype for Business on your computer.</span></span> <span data-ttu-id="994ac-138">退出后，如果您想要重新启动，请选择**开始** > **所有程序**> Skype 业务。</span><span class="sxs-lookup"><span data-stu-id="994ac-138">After exiting, if you want to restart, select **Start** > **All Programs** > Skype for Business.</span></span> <br/> |<span data-ttu-id="994ac-139">在 Skype 业务主窗口中，选择**选项**按钮，然后选择**文件** > **退出**。</span><span class="sxs-lookup"><span data-stu-id="994ac-139">On the Skype for Business main window, select the **Options** button, then select **File** > **Exit**.</span></span>  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a><span data-ttu-id="994ac-140">使用智能卡登录 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="994ac-140">Sign in to Skype for Business with a Smart Card</span></span>

<span data-ttu-id="994ac-141">一些组织现在使用多步骤登录过程（称为双重身份验证）来为其用户提高安全性。</span><span class="sxs-lookup"><span data-stu-id="994ac-141">Some organizations now use a multi-step sign-in process, called two-factor authentication, to increase security for their users.</span></span> <span data-ttu-id="994ac-142">如果希望您要使用此选项，您将需要"智能卡"登录 Skype 业务。</span><span class="sxs-lookup"><span data-stu-id="994ac-142">If you're expected to use this option, you'll need a "smart card" to sign in to Skype for Business.</span></span> <span data-ttu-id="994ac-143">智能卡可以是物理或虚拟：</span><span class="sxs-lookup"><span data-stu-id="994ac-143">Smart cards can be either physical or virtual:</span></span>
  
- <span data-ttu-id="994ac-144">**物理**关于信用卡的大小。</span><span class="sxs-lookup"><span data-stu-id="994ac-144">**Physical** About the size of a credit card.</span></span> <span data-ttu-id="994ac-145">登录时请将其插入到智能卡读卡器中。</span><span class="sxs-lookup"><span data-stu-id="994ac-145">You insert it into a smart card reader when you log in.</span></span>
    
- <span data-ttu-id="994ac-146">**虚拟**不是一个物理对象，但电子标识符获取写入您实质上可用于智能卡构建到您的计算机的计算机上的特殊芯片。</span><span class="sxs-lookup"><span data-stu-id="994ac-146">**Virtual** Not a physical object, but an electronic identifier that gets written to a special chip on your computer, which in essence builds the smart card into your computer.</span></span> <span data-ttu-id="994ac-147">只可使用与 Windows 8 计算机包含 TPM （可信平台模块） 芯片。</span><span class="sxs-lookup"><span data-stu-id="994ac-147">Available only for use with Windows 8 computers that contain the TPM (Trusted Platform Module) chip.</span></span>
    
### <a name="enroll-your-smart-card"></a><span data-ttu-id="994ac-148">注册智能卡</span><span class="sxs-lookup"><span data-stu-id="994ac-148">Enroll your smart card</span></span>

<span data-ttu-id="994ac-149">您可以使用智能卡登录之前，卡必须"登记"— — 您的用户凭据即具有被识别的卡。</span><span class="sxs-lookup"><span data-stu-id="994ac-149">Before you can sign in with a smart card, the card must be "enrolled"—that is, your user credentials have to be identified with the card.</span></span> <span data-ttu-id="994ac-150">不管是物理智能卡还是虚拟智能卡都是如此。</span><span class="sxs-lookup"><span data-stu-id="994ac-150">This is the case whether the card is physical or virtual.</span></span> <span data-ttu-id="994ac-151">此过程可能已被执行的业务服务器 2015年管理员为您 Skype。</span><span class="sxs-lookup"><span data-stu-id="994ac-151">This process may already been carried out by your Skype for Business Server 2015 administrator.</span></span> <span data-ttu-id="994ac-152">如果您不确定是否这样做了，请检查它们。</span><span class="sxs-lookup"><span data-stu-id="994ac-152">Check with them if you're not sure whether that has been done.</span></span>
  
> [!NOTE]
> <span data-ttu-id="994ac-153">因为每个虚拟智能卡是只与该设备上安装了，一个单独的卡将需要为每个您所使用的 Windows 8 计算机注册。</span><span class="sxs-lookup"><span data-stu-id="994ac-153">Since each virtual smart card is associated only with the device it's installed on, a separate card will need to be enrolled for each Windows 8 computer you use.</span></span> 
  
### <a name="to-manually-enroll-your-smart-card"></a><span data-ttu-id="994ac-154">手动注册智能卡</span><span class="sxs-lookup"><span data-stu-id="994ac-154">To manually enroll your smart card</span></span>

1. <span data-ttu-id="994ac-155">登录到您的计算机将是 Skype 的业务上。</span><span class="sxs-lookup"><span data-stu-id="994ac-155">Log on to the computer you'll be running Skype for Business on.</span></span>
    
2. <span data-ttu-id="994ac-156">使用 Internet Explorer，浏览到您的组织的证书颁发机构 Web 注册页。</span><span class="sxs-lookup"><span data-stu-id="994ac-156">Using Internet Explorer, browse to your organization's Certificate Authority Web Enrollment page.</span></span> 
    
    <span data-ttu-id="994ac-157">如果尚不具备，询问业务服务器管理员为您 Skype 此资源的 web 地址。</span><span class="sxs-lookup"><span data-stu-id="994ac-157">Ask your Skype for Business Server administrator for the web address of this resource if you don't already have it.</span></span> <span data-ttu-id="994ac-158">该 URL 将如下所示： https://MyCA。[yourcompanyname].com/certsrv。</span><span class="sxs-lookup"><span data-stu-id="994ac-158">The URL will look something like this: https://MyCA.[yourcompanyname].com/certsrv.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="994ac-159">如果您正在使用 Internet Explorer 10，您可能需要在兼容模式下查看该网站。</span><span class="sxs-lookup"><span data-stu-id="994ac-159">If you're using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span> 
  
3. <span data-ttu-id="994ac-160">当出现提示时登录到证书页上时，日志上使用您的域帐户 （而不是作为计算机的管理员）。</span><span class="sxs-lookup"><span data-stu-id="994ac-160">When you're prompted to log on to the certification page, log on using your domain account (rather than as administrator of your computer).</span></span>
    
4. <span data-ttu-id="994ac-161">在网站的“欢迎”页面上，选择“申请证书”****。</span><span class="sxs-lookup"><span data-stu-id="994ac-161">On the website Welcome Page, select **Request a certificate**.</span></span>
    
5. <span data-ttu-id="994ac-162">单击“高级申请”****。</span><span class="sxs-lookup"><span data-stu-id="994ac-162">Select **Advanced Request**.</span></span>
    
6. <span data-ttu-id="994ac-163">选择“创建并向此 CA 提交一个申请”****，然后单击“下一步”****。</span><span class="sxs-lookup"><span data-stu-id="994ac-163">Select **Create and submit a request to this CA**, then click **Next**.</span></span>
    
7. <span data-ttu-id="994ac-164">现在您将看到名为智能卡注册站的页面。</span><span class="sxs-lookup"><span data-stu-id="994ac-164">Now you'll see a page called Smart Card Enrollment Station.</span></span> <span data-ttu-id="994ac-165">批准申请以安装 ActiveX 控件，然后填写“高级证书申请”表单，如下所示：</span><span class="sxs-lookup"><span data-stu-id="994ac-165">Approve the request to install the ActiveX control, and then complete the Advanced Certificate Request form as follows:</span></span>
    
    <span data-ttu-id="994ac-166">a.</span><span class="sxs-lookup"><span data-stu-id="994ac-166">a.</span></span> <span data-ttu-id="994ac-167">从“证书模板”****下拉列表中选择“智能卡用户”****。</span><span class="sxs-lookup"><span data-stu-id="994ac-167">Select **Smartcard user** from the **Certificate Template** dropdown list.</span></span>
    
    <span data-ttu-id="994ac-168">b.</span><span class="sxs-lookup"><span data-stu-id="994ac-168">b.</span></span> <span data-ttu-id="994ac-169">选择“创建新密钥集”****。</span><span class="sxs-lookup"><span data-stu-id="994ac-169">Select **Create new key set**.</span></span>
    
    <span data-ttu-id="994ac-170">c.</span><span class="sxs-lookup"><span data-stu-id="994ac-170">c.</span></span> <span data-ttu-id="994ac-171">在智能卡标签上查找制造商信息，然后从“CSP”****下拉列表中选择该制造商。</span><span class="sxs-lookup"><span data-stu-id="994ac-171">Find the manufacturer information on the label of your smart card and select that manufacturer from the **CSP** dropdown list.</span></span>
    
    <span data-ttu-id="994ac-172">d.</span><span class="sxs-lookup"><span data-stu-id="994ac-172">d.</span></span> <span data-ttu-id="994ac-173">如果没有选中它，作为请求格式，选择**的 CSP** 。</span><span class="sxs-lookup"><span data-stu-id="994ac-173">Select **CSP** as the Request Format, if it's not already selected.</span></span>
    
    <span data-ttu-id="994ac-174">电子。</span><span class="sxs-lookup"><span data-stu-id="994ac-174">e.</span></span> <span data-ttu-id="994ac-175">如果尚未选中，请选择**sha1**哈希算法下拉列表中，从。</span><span class="sxs-lookup"><span data-stu-id="994ac-175">Select **sha1** from the Hash Algorithm dropdown list, if it's not already selected.</span></span>
    
    <span data-ttu-id="994ac-176">f。</span><span class="sxs-lookup"><span data-stu-id="994ac-176">f.</span></span> <span data-ttu-id="994ac-177">为您的证书的名称将识别，并单击**提交**。</span><span class="sxs-lookup"><span data-stu-id="994ac-177">Give your certificate a name you'll recognize, and click **Submit**.</span></span>
    
8. <span data-ttu-id="994ac-178">现在在连接到注册站的读卡器中插入空智能卡，然后单击“注册”****。</span><span class="sxs-lookup"><span data-stu-id="994ac-178">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>
    
9. <span data-ttu-id="994ac-179">出现提示时，输入您的个人标识号 (PIN)，然后单击“确定”****。</span><span class="sxs-lookup"><span data-stu-id="994ac-179">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="994ac-180">如果您的技术支持人员未向您提供用于注册智能卡的特殊 PIN，请使用默认智能卡 PIN 值 12345678。</span><span class="sxs-lookup"><span data-stu-id="994ac-180">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span> 
  
10. <span data-ttu-id="994ac-181">选择可在首次使用智能卡时强制用户（您）更改 PIN 的选项。</span><span class="sxs-lookup"><span data-stu-id="994ac-181">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>
    
11. <span data-ttu-id="994ac-182">现在在连接到注册站的读卡器中插入空智能卡，然后单击“注册”****。</span><span class="sxs-lookup"><span data-stu-id="994ac-182">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>
    
12. <span data-ttu-id="994ac-183">出现提示时，输入您的个人标识号 (PIN)，然后单击“确定”****。</span><span class="sxs-lookup"><span data-stu-id="994ac-183">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="994ac-184">如果您的技术支持人员未向您提供用于注册智能卡的特殊 PIN，请使用默认智能卡 PIN 值 12345678。</span><span class="sxs-lookup"><span data-stu-id="994ac-184">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span> 
  
13. <span data-ttu-id="994ac-185">选择可在首次使用智能卡时强制用户（您）更改 PIN 的选项。</span><span class="sxs-lookup"><span data-stu-id="994ac-185">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>
    
14. <span data-ttu-id="994ac-186">单击“确定”****以确认显示的证书包含您的信息。</span><span class="sxs-lookup"><span data-stu-id="994ac-186">Click **OK** to confirm that the certificate displayed has your information on it.</span></span>
    
15. <span data-ttu-id="994ac-187">看到已颁发证书的通知后，单击“安装此证书”****以完成注册过程。</span><span class="sxs-lookup"><span data-stu-id="994ac-187">Once you see the notice that the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>
    
### <a name="sign-in-to-skype-for-business-with-your-smart-card-credentials"></a><span data-ttu-id="994ac-188">使用智能卡凭据登录 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="994ac-188">Sign in to Skype for Business with your smart card credentials</span></span>

<span data-ttu-id="994ac-189">第一次使用您的智能卡之前，建议您单击 Skype 业务登录页上的**删除我的登录信息**。</span><span class="sxs-lookup"><span data-stu-id="994ac-189">Before you use your smart card for the first time, it's recommended that you click **Delete my sign-in info** on the Skype for Business sign-in page.</span></span> <span data-ttu-id="994ac-190">这样做可清除您的计算机上存储的任何登录凭据，并消除可能的错误源。</span><span class="sxs-lookup"><span data-stu-id="994ac-190">Doing this clears any sign-in credentials stored on your computer, and eliminates a possible source of error.</span></span>
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a><span data-ttu-id="994ac-191">使用智能卡凭据登录 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="994ac-191">To sign in to Skype for Business with your smart card credentials</span></span>

1. <span data-ttu-id="994ac-192">启动业务客户端的 Skype。</span><span class="sxs-lookup"><span data-stu-id="994ac-192">Start the Skype for Business client.</span></span>
    
2. <span data-ttu-id="994ac-193">在“登录”屏幕上，在“登录地址”****框中键入您的登录用户帐户名称，然后单击“登录”****。</span><span class="sxs-lookup"><span data-stu-id="994ac-193">On the Sign in screen, type your sign in user account name in the **Sign-in address** box, and then click **Sign In**.</span></span>
    
3. <span data-ttu-id="994ac-194">如果您正在使用虚拟智能卡，请跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="994ac-194">If you are using a virtual smart card, skip this step.</span></span>
    
    <span data-ttu-id="994ac-195">如果您正在使用物理智能卡，请在出现提示时在您的智能卡读卡器中插入智能卡，然后当检测到卡时单击“确定”****。</span><span class="sxs-lookup"><span data-stu-id="994ac-195">If you are using a physical smart card, insert the smart card into your smart card reader and prompted to do so, and then click **OK** when the card is detected.</span></span>
    
4. <span data-ttu-id="994ac-196">为您的智能卡键入 PIN 号码，然后单击“确定”****。</span><span class="sxs-lookup"><span data-stu-id="994ac-196">Type in the PIN number you for your smart card and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="994ac-197">如果您的支持人员未向您提供智能卡 PIN 号码，请使用默认值 12345678。</span><span class="sxs-lookup"><span data-stu-id="994ac-197">If you were not assigned a smart card PIN number by your support person, use the default value, which is 12345678.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="994ac-198">另请参阅</span><span class="sxs-lookup"><span data-stu-id="994ac-198">See also</span></span>

#### 

[<span data-ttu-id="994ac-199">管理在 Skype 的业务服务器 2015年的双因素身份验证</span><span class="sxs-lookup"><span data-stu-id="994ac-199">Manage two-factor authentication in Skype for Business Server 2015</span></span>](two-factor-authentication.md)
  
[<span data-ttu-id="994ac-200">在 Skype 为业务服务器 2015年配置两因素身份验证</span><span class="sxs-lookup"><span data-stu-id="994ac-200">Configure two-factor authentication in Skype for Business Server 2015</span></span>](configure.md)

