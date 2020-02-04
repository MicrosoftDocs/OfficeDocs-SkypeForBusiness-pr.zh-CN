---
title: Lync Server 2013：配置推送通知
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring for push notifications
ms:assetid: d77f2c06-0fe6-45d5-8f08-808ab871b3e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690047(v=OCS.15)
ms:contentKeyID: 48185574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c34b49d6c968effa46005a01df286d14fcff394c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-for-push-notifications-in-lync-server-2013"></a>在 Lync Server 2013 中配置推送通知

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-12_

即使移动应用处于非活动状态，推送通知（以锁屏提醒、图标或警报形式）也可以发送到移动设备。 推送通知通知用户诸如新的或错过的 IM 邀请和语音邮件等事件。 Lync Server 2013 移动服务将通知发送到基于云的 Lync Server 推送通知服务，然后将通知发送到 Apple 推送通知服务（APNS）（适用于运行 Lync 2010 移动客户端的 Apple 设备）或Microsoft 推送通知服务（MPNS）（适用于运行 Lync 2010 手机或 Lync 2013 移动客户端的 Windows Phone 设备）。

<div>


> [!IMPORTANT]  
> 如果您将 Windows Phone 与 Lync 2010 移动版或 Lync 2013 移动客户端配合使用，推送通知是重要的考虑因素。<BR>如果在 Apple 设备上使用 Lync 2010 Mobile，推送通知是重要的考虑因素。<BR>如果在 Apple 设备上使用 Lync 2013 Mobile，则不再需要推送通知。



</div>

通过执行下列操作配置拓扑以支持推送通知：

  - 如果你的环境具有 Lync Server 2010 或 Lync Server 2013 Edge 服务器，你需要添加新的托管提供商和 Microsoft Lync Online，然后在你的组织和 Lync Online 之间设置托管提供商联合身份验证。

  - 如果你的环境具有 Office 通信服务器 2007 R2 Edge 服务器，你需要使用 push.lync.com 设置直接 SIP 联合身份验证。
    
    <div>
    

    > [!NOTE]  
    > Push.lync.com 是推送通知服务的 Microsoft Office 365 域。

    
    </div>

  - 若要启用推送通知，你需要运行**CsPushNotificationConfiguration** cmdlet。 默认情况下，推送通知已关闭。

  - 测试联合身份验证配置和推送通知。

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a>要配置 Lync Server 2013 或 Lync Server 2010 Edge 服务器的推送通知

1.  登录到安装了 Lync Server 命令行管理器和 Ocscore 的计算机作为 RtcUniversalServerAdmins 组的成员。

2.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

3.  添加 Lync Server online 托管提供商。 在命令行中键入：
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    例如：
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > 一个托管提供程序不能有多个联合关系。 也就是说，如果你已设置与 sipfed.online.lync.com 的联合关系的托管提供商，请不要为其添加另一个托管提供程序，即使托管提供程序的标识是 LyncOnline 以外的其他内容。

    
    </div>

4.  在 Lync Online 上设置你的组织和推送通知服务之间的托管提供程序联合身份验证。 在命令行中键入：
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a>配置 Office 通信服务器 2007 R2 Edge 服务器的推送通知

1.  以 RtcUniversalServerAdmins 组成员的身份登录到边缘服务器。

2.  单击 "**开始**"，单击 "**所有程序**"，单击 "**管理工具**"，然后单击 "**计算机管理**"。

3.  在控制台树中，展开 "**服务和应用程序**"，右键单击 " **Microsoft Office 通信服务器 2007 R2**"，然后单击 "**属性**"。

4.  在 "**允许**" 选项卡上，单击 "**添加**"。

5.  在 "**添加联盟合作伙伴**" 对话框中，执行下列操作：
    
      - 在 "**联盟伙伴域名**" 中，键入**push.lync.com**。
    
      - 在 "**联盟伙伴访问边缘服务器**" 中，键入**sipfed.online.lync.com**。
    
      - 单击“**确定**”。

</div>

<div>

## <a name="to-enable-push-notifications"></a>启用推送通知

1.  登录到 Lync Server Management Shell 和 Ocscore 作为 CsAdministrator 角色的成员进行安装的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

3.  启用推送通知。 在命令行中键入：
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  启用联盟。 在命令行中键入：
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a>测试联盟和推送通知

1.  登录到 Lync Server Management Shell 和 Ocscore 作为 CsAdministrator 角色的成员进行安装的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

3.  测试联合身份验证配置。 在命令行中键入：
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    例如：
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  测试推送通知。 在命令行中键入：
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    例如：
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a>另请参阅


[Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

