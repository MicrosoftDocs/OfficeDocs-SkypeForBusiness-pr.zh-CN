---
title: 用于双重身份验证与 Skype 的业务客户端和 Skype 业务服务器
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: 摘要： 业务服务器和 Skype for Business 使用与 Skype 的双重身份验证。
ms.openlocfilehash: 0c66808f22655e3f78a23930adc84dcbc31af6bb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894200"
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server"></a><span data-ttu-id="0d482-103">用于双重身份验证与 Skype 的业务客户端和 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="0d482-103">Use two-factor authentication with Skype for Business client and Skype for Business Server</span></span>
 
<span data-ttu-id="0d482-104">**摘要：** 使用双重身份验证 Skype 业务服务器和 Skype 的业务。</span><span class="sxs-lookup"><span data-stu-id="0d482-104">**Summary:** Use two-factor authentication with Skype for Business Server and Skype for Business.</span></span>
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a><span data-ttu-id="0d482-105">首次登录 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0d482-105">Sign in to Skype for Business for the first time</span></span>

<span data-ttu-id="0d482-106">安装 for Business 的 Skype 时，通常是自动配置您的登录信息。</span><span class="sxs-lookup"><span data-stu-id="0d482-106">Your sign-in information is usually configured automatically when Skype for Business is installed.</span></span> <span data-ttu-id="0d482-107">但第一次 Skype 用于业务，您可能需要手动启动客户端。</span><span class="sxs-lookup"><span data-stu-id="0d482-107">But the first time you use Skype for Business, you might have to manually start the client.</span></span>
  
### <a name="to-sign-in-for-the-first-time"></a><span data-ttu-id="0d482-108">首次登录</span><span class="sxs-lookup"><span data-stu-id="0d482-108">To sign in for the first time</span></span>

1. <span data-ttu-id="0d482-109">登录到贵组织的网络。</span><span class="sxs-lookup"><span data-stu-id="0d482-109">Log on to your organization's network.</span></span>
    
2. <span data-ttu-id="0d482-110">选择**启动** > **所有程序** > **for Business 的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="0d482-110">Select **Start** > **All Programs** > **Skype for Business**.</span></span>
    
    <span data-ttu-id="0d482-111">您应该会看到登录屏幕。</span><span class="sxs-lookup"><span data-stu-id="0d482-111">You should see the sign-in screen.</span></span>
    
    - <span data-ttu-id="0d482-112">如果登录地址框已经填充，请确认显示的地址是否正确。</span><span class="sxs-lookup"><span data-stu-id="0d482-112">If the sign-in address box is already filled in, confirm that the address shown is correct.</span></span>
    
    - <span data-ttu-id="0d482-113">如果不正确，或者框为空，输入登录地址 （这通常是您的电子邮件地址相同）。</span><span class="sxs-lookup"><span data-stu-id="0d482-113">If it's not correct, or if the box is empty, enter your sign-in address (this is usually the same as your email address).</span></span>
    
    - <span data-ttu-id="0d482-114">如果显示空密码框，请添加您的密码。</span><span class="sxs-lookup"><span data-stu-id="0d482-114">If an empty password box is displayed, add your password.</span></span>
    
3. <span data-ttu-id="0d482-115">选择“登录”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0d482-115">Select **Sign-in**.</span></span>
    
## <a name="sign-out-of-skype-for-business"></a><span data-ttu-id="0d482-116">注销 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0d482-116">Sign out of Skype for Business</span></span>

<span data-ttu-id="0d482-117">完成 for Business 使用 Skype 时，您可以关闭显示，登录到您的会话，或退出程序，所有从文件菜单。</span><span class="sxs-lookup"><span data-stu-id="0d482-117">When you're finished using Skype for Business, you can close the display, sign out of your session, or exit from the program, all from the File menu.</span></span> <span data-ttu-id="0d482-118">下表说明了这些选项之间的差异。</span><span class="sxs-lookup"><span data-stu-id="0d482-118">The following table explains the differences in the options.</span></span>
  
