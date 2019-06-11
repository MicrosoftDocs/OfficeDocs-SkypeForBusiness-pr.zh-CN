---
title: 'Lync Server 2013: 为用户配置电话服务'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure telephony for a user
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520988(v=OCS.15)
ms:contentKeyID: 48183987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97f4fc79b871a962fe498d6dbd908b75f6b2fecd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a>在 Lync Server 2013 中为用户配置电话服务

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

电话设置是用户帐户的一些个人设置, 可在 Lync Server 控制面板 for 用户 (即, 如果个人用户已启用 Lync Server 2013 且组织支持电话服务) 中进行配置。

Lync Server 用户电话选项包括以下内容:

  - **音频/视频已禁用**   用户无法使用音频和视频进行呼叫。

  - **仅限**   pc 至 pc 用户只能进行 pc 到 pc 的音频或视频通话。

  - **企业语音**   用户可以使用 Lync Server 2013 基础结构路由所有传入和传出呼叫。 用户还可以进行 PC 到 PC 呼叫。

  - **远程呼叫控制**   用户可以使用 Lync Server 2013 控制桌面电话, 也可以进行 pc 到 pc 呼叫。

有关为组织配置电话的详细信息, 请参阅在部署文档中[为 Lync server 2013 中的用户配置电话](lync-server-2013-configure-telephony-for-a-user.md)和[在 lync Server 2013 中部署企业语音](lync-server-2013-deploying-enterprise-voice.md)。

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a>为特定用户帐户配置电话服务

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左导航栏中，单击“用户”****。

4.  在 "**搜索用户**" 框中, 键入所需用户帐户的所有或第一部分的显示名称、"名字"、"姓氏"、安全帐户管理器 (SAM) 帐户名、SIP 地址或行统一资源标识符 (URI), 然后单击 "**查找"**.

5.  在表中, 单击要修改的用户帐户。

6.  在 "**编辑**" 菜单上, 单击 "**修改**"。

7.  在**电话服务**中, 执行以下操作:
    
      - 若要为用户禁用音频和视频呼叫, 请单击 "**音频/视频已禁用**"。
    
      - 若要为用户启用 PC 至 PC 音频通信, 但不支持远程呼叫控制或企业语音, 请单击 "**仅 pc 到 pc**"。 为用户用于 PC 到 PC 音频通信的电话指定**行 URI**的值。
    
      - 若要根据服务策略类别 (包括 PC 到 PC 音频通信) 使用 Lync Server 2010 基础结构路由用户的电话呼叫, 请单击 "**企业语音**"。 在 "**行 URI**" 中, 指定企业语音的电话号码。 在 "**拨号计划策略**" 和 "**语音策略**" 中, 为用户指定适当的策略。 若要指定将用户拨打的电话号码转换为电子164格式的规范化规则, 请在 "**位置策略**" 中选择相应的位置配置文件。
    
      - 若要启用 "远程呼叫控制", 使用户能够从 Lync Server 2013 控制其桌面电话线路, 以进行 PC 到 PC 呼叫和 PC 至电话呼叫, 请单击 "**远程呼叫控制**"。 在 "**行 URI**" 中, 指定远程呼叫控制的电话号码。 用户必须具有桌面电话和专用分支 exchange (PBX) 连接才能使用呼叫路由。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中修改用户帐户属性](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

