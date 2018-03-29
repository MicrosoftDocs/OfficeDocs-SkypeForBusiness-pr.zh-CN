---
title: 在 Skype for Business Server 2015 中部署 SRS v1 管理 Web 门户
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/3/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
description: 业务服务器 2015 Skype 的空间系统 v1 Skype (SRS v1，前身为 Lync 室系统) 管理 Web 门户是 web 门户的组织可以用来维护其 Skype 的空间系统的会议室。 管理员可以使用 SRS v1 管理 Web 门户来监控设备运行状况，例如通过监视音频/视频设备。 与此门户网站，管理员可以远程收集诊断信息，以监测会议空间状况。
ms.openlocfilehash: d87241cc983fabf76a952bce4941063169f787c2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中部署 SRS v1 管理 Web 门户
 
业务服务器 2015 Skype 的空间系统 v1 Skype (SRS v1，前身为 Lync 室系统) 管理 Web 门户是 web 门户的组织可以用来维护其 Skype 的空间系统的会议室。 管理员可以使用 SRS v1 管理 Web 门户来监控设备运行状况，例如通过监视音频/视频设备。 与此门户网站，管理员可以远程收集诊断信息，以监测会议空间状况。
  
若要使用此功能，需要为业务服务器前端服务器部署在每个 Skype 上 SRS v1 管理 Web 门户。 本指南面向管理员提供有关如何安装和配置 SRS 管理 Web 门户的说明。 这被专为管理员拥有 Skype 的业务服务器管理的知识和拥有管理员权限才能修改业务服务器拓扑 Skype。
  
之后 SRS v1 管理 Web 门户部署在服务器，管理员可以从自己的计算机或便携式计算机登录到站点状态 SRS v1 设备检查。 
  
