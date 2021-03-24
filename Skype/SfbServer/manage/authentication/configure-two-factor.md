---
title: 在 Skype for Business Server 中配置双重身份验证
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
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: 摘要：在 Skype for Business Server 中配置双重身份验证。
ms.openlocfilehash: 8651be3fbc07bb890637bc8d1c7c99a827d1ea1e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096818"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="73050-103">在 Skype for Business Server 中配置双重身份验证</span><span class="sxs-lookup"><span data-stu-id="73050-103">Configure two-factor authentication in Skype for Business Server</span></span>

<span data-ttu-id="73050-104">**摘要：** 在 Skype for Business Server 中配置双重身份验证。</span><span class="sxs-lookup"><span data-stu-id="73050-104">**Summary:** Configure two-factor authentication in Skype for Business Server.</span></span>

<span data-ttu-id="73050-105">以下各节介绍为部署配置双重身份验证所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="73050-105">The following sections describe the steps necessary to configure two-factor authentication for your deployment.</span></span> <span data-ttu-id="73050-106">有关双重身份验证详细信息，请参阅为联机管理员启用 [Office 365](https://go.microsoft.com/fwlink/p/?LinkId=313332)多重身份验证 - 网格用户帖子。</span><span class="sxs-lookup"><span data-stu-id="73050-106">For more information about Two-factor authentication, see [Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).</span></span>

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="73050-107">配置企业根证书颁发机构以支持智能卡身份验证</span><span class="sxs-lookup"><span data-stu-id="73050-107">Configure an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="73050-108">以下步骤介绍如何配置企业根 CA 以支持智能卡身份验证：</span><span class="sxs-lookup"><span data-stu-id="73050-108">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

<span data-ttu-id="73050-109">若要了解如何安装企业根 CA，请参阅安装 [企业根证书颁发机构](/previous-versions/windows/it-pro/windows-server-2003/cc776709(v=ws.10))。</span><span class="sxs-lookup"><span data-stu-id="73050-109">For information on how to install an Enterprise Root CA, see [Install an Enterprise Root Certification Authority](/previous-versions/windows/it-pro/windows-server-2003/cc776709(v=ws.10)).</span></span>

1. <span data-ttu-id="73050-110">使用域管理员帐户登录到企业 CA 计算机。</span><span class="sxs-lookup"><span data-stu-id="73050-110">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="73050-111">启动系统管理器，并验证是否安装了证书颁发机构 Web 注册角色。</span><span class="sxs-lookup"><span data-stu-id="73050-111">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3. <span data-ttu-id="73050-112">从" **管理工具"菜单中** ，打开 **证书颁发机构** 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="73050-112">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4. <span data-ttu-id="73050-113">在导航窗格中，展开"**证书颁发机构"。**</span><span class="sxs-lookup"><span data-stu-id="73050-113">In the Navigation pane, expand **Certification Authority**.</span></span>

5. <span data-ttu-id="73050-114">右键单击 **"证书模板"，** 选择 **"新建"，** 然后选择"**要颁发的证书模板"。**</span><span class="sxs-lookup"><span data-stu-id="73050-114">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6. <span data-ttu-id="73050-115">选择 **注册代理**、 **智能卡用户** 和 **智能卡登录**。</span><span class="sxs-lookup"><span data-stu-id="73050-115">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7. <span data-ttu-id="73050-116">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="73050-116">Click **OK**.</span></span>

8. <span data-ttu-id="73050-117">右键单击 **"证书模板"。**</span><span class="sxs-lookup"><span data-stu-id="73050-117">Right click on **Certificate Templates**.</span></span>

9. <span data-ttu-id="73050-118">选择"**管理"。**</span><span class="sxs-lookup"><span data-stu-id="73050-118">Select **Manage**.</span></span>

10. <span data-ttu-id="73050-119">打开"智能卡用户"模板的属性。</span><span class="sxs-lookup"><span data-stu-id="73050-119">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="73050-120">单击"安全 **"选项卡** 。</span><span class="sxs-lookup"><span data-stu-id="73050-120">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="73050-121">更改权限，如下所示：</span><span class="sxs-lookup"><span data-stu-id="73050-121">Change the permissions as follows:</span></span>

    - <span data-ttu-id="73050-122">使用"读取/注册"权限添加单个用户 AD (允许) 用户 AD 帐户，或</span><span class="sxs-lookup"><span data-stu-id="73050-122">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="73050-123">添加一个安全组，其中包含具有读取/注册权限的 (允许) 智能卡用户，或者</span><span class="sxs-lookup"><span data-stu-id="73050-123">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="73050-124">添加具有"读取/注册"权限的"域 (") "权限</span><span class="sxs-lookup"><span data-stu-id="73050-124">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

