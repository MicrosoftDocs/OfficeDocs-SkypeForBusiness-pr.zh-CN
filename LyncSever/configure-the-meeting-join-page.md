---
title: 配置与会页面
TOCTitle: 配置与会页面
ms:assetid: 036c9d03-ad95-4d63-a3d8-6cae1a8ad530
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204635(v=OCS.15)
ms:contentKeyID: 49311838
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置与会页面

 

_**上一次修改主题：** 2015-03-09_

用户单击会议请求中的会议链接时，会议加入页面将检测该用户的计算机上是否已安装 Lync 2013 客户端。如果已安装客户端，将打开该客户端并加入会议。如果未安装客户端，默认情况下会打开 Lync Web App 的 2013 版本。

如果想要允许用户通过 Office Communicator 2007 R2 或 Lync 2010 Attendant 加入会议，则可以修改会议加入页面的行为。这些配置选项已从 Lync Server 2013 控制面板中删除，但是您可以使用 CsWebServiceConfiguration cmdlet 来配置它们。

### 会议加入页面 CsWebServiceConfiguration 参数

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>CsWebServiceConfiguration 参数</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ShowJoinUsingLegacyClientLink</p></td>
<td><p>如果设置为 True，则将会为使用除 Lync 以外的客户端应用程序加入会议的用户提供一次使用 Office Communicator 2007 R2 加入会议的机会。默认值为 False。</p></td>
</tr>
<tr class="even">
<td><p>ShowAlternateJoinOptionsExpanded</p></td>
<td><p>如果设置为 True，则用于加入联机会议的替代选项（如 Office Communicator 2007 R2）将自动展开并显示给用户。如果设置为 False（默认值），这些选项将可用，但用户需要自己显示选项列表。</p></td>
</tr>
</tbody>
</table>


## 使用 Lync Server 2013 命令行管理程序配置会议加入页面

1.  启动 Lync Server 2013 命令行管理程序：依次单击“开始”、“所有程序”、“Microsoft Lync Server 2013”和“Lync Server 命令行管理程序”。

2.  运行以下 cmdlet：
    
        Get-CsWebServiceConfiguration
    
    此 cmdlet 将返回 Web 服务配置设置。

3.  运行以下命令，其中的参数设置为 True 或 False，具体取决于您的首选项（有关此 cmdlet 的参数的详细信息，请参阅 Lync Server 2013 命令行管理程序文档）：
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

