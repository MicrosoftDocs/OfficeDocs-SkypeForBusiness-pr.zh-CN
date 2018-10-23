---
title: Lync Server 2013：创建或编辑公共 SIP 联盟提供程序
TOCTitle: 创建或编辑公共 SIP 联盟提供程序
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398349(v=OCS.15)
ms:contentKeyID: 49312855
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中创建或编辑公共 SIP 联盟提供程序

 

_**上一次修改主题：** 2012-10-19_

通过公共即时消息 (IM) 连接，组织中的用户可以使用 IM 与公共 IM 服务提供程序（包括 Windows Live Messenger、Yahoo\! 和 AOL）提供的 IM 服务的用户进行通信。

Lync Server 2013 包含针对 America Online、Windows Live 和 Yahoo\! 即时消息的公共提供程序配置。每个公共提供程序均使用提供程序的边缘服务器完全限定域名和默认验证级别“仅允许用户与其联系人列表中使用此提供程序的人员进行通信”进行配置。

作为默认设置，将不启用任何公共提供程序。您应先完成许可协议和设置工作，然后再启用公共提供程序。您可以先启用提供程序，然后再完成许可和设置工作。在完成首要工作之前，用户将无法与这些提供程序的联系人进行通信。有关公共提供程序的许可和设置的详细信息，请参阅 [在 Lync Server 2013 中配置策略以控制公共用户访问](lync-server-2013-configure-policies-to-control-public-user-access.md)。

使用以下过程可创建或编辑公共提供程序：

## 创建或编辑公共提供程序

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“联盟和外部访问”，然后单击“SIP 联盟提供程序”。

4.  如果您需要创建新的公共提供程序，请单击“新建”，然后单击“公共提供程序”。

5.  如果您需要编辑公共提供程序列表中的条目，请选择一个公共提供程序，单击“编辑”，然后单击“显示详细信息”。

6.  在“编辑 SIP 联盟提供程序”页上，可以键入或编辑以下设置：
    
      - **允许与此提供程序进行通信**    选择此设置可为此提供程序的用户启用 IM。
    
      - **提供程序名称**    必需属性，键入此提供程序的名称，因为 SIP 联盟提供程序的列表中将反映此名称。
    
      - **访问边缘服务 (FQDN)**    必需属性，键入您正在配置的提供程序的访问边缘服务的完全限定域名。此信息作为默认项提供，并且只应在公共提供程序更改其访问边缘服务的 FQDN 时被更改。
    
      - **默认验证级别**    默认设置“允许用户与其联系人列表中使用此提供程序的人员进行通信”将只允许与您接受的且位于您的联系人列表中的联系人进行通信。
        
        选择“允许用户与使用此提供程序的每个人通信”将去除您必须接收和接受联系人邀请的限制。此设置不会对可从公共提供程序网络与您联系的人员进行限制。

7.  配置完这些设置后，请单击“提交”以进行保存，或单击“取消”以放弃更改。

## 另请参阅

#### 任务

[在 Lync Server 2013 中配置策略以控制公共用户访问](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

