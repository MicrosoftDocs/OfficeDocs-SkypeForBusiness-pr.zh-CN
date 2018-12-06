---
title: Lync Server 2013：配置与会页面
TOCTitle: 配置与会页面
ms:assetid: 45880423-47f4-49af-b825-cbd8e3fc1046
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204861(v=OCS.15)
ms:contentKeyID: 49312707
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置与会页面

 

_**上一次修改主题：** 2015-03-09_

用户单击会议请求中的会议链接时，与会页面将检测该用户的计算机上是否已安装 Lync 2013 客户端。如果已安装客户端，则将打开该客户端并加入会议。如果没有安装客户端，则将打开默认的 2013 版本的 Lync Web App。

如果您要允许用户使用 Office Communicator 2007 R2 或 Lync 2010 Attendant 来加入会议，则可以修改与会页面的行为。已从 Lync Server 2013 控制面板中删除了这些配置选项，但您可使用 Set-CsWebServiceConfiguration cmdlet 配置它们。

### 与会页面 Set-CsWebServiceConfiguration 参数

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Set-CsWebServiceConfiguration 参数</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ShowJoinUsingLegacyClientLink</p></td>
<td><p>如果设置为 True，则当通过客户端应用程序而非 Lync 加入会议时，用户可使用 Office Communicator 2007 R2 加入会议。默认值为 False。</p></td>
</tr>
<tr class="even">
<td><p>ShowAlternateJoinOptionsExpanded</p></td>
<td><p>如果设置为 True，则用于加入联机会议的替代选项（如 Office Communicator 2007 R2）将自动展开并显示给用户。如果设置为 False（默认值），这些选项将可用，但用户需要自己显示选项列表。</p></td>
</tr>
</tbody>
</table>


## 使用 Lync Server 2013 命令行管理程序配置与会页面

1.  启动 Lync Server 2013 命令行管理程序：依次单击“开始”、“所有程序”、“Microsoft Lync Server 2013”和“Lync Server 命令行管理程序”。

2.  若要查看 Web 服务配置设置，请运行以下 cmdlet：
    
        Get-CsWebServiceConfiguration

3.  运行以下命令，其中的参数设置为 True 或 False，具体取决于您的首选项（有关此 cmdlet 的参数的详细信息，请参阅 Lync Server 2013 命令行管理程序 文档中的 [Set-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsWebServiceConfiguration)：
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

## 另请参阅

#### 其他资源

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsWebServiceConfiguration)

