---
title: Lync Server 2013：为推送通知配置
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
ms.openlocfilehash: ad1967bea18e0a03ac3a34bf187c1248ec5a1ab2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197791"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-for-push-notifications-in-lync-server-2013"></a>在 Lync Server 2013 中配置推送通知

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-12_

即使移动应用程序处于非活动状态，也可以向移动设备发送推送通知（以徽章、图标或警告的形式）。 推送通知会将一些事件（例如，新的或错过的 IM 邀请和语音邮件）告知用户。 Lync Server 2013 移动服务将通知发送到基于云的 Lync Server 推送通知服务，后者随后会将通知发送到 Apple 推送通知服务（APNS）（对于运行 Lync 2010 移动客户端的 Apple 设备）或Microsoft 推送通知服务（MPNS）（适用于运行 Lync 2010 Mobile 或 Lync 2013 移动客户端的 Windows Phone 设备）。

<div>


> [!IMPORTANT]  
> 如果您将 Windows Phone 与 Lync 2010 移动或 Lync 2013 移动客户端一起使用，则推送通知是一个重要的考虑事项。<BR>如果您在 Apple 设备上使用 Lync 2010 移动，则推送通知是一个重要的考虑事项。<BR>如果在 Apple 设备上使用 Lync 2013 Mobile，则不再需要推送通知。



</div>

通过执行下列操作，将您的拓扑配置为支持推送通知：

  - 如果你的环境具有 Lync Server 2010 或 Lync Server 2013 边缘服务器，则需要添加新的托管提供程序（Microsoft Lync Online），然后在你的组织和 Lync Online 之间设置托管提供程序联合。

  - 如果您的环境具有 Office 通信服务器 2007 R2 边缘服务器，则需要设置与 push.lync.com 的直接 SIP 联盟。
    
    <div>
    

    > [!NOTE]  
    > Push.lync.com 是一个适用于推送通知服务的 Microsoft Office 365 域。

    
    </div>

  - 若要启用推送通知，您需要运行 **Set-CsPushNotificationConfiguration** cmdlet。 默认情况下，推送通知已关闭。

  - 测试联盟配置和推送通知。

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a>使用 Lync Server 2013 或 Lync Server 2010 边缘服务器配置推送通知

1.  以 RtcUniversalServerAdmins 组成员的身份登录到安装了 Lync Server 命令行管理程序和 Ocscore 的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  添加 Lync Server online 承载提供程序。 在命令行中键入：
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    例如：
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > 您不能与一个宿主提供程序建立多个联盟关系。也就是说，如果您已设置一个与 sipfed.online.lync.com 建立了联盟关系的宿主提供程序，则请不要为其添加其他宿主提供程序，即使该宿主提供程序的标识不是 LyncOnline 也是如此。

    
    </div>

4.  在 Lync Online 上设置组织与推送通知服务之间的宿主提供程序联盟。在命令行中键入：
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a>使用 Office 通信服务器 2007 R2 边缘服务器配置推送通知

1.  以 RtcUniversalServerAdmins 组成员的身份登录到边缘服务器。

2.  依次单击“开始”****、“所有程序”****、“管理工具”**** 和“计算机管理”****。

3.  在控制台树中，展开“服务和应用程序”****，右键单击“Microsoft Office Communications Server 2007 R2”****，然后单击“属性”****。

4.  在“允许”**** 选项卡上，单击“添加”****。

5.  在“添加联盟伙伴”**** 对话框中，执行下列操作：
    
      - 在“联盟伙伴域名”**** 中，键入 **push.lync.com**。
    
      - 在“联盟伙伴访问边缘服务器”**** 中，键入 **sipfed.online.lync.com**。
    
      - 单击“确定”****。

</div>

<div>

## <a name="to-enable-push-notifications"></a>启用推送通知

1.  以 CsAdministrator 角色的成员身份登录到安装了 Lync Server 命令行管理程序和 Ocscore 的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  启用推送通知。在命令行中键入：
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  启用联盟。在命令行中键入：
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a>测试联盟和推送通知

1.  以 CsAdministrator 角色的成员身份登录到安装了 Lync Server 命令行管理程序和 Ocscore 的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  测试联盟配置。在命令行中键入：
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    例如：
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  测试推送通知。在命令行中键入：
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    例如：
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a>请参阅


[Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