## <a name="configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="73050-125">为 Windows 8 配置虚拟智能卡</span><span class="sxs-lookup"><span data-stu-id="73050-125">Configure Windows 8 for Virtual Smart Cards</span></span>

<span data-ttu-id="73050-126">部署双重身份验证和智能卡技术时要考虑的一个因素是实现成本。</span><span class="sxs-lookup"><span data-stu-id="73050-126">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="73050-127">Windows 8 提供了许多新的安全功能，其中一项最有趣的新功能是支持虚拟智能卡。</span><span class="sxs-lookup"><span data-stu-id="73050-127">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="73050-128">对于配备了受信任的平台模块 (TPM) 芯片（符合规范版本 1.2）的计算机，组织现在可以从智能卡登录中获益，而无需在硬件方面进行任何其他投资。</span><span class="sxs-lookup"><span data-stu-id="73050-128">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="73050-129">有关详细信息，请参阅将 [虚拟智能卡与 Windows 8 一同使用](https://go.microsoft.com/fwlink/p/?LinkId=313365)。</span><span class="sxs-lookup"><span data-stu-id="73050-129">For more information, see [Using Virtual Smart Cards with Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span></span>

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="73050-130">为 Windows 8 配置虚拟智能卡</span><span class="sxs-lookup"><span data-stu-id="73050-130">To Configure Windows 8 for Virtual Smart Cards</span></span>

1. <span data-ttu-id="73050-131">使用启用了 Skype for Business 的用户的凭据登录到 Windows 8 计算机。</span><span class="sxs-lookup"><span data-stu-id="73050-131">Log in to the Windows 8 computer using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="73050-132">在 Windows 8"开始"屏幕上，将光标移到屏幕右下角。</span><span class="sxs-lookup"><span data-stu-id="73050-132">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3. <span data-ttu-id="73050-133">选择" **搜索"** 选项，然后搜索"命令提示"。</span><span class="sxs-lookup"><span data-stu-id="73050-133">Select the **Search** option, and then search forCommand Prompt.</span></span>

4. <span data-ttu-id="73050-134">右键单击命令 **提示符**，然后选择以 **管理员角色运行**。</span><span class="sxs-lookup"><span data-stu-id="73050-134">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5. <span data-ttu-id="73050-135">通过运行以下命令 (TPM) 控制台打开受信任的平台模块：</span><span class="sxs-lookup"><span data-stu-id="73050-135">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>

  ```console
  Tpm.msc
  ```

6. <span data-ttu-id="73050-136">从 TPM 管理控制台中，验证 TPM 规范版本是否至少为 1.2</span><span class="sxs-lookup"><span data-stu-id="73050-136">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>

    > [!NOTE]
    > <span data-ttu-id="73050-137">如果您收到一个对话框，指出找不到兼容的信任平台模块 (TPM) ，请验证计算机是否具有兼容的 TPM 模块，以及它在系统 BIOS 中是否已启用。</span><span class="sxs-lookup"><span data-stu-id="73050-137">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

7. <span data-ttu-id="73050-138">关闭 TPM 管理控制台</span><span class="sxs-lookup"><span data-stu-id="73050-138">Close the TPM management console</span></span>

8. <span data-ttu-id="73050-139">在命令提示符下，使用下列命令创建新的虚拟智能卡：</span><span class="sxs-lookup"><span data-stu-id="73050-139">From the command prompt, create a new virtual smart card using the following command:</span></span>

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > <span data-ttu-id="73050-140">若要在创建虚拟智能卡时提供自定义 PIN 值，请改为使用 /pin 提示符。</span><span class="sxs-lookup"><span data-stu-id="73050-140">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

9. <span data-ttu-id="73050-141">在命令提示符下，通过运行以下命令打开计算机管理控制台：</span><span class="sxs-lookup"><span data-stu-id="73050-141">From the command prompt, open the Computer Management console by running the following command:</span></span>

  ```console
  CompMgmt.msc
  ```

10. <span data-ttu-id="73050-142">在"计算机管理"控制台中，选择"**设备管理"。**</span><span class="sxs-lookup"><span data-stu-id="73050-142">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="73050-143">展开 **智能卡读卡器**。</span><span class="sxs-lookup"><span data-stu-id="73050-143">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="73050-144">验证是否成功创建了新的虚拟智能卡读卡器。</span><span class="sxs-lookup"><span data-stu-id="73050-144">Verify that the new virtual smart card reader has been created successfully.</span></span>

## <a name="enroll-users-for-smart-card-authentication"></a><span data-ttu-id="73050-145">为用户注册智能卡身份验证</span><span class="sxs-lookup"><span data-stu-id="73050-145">Enroll users for smart card authentication</span></span>

<span data-ttu-id="73050-146">通常有两种方法为用户注册智能卡身份验证。</span><span class="sxs-lookup"><span data-stu-id="73050-146">There are generally two methods for enrolling users for smart card authentication.</span></span> <span data-ttu-id="73050-147">更简单的方法涉及让用户使用 Web 注册直接注册智能卡身份验证，而更复杂的方法涉及使用注册代理。</span><span class="sxs-lookup"><span data-stu-id="73050-147">The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent.</span></span> <span data-ttu-id="73050-148">本主题重点介绍智能卡证书的自注册。</span><span class="sxs-lookup"><span data-stu-id="73050-148">This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="73050-149">有关代表用户注册为注册代理的信息，请参阅代表其他用户注册 [证书](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc770802(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="73050-149">For more information on enrolling on behalf of users as an enrollment agent, see [Enroll for Certificates on Behalf of Other Users](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc770802(v=ws.11)).</span></span>

### <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="73050-150">为用户注册智能卡身份验证</span><span class="sxs-lookup"><span data-stu-id="73050-150">To Enroll Users for Smart Card Authentication</span></span>

1. <span data-ttu-id="73050-151">使用启用了 Skype for Business 的用户的凭据登录到 Windows 8 工作站。</span><span class="sxs-lookup"><span data-stu-id="73050-151">Log in to the Windows 8 workstation using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="73050-152">启动Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="73050-152">Launch Internet Explorer.</span></span>

3. <span data-ttu-id="73050-153">浏览到证书 **颁发机构 Web 注册** 页 (例如 https://MyCA.contoso.com/certsrv) 。</span><span class="sxs-lookup"><span data-stu-id="73050-153">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>

    > [!NOTE]
    > <span data-ttu-id="73050-154">如果你使用的是 Internet Explorer 10，可能需要在兼容模式下查看此网站。</span><span class="sxs-lookup"><span data-stu-id="73050-154">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

4. <span data-ttu-id="73050-155">在"**欢迎"** 页上，选择"**请求证书"。**</span><span class="sxs-lookup"><span data-stu-id="73050-155">On the **Welcome** Page, select **Request a certificate**.</span></span>

5. <span data-ttu-id="73050-156">接下来，选择"**高级请求"。**</span><span class="sxs-lookup"><span data-stu-id="73050-156">Next, select **Advanced Request**.</span></span>

6. <span data-ttu-id="73050-157">选择 **"创建"，然后向此 CA 提交请求**。</span><span class="sxs-lookup"><span data-stu-id="73050-157">Select **Create and submit a request to this CA**.</span></span>

7. <span data-ttu-id="73050-158">选择 **"证书模板\*\*\*\*"部分下的**"智能卡用户"，然后使用下列值完成高级证书请求：</span><span class="sxs-lookup"><span data-stu-id="73050-158">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>

  - <span data-ttu-id="73050-159">**密钥选项** 确认他以下设置：</span><span class="sxs-lookup"><span data-stu-id="73050-159">**Key Options** confirm he following settings:</span></span>

    - <span data-ttu-id="73050-160">选择" **创建新密钥集"单** 选按钮</span><span class="sxs-lookup"><span data-stu-id="73050-160">Select the **Create new key set** radio button</span></span>

    - <span data-ttu-id="73050-161">对于 **云** 解决方案提供商，选择 **"Microsoft 基本智能卡加密提供程序"**</span><span class="sxs-lookup"><span data-stu-id="73050-161">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>

    - <span data-ttu-id="73050-162">对于 **"密钥用法\*\*\*\*"， ("** 这是唯一可用于") "选项。</span><span class="sxs-lookup"><span data-stu-id="73050-162">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>

    - <span data-ttu-id="73050-163">对于 **"密钥大小"，** 输入 2048</span><span class="sxs-lookup"><span data-stu-id="73050-163">For **Key Size**, enter 2048</span></span>

    - <span data-ttu-id="73050-164">确认 **已选择"自动密钥** 容器名称"</span><span class="sxs-lookup"><span data-stu-id="73050-164">Confirm that **Automatic key container name** is selected</span></span>

    - <span data-ttu-id="73050-165">将其他框保持未选中状态。</span><span class="sxs-lookup"><span data-stu-id="73050-165">Leave the other boxes unchecked.</span></span>

  - <span data-ttu-id="73050-166">在 **"其他选项"** 下，确认以下值：</span><span class="sxs-lookup"><span data-stu-id="73050-166">Under **Additional Options** confirm the following values:</span></span>

    - <span data-ttu-id="73050-167">对于 **"请求格式"，** 选择 **"CMC"。**</span><span class="sxs-lookup"><span data-stu-id="73050-167">For **Request Format** select **CMC**.</span></span>

    - <span data-ttu-id="73050-168">对于 **哈希算法，** 选择 **sha1**。</span><span class="sxs-lookup"><span data-stu-id="73050-168">For **Hash Algorithm** select **sha1**.</span></span>

    - <span data-ttu-id="73050-169">对于 **"友好名称** "，输入"证书"。</span><span class="sxs-lookup"><span data-stu-id="73050-169">For **Friendly Name** enterSmardcard Certificate.</span></span>

8. <span data-ttu-id="73050-170">如果使用物理智能卡读卡器，请将智能卡插入设备。</span><span class="sxs-lookup"><span data-stu-id="73050-170">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9. <span data-ttu-id="73050-171">单击 **"提交** "以提交证书请求。</span><span class="sxs-lookup"><span data-stu-id="73050-171">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="73050-172">系统提示时，输入用于创建虚拟智能卡的 PIN。</span><span class="sxs-lookup"><span data-stu-id="73050-172">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>

    > [!NOTE]
    > <span data-ttu-id="73050-173">默认虚拟智能卡 PIN 值为"12345678"。</span><span class="sxs-lookup"><span data-stu-id="73050-173">The default virtual smart card PIN value is '12345678'.</span></span>

11. <span data-ttu-id="73050-174">颁发证书后，单击 **"安装此证书** "以完成注册过程。</span><span class="sxs-lookup"><span data-stu-id="73050-174">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="73050-175">如果证书请求失败并出现错误"此 Web 浏览器不支持生成证书请求"，则有三种可能的方法可以解决此问题：</span><span class="sxs-lookup"><span data-stu-id="73050-175">If your certificate request fails with the error "This Web browser does not support the generation of certificate requests," there are three possible ways to resolve the issue:</span></span>

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a><span data-ttu-id="73050-176">配置 Active Directory 联合身份验证服务 (AD FS 2.0) </span><span class="sxs-lookup"><span data-stu-id="73050-176">Configure Active Directory Federation Services (AD FS 2.0)</span></span>

<span data-ttu-id="73050-177">下一节介绍如何配置 Active Directory 联合身份验证服务 (AD FS 2.0) 以支持多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="73050-177">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="73050-178">若要了解如何安装 AD FS 2.0，请参阅 [AD FS 2.0 分步指南和操作指南](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10))。</span><span class="sxs-lookup"><span data-stu-id="73050-178">For information on how to install AD FS 2.0, see [AD FS 2.0 Step-by-Step and How To Guides](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10)).</span></span>

> [!NOTE]
> <span data-ttu-id="73050-179">安装 AD FS 2.0 时，请勿使用 Windows Server 管理器添加 Active Directory 联合身份验证服务角色。</span><span class="sxs-lookup"><span data-stu-id="73050-179">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="73050-180">相反，请下载并安装 [Active Directory 联合身份验证服务 2.0 RTW 程序包](https://go.microsoft.com/fwlink/p/?LinkId=313375)。</span><span class="sxs-lookup"><span data-stu-id="73050-180">Instead, download and install the [Active Directory Federation Services 2.0 RTW package](https://go.microsoft.com/fwlink/p/?LinkId=313375).</span></span>

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a><span data-ttu-id="73050-181">为双因素身份验证配置 AD FS</span><span class="sxs-lookup"><span data-stu-id="73050-181">To configure AD FS for two-factor Authentication</span></span>

1. <span data-ttu-id="73050-182">使用域管理员帐户登录到 AD FS 2.0 计算机。</span><span class="sxs-lookup"><span data-stu-id="73050-182">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="73050-183">启动 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="73050-183">Start Windows PowerShell.</span></span>

3. <span data-ttu-id="73050-184">从Windows PowerShell命令行运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="73050-184">From the Windows PowerShell command-line, run the following command:</span></span>

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. <span data-ttu-id="73050-185">通过运行以下命令与将启用被动身份验证的每台服务器建立合作关系，替换特定于您的部署的服务器名称：</span><span class="sxs-lookup"><span data-stu-id="73050-185">Establish a partnership with each server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. <span data-ttu-id="73050-186">从"管理工具"菜单中，启动 AD FS 2.0 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="73050-186">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6. <span data-ttu-id="73050-187">展开 **"信任**  >  **关系信赖方信任"。**</span><span class="sxs-lookup"><span data-stu-id="73050-187">Expand **Trust Relationships** > **Relying Party Trusts**.</span></span>

7. <span data-ttu-id="73050-188">验证是否为 Skype for Business Server 创建了新信任。</span><span class="sxs-lookup"><span data-stu-id="73050-188">Verify that a new trust has been created for your Skype for Business Server.</span></span>

8. <span data-ttu-id="73050-189">通过运行以下命令，使用 Windows PowerShell为信赖方信任创建和分配颁发授权规则：</span><span class="sxs-lookup"><span data-stu-id="73050-189">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. <span data-ttu-id="73050-190">通过运行以下命令，使用 Windows PowerShell为信赖方信任创建和分配颁发转换规则：</span><span class="sxs-lookup"><span data-stu-id="73050-190">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. <span data-ttu-id="73050-191">从 AD FS 2.0 管理控制台中，右键单击信赖方信任并选择"**编辑声明规则"。**</span><span class="sxs-lookup"><span data-stu-id="73050-191">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="73050-192">选择颁发 **授权规则** 选项卡并验证是否成功创建了新的授权规则。</span><span class="sxs-lookup"><span data-stu-id="73050-192">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="73050-193">选择" **颁发转换规则** "选项卡，并验证是否成功创建了新的转换规则。</span><span class="sxs-lookup"><span data-stu-id="73050-193">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="73050-194">配置 AD FS 2.0 以支持客户端身份验证</span><span class="sxs-lookup"><span data-stu-id="73050-194">Configuring AD FS 2.0 to support client authentication</span></span>

<span data-ttu-id="73050-195">可以配置两种可能的身份验证类型，以允许 AD FS 2.0 支持使用智能卡进行身份验证：</span><span class="sxs-lookup"><span data-stu-id="73050-195">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

- <span data-ttu-id="73050-196">基于表单的身份验证 (FBA) </span><span class="sxs-lookup"><span data-stu-id="73050-196">Forms-based authentication (FBA)</span></span>

- <span data-ttu-id="73050-197">传输层安全性客户端身份验证</span><span class="sxs-lookup"><span data-stu-id="73050-197">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="73050-198">使用基于表单的身份验证，您可以开发一个网页，允许用户通过使用其用户名/密码或通过使用其智能卡和 PIN 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="73050-198">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="73050-199">本主题重点介绍如何使用 AD FS 2.0 实现传输层安全客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="73050-199">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="73050-200">有关 AD FS 2.0 身份验证类型的信息，请参阅 [AD FS 2.0：如何更改本地身份验证类型](https://go.microsoft.com/fwlink/p/?LinkId=313384)。</span><span class="sxs-lookup"><span data-stu-id="73050-200">For more information about AD FS 2.0 authentication types, see [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span></span>

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="73050-201">配置 AD FS 2.0 以支持客户端身份验证</span><span class="sxs-lookup"><span data-stu-id="73050-201">To Configure AD FS 2.0 to Support Client Authentication</span></span>

1. <span data-ttu-id="73050-202">使用域管理员帐户登录到 AD FS 2.0 计算机。</span><span class="sxs-lookup"><span data-stu-id="73050-202">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="73050-203">启动 Windows 资源管理器。</span><span class="sxs-lookup"><span data-stu-id="73050-203">Launch Windows Explorer.</span></span>

3. <span data-ttu-id="73050-204">浏览到 C：\inetpub\adfs\ls</span><span class="sxs-lookup"><span data-stu-id="73050-204">Browse to C:\inetpub\adfs\ls</span></span>

4. <span data-ttu-id="73050-205">创建现有数据库文件的web.config副本。</span><span class="sxs-lookup"><span data-stu-id="73050-205">Make a backup copy of the existing web.config file.</span></span>

5. <span data-ttu-id="73050-206">使用记web.config打开现有文件。</span><span class="sxs-lookup"><span data-stu-id="73050-206">Open the existing web.config file using Notepad.</span></span>

6. <span data-ttu-id="73050-207">从"菜单"栏中，选择 **"编辑"，** 然后选择"查找 **"。**</span><span class="sxs-lookup"><span data-stu-id="73050-207">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7. <span data-ttu-id="73050-208">搜索 \<localAuthenticationTypes\> 。</span><span class="sxs-lookup"><span data-stu-id="73050-208">Search for \<localAuthenticationTypes\>.</span></span>

    <span data-ttu-id="73050-209">请注意，列出了四种身份验证类型，每行一种。</span><span class="sxs-lookup"><span data-stu-id="73050-209">Note that there are four authentication types listed, one per line.</span></span>

8. <span data-ttu-id="73050-210">将包含 TLSClient 身份验证类型的行移到 部分的列表顶部。</span><span class="sxs-lookup"><span data-stu-id="73050-210">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9. <span data-ttu-id="73050-211">保存并关闭web.config文件。</span><span class="sxs-lookup"><span data-stu-id="73050-211">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="73050-212">使用提升的权限启动命令提示符。</span><span class="sxs-lookup"><span data-stu-id="73050-212">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="73050-213">通过运行以下命令来重新启动 IIS：</span><span class="sxs-lookup"><span data-stu-id="73050-213">Restart IIS by running the following command:</span></span>

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a><span data-ttu-id="73050-214">配置 Skype for Business Server 被动身份验证</span><span class="sxs-lookup"><span data-stu-id="73050-214">Configuring Skype for Business Server passive authentication</span></span>

<span data-ttu-id="73050-215">以下部分介绍如何配置 Skype for Business Server 以支持被动身份验证。</span><span class="sxs-lookup"><span data-stu-id="73050-215">The following section describes how to configure Skype for Business Server to support passive authentication.</span></span> <span data-ttu-id="73050-216">启用后，启用双重身份验证的用户需要使用物理或虚拟智能卡和有效 PIN 才能使用 Skype for Business 客户端登录。</span><span class="sxs-lookup"><span data-stu-id="73050-216">Once enabled, users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Skype for Business client.</span></span>

> [!NOTE]
> <span data-ttu-id="73050-217">强烈建议客户在服务级别为注册器和 Web 服务启用被动身份验证。</span><span class="sxs-lookup"><span data-stu-id="73050-217">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="73050-218">如果在全局级别为注册器和 Web 服务启用被动身份验证，则可能导致未使用受支持的桌面客户端登录的用户在组织范围内进行身份验证失败。</span><span class="sxs-lookup"><span data-stu-id="73050-218">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the supported desktop client.</span></span>

### <a name="web-service-configuration"></a><span data-ttu-id="73050-219">Web 服务配置</span><span class="sxs-lookup"><span data-stu-id="73050-219">Web Service Configuration</span></span>

<span data-ttu-id="73050-220">以下步骤介绍如何为将启用被动身份验证的控制器、企业池和 Standard Edition 服务器创建自定义 Web 服务配置。</span><span class="sxs-lookup"><span data-stu-id="73050-220">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-web-service-configuration"></a><span data-ttu-id="73050-221">创建自定义 Web 服务配置</span><span class="sxs-lookup"><span data-stu-id="73050-221">To create a custom web service configuration</span></span>

1. <span data-ttu-id="73050-222">使用 Skype for Business 管理员帐户登录到 Skype for Business Server 前端服务器。</span><span class="sxs-lookup"><span data-stu-id="73050-222">Log in to your Skype for Business Server Front End server using a Skype for Business administrator account.</span></span>

2. <span data-ttu-id="73050-223">启动 Skype for Business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="73050-223">Launch the Skype for Business Server Management Shell.</span></span>

3. <span data-ttu-id="73050-224">从 Skype for Business Server 命令行管理程序命令行中，通过运行以下命令，为每个将启用被动身份验证的控制器、企业池和 Standard Edition Server 创建新的 Web 服务配置：</span><span class="sxs-lookup"><span data-stu-id="73050-224">From the Skype for Business Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > <span data-ttu-id="73050-225">WsFedPassiveMetadataUri FQDN 的值为 AD FS 2.0 服务器的联合身份验证服务名称。</span><span class="sxs-lookup"><span data-stu-id="73050-225">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server.</span></span> <span data-ttu-id="73050-226">可以在 AD FS 2.0 管理控制台中找到联合身份验证服务名称值，方法是从导航窗格中右键单击"服务"，然后选择"编辑联合身份验证服务 **属性"。**</span><span class="sxs-lookup"><span data-stu-id="73050-226">The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on **Service** from the navigation pane and then selecting **Edit Federation Service Properties**.</span></span>

4. <span data-ttu-id="73050-227">通过运行以下命令验证 UseWsFedPassiveAuth 和 WsFedPassiveMetadataUri 值是否正确设置：</span><span class="sxs-lookup"><span data-stu-id="73050-227">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. <span data-ttu-id="73050-228">对于客户端，被动身份验证是 Webticket 身份验证最不首选的身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="73050-228">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="73050-229">对于将启用被动身份验证的所有控制器、企业池和 Standard Edition 服务器，必须通过运行以下 cmdlet 在 Skype for Business Web 服务中禁用所有其他身份验证类型：</span><span class="sxs-lookup"><span data-stu-id="73050-229">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Skype for Business Web Services by running the following cmdlet:</span></span>

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. <span data-ttu-id="73050-230">通过运行以下 cmdlet 验证是否成功禁用了所有其他身份验证类型：</span><span class="sxs-lookup"><span data-stu-id="73050-230">Verify that all other authentication types have been successfully disabled by running the following cmdlet:</span></span>

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a><span data-ttu-id="73050-231">代理配置</span><span class="sxs-lookup"><span data-stu-id="73050-231">Proxy Configuration</span></span>

<span data-ttu-id="73050-232">为 Skype for Business Web 服务禁用证书身份验证后，Skype for Business 客户端将使用不太首选的身份验证类型（如 Kerberos 或 NTLM）向注册器服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="73050-232">When certificate authentication is disabled for Skype for Business Web Services, the Skype for Business client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="73050-233">仍然需要证书身份验证以允许客户端检索 Web 令牌，但是，必须为注册器服务禁用 Kerberos 和 NTLM。</span><span class="sxs-lookup"><span data-stu-id="73050-233">Certificate authentication is still needed to allow the client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="73050-234">以下步骤介绍如何为将启用被动身份验证的边缘池、企业池和 Standard Edition 服务器创建自定义代理配置。</span><span class="sxs-lookup"><span data-stu-id="73050-234">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-proxy-configuration"></a><span data-ttu-id="73050-235">创建自定义代理配置</span><span class="sxs-lookup"><span data-stu-id="73050-235">To create a custom proxy configuration</span></span>

1. <span data-ttu-id="73050-236">通过 Skype for Business Server 命令行管理程序命令行，通过运行以下命令，为每个将启用被动身份验证的 Skype for Business Server 边缘池、企业池和 Standard Edition Server 创建新的代理配置：</span><span class="sxs-lookup"><span data-stu-id="73050-236">From the Skype for Business Server Management Shell command-line, create a new proxy configuration for each Skype for Business Server Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. <span data-ttu-id="73050-237">通过运行以下命令验证是否成功禁用所有其他代理身份验证类型：</span><span class="sxs-lookup"><span data-stu-id="73050-237">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>

  ```PowerShell
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a><span data-ttu-id="73050-238">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73050-238">See also</span></span>

[<span data-ttu-id="73050-239">在 Skype for Business Server 中管理双重身份验证</span><span class="sxs-lookup"><span data-stu-id="73050-239">Manage two-factor authentication in Skype for Business Server</span></span>](two-factor-authentication.md)

[<span data-ttu-id="73050-240">对 Skype for Business 客户端和 Skype for Business Server 使用双重身份验证</span><span class="sxs-lookup"><span data-stu-id="73050-240">Use two-factor authentication with Skype for Business client and Skype for Business Server</span></span>](use-two-factor.md)