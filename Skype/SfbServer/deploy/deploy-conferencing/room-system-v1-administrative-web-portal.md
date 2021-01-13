---
title: 在 Skype for Business Server 中部署 SRS v1 管理 Web 门户
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: Skype for Business Server Skype 会议室系统 v1 (SRS v1（以前称为 Lync Room System) 管理 Web 门户）是一个 Web 门户，组织可以使用该门户维护其 Skype 会议室系统会议室。 管理员可以使用 SRS v1 管理 Web 门户监视设备运行状况，例如通过监视音频/视频设备。 通过此门户，管理员可以远程收集诊断信息以监视会议室运行状况。
ms.openlocfilehash: 7d7bef99149d09ebf72c9b633370f262e535b23f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804532"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a><span data-ttu-id="944c3-105">在 Skype for Business Server 中部署 SRS v1 管理 Web 门户</span><span class="sxs-lookup"><span data-stu-id="944c3-105">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>

<span data-ttu-id="944c3-106">Skype for Business Server Skype 会议室系统 v1 (SRS v1（以前称为 Lync Room System) 管理 Web 门户）是一个 Web 门户，组织可以使用该门户维护其 Skype 会议室系统会议室。</span><span class="sxs-lookup"><span data-stu-id="944c3-106">The Skype for Business Server Skype Room Systems v1 (SRS v1, formerly known as Lync Room System) Administrative Web Portal is a web portal that organizations can use to maintain their Skype Room Systems conference rooms.</span></span> <span data-ttu-id="944c3-107">管理员可以使用 SRS v1 管理 Web 门户监视设备运行状况，例如通过监视音频/视频设备。</span><span class="sxs-lookup"><span data-stu-id="944c3-107">Administrators can use the SRS v1 Administrative Web Portal to monitor device health, for example by monitoring audio/video devices.</span></span> <span data-ttu-id="944c3-108">通过此门户，管理员可以远程收集诊断信息以监视会议室运行状况。</span><span class="sxs-lookup"><span data-stu-id="944c3-108">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="944c3-109">若要使用此功能，需要在每个 Skype for Business Server 前端服务器上部署 SRS v1 管理 Web 门户。</span><span class="sxs-lookup"><span data-stu-id="944c3-109">To use this feature, the SRS v1 Administrative Web Portal needs to be deployed on every Skype for Business Server Front End Server.</span></span> <span data-ttu-id="944c3-110">本指南向管理员提供有关如何安装和配置 SRS 管理 Web 门户的说明。</span><span class="sxs-lookup"><span data-stu-id="944c3-110">This guide provides instructions for administrators on how to install and configure the SRS Administrative Web Portal.</span></span> <span data-ttu-id="944c3-111">它适用于了解 Skype for Business Server 管理，并且具有修改 Skype for Business Server 拓扑的管理员用户权限的管理员。</span><span class="sxs-lookup"><span data-stu-id="944c3-111">It is intended for administrators who have knowledge of Skype for Business Server administration, and who have administrator user rights to modify the Skype for Business Server topology.</span></span>

