---
title: 确认配置设置
TOCTitle: 确认配置设置
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204848(v=OCS.15)
ms:contentKeyID: 49312651
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 确认配置设置

 

_**上一次修改主题：** 2015-03-09_

合并拓扑并运行 **Import-CsLegacyConfiguration** cmdlet 后，应确认 Office Communications Server 2007 R2 策略和设置已导入 Lync Server 2013。下表列出了应确认的策略和设置。

## 迁移后要确认的策略和设置


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>如果使用该工作负荷：</th>
<th>确认这些策略和设置：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>即时消息 (IM) 和会议</p></td>
<td><p>状态策略</p>
<p>会议策略</p></td>
</tr>
<tr class="even">
<td><p>电话拨入式会议</p></td>
<td><p>拨入访问号码</p>
<p>拨号计划</p></td>
</tr>
<tr class="odd">
<td><p>企业语音</p></td>
<td><p>语音策略</p>
<p>语音路由</p>
<p>拨号计划</p>
<p>PSTN 用法设置</p></td>
</tr>
<tr class="even">
<td><p>Communicator Web Access</p></td>
<td><p>简单 URL</p></td>
</tr>
<tr class="odd">
<td><p>外部用户</p></td>
<td><p>外部访问策略</p></td>
</tr>
<tr class="even">
<td><p>存档</p></td>
<td><p>存档策略</p></td>
</tr>
</tbody>
</table>


## 确认策略和设置

1.  在 Office Communications Server 2007 R2 环境中，记下拨号计划（以前称为位置配置文件）、拨入访问号码（会议助理访问号码和区域）、语音路由和上表中列出的策略的名称，另外还要记下 Communicator Web Access 使用的 URL。

2.  在 Lync Server 2013 前端服务器中，打开 Lync Server 控制面板。

3.  若要确认导入的会议策略，请在左窗格中，依次单击“会议”和“会议策略”，然后确认 Office Communications Server 2007 R2 环境中的所有会议策略都包含在列表中。
    
    > [!NOTE]
    > Office Communications Server 早期版本中的“会议”(Meeting) 策略现在在 Lync Server 2013 中称为会议 (Conferencing) 策略。此外，Office Communications Server 早期版本中的“匿名参与者”设置现在是 Lync Server 2013 会议策略中的一项设置。
    
    > [!NOTE]
    > 在 Office Communications Server 2007 R2 中，如果会议策略未设置为“对每个用户使用”，则只导入全局策略设置。这种情况下不会导入其他会议策略。
    
    > [!NOTE]
    > 如果 Office Communications Server 2007 R2 会议策略中的“匿名参与者”设置为“对于每个用户强制执行”，则会在迁移期间创建两个会议策略：一个将“AllowAnonymousParticipantsInMeetings”设置为“True”，一个将“AllowAnonymousParticipantsInMeetings”设置为“False”。


4.  若要确认导入的拨号计划，请依次单击“语音路由”和“拨号计划”，然后确认 Office Communicator 2007 R2 环境中的所有拨号计划都包含在列表中。
    
    > [!NOTE]
    > 在 Lync Server 2013 中，“位置配置文件”现在称为“拨号计划”。


5.  若要确认导入的语音策略，请依次单击“语音路由”和“语音策略”，然后确认 Office Communicator 2007 R2 环境中的所有语音策略都包含在列表中。
    
    > [!NOTE]
    > 在 Office Communications Server 2007 R2 环境中，如果语音策略未设置为“对每个用户使用”，则只导入全局策略设置。这种情况下不会导入其他语音策略。


6.  若要确认导入的语音路由，请依次单击“语音路由”和“路由”，然后确认 Office Communicator 2007 R2 环境中的所有语音路由都包含在列表中。

7.  若要确认导入的 PSTN 用法设置，请依次单击“语音路由”和“PSTN 用法”，然后确认 Office Communicator 2007 R2 环境中的 PSTN 用法设置包含在列表中。

8.  若要确认导入的外部访问策略，请依次单击“联盟和外部访问”和“外部访问策略”，然后确认 Office Communicator 2007 R2 环境中的所有外部访问策略都包含在列表中。

9.  若要确认存档策略，请依次单击“监控和存档”和“存档策略”，然后确认 Office Communications Server 2007 R2 环境中的所有存档策略都包含在列表中。

10. 打开 Lync Server 命令行管理程序。

11. 若要验证状态策略，请在命令行中键入：
    
        Get-CsPresencePolicy
    
    通过查看 **Identity** 参数中的名称，确认 Office Communications Server 2007 R2 环境中的所有状态策略均已导入。

## 使用 cmdlet 确认策略和设置

1.  打开 Lync Server 命令行管理程序。

2.  运行下表中的 cmdlet 以确认策略和设置。
    
    这些 cmdlet 的语法如以下示例所示：
    
        Get-CsConferencingPolicy
    
    有关这些 cmdlet 的详细信息，请运行：
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>对于该策略或设置：</th>
<th>使用该 cmdlet：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>状态策略</p></td>
<td><p><strong>Get-CsPresencePolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>会议策略</p></td>
<td><p><strong>Get-CsConferencingPolicy</strong></p></td>
</tr>
<tr class="odd">
<td><p>拨入访问号码</p></td>
<td><p><strong>Get-CsDialInConferencingAccessNumber</strong></p></td>
</tr>
<tr class="even">
<td><p>拨号计划</p></td>
<td><p><strong>Get-CsDialPlan</strong></p></td>
</tr>
<tr class="odd">
<td><p>语音策略</p></td>
<td><p><strong>Get-CsVoicePolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>语音路由</p></td>
<td><p><strong>Get-CsVoiceRoute</strong></p></td>
</tr>
<tr class="odd">
<td><p>PSTN 用法</p></td>
<td><p><strong>Get-CsPstnUsage</strong></p></td>
</tr>
<tr class="even">
<td><p>URL</p></td>
<td><p><strong>Get-CsSimpleUrlConfiguration</strong></p></td>
</tr>
<tr class="odd">
<td><p>外部访问策略</p></td>
<td><p><strong>Get-CsExternalAccessPolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>存档策略</p></td>
<td><p><strong>Get-CsArchivingPolicy</strong></p></td>
</tr>
</tbody>
</table>

