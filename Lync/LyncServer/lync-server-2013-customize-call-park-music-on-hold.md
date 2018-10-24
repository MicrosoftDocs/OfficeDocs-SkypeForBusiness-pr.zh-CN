---
title: 在 Lync Server 2013 中自定义保持呼叫寄存音乐
TOCTitle: 在 Lync Server 2013 中自定义保持呼叫寄存音乐
ms:assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688031(v=OCS.15)
ms:contentKeyID: 49888387
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中自定义保持呼叫寄存音乐

 

_**上一次修改主题：** 2012-09-10_

可以指定您自己的要用于保留音乐的音乐文件，而不是指定 Lync Server 2013 附带的默认音乐文件。若要自定义保留音乐，请使用 **Set-CsCallParkServiceMusicOnHoldFile** cmdlet。

> [!NOTE]  
> 如果您自定义保留音乐并希望多个网站使用同一音乐，则必须为运行呼叫寄存应用程序的每个网站配置音乐文件。



## 自定义音乐文件

1.  以 RTCUniversalServerAdmins 组成员的身份或利用[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述的必要用户权限登录安装了 Lync Server 命令行管理程序的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  运行：
    
        Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte[]>
    
    > [!TIP]
    > 使用 <strong>Get-CsService</strong> cmdlet 可标识服务。有关详细信息，请参阅 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsService">Get-CsService</a>。
    
    以下示例说明了如何以字节数组的形式获取文件 soothingmusic.wma 的内容并将其分配给变量。然后，将音频文件指定为呼叫寄存的保留音乐文件。有关详细信息，请参阅 [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)。
    
        $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
        Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a

## 另请参阅

#### 其他资源

[Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)  
[Get-CsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsService)

