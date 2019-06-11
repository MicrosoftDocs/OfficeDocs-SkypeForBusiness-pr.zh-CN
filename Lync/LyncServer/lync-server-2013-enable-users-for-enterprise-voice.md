---
title: 'Lync Server 2013: 为企业语音启用用户'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable users for Enterprise Voice
ms:assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413011(v=OCS.15)
ms:contentKeyID: 48185800
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d94b2ad348bc1d086716deed2beef0dcfbe78e2b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a>在 Lync Server 2013 中启用企业语音用户

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

为一个或多个中介服务器安装文件后, 配置出站呼叫路由, 并有选择地部署一个或多个高级企业语音功能, 您可以使用以下过程使用户能够使用企业语音进行呼叫:

<div>


> [!NOTE]  
> 在以下过程中, 仅可以使用 Lync Server 控制面板执行第一个过程。 对于剩余的过程, 您只能使用 Lync Server 命令行管理程序。



</div>

  - 启用企业语音的用户帐户。

  - （可选）为用户帐户分配特定于用户的语音策略。

  - （可选）为用户帐户分配特定于用户的拨号计划。

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a>启用企业语音的用户帐户

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左导航栏中，单击“用户”****。

4.  在“搜索用户”**** 框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”****。

5.  在表中, 单击要为企业语音启用的用户帐户。

6.  在“编辑”**** 菜单上，单击“显示详细信息”****。

7.  在 "**编辑 Lync Server 用户**" 页面上的 "**电话服务**" 下, 单击 "**企业语音**"。

8.  单击“线路 URI”****，然后键入唯一的规范化电话号码（例如，tel:+14255550200）。

9.  单击“**提交**”。

若要为用户启用企业语音, 请确保向用户分配一个语音策略和一个拨号计划, 无论是全局的 (默认情况下分配的) 还是特定于用户。

默认情况下，会为所有用户分配一个全局语音策略和一个拨号计划。 如果语音策略或拨号计划的站点级别与承载用户帐户的站点相同，则这些站点策略将自动应用于用户。 要对用户应用每用户语音策略或拨号计划，您必须运行 **Grant-CsVoicePolicy** 和 **Grant-CsDialPlan** cmdlet。 有关详细信息, 请参阅[Lync Server 2013 管理外壳](lync-server-2013-lync-server-management-shell.md)文档。

</div>

<div>

## <a name="voice-policy-assignment"></a>语音策略分配

全局策略和网站级语音策略将自动分配给所有已启用企业语音的用户帐户。 还可以创建适用于特定的用户或组的语音策略。 必须将这些每用户策略显式分配给用户或组。 如果要对已启用企业语音的所有用户使用全局或网站语音策略, 可以跳过此部分, 然后继续本主题后面部分的 "拨入计划作业" 部分。

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a>分配特定于用户的语音策略

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

3.  要将现有用户语音策略分配给用户，请在命令提示符处运行以下命令：
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    例如：
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    在此示例中, 具有显示名称 Bob 凯利的用户被分配了名称为 " **VoicePolicyJapan**" 的语音策略。

有关分配特定于用户的语音策略或运行**CsVoicePolicy** cmdlet 的详细信息, 请参阅[Lync Server 2013 管理外壳](lync-server-2013-lync-server-management-shell.md)文档。

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a>拨号计划分配

若要为企业语音的用户和电话拨入式会议的用户完成用户帐户配置, 必须为用户分配一个拨号计划。 如果没有显式分配现有每用户拨号计划，则用户帐户将自动使用全局拨号计划或站点级别拨号计划（如果存在）。 如果要对启用了企业语音的所有用户使用全局或网站拨号计划, 可以跳过此部分。

<div>

## <a name="to-assign-a-dial-plan"></a>分配拨号计划

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

3.  要分配特定于用户的拨号计划，请在命令提示符处运行：
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    例如：
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    在此示例中, 使用显示名称 Bob 凯利的用户被分配了名称为 " **DialPlanJapan**" 的用户拨号计划。

有关分配用户拨号计划或运行**CsDialPlan** cmdlet 的详细信息, 请参阅[Lync Server 2013 管理外壳](lync-server-2013-lync-server-management-shell.md)文档。

</div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中禁用企业语音用户](lync-server-2013-disable-a-user-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

