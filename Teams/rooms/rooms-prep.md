---
title: 准备环境
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: 了解如何准备基础结构以部署Microsoft Teams 会议室以便可以利用所有功能。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 81aa41895f11b65c9406bd30311f2fcb974949a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117420"
---
# <a name="prepare-your-environment"></a><span data-ttu-id="09900-103">准备环境</span><span class="sxs-lookup"><span data-stu-id="09900-103">Prepare your environment</span></span>

<span data-ttu-id="09900-104">本部分包含准备环境所需的步骤概述，以便可以使用所有 Microsoft Teams 会议室。</span><span class="sxs-lookup"><span data-stu-id="09900-104">This section contains an overview of the steps required to prepare your environment so that you can use all of the features of Microsoft Teams Rooms.</span></span>
  
1. <span data-ttu-id="09900-105">为每台主机准备Microsoft Teams 会议室帐户。</span><span class="sxs-lookup"><span data-stu-id="09900-105">Prepare a device account for each Microsoft Teams Rooms console.</span></span> <span data-ttu-id="09900-106">有关详细信息[，Microsoft Teams 会议室](rooms-deploy.md)部署应用程序。</span><span class="sxs-lookup"><span data-stu-id="09900-106">See [Deploy Microsoft Teams Rooms](rooms-deploy.md) for details.</span></span>
    
2. <span data-ttu-id="09900-107">确保有运行良好的网络/Internet 连接可供设备使用。</span><span class="sxs-lookup"><span data-stu-id="09900-107">Ensure that there is a working network/Internet connection for the device to use.</span></span> 
    
   <span data-ttu-id="09900-108">它必须能够使用 DHCP 接收 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="09900-108">It must be able to receive an IP address by using DHCP.</span></span> <span data-ttu-id="09900-109"> (Microsoft Teams 会议室第一个单元启动时无法使用静态 IP 地址进行配置，但之后，可以在设备或上游交换机或路由器.) </span><span class="sxs-lookup"><span data-stu-id="09900-109">(Microsoft Teams Rooms cannot be configured with a static IP address at the first unit startup, but afterwards, a static IP address for the device could be configured on the device or on the upstream switch or router.)</span></span>

   <span data-ttu-id="09900-110">除了为媒体服务打开 (，还必须让这些端口打开) ：</span><span class="sxs-lookup"><span data-stu-id="09900-110">It must have these ports open (in addition to opening the normal ports for media):</span></span>
   - <span data-ttu-id="09900-111">HTTPS：443</span><span class="sxs-lookup"><span data-stu-id="09900-111">HTTPS: 443</span></span>
   - <span data-ttu-id="09900-112">HTTP：80</span><span class="sxs-lookup"><span data-stu-id="09900-112">HTTP: 80</span></span>

   <span data-ttu-id="09900-113">如果你的网络通过代理运行，则还需要提供代理地址或脚本信息。</span><span class="sxs-lookup"><span data-stu-id="09900-113">If your network runs through a proxy, you'll need the proxy address or script information as well.</span></span>
    
   > [!IMPORTANT]
   > <span data-ttu-id="09900-114">Microsoft Teams 会议室不支持代理身份验证，因为它可能会干扰聊天室的常规操作。</span><span class="sxs-lookup"><span data-stu-id="09900-114">Microsoft Teams Rooms does not support proxy authentication as it may interfere with regular operations of the room.</span></span> <span data-ttu-id="09900-115">在投入Microsoft Teams 会议室之前，请确保已免除代理身份验证。</span><span class="sxs-lookup"><span data-stu-id="09900-115">Ensure that Microsoft Teams Rooms have been exempted from proxy authentication before going into production.</span></span>
  
