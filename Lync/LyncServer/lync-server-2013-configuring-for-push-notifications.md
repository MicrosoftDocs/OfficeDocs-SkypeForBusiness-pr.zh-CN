---
title: Lync Server 2013：配置推送通知
TOCTitle: 配置推送通知
ms:assetid: d77f2c06-0fe6-45d5-8f08-808ab871b3e0
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690047(v=OCS.15)
ms:contentKeyID: 49314399
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置推送通知

 

_**上一次修改主题：** 2013-02-12_

即使移动应用程序处于非活动状态，也可以向移动设备发送推送通知（以徽章、图标或警告的形式）。推送通知会将一些事件（例如，新的或错过的 IM 邀请和语音邮件）告知用户。 Lync Server 2013 Mobility Service 会将通知发送到基于云的 Lync Server 推送通知服务，然后该服务会将通知发送到 Apple 推送通知服务 (APNS)（对于运行 Lync 2010 Mobile 客户端的 Apple 设备）或 Microsoft 推送通知服务 (MPNS)（对于运行 Lync 2010 Mobile 或 Lync 2013 Mobile 客户端的 Windows Phone 设备）。

> [!IMPORTANT]  
> 如果您将 Windows Phone 与 Lync 2010 Mobile 或 Lync 2013 Mobile 客户端一起使用，则推送通知是一个重要的考虑因素。<br />
> 如果您在 Apple 设备上使用 Lync 2010 Mobile，则推送通知是一个重要的考虑因素。<br />
> 如果您在 Apple 设备上使用 Lync 2013 Mobile，您将不再需要推送通知。



通过执行下列操作，将您的拓扑配置为支持推送通知：

  - 如果您的环境包含一台 Lync Server 2010 或 Lync Server 2013边缘服务器，则您需要添加一个新的宿主提供程序（即 Microsoft Lync Online），然后在您的组织和 Lync Online 之间设置宿主提供程序联盟。

  - 如果您的环境包含一台 Office Communications Server 2007 R2边缘服务器，则您需要设置与 push.lync.com 的直接 SIP 联盟。
    
    > [!NOTE]  
    > Push.lync.com 是一个适用于推送通知服务的 Microsoft Office 365 域。
    


  - 若要启用推送通知，您需要运行 **Set-CsPushNotificationConfiguration** cmdlet。默认情况下，推送通知已关闭。

  - 测试联盟配置和推送通知。

## 使用 Lync Server 2013 或 Lync Server 2010边缘服务器配置推送通知

1.  以 RtcUniversalServerAdmins 组的成员身份登录到安装 Lync Server 命令行管理程序和 Ocscore 的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  添加 Lync Server 联机宿主提供程序。在命令行中键入：
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    例如：
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    > [!NOTE]  
    > 您不能与一个宿主提供程序建立多个联盟关系。也就是说，如果您已设置一个与 sipfed.online.lync.com 建立了联盟关系的宿主提供程序，则请不要为其添加其他宿主提供程序，即使该宿主提供程序的标识不是 LyncOnline 也是如此。
    


4.  在 Lync Online 上设置组织与推送通知服务之间的宿主提供程序联盟。在命令行中键入：
    
        New-CsAllowedDomain -Identity "push.lync.com"

## 使用 Office Communications Server 2007 R2边缘服务器配置推送通知

1.  以 RtcUniversalServerAdmins 组的成员身份登录到 边缘服务器。

2.  依次单击“开始”、“所有程序”、“管理工具”和“计算机管理”。

3.  在控制台树中，展开“服务和应用程序”，右键单击“Microsoft Office Communications Server 2007 R2”，然后单击“属性”。

4.  在“允许”选项卡上，单击“添加”。

5.  在“添加联盟伙伴”对话框中，执行下列操作：
    
      - 在“联盟伙伴域名”中，键入 **push.lync.com** 。
    
      - 在“联盟伙伴访问边缘服务器”中，键入 **sipfed.online.lync.com**。
    
      - 单击“确定”。

## 启用推送通知

1.  以 CsAdministrator 角色的成员身份登录到安装 Lync Server 命令行管理程序和 Ocscore 的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  启用推送通知。在命令行中键入：
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  启用联盟。在命令行中键入：
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

## 测试联盟和推送通知

1.  以 CsAdministrator 角色的成员身份登录到安装 Lync Server 命令行管理程序和 Ocscore 的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  测试联盟配置。在命令行中键入：
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    例如：
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  测试推送通知。在命令行中键入：
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    例如：
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

## 另请参阅

#### 其他资源

[Test-CsFederatedPartner](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsFederatedPartner)  
[Test-CsMcxPushNotification](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsMcxPushNotification)

