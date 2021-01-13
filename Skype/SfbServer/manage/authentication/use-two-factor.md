---
title: 将双重身份验证与 Skype for Business 客户端和 Skype for Business Server 一同使用
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: 摘要：对 Skype for Business Server 和 Skype for Business 使用双重身份验证。
ms.openlocfilehash: 72ec3570d632eecefd28ebfd0aa50eb70c54ff99
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806533"
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server"></a><span data-ttu-id="0889c-103">将双重身份验证与 Skype for Business 客户端和 Skype for Business Server 一同使用</span><span class="sxs-lookup"><span data-stu-id="0889c-103">Use two-factor authentication with Skype for Business client and Skype for Business Server</span></span>
 
<span data-ttu-id="0889c-104">**摘要：** 将双重身份验证与 Skype for Business Server 和 Skype for Business 一同使用。</span><span class="sxs-lookup"><span data-stu-id="0889c-104">**Summary:** Use two-factor authentication with Skype for Business Server and Skype for Business.</span></span>
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a><span data-ttu-id="0889c-105">首次登录 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0889c-105">Sign in to Skype for Business for the first time</span></span>

<span data-ttu-id="0889c-106">安装 Skype for Business 时，通常会自动配置登录信息。</span><span class="sxs-lookup"><span data-stu-id="0889c-106">Your sign-in information is usually configured automatically when Skype for Business is installed.</span></span> <span data-ttu-id="0889c-107">但是，第一次使用 Skype for Business 时，可能需要手动启动客户端。</span><span class="sxs-lookup"><span data-stu-id="0889c-107">But the first time you use Skype for Business, you might have to manually start the client.</span></span>
  
### <a name="to-sign-in-for-the-first-time"></a><span data-ttu-id="0889c-108">首次登录</span><span class="sxs-lookup"><span data-stu-id="0889c-108">To sign in for the first time</span></span>

1. <span data-ttu-id="0889c-109">登录到组织的网络。</span><span class="sxs-lookup"><span data-stu-id="0889c-109">Log on to your organization's network.</span></span>
    
2. <span data-ttu-id="0889c-110">选择 **"**  >  **启动 Skype** for  >  **Business 的所有程序"。**</span><span class="sxs-lookup"><span data-stu-id="0889c-110">Select **Start** > **All Programs** > **Skype for Business**.</span></span>
    
    <span data-ttu-id="0889c-111">你应该会看到登录屏幕。</span><span class="sxs-lookup"><span data-stu-id="0889c-111">You should see the sign-in screen.</span></span>
    
    - <span data-ttu-id="0889c-112">如果已填写登录地址框，请确认显示的地址正确。</span><span class="sxs-lookup"><span data-stu-id="0889c-112">If the sign-in address box is already filled in, confirm that the address shown is correct.</span></span>
    
    - <span data-ttu-id="0889c-113">如果不正确，或者框为空，请输入登录地址 (该地址通常与电子邮件地址相同) 。</span><span class="sxs-lookup"><span data-stu-id="0889c-113">If it's not correct, or if the box is empty, enter your sign-in address (this is usually the same as your email address).</span></span>
    
    - <span data-ttu-id="0889c-114">如果显示空密码框，请添加密码。</span><span class="sxs-lookup"><span data-stu-id="0889c-114">If an empty password box is displayed, add your password.</span></span>
    
3. <span data-ttu-id="0889c-115">选择 **"登录"。**</span><span class="sxs-lookup"><span data-stu-id="0889c-115">Select **Sign-in**.</span></span>
    
## <a name="sign-out-of-skype-for-business"></a><span data-ttu-id="0889c-116">注销 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0889c-116">Sign out of Skype for Business</span></span>