|<span data-ttu-id="0d482-119">**选项**</span><span class="sxs-lookup"><span data-stu-id="0d482-119">**Option**</span></span>|<span data-ttu-id="0d482-120">**执行的结果**</span><span class="sxs-lookup"><span data-stu-id="0d482-120">**What it does**</span></span>|<span data-ttu-id="0d482-121">**如何执行**</span><span class="sxs-lookup"><span data-stu-id="0d482-121">**How to perform it**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0d482-122">关闭</span><span class="sxs-lookup"><span data-stu-id="0d482-122">Close</span></span>  <br/> |<span data-ttu-id="0d482-123">关闭您显示，但允许 Skype 业务会话标识与您的用户 ID 继续运行。</span><span class="sxs-lookup"><span data-stu-id="0d482-123">Closes your display but lets the Skype for Business session identified with your user ID continue to run.</span></span> <span data-ttu-id="0d482-124">因此，您可以继续接收通知并与其他人互动。</span><span class="sxs-lookup"><span data-stu-id="0d482-124">This is so you can continue to get notifications and interact with others.</span></span> <br/> <br/> <span data-ttu-id="0d482-125">您可以通过单击任务栏上或在屏幕底部的通知区域上的业务图标 Skype 获取随时后显示。</span><span class="sxs-lookup"><span data-stu-id="0d482-125">You can get the display back at any time by clicking the Skype for Business icon on the taskbar or the notification area at the bottom of your screen.</span></span>  <br/> | <span data-ttu-id="0d482-126">在业务主窗口的 Skype，执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="0d482-126">On the Skype for Business main window, do one of the following:</span></span> <br/> <span data-ttu-id="0d482-127">1.选择**选项**按钮，然后选择**文件** > **关闭**。</span><span class="sxs-lookup"><span data-stu-id="0d482-127">1. Select the **Options** button, then select **File** > **Close**.</span></span>  <br/> <span data-ttu-id="0d482-128">2.在窗口的右上角，单击**关闭**按钮 (X)。</span><span class="sxs-lookup"><span data-stu-id="0d482-128">2. Click the **Close** button (X) in the upper-right corner of the window.</span></span> <br/> |
|<span data-ttu-id="0d482-129">注销</span><span class="sxs-lookup"><span data-stu-id="0d482-129">Sign out</span></span>  <br/> |<span data-ttu-id="0d482-130">结束与您的用户 ID 但 for Business 的 Skype 关联的会话继续在后台运行。</span><span class="sxs-lookup"><span data-stu-id="0d482-130">Ends the session associated with your user ID, but Skype for Business continues to run in the background.</span></span> <span data-ttu-id="0d482-131">注销时，登录窗口将会出现。</span><span class="sxs-lookup"><span data-stu-id="0d482-131">When you sign out, the sign-in window will appear.</span></span>  <br/> <span data-ttu-id="0d482-132">**提示：** 注销若要从计算机中删除您的登录 ID 和密码的记录时，请选择**删除我登录信息**。</span><span class="sxs-lookup"><span data-stu-id="0d482-132">**Tip:** Select **Delete my sign-in information** when you sign out to remove the record of your logon ID and password from the computer.</span></span> <span data-ttu-id="0d482-133">这样做使支持人员可以更轻松地解决登录问题。</span><span class="sxs-lookup"><span data-stu-id="0d482-133">Doing this might make it easier for support people to troubleshoot sign-in issues.</span></span> <span data-ttu-id="0d482-134">还通过使未经授权的用户难以使用您的凭据登录来帮助确保您的登录信息更安全。</span><span class="sxs-lookup"><span data-stu-id="0d482-134">It can also help ensure your sign-in information is more secure by making it difficult for unauthorized users to log on with your credentials.</span></span> <br/> |<span data-ttu-id="0d482-135">在业务主窗口的 Skype，选择**选项**按钮，然后选择**文件** > **注销**。</span><span class="sxs-lookup"><span data-stu-id="0d482-135">On the Skype for Business main window, select the **Options** button, then select **File** > **Sign Out**.</span></span>  <br/> |
|<span data-ttu-id="0d482-136">退出</span><span class="sxs-lookup"><span data-stu-id="0d482-136">Exit</span></span>  <br/> |<span data-ttu-id="0d482-137">业务会话结束您 Skype，并在计算机上关闭 for Business 的 Skype。</span><span class="sxs-lookup"><span data-stu-id="0d482-137">Ends your Skype for Business session and shuts down Skype for Business on your computer.</span></span> <span data-ttu-id="0d482-138">如果您想要重新启动，选择退出之后中,**启动** > **所有程序**> for Business 的 Skype。</span><span class="sxs-lookup"><span data-stu-id="0d482-138">After exiting, if you want to restart, select **Start** > **All Programs** > Skype for Business.</span></span> <br/> |<span data-ttu-id="0d482-139">在业务主窗口的 Skype，选择**选项**按钮，然后选择**文件** > **退出**。</span><span class="sxs-lookup"><span data-stu-id="0d482-139">On the Skype for Business main window, select the **Options** button, then select **File** > **Exit**.</span></span>  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a><span data-ttu-id="0d482-140">使用智能卡登录 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0d482-140">Sign in to Skype for Business with a Smart Card</span></span>

