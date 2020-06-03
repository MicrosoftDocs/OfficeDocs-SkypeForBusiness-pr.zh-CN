---
title: 在 Skype for Business Server 中部署 SRS v1 管理 Web 门户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: Skype for business Server Skype 会议室系统 v1 （SRS v1，以前称为 Lync 会议室系统）管理 Web 门户是一个 Web 门户，组织可以使用它来维护其 Skype 会议室系统会议室。 管理员可以使用 SRS v1 管理 Web 门户监视设备运行状况，例如通过监视音频/视频设备。 通过此门户，管理员可以远程收集诊断信息，以监视会议室运行状况。
ms.openlocfilehash: d718adb60437fdd7e08724a5ba5fc48fa120425e
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2020
ms.locfileid: "42045895"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a>在 Skype for Business Server 中部署 SRS v1 管理 Web 门户

Skype for business Server Skype 会议室系统 v1 （SRS v1，以前称为 Lync 会议室系统）管理 Web 门户是一个 Web 门户，组织可以使用它来维护其 Skype 会议室系统会议室。 管理员可以使用 SRS v1 管理 Web 门户监视设备运行状况，例如通过监视音频/视频设备。 通过此门户，管理员可以远程收集诊断信息，以监视会议室运行状况。

若要使用此功能，需要在每个 Skype for Business Server 前端服务器上部署 SRS v1 管理 Web 门户。 本指南为管理员提供了有关如何安装和配置 SRS 管理 Web 门户的说明。 它适用于了解 Skype for business Server 管理的管理员，以及拥有修改 Skype for Business Server 拓扑的管理员用户权限的人员。

在服务器上部署 SRS v1 管理 Web 门户后，管理员可以通过从其自己的计算机或笔记本登录网站来检查状态 SRS v1 设备。

