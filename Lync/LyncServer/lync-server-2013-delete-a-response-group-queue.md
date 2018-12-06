---
title: 删除响应组队列
TOCTitle: 删除响应组队列
ms:assetid: 67c7a489-8c5f-4c6b-9387-9d4c11d43695
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg521008(v=OCS.15)
ms:contentKeyID: 49313110
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除响应组队列

 

_**上一次修改主题：** 2012-11-01_

使用下列过程之一删除队列。

## 使用 Lync Server 控制面板删除队列

1.  以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“响应组”，然后单击“队列”。

4.  在搜索字段中，键入要删除的队列的部分或全部名称。

5.  在队列列表中，单击所需的队列，再单击“编辑”，然后单击“删除”。

6.  单击“确定”。

## 使用 cmdlet 删除队列

1.  以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  在命令行中运行：
    
        Get-CsRgsQueue -Identity <Application Server service> -Name "<name of queue>" | Remove-CsRgsQueue
    
    例如：
    
        Get-CsRgsQueue -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsQueue

