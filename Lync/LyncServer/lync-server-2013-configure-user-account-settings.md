---
title: Lync Server 2013：配置用户帐户设置
TOCTitle: 配置用户帐户设置
ms:assetid: b7c74ecc-b924-4efc-8a56-3a5f94a9ef13
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412896(v=OCS.15)
ms:contentKeyID: 49314027
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置用户帐户设置

 

_**上一次修改主题：** 2016-12-08_

拨入用户输入其电话号码或分机号和 PIN，即可以经过身份验证的用户身份加入会议。身份验证需要 Lync Server 用户帐户上指定的电话“线路 URI”。

本主题中的过程介绍如何为单个用户帐户分配“线路 URI”。如果需要为多个用户帐户分配“线路 URI”，则可以创建使用 **Set-CsUser** cmdlet 的脚本。有关使用示例脚本将“线路 URI”分配给多个用户帐户的详细信息，请参阅“为多个用户分配线路 URI”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=196945](http://go.microsoft.com/fwlink/p/?linkid=196945)。

## 配置用户帐户设置

1.  以 RTCUniversalServerAdmins 组成员或者 **Cs-UserAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左导航栏中，单击“用户”。

4.  在搜索字段中，键入要为其配置电话拨入式会议的用户的名称，或单击“添加筛选器”以指定搜索字段，然后单击“查找”。

5.  双击用户名打开“编辑 Lync Server 用户”对话框。

6.  在“电话”下的“线路 URI”字段中，键入唯一的规范化电话号码（例如，tel:+14255550200）。
    
    > [!NOTE]  
    > 仅当将“电话”设置为“仅限 PC 到 PC”、“企业语音”、“远程呼叫控制”或“仅远程呼叫控制”时，才可以指定“线路 URI”。
    


7.  单击“提交”。

