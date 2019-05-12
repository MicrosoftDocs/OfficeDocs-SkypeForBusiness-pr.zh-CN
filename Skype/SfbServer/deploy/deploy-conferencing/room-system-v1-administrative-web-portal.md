---
title: 为业务服务器部署中 Skype SR v1 管理 Web 门户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: 为业务服务器 Skype 会议室系统 v1 Skype (SR v1、 之前被称为 Lync 会议室系统) 管理 Web 门户是以便组织用来维护其 Skype 会议室系统会议室的 web 门户。 管理员可以使用 SR v1 管理 Web 门户以进行监视，设备运行状况，例如监视音频/视频设备。 与此门户，管理员可以远程收集诊断信息来监视会议室内运行状况。
ms.openlocfilehash: ee94db48470747999b2554732bc03d72d129adbd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895066"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a><span data-ttu-id="afc33-105">为业务服务器部署中 Skype SR v1 管理 Web 门户</span><span class="sxs-lookup"><span data-stu-id="afc33-105">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>

<span data-ttu-id="afc33-106">为业务服务器 Skype 会议室系统 v1 Skype (SR v1、 之前被称为 Lync 会议室系统) 管理 Web 门户是以便组织用来维护其 Skype 会议室系统会议室的 web 门户。</span><span class="sxs-lookup"><span data-stu-id="afc33-106">The Skype for Business Server Skype Room Systems v1 (SRS v1, formerly known as Lync Room System) Administrative Web Portal is a web portal that organizations can use to maintain their Skype Room Systems conference rooms.</span></span> <span data-ttu-id="afc33-107">管理员可以使用 SR v1 管理 Web 门户以进行监视，设备运行状况，例如监视音频/视频设备。</span><span class="sxs-lookup"><span data-stu-id="afc33-107">Administrators can use the SRS v1 Administrative Web Portal to monitor device health, for example by monitoring audio/video devices.</span></span> <span data-ttu-id="afc33-108">与此门户，管理员可以远程收集诊断信息来监视会议室内运行状况。</span><span class="sxs-lookup"><span data-stu-id="afc33-108">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="afc33-109">若要使用此功能，需要为业务 Server 前端服务器部署在每个 Skype SR v1 管理 Web 门户。</span><span class="sxs-lookup"><span data-stu-id="afc33-109">To use this feature, the SRS v1 Administrative Web Portal needs to be deployed on every Skype for Business Server Front End Server.</span></span> <span data-ttu-id="afc33-110">本指南面向管理员提供有关如何安装和配置 SRS 管理 Web 门户的说明。</span><span class="sxs-lookup"><span data-stu-id="afc33-110">This guide provides instructions for administrators on how to install and configure the SRS Administrative Web Portal.</span></span> <span data-ttu-id="afc33-111">这被专为管理员拥有业务服务器管理，Skype 的知识和谁具有管理员用户权限，才能修改企业服务器拓扑的 Skype。</span><span class="sxs-lookup"><span data-stu-id="afc33-111">It is intended for administrators who have knowledge of Skype for Business Server administration, and who have administrator user rights to modify the Skype for Business Server topology.</span></span>

