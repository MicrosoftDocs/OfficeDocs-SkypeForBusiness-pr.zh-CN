---
title: Lync Server 2013：针对 Lync Room System 管理 Web 门户配置您的环境
TOCTitle: 针对 Lync Room System 管理 Web 门户配置您的环境
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn436325(v=OCS.15)
ms:contentKeyID: 59602815
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 针对 Lync Room System 管理 Web 门户配置您的 Lync Server 2013 环境

 

_**上一次修改主题：** 2016-12-08_

要使用 Lync Room System (LRS) 管理 Web 门户，您需要安装或配置以下先决条件。

> [!IMPORTANT]
> 如果服务器配置了 Kerberos 和 NTLM 身份验证，并且 LRS 在未加入域的计算机上运行，则 Kerberos 身份验证将会失败，并且用户在管理门户中看不到 LRS 的状态。要解决此问题，请为服务器配置 NTLM 身份验证或者 NTLM 和 TLS-DSK 身份验证（无 Kerberos），或者将 LRS 计算机加入域。


1.  在 Lync Server 拓扑中安装 2013 年 7 月的 Lync Server 2013 累积更新。
    
    要获取更新或查看其涵盖内容，请参阅 [Lync Server 2013 的更新](http://go.microsoft.com/fwlink/p/?linkid=323959)。

2.  创建启用了 SIP 的 Active Directory 用户。
    
    LRS 管理 Web 门户使用这些凭据从 Lync Server 查询信息。推荐的用户名为 LRSApp。

3.  创建名称为 LRSSupportAdminGroup 的 Active Directory 安全组。
    
    创建组作用域为“全局”、“组类型”为“安全”的组。添加到此组启用了 SIP 的用户将被授权查看聊天室列表并执行特定命令（例如收集日志）。

4.  创建名称为 LRSFullAccessAdminGroup 的 Active Directory 安全组。
    
    创建组作用域为“全局”、“组类型”为“安全”的组。添加到此组启用了 SIP 的用户将被授权使用所有管理门户功能。
    
     
    
    ![具有安全组角色的 Admin 组的列表](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "具有安全组角色的 Admin 组的列表")  
    
     

5.  将 LRSFullAccessAdminGroup 添加为 LRSSupportAdminGroup 的成员。
    
    ![LRSSupportAdminGroup 属性 -“成员”页](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup 属性 -“成员”页")  
    
     

6.  创建名称为 LRSSupport 的启用了 SIP 的 Active Directory 用户。将此用户添加到 LRSSupportAdminGroup。
    
    ![LRSSupportAdminGroup 属性 -“成员”页](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup 属性 -“成员”页")  
    
     

7.  安装 ASP.NET MVC 4 for Visual Studio 2010 SP1 和 Visual Web Developer 2010 SP1，它们在 Microsoft 下载中心上提供，网址为 [http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967)。

