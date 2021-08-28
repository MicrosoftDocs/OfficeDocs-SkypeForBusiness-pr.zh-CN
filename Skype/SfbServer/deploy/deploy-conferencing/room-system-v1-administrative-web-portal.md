---
title: 部署 SRS v1 管理 Web 门户Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: Skype for Business Server Skype Room Systems v1 (SRS v1（以前称为 Lync Room System) Administrative Web Portal）是一个 Web 门户，组织可以使用它来维护其 Skype Room Systems 会议室。 管理员可以使用 SRS v1 管理 Web 门户监视设备运行状况，例如通过监视音频/视频设备。 通过此门户，管理员可以远程收集诊断信息来监视会议室运行状况。
ms.openlocfilehash: 2451d9892bc15b1b1f189a764823c2f9beb019ac
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618128"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a>部署 SRS v1 管理 Web 门户Skype for Business Server

Skype for Business Server Skype Room Systems v1 (SRS v1（以前称为 Lync Room System) Administrative Web Portal）是一个 Web 门户，组织可以使用它来维护其 Skype Room Systems 会议室。 管理员可以使用 SRS v1 管理 Web 门户监视设备运行状况，例如通过监视音频/视频设备。 通过此门户，管理员可以远程收集诊断信息来监视会议室运行状况。

若要使用此功能，需要将 SRS v1 管理 Web 门户部署在前端Skype for Business Server服务器上。 本指南为管理员提供了有关如何安装和配置 SRS 管理 Web 门户的说明。 它适用于了解管理Skype for Business Server并且具有管理员用户权限来修改拓扑Skype for Business Server管理员。

在服务器上部署 SRS v1 管理 Web 门户后，管理员可以通过从自己的计算机或笔记本电脑登录到网站来检查 SRS v1 设备的状态。

