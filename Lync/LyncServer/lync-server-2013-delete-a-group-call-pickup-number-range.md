---
title: 删除组内呼叫应答号码范围
TOCTitle: 删除组内呼叫应答号码范围
ms:assetid: 521891f3-7a5d-45de-92dc-d57025453159
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ945629(v=OCS.15)
ms:contentKeyID: 52061024
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除组内呼叫应答号码范围

 

_**上一次修改主题：** 2013-01-30_

使用以下过程删除组内呼叫应答号码范围。

## 删除呼叫应答组号码范围

1.  以 RTCUniversalServerAdmins 组成员的身份或利用[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述的必要用户权限登录安装了 Lync Server 命令行管理程序的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  在命令行中键入：
    
        Remove-CsCallParkOrbit -Identity "<group number range name>" 
    
    例如：
    
        Remove-CsCallParkOrbit -Identity "Redmond call pickup"
    
    > [!NOTE]  
    > 有关更多选项的详细信息，请参阅 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</a>。
    


## 另请参阅

#### 任务

[在 Lync Server 2013 中创建或修改呼叫寄存通道范围](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  

#### 其他资源

[Remove-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCallParkOrbit)  
[Get-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCallParkOrbit)