<span data-ttu-id="0889c-117">使用完 Skype for Business 后，你可以关闭屏幕、注销会话或退出程序，所有这些都来自"文件"菜单。</span><span class="sxs-lookup"><span data-stu-id="0889c-117">When you're finished using Skype for Business, you can close the display, sign out of your session, or exit from the program, all from the File menu.</span></span> <span data-ttu-id="0889c-118">下表说明了这些选项之间的差异。</span><span class="sxs-lookup"><span data-stu-id="0889c-118">The following table explains the differences in the options.</span></span>
  
|<span data-ttu-id="0889c-119">**选项**</span><span class="sxs-lookup"><span data-stu-id="0889c-119">**Option**</span></span>|<span data-ttu-id="0889c-120">**功能**</span><span class="sxs-lookup"><span data-stu-id="0889c-120">**What it does**</span></span>|<span data-ttu-id="0889c-121">**如何执行**</span><span class="sxs-lookup"><span data-stu-id="0889c-121">**How to perform it**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0889c-122">关闭</span><span class="sxs-lookup"><span data-stu-id="0889c-122">Close</span></span>  <br/> |<span data-ttu-id="0889c-123">关闭你的屏幕，但允许使用你的用户 ID 标识的 Skype for Business 会话继续运行。</span><span class="sxs-lookup"><span data-stu-id="0889c-123">Closes your display but lets the Skype for Business session identified with your user ID continue to run.</span></span> <span data-ttu-id="0889c-124">这样，你可以继续获取通知并与他人交互。</span><span class="sxs-lookup"><span data-stu-id="0889c-124">This is so you can continue to get notifications and interact with others.</span></span> <br/> <br/> <span data-ttu-id="0889c-125">你随时都可以通过单击任务栏上的 Skype for Business 图标或屏幕底部的通知区域来恢复显示。</span><span class="sxs-lookup"><span data-stu-id="0889c-125">You can get the display back at any time by clicking the Skype for Business icon on the taskbar or the notification area at the bottom of your screen.</span></span>  <br/> | <span data-ttu-id="0889c-126">在 Skype for Business 主窗口中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="0889c-126">On the Skype for Business main window, do one of the following:</span></span> <br/> <span data-ttu-id="0889c-127">1. 选择 **"选项"** 按钮，然后选择"**文件**  >  **关闭"。**</span><span class="sxs-lookup"><span data-stu-id="0889c-127">1. Select the **Options** button, then select **File** > **Close**.</span></span>  <br/> <span data-ttu-id="0889c-128">2. 单击窗口右上角 (X) 的"关闭"按钮。</span><span class="sxs-lookup"><span data-stu-id="0889c-128">2. Click the **Close** button (X) in the upper-right corner of the window.</span></span> <br/> |
|<span data-ttu-id="0889c-129">注销</span><span class="sxs-lookup"><span data-stu-id="0889c-129">Sign out</span></span>  <br/> |<span data-ttu-id="0889c-130">结束与用户 ID 关联的会话，但 Skype for Business 继续在后台运行。</span><span class="sxs-lookup"><span data-stu-id="0889c-130">Ends the session associated with your user ID, but Skype for Business continues to run in the background.</span></span> <span data-ttu-id="0889c-131">注销时，将显示登录窗口。</span><span class="sxs-lookup"><span data-stu-id="0889c-131">When you sign out, the sign-in window will appear.</span></span>  <br/> <span data-ttu-id="0889c-132">**提示：\*\*\*\*Select Delete my sign-in information** when you sign out to remove the record of your logon ID and password from the computer.</span><span class="sxs-lookup"><span data-stu-id="0889c-132">**Tip:** Select **Delete my sign-in information** when you sign out to remove the record of your logon ID and password from the computer.</span></span> <span data-ttu-id="0889c-133">这样做可能会让支持人员更轻松地排查登录问题。</span><span class="sxs-lookup"><span data-stu-id="0889c-133">Doing this might make it easier for support people to troubleshoot sign-in issues.</span></span> <span data-ttu-id="0889c-134">它还可以帮助确保登录信息更加安全，因为未经授权的用户很难使用凭据登录。</span><span class="sxs-lookup"><span data-stu-id="0889c-134">It can also help ensure your sign-in information is more secure by making it difficult for unauthorized users to log on with your credentials.</span></span> <br/> |<span data-ttu-id="0889c-135">在 Skype for Business 主窗口中，选择 **"选项"** 按钮，然后选择"**文件**  >  **注销"。**</span><span class="sxs-lookup"><span data-stu-id="0889c-135">On the Skype for Business main window, select the **Options** button, then select **File** > **Sign Out**.</span></span>  <br/> |
|<span data-ttu-id="0889c-136">Exit</span><span class="sxs-lookup"><span data-stu-id="0889c-136">Exit</span></span>  <br/> |<span data-ttu-id="0889c-137">结束你的 Skype for Business 会话并关闭你的计算机上 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="0889c-137">Ends your Skype for Business session and shuts down Skype for Business on your computer.</span></span> <span data-ttu-id="0889c-138">退出后，如果要重新启动，**请选择"启动** Skype for Business >  >  所有程序"。</span><span class="sxs-lookup"><span data-stu-id="0889c-138">After exiting, if you want to restart, select **Start** > **All Programs** > Skype for Business.</span></span> <br/> |<span data-ttu-id="0889c-139">在 Skype for Business 主窗口中，选择"选项 **"按钮，** 然后选择"**文件**  >  **退出"。**</span><span class="sxs-lookup"><span data-stu-id="0889c-139">On the Skype for Business main window, select the **Options** button, then select **File** > **Exit**.</span></span>  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a><span data-ttu-id="0889c-140">使用智能卡登录 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0889c-140">Sign in to Skype for Business with a Smart Card</span></span>

