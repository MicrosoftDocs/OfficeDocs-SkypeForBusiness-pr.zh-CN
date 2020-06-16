---
title: 验证配置设置
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2430fe82aa424571405def33139ba315677ffcc7
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a>验证配置设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-28_

在合并拓扑并运行**CsLegacyConfiguration** cmdlet 之后，请验证是否已将 Office 通信服务器 2007 R2 策略和设置导入到 Lync Server 2013。 下表列出了应确认的策略和设置。

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a>迁移后要确认的策略和设置


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


</div>

<div>

## <a name="to-verify-policies-and-settings"></a>确认策略和设置

1.  在 Office 通信服务器 2007 R2 环境中，除了用于 Communicator Web Access 的 Url 之外，请记下拨号计划的名称（以前称为位置配置文件）、电话拨入访问号码（会议助理访问电话号码和区域）、语音路由以及上表中列出的策略。

2.  在 Lync Server 2013 前端服务器上，打开 "Lync Server 控制面板"。

3.  若要验证导入的会议策略，请在左窗格中，单击 "**会议**"，单击 "**会议策略**"，然后验证 Office 通信服务器 2007 R2 环境中的所有会议策略是否都包含在列表中。
    
    <div>
    

    > [!NOTE]  
    > 以前版本的 Office 通信服务器的<STRONG>会议</STRONG>策略现在称为 Lync Server 2013 中的会议策略。 此外，以前版本的 Office 通信服务器的<STRONG>匿名 Particpants</STRONG>设置现在是 Lync Server 2013 会议策略中的设置。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 在 Office 通信服务器 2007 R2 中，如果未将会议策略设置为 "<STRONG>每用户使用</STRONG>"，则只导入全局策略设置。 这种情况下不会导入其他会议策略。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 如果在 Office 通信服务器 2007 R2 会议策略中将<STRONG>匿名参与者</STRONG>设置为<STRONG>按用户强制实施</STRONG>，则迁移过程中将创建两个会议策略：一个将<STRONG>AllowAnonymousParticipantsInMeetings</STRONG>设置为<STRONG>True</STRONG> ，另一个设置为<STRONG>AllowAnonymousParticipantsInMeetings</STRONG>设置为<STRONG>False</STRONG>。

    
    </div>

4.  若要确认导入的拨号计划，请依次单击“语音路由”**** 和“拨号计划”****，然后确认 Office Communicator 2007 R2 环境中的所有拨号计划都包含在列表中。
    
    <div>
    

    > [!NOTE]  
    > 在 Lync Server 2013 中，<STRONG>位置配置文件</STRONG>现在称为 "<STRONG>拨号计划</STRONG>"。

    
    </div>

5.  若要确认导入的语音策略，请依次单击“语音路由”**** 和“语音策略”****，然后确认 Office Communicator 2007 R2 环境中的所有语音策略都包含在列表中。
    
    <div>
    

    > [!NOTE]  
    > 如果您的 Office 通信服务器 2007 R2 环境中的 "语音策略" 未设置为 "在<STRONG>每个用户使用</STRONG>"，则只导入全局策略设置。 这种情况下不会导入其他语音策略。

    
    </div>

6.  若要确认导入的语音路由，请依次单击“语音路由”**** 和“路由”****，然后确认 Office Communicator 2007 R2 环境中的所有语音路由都包含在列表中。

7.  若要确认导入的 PSTN 用法设置，请依次单击“语音路由”**** 和“PSTN 用法”****，然后确认 Office Communicator 2007 R2 环境中的 PSTN 用法设置包含在列表中。

8.  若要确认导入的外部访问策略，请依次单击“联盟和外部访问”**** 和“外部访问策略”****，然后确认 Office Communicator 2007 R2 环境中的所有外部访问策略都包含在列表中。

9.  若要验证存档策略，请单击 "**监视和存档**"，再单击 "**存档策略**"，然后验证 Office 通信服务器 2007 R2 环境中的所有存档策略是否都包含在列表中。

10. 打开 Lync Server 命令行管理程序。

11. 若要验证状态策略，请在命令行中键入：
    
        Get-CsPresencePolicy
    
    通过查看**Identity**参数中的名称，验证是否已导入 Office 通信服务器 2007 R2 环境中的所有状态策略。

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a>使用 cmdlet 确认策略和设置

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
<td><p><strong>CsPresencePolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>会议策略</p></td>
<td><p><strong>Set-csconferencingpolicy</strong></p></td>
</tr>
<tr class="odd">
<td><p>拨入访问号码</p></td>
<td><p><strong>Set-csdialinconferencingaccessnumber</strong></p></td>
</tr>
<tr class="even">
<td><p>拨号计划</p></td>
<td><p><strong>Grant-csdialplan</strong></p></td>
</tr>
<tr class="odd">
<td><p>语音策略</p></td>
<td><p><strong>Set-csvoicepolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>语音路由</p></td>
<td><p><strong>CsVoiceRoute</strong></p></td>
</tr>
<tr class="odd">
<td><p>PSTN 用法</p></td>
<td><p><strong>CsPstnUsage</strong></p></td>
</tr>
<tr class="even">
<td><p>URL</p></td>
<td><p><strong>CsSimpleUrlConfiguration</strong></p></td>
</tr>
<tr class="odd">
<td><p>外部访问策略</p></td>
<td><p><strong>Set-csexternalaccesspolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>存档策略</p></td>
<td><p><strong>New-csarchivingpolicy</strong></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

