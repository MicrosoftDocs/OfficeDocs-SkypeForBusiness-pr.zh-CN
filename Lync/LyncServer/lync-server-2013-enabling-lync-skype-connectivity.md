---
title: Lync Server 2013：启用 Lync-Skype 连接
TOCTitle: 启用 Lync-Skype 连接
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn440170(v=OCS.15)
ms:contentKeyID: 59602816
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中启用 Lync-Skype 连接

 

_**上一次修改主题：** 2016-12-08_

在提交设置请求后，您可以集中精力关注 Lync Server 环境和配置 Lync-Skype 连接所需的管理任务。在此部分中，我们假设 Lync Server 管理员已部署 Lync Server 并配置了外部访问。有关为 Lync Server 配置外部访问的其他信息，请参阅 [在 Lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)和 [在 Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)。

要针对 Lync-Skype 连接准备 Lync Server 环境，Lync Server 管理员必须完成以下三个任务：

## 1\. 配置联盟和 PIC

需要联盟，Skype 用户才能与您的组织中的 Lync 用户进行通信。公共即时消息连接 (PIC) 是一种联盟类别，必须配置它，您的 Lync 用户才能够与 Skype 用户进行通信。联盟和 PIC 可使用 Lync Server 控制面板进行配置，如下所示。

![显示 PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "显示 PIC")

> [!IMPORTANT]
> Live Communication Server 2005 SP1 或 Office Communications Server 2007 不再支持 PIC 联盟。支持 PIC 联盟的平台包括 Lync Server 2013、Lync Server 2010 和 Office Communications Server 2007 R2。


## 2\. 配置至少一个策略以支持联盟的用户访问

使用 Lync Server 控制面板，管理员必须配置一个或多个外部用户访问策略来控制 Skype 用户能否与内部 Lync Server 用户进行协作。

![策略](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "策略")

## 3\. 针对 Lync 配置 Skype PIC 提供商设置

使用 Lync Server 命令行管理程序，管理员必须配置 Lync 客户端策略以将 Skype 显示为附加 PIC 提供商。

> [!NOTE]  
> 只有至少再配置一个策略（步骤 2，此过程前面所述）以支持公共 IM 连接，公共即时消息连接 (PIC) 服务提供商的用户才能参与组织中的 IM、音频或视频会议。



1.  要配置联盟和 PIC，请参阅"启用或禁用联盟和公共 IM 连接"，网址为 [http://go.microsoft.com/fwlink/p/?LinkId=306063](http://go.microsoft.com/fwlink/p/?linkid=306063)。

2.  要至少配置一个策略以支持联盟的用户访问，请参阅"配置策略以控制公共用户访问"，网址为 [http://go.microsoft.com/fwlink/p/?LinkId=306064](http://go.microsoft.com/fwlink/p/?linkid=306064)。

**编辑 Messenger PIC 提供商并针对 Skype 对其进行配置**

1.  从 Lync Server 前端服务器，打开 Lync Server 命令行管理程序。

2.  运行以下两个命令：
    
    `Remove-CsPublicProvider -Identity Messenger`
    
    `New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png" -VerificationLevel 2 -Enabled 1`

3.  从 Lync 客户端，您现在可以选择 Skype 作为 PIC 提供商，并通过指定其 Microsoft 帐户来添加 Skype 客户端。此外，已合并并使用其 Microsoft 帐户登录的 Skype 用户可以向 Lync 用户发送联系人请求。有关 Microsoft 帐户的详细信息，请参阅[什么是 Microsoft 帐户？](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account)。有关向 Lync 添加客户端的附加信息，请参阅[在 Lync Server 2013 中使用 Lync-Skype 连接作为最终用户](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)。
    
    ![添加 Skype 联系人](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "添加 Skype 联系人")

4.  有关修改托管提供商的详细信息，请参阅"创建或编辑托管的 SIP 联盟提供商"，网址为 [http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065)。

这将完成必须在服务器上执行的管理任务。您现在可以设置 Lync-Skype 连接。