<span data-ttu-id="0889c-141">一些组织现在使用多步骤登录过程（称为双重身份验证）来增强用户的安全性。</span><span class="sxs-lookup"><span data-stu-id="0889c-141">Some organizations now use a multi-step sign-in process, called two-factor authentication, to increase security for their users.</span></span> <span data-ttu-id="0889c-142">如果你希望使用此选项，则需要"智能卡"登录 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="0889c-142">If you're expected to use this option, you'll need a "smart card" to sign in to Skype for Business.</span></span> <span data-ttu-id="0889c-143">智能卡可以是物理智能卡，也可以虚拟智能卡：</span><span class="sxs-lookup"><span data-stu-id="0889c-143">Smart cards can be either physical or virtual:</span></span>
  
- <span data-ttu-id="0889c-144">**物理** 关于信用卡的大小。</span><span class="sxs-lookup"><span data-stu-id="0889c-144">**Physical** About the size of a credit card.</span></span> <span data-ttu-id="0889c-145">登录时将其插入智能卡读卡器。</span><span class="sxs-lookup"><span data-stu-id="0889c-145">You insert it into a smart card reader when you log in.</span></span>
    
- <span data-ttu-id="0889c-146">**虚拟** 不是物理对象，而是写入计算机上特殊芯片的电子标识符，这本质上将智能卡生成到计算机中。</span><span class="sxs-lookup"><span data-stu-id="0889c-146">**Virtual** Not a physical object, but an electronic identifier that gets written to a special chip on your computer, which in essence builds the smart card into your computer.</span></span> <span data-ttu-id="0889c-147">仅适用于包含 TPM 和受信任的平台模块或芯片 (Windows 8) 。</span><span class="sxs-lookup"><span data-stu-id="0889c-147">Available only for use with Windows 8 computers that contain the TPM (Trusted Platform Module) chip.</span></span>
    
### <a name="enroll-your-smart-card"></a><span data-ttu-id="0889c-148">注册智能卡</span><span class="sxs-lookup"><span data-stu-id="0889c-148">Enroll your smart card</span></span>

