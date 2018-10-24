---
title: 删除未分配号码范围
TOCTitle: 删除未分配号码范围
ms:assetid: a8141bfb-b94d-4d0f-a7a9-2e60d10b103a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182565(v=OCS.15)
ms:contentKeyID: 49313856
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除未分配号码范围

 

_**上一次修改主题：** 2012-11-01_

使用以下其中一个过程删除通知的未分配号码范围。

## 使用 Lync Server 控制面板删除未分配的号码范围

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“语音功能”，然后单击“未分配号码”。

4.  在“未分配号码”页上的搜索字段中，键入要删除的未分配号码范围的全部或部分名称。

5.  在号码范围的结果列表中，单击名称，再单击“编辑”，然后单击“删除”。

6.  单击“全部提交”。

## 使用 Cmdlet 删除未分配的号码范围

1.  以 RTCUniversalServerAdmins 组成员的身份或利用[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述的必要用户权限登录安装了 Lync Server 命令行管理程序的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  在命令行中键入：
    
        Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
    
    例如：
    
        Remove-CsUnassignedNumber -Identity "Unassigned range 1"
    
    > [!NOTE]  
    > 有关更多选项的详细信息，请参阅 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</a>。
    


## 另请参阅

#### 任务

[在 Lync Server 2013 中创建或修改未分配号码范围](lync-server-2013-create-or-modify-an-unassigned-number-range.md)  

#### 其他资源

[Remove-CsUnassignedNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsUnassignedNumber)  
[Get-CsUnassignedNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUnassignedNumber)

