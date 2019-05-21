---
title: 在 Skype for Business 服务器中部署 SRS v1 管理 Web 门户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: Skype for business Server Skype 会议室系统 v1 (SRS v1, 以前称为 Lync 房间系统) 管理 Web 门户是一种 Web 门户, 组织可以使用该门户维护其 Skype 会议室系统会议室。 管理员可以使用 SRS v1 管理 Web 门户监视设备运行状况, 例如通过监视音频/视频设备进行监视。 通过此门户, 管理员可以远程收集诊断信息以监控会议室的运行状况。
ms.openlocfilehash: 5ad4ffb08ecbc32feaa87aa2f7d48d82003e2e3e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307159"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a>在 Skype for Business 服务器中部署 SRS v1 管理 Web 门户

Skype for business Server Skype 会议室系统 v1 (SRS v1, 以前称为 Lync 房间系统) 管理 Web 门户是一种 Web 门户, 组织可以使用该门户维护其 Skype 会议室系统会议室。 管理员可以使用 SRS v1 管理 Web 门户监视设备运行状况, 例如通过监视音频/视频设备进行监视。 通过此门户, 管理员可以远程收集诊断信息以监控会议室的运行状况。

若要使用此功能, 需要在每个 Skype for business 服务器前端服务器上部署 SRS v1 管理 Web 门户。 本指南面向管理员提供有关如何安装和配置 SRS 管理 Web 门户的说明。 它适用于了解 Skype for business 服务器管理知识的管理员, 以及拥有修改 Skype for Business 服务器拓扑的管理员用户权限的人员。

在服务器上部署 SRS v1 管理 Web 门户后, 管理员可以通过从其自己的计算机或笔记本电脑登录到网站来检查状态 SRS v1 设备。