<span data-ttu-id="0889c-149">在可以使用智能卡登录之前，该卡必须"已注册"，即用户凭据必须用卡标识。</span><span class="sxs-lookup"><span data-stu-id="0889c-149">Before you can sign in with a smart card, the card must be "enrolled"—that is, your user credentials have to be identified with the card.</span></span> <span data-ttu-id="0889c-150">这是卡片是物理卡还是虚拟卡的情况。</span><span class="sxs-lookup"><span data-stu-id="0889c-150">This is the case whether the card is physical or virtual.</span></span> <span data-ttu-id="0889c-151">此过程可能已经由 Skype for Business Server 管理员执行。</span><span class="sxs-lookup"><span data-stu-id="0889c-151">This process may already been carried out by your Skype for Business Server administrator.</span></span> <span data-ttu-id="0889c-152">如果不确定是否已完成，请与他们核实。</span><span class="sxs-lookup"><span data-stu-id="0889c-152">Check with them if you're not sure whether that has been done.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0889c-153">由于每个虚拟智能卡仅与其安装的设备相关联，因此需要为使用的每个 Windows 8 计算机注册单独的卡。</span><span class="sxs-lookup"><span data-stu-id="0889c-153">Since each virtual smart card is associated only with the device it's installed on, a separate card will need to be enrolled for each Windows 8 computer you use.</span></span> 
  
### <a name="to-manually-enroll-your-smart-card"></a><span data-ttu-id="0889c-154">手动注册智能卡</span><span class="sxs-lookup"><span data-stu-id="0889c-154">To manually enroll your smart card</span></span>

1. <span data-ttu-id="0889c-155">登录到将运行 Skype for Business 的计算机。</span><span class="sxs-lookup"><span data-stu-id="0889c-155">Log on to the computer you'll be running Skype for Business on.</span></span>
    
2. <span data-ttu-id="0889c-156">使用Internet Explorer，浏览到组织的"证书颁发机构 Web 注册"页。</span><span class="sxs-lookup"><span data-stu-id="0889c-156">Using Internet Explorer, browse to your organization's Certificate Authority Web Enrollment page.</span></span> 
    
    <span data-ttu-id="0889c-157">如果尚未提供此资源的 Web 地址，请询问 Skype for Business Server 管理员。</span><span class="sxs-lookup"><span data-stu-id="0889c-157">Ask your Skype for Business Server administrator for the web address of this resource if you don't already have it.</span></span> <span data-ttu-id="0889c-158">URL 将如下所示 https://MyCA ：.[yourcompanyname].com/certsrv。</span><span class="sxs-lookup"><span data-stu-id="0889c-158">The URL will look something like this: https://MyCA.[yourcompanyname].com/certsrv.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0889c-159">如果你使用的是Internet Explorer 10，可能需要在兼容模式下查看此网站。</span><span class="sxs-lookup"><span data-stu-id="0889c-159">If you're using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span> 
  
3. <span data-ttu-id="0889c-160">当系统提示你登录认证页面时，使用域帐户登录 (而不是以计算机管理员) 。</span><span class="sxs-lookup"><span data-stu-id="0889c-160">When you're prompted to log on to the certification page, log on using your domain account (rather than as administrator of your computer).</span></span>
    
4. <span data-ttu-id="0889c-161">在网站欢迎页面上，选择 **"请求证书"。**</span><span class="sxs-lookup"><span data-stu-id="0889c-161">On the website Welcome Page, select **Request a certificate**.</span></span>
    
5. <span data-ttu-id="0889c-162">选择 **"高级请求"。**</span><span class="sxs-lookup"><span data-stu-id="0889c-162">Select **Advanced Request**.</span></span>
    
6. <span data-ttu-id="0889c-163">选择 **"创建"，然后向此 CA** 提交请求，然后单击"下 **一步"。**</span><span class="sxs-lookup"><span data-stu-id="0889c-163">Select **Create and submit a request to this CA**, then click **Next**.</span></span>
    