> [!IMPORTANT]
> 下载[适用于 Skype for Business Server 2015 的 Microsoft Skype 会议室 Systems V1 管理 Web 门户](https://www.microsoft.com/download/details.aspx?id=46906)。

本主题内容：

- [为 SRS v1 管理 Web 门户配置你的环境](room-system-v1-administrative-web-portal.md#Config_Env)

- [安装 SRS v1 管理 Web 门户](room-system-v1-administrative-web-portal.md#Install_SRS)

- [使用 SRS 管理 Web 门户](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a>为 SRS v1 管理 Web 门户配置你的环境
<a name="Config_Env"> </a>

若要使用 SRS v1 管理 Web 门户，你将需要安装或配置以下必备组件。

> [!IMPORTANT]
> 如果服务器配置了 Kerberos 和 NTLM 身份验证，而 SRS 在未加入域的计算机上运行，则 Kerberos 身份验证将失败，用户在管理门户中将看不到 SRS 的状态。 若要解决此问题，请将服务器配置为使用 NTLM 身份验证或 NTLM 和 TLS DSK 身份验证（不使用 Kerberos），或将 SRS 计算机加入域。

1. 在 Skype for business Server 拓扑中安装 Skype for Business Server 累积更新。

    若要获取更新或查看它所包含的内容，请参阅[Skype for Business Server 2015 更新](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。

2. 创建启用了 SIP 的 Active Directory 用户。

    SRS v1 管理 Web 门户使用这些凭据来查询 Skype for Business Server 中的信息。 给定示例中的用户名为 LRSApp。

3. 创建名称为 LRSSupportAdminGroup 的 Active Directory 安全组。

    创建组作用域为 "全局" 和 "组类型" 作为 "安全" 的组。 添加到此组的启用 SIP 的用户将被授权查看聊天室列表并执行某些命令，如收集日志。

4. 创建名称为 LRSFullAccessAdminGroup 的 Active Directory 安全组。

    创建组作用域为 "全局" 和 "组类型" 的组作为安全性。添加到此组的启用 SIP 的用户将被授权使用单个 Skype 会议室上的所有管理门户功能。 若要包括对 Skype 会议室的批量管理支持，请参阅步骤5。

     ![具有安全组角色的管理员组的列表](../../media/LRS_LRSFullAccessAdminGroup.png)

5. 创建名称为 LRSPowerUserAdminsGroup 的 Active Directory 安全组。

    创建组作用域为 "全局" 和 "组类型" 作为 "安全" 的组。 已授权添加到此组的 SIP 用户使用所有管理门户功能，包括对 Skype for business 聊天室的批量管理。

6. 将 LRSFullAccessAdminGroup 添加为 LRSSupportAdminGroup 的成员。

     ![LRSSupportAdminGroup 属性 "成员" 页](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. 创建具有名称 LRSSupport 的启用 SIP 的 Active Directory 用户。 将此用户添加到 LRSSupportAdminGroup。

     ![LRSSupportAdminGroup 属性 "成员" 页](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. 安装[ASP.NET MVC 4 For Visual Studio 2010 sp1 和 Visual Web Developer 2010 sp1](https://go.microsoft.com/fwlink/p/?LinkId=323967)。

## <a name="install-the-srs-v1-administrative-web-portal"></a>安装 SRS v1 管理 Web 门户
<a name="Install_SRS"> </a>

下载[适用于 Skype for Business Server 2015 的 Microsoft Skype 会议室 Systems V1 管理 Web 门户](https://www.microsoft.com/download/details.aspx?id=46906)。

若要安装 SRS v1 管理 Web 门户，请执行以下步骤。

1. 通过在 Skype for Business Server 命令行管理程序中运行以下 cmdlet 来配置受信任的应用程序端口：

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. 若要安装会议室门户，请下载**MeetingRoomPortalInstaller** ，然后以管理员身份运行它。

3. 从以下位置打开 web.config 文件：

    % Program Files%\Skype for Business Server 2015 \ Web Components\Meeting 聊天室 Portal\Int\Handler\

4. 在 web.config 文件中，将 PortalUserName 更改为 "[Configure THE SRS V1 管理 Web 门户的环境](room-system-v1-administrative-web-portal.md#Config_Env)" 一节中的步骤2中创建的用户名（步骤中的推荐名称为 LRSApp）：

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. 由于 SRS v1 管理门户是一个受信任的应用程序，因此您无需在门户配置中提供密码。 如果此用户使用的是与本地注册器不同的注册器，则需要通过在 Web.config 文件中添加以下行来为其指定注册器：

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. 如果使用的端口不是5061，则在 Web.config 文件中添加以下行：

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a>验证 SRS 管理 Web 门户的安装

若要验证 SRS v1 管理 Web 门户的安装，请执行以下操作：

1. 在前端服务器上，浏览到以下 URL：

    https:// \<fe-server\> /lrs

    您不应看到任何错误，如下图所示：

     ![Lync 会议室系统管理门户登录屏幕](../../media/LRS_AdminPortalSignIn.png)

2. 如果没有看到任何错误，请尝试从拓扑中的任何其他计算机访问以下 URL：

    https:// \<fe-server\> /lrs

    若要访问该页面，你将需要添加 DNS 记录，如 "[自动客户端登录所需的 DNS 记录](https://go.microsoft.com/fwlink/p/?LinkId=318056)" 中所述。

## <a name="use-the-srs-administrative-web-portal"></a>使用 SRS 管理 Web 门户
<a name="Use_Portal"> </a>

在服务器上部署 SRS 之后，可以通过从浏览器登录 SRS v1 管理 Web 门户来检查所有 SRS 聊天室的状态。

### <a name="sign-in"></a>登录

1. 浏览到以下 URL：

    https:// \<fe-server\> /lrs

2. 输入 LRSSupport 帐户的凭据或已添加到 LRSSupportAdminGroup 安全组的帐户。

![Lync 会议室系统管理门户登录屏幕](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a>SRS 管理 Web 门户摘要页

"摘要" 页面为服务器上部署的所有 SRS 聊天室提供以下信息：

- **标记**管理员为会议室提供的自定义名称。 可以通过单击聊天室名称在门户中设置标记。

- **运行状况**会议室的运行状况状态，该状态源自会议室的聚合运行状况状态，显示在 "会议室设置" 页面的 "运行状况" 部分下。

- **下次会议**安排下一个会议的日期和时间。

- **SRS 版本、制造商、型号**这些值是在 SRS 中预设的。 根据制造商的不同，这些字段可能保留为空。

- **上次刷新**显示上次刷新网页的时间。

![Lync 会议室系统管理门户摘要视图](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> 仅当您是 LRSPowerUserAdminsGroup 安全组的一部分时，您才会看到 "批量管理" 菜单。

### <a name="srs-room-information"></a>SRS 聊天室信息

通过门户的 "会议室信息" 部分，可以查看和配置单个 SRS 聊天室。 它包含四个部分：设置、详细信息、日志记录和运行状况。

#### <a name="settings"></a>设置

在 "设置" 部分中，您可以设置会议室的密码、会议室标记和默认音量级别。 如果配置这些设置，只有在重新启动 SRS 控制台后才会复制更改。 您只会看到使用版本15.12 和更高版本的 SRS 设备的系统更新设置。

![Lync 会议室系统管理门户聊天室设置](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a>详细信息

详细信息部分提供了 SRS 聊天室设置的只读摘要，包括：上次刷新的时间;下一个会议;上次更新、维护和校准;默认扬声器、麦克风和铃声设置;版本SIP URI;屏幕数量和每个屏幕的详细信息;状态和活动。

![Lync 会议室系统管理员门户详细信息视图](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a>疑难解答

故障排除部分可用于远程收集日志并将其保存到指定位置。 您还可以重新启动 SRS 控制台（SRS 用户界面）或重新启动整个系统。 若要收集日志，请提供指定格式的文件夹路径，并确保该文件夹具有授予 SRS 计算机帐户的写入权限。 如果日志太大，可能需要长达5分钟才能完成日志收集。 刷新页面将为你提供最新状态。

#### <a name="health"></a>健康

"运行状况" 部分提供了 Skype for business Server 连接、音频设备、视频设备、复原状态和屏幕设备的运行状况的可视指示。

![Lync 会议室系统管理门户会议室运行状况](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a>有关管理 Web 门户的其他说明

> [!NOTE]
>  仅在重新启动 SRS 系统后才会应用设置更改。 > 如果 LRSApp 帐户密码过期，将无法看到聊天室的状态。 配置 LRSAppuser 帐户密码，使其永不过期，或者确保在密码即将过期时更新密码 >。仅支持本地部署的 SRS 管理 web 门户。

### <a name="bulk-management"></a>批量管理

SRS 聊天室的批量管理是为高级 IT 管理员设计的一项功能，可简化其工作流，并使用节省时间的工具为其启用以批量方式远程管理多个聊天室的功能。

若要查看此功能，需要将用户设置为特殊安全组**LRSPowerUserAdminsGroup**的成员。

对于您可以选择用于批量管理的 SRS 聊天室的数量没有限制。 但是，一次只能执行一个批量管理操作。

若要执行批量管理操作，请选择要监视的聊天室，然后单击 "批量管理" 菜单。

### <a name="frequently-asked-questions"></a>常见问题

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>为什么我无法登录管理 web 门户？

当你打开时 https://localhost/lrs ，你将能够看到登录页，但在你键入凭据时，无法登录。 在这种情况下，您必须打开 https://FQDNofFEserver/SRS 以登录到管理 web 门户。

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a>为什么我在管理 web 门户中看不到 SRS v1？

- 确保在部署中拥有 SRS 帐户，并确保根据 SRS 管理 Web 门户部署建议创建这些帐户。 确保在 Skype for Business Server 上使用 Disable-csmeetingroom，而不是 Enable-Get-csuser 预配 SRS 帐户。

- 如果已创建 SRS 帐户，但在管理 web 门户中看不到这些帐户，请使用已选中**MeetingPortal**组件的 Skype For Business Server 日志记录工具收集服务器日志，然后将其发送到你的 SRS 支持联系人。

- 如果您已创建 SRS 帐户，并且在管理 web 门户中看不到帐户，则使用 Fiddler 收集客户端日志，并从浏览器开发工具中复制控制台日志，然后将其发送到 SRS 支持联系人。 您还可以修改 Web.config 中的跟踪级别值，以获取更详细的日志。

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

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a>为什么我在管理 web 门户中看不到 SRS 的状态？

- 请确保 LRSApp 用户帐户启用了 SIP。

- 如果仍有问题，请从 D:\Tracing\LRSAdminLogs 收集 SRS 系统中的**Trace .log**文件 \, ，然后将其发送到你的 SRS 支持联系人。

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a>为什么我在管理 web 门户中看不到 SRS 的 "批量管理" 菜单？

确保 LRSApp 用户帐户启用了 SIP，并且是 LRSPowerUserAdminsGroup 安全组的一部分。

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a>SRS v1 管理 web 门户是否适用于 Microsoft 团队聊天室？

否。


