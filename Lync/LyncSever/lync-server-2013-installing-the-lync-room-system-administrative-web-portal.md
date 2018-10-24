---
title: 安装 Lync Room System 管理 Web 门户
TOCTitle: 安装 Lync Room System 管理 Web 门户
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn436326(v=OCS.15)
ms:contentKeyID: 59602827
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 安装 Lync Room System 管理 Web 门户

 

_**上一次修改主题：** 2016-12-08_

您可以从 Microsoft 下载中心下载 Microsoft Lync Room System 管理 Web 门户，网址为 [http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044)。

要安装 Lync Room System 管理 Web 门户，请使用以下步骤。

1.  通过在 Lync Server 命令行管理程序 中运行以下 cmdlet 来配置受信任的应用程序端口：
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  要安装会议室门户，请下载 **LyncRoomAdminPortal.exe**，然后以管理员身份运行它。

3.  从以下位置打开 Web.config 文件：
    
    %Program Files%\\Microsoft Lync Server 2013\\Web Components\\Meeting Room Portal\\Int\\Handler\\

4.  在 Web.Config 文件中，将 PortalUserName 更改为在“配置 Lync Room System 管理门户的先决条件”部分下的步骤 2 中创建的用户名（步骤中建议的名称为 LRSApp）：
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  由于 LRS 管理门户是受信任的应用程序，您不需要在门户配置中提供密码。如果此用户正在使用的注册机构不同于本地注册机构，您需要通过在 Web.Config 文件中添加以下行来为其指定注册机构：
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  如果使用的端口不是 5061，请在 Web.Config 文件中添加以下行：
    
        <add key="PortalUserRegistrarPort" value="5061" />

## 验证 Lync Room System 管理 Web 门户的安装

要验证 Lync Room System 管理 Web 门户的安装，请执行以下操作：


1.  在前端服务器上，浏览到以下 URL：
    
    https://\<fe-server\>/lrs
    
    您应不会看到任何错误，如下图所示：
    
    ![Lync 聊天室系统管理门户登录屏幕](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync 聊天室系统管理门户登录屏幕")

2.  如果未看到任何错误，请尝试从拓扑中的任何其他计算机访问以下 URL：
    
    https://\<fe-server\>/lrs
    
    要访问该页面，您需要按“自动客户端登录需要的 DNS 记录”所述添加 DNS 记录，网址为 [http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056)。