7. <span data-ttu-id="0889c-164">现在，你将看到一个称为"智能卡注册站"的页面。</span><span class="sxs-lookup"><span data-stu-id="0889c-164">Now you'll see a page called Smart Card Enrollment Station.</span></span> <span data-ttu-id="0889c-165">批准安装证书ActiveX，然后完成"高级证书申请"表单，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0889c-165">Approve the request to install the ActiveX control, and then complete the Advanced Certificate Request form as follows:</span></span>
    
    <span data-ttu-id="0889c-166">a.</span><span class="sxs-lookup"><span data-stu-id="0889c-166">a.</span></span> <span data-ttu-id="0889c-167">从 **"证书模板** "下拉列表 **中选择** 智能卡用户。</span><span class="sxs-lookup"><span data-stu-id="0889c-167">Select **Smartcard user** from the **Certificate Template** dropdown list.</span></span>
    
    <span data-ttu-id="0889c-168">b.</span><span class="sxs-lookup"><span data-stu-id="0889c-168">b.</span></span> <span data-ttu-id="0889c-169">选择 **"新建密钥集"。**</span><span class="sxs-lookup"><span data-stu-id="0889c-169">Select **Create new key set**.</span></span>
    
    <span data-ttu-id="0889c-170">c.</span><span class="sxs-lookup"><span data-stu-id="0889c-170">c.</span></span> <span data-ttu-id="0889c-171">在智能卡标签上查找制造商信息，然后从 **云** 解决方案提供商下拉列表中选择该制造商。</span><span class="sxs-lookup"><span data-stu-id="0889c-171">Find the manufacturer information on the label of your smart card and select that manufacturer from the **CSP** dropdown list.</span></span>
    
    <span data-ttu-id="0889c-172">d.</span><span class="sxs-lookup"><span data-stu-id="0889c-172">d.</span></span> <span data-ttu-id="0889c-173">选择 **CSP** 作为请求格式（如果尚未选择）。</span><span class="sxs-lookup"><span data-stu-id="0889c-173">Select **CSP** as the Request Format, if it's not already selected.</span></span>
    
    <span data-ttu-id="0889c-174">e.</span><span class="sxs-lookup"><span data-stu-id="0889c-174">e.</span></span> <span data-ttu-id="0889c-175">从"哈希算法"下拉列表中选择 **sha1（** 如果尚未选择）。</span><span class="sxs-lookup"><span data-stu-id="0889c-175">Select **sha1** from the Hash Algorithm dropdown list, if it's not already selected.</span></span>
    
    <span data-ttu-id="0889c-176">f.</span><span class="sxs-lookup"><span data-stu-id="0889c-176">f.</span></span> <span data-ttu-id="0889c-177">为证书指定你将识别的名称，然后单击"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="0889c-177">Give your certificate a name you'll recognize, and click **Submit**.</span></span>
    
8. <span data-ttu-id="0889c-178">现在，将空白智能卡插入连接到注册站的读卡器中，然后单击"注册 **"。**</span><span class="sxs-lookup"><span data-stu-id="0889c-178">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>
    
9. <span data-ttu-id="0889c-179">当系统提示时，在 PIN (输入) ，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="0889c-179">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0889c-180">如果技术支持人员未提供用于注册智能卡的特殊 PIN，请使用默认的智能卡 PIN 值，即 12345678。</span><span class="sxs-lookup"><span data-stu-id="0889c-180">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span> 
  
10. <span data-ttu-id="0889c-181">选择强制用户更改 () 第一次使用智能卡时更改 PIN。</span><span class="sxs-lookup"><span data-stu-id="0889c-181">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>
    
11. <span data-ttu-id="0889c-182">现在，将空白智能卡插入连接到注册站的读卡器中，然后单击"注册 **"。**</span><span class="sxs-lookup"><span data-stu-id="0889c-182">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>
    
12. <span data-ttu-id="0889c-183">当系统提示时，在 PIN (输入) ，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="0889c-183">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0889c-184">如果技术支持人员未提供用于注册智能卡的特殊 PIN，请使用默认的智能卡 PIN 值，即 12345678。</span><span class="sxs-lookup"><span data-stu-id="0889c-184">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span> 
  
