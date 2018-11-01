---
title: Lync Server 2013：分配会议策略以支持匿名用户
TOCTitle: 分配会议策略以支持匿名用户
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg521007(v=OCS.15)
ms:contentKeyID: 49313085
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中分配会议策略以支持匿名用户

 

_**上一次修改主题：** 2012-10-19_

默认情况下，禁止所有用户邀请匿名用户参加会议。通过配置支持匿名用户的会议策略并将该会议策略应用于特定用户，可以控制能够邀请匿名用户的用户。有关如何配置会议策略以支持匿名用户的详细信息，请参阅 [在 Lync Server 2013 中创建或修改会议策略](lync-server-2013-create-or-modify-a-conferencing-policy.md)和 [管理对 Lync Server 2013 的联盟和外部访问](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)。

使用本节中的过程可将已创建的会议策略应用于一个或多个用户或用户组。

> [!NOTE]  
> 除了配置和应用策略以允许用户邀请匿名用户之外，还必须为组织启用对匿名用户的支持。有关详细信息，请参阅 <a href="lync-server-2013-configure-policies-to-control-public-user-access.md">在 Lync Server 2013 中配置策略以控制公共用户访问</a>。



## 为匿名参与会议配置用户策略

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“会议”，然后执行下列操作之一：
    
    1.  要创建新的用户策略，请单击“新建”，然后单击“用户策略”。在“名称”字段中，创建一个唯一的名称以指示用户策略的作用范围（例如， **EnableAnonymous** 代表允许与匿名用户进行通信的用户策略）。
    
    2.  要配置现有用户策略，请单击表中列出的相应策略，再单击“编辑”，然后单击“显示详细信息”。

4.  在“会议策略”对话框中，选中“允许参与者邀请匿名用户”复选框。

5.  单击“提交”。

6.  在左侧导航栏中，单击“用户”，搜索要配置的用户帐户。

7.  在列出搜索结果的表中，单击相应的用户帐户，再单击“编辑”，然后单击“显示详细信息”。

8.  在“编辑 Lync Server 用户”中的“会议策略”下，选择具有要应用于此用户的匿名用户访问配置的用户策略。
    
    > [!NOTE]  
    > “&lt;自动&gt;”设置应用默认服务器安装设置，并由服务器自动应用。
    


要允许用户邀请匿名用户参加会议，还必须在组织中启用匿名用户支持。有关详细信息，请参阅部署文档或操作文档中的 [在 Lync Server 2013 中配置策略以控制公共用户访问](lync-server-2013-configure-policies-to-control-public-user-access.md)。