<span data-ttu-id="afc33-112">之后的服务器部署管理 Web 门户 SR v1，管理员可以通过从其自己的计算机或便携式计算机登录到网站检查状态 SR v1 设备。</span><span class="sxs-lookup"><span data-stu-id="afc33-112">After the SRS v1 Administrative Web Portal is deployed on the server, administrators can check the status SRS v1 devices by logging on to the site from their own computers or laptops.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="afc33-113">下载[Microsoft Skype 会议室业务服务器 2015 Skype 系统 v1 管理 Web 门户](https://www.microsoft.com/en-us/download/details.aspx?id=46906)。</span><span class="sxs-lookup"><span data-stu-id="afc33-113">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="afc33-114">在本主题中：</span><span class="sxs-lookup"><span data-stu-id="afc33-114">In this topic:</span></span>

- [<span data-ttu-id="afc33-115">针对 SRS v1 管理 Web 门户配置你的环境</span><span class="sxs-lookup"><span data-stu-id="afc33-115">Configure your environment for the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Config_Env)

- [<span data-ttu-id="afc33-116">安装 SRS v1 管理 Web 门户</span><span class="sxs-lookup"><span data-stu-id="afc33-116">Install the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Install_SRS)

- [<span data-ttu-id="afc33-117">使用 SRS 管理 Web 门户</span><span class="sxs-lookup"><span data-stu-id="afc33-117">Use the SRS Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="afc33-118">针对 SRS v1 管理 Web 门户配置你的环境</span><span class="sxs-lookup"><span data-stu-id="afc33-118">Configure your environment for the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="afc33-119"><a name="Config_Env"> </a></span><span class="sxs-lookup"><span data-stu-id="afc33-119"></span></span>

<span data-ttu-id="afc33-120">要使用 SRS v1 管理 Web 门户，你将需要安装或配置以下先决条件。</span><span class="sxs-lookup"><span data-stu-id="afc33-120">To use the SRS v1 Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="afc33-p104">如果服务器同时配置了 Kerberos 和 NTLM 身份验证，并且 SRS 在未加入域的计算机上运行，则 Kerberos 身份验证将会失败，并且用户在管理门户中看不到 SRS 的状态。要解决此问题，请为服务器配置 NTLM 身份验证或者同时配置 NTLM 和 TLS-DSK 身份验证（无 Kerberos），或者将 SRS 计算机加入域。</span><span class="sxs-lookup"><span data-stu-id="afc33-p104">If the server is configured with both Kerberos and NTLM authentication, and SRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of SRS in the administrative portal. To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the SRS computer to the domain.</span></span>

1. <span data-ttu-id="afc33-123">安装 Business Server 累积更新中的企业服务器拓扑 Skype Skype。</span><span class="sxs-lookup"><span data-stu-id="afc33-123">Install Skype for Business Server Cumulative Updates in the Skype for Business Server topology.</span></span>

    <span data-ttu-id="afc33-124">若要获取更新或参阅与其具有包含的内容，请参阅[更新业务服务器 2015年的 Skype](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)。</span><span class="sxs-lookup"><span data-stu-id="afc33-124">To get the update or see what's included with it, see [Updates for Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

2. <span data-ttu-id="afc33-125">创建启用了 SIP 的 Active Directory 用户。</span><span class="sxs-lookup"><span data-stu-id="afc33-125">Create a SIP-enabled Active Directory user.</span></span>

    <span data-ttu-id="afc33-126">SR v1 管理 Web 门户使用这些凭据查询信息从 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="afc33-126">The SRS v1 Administrative Web Portal uses these credentials to query information from Skype for Business Server.</span></span> <span data-ttu-id="afc33-127">给定示例中的用户名是 LRSApp。</span><span class="sxs-lookup"><span data-stu-id="afc33-127">The username in the examples given is LRSApp.</span></span>

3. <span data-ttu-id="afc33-128">创建名称为 LRSSupportAdminGroup 的 Active Directory 安全组。</span><span class="sxs-lookup"><span data-stu-id="afc33-128">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>

    <span data-ttu-id="afc33-p106">创建“组作用域”为“全局”、“组类型”为“安全”的组。添加到此组启用了 SIP 的用户将被授权查看聊天室列表并执行特定命令（例如收集日志）。</span><span class="sxs-lookup"><span data-stu-id="afc33-p106">Create the group with Group Scope as Global and Group Type as Security. SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4. <span data-ttu-id="afc33-131">创建名称为 LRSFullAccessAdminGroup 的 Active Directory 安全组。</span><span class="sxs-lookup"><span data-stu-id="afc33-131">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>

    <span data-ttu-id="afc33-p107">创建“组作用域”为“全局”、“组类型”为“安全”的组。添加到此组、启用了 SIP 的用户将被授权在单个 Skype 会议室中使用所有管理门户功能。要支持对 Skype 会议室进行批量管理，请参阅步骤 5。</span><span class="sxs-lookup"><span data-stu-id="afc33-p107">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality on a single Skype room. To include support for bulk management of Skype rooms, refer to step 5.</span></span>

     ![具有安全组角色的 Admin 组的列表](../../media/LRS_LRSFullAccessAdminGroup.png)

5. <span data-ttu-id="afc33-135">创建名称为 LRSPowerUserAdminsGroup 的 Active Directory 安全组。</span><span class="sxs-lookup"><span data-stu-id="afc33-135">Create an Active Directory security group with name LRSPowerUserAdminsGroup.</span></span>

    <span data-ttu-id="afc33-136">创建“组作用域”为“全局”、“组类型”为“安全”的组。</span><span class="sxs-lookup"><span data-stu-id="afc33-136">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="afc33-137">启用了 SIP 的用户添加到此组有权使用包括 Skype 批量管理业务聊天室的所有管理门户功能。</span><span class="sxs-lookup"><span data-stu-id="afc33-137">SIP enabled users who are added to this group are authorized to use all admin portal functionality including bulk management of Skype for Business rooms.</span></span>

6. <span data-ttu-id="afc33-138">将 LRSFullAccessAdminGroup 添加为 LRSSupportAdminGroup 的成员。</span><span class="sxs-lookup"><span data-stu-id="afc33-138">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>

     ![LRSSupportAdminGroup 属性 -“成员”页](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. <span data-ttu-id="afc33-140">创建名称为 LRSSupport 的启用了 SIP 的 Active Directory 用户。</span><span class="sxs-lookup"><span data-stu-id="afc33-140">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="afc33-141">将此用户添加到 LRSSupportAdminGroup。</span><span class="sxs-lookup"><span data-stu-id="afc33-141">Add this user to LRSSupportAdminGroup.</span></span>

     ![LRSSupportAdminGroup 属性 -“成员”页](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. <span data-ttu-id="afc33-143">安装[ASP.NET MVC 4 的 Visual Studio 2010 SP1 和可视 Web 开发人员 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967)。</span><span class="sxs-lookup"><span data-stu-id="afc33-143">Install [ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span></span>

## <a name="install-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="afc33-144">安装 SRS v1 管理 Web 门户</span><span class="sxs-lookup"><span data-stu-id="afc33-144">Install the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="afc33-145"><a name="Install_SRS"> </a></span><span class="sxs-lookup"><span data-stu-id="afc33-145"></span></span>

<span data-ttu-id="afc33-146">下载[Microsoft Skype 会议室业务服务器 2015 Skype 系统 v1 管理 Web 门户](https://www.microsoft.com/en-us/download/details.aspx?id=46906)。</span><span class="sxs-lookup"><span data-stu-id="afc33-146">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="afc33-147">要安装 SRS v1 管理 Web 门户，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="afc33-147">To install the SRS v1 Administrative Web Portal, use the following steps.</span></span>

1. <span data-ttu-id="afc33-148">通过运行以下 cmdlet 中 Skype 业务 Server 命令行管理程序配置受信任应用程序端口：</span><span class="sxs-lookup"><span data-stu-id="afc33-148">Configure the Trusted Application Port by running the following cmdlet in Skype for Business Server Management Shell:</span></span>

   ```
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. <span data-ttu-id="afc33-149">要安装会议室门户，请下载 **MeetingRoomPortalInstaller.msi**，然后以管理员身份运行它。</span><span class="sxs-lookup"><span data-stu-id="afc33-149">To install the Meeting Room Portal, download **MeetingRoomPortalInstaller.msi** and then run it as an administrator.</span></span>

3. <span data-ttu-id="afc33-150">打开以下位置中的 Web.config 文件：</span><span class="sxs-lookup"><span data-stu-id="afc33-150">Open the Web.config file from the following location:</span></span>

    <span data-ttu-id="afc33-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler\\</span><span class="sxs-lookup"><span data-stu-id="afc33-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler\\</span></span>

4. <span data-ttu-id="afc33-152">在 Web.Config 文件中，更改为在步骤 2 中创建在部分的"[配置您的环境 SR v1 管理 Web 门户的](room-system-v1-administrative-web-portal.md#Config_Env)"（步骤中建议的名称是 LRSApp） 下 username PortalUserName:</span><span class="sxs-lookup"><span data-stu-id="afc33-152">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section "[Configure your environment for the SRS v1 Administrative Web Portal](room-system-v1-administrative-web-portal.md#Config_Env)" (the recommended name in the step is LRSApp):</span></span>

    ```
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. <span data-ttu-id="afc33-p110">由于 SRS v1 管理门户是受信任的应用，你不必在门户配置中提供密码。如果此用户使用的是非本地注册器，你需要通过在 Web.Config 文件中添加以下行来为其指定注册器：</span><span class="sxs-lookup"><span data-stu-id="afc33-p110">Because the SRS v1 Admin Portal is a trusted application, you do not need to provide the password in the portal configuration. If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>

   ```
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. <span data-ttu-id="afc33-155">如果使用的端口不是 5061，则需要在 Web.Config 文件中添加以下行：</span><span class="sxs-lookup"><span data-stu-id="afc33-155">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>

   ```
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a><span data-ttu-id="afc33-156">验证 SRS 管理 Web 门户的安装</span><span class="sxs-lookup"><span data-stu-id="afc33-156">Verify Installation of the SRS Administrative Web Portal</span></span>

<span data-ttu-id="afc33-157">要验证 SRS v1 管理 Web 门户的安装，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="afc33-157">To verify installation of the SRS v1 Administrative Web Portal, do the following:</span></span>

1. <span data-ttu-id="afc33-158">在前端服务器上，浏览至以下 URL：</span><span class="sxs-lookup"><span data-stu-id="afc33-158">On a Front End server, browse to the following URL:</span></span>

    <span data-ttu-id="afc33-159">https://\<fe 服务器\>/lrs</span><span class="sxs-lookup"><span data-stu-id="afc33-159">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="afc33-160">你不应该看到任何错误，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="afc33-160">You should not see any errors, as shown in the following image:</span></span>

     ![Lync 聊天室系统管理门户登录屏幕](../../media/LRS_AdminPortalSignIn.png)

2. <span data-ttu-id="afc33-162">如果你未看到任何错误，请尝试从拓扑中的任何其他计算机访问以下 URL：</span><span class="sxs-lookup"><span data-stu-id="afc33-162">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>

    <span data-ttu-id="afc33-163">https://\<fe 服务器\>/lrs</span><span class="sxs-lookup"><span data-stu-id="afc33-163">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="afc33-164">若要访问页上，您需要添加的 DNS 记录，如"[所需的自动客户端登录的 DNS 记录](https://go.microsoft.com/fwlink/p/?LinkId=318056)"中所述</span><span class="sxs-lookup"><span data-stu-id="afc33-164">To access the page, you will need to add the DNS records as described in "[Required DNS Records for Automatic Client Sign-In](https://go.microsoft.com/fwlink/p/?LinkId=318056)."</span></span>

## <a name="use-the-srs-administrative-web-portal"></a><span data-ttu-id="afc33-165">使用 SRS 管理 Web 门户</span><span class="sxs-lookup"><span data-stu-id="afc33-165">Use the SRS Administrative Web Portal</span></span>
<span data-ttu-id="afc33-166"><a name="Use_Portal"> </a></span><span class="sxs-lookup"><span data-stu-id="afc33-166"></span></span>

<span data-ttu-id="afc33-167">在服务器上部署 SRS 之后，你可以通过从浏览器登录到 SRS v1 管理 Web 门户来检查所有 SRS 会议室的状态。</span><span class="sxs-lookup"><span data-stu-id="afc33-167">After you deploy SRS on the server, you can check the status of all SRS rooms by signing into the SRS v1 Administrative Web Portal from a browser.</span></span>

### <a name="sign-in"></a><span data-ttu-id="afc33-168">登录</span><span class="sxs-lookup"><span data-stu-id="afc33-168">Sign in</span></span>

1. <span data-ttu-id="afc33-169">浏览到以下 URL：</span><span class="sxs-lookup"><span data-stu-id="afc33-169">Browse to the following URL:</span></span>

    <span data-ttu-id="afc33-170">https://\<fe 服务器\>/lrs</span><span class="sxs-lookup"><span data-stu-id="afc33-170">https://\<fe-server\>/lrs</span></span>

2. <span data-ttu-id="afc33-171">输入 LRSSupport 帐户或者已添加到 LRSSupportAdminGroup 安全组的帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="afc33-171">Enter the credentials for the LRSSupport account or an account that was added to the LRSSupportAdminGroup security group.</span></span>

![Lync 聊天室系统管理门户登录屏幕](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a><span data-ttu-id="afc33-173">SRS 管理 Web 门户摘要页面</span><span class="sxs-lookup"><span data-stu-id="afc33-173">SRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="afc33-174">摘要页面为服务器上部署的所有 SRS 会议室提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="afc33-174">The summary page provides the following information for all of the SRS rooms deployed on the server:</span></span>

- <span data-ttu-id="afc33-175">**标记**聊天室管理员提供自定义名称。</span><span class="sxs-lookup"><span data-stu-id="afc33-175">**Tag** The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="afc33-176">可以通过在门户中单击会议室名称来设置标记。</span><span class="sxs-lookup"><span data-stu-id="afc33-176">The Tag can be set in the portal by clicking on the room name.</span></span>

- <span data-ttu-id="afc33-177">**运行状况**运行状况状态的聊天室，派生的聊天室，显示在聊天室设置页的运行状况部分的聚合健康状态。</span><span class="sxs-lookup"><span data-stu-id="afc33-177">**Health** The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

- <span data-ttu-id="afc33-178">**下次会议**计划的日期和时间在下次会议。</span><span class="sxs-lookup"><span data-stu-id="afc33-178">**Next Meeting** The date and time the next meeting is scheduled.</span></span>

- <span data-ttu-id="afc33-179">**SR 版本，制造商，模型**这些值是在 SR 预设的。</span><span class="sxs-lookup"><span data-stu-id="afc33-179">**SRS Version, Manufacturer, Model** These values are preset in SRS.</span></span> <span data-ttu-id="afc33-180">根据制造商，这些字段可能留空。</span><span class="sxs-lookup"><span data-stu-id="afc33-180">Depending on the manufacturer, these fields might be left blank.</span></span>

- <span data-ttu-id="afc33-181">**上次刷新**显示的上次刷新网页。</span><span class="sxs-lookup"><span data-stu-id="afc33-181">**Last Refresh** Displays the last time the web page was refreshed.</span></span>

![Lync 聊天室系统管理门户摘要视图](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> <span data-ttu-id="afc33-183">如果您是 LRSPowerUserAdminsGroup 安全组的一部分，将只能看到批量管理菜单。</span><span class="sxs-lookup"><span data-stu-id="afc33-183">You will only see the Bulk Management menu if you are part of the LRSPowerUserAdminsGroup security group.</span></span>

### <a name="srs-room-information"></a><span data-ttu-id="afc33-184">SRS 会议室信息</span><span class="sxs-lookup"><span data-stu-id="afc33-184">SRS Room Information</span></span>

<span data-ttu-id="afc33-p113">在门户的“会议室信息”部分可以查看和配置各个 SRS 会议室。它包含四个部分：设置、详细信息、日志记录和运行状况。</span><span class="sxs-lookup"><span data-stu-id="afc33-p113">The Room Info section of the portal allows you to view and configure individual SRS rooms. It contains four sections: Settings, Details, Logging, and Health.</span></span>

#### <a name="settings"></a><span data-ttu-id="afc33-187">设置</span><span class="sxs-lookup"><span data-stu-id="afc33-187">Settings</span></span>

<span data-ttu-id="afc33-p114">在“设置”部分中，你可以设置会议室的密码、会议室标记和默认音量大小。如果配置这些设置，只会在你重新启动 SRS 控制台之后复制更改。对于使用 15.12 及更高版本的 SRS 设备，你将只会看到“系统更新”设置。</span><span class="sxs-lookup"><span data-stu-id="afc33-p114">In the Settings section, you can set the password, room tag, and default volume levels for the room. If you configure these settings, the changes are replicated only after you restart the SRS console. You will only see System Updates settings for SRS devices using release 15.12 and later.</span></span>

![Lync 聊天室系统管理门户聊天室设置](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a><span data-ttu-id="afc33-192">详细信息</span><span class="sxs-lookup"><span data-stu-id="afc33-192">Details</span></span>

<span data-ttu-id="afc33-193">详细信息部分中提供的 SR 会议室的设置，包括只读摘要： 上次刷新; 的时间下次会议;上次更新、 维护和校准;默认扬声器和麦克风，铃声设置;版本;SIP URI;屏幕和每个屏幕; 有关详细信息的数量状态和活动。</span><span class="sxs-lookup"><span data-stu-id="afc33-193">The Details section provides a read-only summary of the SRS room's settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

![Lync 聊天室系统管理门户详细信息视图](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a><span data-ttu-id="afc33-195">疑难解答</span><span class="sxs-lookup"><span data-stu-id="afc33-195">Troubleshooting</span></span>

<span data-ttu-id="afc33-p115">“疑难解答”部分可用于远程收集日志并将它们保存到指定位置。你还可以重新启动 SRS 控制台（SRS 用户界面）或重新启动整个系统。要收集日志，请按指定格式提供文件夹路径，并确保为 SRS 计算机帐户提供了写入该文件夹的权限。如果日志太大，可能需要长达 5 分钟才能完成日志的收集。刷新页面将显示最新状态。</span><span class="sxs-lookup"><span data-stu-id="afc33-p115">The Troubleshooting section can be used to remotely collect logs and save them to a specified location. You can also restart the SRS console (SRS user interface) or restart the entire system. To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the SRS machine account. If the log size is too big, it can take up to 5 minutes to finish collecting logs. Refreshing the page will give you the latest status.</span></span>

#### <a name="health"></a><span data-ttu-id="afc33-201">运行状况</span><span class="sxs-lookup"><span data-stu-id="afc33-201">Health</span></span>

<span data-ttu-id="afc33-202">运行状况部分提供了直观的指示 Business Server 连接、 音频设备、 视频设备、 恢复能力状态和屏幕设备的 Skype 的运行状况。</span><span class="sxs-lookup"><span data-stu-id="afc33-202">The Health section gives a visual indication of the health of the Skype for Business Server connection, audio device, video device, resiliency state, and screen device.</span></span>

![Lync 聊天室系统管理门户聊天室运行状况](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="afc33-204">有关管理 Web 门户的其他说明</span><span class="sxs-lookup"><span data-stu-id="afc33-204">Additional Notes about the Administrative Web Portal</span></span>

> [!NOTE]
>  <span data-ttu-id="afc33-205">仅后 SR 系统 LRSApp 帐户密码过期时重新启动的.> 应用设置更改，您将无法查看聊天室的状态。</span><span class="sxs-lookup"><span data-stu-id="afc33-205">Setting changes are applied only after the SRS system is restarted.>  If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="afc33-206">配置 LRSAppuser 帐户密码，以便它永远不会过期，或确保时附近 expiration.> SR 管理 web 门户支持仅限本地部署的更新的密码。</span><span class="sxs-lookup"><span data-stu-id="afc33-206">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it is near expiration.>  The SRS administrative web portal is supported for on-premises deployments only.</span></span>

### <a name="bulk-management"></a><span data-ttu-id="afc33-207">批量管理 </span><span class="sxs-lookup"><span data-stu-id="afc33-207">Bulk management</span></span>

<span data-ttu-id="afc33-208">SRS 会议室批量管理是一项专门面向高级 IT 管理员的功能，用于简化其工作流，使他们能够通过一个节省时间的便利工具来以批量方式远程管理多个会议室。</span><span class="sxs-lookup"><span data-stu-id="afc33-208">Bulk management of SRS rooms is a feature designed for advanced IT administrators, to simplify their workflow, and enable them with a time-saving convenient tool to remotely manage multiple rooms in a bulk fashion.</span></span>

<span data-ttu-id="afc33-209">用户要看到此功能，需要设置为特殊安全组 **LRSPowerUserAdminsGroup** 的成员。</span><span class="sxs-lookup"><span data-stu-id="afc33-209">In order to see this functionality, the user need to be provisioned as a member of the special security group, **LRSPowerUserAdminsGroup**.</span></span>

<span data-ttu-id="afc33-p117">可以选择进行批量管理的 SRS 会议室数没有限制。但一次只能执行一个批量管理操作。</span><span class="sxs-lookup"><span data-stu-id="afc33-p117">There is no limit to the number of SRS rooms you can select for bulk management. However, you can perform only one bulk management operation at a time.</span></span>

<span data-ttu-id="afc33-212">要执行批量管理操作，请选择要监视的会议室，并单击“批量管理”菜单。</span><span class="sxs-lookup"><span data-stu-id="afc33-212">To perform a bulk management operation, select the rooms you want to monitor, and click on the Bulk management menu.</span></span>

### <a name="frequently-asked-questions"></a><span data-ttu-id="afc33-213">常见问题</span><span class="sxs-lookup"><span data-stu-id="afc33-213">Frequently asked questions</span></span>

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="afc33-214">为什么我无法登录到管理 web 门户？</span><span class="sxs-lookup"><span data-stu-id="afc33-214">Why can't I sign in to the administrative web portal?</span></span>

<span data-ttu-id="afc33-215">当您打开https://localhost/lrs，您将能够看到登录页上，但时您键入您的凭据，因此您无法登录。</span><span class="sxs-lookup"><span data-stu-id="afc33-215">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="afc33-216">在这种情况下，必须打开https://FQDNofFEserver/SRSto sign in to 管理 web 门户。</span><span class="sxs-lookup"><span data-stu-id="afc33-216">In this case, you must open https://FQDNofFEserver/SRS to sign in to the administrative web portal.</span></span>

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a><span data-ttu-id="afc33-217">为什么看不到 SR v1 管理 web 门户中？</span><span class="sxs-lookup"><span data-stu-id="afc33-217">Why can't I see SRS v1 in the administrative web portal?</span></span>

- <span data-ttu-id="afc33-218">确保你的部署中有 SRS 帐户，并且它们是按照 SRS 管理 Web 门户部署建议创建的。</span><span class="sxs-lookup"><span data-stu-id="afc33-218">Make sure you have SRS accounts in your deployment and that they are created according to the SRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="afc33-219">请确保使用业务服务器 Skype Enable-csmeetingroom，不启用 CsUser，设置 SR 帐户。</span><span class="sxs-lookup"><span data-stu-id="afc33-219">Make sure the SRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Skype for Business Server.</span></span>

- <span data-ttu-id="afc33-220">如果您创建了 SR 帐户，不能查看管理 web 门户中的帐户，使用 Skype 业务服务器日志记录工具与所选， **MeetingPortal**组件收集服务器日志，然后将它们发送到您的 SR 支持联系人。</span><span class="sxs-lookup"><span data-stu-id="afc33-220">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Skype for Business Server Logging tool with the **MeetingPortal** component selected, and then send them to your SRS support contact.</span></span>

- <span data-ttu-id="afc33-p120">如果你已创建 SRS 帐户，但是在管理 Web 门户中看不到这些帐户，请使用 Fiddler 来收集客户端日志，并从浏览器开发工具复制控制台日志，然后将它们发送给你的 SRS 支持联系人。你还可以在 Web.config 中修改跟踪级别值以获取更详细的日志。</span><span class="sxs-lookup"><span data-stu-id="afc33-p120">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the client logs using Fiddler, and also copy the console log from the browser development tools, and then send them to your SRS support contact. You can also modify the trace level value in the Web.config to get a more detailed log.</span></span>

  ```
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

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a><span data-ttu-id="afc33-223">为什么看不到 SR 管理 web 门户中的状态？</span><span class="sxs-lookup"><span data-stu-id="afc33-223">Why can't I see the status of SRS in the administrative web portal?</span></span>

- <span data-ttu-id="afc33-224">请确保 LRSApp 用户帐户已启用 SIP。</span><span class="sxs-lookup"><span data-stu-id="afc33-224">Make sure that the LRSApp user account is SIP-enabled.</span></span>

- <span data-ttu-id="afc33-225">如果您仍然存在问题，收集**Trace.log**文件 SR 系统中从 D:\Tracing\LRSAdminLogs\, ，然后将其发送到您的 SR 支持联系人。</span><span class="sxs-lookup"><span data-stu-id="afc33-225">If you are still having issues, collect the **Trace.log** file in the SRS system from D:\Tracing\LRSAdminLogs\, and then send it to your SRS support contact.</span></span>

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a><span data-ttu-id="afc33-226">为什么我看不批量管理菜单的 SR 管理 web 门户中？</span><span class="sxs-lookup"><span data-stu-id="afc33-226">Why can't I see the bulk management menus for SRS in the administrative web portal?</span></span>

<span data-ttu-id="afc33-227">请确保 LRSApp 用户帐户已启用 SIP，并且是 LRSPowerUserAdminsGroup 安全组的一部分。</span><span class="sxs-lookup"><span data-stu-id="afc33-227">Make sure that the LRSApp user account is SIP-enabled, and is part of the LRSPowerUserAdminsGroup security group.</span></span>

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a><span data-ttu-id="afc33-228">SR v1 管理 web 门户使用 Microsoft 团队聊天室？</span><span class="sxs-lookup"><span data-stu-id="afc33-228">Does the SRS v1 administrative web portal work with Microsoft Teams Rooms?</span></span>

<span data-ttu-id="afc33-229">否。</span><span class="sxs-lookup"><span data-stu-id="afc33-229">No.</span></span>


