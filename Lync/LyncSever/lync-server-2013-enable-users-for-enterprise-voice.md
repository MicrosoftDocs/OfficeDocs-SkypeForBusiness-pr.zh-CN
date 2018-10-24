---
title: Lync Server 2013：为用户启用企业语音
TOCTitle: 为用户启用企业语音
ms:assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413011(v=OCS.15)
ms:contentKeyID: 49314707
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中为用户启用企业语音

 

_**上一次修改主题：** 2012-11-01_

为一个或多个中介服务器安装文件，配置出站呼叫路由，并选择性地部署一个或多个高级 企业语音功能之后，可以使用以下过程让用户可以使用 企业语音发出呼叫：

> [!NOTE]  
> 在以下过程中，只有第一个过程可以使用 Lync Server 控制面板执行。对于其余过程，只能使用 Lync Server 命令行管理程序。



  - 为用户帐户启用 企业语音。

  - （可选）为用户帐户分配特定于用户的语音策略。

  - （可选）为用户帐户分配特定于用户的拨号计划。

## 为用户帐户启用 企业语音

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左导航栏中，单击“用户”。

4.  在“搜索用户”框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”。

5.  在表中，单击要启用 企业语音的用户帐户。

6.  在“编辑”菜单上，单击“显示详细信息”。

7.  在“编辑 Lync Server 用户”页的“电话”下，单击“企业语音”。

8.  单击“线路 URI”，然后键入唯一的规范化电话号码（例如，tel:+14255550200）。

9.  单击“提交”。

要完成为用户启用 企业语音的过程，请确保为该用户分配全局（默认分配）或特定于用户的语音策略和拨号计划。

默认情况下，会为所有用户分配一个全局语音策略和一个拨号计划。如果语音策略或拨号计划的站点级别与承载用户帐户的站点相同，则这些站点策略将自动应用于用户。要对用户应用每用户语音策略或拨号计划，您必须运行 **Grant-CsVoicePolicy** 和 **Grant-CsDialPlan** cmdlet。有关详细信息，请参阅 [Lync Server 命令行管理程序](lync-server-2013-lync-server-management-shell.md)文档。

## 语音策略分配

全局和站点级别语音策略将自动分配给所有启用 企业语音的用户帐户。还可以创建适用于特定的用户或组的语音策略。必须将这些每用户策略显式分配给用户或组。如果要对所有启用 企业语音的用户使用全局或站点语音策略，可以跳过这一节，并继续本主题后面的 拨号计划分配 一节。

## 分配特定于用户的语音策略

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  要将现有用户语音策略分配给用户，请在命令提示符处运行：
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    例如：
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    在此示例中，为显示名称为 何石 的用户分配了名称为 **VoicePolicyJapan** 的语音策略。

有关分配特定于用户的语音策略或有关运行 **Grant-CsVoicePolicy** cmdlet 的详细信息，请参阅 [Lync Server 命令行管理程序](lync-server-2013-lync-server-management-shell.md)文档。

## 拨号计划分配

要完成 企业语音用户或电话拨入式会议用户的用户帐户配置，必须为用户分配拨号计划。如果没有显式分配现有每用户拨号计划，则用户帐户将自动使用全局拨号计划或站点级别拨号计划（如果存在）。如果要为所有启用 企业语音的用户使用全局或站点拨号计划，可以跳过这一节。

## 分配拨号计划

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  要分配特定于用户的拨号计划，请在命令提示符处运行：
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    例如：
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    在此示例中，为显示名称为 何石 的用户分配了名为 **DialPlanJapan** 的用户拨号计划。

有关分配用户拨号计划或运行 **Grant-CsDialPlan** cmdlet 的详细信息，请参阅 [Lync Server 命令行管理程序](lync-server-2013-lync-server-management-shell.md)文档。

## 另请参阅

#### 任务

[禁用用于企业语音的用户](lync-server-2013-disable-a-user-for-enterprise-voice.md)

