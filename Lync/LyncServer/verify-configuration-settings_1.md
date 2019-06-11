---
title: 验证配置设置
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a20b78ac9275657461beb74a7325c0c46e4e40fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a>验证配置设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-28_

合并拓扑并运行**CsLegacyConfiguration** cmdlet 后, 请验证你的 Office 通信服务器 2007 R2 策略和设置是否已导入到 Lync Server 2013。 下表列出了应验证的策略和设置。

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a>迁移后要验证的策略和设置


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>如果使用此工作负荷:</th>
<th>验证这些策略和设置:</th>
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
<p>PSTN 使用设置</p></td>
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

## <a name="to-verify-policies-and-settings"></a>验证策略和设置

1.  在 Office 通信服务器 2007 R2 环境中, 记下拨号计划 (以前称为 "位置配置文件") 的名称、拨入访问号码 ("会议助理" 访问电话号码和区域)、语音路由和 "说明" 中列出的策略。上表, 以及用于 Communicator Web Access 的 Url。

2.  在 Lync Server 2013 前端服务器上, 打开 "Lync Server 控制面板"。

3.  若要验证导入的会议策略, 请在左窗格中单击 "**会议**", 单击 "**会议策略**", 然后验证列表中是否包含 Office 通信服务器 2007 R2 环境中的所有会议策略。
    
    <div>
    

    > [!NOTE]  
    > 以前版本的 Office 通信服务器的<STRONG>会议</STRONG>策略现在称为 Lync Server 2013 中的会议策略。 此外, 以前版本的 Office 通信服务器的<STRONG>匿名 Particpants</STRONG>设置现在是 Lync Server 2013 会议策略中的一个设置。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 在 Office 通信服务器 2007 R2 中, 如果会议策略未设置为 "<STRONG>每用户使用</STRONG>", 则仅导入全局策略设置。 在这种情况下, 不会导入任何其他会议策略。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 如果在您的 Office 通信服务器2007中将<STRONG>匿名参与者</STRONG>设置为<STRONG>按用户强制实施</STRONG>, 则迁移期间将创建两个会议策略: 一个具有<STRONG>AllowAnonymousParticipantsInMeetings</STRONG>设置为<STRONG>True</STRONG> , 其中一个<STRONG>AllowAnonymousParticipantsInMeetings</STRONG>设置为<STRONG>False</STRONG>。

    
    </div>

4.  若要验证导入的拨号计划, 请单击 "**语音路由**", 单击 "**拨号计划**", 然后验证列表中是否包含 Office Communicator 2007 R2 环境中的所有拨号计划。
    
    <div>
    

    > [!NOTE]  
    > 在 Lync Server 2013 中,<STRONG>位置配置文件</STRONG>现在称为 "<STRONG>拨号计划</STRONG>"。

    
    </div>

5.  若要验证导入的语音策略, 请单击 "**语音路由**", 单击 "**语音策略**", 然后验证列表中是否包含 Office Communicator 2007 R2 环境中的所有语音策略。
    
    <div>
    

    > [!NOTE]  
    > 如果在您的 Office 通信服务器 2007 R2 环境中未将语音策略设置为 "<STRONG>每用户使用</STRONG>", 则只导入全局策略设置。 在这种情况下, 不会导入任何其他语音策略。

    
    </div>

6.  若要验证导入的语音路由, 请单击 "**语音路由**", 单击 "**路由**", 然后验证列表中是否包含 Office Communicator 2007 R2 环境中的所有语音路由。

7.  若要验证导入的 PSTN 使用设置, 请单击 "**语音路由**", 单击 " **PSTN 使用**", 然后验证列表中是否包含 Office Communicator 2007 R2 环境中的 PSTN 使用设置。

8.  若要验证导入的外部访问策略, 请单击 "**联盟和外部访问**", 单击 "**外部访问策略**", 然后验证列表中是否包含 Office Communicator 2007 R2 环境中的所有外部访问策略。

9.  若要验证存档策略, 请单击 "**监视和存档**", 单击 "**存档策略**", 然后验证你的 Office 通信服务器 2007 R2 环境中的所有存档策略是否都包含在列表中。

10. 打开 Lync Server 命令行管理程序。

11. 若要验证状态策略, 请在命令行中键入以下内容:
    
        Get-CsPresencePolicy
    
    通过在**Identity**参数中查看名称, 验证是否已导入 Office 通信服务器 2007 R2 环境中的所有状态策略。

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a>使用 cmdlet 验证策略和设置

1.  打开 Lync Server 命令行管理程序。

2.  运行下表中的 cmdlet 以验证策略和设置。
    
    这些 cmdlet 的语法类似于以下示例:
    
        Get-CsConferencingPolicy
    
    有关这些 cmdlet 的详细信息, 请运行:
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>对于此策略或设置:</th>
<th>使用此 cmdlet:</th>
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
<td><p><strong>CsVoicePolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>语音路由</p></td>
<td><p><strong>CsVoiceRoute</strong></p></td>
</tr>
<tr class="odd">
<td><p>PSTN 用法</p></td>
<td><p><strong>Get-CsPstnUsage</strong></p></td>
</tr>
<tr class="even">
<td><p>URL</p></td>
<td><p><strong>CsSimpleUrlConfiguration</strong></p></td>
</tr>
<tr class="odd">
<td><p>外部访问策略</p></td>
<td><p><strong>CsExternalAccessPolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>存档策略</p></td>
<td><p><strong>Get-CsArchivingPolicy</strong></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