<span data-ttu-id="0d482-141">一些组织现在使用多步骤登录过程（称为双重身份验证）来为其用户提高安全性。</span><span class="sxs-lookup"><span data-stu-id="0d482-141">Some organizations now use a multi-step sign-in process, called two-factor authentication, to increase security for their users.</span></span> <span data-ttu-id="0d482-142">如果希望您要使用此选项，您将需要"智能卡"登录到 for Business 的 Skype。</span><span class="sxs-lookup"><span data-stu-id="0d482-142">If you're expected to use this option, you'll need a "smart card" to sign in to Skype for Business.</span></span> <span data-ttu-id="0d482-143">物理或虚拟，可以是智能卡：</span><span class="sxs-lookup"><span data-stu-id="0d482-143">Smart cards can be either physical or virtual:</span></span>
  
- <span data-ttu-id="0d482-144">**物理**有关信用卡号的大小。</span><span class="sxs-lookup"><span data-stu-id="0d482-144">**Physical** About the size of a credit card.</span></span> <span data-ttu-id="0d482-145">登录时请将其插入到智能卡读卡器中。</span><span class="sxs-lookup"><span data-stu-id="0d482-145">You insert it into a smart card reader when you log in.</span></span>
    
- <span data-ttu-id="0d482-146">**虚拟**不是物理对象，但在您的计算机，实质上用于智能卡构建到您的计算机获取写入到一个特殊芯片电子标识符。</span><span class="sxs-lookup"><span data-stu-id="0d482-146">**Virtual** Not a physical object, but an electronic identifier that gets written to a special chip on your computer, which in essence builds the smart card into your computer.</span></span> <span data-ttu-id="0d482-147">仅可与 Windows 8 的计算机包含 TPM （受信任平台模块） 芯片一起使用。</span><span class="sxs-lookup"><span data-stu-id="0d482-147">Available only for use with Windows 8 computers that contain the TPM (Trusted Platform Module) chip.</span></span>
    
### <a name="enroll-your-smart-card"></a><span data-ttu-id="0d482-148">注册智能卡</span><span class="sxs-lookup"><span data-stu-id="0d482-148">Enroll your smart card</span></span>

<span data-ttu-id="0d482-149">您可以使用智能卡登录之前，请在卡片必须"注册"— 即，您的用户凭据必须与卡标识。</span><span class="sxs-lookup"><span data-stu-id="0d482-149">Before you can sign in with a smart card, the card must be "enrolled"—that is, your user credentials have to be identified with the card.</span></span> <span data-ttu-id="0d482-150">不管是物理智能卡还是虚拟智能卡都是如此。</span><span class="sxs-lookup"><span data-stu-id="0d482-150">This is the case whether the card is physical or virtual.</span></span> <span data-ttu-id="0d482-151">此过程可能已被签出的企业服务器管理员将 Skype 执行。</span><span class="sxs-lookup"><span data-stu-id="0d482-151">This process may already been carried out by your Skype for Business Server administrator.</span></span> <span data-ttu-id="0d482-152">如果您不确定是否已完成的则检查与他们。</span><span class="sxs-lookup"><span data-stu-id="0d482-152">Check with them if you're not sure whether that has been done.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0d482-153">因为每个虚拟智能卡仅与设备相关联安装它的、 一张卡将需要您使用的每台 Windows 8 计算机的注册。</span><span class="sxs-lookup"><span data-stu-id="0d482-153">Since each virtual smart card is associated only with the device it's installed on, a separate card will need to be enrolled for each Windows 8 computer you use.</span></span> 
  
### <a name="to-manually-enroll-your-smart-card"></a><span data-ttu-id="0d482-154">手动注册智能卡</span><span class="sxs-lookup"><span data-stu-id="0d482-154">To manually enroll your smart card</span></span>

1. <span data-ttu-id="0d482-155">登录到您将在运行 for Business 的 Skype 的计算机上。</span><span class="sxs-lookup"><span data-stu-id="0d482-155">Log on to the computer you'll be running Skype for Business on.</span></span>
    