> [!IMPORTANT]
> 下载[适用于 skype for Business Server 2015 的 Microsoft Skype 会议室系统 V1 管理 Web 门户](https://www.microsoft.com/en-us/download/details.aspx?id=46906)。

在本主题中：

- [针对 SRS v1 管理 Web 门户配置你的环境](room-system-v1-administrative-web-portal.md#Config_Env)

- [安装 SRS v1 管理 Web 门户](room-system-v1-administrative-web-portal.md#Install_SRS)

- [使用 SRS 管理 Web 门户](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a>针对 SRS v1 管理 Web 门户配置你的环境
<a name="Config_Env"> </a>

要使用 SRS v1 管理 Web 门户，你将需要安装或配置以下先决条件。

> [!IMPORTANT]
> 如果服务器同时配置了 Kerberos 和 NTLM 身份验证，并且 SRS 在未加入域的计算机上运行，则 Kerberos 身份验证将会失败，并且用户在管理门户中看不到 SRS 的状态。要解决此问题，请为服务器配置 NTLM 身份验证或者同时配置 NTLM 和 TLS-DSK 身份验证（无 Kerberos），或者将 SRS 计算机加入域。

1. 在 Skype for business Server 拓扑中安装 Skype for business Server 累积更新。

    若要获取更新或查看它附带的内容, 请参阅[Skype for Business Server 2015 更新](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)。

2. 创建启用了 SIP 的 Active Directory 用户。

    SRS v1 管理 Web 门户使用这些凭据从 Skype for Business 服务器查询信息。 给定示例中的用户名是 LRSApp。

3. 创建名称为 LRSSupportAdminGroup 的 Active Directory 安全组。

    创建“组作用域”为“全局”、“组类型”为“安全”的组。添加到此组启用了 SIP 的用户将被授权查看聊天室列表并执行特定命令（例如收集日志）。

4. 创建名称为 LRSFullAccessAdminGroup 的 Active Directory 安全组。

    创建“组作用域”为“全局”、“组类型”为“安全”的组。添加到此组、启用了 SIP 的用户将被授权在单个 Skype 会议室中使用所有管理门户功能。要支持对 Skype 会议室进行批量管理，请参阅步骤 5。

     ![具有安全组角色的 Admin 组的列表](../../media/LRS_LRSFullAccessAdminGroup.png)

5. 创建名称为 LRSPowerUserAdminsGroup 的 Active Directory 安全组。

    创建“组作用域”为“全局”、“组类型”为“安全”的组。 添加到此群组的 SIP 启用的用户已获得使用所有管理员门户功能 (包括 Skype for business 会议室的批量管理) 的授权。

6. 将 LRSFullAccessAdminGroup 添加为 LRSSupportAdminGroup 的成员。

     ![LRSSupportAdminGroup 属性 -“成员”页](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. 创建名称为 LRSSupport 的启用了 SIP 的 Active Directory 用户。 将此用户添加到 LRSSupportAdminGroup。

     ![LRSSupportAdminGroup 属性 -“成员”页](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. 安装[Visual Studio 2010 sp1 和 Visual Web Developer 2010 SP1 的 ASP.NET MVC 4](https://go.microsoft.com/fwlink/p/?LinkId=323967)。

## <a name="install-the-srs-v1-administrative-web-portal"></a>安装 SRS v1 管理 Web 门户
<a name="Install_SRS"> </a>

下载[适用于 skype for Business Server 2015 的 Microsoft Skype 会议室系统 V1 管理 Web 门户](https://www.microsoft.com/en-us/download/details.aspx?id=46906)。

要安装 SRS v1 管理 Web 门户，请执行以下步骤。

1. 通过在 Skype for Business Server Management Shell 中运行以下 cmdlet 来配置受信任的应用程序端口:

   ```
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. 要安装会议室门户，请下载 **MeetingRoomPortalInstaller.msi**，然后以管理员身份运行它。

3. 打开以下位置中的 Web.config 文件：

    %Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler\

4. 在 web.config 文件中, 将 PortalUserName 更改为在步骤2中的 "为[SRS V1 管理 Web 门户配置环境](room-system-v1-administrative-web-portal.md#Config_Env)" 部分中创建的用户名 (步骤中推荐的名称为 LRSApp):

    ```
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. 由于 SRS v1 管理门户是受信任的应用，你不必在门户配置中提供密码。如果此用户使用的是非本地注册器，你需要通过在 Web.Config 文件中添加以下行来为其指定注册器：

   ```
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. 如果使用的端口不是 5061，则需要在 Web.Config 文件中添加以下行：

   ```
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a>验证 SRS 管理 Web 门户的安装

要验证 SRS v1 管理 Web 门户的安装，请执行以下操作：

1. 在前端服务器上，浏览至以下 URL：

    https://\<fe-服务器\>/lrs

    你不应该看到任何错误，如下图所示：

     ![Lync 聊天室系统管理门户登录屏幕](../../media/LRS_AdminPortalSignIn.png)

2. 如果你未看到任何错误，请尝试从拓扑中的任何其他计算机访问以下 URL：

    https://\<fe-服务器\>/lrs

    若要访问页面, 你将需要添加 DNS 记录, 如 "[自动客户端登录所需的 DNS 记录](https://go.microsoft.com/fwlink/p/?LinkId=318056)" 中所述。

## <a name="use-the-srs-administrative-web-portal"></a>使用 SRS 管理 Web 门户
<a name="Use_Portal"> </a>

在服务器上部署 SRS 之后，你可以通过从浏览器登录到 SRS v1 管理 Web 门户来检查所有 SRS 会议室的状态。

### <a name="sign-in"></a>登录

1. 浏览到以下 URL：

    https://\<fe-服务器\>/lrs

2. 输入 LRSSupport 帐户或者已添加到 LRSSupportAdminGroup 安全组的帐户的凭据。

![Lync 聊天室系统管理门户登录屏幕](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a>SRS 管理 Web 门户摘要页面

摘要页面为服务器上部署的所有 SRS 会议室提供以下信息：

- **标记**管理员提供给聊天室的自定义名称。 可以通过在门户中单击会议室名称来设置标记。

- **运行状况**聊天室的运行状况状态, 该状态派生自会议室的聚合运行状况, 该状态显示在 "房间设置" 页面的 "运行状况" 部分下方。

- **下一次会议**安排下一个会议的日期和时间。

- **SRS 版本、制造商、型号**这些值是在 SRS 中预置的。 根据制造商，这些字段可能留空。

- **上次刷新**显示上次刷新网页的时间。

![Lync 聊天室系统管理门户摘要视图](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> 如果你是 LRSPowerUserAdminsGroup 安全组的一部分, 你将只能看到 "批量管理" 菜单。

### <a name="srs-room-information"></a>SRS 会议室信息

在门户的“会议室信息”部分可以查看和配置各个 SRS 会议室。它包含四个部分：设置、详细信息、日志记录和运行状况。

#### <a name="settings"></a>设置

在“设置”部分中，你可以设置会议室的密码、会议室标记和默认音量大小。如果配置这些设置，只会在你重新启动 SRS 控制台之后复制更改。对于使用 15.12 及更高版本的 SRS 设备，你将只会看到“系统更新”设置。

![Lync 聊天室系统管理门户聊天室设置](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a>详细信息

详细信息部分提供了 SRS 聊天室的设置的只读摘要, 包括: 上次刷新的时间;下一次会议;上次更新、维护和校准;默认扬声器、麦克风和铃声设置;版本SIP URI;屏幕数和每个屏幕的详细信息;状态和活动。

![Lync 聊天室系统管理门户详细信息视图](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a>疑难解答

“疑难解答”部分可用于远程收集日志并将它们保存到指定位置。你还可以重新启动 SRS 控制台（SRS 用户界面）或重新启动整个系统。要收集日志，请按指定格式提供文件夹路径，并确保为 SRS 计算机帐户提供了写入该文件夹的权限。如果日志太大，可能需要长达 5 分钟才能完成日志的收集。刷新页面将显示最新状态。

#### <a name="health"></a>运行状况

"运行状况" 部分提供了 Skype for business 服务器连接、音频设备、视频设备、复原状态和屏幕设备的运行状况的可视指示。

![Lync 聊天室系统管理门户聊天室运行状况](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a>有关管理 Web 门户的其他说明

> [!NOTE]
>  只有在 SRS 系统重新启动后才会应用设置更改。 > 如果 LRSApp 帐户密码过期, 您将无法看到聊天室的状态。 配置 LRSAppuser 帐户密码, 使其永不过期, 或者确保在密码即将过期时更新密码。 > 仅支持本地部署的 SRS 管理 web 门户。

### <a name="bulk-management"></a>批量管理 

SRS 会议室批量管理是一项专门面向高级 IT 管理员的功能，用于简化其工作流，使他们能够通过一个节省时间的便利工具来以批量方式远程管理多个会议室。

用户要看到此功能，需要设置为特殊安全组 **LRSPowerUserAdminsGroup** 的成员。

可以选择进行批量管理的 SRS 会议室数没有限制。但一次只能执行一个批量管理操作。

要执行批量管理操作，请选择要监视的会议室，并单击“批量管理”菜单。

### <a name="frequently-asked-questions"></a>常见问题

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>为什么我无法登录到管理 web 门户？

打开https://localhost/lrs时, 你将能够看到 "登录" 页面, 但当你键入凭据时, 无法登录。 在这种情况下, 必须https://FQDNofFEserver/SRS打开才能登录到管理 web 门户。

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a>为什么在管理 web 门户中看不到 SRS v1？

- 确保你的部署中有 SRS 帐户，并且它们是按照 SRS 管理 Web 门户部署建议创建的。 请确保在 Skype for Business 服务器上使用 Enable-CsMeetingRoom, 而不是 Enable-Move-csuser 设置 SRS 帐户。

- 如果你已创建了 SRS 帐户, 并且在管理 web 门户中看不到帐户, 请使用选择了**MeetingPortal**组件的 Skype For Business 服务器日志记录工具收集服务器日志, 然后将其发送到你的 SRS 支持联系人。

- 如果你已创建 SRS 帐户，但是在管理 Web 门户中看不到这些帐户，请使用 Fiddler 来收集客户端日志，并从浏览器开发工具复制控制台日志，然后将它们发送给你的 SRS 支持联系人。你还可以在 Web.config 中修改跟踪级别值以获取更详细的日志。

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

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a>为什么我在管理 web 门户中看不到 SRS 的状态？

- 请确保 LRSApp 用户帐户已启用 SIP。

- 如果仍有问题, 请从 D:\Tracing\LRSAdminLogs\,中收集 SRS 系统中的**Trace .log**文件, 然后将其发送到你的 SRS 支持联系人。

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a>为什么在管理 web 门户中看不到 SRS 的批量管理菜单？

请确保 LRSApp 用户帐户是 SIP 启用的, 并且是 LRSPowerUserAdminsGroup 安全组的一部分。

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a>SRS v1 管理 web 门户是否与 Microsoft 团队聊天室一起工作？

否。


