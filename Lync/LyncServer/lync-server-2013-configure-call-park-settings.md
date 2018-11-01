---
title: 在 Lync Server 2013 中配置呼叫寄存设置
TOCTitle: 在 Lync Server 2013 中配置呼叫寄存设置
ms:assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425886(v=OCS.15)
ms:contentKeyID: 49312564
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置呼叫寄存设置

 

_**上一次修改主题：** 2015-03-09_

如果不想使用默认呼叫寄存设置，则也可以自定义该设置。安装呼叫寄存应用程序时，默认情况下将配置全局设置。您可以修改全局设置，也可以指定特定于站点的设置。使用 **New-CsCpsConfiguration** cmdlet 可创建新的特定于站点的设置。使用 **Set-CsCpsConfiguration** cmdlet 可修改现有设置。

> [!NOTE]  
> 寄存呼叫超时且回拨失败时，我们建议您至少为要使用的回退目标配置 <strong>OnTimeoutURI</strong> 选项。



使用 **New-CsCpsConfiguration** cmdlet 或 **Set-CsCpsConfiguration** cmdlet 配置以下任何设置：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>此选项：</th>
<th>指定以下内容：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>CallPickupTimeoutThreshold</strong></p></td>
<td><p>呼叫寄存后到回拨此前应答呼叫的电话之前等待的时间。</p>
<p>该值必须采用 hh:mm:ss 的格式输入，以便指定小时数、分钟数和秒数。最小值为 10 秒，最大值为 10 分钟。默认值为 00:01:30。</p></td>
</tr>
<tr class="even">
<td><p><strong>EnableMusicOnHold</strong></p></td>
<td><p>寄存呼叫时是否向呼叫者播放音乐。</p>
<p>值为 True 或 False。默认值为 True。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCallPickupAttempts</strong></p></td>
<td><p>在将寄存呼叫转接到为 <strong>OnTimeoutURI</strong> 指定的回退统一资源标识符 (URI) 之前该寄存呼叫回拨应答电话的次数。默认值为 1。</p></td>
</tr>
<tr class="even">
<td><p><strong>OnTimeoutURI</strong></p></td>
<td><p>超出 <strong>MaxCallPickupAttempts</strong> 时未应答的寄存呼叫将路由到的用户或响应组的 SIP 地址。</p>
<p>值必须为以字符串 sip: 开头的 SIP URI。例如，sip:bob@contoso.com。默认情况下没有转接地址。</p></td>
</tr>
</tbody>
</table>


## 配置呼叫寄存设置

1.  以 RTCUniversalServerAdmins 组成员的身份或利用[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述的必要用户权限登录安装了 Lync Server 命令行管理程序的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  运行：
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    
    > [!TIP]
    > 使用 <strong>Get-CsSite</strong> cmdlet 可标识站点。有关详细信息，请参阅 Lync Server 命令行管理程序文档。
    
    例如：
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

## 另请参阅

#### 任务

[在 Lync Server 2013 中自定义保持呼叫寄存音乐](lync-server-2013-customize-call-park-music-on-hold.md)  

#### 其他资源

[New-CsCpsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCpsConfiguration)  
[Set-CsCpsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCpsConfiguration)  
[Get-CsSite](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsSite)