2. <span data-ttu-id="0d482-156">使用 Internet Explorer，浏览到您的组织的证书颁发机构 Web 注册页。</span><span class="sxs-lookup"><span data-stu-id="0d482-156">Using Internet Explorer, browse to your organization's Certificate Authority Web Enrollment page.</span></span> 
    
    <span data-ttu-id="0d482-157">如果没有已将您 Skype 业务服务器管理员寻求此资源的 web 地址。</span><span class="sxs-lookup"><span data-stu-id="0d482-157">Ask your Skype for Business Server administrator for the web address of this resource if you don't already have it.</span></span> <span data-ttu-id="0d482-158">URL 将如下所示： https://MyCA。[yourcompanyname].com/certsrv。</span><span class="sxs-lookup"><span data-stu-id="0d482-158">The URL will look something like this: https://MyCA.[yourcompanyname].com/certsrv.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0d482-159">如果您正在使用 Internet Explorer 10，您可能需要在兼容模式下查看该网站。</span><span class="sxs-lookup"><span data-stu-id="0d482-159">If you're using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span> 
  
3. <span data-ttu-id="0d482-160">当提示您登录到证书页上时，记录使用您的域帐户 （而不是作为您的计算机的管理员）。</span><span class="sxs-lookup"><span data-stu-id="0d482-160">When you're prompted to log on to the certification page, log on using your domain account (rather than as administrator of your computer).</span></span>
    
4. <span data-ttu-id="0d482-161">在网站的“欢迎”页面上，选择“申请证书”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0d482-161">On the website Welcome Page, select **Request a certificate**.</span></span>
    
5. <span data-ttu-id="0d482-162">单击“高级申请”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0d482-162">Select **Advanced Request**.</span></span>
    
6. <span data-ttu-id="0d482-163">选择“创建并向此 CA 提交一个申请”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0d482-163">Select **Create and submit a request to this CA**, then click **Next**.</span></span>
    
7. <span data-ttu-id="0d482-164">现在，您将看到调用智能卡注册站页面。</span><span class="sxs-lookup"><span data-stu-id="0d482-164">Now you'll see a page called Smart Card Enrollment Station.</span></span> <span data-ttu-id="0d482-165">批准申请以安装 ActiveX 控件，然后填写“高级证书申请”表单，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0d482-165">Approve the request to install the ActiveX control, and then complete the Advanced Certificate Request form as follows:</span></span>
    
    <span data-ttu-id="0d482-166">a.</span><span class="sxs-lookup"><span data-stu-id="0d482-166">a.</span></span> <span data-ttu-id="0d482-167">从“证书模板”\*\*\*\* 下拉列表中选择“智能卡用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0d482-167">Select **Smartcard user** from the **Certificate Template** dropdown list.</span></span>
    
    <span data-ttu-id="0d482-168">b.</span><span class="sxs-lookup"><span data-stu-id="0d482-168">b.</span></span> <span data-ttu-id="0d482-169">选择“创建新密钥集”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0d482-169">Select **Create new key set**.</span></span>
    
    <span data-ttu-id="0d482-170">c.</span><span class="sxs-lookup"><span data-stu-id="0d482-170">c.</span></span> <span data-ttu-id="0d482-171">在智能卡标签上查找制造商信息，然后从“CSP”\*\*\*\* 下拉列表中选择该制造商。</span><span class="sxs-lookup"><span data-stu-id="0d482-171">Find the manufacturer information on the label of your smart card and select that manufacturer from the **CSP** dropdown list.</span></span>
    
    <span data-ttu-id="0d482-172">d.</span><span class="sxs-lookup"><span data-stu-id="0d482-172">d.</span></span> <span data-ttu-id="0d482-173">选择**CSP**作为请求格式，如果尚未选择它。</span><span class="sxs-lookup"><span data-stu-id="0d482-173">Select **CSP** as the Request Format, if it's not already selected.</span></span>
    
    <span data-ttu-id="0d482-174">e。</span><span class="sxs-lookup"><span data-stu-id="0d482-174">e.</span></span> <span data-ttu-id="0d482-175">从哈希算法下拉列表中，选择**sha1** ，如果尚未选择它。</span><span class="sxs-lookup"><span data-stu-id="0d482-175">Select **sha1** from the Hash Algorithm dropdown list, if it's not already selected.</span></span>
    
    <span data-ttu-id="0d482-176">f。</span><span class="sxs-lookup"><span data-stu-id="0d482-176">f.</span></span> <span data-ttu-id="0d482-177">为您的证书的名称将识别，并单击**提交**。</span><span class="sxs-lookup"><span data-stu-id="0d482-177">Give your certificate a name you'll recognize, and click **Submit**.</span></span>
    
8. <span data-ttu-id="0d482-178">现在在连接到注册站的读卡器中插入空智能卡，然后单击“注册”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0d482-178">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>
    
9. <span data-ttu-id="0d482-179">出现提示时，输入您的个人标识号 (PIN)，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0d482-179">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0d482-180">如果您的技术支持人员未向您提供用于注册智能卡的特殊 PIN，请使用默认智能卡 PIN 值 12345678。</span><span class="sxs-lookup"><span data-stu-id="0d482-180">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span> 
  