3. <span data-ttu-id="09900-116">为了改进你的体验，Microsoft 将收集数据。</span><span class="sxs-lookup"><span data-stu-id="09900-116">In order to improve your experience, Microsoft collects data.</span></span> <span data-ttu-id="09900-117">若要允许 Microsoft 收集数据，请允许以下网站：</span><span class="sxs-lookup"><span data-stu-id="09900-117">To allow Microsoft to collect data, allow these sites:</span></span>

   - <span data-ttu-id="09900-118">遥测客户端终结点： https://vortex.data.microsoft.com/</span><span class="sxs-lookup"><span data-stu-id="09900-118">Telemetry client endpoint: https://vortex.data.microsoft.com/</span></span>
   - <span data-ttu-id="09900-119">遥测设置终结点： https://settings.data.microsoft.com/</span><span class="sxs-lookup"><span data-stu-id="09900-119">Telemetry settings endpoint: https://settings.data.microsoft.com/</span></span>
    
### <a name="create-and-test-a-device-account"></a><span data-ttu-id="09900-120">创建和测试设备帐户</span><span class="sxs-lookup"><span data-stu-id="09900-120">Create and test a device account</span></span>

<span data-ttu-id="09900-121">*设备帐户* 是一个帐户，Microsoft Teams 会议室客户端用来从日历等Exchange访问功能，以及启用Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="09900-121">A  *device account*  is an account that the Microsoft Teams Rooms client uses to access features from Exchange, like calendar, and to enable Skype for Business.</span></span> <span data-ttu-id="09900-122">有关详细信息[，Microsoft Teams 会议室](rooms-deploy.md)部署应用程序。</span><span class="sxs-lookup"><span data-stu-id="09900-122">See [Deploy Microsoft Teams Rooms](rooms-deploy.md) for details.</span></span>
  
### <a name="check-network-availability"></a><span data-ttu-id="09900-123">检查网络可用性</span><span class="sxs-lookup"><span data-stu-id="09900-123">Check network availability</span></span>

<span data-ttu-id="09900-124">若要正常运行，Microsoft Teams 会议室设备必须有权访问满足这些要求的有线网络：</span><span class="sxs-lookup"><span data-stu-id="09900-124">In order to function properly, the Microsoft Teams Rooms device must have access to a wired network that meets these requirements:</span></span>
  
- <span data-ttu-id="09900-125">可访问 Active Directory 或 Azure Active Directory (Azure AD) 实例以及 Microsoft Exchange 和 Skype for Business 服务器。</span><span class="sxs-lookup"><span data-stu-id="09900-125">Access to your Active Directory or Azure Active Directory (Azure AD) instance, as well as your Microsoft Exchange and Skype for Business servers.</span></span>

- <span data-ttu-id="09900-126">可访问能够使用 DHCP 提供 IP 地址的服务器。</span><span class="sxs-lookup"><span data-stu-id="09900-126">Access to a server that can provide an IP address using DHCP.</span></span> <span data-ttu-id="09900-127">Microsoft Teams 会议室单元启动时无法使用静态 IP 地址进行配置。</span><span class="sxs-lookup"><span data-stu-id="09900-127">Microsoft Teams Rooms cannot be configured with a static IP address at the first unit startup.</span></span>

- <span data-ttu-id="09900-128">访问 HTTP 端口 80 和 443。</span><span class="sxs-lookup"><span data-stu-id="09900-128">Access to HTTP ports 80 and 443.</span></span>

- <span data-ttu-id="09900-129">根据本地 Skype for Business Server 实现[、Microsoft 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)和[](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols)Office 365 URL 以及 Microsoft Teams 或 Skype for Business 联机实现的服务器端口和协议要求中所述配置 TCP 和 UDP 端口。</span><span class="sxs-lookup"><span data-stu-id="09900-129">TCP and UDP ports configured as described in [Port and protocol requirements for servers](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) for on-premise Skype for Business Server implementations, or [Microsoft 365 and Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) for Microsoft Teams or Skype for Business online implementations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="09900-130">务必使用 1 Gbps 的有线网络连接来确保获得所需带宽。</span><span class="sxs-lookup"><span data-stu-id="09900-130">Be sure to use a wired 1 Gbps network connection to assure you will have the needed bandwidth.</span></span>