13. <span data-ttu-id="0889c-185">选择强制用户更改 () 第一次使用智能卡时更改 PIN。</span><span class="sxs-lookup"><span data-stu-id="0889c-185">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>
    
14. <span data-ttu-id="0889c-186">单击 **"** 确定"确认显示的证书上包含你的信息。</span><span class="sxs-lookup"><span data-stu-id="0889c-186">Click **OK** to confirm that the certificate displayed has your information on it.</span></span>
    
15. <span data-ttu-id="0889c-187">在看到证书颁发通知后，单击"安装 **此证书** "以完成注册过程。</span><span class="sxs-lookup"><span data-stu-id="0889c-187">Once you see the notice that the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>
    
### <a name="sign-in-to-skype-for-business-with-your-smart-card-credentials"></a><span data-ttu-id="0889c-188">使用智能卡凭据登录 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0889c-188">Sign in to Skype for Business with your smart card credentials</span></span>

<span data-ttu-id="0889c-189">首次使用智能卡之前，建议在 Skype for Business 登录页面上单击"删除我的登录信息"。</span><span class="sxs-lookup"><span data-stu-id="0889c-189">Before you use your smart card for the first time, it's recommended that you click **Delete my sign-in info** on the Skype for Business sign-in page.</span></span> <span data-ttu-id="0889c-190">这样做可清除存储在您的计算机上的任何登录凭据，并消除可能的错误源。</span><span class="sxs-lookup"><span data-stu-id="0889c-190">Doing this clears any sign-in credentials stored on your computer, and eliminates a possible source of error.</span></span>
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a><span data-ttu-id="0889c-191">使用智能卡凭据登录 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0889c-191">To sign in to Skype for Business with your smart card credentials</span></span>

1. <span data-ttu-id="0889c-192">启动 Skype for Business 客户端。</span><span class="sxs-lookup"><span data-stu-id="0889c-192">Start the Skype for Business client.</span></span>
    
2. <span data-ttu-id="0889c-193">在"登录"屏幕上，在登录地址框中键入登录用户帐户名，然后单击 **"登录"。**</span><span class="sxs-lookup"><span data-stu-id="0889c-193">On the Sign in screen, type your sign in user account name in the **Sign-in address** box, and then click **Sign In**.</span></span>
    
3. <span data-ttu-id="0889c-194">如果使用的是虚拟智能卡，请跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="0889c-194">If you are using a virtual smart card, skip this step.</span></span>
    
    <span data-ttu-id="0889c-195">如果使用物理智能卡，请将智能卡插入智能卡读卡器，并提示你这样做，然后在检测到智能卡时单击"确定"。 </span><span class="sxs-lookup"><span data-stu-id="0889c-195">If you are using a physical smart card, insert the smart card into your smart card reader and prompted to do so, and then click **OK** when the card is detected.</span></span>
    
4. <span data-ttu-id="0889c-196">键入智能卡的 PIN 号，然后单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="0889c-196">Type in the PIN number you for your smart card and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0889c-197">如果支持人员未分配智能卡 PIN 号码，请使用默认值 12345678。</span><span class="sxs-lookup"><span data-stu-id="0889c-197">If you were not assigned a smart card PIN number by your support person, use the default value, which is 12345678.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0889c-198">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0889c-198">See also</span></span>

[<span data-ttu-id="0889c-199">在 Skype for Business Server 中管理双重身份验证</span><span class="sxs-lookup"><span data-stu-id="0889c-199">Manage two-factor authentication in Skype for Business Server</span></span>](two-factor-authentication.md)
  
[<span data-ttu-id="0889c-200">在 Skype for Business Server 中配置双重身份验证</span><span class="sxs-lookup"><span data-stu-id="0889c-200">Configure two-factor authentication in Skype for Business Server</span></span>](configure-two-factor.md)