<span data-ttu-id="944c3-112">在服务器上部署 SRS v1 管理 Web 门户后，管理员可以通过从自己的计算机或笔记本电脑登录到网站来检查 SRS v1 设备的状态。</span><span class="sxs-lookup"><span data-stu-id="944c3-112">After the SRS v1 Administrative Web Portal is deployed on the server, administrators can check the status SRS v1 devices by logging on to the site from their own computers or laptops.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="944c3-113">下载 [适用于 Skype for Business Server 2015 的 Microsoft Skype 会议室系统 v1](https://www.microsoft.com/download/details.aspx?id=46906)管理 Web 门户。</span><span class="sxs-lookup"><span data-stu-id="944c3-113">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="944c3-114">本主题内容：</span><span class="sxs-lookup"><span data-stu-id="944c3-114">In this topic:</span></span>

- [<span data-ttu-id="944c3-115">为 SRS v1 管理 Web 门户配置环境</span><span class="sxs-lookup"><span data-stu-id="944c3-115">Configure your environment for the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Config_Env)

- [<span data-ttu-id="944c3-116">安装 SRS v1 管理 Web 门户</span><span class="sxs-lookup"><span data-stu-id="944c3-116">Install the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Install_SRS)

- [<span data-ttu-id="944c3-117">使用 SRS 管理 Web 门户</span><span class="sxs-lookup"><span data-stu-id="944c3-117">Use the SRS Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="944c3-118">为 SRS v1 管理 Web 门户配置环境</span><span class="sxs-lookup"><span data-stu-id="944c3-118">Configure your environment for the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="944c3-119"><a name="Config_Env"> </a></span><span class="sxs-lookup"><span data-stu-id="944c3-119"><a name="Config_Env"> </a></span></span>

<span data-ttu-id="944c3-120">若要使用 SRS v1 管理 Web 门户，您需要安装或配置以下必备组件。</span><span class="sxs-lookup"><span data-stu-id="944c3-120">To use the SRS v1 Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="944c3-121">如果服务器同时配置了 Kerberos 和 NTLM 身份验证，并且 SRS 正在未加入域的计算机上运行，则 Kerberos 身份验证将失败，并且用户不会在管理门户中看到 SRS 的状态。</span><span class="sxs-lookup"><span data-stu-id="944c3-121">If the server is configured with both Kerberos and NTLM authentication, and SRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of SRS in the administrative portal.</span></span> <span data-ttu-id="944c3-122">若要解决此问题，请配置具有 NTLM 身份验证的服务器，或者配置 NTLM 身份验证和 TLS-DSK 身份验证 (而无需 Kerberos) ，或将 SRS 计算机加入域。</span><span class="sxs-lookup"><span data-stu-id="944c3-122">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the SRS computer to the domain.</span></span>

1. <span data-ttu-id="944c3-123">在 Skype for Business Server 拓扑中安装 Skype for Business Server 累积更新。</span><span class="sxs-lookup"><span data-stu-id="944c3-123">Install Skype for Business Server Cumulative Updates in the Skype for Business Server topology.</span></span>

    <span data-ttu-id="944c3-124">若要获取更新或查看其中包含哪些内容，请参阅 Skype [for Business Server 2015 的更新](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。</span><span class="sxs-lookup"><span data-stu-id="944c3-124">To get the update or see what's included with it, see [Updates for Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

2. <span data-ttu-id="944c3-125">创建启用 SIP 的 Active Directory 用户。</span><span class="sxs-lookup"><span data-stu-id="944c3-125">Create a SIP-enabled Active Directory user.</span></span>

    <span data-ttu-id="944c3-126">SRS v1 管理 Web 门户使用这些凭据从 Skype for Business Server 查询信息。</span><span class="sxs-lookup"><span data-stu-id="944c3-126">The SRS v1 Administrative Web Portal uses these credentials to query information from Skype for Business Server.</span></span> <span data-ttu-id="944c3-127">给定示例中的用户名是 LRSApp。</span><span class="sxs-lookup"><span data-stu-id="944c3-127">The username in the examples given is LRSApp.</span></span>

3. <span data-ttu-id="944c3-128">创建名称为 LRSSupportAdminGroup 的 Active Directory 安全组。</span><span class="sxs-lookup"><span data-stu-id="944c3-128">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>

    <span data-ttu-id="944c3-129">将组作用域创建为全局组，将组类型创建为安全组。</span><span class="sxs-lookup"><span data-stu-id="944c3-129">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="944c3-130">添加到此组的启用 SIP 的用户将有权查看聊天室列表并执行某些命令，例如收集日志。</span><span class="sxs-lookup"><span data-stu-id="944c3-130">SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4. <span data-ttu-id="944c3-131">创建一个名称为 LRSFullAccessAdminGroup 的 Active Directory 安全组。</span><span class="sxs-lookup"><span data-stu-id="944c3-131">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>

    <span data-ttu-id="944c3-132">创建组作用域为全局组，将组类型作为安全组。添加到该组的启用 SIP 的用户有权使用单个 Skype 会议室上的所有管理门户功能。</span><span class="sxs-lookup"><span data-stu-id="944c3-132">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality on a single Skype room.</span></span> <span data-ttu-id="944c3-133">若要包含对 Skype 会议室批量管理的支持，请参阅步骤 5。</span><span class="sxs-lookup"><span data-stu-id="944c3-133">To include support for bulk management of Skype rooms, refer to step 5.</span></span>

     ![具有安全组角色的管理员组列表](../../media/LRS_LRSFullAccessAdminGroup.png)

5. <span data-ttu-id="944c3-135">创建名称为 LRSPowerUserAdminsGroup 的 Active Directory 安全组。</span><span class="sxs-lookup"><span data-stu-id="944c3-135">Create an Active Directory security group with name LRSPowerUserAdminsGroup.</span></span>

    <span data-ttu-id="944c3-136">将组作用域创建为全局组，将组类型创建为安全组。</span><span class="sxs-lookup"><span data-stu-id="944c3-136">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="944c3-137">添加到此组的启用 SIP 的用户有权使用所有管理门户功能，包括批量管理 Skype for Business 会议室。</span><span class="sxs-lookup"><span data-stu-id="944c3-137">SIP enabled users who are added to this group are authorized to use all admin portal functionality including bulk management of Skype for Business rooms.</span></span>

6. <span data-ttu-id="944c3-138">添加 LRSFullAccessAdminGroup 作为 LRSSupportAdminGroup 的成员。</span><span class="sxs-lookup"><span data-stu-id="944c3-138">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>

     ![LRSSupportAdminGroup 属性成员页](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. <span data-ttu-id="944c3-140">创建名称为 LRSSupport 的启用 SIP 的 Active Directory 用户。</span><span class="sxs-lookup"><span data-stu-id="944c3-140">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="944c3-141">将此用户添加到 LRSSupportAdminGroup。</span><span class="sxs-lookup"><span data-stu-id="944c3-141">Add this user to LRSSupportAdminGroup.</span></span>

     ![LRSSupportAdminGroup 属性成员页](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. <span data-ttu-id="944c3-143">安装[ASP.NET SP1 Visual Studio 2010 Visual Web Developer 2010 SP1 的 MVC 4。](https://go.microsoft.com/fwlink/p/?LinkId=323967)</span><span class="sxs-lookup"><span data-stu-id="944c3-143">Install [ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span></span>

## <a name="install-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="944c3-144">安装 SRS v1 管理 Web 门户</span><span class="sxs-lookup"><span data-stu-id="944c3-144">Install the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="944c3-145"><a name="Install_SRS"> </a></span><span class="sxs-lookup"><span data-stu-id="944c3-145"><a name="Install_SRS"> </a></span></span>

<span data-ttu-id="944c3-146">下载 [适用于 Skype for Business Server 2015 的 Microsoft Skype 会议室系统 v1](https://www.microsoft.com/download/details.aspx?id=46906)管理 Web 门户。</span><span class="sxs-lookup"><span data-stu-id="944c3-146">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="944c3-147">若要安装 SRS v1 管理 Web 门户，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="944c3-147">To install the SRS v1 Administrative Web Portal, use the following steps.</span></span>

1. <span data-ttu-id="944c3-148">在 Skype for Business Server 命令行管理程序 中运行以下 cmdlet 配置受信任应用程序端口：</span><span class="sxs-lookup"><span data-stu-id="944c3-148">Configure the Trusted Application Port by running the following cmdlet in Skype for Business Server Management Shell:</span></span>

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. <span data-ttu-id="944c3-149">若要安装会议室门户， **请下载** MeetingRoomPortalInstaller.msi，然后以管理员角色运行它。</span><span class="sxs-lookup"><span data-stu-id="944c3-149">To install the Meeting Room Portal, download **MeetingRoomPortalInstaller.msi** and then run it as an administrator.</span></span>

3. <span data-ttu-id="944c3-150">从Web.config打开文件：</span><span class="sxs-lookup"><span data-stu-id="944c3-150">Open the Web.config file from the following location:</span></span>

    <span data-ttu-id="944c3-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler</span><span class="sxs-lookup"><span data-stu-id="944c3-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler</span></span>\

4. <span data-ttu-id="944c3-152">在 Web.Config 文件中，将 PortalUserName 更改为步骤 2 中"为[SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)管理 Web 门户配置环境"部分下创建的用户名 (步骤中的推荐名称为 LRSApp) ：</span><span class="sxs-lookup"><span data-stu-id="944c3-152">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section "[Configure your environment for the SRS v1 Administrative Web Portal](room-system-v1-administrative-web-portal.md#Config_Env)" (the recommended name in the step is LRSApp):</span></span>

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. <span data-ttu-id="944c3-153">由于 SRS v1 管理门户是受信任的应用程序，因此无需在门户配置中提供密码。</span><span class="sxs-lookup"><span data-stu-id="944c3-153">Because the SRS v1 Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="944c3-154">如果此用户使用的注册机构与本地注册机构不同，则需要在注册文件中添加以下行来指定Web.Config注册器：</span><span class="sxs-lookup"><span data-stu-id="944c3-154">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. <span data-ttu-id="944c3-155">如果使用的端口不是 5061，则向文件中添加以下Web.Config行：</span><span class="sxs-lookup"><span data-stu-id="944c3-155">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a><span data-ttu-id="944c3-156">验证 SRS 管理 Web 门户的安装</span><span class="sxs-lookup"><span data-stu-id="944c3-156">Verify Installation of the SRS Administrative Web Portal</span></span>

<span data-ttu-id="944c3-157">若要验证 SRS v1 管理 Web 门户的安装，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="944c3-157">To verify installation of the SRS v1 Administrative Web Portal, do the following:</span></span>

1. <span data-ttu-id="944c3-158">在前端服务器上，浏览到以下 URL：</span><span class="sxs-lookup"><span data-stu-id="944c3-158">On a Front End server, browse to the following URL:</span></span>

    <span data-ttu-id="944c3-159">https:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="944c3-159">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="944c3-160">不应看到任何错误，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="944c3-160">You should not see any errors, as shown in the following image:</span></span>

     ![Lync 会议室系统管理门户登录屏幕](../../media/LRS_AdminPortalSignIn.png)

2. <span data-ttu-id="944c3-162">如果看不到任何错误，请尝试从拓扑中的其他任何计算机访问以下 URL：</span><span class="sxs-lookup"><span data-stu-id="944c3-162">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>

    <span data-ttu-id="944c3-163">https:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="944c3-163">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="944c3-164">若要访问该页面，您需要添加 DNS 记录，如"自动客户端登录所需的 DNS 记录["中所述](https://go.microsoft.com/fwlink/p/?LinkId=318056)。</span><span class="sxs-lookup"><span data-stu-id="944c3-164">To access the page, you will need to add the DNS records as described in "[Required DNS Records for Automatic Client Sign-In](https://go.microsoft.com/fwlink/p/?LinkId=318056)."</span></span>

## <a name="use-the-srs-administrative-web-portal"></a><span data-ttu-id="944c3-165">使用 SRS 管理 Web 门户</span><span class="sxs-lookup"><span data-stu-id="944c3-165">Use the SRS Administrative Web Portal</span></span>
<span data-ttu-id="944c3-166"><a name="Use_Portal"> </a></span><span class="sxs-lookup"><span data-stu-id="944c3-166"><a name="Use_Portal"> </a></span></span>

<span data-ttu-id="944c3-167">在服务器上部署 SRS 后，可以通过从浏览器登录 SRS v1 管理 Web 门户来检查所有 SRS 会议室的状态。</span><span class="sxs-lookup"><span data-stu-id="944c3-167">After you deploy SRS on the server, you can check the status of all SRS rooms by signing into the SRS v1 Administrative Web Portal from a browser.</span></span>

### <a name="sign-in"></a><span data-ttu-id="944c3-168">登录</span><span class="sxs-lookup"><span data-stu-id="944c3-168">Sign in</span></span>

1. <span data-ttu-id="944c3-169">浏览到以下 URL：</span><span class="sxs-lookup"><span data-stu-id="944c3-169">Browse to the following URL:</span></span>

    <span data-ttu-id="944c3-170">https:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="944c3-170">https://\<fe-server\>/lrs</span></span>

2. <span data-ttu-id="944c3-171">输入 LRSSupport 帐户或已添加到 LRSSupportAdminGroup 安全组的帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="944c3-171">Enter the credentials for the LRSSupport account or an account that was added to the LRSSupportAdminGroup security group.</span></span>

![Lync 会议室系统管理门户登录屏幕](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a><span data-ttu-id="944c3-173">SRS 管理 Web 门户摘要页</span><span class="sxs-lookup"><span data-stu-id="944c3-173">SRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="944c3-174">摘要页提供了服务器上部署的所有 SRS 会议室的以下信息：</span><span class="sxs-lookup"><span data-stu-id="944c3-174">The summary page provides the following information for all of the SRS rooms deployed on the server:</span></span>

- <span data-ttu-id="944c3-175">**Tag** 管理员为会议室提供自定义名称。</span><span class="sxs-lookup"><span data-stu-id="944c3-175">**Tag** The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="944c3-176">可以通过单击会议室名称在门户中设置 Tag。</span><span class="sxs-lookup"><span data-stu-id="944c3-176">The Tag can be set in the portal by clicking on the room name.</span></span>

- <span data-ttu-id="944c3-177">**运行状况** 聊天室的运行状况状态，派生自聊天室的聚合运行状况状态，显示在"会议室设置"页的"运行状况"部分下。</span><span class="sxs-lookup"><span data-stu-id="944c3-177">**Health** The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

- <span data-ttu-id="944c3-178">**下一次会议** 安排下一次会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="944c3-178">**Next Meeting** The date and time the next meeting is scheduled.</span></span>

- <span data-ttu-id="944c3-179">**SRS 版本， 制造商， 型号** 这些值在 SRS 中预设。</span><span class="sxs-lookup"><span data-stu-id="944c3-179">**SRS Version, Manufacturer, Model** These values are preset in SRS.</span></span> <span data-ttu-id="944c3-180">根据制造商，这些字段可能保留为空。</span><span class="sxs-lookup"><span data-stu-id="944c3-180">Depending on the manufacturer, these fields might be left blank.</span></span>

- <span data-ttu-id="944c3-181">**上次刷新** 显示上次刷新网页的时间。</span><span class="sxs-lookup"><span data-stu-id="944c3-181">**Last Refresh** Displays the last time the web page was refreshed.</span></span>

![Lync 会议室系统管理门户摘要视图](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> <span data-ttu-id="944c3-183">只有 LRSPowerUserAdminsGroup 安全组的成员，才能看到"批量管理"菜单。</span><span class="sxs-lookup"><span data-stu-id="944c3-183">You will only see the Bulk Management menu if you are part of the LRSPowerUserAdminsGroup security group.</span></span>

### <a name="srs-room-information"></a><span data-ttu-id="944c3-184">SRS 会议室信息</span><span class="sxs-lookup"><span data-stu-id="944c3-184">SRS Room Information</span></span>

<span data-ttu-id="944c3-185">门户的"会议室信息"部分允许你查看和配置各个 SRS 会议室。</span><span class="sxs-lookup"><span data-stu-id="944c3-185">The Room Info section of the portal allows you to view and configure individual SRS rooms.</span></span> <span data-ttu-id="944c3-186">它包含四个部分：设置、详细信息、日志记录和运行状况。</span><span class="sxs-lookup"><span data-stu-id="944c3-186">It contains four sections: Settings, Details, Logging, and Health.</span></span>

#### <a name="settings"></a><span data-ttu-id="944c3-187">设置</span><span class="sxs-lookup"><span data-stu-id="944c3-187">Settings</span></span>

<span data-ttu-id="944c3-188">在"设置"部分，可以设置会议室的密码、会议室标记和默认音量级别。</span><span class="sxs-lookup"><span data-stu-id="944c3-188">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="944c3-189">如果配置这些设置，则仅在重新启动 SRS 控制台后复制更改。</span><span class="sxs-lookup"><span data-stu-id="944c3-189">If you configure these settings, the changes are replicated only after you restart the SRS console.</span></span> <span data-ttu-id="944c3-190">你将仅看到使用版本 15.12 及更高版本的 SRS 设备的系统更新设置。</span><span class="sxs-lookup"><span data-stu-id="944c3-190">You will only see System Updates settings for SRS devices using release 15.12 and later.</span></span>

![Lync 会议室系统管理门户聊天室设置](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a><span data-ttu-id="944c3-192">详细信息</span><span class="sxs-lookup"><span data-stu-id="944c3-192">Details</span></span>

<span data-ttu-id="944c3-193">"详细信息"部分提供 SRS 聊天室设置的只读摘要，包括：上次刷新的时间;下一个会议;上次更新、维护和校准;默认扬声器、麦克风和响铃设置;version;SIP URI;屏幕数量和有关每个屏幕的详细信息;状态和活动。</span><span class="sxs-lookup"><span data-stu-id="944c3-193">The Details section provides a read-only summary of the SRS room's settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

![Lync 会议室系统管理门户详细信息视图](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a><span data-ttu-id="944c3-195">疑难解答</span><span class="sxs-lookup"><span data-stu-id="944c3-195">Troubleshooting</span></span>

<span data-ttu-id="944c3-196">疑难解答部分可用于远程收集日志并将其保存到指定位置。</span><span class="sxs-lookup"><span data-stu-id="944c3-196">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="944c3-197">还可以在 SRS 用户界面 (SRS) 或重新启动整个系统。</span><span class="sxs-lookup"><span data-stu-id="944c3-197">You can also restart the SRS console (SRS user interface) or restart the entire system.</span></span> <span data-ttu-id="944c3-198">若要收集日志，请提供指定格式的文件夹路径，并确保该文件夹具有为 SRS 计算机帐户提供的写入权限。</span><span class="sxs-lookup"><span data-stu-id="944c3-198">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the SRS machine account.</span></span> <span data-ttu-id="944c3-199">如果日志大小太大，则最多可能需要 5 分钟才能完成日志收集。</span><span class="sxs-lookup"><span data-stu-id="944c3-199">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="944c3-200">刷新页面会提供最新状态。</span><span class="sxs-lookup"><span data-stu-id="944c3-200">Refreshing the page will give you the latest status.</span></span>

#### <a name="health"></a><span data-ttu-id="944c3-201">健康</span><span class="sxs-lookup"><span data-stu-id="944c3-201">Health</span></span>

<span data-ttu-id="944c3-202">"运行状况"部分直观指示 Skype for Business Server 连接、音频设备、视频设备、恢复能力状态和屏幕设备的运行状况。</span><span class="sxs-lookup"><span data-stu-id="944c3-202">The Health section gives a visual indication of the health of the Skype for Business Server connection, audio device, video device, resiliency state, and screen device.</span></span>

![Lync 会议室系统管理门户聊天室运行状况](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="944c3-204">有关管理 Web 门户的其他说明</span><span class="sxs-lookup"><span data-stu-id="944c3-204">Additional Notes about the Administrative Web Portal</span></span>

> [!NOTE]
>  <span data-ttu-id="944c3-205">仅在重新启动 SRS 系统后应用设置更改。>如果 LRSApp 帐户密码过期，将看不到聊天室的状态。</span><span class="sxs-lookup"><span data-stu-id="944c3-205">Setting changes are applied only after the SRS system is restarted.>  If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="944c3-206">将 LRSAppuser 帐户密码配置为永不过期，或确保在密码即将过期时更新密码。> SRS 管理 Web 门户仅支持本地部署。</span><span class="sxs-lookup"><span data-stu-id="944c3-206">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it is near expiration.>  The SRS administrative web portal is supported for on-premises deployments only.</span></span>

### <a name="bulk-management"></a><span data-ttu-id="944c3-207">批量管理</span><span class="sxs-lookup"><span data-stu-id="944c3-207">Bulk management</span></span>

<span data-ttu-id="944c3-208">SRS 聊天室的批量管理是一项专为高级 IT 管理员设计的功能，可简化其工作流，并使他们能够使用节省时间的便捷工具以批量方式远程管理多个聊天室。</span><span class="sxs-lookup"><span data-stu-id="944c3-208">Bulk management of SRS rooms is a feature designed for advanced IT administrators, to simplify their workflow, and enable them with a time-saving convenient tool to remotely manage multiple rooms in a bulk fashion.</span></span>

<span data-ttu-id="944c3-209">为了看到此功能，需要将用户预配为特殊安全组 **LRSPowerUserAdminsGroup 的成员**。</span><span class="sxs-lookup"><span data-stu-id="944c3-209">In order to see this functionality, the user need to be provisioned as a member of the special security group, **LRSPowerUserAdminsGroup**.</span></span>

<span data-ttu-id="944c3-210">可以选择进行批量管理的 SRS 聊天室数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="944c3-210">There is no limit to the number of SRS rooms you can select for bulk management.</span></span> <span data-ttu-id="944c3-211">但是，一次只能执行一个批量管理操作。</span><span class="sxs-lookup"><span data-stu-id="944c3-211">However, you can perform only one bulk management operation at a time.</span></span>

<span data-ttu-id="944c3-212">若要执行批量管理操作，请选择要监视的聊天室，然后单击"批量管理"菜单。</span><span class="sxs-lookup"><span data-stu-id="944c3-212">To perform a bulk management operation, select the rooms you want to monitor, and click on the Bulk management menu.</span></span>

### <a name="frequently-asked-questions"></a><span data-ttu-id="944c3-213">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="944c3-213">Frequently asked questions</span></span>

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="944c3-214">为什么我无法登录管理 Web 门户？</span><span class="sxs-lookup"><span data-stu-id="944c3-214">Why can't I sign in to the administrative web portal?</span></span>

<span data-ttu-id="944c3-215">打开后，你将能够看到登录页，但当您键入凭据时 https://localhost/lrs ，将无法登录。</span><span class="sxs-lookup"><span data-stu-id="944c3-215">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="944c3-216">在这种情况下，您必须打开 https://FQDNofFEserver/SRS 以登录到管理 Web 门户。</span><span class="sxs-lookup"><span data-stu-id="944c3-216">In this case, you must open https://FQDNofFEserver/SRS to sign in to the administrative web portal.</span></span>

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a><span data-ttu-id="944c3-217">为什么我在管理 Web 门户中看不到 SRS v1？</span><span class="sxs-lookup"><span data-stu-id="944c3-217">Why can't I see SRS v1 in the administrative web portal?</span></span>

- <span data-ttu-id="944c3-218">确保部署中具有 SRS 帐户，并且这些帐户是按照 SRS 管理 Web 门户部署建议创建的。</span><span class="sxs-lookup"><span data-stu-id="944c3-218">Make sure you have SRS accounts in your deployment and that they are created according to the SRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="944c3-219">确保在 Skype for Business Server 中使用 Enable-CsMeetingRoom（而非 Enable-CsUser）预配 SRS 帐户。</span><span class="sxs-lookup"><span data-stu-id="944c3-219">Make sure the SRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Skype for Business Server.</span></span>

- <span data-ttu-id="944c3-220">如果已创建 SRS 帐户，但无法在管理 Web 门户中查看这些帐户，请通过使用 Skype for Business Server 日志记录工具收集服务器日志，同时选择 **MeetingPortal** 组件，然后将这些日志发送给 SRS 支持联系人。</span><span class="sxs-lookup"><span data-stu-id="944c3-220">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Skype for Business Server Logging tool with the **MeetingPortal** component selected, and then send them to your SRS support contact.</span></span>

- <span data-ttu-id="944c3-221">如果已创建 SRS 帐户，但无法查看管理 Web 门户中的帐户，则使用 Fiddler 收集客户端日志，并复制浏览器开发工具中的控制台日志，然后将这些日志发送给 SRS 支持联系人。</span><span class="sxs-lookup"><span data-stu-id="944c3-221">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the client logs using Fiddler, and also copy the console log from the browser development tools, and then send them to your SRS support contact.</span></span> <span data-ttu-id="944c3-222">您还可以修改跟踪级别值，Web.config获取更详细的日志。</span><span class="sxs-lookup"><span data-stu-id="944c3-222">You can also modify the trace level value in the Web.config to get a more detailed log.</span></span>

  ```xml
  <system.diagnostics>
    <switches>
      <!--
      This switch controls logging message levels. 0 implies
      logging is turned off. 1 implies only errors are logged,
      2 implies errors &amp; warnings. 4 is the most detailed.
      -->
      <add name="TraceLevelSwitch" value="3" />
    </switches>
  </system.diagnostics>
  ```

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a><span data-ttu-id="944c3-223">为什么我在管理 Web 门户中看不到 SRS 的状态？</span><span class="sxs-lookup"><span data-stu-id="944c3-223">Why can't I see the status of SRS in the administrative web portal?</span></span>

- <span data-ttu-id="944c3-224">确保 LRSApp 用户帐户已启用 SIP。</span><span class="sxs-lookup"><span data-stu-id="944c3-224">Make sure that the LRSApp user account is SIP-enabled.</span></span>

- <span data-ttu-id="944c3-225">如果仍有问题，请从 D：\Tracing\LRSAdminLogs 收集 SRS 系统中 **Trace.log** 文件，然后将它发送给 \, SRS 支持联系人。</span><span class="sxs-lookup"><span data-stu-id="944c3-225">If you are still having issues, collect the **Trace.log** file in the SRS system from D:\Tracing\LRSAdminLogs\, and then send it to your SRS support contact.</span></span>

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a><span data-ttu-id="944c3-226">为什么我在管理 Web 门户中看不到 SRS 的批量管理菜单？</span><span class="sxs-lookup"><span data-stu-id="944c3-226">Why can't I see the bulk management menus for SRS in the administrative web portal?</span></span>

<span data-ttu-id="944c3-227">确保 LRSApp 用户帐户已启用 SIP，并且属于 LRSPowerUserAdminsGroup 安全组。</span><span class="sxs-lookup"><span data-stu-id="944c3-227">Make sure that the LRSApp user account is SIP-enabled, and is part of the LRSPowerUserAdminsGroup security group.</span></span>

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a><span data-ttu-id="944c3-228">SRS v1 管理 Web 门户是否与 Microsoft Teams 会议室一起工作？</span><span class="sxs-lookup"><span data-stu-id="944c3-228">Does the SRS v1 administrative web portal work with Microsoft Teams Rooms?</span></span>

<span data-ttu-id="944c3-229">否。</span><span class="sxs-lookup"><span data-stu-id="944c3-229">No.</span></span>


