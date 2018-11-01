---
title: Lync Server 2013：配置对允许的外部域的支持
TOCTitle: 配置对允许的外部域的支持
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425908(v=OCS.15)
ms:contentKeyID: 49312614
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置对允许的外部域的支持

 

_**上一次修改主题：** 2012-10-19_

如果配置了对联盟伙伴的支持，您可以管理可与组织联盟的特定域。您将一个或多个特定外部域配置为允许的联盟域。要执行此操作，请将每个域添加到允许域列表中。即使组织启用了伙伴发现，但如果域是需要与 1,000 个以上的用户通信或每秒需要发送 20 多条消息的联盟伙伴，也请执行此操作。如果组织未启用伙伴发现，则只有添加到允许域列表的外部域的用户才能与组织内的用户一起参与 IM 会话和会议。如果要将对联盟域的访问限制为运行联盟伙伴的访问边缘服务的特定服务器，可以为允许域列表中的每个域指定运行访问边缘服务的服务器的域名。

> [!NOTE]  
> 此过程描述如何配置对特定域的支持，但是实施对联盟用户的支持还需要组织启用对联盟用户的支持，并配置和应用策略以控制可与联盟用户协作的用户。有关启用对联盟用户的支持的详细信息，请参阅 <a href="lync-server-2013-enable-or-disable-remote-user-access.md">在 Lync Server 2013 中启用或禁用远程用户访问</a>。有关配置用于控制联盟的策略的详细信息，请参阅 <a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中配置策略以控制联盟用户访问</a>。



## 将外部域添加到允许域列表中

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“外部用户访问”，然后单击“联盟域”。

4.  在“联盟域”页上，单击“新建”，然后单击“允许的域”。

5.  在“新建联盟域”中，执行下列操作：
    
      - 在“域名（或 FQDN）”中，键入联盟伙伴域的名称。
        
        > [!NOTE]  
		> 此名称必须是唯一的，并且不能与运行访问边缘服务的服务器的允许域的已有名称相同。该名称的长度不能超过 256 个字符。<br />
        > 搜索联盟伙伴域名时执行后缀匹配。例如，如果键入 <strong>contoso.com</strong> ，搜索还将返回域 <strong>it.contoso.com</strong> 。<br />
        > 无法同时阻止和允许联盟合作伙伴域。 Lync Server 2013 将阻止此类事件发生，从而不必同步列表。
        
    
      - 如果要将对此联盟域的访问限制为运行访问边缘服务的特定服务器的用户，请在“访问边缘服务 (FQDN)”中键入运行访问边缘服务的联盟域的服务器的 FQDN。
    
      - 如果要提供其他信息，请在“注释”中键入要与其他系统管理员共享的有关此配置的信息。

6.  单击“提交”。

7.  对要允许的每个联盟伙伴域，重复步骤 4 至 6。

若要启用联盟用户的访问，还必须在组织中启用对联盟用户访问的支持。有关详细信息，请参阅 [在 Lync Server 2013 中启用或禁用远程用户访问](lync-server-2013-enable-or-disable-remote-user-access.md)。

此外，还必须为希望能够与联盟用户协作的用户配置和应用策略。有关详细信息，请参阅 [在 Lync Server 2013 中配置策略以控制联盟用户访问](lync-server-2013-configure-policies-to-control-federated-user-access.md)。