10. <span data-ttu-id="0d482-181">选择可在首次使用智能卡时强制用户（您）更改 PIN 的选项。</span><span class="sxs-lookup"><span data-stu-id="0d482-181">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>
    
11. <span data-ttu-id="0d482-182">现在在连接到注册站的读卡器中插入空智能卡，然后单击“注册”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0d482-182">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>
    
12. <span data-ttu-id="0d482-183">出现提示时，输入您的个人标识号 (PIN)，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0d482-183">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0d482-184">如果您的技术支持人员未向您提供用于注册智能卡的特殊 PIN，请使用默认智能卡 PIN 值 12345678。</span><span class="sxs-lookup"><span data-stu-id="0d482-184">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span> 
  
13. <span data-ttu-id="0d482-185">选择可在首次使用智能卡时强制用户（您）更改 PIN 的选项。</span><span class="sxs-lookup"><span data-stu-id="0d482-185">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>
    
14. <span data-ttu-id="0d482-186">单击“确定”\*\*\*\* 以确认显示的证书包含您的信息。</span><span class="sxs-lookup"><span data-stu-id="0d482-186">Click **OK** to confirm that the certificate displayed has your information on it.</span></span>
    
15. <span data-ttu-id="0d482-187">看到已颁发证书的通知后，单击“安装此证书”\*\*\*\* 以完成注册过程。</span><span class="sxs-lookup"><span data-stu-id="0d482-187">Once you see the notice that the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>
    
### <a name="sign-in-to-skype-for-business-with-your-smart-card-credentials"></a><span data-ttu-id="0d482-188">使用智能卡凭据登录 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0d482-188">Sign in to Skype for Business with your smart card credentials</span></span>

<span data-ttu-id="0d482-189">在首次使用您的智能卡之前，建议您单击 Skype 业务登录页上的**删除我登录的信息**。</span><span class="sxs-lookup"><span data-stu-id="0d482-189">Before you use your smart card for the first time, it's recommended that you click **Delete my sign-in info** on the Skype for Business sign-in page.</span></span> <span data-ttu-id="0d482-190">这样做可清除您的计算机上存储的任何登录凭据，并消除可能的错误源。</span><span class="sxs-lookup"><span data-stu-id="0d482-190">Doing this clears any sign-in credentials stored on your computer, and eliminates a possible source of error.</span></span>
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a><span data-ttu-id="0d482-191">使用智能卡凭据登录 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0d482-191">To sign in to Skype for Business with your smart card credentials</span></span>

1. <span data-ttu-id="0d482-192">启动业务客户端 Skype。</span><span class="sxs-lookup"><span data-stu-id="0d482-192">Start the Skype for Business client.</span></span>
    
2. <span data-ttu-id="0d482-193">在“登录”屏幕上，在“登录地址”\*\*\*\* 框中键入您的登录用户帐户名称，然后单击“登录”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0d482-193">On the Sign in screen, type your sign in user account name in the **Sign-in address** box, and then click **Sign In**.</span></span>
    
3. <span data-ttu-id="0d482-194">如果您正在使用虚拟智能卡，请跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="0d482-194">If you are using a virtual smart card, skip this step.</span></span>
    
    <span data-ttu-id="0d482-195">如果您正在使用物理智能卡，请在出现提示时在您的智能卡读卡器中插入智能卡，然后当检测到卡时单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0d482-195">If you are using a physical smart card, insert the smart card into your smart card reader and prompted to do so, and then click **OK** when the card is detected.</span></span>
    
4. <span data-ttu-id="0d482-196">为您的智能卡键入 PIN 号码，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0d482-196">Type in the PIN number you for your smart card and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0d482-197">如果您的支持人员未向您提供智能卡 PIN 号码，请使用默认值 12345678。</span><span class="sxs-lookup"><span data-stu-id="0d482-197">If you were not assigned a smart card PIN number by your support person, use the default value, which is 12345678.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0d482-198">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d482-198">See also</span></span>

[<span data-ttu-id="0d482-199">管理 Skype 中的业务服务器的双重身份验证</span><span class="sxs-lookup"><span data-stu-id="0d482-199">Manage two-factor authentication in Skype for Business Server</span></span>](two-factor-authentication.md)
  
[<span data-ttu-id="0d482-200">在 Skype for Business Server 中配置双重身份验证</span><span class="sxs-lookup"><span data-stu-id="0d482-200">Configure two-factor authentication in Skype for Business Server</span></span>](configure-two-factor.md)