> [!NOTE]
> <span data-ttu-id="09900-131">系统会自动Microsoft Teams 会议室下载适用于 适用于企业的 Microsoft Store 的软件更新。</span><span class="sxs-lookup"><span data-stu-id="09900-131">Software updates for Microsoft Teams Rooms are automatically downloaded from the Microsoft Store for Business.</span></span> <span data-ttu-id="09900-132">请参阅[适用于企业的 Microsoft Store](/microsoft-store/prerequisites-microsoft-store-for-business)和教育的先决条件，验证会议室主机是否能够访问应用商店和自我更新。</span><span class="sxs-lookup"><span data-stu-id="09900-132">See [Prerequisites for Microsoft Store for Business and Education](/microsoft-store/prerequisites-microsoft-store-for-business) to verify that the room console will be able to access the store and self-update.</span></span>
  
### <a name="certificates"></a><span data-ttu-id="09900-133">证书</span><span class="sxs-lookup"><span data-stu-id="09900-133">Certificates</span></span>

<span data-ttu-id="09900-134">你的 Microsoft Teams 会议室 设备使用证书Exchange Web 服务、Microsoft Teams或Skype for Business、网络使用情况和身份验证。</span><span class="sxs-lookup"><span data-stu-id="09900-134">Your Microsoft Teams Rooms device uses certificates for Exchange Web Services, Microsoft Teams or Skype for Business, network usage, and authentication.</span></span> <span data-ttu-id="09900-135">如果相关服务器使用公用证书（联机部署和部分本地部署便属于这种情况），则无需在管理部分执行任何进一步操作来安装证书。</span><span class="sxs-lookup"><span data-stu-id="09900-135">If the related servers use public certificates, which is the case for Online and some On-Premises deployments, there should be no further action required on the part of the admin to install certificates.</span></span> <span data-ttu-id="09900-136">另一方面，如果证书颁发机构为私有 CA（通常用于本地部署），则设备需要信任该 CA，这意味着在设备中安装了 CA + CA 链证书。</span><span class="sxs-lookup"><span data-stu-id="09900-136">If, on the other hand, the certificate authority is a private CA (typical for On-Premises deployments) then the device needs to trust that CA which means having the CA + CA chain certificates installed on the device.</span></span> <span data-ttu-id="09900-137">将设备添加到域时，可以自动执行此任务。</span><span class="sxs-lookup"><span data-stu-id="09900-137">Adding the device to the domain may perform this task automatically.</span></span>
  
<span data-ttu-id="09900-138">安装证书的方式与任何其他 Windows 客户端一样。</span><span class="sxs-lookup"><span data-stu-id="09900-138">You will install certificates the same way you would for any other Windows client.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="09900-139">可能需要证书才能Microsoft Teams 会议室Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="09900-139">Certificates may be required in order to have Microsoft Teams Rooms use Skype for Business Server.</span></span>
  
### <a name="proxy"></a><span data-ttu-id="09900-140">代理</span><span class="sxs-lookup"><span data-stu-id="09900-140">Proxy</span></span>

<span data-ttu-id="09900-141">Microsoft Teams 会议室旨在从操作系统继承代理Windows设置。</span><span class="sxs-lookup"><span data-stu-id="09900-141">Microsoft Teams Rooms is designed to inherit Proxy settings from the Windows OS.</span></span> <span data-ttu-id="09900-142">通过以下方式访问 Windows OS：</span><span class="sxs-lookup"><span data-stu-id="09900-142">Access the Windows OS in the following manner:</span></span>
  