> [!IMPORTANT]
> 下载[Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015。](https://www.microsoft.com/download/details.aspx?id=46906)

本主题内容：

- [为 SRS v1 管理 Web 门户配置环境](room-system-v1-administrative-web-portal.md#Config_Env)

- [安装 SRS v1 管理 Web 门户](room-system-v1-administrative-web-portal.md#Install_SRS)

- [使用 SRS 管理 Web 门户](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a>为 SRS v1 管理 Web 门户配置环境
<a name="Config_Env"> </a>

若要使用 SRS v1 管理 Web 门户，您需要安装或配置以下必备组件。

> [!IMPORTANT]
> 如果服务器同时配置了 Kerberos 和 NTLM 身份验证，并且 SRS 正在未加入域的计算机上运行，则 Kerberos 身份验证将失败，并且用户将不会在管理门户中看到 SRS 的状态。 若要解决此问题，请配置具有 NTLM 身份验证的服务器或同时使用 NTLM 和 TLS-DSK 身份验证 (而无需 Kerberos) ，或者将 SRS 计算机加入域。

1. 在Skype for Business Server拓扑中安装累积Skype for Business Server更新。

    若要获取更新或查看它中包含的内容，请参阅[updates for Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。

2. 创建启用 SIP 的 Active Directory 用户。

    SRS v1 管理 Web 门户使用这些凭据从网站Skype for Business Server。 给定示例中的用户名是 LRSApp。

3. 创建名称为 LRSSupportAdminGroup 的 Active Directory 安全组。

    创建组作用域为全局组，组类型为安全组。 添加到该组的启用 SIP 的用户将有权查看聊天室列表并执行某些命令，例如收集日志。

4. 创建名称为 LRSFullAccessAdminGroup 的 Active Directory 安全组。

    创建组作用域为全局组，组类型为安全组。添加到该组的启用 SIP 的用户有权在单个聊天室使用所有管理Skype功能。 若要包含对聊天室的批量Skype支持，请参阅步骤 5。

     ![具有安全组角色的管理员组列表](../../media/LRS_LRSFullAccessAdminGroup.png)

5. 创建名称为 LRSPowerUserAdminsGroup 的 Active Directory 安全组。

    创建组作用域为全局组，组类型为安全组。 添加到此组的启用 SIP 的用户有权使用所有管理门户功能，包括聊天室Skype for Business管理。

6. 将 LRSFullAccessAdminGroup 添加为 LRSSupportAdminGroup 的成员。

     ![LRSSupportAdminGroup 属性成员页](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. 创建名称为 LRSSupport 的启用 SIP 的 Active Directory 用户。 将此用户添加到 LRSSupportAdminGroup。

     ![LRSSupportAdminGroup 属性成员页](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. 安装[ASP.NET 2010 SP1 Visual Studio Visual Web Developer 2010 SP1 的 MVC 4。](https://go.microsoft.com/fwlink/p/?LinkId=323967)

## <a name="install-the-srs-v1-administrative-web-portal"></a>安装 SRS v1 管理 Web 门户
<a name="Install_SRS"> </a>

下载[Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015。](https://www.microsoft.com/download/details.aspx?id=46906)

若要安装 SRS v1 管理 Web 门户，请使用以下步骤。

1. 通过运行命令行管理程序中的以下 cmdlet 配置受信任Skype for Business Server端口：

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. 若要安装 会议室 门户，**请** MeetingRoomPortalInstaller.msi，然后以管理员角色运行它。

3. 从Web.config打开文件：

    %Program Files%\Skype for Business Server 2015\Web Components\会议室 Portal\Int\Handler\

4. 在 Web.Config 文件中，将 PortalUserName 更改为"为[SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)管理 Web 门户配置环境"部分下的步骤 2 中创建的用户名 (步骤中的推荐名称为 LRSApp) ：

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. 由于 SRS v1 管理门户是受信任的应用程序，因此无需在门户配置中提供密码。 如果此用户使用的注册机构与本地注册机构不同，则需要在注册器文件中添加以下行来指定Web.Config注册器：

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. 如果使用的端口不是 5061，则向文件中添加Web.Config行：

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a>验证 SRS 管理 Web 门户的安装

若要验证 SRS v1 管理 Web 门户的安装，请执行下列操作：

1. 在前端服务器上，浏览到以下 URL：

    https:// \<fe-server\> /lrs

    您不应看到任何错误，如下图所示：

     ![Lync 会议室系统管理门户登录屏幕](../../media/LRS_AdminPortalSignIn.png)

2. 如果看不到任何错误，请尝试从拓扑中的其他任何计算机访问以下 URL：

    https:// \<fe-server\> /lrs

    若要访问该页面，您需要添加 DNS 记录，如"自动客户端登录所需的 DNS 记录"[中所述](/previous-versions/office/communications-server/bb663700(v=office.12))。

## <a name="use-the-srs-administrative-web-portal"></a>使用 SRS 管理 Web 门户
<a name="Use_Portal"> </a>

在服务器上部署 SRS 后，可以通过从浏览器登录 SRS v1 管理 Web 门户来检查所有 SRS 会议室的状态。

### <a name="sign-in"></a>登录

1. 浏览到以下 URL：

    https:// \<fe-server\> /lrs

2. 输入 LRSSupport 帐户或已添加到 LRSSupportAdminGroup 安全组的帐户的凭据。

![Lync 会议室系统管理门户登录屏幕](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a>SRS 管理 Web 门户摘要页

摘要页提供了服务器上部署的所有 SRS 会议室的以下信息：

- **Tag** 管理员为会议室提供自定义名称。 可以通过单击会议室名称在门户中设置 Tag。

- **运行状况** 聊天室的运行状况状态，派生自会议室的"聚合运行状况"状态，显示在"会议室运行状况"页的"运行状况"设置下。

- **下一次会议** 安排下一次会议的日期和时间。

- **SRS 版本、制造商、型号** 这些值在 SRS 中预设。 根据制造商，这些字段可能保留为空。

- **上次刷新** 显示上次刷新网页的时间。

![Lync 会议室系统管理门户摘要视图](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> 只有属于 LRSPowerUserAdminsGroup 安全组的一部分，才能看到"批量管理"菜单。

### <a name="srs-room-information"></a>SRS 会议室信息

门户的"会议室信息"部分允许你查看和配置各个 SRS 会议室。 它包含四个部分：设置、详细信息、日志记录和运行状况。

#### <a name="settings"></a>设置

在设置部分中，你可以设置会议室的密码、会议室标记和默认音量级别。 如果配置这些设置，则仅在重新启动 SRS 控制台后复制更改。 你将仅看到使用版本 15.12 及更高版本的 SRS 设备的系统更新设置。

![Lync 会议室系统管理门户设置](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a>详细信息

"详细信息"部分提供 SRS 会议室设置的只读摘要，包括：上次刷新的时间;下一次会议;上次更新、维护和校准;默认扬声器、麦克风和响铃设置;version;SIP URI;屏幕数和有关每个屏幕的详细信息;状态和活动。

![Lync 会议室系统管理门户详细信息视图](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a>疑难解答

疑难解答部分可用于远程收集日志并将其保存到指定位置。 还可以在 SRS 用户界面 (SRS 控制台) 或重新启动整个系统。 若要收集日志，请提供指定格式的文件夹路径，并确保该文件夹具有为 SRS 计算机帐户提供的写入权限。 如果日志大小太大，可能需要 5 分钟才能完成日志收集。 刷新页面将为您提供最新状态。

#### <a name="health"></a>健康

"运行状况"部分直观指示连接、音频Skype for Business Server、视频设备、恢复能力状态和屏幕设备的运行状况。

![Lync 会议室系统管理门户聊天室运行状况](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a>有关管理 Web 门户的其他说明

> [!NOTE]
>  设置更改仅在重新启动 SRS 系统后应用。> 如果 LRSApp 帐户密码过期，你将看不到会议室的状态。 将 LRSAppuser 帐户密码配置为永不过期，或确保在密码即将过期时更新密码。>仅支持本地部署使用 SRS 管理 Web 门户。

### <a name="bulk-management"></a>批量管理

SRS 聊天室的批量管理是专为高级 IT 管理员设计的一项功能，用于简化其工作流，并使他们能够使用节省时间的便捷工具以批量方式远程管理多个会议室。

为了看到此功能，需要将用户预配为特殊安全组 **LRSPowerUserAdminsGroup** 的成员。

可以选择进行批量管理的 SRS 会议室数量没有限制。 但是，一次只能执行一个批量管理操作。

若要执行批量管理操作，请选择要监视的聊天室，然后单击"批量管理"菜单。

### <a name="frequently-asked-questions"></a>常见问题解答

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>为什么我无法登录管理 Web 门户？

打开 时，你将能够看到登录页，但当你键入凭据时 https://localhost/lrs ，你无法登录。 在这种情况下，必须打开 https://FQDNofFEserver/SRS 以登录到管理 Web 门户。

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a>为什么我在管理 Web 门户中看不到 SRS v1？

- 确保部署中具有 SRS 帐户，并且这些帐户是按照 SRS 管理 Web 门户部署建议创建的。 请确保使用 Enable-CsMeetingRoom（而不是 Enable-CsUser）预配 SRS Skype for Business Server。

- 如果已创建 SRS 帐户，但无法在管理 Web 门户中查看这些帐户，请通过使用 Skype for Business Server 日志记录工具（选择 **MeetingPortal** 组件）收集服务器日志，然后将这些日志发送到 SRS 支持联系人。

- 如果已创建 SRS 帐户，但无法在管理 Web 门户中查看这些帐户，则使用 Fiddler 收集客户端日志，并复制浏览器开发工具中的控制台日志，然后将这些日志发送给 SRS 支持联系人。 还可以修改跟踪级别值Web.config获取更详细的日志。

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

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a>为什么我在管理 Web 门户中看不到 SRS 的状态？

- 确保 LRSApp 用户帐户已启用 SIP。

- 如果仍有问题，请从 D：\Tracing\LRSAdminLogs 收集 SRS 系统中 **Trace.log** 文件，然后将它发送给 \, SRS 支持联系人。

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a>为什么我在管理 Web 门户中看不到 SRS 的批量管理菜单？

确保 LRSApp 用户帐户已启用 SIP，并且属于 LRSPowerUserAdminsGroup 安全组。

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a>SRS v1 管理 Web 门户是否与 Microsoft Teams 会议室？

不需要。