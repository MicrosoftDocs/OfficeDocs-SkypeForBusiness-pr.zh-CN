---
title: 创建用户体验质量配置设置
TOCTitle: 创建用户体验质量配置设置
ms:assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg521006(v=OCS.15)
ms:contentKeyID: 49313062
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 创建用户体验质量配置设置

 

_**上一次修改主题：** 2015-03-09_

用户体验质量 (QoE) 指标跟踪组织内发出的音频和视频呼叫的质量，包括网络数据包丢失数量、后台噪音和“抖动”量（数据包延迟中的差异）等内容。这些指标将远离其他数据（如呼叫详细信息记录）存储在数据库中，从而使您可不依赖其他数据记录来启用和禁用 QoE。

安装 Microsoft Lync Server 2013 时，将为您创建单一的全局 QoE 配置设置集合。管理员还具有创建站点作用域的自定义设置的选项。使用这些站点作用域设置时，它们将优先于全局设置。例如，如果您为 Redmond 站点创建了站点作用域设置，则这些设置（而不是全局设置）将用于管理 Redmond 内的 QoE。

QoE 配置设置可使用 Lync Server 控制面板或 [New-CsQoEConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsQoEConfiguration) cmdlet 创建。如果您要使用 Lync Server 控制面板创建新设置，则下列选项将可供您使用：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>UI 设置</th>
<th>PowerShell 参数</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>名称</p></td>
<td><p>Identity</p></td>
<td><p>要创建的设置的唯一标识符。只能创建站点作用域的 QoE 配置设置。</p></td>
</tr>
<tr class="even">
<td><p>启用对 QoE 数据的监视</p></td>
<td><p>EnableQoE</p></td>
<td><p>指定是否将 QoE 记录收集并保存到监控数据库。</p></td>
</tr>
<tr class="odd">
<td><p>启用清除 QoE 数据功能</p></td>
<td><p>EnablePurging</p></td>
<td><p>指定经过在“QoE 数据最长保留期限(天)”中定义的持续时间后是否清除记录。</p></td>
</tr>
<tr class="even">
<td><p>QoE 数据最长保留期限(天)</p></td>
<td><p>KeepQoEDataForDays</p></td>
<td><p>从数据库清除 QoE 数据之前存储的天数。如果禁用清除，则忽略此值。</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> New-CsQoEConfiguration cmdlet 包含 Lync Server 控制面板中未提供的其他选项。有关详细信息，请参阅 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</a> 帮助主题。



## 使用 Lync Server 控制面板创建 QoE 配置设置

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“监控和存档”，然后单击“用户体验质量数据”。

4.  在“用户体验质量数据”页上，单击“新建”。

5.  在“选择站点”中，单击要应用此策略的站点，然后单击“确定”。

6.  在“新建用户体验质量设置”中，执行下列操作：
    
      - 选择“启用对 QoE 数据的监视”以启用监视。
    
      - 选择“启用清除 QoE 数据功能”以启用清除。
    
      - 在“QoE 最长保留期限(天)”中，选择应保留 QoE 记录的最长天数。

7.  单击“提交”。

## 使用 Windows PowerShell cmdlet 创建 QoE 配置设置

还可使用 Windows PowerShell 和 New-CsQoEConfiguration cmdlet 创建 QoE 配置设置。您可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 创建新的 QoE 配置设置的集合

  - 以下命令将创建新的应用于 Redmond 站点的 QoE 配置设置的集合：
    
        New-CsQoEConfiguration -Identity "site:Redmond"

## 创建其中禁用 QoE 监视的 QoE 配置设置的新集合

  - 由于前面的命令中未指定参数（必需的 Identity 参数之外），因此新的配置设置集合将对其所有属性使用默认值。若要创建使用不同属性值的设置，只需包含相应的参数和参数值。例如，若要创建用户体验质量配置设置的集合，默认情况下，允许禁用 QoE 记录使用与以下命令类似的命令：
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

## 创建新的 QoE 配置设置集合时指定多个属性值

  - 您可通过包含多个参数指定多个属性值。例如，此命令会将新设置配置为保留 QoE 数据 30 天并于上午 3:00 清除旧数据：
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

有关详细信息，请参阅 [New-CsQoEConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsQoEConfiguration) cmdlet 的帮助主题。