> [!IMPORTANT]
> 下载[Skype Microsoft 文件室系统 Skype 业务服务器 2015 v1 管理 Web 门户](https://www.microsoft.com/en-us/download/details.aspx?id=46906)。 
  
在本主题中：
  
- [SRS v1 管理 Web 门户的配置环境](room-system-v1-administrative-web-portal.md#Config_Env)
    
- [安装 SRS v1 管理 Web 门户](room-system-v1-administrative-web-portal.md#Install_SRS)
    
- [使用 SRS 管理 Web 门户](room-system-v1-administrative-web-portal.md#Use_Portal)
    
## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a>针对 SRS v1 管理 Web 门户配置你的环境
<a name="Config_Env"> </a>

要使用 SRS v1 管理 Web 门户，你将需要安装或配置以下先决条件。
  
> [!IMPORTANT]
> 如果服务器同时配置了 Kerberos 和 NTLM 身份验证，并且 SRS 在未加入域的计算机上运行，则 Kerberos 身份验证将会失败，并且用户在管理门户中看不到 SRS 的状态。要解决此问题，请为服务器配置 NTLM 身份验证或者同时配置 NTLM 和 TLS-DSK 身份验证（无 Kerberos），或者将 SRS 计算机加入域。 
  
1. 为业务 Skype 业务服务器拓扑中的服务器累积更新安装 Skype。 
    
    若要获取更新或查看它所包含，请参阅[更新业务服务器 2015年的 Skype](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)。
    
2. 创建启用了 SIP 的 Active Directory 用户。
    
    SRS v1 管理 Web 门户使用这些凭据查询信息从 Skype 业务服务器。 给定示例中的用户名是 LRSApp。
    
3. 创建名称为 LRSSupportAdminGroup 的 Active Directory 安全组。
    
    创建“组作用域”为“全局”、“组类型”为“安全”的组。添加到此组启用了 SIP 的用户将被授权查看聊天室列表并执行特定命令（例如收集日志）。
    
4. 创建名称为 LRSFullAccessAdminGroup 的 Active Directory 安全组。 
    
    创建“组作用域”为“全局”、“组类型”为“安全”的组。添加到此组、启用了 SIP 的用户将被授权在单个 Skype 会议室中使用所有管理门户功能。要支持对 Skype 会议室进行批量管理，请参阅步骤 5。 
    
     ![具有安全组角色的 Admin 组的列表](../../media/LRS_LRSFullAccessAdminGroup.png)
  
5. 创建名称为 LRSPowerUserAdminsGroup 的 Active Directory 安全组。 
    
    创建“组作用域”为“全局”、“组类型”为“安全”的组。 添加到此组启用了 SIP 用户有权使用所有管理门户功能包括 Skype 业务间的大容量管理。 
    
6. 将 SRSFullAccessAdminGroup 添加为 LRSSupportAdminGroup 的成员。
    
     ![LRSSupportAdminGroup 属性 -“成员”页](../../media/LRS_Add_LRSSupportAdminGroup.png)
  
7. 创建名称为 LRSSupport 的启用了 SIP 的 Active Directory 用户。将此用户添加到 LRSSupportAdminGroup。
    
     ![LRSSupportAdminGroup 属性 -“成员”页](../../media/LRS_Add_LRS_SIP_SupportUser.png)
  
8. [ASP.NET MVC 4 Visual Studio 2010 sp1 和可视 Web 开发人员 2010 SP1](http://go.microsoft.com/fwlink/p/?LinkId=323967)的安装。
    
## <a name="install-the-srs-v1-administrative-web-portal"></a>安装 SRS v1 管理 Web 门户
<a name="Install_SRS"> </a>

下载[Skype Microsoft 文件室系统 Skype 业务服务器 2015 v1 管理 Web 门户](https://www.microsoft.com/en-us/download/details.aspx?id=46906)。 
  
要安装 SRS v1 管理 Web 门户，请执行以下步骤。
  
1. 通过运行以下 cmdlet 在 Skype 业务服务器管理外壳配置受信任的应用程序端口：
    
   ```
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. 要安装会议室门户，请下载 **MeetingRoomPortalInstaller.msi**，然后以管理员身份运行它。
    
3. 打开以下位置中的 Web.config 文件：
    
    %Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler\
    
4. 在 Web.Config 文件中，改为 PortalUserName 下部分"[配置 SRS v1 管理 Web 门户的环境](room-system-v1-administrative-web-portal.md#Config_Env)"（在步骤的建议的名称为 LRSApp） 在第 2 步中创建的用户名： 
    
    ```
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. 由于 SRS v1 管理门户是受信任的应用，你不必在门户配置中提供密码。如果此用户使用的是非本地注册器，你需要通过在 Web.Config 文件中添加以下行来为其指定注册器： 
    
   ```
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. 如果所用的端口 other than 5061，在 Web.Config 文件中添加以下行： 
    
   ```
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a>验证 SRS 管理 Web 门户的安装

要验证 SRS v1 管理 Web 门户的安装，请执行以下操作：
  
1. 在前端服务器上，浏览至以下 URL：
    
    https://\<fe 服务器\>/lrs
    
    你不应该看到任何错误，如下图所示：
    
     ![Lync 聊天室系统管理门户登录屏幕](../../media/LRS_AdminPortalSignIn.png)
  
2. 如果你未看到任何错误，请尝试从拓扑中的任何其他计算机访问以下 URL：
    
    https://\<fe 服务器\>/lrs
    
    若要访问此页，您需要添加的 DNS 记录，如"[需要的 DNS 记录有关自动客户端登录](https://go.microsoft.com/fwlink/p/?LinkId=318056)"中所述
    
## <a name="use-the-srs-administrative-web-portal"></a>使用 SRS 管理 Web 门户
<a name="Use_Portal"> </a>

在服务器上部署 SRS 之后，你可以通过从浏览器登录到 SRS v1 管理 Web 门户来检查所有 SRS 会议室的状态。
  
### <a name="sign-in"></a>登录

1. 浏览到以下 URL：
    
    https://\<fe 服务器\>/lrs
    
2. 输入 LRSSupport 帐户或者已添加到 LRSSupportAdminGroup 安全组的帐户的凭据。
    
![Lync 聊天室系统管理门户登录屏幕](../../media/LRS_AdminPortalSignIn.png)
  
### <a name="srs-administrative-web-portal-summary-page"></a>SRS 管理 Web 门户摘要页面

摘要页面为服务器上部署的所有 SRS 会议室提供以下信息：
  
- **标记**自定义管理员可以使该文件室的名称。 可以通过在门户中单击会议室名称来设置标记。
    
- **健康状况**健康状态的房间，从文件室，而在空间设置页的健康部分会显示的聚合的健康状况。
    
- **下一次会议**计划的日期和时间下一次会议。
    
- **SRS 版本、 制造商、 型号**这些值是预设在 SRS。 根据制造商，这些字段可能留空。
    
- **上次刷新**显示的上次刷新该 web 页。
    
![Lync 聊天室系统管理门户摘要视图](../../media/LRS_AdminPortal_Summary_view.png)
  
> [!NOTE]
> 如果您是 LRSPowerUserAdminsGroup 安全组的一部分，只会看到批量管理菜单。 
  
### <a name="srs-room-information"></a>SRS 会议室信息

在门户的“会议室信息”部分可以查看和配置各个 SRS 会议室。它包含四个部分：设置、详细信息、日志记录和运行状况。
  
#### <a name="settings"></a>设置

在“设置”部分中，你可以设置会议室的密码、会议室标记和默认音量大小。如果配置这些设置，只会在你重新启动 SRS 控制台之后复制更改。对于使用 15.12 及更高版本的 SRS 设备，你将只会看到“系统更新”设置。
  
![Lync 聊天室系统管理门户聊天室设置](../../media/LRS_AdminPortal_RoomInfoSettings.png)
  
#### <a name="details"></a>详细信息

详细信息部分中提供的 SRS 文件室的设置，包括只读摘要： 上次刷新; 时间下一次会议;最后一次更新、 维护和校准;默认扬声器、 麦克风和铃声设置;版本。SIP URI;屏幕和每个屏幕中; 有关详细信息的数量状态和活动。
  
![Lync 聊天室系统管理门户详细信息视图](../../media/LRS_AdminPortal_Detail_view.png)
  
#### <a name="troubleshooting"></a>疑难解答

“疑难解答”部分可用于远程收集日志并将它们保存到指定位置。你还可以重新启动 SRS 控制台（SRS 用户界面）或重新启动整个系统。要收集日志，请按指定格式提供文件夹路径，并确保为 SRS 计算机帐户提供了写入该文件夹的权限。如果日志太大，可能需要长达 5 分钟才能完成日志的收集。刷新页面将显示最新状态。
  
#### <a name="health"></a>运行状况

健康一节提供 Skype 业务服务器连接、 音频设备、 视频设备、 复原状态和屏幕设备的运行状况的可视化的表示。
  
![Lync 聊天室系统管理门户聊天室运行状况](../../media/LRS_AdminPortal_RoomInfoHealth.png)
  
### <a name="additional-notes-about-the-administrative-web-portal"></a>有关管理 Web 门户的其他说明

> [!NOTE]
>  设置更改仅在 SRS 系统重新启动后应用。 > 如果 LRSApp 帐户密码已过期，您将不能查看房间的状态。 配置的 LRSAppuser 帐户密码，以便它永远不会过期，或一定要更新密码，当它接近到期。 > 内部部署仅支持 SRS 管理 web 门户。
  
### <a name="bulk-management"></a>批量管理 

SRS 会议室批量管理是一项专门面向高级 IT 管理员的功能，用于简化其工作流，使他们能够通过一个节省时间的便利工具来以批量方式远程管理多个会议室。
  
用户要看到此功能，需要设置为特殊安全组 **LRSPowerUserAdminsGroup** 的成员。 
  
可以选择进行批量管理的 SRS 会议室数没有限制。但一次只能执行一个批量管理操作。
  
要执行批量管理操作，请选择要监视的会议室，并单击“批量管理”菜单。 
  
### <a name="frequently-asked-questions"></a>常见问题

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>为什么我无法登录到管理 web 门户？

当您打开https://localhost/lrs，您将能够看到登录页面，但您在凭据中键入时，您不能登录。 在这种情况下，您必须打开https://FQDNofFEserver/SRS以用于登录到管理 web 门户。
  
#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a>为什么看不到管理 web 门户中的 SRS v1？

- 确保你的部署中有 SRS 帐户，并且它们是按照 SRS 管理 Web 门户部署建议创建的。 请确保使用 Skype 业务服务器上启用 CsMeetingRoom，不启用 CsUser，调配 SRS 帐户。
    
- 如果已创建 SRS 帐户无法看到管理 web 门户中的帐户，通过 Skype 业务服务器日志记录工具与选择， **MeetingPortal**组件收集服务器日志，然后将它们发送给您的 SRS 支持联系人。
    
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

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a>为什么看不到管理 web 门户中的 SRS 状态？

- 请确保 LRSApp 用户帐户已启用 SIP。
    
- 如果仍有问题，收集**Trace.log**文件 SRS 系统中 D:\Tracing\LRSAdminLogs\, ，然后将其发送给您的 SRS 支持联系人。
    
#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a>为什么看不到的批量管理菜单的 SRS 管理 web 门户中？

确保 LRSApp 用户帐户是 SIP 启用的并且是 LRSPowerUserAdminsGroup 安全组的一部分。 
  
#### <a name="does-the-srs-v1-administrative-web-portal-work-with-skype-room-systems-v2"></a>SRS v1 管理 Web 门户是否可以使用 Skype Room Systems v2？

否。
  

