---
title: 分配每用户语音策略
TOCTitle: 分配每用户语音策略
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49888536
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 分配每用户语音策略

 

_**上一次修改主题：** 2013-02-22_

全局和站点级别语音策略将自动分配给所有启用企业语音的 Lync Server 2013 用户帐户。您还可以使用 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序向特定用户分配语音策略。使用本主题中的过程将每用户策略显式分配给 Lync Server 用户。

## 使用 Lync Server 控制面板分配用户特定的语音策略

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“用户”，然后搜索要配置的用户帐户。

4.  在列出搜索结果的表中，单击相应的用户帐户，再单击“编辑”，然后单击“显示详细信息”。

5.  在“编辑 Lync Server 用户”中的“语音策略”下，选择要应用的用户策略。
    
    > [!NOTE]  
    > “&lt;自动&gt;”设置将应用默认服务器或全局策略设置。
    


## 使用 Lync Server 命令行管理程序分配用户特定的语音策略

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  要将现有用户语音策略分配给用户，请在命令提示符处运行：
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    例如：
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    在此示例中，向显示名称为 何石 的用户分配了名为 **VoicePolicyJapan** 的语音策略。

有关分配特定于用户的语音策略或有关运行 **Grant-CsVoicePolicy** cmdlet 的详细信息，请参阅 [Lync Server 命令行管理程序](lync-server-2013-lync-server-management-shell.md)文档。

## 使用 Windows PowerShell cmdlet 分配每用户语音策略

还可以使用 Windows PowerShell 和 **Grant-CsVoicePolicy** cmdlet 分配每用户语音策略。此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 向单个用户分配每用户语音策略

  - 以下命令向用户 Ken Myer 分配每用户语音策略 RedmondVoicePolicy。
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## 向多个用户分配每用户语音策略

  - 此命令向在 Active Directory 的 Finance OU 中拥有帐户的所有用户分配每用户语音策略 FinanceVoicePolicy。有关此命令中使用的 OU 参数的详细信息，请参阅 [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) cmdlet 的文档。
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## 取消分配每用户语音策略

  - 以下命令取消分配之前为 Ken Myer 分配的任何每用户语音策略。在取消分配每用户策略后，将自动使用全局策略或本地站点策略（如果有）管理 Ken Myer。站点策略优先于全局策略。
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

有关详细信息，请参阅 [Grant-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsVoicePolicy) cmdlet 的帮助主题。

## 另请参阅

#### 任务

[禁用用于企业语音的用户](lync-server-2013-disable-a-user-for-enterprise-voice.md)  

#### 其他资源

[Lync Server 命令行管理程序](lync-server-2013-lync-server-management-shell.md)

