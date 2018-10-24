---
title: 禁用用于企业语音的用户
TOCTitle: 禁用用于企业语音的用户
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49888398
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 禁用用于企业语音的用户

 

_**上一次修改主题：** 2012-09-21_

使用以下过程禁用已启用 Lync Server 2013 的用户帐户的企业语音。

## 对用户帐户禁用企业语音

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“用户”。

4.  在“搜索用户”框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”。

5.  在表中，单击要为之启用企业语音的用户帐户。

6.  在“编辑”菜单上，单击“显示详细信息”。

7.  在“编辑 Lync Server 用户”页的“电话”下，单击“企业语音”。
    
    > [!NOTE]  
    > 若要通过使用 Lync 限制用户发出音频或视频呼叫，请在“电话”下，单击“禁用音频/视频”。
    


8.  单击“提交”。

用户现在将无法使用企业语音功能。

## 另请参阅

#### 任务

[在 Lync Server 2013 中为用户启用企业语音](lync-server-2013-enable-users-for-enterprise-voice.md)  

#### 其他资源

[管理用户的企业语音](lync-server-2013-managing-enterprise-voice-for-users.md)  
[Lync Server 命令行管理程序](lync-server-2013-lync-server-management-shell.md)