1. <span data-ttu-id="09900-143">在 Microsoft Teams 会议室 UI 中，单击 设置 齿轮图标，系统会提示输入设备的本地管理员密码 (默认密码是 **sfb**) 。</span><span class="sxs-lookup"><span data-stu-id="09900-143">In the Microsoft Teams Rooms UI, click on the Settings gear icon where you'll be prompted for the local Administrator password on the device (the default password is **sfb**).</span></span>
2. <span data-ttu-id="09900-144">点击 **设置，** 然后点击"转到 **Windows"** 按钮，然后点击转到"管理员登录"按钮，然后单击"管理员"按钮 (如果计算机已加入域，请选择"其他用户"，然后使用 .\admin作为用户名) 。 </span><span class="sxs-lookup"><span data-stu-id="09900-144">Tap on **Settings** followed by tapping on the **Go to Windows** button and then tapping on the **go to Admin Sign In** button and then clicking the **Administrator** button (if the computer is domain joined choose **Other User,** then use .\admin as the user name).</span></span>
3. <span data-ttu-id="09900-145">在"**搜索Windows"** 框中，键入 regedit (长按屏幕或右键单击并选择"以管理员角色运行") 。 </span><span class="sxs-lookup"><span data-stu-id="09900-145">In the **Search Windows** box bottom left type in regedit (either long press the screen or right click and choose **Run as administrator**).</span></span>
4. <span data-ttu-id="09900-146">单击 HKEY_USERS 文件夹（你将看到计算机用户 SID 列表），确保选择根文件夹 HKEY_USERS。</span><span class="sxs-lookup"><span data-stu-id="09900-146">Click on the HKEY_USERS folder (you'll see a list of machine user SIDs) ensure the root folder HKEY_USERS is selected.</span></span>
       
5. <span data-ttu-id="09900-147">单击"文件"，然后选择" **加载 Hive"。**</span><span class="sxs-lookup"><span data-stu-id="09900-147">Click on File and then choose **Load Hive.**</span></span>
6. <span data-ttu-id="09900-148">浏览到 **C：\Users\Skype** 文件夹，键入"文件名"框 NTUSER.dat，然后按打开按钮</span><span class="sxs-lookup"><span data-stu-id="09900-148">Browse to the **C:\Users\Skype** folder and type in the File name box NTUSER.dat and press the open button</span></span>

7. <span data-ttu-id="09900-149">系统会提示输入新加载的 Hive 的密钥名称;键入Skype (现在应会看到"用户"Skype的注册表) 。</span><span class="sxs-lookup"><span data-stu-id="09900-149">You'll be prompted for a Key Name for your newly loaded Hive; type in Skype (you should now see the registry settings for the Skype User).</span></span>
 
8. <span data-ttu-id="09900-150">打开Skype并浏览HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings，然后确保输入这些设置：</span><span class="sxs-lookup"><span data-stu-id="09900-150">Open the Skype key and browse to HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings then ensure these settings are entered:</span></span> 
    
    ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "ProxyServer"="xx.xx.xx.xx:8080"
    ```
    
    <span data-ttu-id="09900-151">如果 ProxyServer 不存在，你可能必须以字符串形式添加此注册表项，将 xx.xx.xx.xx:8080 更改为你的代理服务器的 IP/主机和端口。</span><span class="sxs-lookup"><span data-stu-id="09900-151">If ProxyServer doesn't exist you may have to add this key as a string, change the xx.xx.xx.xx:8080 to the ip/host and port of your Proxy server.</span></span>
 
    <span data-ttu-id="09900-152">如果客户使用 PAC 文件，配置将如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="09900-152">If the customer is using a PAC file the configuration would look like the example below:</span></span>

     ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "AutoConfigURL"=http://contosoproxy.corp.net/proxy.pac
    ```
    
9. <span data-ttu-id="09900-153">完成更改后，请突出显示 Skype 用户注册表项（Skype 的根文件夹），并从“注册表文件”菜单中选择“卸载配置单元”（系统将提示你确认 - 请选择 **是**）。</span><span class="sxs-lookup"><span data-stu-id="09900-153">Once you are finished making your changes highlight the Skype User key (root folder for Skype) and choose unload Hive from the Registry file menu (you'll be prompted for confirmation - select **Yes**).</span></span>
    
10. <span data-ttu-id="09900-154">现在可以关闭注册表编辑器并在 Windows 搜索框中键入“注销”。</span><span class="sxs-lookup"><span data-stu-id="09900-154">You can now close the registry editor and type logoff into the Windows search box.</span></span>
    
11. <span data-ttu-id="09900-155">返回登录屏幕，选择 **Skype** 用户。</span><span class="sxs-lookup"><span data-stu-id="09900-155">Back at the sign-in screen, choose the **Skype** user.</span></span> <span data-ttu-id="09900-156">如果上述所有步骤都成功，Microsoft Teams 会议室设备将成功登录。</span><span class="sxs-lookup"><span data-stu-id="09900-156">If all the previous steps were successful, the Microsoft Teams Rooms device will sign-in successfully.</span></span>
    
<span data-ttu-id="09900-157">有关[FQDN、](./security.md#network-security)端口和 IP 地址范围的详细信息，请参阅网络安全一文Microsoft Teams 会议室。</span><span class="sxs-lookup"><span data-stu-id="09900-157">See the [Network Security](./security.md#network-security) article for full details on FQDNs, ports, and IP address ranges required for Microsoft Teams Rooms.</span></span>
  
  
### <a name="create-provisioning-packages"></a><span data-ttu-id="09900-158">创建设置包</span><span class="sxs-lookup"><span data-stu-id="09900-158">Create provisioning packages</span></span>

<span data-ttu-id="09900-159">将使用预配包进行身份验证，以Exchange Server、Microsoft 365或Office 365。</span><span class="sxs-lookup"><span data-stu-id="09900-159">You will use provisioning packages to authenticate to Exchange Server, Microsoft 365, or Office 365.</span></span>
  
### <a name="admin-group-management"></a><span data-ttu-id="09900-160">管理员组管理</span><span class="sxs-lookup"><span data-stu-id="09900-160">Admin group management</span></span>

<span data-ttu-id="09900-161">加入域后，可以本地管理员身份使用组策略或本地计算机管理来设置安全组，就像对你的域中的 Windows 电脑那样。</span><span class="sxs-lookup"><span data-stu-id="09900-161">After domain joining, you can use Group Policy or the Local Computer Management to set a Security Group as local administrator just like you would for a Windows PC in your domain.</span></span> <span data-ttu-id="09900-162">该安全组的任何成员均可输入其凭据并解锁设置。</span><span class="sxs-lookup"><span data-stu-id="09900-162">Anyone who is a member of that security group can enter their credentials and unlock Settings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="09900-163">如果你的 Microsoft Teams 会议室设备失去与域的信任关系（例如，如果在 Microsoft Teams 会议室加入域后将其从域中移除），你将无法通过身份验证进入设备并打开“设置”。</span><span class="sxs-lookup"><span data-stu-id="09900-163">If your Microsoft Teams Rooms device loses trust with the domain (for example, if you remove the Microsoft Teams Rooms from the domain after it is domain joined), you won't be able to authenticate into the device and open up Settings.</span></span> <span data-ttu-id="09900-164">解决方法是使用本地管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="09900-164">The workaround is to log in with the local Admin account.</span></span> 
  
## <a name="local-accounts"></a><span data-ttu-id="09900-165">本地帐户</span><span class="sxs-lookup"><span data-stu-id="09900-165">Local accounts</span></span>

### <a name="microsoft-teams-rooms-local-user-account"></a><span data-ttu-id="09900-166">Microsoft Teams 会议室本地用户帐户</span><span class="sxs-lookup"><span data-stu-id="09900-166">Microsoft Teams Rooms Local User Account</span></span>

<span data-ttu-id="09900-167">该设备帐户通常不使用密码。</span><span class="sxs-lookup"><span data-stu-id="09900-167">The Device Account does not typically use a password.</span></span> <span data-ttu-id="09900-168">可以为其给定密码，但会有一些后果，包括密码过期后用户可能被锁在该控制台应用程序之外。</span><span class="sxs-lookup"><span data-stu-id="09900-168">It is possible to give it a password, but there are consequences, including a possibility that users might get locked out of the console application when that password expires.</span></span> <span data-ttu-id="09900-169">因此，管理员应确保不允许密码过期。</span><span class="sxs-lookup"><span data-stu-id="09900-169">Consequently, the administrator should take are to ensure that the password is not allowed to expire.</span></span>
  
### <a name="admin---local-administrator-account"></a><span data-ttu-id="09900-170">“Admin”- 本地管理员帐户</span><span class="sxs-lookup"><span data-stu-id="09900-170">"Admin" - Local Administrator Account</span></span>

<span data-ttu-id="09900-171">Microsoft Teams 会议室默认密码设置为"sfb"。</span><span class="sxs-lookup"><span data-stu-id="09900-171">Microsoft Teams Rooms default password is set to "sfb".</span></span> <span data-ttu-id="09900-172">可以通过转到 Windows 设置 转到 Windows 或在 AutoUnattend.xml 文件中更改密码 (使用 ADK 中的 Windows 系统映像管理器更改 xml 文件 \>) 。</span><span class="sxs-lookup"><span data-stu-id="09900-172">The Password can be changed locally by going to Windows Settings \> Go to Windows or in the AutoUnattend.xml file (use the Windows System Image manager from ADK to make the change to the xml file).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="09900-173">请务必尽快更改Microsoft Teams 会议室密码。</span><span class="sxs-lookup"><span data-stu-id="09900-173">Be sure to change the Microsoft Teams Rooms password as soon as possible.</span></span> 
  
<span data-ttu-id="09900-174">还可以通过设置组策略（其中域管理员设为本地管理员）来管理本地管理员密码。</span><span class="sxs-lookup"><span data-stu-id="09900-174">You can also manage the Local Administrator password by setting up a group policy where domain admins are made local admins.</span></span>
  
<span data-ttu-id="09900-175">本地管理员密码不是安装过程中的一个选项。</span><span class="sxs-lookup"><span data-stu-id="09900-175">The Local admin password is not included as a choice during Setup.</span></span>
  
### <a name="machine-account"></a><span data-ttu-id="09900-176">计算机帐户</span><span class="sxs-lookup"><span data-stu-id="09900-176">Machine Account</span></span>

<span data-ttu-id="09900-177">与任何Windows一样，可以通过右键单击"关于重命名电脑"设置 \> **重命名** 计算机 \> **名称**。</span><span class="sxs-lookup"><span data-stu-id="09900-177">Much like any Windows device, the Machine Name can be renamed by right-clicking in **Settings** \> **About** \> **Rename PC**.</span></span>
  
<span data-ttu-id="09900-178">如果要在将计算机加入域后重命名计算机，请使用 **Rename-Computer（PowerShell** 命令，后跟计算机的新名称）。</span><span class="sxs-lookup"><span data-stu-id="09900-178">If you would like to rename the computer after joining it to a domain, use **Rename-Computer**, a PowerShell command, followed by the computer's new name.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="09900-179">相关主题</span><span class="sxs-lookup"><span data-stu-id="09900-179">Related topics</span></span>

[<span data-ttu-id="09900-180">计划Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="09900-180">Plan Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="09900-181">Microsoft Teams 会议室要求</span><span class="sxs-lookup"><span data-stu-id="09900-181">Microsoft Teams Rooms requirements</span></span>](requirements.md)
  
[<span data-ttu-id="09900-182">部署 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="09900-182">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="09900-183">配置 Microsoft Teams 会议室控制台</span><span class="sxs-lookup"><span data-stu-id="09900-183">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="09900-184">管理 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="09900-184">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

[<span data-ttu-id="09900-185">课程适用于企业的 Microsoft Store教育的先决条件</span><span class="sxs-lookup"><span data-stu-id="09900-185">Prerequisites for Microsoft Store for Business and Education</span></span>](/microsoft-store/prerequisites-microsoft-store-for-business)