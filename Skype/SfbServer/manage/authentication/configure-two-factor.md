---
title: 在 Skype for Business Server 中配置双重身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: 摘要： 在 Skype for Business Server 配置双重身份验证。
ms.openlocfilehash: d328f9b60c413c58f7f0ca90a922794fa9f60a4d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919652"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="ee134-103">在 Skype for Business Server 中配置双重身份验证</span><span class="sxs-lookup"><span data-stu-id="ee134-103">Configure two-factor authentication in Skype for Business Server</span></span>

<span data-ttu-id="ee134-104">**摘要：** 在 Skype for Business Server 配置双重身份验证。</span><span class="sxs-lookup"><span data-stu-id="ee134-104">**Summary:** Configure two-factor authentication in Skype for Business Server.</span></span>

<span data-ttu-id="ee134-105">以下部分介绍了为您的部署配置双重身份验证所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="ee134-105">The following sections describe the steps necessary to configure two-factor authentication for your deployment.</span></span> <span data-ttu-id="ee134-106">有关双重身份验证的详细信息，请参阅[启用 Office 365 联机管理员-网格用户公告的多因素身份验证](https://go.microsoft.com/fwlink/p/?LinkId=313332)。</span><span class="sxs-lookup"><span data-stu-id="ee134-106">For more information about Two-factor authentication, see [Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).</span></span>

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="ee134-107">配置企业根证书颁发机构以支持智能卡身份验证</span><span class="sxs-lookup"><span data-stu-id="ee134-107">Configure an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="ee134-108">以下步骤介绍如何配置企业根 CA 以支持智能卡身份验证：</span><span class="sxs-lookup"><span data-stu-id="ee134-108">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

<span data-ttu-id="ee134-109">有关如何安装在企业根 CA 的信息，请参阅[安装企业根证书颁发机构](https://go.microsoft.com/fwlink/p/?LinkID=313364)。</span><span class="sxs-lookup"><span data-stu-id="ee134-109">For information on how to install an Enterprise Root CA, see [Install an Enterprise Root Certification Authority](https://go.microsoft.com/fwlink/p/?LinkID=313364).</span></span>

1. <span data-ttu-id="ee134-110">使用域管理员帐户登录到企业 CA 计算机。</span><span class="sxs-lookup"><span data-stu-id="ee134-110">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="ee134-111">启动系统管理器，并验证是否已安装“证书颁发机构 Web 注册”角色。</span><span class="sxs-lookup"><span data-stu-id="ee134-111">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3. <span data-ttu-id="ee134-112">从“管理工具”\*\*\*\* 菜单中，打开“证书颁发机构”\*\*\*\* 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="ee134-112">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4. <span data-ttu-id="ee134-113">在导航窗格中，展开“证书颁发机构”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ee134-113">In the Navigation pane, expand **Certification Authority**.</span></span>

5. <span data-ttu-id="ee134-114">右键单击“证书模板”\*\*\*\*，选择“新建”\*\*\*\*，然后选择“要颁发的证书模板”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ee134-114">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6. <span data-ttu-id="ee134-115">选择“注册代理”\*\*\*\*、“智能卡用户”\*\*\*\* 和“智能卡登录”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ee134-115">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7. <span data-ttu-id="ee134-116">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="ee134-116">Click **OK**.</span></span>

8. <span data-ttu-id="ee134-117">右键单击“证书模板”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ee134-117">Right click on **Certificate Templates**.</span></span>

9. <span data-ttu-id="ee134-118">选择“管理”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ee134-118">Select **Manage**.</span></span>

10. <span data-ttu-id="ee134-119">打开智能卡用户模板的属性。</span><span class="sxs-lookup"><span data-stu-id="ee134-119">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="ee134-120">单击“安全”\*\*\*\* 选项卡。</span><span class="sxs-lookup"><span data-stu-id="ee134-120">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="ee134-121">更改权限，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ee134-121">Change the permissions as follows:</span></span>

    - <span data-ttu-id="ee134-122">添加具有读取/注册（允许）权限的各个用户 AD 帐户，或者</span><span class="sxs-lookup"><span data-stu-id="ee134-122">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="ee134-123">添加具有读取/注册（允许）权限且包含智能卡用户的安全组，或者</span><span class="sxs-lookup"><span data-stu-id="ee134-123">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="ee134-124">添加具有读取/注册（允许）权限的域用户组</span><span class="sxs-lookup"><span data-stu-id="ee134-124">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

## <a name="configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="ee134-125">为 Windows 8 配置虚拟智能卡</span><span class="sxs-lookup"><span data-stu-id="ee134-125">Configure Windows 8 for Virtual Smart Cards</span></span>

<span data-ttu-id="ee134-126">部署双重身份验证和智能卡技术时要考虑的一个因素是实施成本。</span><span class="sxs-lookup"><span data-stu-id="ee134-126">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="ee134-127">Windows 8 提供大量的新安全功能，并最有意义的新功能之一是虚拟智能卡支持。</span><span class="sxs-lookup"><span data-stu-id="ee134-127">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="ee134-128">对于配备了符合规范版本 1.2 要求的受信任的平台模块 (TPM) 芯片的计算机，组织现在可以享受智能卡登录带来的好处，不必在硬件方面做任何额外投资。</span><span class="sxs-lookup"><span data-stu-id="ee134-128">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="ee134-129">有关详细信息，请参阅[Windows 8 与使用虚拟智能卡](https://go.microsoft.com/fwlink/p/?LinkId=313365)。</span><span class="sxs-lookup"><span data-stu-id="ee134-129">For more information, see [Using Virtual Smart Cards with Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span></span>

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="ee134-130">为 Windows 8 配置虚拟智能卡</span><span class="sxs-lookup"><span data-stu-id="ee134-130">To Configure Windows 8 for Virtual Smart Cards</span></span>

1. <span data-ttu-id="ee134-131">登录到已启用业务的用户使用的 Skype 凭据的 Windows 8 计算机。</span><span class="sxs-lookup"><span data-stu-id="ee134-131">Log in to the Windows 8 computer using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="ee134-132">在 Windows 8“开始”屏幕中，将您的光标移动到屏幕右下角。</span><span class="sxs-lookup"><span data-stu-id="ee134-132">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3. <span data-ttu-id="ee134-133">选择**搜索**选项，然后搜索 forCommand 提示。</span><span class="sxs-lookup"><span data-stu-id="ee134-133">Select the **Search** option, and then search forCommand Prompt.</span></span>

4. <span data-ttu-id="ee134-134">右键单击“命令提示符”\*\*\*\*，然后选择“以管理员身份运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ee134-134">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5. <span data-ttu-id="ee134-135">通过以下命令打开受信任的平台模块 (TPM) 管理控制台：</span><span class="sxs-lookup"><span data-stu-id="ee134-135">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>

  ```
  Tpm.msc
  ```

6. <span data-ttu-id="ee134-136">从 TPM 管理控制台中，验证您的 TPM 规范版本是否至少为 1.2</span><span class="sxs-lookup"><span data-stu-id="ee134-136">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>

    > [!NOTE]
    > <span data-ttu-id="ee134-137">如果您收到一个对话框表明找不到兼容的受信任的平台模块 (TPM)，请验证计算机是否具有兼容的 TPM 模块以及是否在系统 BIOS 中启用了它。</span><span class="sxs-lookup"><span data-stu-id="ee134-137">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

7. <span data-ttu-id="ee134-138">关闭 TPM 管理控制台</span><span class="sxs-lookup"><span data-stu-id="ee134-138">Close the TPM management console</span></span>

8. <span data-ttu-id="ee134-139">从命令提示符处，使用以下命令创建新的虚拟智能卡：</span><span class="sxs-lookup"><span data-stu-id="ee134-139">From the command prompt, create a new virtual smart card using the following command:</span></span>

  ```
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > <span data-ttu-id="ee134-140">要在创建虚拟智能卡时提供自定义 PIN 值，请使用 /pin 提示符。</span><span class="sxs-lookup"><span data-stu-id="ee134-140">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

9. <span data-ttu-id="ee134-141">从命令提示符处，通过运行以下命令来打开计算机管理控制台：</span><span class="sxs-lookup"><span data-stu-id="ee134-141">From the command prompt, open the Computer Management console by running the following command:</span></span>

  ```
  CompMgmt.msc
  ```

10. <span data-ttu-id="ee134-142">在计算机管理控制台中，选择“设备管理”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ee134-142">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="ee134-143">展开“智能卡读取器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ee134-143">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="ee134-144">验证是否已成功创建新的智能卡读取器。</span><span class="sxs-lookup"><span data-stu-id="ee134-144">Verify that the new virtual smart card reader has been created successfully.</span></span>

## <a name="enroll-users-for-smart-card-authentication"></a><span data-ttu-id="ee134-145">为用户注册智能卡身份验证</span><span class="sxs-lookup"><span data-stu-id="ee134-145">Enroll users for smart card authentication</span></span>

<span data-ttu-id="ee134-p104">通常，可通过两种方法为用户注册智能卡身份验证。较为轻松的方法涉及使用 Web 注册直接为用户注册智能卡身份验证，而较为复杂的方法涉及使用注册代理。本主题着重介绍自动注册智能卡证书。</span><span class="sxs-lookup"><span data-stu-id="ee134-p104">There are generally two methods for enrolling users for smart card authentication. The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent. This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="ee134-149">代表用户注册为注册代理的详细信息，请参阅[证书代表其他用户的注册](https://go.microsoft.com/fwlink/p/?LinkID=313367)。</span><span class="sxs-lookup"><span data-stu-id="ee134-149">For more information on enrolling on behalf of users as an enrollment agent, see [Enroll for Certificates on Behalf of Other Users](https://go.microsoft.com/fwlink/p/?LinkID=313367).</span></span>

### <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="ee134-150">为用户注册智能卡身份验证</span><span class="sxs-lookup"><span data-stu-id="ee134-150">To Enroll Users for Smart Card Authentication</span></span>

1. <span data-ttu-id="ee134-151">登录到 Windows 8 工作站已启用业务的用户使用 Skype 的凭据。</span><span class="sxs-lookup"><span data-stu-id="ee134-151">Log in to the Windows 8 workstation using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="ee134-152">启动 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="ee134-152">Launch Internet Explorer.</span></span>

3. <span data-ttu-id="ee134-153">浏览到的**证书颁发机构 Web 注册**页面 (例如https://MyCA.contoso.com/certsrv)。</span><span class="sxs-lookup"><span data-stu-id="ee134-153">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>

    > [!NOTE]
    > <span data-ttu-id="ee134-154">如果您正在使用 Internet Explorer 10，则可能需要在兼容模式下查看此网站。</span><span class="sxs-lookup"><span data-stu-id="ee134-154">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

4. <span data-ttu-id="ee134-155">在“欢迎”\*\*\*\* 页面上，选择“申请证书”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ee134-155">On the **Welcome** Page, select **Request a certificate**.</span></span>

5. <span data-ttu-id="ee134-156">下一步，选择“高级申请”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ee134-156">Next, select **Advanced Request**.</span></span>

6. <span data-ttu-id="ee134-157">单击“创建并向此 CA 提交一个申请”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ee134-157">Select **Create and submit a request to this CA**.</span></span>

7. <span data-ttu-id="ee134-158">在“证书模板”\*\*\*\* 部分下方选择“智能卡用户”\*\*\*\*，并使用以下值完成高级证书申请：</span><span class="sxs-lookup"><span data-stu-id="ee134-158">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>

  - <span data-ttu-id="ee134-159">“密钥选项”\*\*\*\* 确认以下设置：</span><span class="sxs-lookup"><span data-stu-id="ee134-159">**Key Options** confirm he following settings:</span></span>

    - <span data-ttu-id="ee134-160">选择“创建新密钥集”\*\*\*\* 单选按钮</span><span class="sxs-lookup"><span data-stu-id="ee134-160">Select the **Create new key set** radio button</span></span>

    - <span data-ttu-id="ee134-161">对于“CSP”\*\*\*\*，选择“Microsoft 基本智能卡加密提供程序”\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ee134-161">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>

    - <span data-ttu-id="ee134-162">对于“密钥用法”\*\*\*\*，选择“Exchange”\*\*\*\*（这是唯一可用选项）。</span><span class="sxs-lookup"><span data-stu-id="ee134-162">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>

    - <span data-ttu-id="ee134-163">对于“密码大小”\*\*\*\*，输入 2048</span><span class="sxs-lookup"><span data-stu-id="ee134-163">For **Key Size**, enter 2048</span></span>

    - <span data-ttu-id="ee134-164">确认已选中“自动密钥容器名称”\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ee134-164">Confirm that **Automatic key container name** is selected</span></span>

    - <span data-ttu-id="ee134-165">取消选中其他框。</span><span class="sxs-lookup"><span data-stu-id="ee134-165">Leave the other boxes unchecked.</span></span>

  - <span data-ttu-id="ee134-166">在“其他选项”\*\*\*\* 下方，确认以下值：</span><span class="sxs-lookup"><span data-stu-id="ee134-166">Under **Additional Options** confirm the following values:</span></span>

    - <span data-ttu-id="ee134-167">对于“申请格式”\*\*\*\*，选择“CMC”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ee134-167">For **Request Format** select **CMC**.</span></span>

    - <span data-ttu-id="ee134-168">对于“哈希算法”\*\*\*\*，选择“sha1”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ee134-168">For **Hash Algorithm** select **sha1**.</span></span>

    - <span data-ttu-id="ee134-169">**友好名称**enterSmardcard 证书。</span><span class="sxs-lookup"><span data-stu-id="ee134-169">For **Friendly Name** enterSmardcard Certificate.</span></span>

8. <span data-ttu-id="ee134-170">如果您正在使用物理智能卡读取器，请将智能卡插入设备中。</span><span class="sxs-lookup"><span data-stu-id="ee134-170">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9. <span data-ttu-id="ee134-171">单击“提交”\*\*\*\* 提交证书申请。</span><span class="sxs-lookup"><span data-stu-id="ee134-171">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="ee134-172">出现提示时，输入用于创建虚拟智能卡的 PIN。</span><span class="sxs-lookup"><span data-stu-id="ee134-172">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ee134-173">默认虚拟智能卡 PIN 值为"12345678"。</span><span class="sxs-lookup"><span data-stu-id="ee134-173">The default virtual smart card PIN value is '12345678'.</span></span>

11. <span data-ttu-id="ee134-174">颁发证书后，单击“安装此证书”\*\*\*\* 完成注册过程。</span><span class="sxs-lookup"><span data-stu-id="ee134-174">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="ee134-175">如果您的证书请求失败，错误"此 Web 浏览器不支持生成的证书请求"，有三种可能的方法来解决问题：</span><span class="sxs-lookup"><span data-stu-id="ee134-175">If your certificate request fails with the error "This Web browser does not support the generation of certificate requests," there are three possible ways to resolve the issue:</span></span>

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a><span data-ttu-id="ee134-176">配置 Active Directory 联合身份验证服务 (AD FS 2.0)</span><span class="sxs-lookup"><span data-stu-id="ee134-176">Configure Active Directory Federation Services (AD FS 2.0)</span></span>

<span data-ttu-id="ee134-177">下面一节介绍如何配置 Active Directory 联合身份验证服务 (AD FS 2.0) 来支持多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="ee134-177">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="ee134-178">有关如何安装 AD FS 2.0 的信息，请参阅[AD FS 2.0 分步和如何到参考线](https://go.microsoft.com/fwlink/p/?LinkId=313374)。</span><span class="sxs-lookup"><span data-stu-id="ee134-178">For information on how to install AD FS 2.0, see [AD FS 2.0 Step-by-Step and How To Guides](https://go.microsoft.com/fwlink/p/?LinkId=313374).</span></span>

> [!NOTE]
> <span data-ttu-id="ee134-179">安装 AD FS 2.0 时，请勿使用 Windows Server Manager 添加联合身份验证服务角色。</span><span class="sxs-lookup"><span data-stu-id="ee134-179">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="ee134-180">相反，下载并安装[Active Directory 联合身份验证服务 2.0 一项包](https://go.microsoft.com/fwlink/p/?LinkId=313375)。</span><span class="sxs-lookup"><span data-stu-id="ee134-180">Instead, download and install the [Active Directory Federation Services 2.0 RTW package](https://go.microsoft.com/fwlink/p/?LinkId=313375).</span></span>

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a><span data-ttu-id="ee134-181">针对双重身份验证配置 AD FS</span><span class="sxs-lookup"><span data-stu-id="ee134-181">To configure AD FS for two-factor Authentication</span></span>

1. <span data-ttu-id="ee134-182">使用域管理员帐户登录到 AD FS 2.0 计算机。</span><span class="sxs-lookup"><span data-stu-id="ee134-182">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="ee134-183">启动 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="ee134-183">Start Windows PowerShell.</span></span>

3. <span data-ttu-id="ee134-184">从 Windows PowerShell 命令行，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="ee134-184">From the Windows PowerShell command-line, run the following command:</span></span>

  ```
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. <span data-ttu-id="ee134-185">运行下面的命令，与将启用被动身份验证的每个服务器建立合作关系，运行时替换特定于部署的服务器名称：</span><span class="sxs-lookup"><span data-stu-id="ee134-185">Establish a partnership with each server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>

  ```
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. <span data-ttu-id="ee134-186">从“管理工具”菜单中，启动 AD FS 2.0 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="ee134-186">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6. <span data-ttu-id="ee134-187">展开**的信任关系** > **信赖方信任**。</span><span class="sxs-lookup"><span data-stu-id="ee134-187">Expand **Trust Relationships** > **Relying Party Trusts**.</span></span>

7. <span data-ttu-id="ee134-188">验证新信任已创建为您 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="ee134-188">Verify that a new trust has been created for your Skype for Business Server.</span></span>

8. <span data-ttu-id="ee134-189">使用 Windows PowerShell 通过运行以下命令为您的依赖方信任创建并分配颁发授权规则：</span><span class="sxs-lookup"><span data-stu-id="ee134-189">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. <span data-ttu-id="ee134-190">使用 Windows PowerShell 通过运行以下命令为您的依赖方信任创建并分配颁发转换规则：</span><span class="sxs-lookup"><span data-stu-id="ee134-190">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. <span data-ttu-id="ee134-191">从 AD FS 2.0 管理控制台中，右键单击您的依赖方信任并选择“编辑声明规则”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ee134-191">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="ee134-192">选择“颁发授权规则”\*\*\*\* 选项卡，并验证是否已成功创建新的授权规则。</span><span class="sxs-lookup"><span data-stu-id="ee134-192">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="ee134-193">选择“颁发转换规则”\*\*\*\* 选项卡，并验证是否已成功创建新的转换规则。</span><span class="sxs-lookup"><span data-stu-id="ee134-193">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="ee134-194">配置 AD FS 2.0 以支持客户端身份验证</span><span class="sxs-lookup"><span data-stu-id="ee134-194">Configuring AD FS 2.0 to support client authentication</span></span>

<span data-ttu-id="ee134-195">有两种可能的身份验证类型可配置为允许 AD FS 2.0 支持使用智能卡进行身份验证：</span><span class="sxs-lookup"><span data-stu-id="ee134-195">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

- <span data-ttu-id="ee134-196">基于表单的身份验证 (FBA)</span><span class="sxs-lookup"><span data-stu-id="ee134-196">Forms-based authentication (FBA)</span></span>

- <span data-ttu-id="ee134-197">传输层安全性客户端身份验证</span><span class="sxs-lookup"><span data-stu-id="ee134-197">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="ee134-198">使用基于表单的身份验证，您可以开发一个网页以允许用户使用其用户名/密码或使用其智能卡和 PIN 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="ee134-198">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="ee134-199">本主题着重介绍如何实施传输层安全性客户端身份验证与 AD FS 2.0。</span><span class="sxs-lookup"><span data-stu-id="ee134-199">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="ee134-200">有关 AD FS 2.0 身份验证类型的详细信息，请参阅[AD FS 2.0： 如何更改本地身份验证类型](https://go.microsoft.com/fwlink/p/?LinkId=313384)。</span><span class="sxs-lookup"><span data-stu-id="ee134-200">For more information about AD FS 2.0 authentication types, see [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span></span>

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="ee134-201">配置 AD FS 2.0 以支持客户端身份验证</span><span class="sxs-lookup"><span data-stu-id="ee134-201">To Configure AD FS 2.0 to Support Client Authentication</span></span>

1. <span data-ttu-id="ee134-202">使用域管理员帐户登录到 AD FS 2.0 计算机。</span><span class="sxs-lookup"><span data-stu-id="ee134-202">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="ee134-203">启动 Windows 资源管理器。</span><span class="sxs-lookup"><span data-stu-id="ee134-203">Launch Windows Explorer.</span></span>

3. <span data-ttu-id="ee134-204">浏览到 C:\inetpub\adfs\ls</span><span class="sxs-lookup"><span data-stu-id="ee134-204">Browse to C:\inetpub\adfs\ls</span></span>

4. <span data-ttu-id="ee134-205">创建现有 web.config 文件的备份副本。</span><span class="sxs-lookup"><span data-stu-id="ee134-205">Make a backup copy of the existing web.config file.</span></span>

5. <span data-ttu-id="ee134-206">使用记事本打开现有 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="ee134-206">Open the existing web.config file using Notepad.</span></span>

6. <span data-ttu-id="ee134-207">从菜单栏中，选择“编辑”\*\*\*\*，然后选择“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ee134-207">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7. <span data-ttu-id="ee134-208">搜索\<localAuthenticationTypes\>。</span><span class="sxs-lookup"><span data-stu-id="ee134-208">Search for \<localAuthenticationTypes\>.</span></span>

    <span data-ttu-id="ee134-209">请注意，列出了四种身份验证类型，每行一个。</span><span class="sxs-lookup"><span data-stu-id="ee134-209">Note that there are four authentication types listed, one per line.</span></span>

8. <span data-ttu-id="ee134-210">将包含 TLSClient 身份验证类型的行移动到列表顶部。</span><span class="sxs-lookup"><span data-stu-id="ee134-210">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9. <span data-ttu-id="ee134-211">保存并关闭 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="ee134-211">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="ee134-212">使用提升的特权启动命令提示符。</span><span class="sxs-lookup"><span data-stu-id="ee134-212">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="ee134-213">通过运行以下命令来重新启动 IIS：</span><span class="sxs-lookup"><span data-stu-id="ee134-213">Restart IIS by running the following command:</span></span>

  ```
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a><span data-ttu-id="ee134-214">配置 Skype for Business Server 被动身份验证</span><span class="sxs-lookup"><span data-stu-id="ee134-214">Configuring Skype for Business Server passive authentication</span></span>

<span data-ttu-id="ee134-215">下面一节介绍如何配置 Skype 业务服务器支持被动身份验证。</span><span class="sxs-lookup"><span data-stu-id="ee134-215">The following section describes how to configure Skype for Business Server to support passive authentication.</span></span> <span data-ttu-id="ee134-216">启用后，启用双重身份验证的用户需要使用物理或虚拟智能卡和有效 PIN 使用 Skype for Business 客户端登录。</span><span class="sxs-lookup"><span data-stu-id="ee134-216">Once enabled, users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Skype for Business client.</span></span>

> [!NOTE]
> <span data-ttu-id="ee134-p109">强烈建议用户在服务级别为注册机构和 Web 服务启用被动身份验证。如果在全局级别为注册机构和 Web 服务启用被动身份验证，则可能导致未使用受支持的桌面客户端登录的用户遭遇组织范围身份验证失败。</span><span class="sxs-lookup"><span data-stu-id="ee134-p109">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level. If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the supported desktop client.</span></span>

### <a name="web-service-configuration"></a><span data-ttu-id="ee134-219">Web 服务配置</span><span class="sxs-lookup"><span data-stu-id="ee134-219">Web Service Configuration</span></span>

<span data-ttu-id="ee134-220">以下步骤介绍了如何为将启用被动身份验证的控制器、企业池和 Standard Edition 服务器创建自定义 Web 服务配置。</span><span class="sxs-lookup"><span data-stu-id="ee134-220">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-web-service-configuration"></a><span data-ttu-id="ee134-221">创建自定义 Web 服务配置</span><span class="sxs-lookup"><span data-stu-id="ee134-221">To create a custom web service configuration</span></span>

1. <span data-ttu-id="ee134-222">登录到您的业务 Server 前端服务器使用 Skype 业务管理员帐户的 Skype。</span><span class="sxs-lookup"><span data-stu-id="ee134-222">Log in to your Skype for Business Server Front End server using a Skype for Business administrator account.</span></span>

2. <span data-ttu-id="ee134-223">为业务 Server 命令行管理程序启动 Skype。</span><span class="sxs-lookup"><span data-stu-id="ee134-223">Launch the Skype for Business Server Management Shell.</span></span>

3. <span data-ttu-id="ee134-224">从业务 Server 命令行管理程序命令行的 Skype，每个控制器、 企业版池和 Standard Edition server 将为被动身份验证启用通过运行以下命令创建新的 Web 服务配置：</span><span class="sxs-lookup"><span data-stu-id="ee134-224">From the Skype for Business Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>

  ```
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > <span data-ttu-id="ee134-p110">WsFedPassiveMetadataUri FQDN 的值是您的 AD FS 2.0 服务器的联合身份验证服务名称。可通过从导航窗格右键单击“服务”\*\*\*\*，然后选择“编辑联合身份验证服务属性”\*\*\*\* 在 AD FS 2.0 管理控制台中找到联合身份验证服务名称值。</span><span class="sxs-lookup"><span data-stu-id="ee134-p110">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server. The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on **Service** from the navigation pane and then selecting **Edit Federation Service Properties**.</span></span>

4. <span data-ttu-id="ee134-227">通过运行以下命令来验证 UseWsFedPassiveAuth 和 WsFedPassiveMetadataUri 值是否设置正确：</span><span class="sxs-lookup"><span data-stu-id="ee134-227">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>

  ```
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. <span data-ttu-id="ee134-228">对于客户端，被动身份验证是 Web 票证身份验证最少首选的身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="ee134-228">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="ee134-229">对于所有 Director、 企业版池和 Standard Edition server 将为被动身份验证启用的所有其他身份验证类型，必须禁用 Skype 业务 Web 服务通过运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ee134-229">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Skype for Business Web Services by running the following cmdlet:</span></span>

  ```
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. <span data-ttu-id="ee134-230">运行以下 cmdlet 验证所有其他身份验证类型是否已成功禁用：</span><span class="sxs-lookup"><span data-stu-id="ee134-230">Verify that all other authentication types have been successfully disabled by running the following cmdlet:</span></span>

  ```
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a><span data-ttu-id="ee134-231">代理配置</span><span class="sxs-lookup"><span data-stu-id="ee134-231">Proxy Configuration</span></span>

<span data-ttu-id="ee134-232">证书身份验证的禁用时的 Skype 业务 Web 服务，业务客户端 Skype 将使用较低首选的身份验证类型，如 Kerberos 或 NTLM，对注册器服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="ee134-232">When certificate authentication is disabled for Skype for Business Web Services, the Skype for Business client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="ee134-233">仍然需要证书身份验证以允许客户端检索 Web 票证，但是，必须为 Kerberos 和 NTLM 禁用注册机构服务。</span><span class="sxs-lookup"><span data-stu-id="ee134-233">Certificate authentication is still needed to allow the client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="ee134-234">以下步骤介绍了如何为将启用被动身份验证的边缘池、企业池和 Standard Edition 服务器创建自定义代理配置。</span><span class="sxs-lookup"><span data-stu-id="ee134-234">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-proxy-configuration"></a><span data-ttu-id="ee134-235">创建自定义代理配置</span><span class="sxs-lookup"><span data-stu-id="ee134-235">To create a custom proxy configuration</span></span>

1. <span data-ttu-id="ee134-236">从业务 Server 命令行管理程序命令行的 Skype，创建新的代理配置为将为被动身份验证启用通过运行以下的业务服务器边缘池、 企业版池和 Standard Edition server 的每个 Skype命令：</span><span class="sxs-lookup"><span data-stu-id="ee134-236">From the Skype for Business Server Management Shell command-line, create a new proxy configuration for each Skype for Business Server Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>

  ```
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. <span data-ttu-id="ee134-237">通过运行以下命令来验证所有其他代理身份验证类型是否已成功禁用：</span><span class="sxs-lookup"><span data-stu-id="ee134-237">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>

  ```
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a><span data-ttu-id="ee134-238">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee134-238">See also</span></span>

[<span data-ttu-id="ee134-239">管理 Skype 中的业务服务器的双重身份验证</span><span class="sxs-lookup"><span data-stu-id="ee134-239">Manage two-factor authentication in Skype for Business Server</span></span>](two-factor-authentication.md)

[<span data-ttu-id="ee134-240">用于双重身份验证与 Skype 的业务客户端和 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="ee134-240">Use two-factor authentication with Skype for Business client and Skype for Business Server</span></span>](use-two-factor.md)
