---
title: Lync Server 2013：创建或编辑托管的 SIP 联盟提供程序
TOCTitle: 创建或编辑托管的 SIP 联盟提供程序
ms:assetid: 0dd6dcb6-a88d-46b8-9c96-b35967309bcd
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ552445(v=OCS.15)
ms:contentKeyID: 49311992
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中创建或编辑托管的 SIP 联盟提供程序

 

_**上一次修改主题：** 2012-10-19_

托管提供程序即时消息 (IM) 连接功能允许您组织中的用户使用 IM 与托管提供程序（包括 Microsoft Office 365 和 Lync Online）提供的 IM 服务的用户进行通信。

使用提供程序的边缘服务器的完全限定域名以及默认验证级别 **仅允许用户与其联系人列表上使用此提供程序的人员进行通信** 来配置每个托管提供程序。

使用以下过程创建或编辑托管提供者：

## 创建或编辑托管提供者

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“联盟和外部访问”，然后单击“SIP 联盟提供程序”。

4.  如果您需要创建一个新的托管提供者，请单击“新建”，然后单击“托管提供者”。

5.  如果您需要编辑托管提供程序列表上的一个条目，请选择一个托管提供程序，单击“编辑”，然后单击“显示详细信息”。

6.  在“编辑 SIP 联盟提供程序”页上，可以键入或编辑以下设置：
    
      - **允许与此提供程序进行通信**    选择此设置将允许与此提供程序的用户通信。
    
      - **提供程序名称**    必需属性，键入此提供程序的名称，因为 SIP 联盟提供程序的列表中将反映此名称。
    
      - **访问边缘服务(FQDN):**    这是一个必需属性，键入您正在配置的托管提供程序的访问边缘服务的完全限定域名。此信息应由托管提供程序提供，并且只应在托管提供程序对托管提供程序处的访问边缘服务的 FQDN 进行了更改时才改变。
    
      - **默认验证级别**    默认设置“允许用户与其联系人列表中使用此提供程序的人员进行通信”将只允许与您接受的且位于您的联系人列表中的联系人进行通信。
        
        选择“允许用户与所有使用此提供程序的人员通信”可取消您必须收到并接受联系人邀请的限制。此设置不限制可从托管提供者的网络与您联系的人。

7.  配置完这些设置后，请单击“提交”以进行保存，或单击“取消”以放弃更改。

## 另请参阅

#### 任务

[在 Lync Server 2013 中配置策略以控制公共用户访问](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

