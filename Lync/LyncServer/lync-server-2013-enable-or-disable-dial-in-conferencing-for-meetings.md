---
title: 启用或禁用会议的拨入式会议
TOCTitle: 启用或禁用会议的拨入式会议
ms:assetid: 418dcf2d-c8d6-4b2c-b1ab-8723c7ef53e0
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688036(v=OCS.15)
ms:contentKeyID: 49888392
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 启用或禁用会议的拨入式会议

 

_**上一次修改主题：** 2012-11-01_

以下过程介绍如何允许用户通过电话拨入加入会议。

## 启用/禁用电话拨入式会议

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“会议”，然后单击“会议策略”。

4.  在会议策略列表中，选择要为其启用电话拨入式会议的策略，单击“编辑”，然后单击“显示详细信息”。

5.  若要允许用户通过电话拨入加入会议，请选中“启用 PSTN 电话拨入式会议”复选框。默认情况下，用户可以通过使用公用电话交换网 (PSTN) 进行电话拨入来加入会议。

6.  单击“提交”。

