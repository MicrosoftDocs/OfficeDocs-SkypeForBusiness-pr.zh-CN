---
title: Lync Server 2013：配置电话拨入式会议策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure conferencing policy for dial-in
ms:assetid: 9bf926d6-0248-4352-98c3-9c5a333debbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398810(v=OCS.15)
ms:contentKeyID: 48184979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 107c5fcf4b341c652cd4044fe47f4b650cf5adb4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739342"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a>在 Lync Server 2013 中配置电话拨入式会议策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-03-21_

会议策略是一种用户帐户设置，用于指定参与者的会议体验。您可以创建具有站点作用域或用户作用域的会议策略。会议策略设置包含会议安排和参与会议的多个方面。一些会议策略设置支持参与者参加电话拨入式会议。当您配置电话拨入式会议时，应该确认已针对组织正确设置了这些字段，并根据需要进行修改。

验证会议策略中的以下字段：

  - **允许参与者邀请匿名用户**   此设置允许会议组织者向会议邀请匿名（即未经身份验证的）参与者。 此设置是电话拨入式会议的可选设置。 默认情况下，此设置在默认全局会议策略中处于选中状态。

  - **启用 PSTN 电话拨入式会议**   此设置允许用户通过从 PSTN 拨入来加入会议的音频部分。 电话拨入式会议需要此设置。 默认情况下，此设置在默认全局会议策略中处于选中状态。

  - **允许匿名参与者拨出**   此设置允许已加入会议的匿名用户拨出到电话号码以加入会议的音频部分。 此设置是电话拨入式会议的可选设置。 默认情况下，不会在默认全局会议策略中选中此设置。

  - **允许未启用企业语音的参与者拨出**   此设置允许未启用企业语音的会议参与者和组织者拨出到电话号码以加入会议的音频部分。 拨出呼叫是根据组织者分配的语音策略获得授权的。 默认情况下，不会在默认全局会议策略中选中此设置。 "设置默认值" 为 "禁用"。
    
    <div>
    

    > [!NOTE]  
    > 若要启用此功能，没有为企业语音启用的会议组织者应为其分配适当的语音策略，以授权由该用户组织的会议拨出任何电话。 可将语音政策分配给未通过 Lync Server 命令行管理器启用企业语音的用户。 如果用户没有明确分配给他的语音策略，则网站语音策略将用于授权拨出请求。 如果没有网站语音策略，将使用全局语音策略。&nbsp;

    
    </div>

本节中的过程介绍了如何修改会议策略。 有关如何配置在默认会议策略中定义参与者体验的所有设置的详细信息，请参阅[在 Lync Server 2013 中创建或修改会议配置设置的集合](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md)。 有关如何为特定用户或用户组创建会议策略的详细信息，请参阅[在 Lync Server 2013 中创建或修改会议策略](lync-server-2013-create-or-modify-a-conferencing-policy.md)。 有关所有可用会议策略设置的列表，请参阅[Lync Server 2013 的会议策略设置参考](lync-server-2013-conferencing-policy-settings-reference.md)。

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a>修改电话拨入式会议策略

1.  以 RTCUniversalServerAdmins 组成员的身份登录计算机，或者作为**Cs-ServerAdministrator**或**CsAdministrator**角色的成员登录到计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“**会议**”。

4.  在 "**会议策略**" 选项卡上，双击会议策略名称以打开 "**编辑会议策略**" 对话框。

5.  验证电话拨入式会议的字段是否适用于你的组织，并根据需要修改设置。

6.  单击“**提交**”。

</div>

</div>

<span> </span>

</div>

</div>

</div>

