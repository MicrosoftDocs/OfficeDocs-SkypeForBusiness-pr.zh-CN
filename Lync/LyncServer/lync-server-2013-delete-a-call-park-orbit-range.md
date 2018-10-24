---
title: 在 Lync Server 2013 中删除呼叫寄存通道范围
TOCTitle: 在 Lync Server 2013 中删除呼叫寄存通道范围
ms:assetid: 85e9f916-062d-450d-ac0a-aeaefc0f7cdc
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182546(v=OCS.15)
ms:contentKeyID: 49313498
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中删除呼叫寄存通道范围

 

_**上一次修改主题：** 2013-02-20_

使用下列过程之一删除呼叫寄存通道范围。

## 使用 Lync Server 控制面板删除呼叫寄存通道范围

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“语音功能”，然后单击“呼叫寄存”。

4.  在“呼叫寄存”页上的搜索字段中，键入要删除的通道范围的全部或部分名称。

5.  在通道的结果列表中，单击通道，再单击“编辑”，然后单击“删除”。

6.  单击“确定”。

## 使用 Cmdlet 删除呼叫寄存通道范围

1.  以 RTCUniversalServerAdmins 组成员的身份或利用[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述的必要用户权限登录安装了 Lync Server 命令行管理程序的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  在命令行中键入：
    
        Remove-CsCallParkOrbit -Identity "<orbit range name>" 
    
    例如：
    
        Remove-CsCallParkOrbit -Identity "Redmond orbit 1"
    
    > [!NOTE]  
    > 有关更多选项的详细信息，请参阅 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</a>。
    


## 另请参阅

#### 任务

[在 Lync Server 2013 中创建或修改呼叫寄存通道范围](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  

#### 其他资源

[Remove-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCallParkOrbit)  
[Get-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCallParkOrbit)

