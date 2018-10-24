---
title: 删除通知
TOCTitle: 删除通知
ms:assetid: 26ea7149-4470-4c22-9bab-8a4065aca44e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ687998(v=OCS.15)
ms:contentKeyID: 49888337
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除通知

 

_**上一次修改主题：** 2012-11-01_

使用以下过程可删除用于呼叫未分配号码的通知。

## 删除通知

1.  以 RTCUniversalServerAdmins 组成员的身份或利用[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述的必要用户权限登录安装了 Lync Server 命令行管理程序的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  列出组织中的所有通知。在命令行运行：
    
        Get-CsAnnouncement

4.  在结果列表中，找到要删除的通知，并复制 GUID。然后，在命令行运行：
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>" 
    
    例如：
    
        Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
    
    > [!NOTE]  
    > 有关更多选项的详细信息，请参阅 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAnnouncement">Get-CsAnnouncement</a> 和 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsAnnouncement">Remove-CsAnnouncement</a>。
    


## 另请参阅

#### 任务

[在 Lync Server 2013 中创建通知](lync-server-2013-create-an-announcement.md)  

#### 其他资源

[Remove-CsAnnouncement](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsAnnouncement)  
[Get-CsAnnouncement](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAnnouncement)

