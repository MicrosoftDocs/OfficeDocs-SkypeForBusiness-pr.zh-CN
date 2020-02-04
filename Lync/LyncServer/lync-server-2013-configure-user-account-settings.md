---
title: Lync Server 2013：配置用户帐户设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure user account settings
ms:assetid: b7c74ecc-b924-4efc-8a56-3a5f94a9ef13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412896(v=OCS.15)
ms:contentKeyID: 48185200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b74056587a192ec81f0dffb0044fb76e7698960
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733802"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-user-account-settings-in-lync-server-2013"></a>在 Lync Server 2013 中配置用户帐户设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-05_

拨入用户输入其电话号码或分机号和 PIN，即可以经过身份验证的用户身份加入会议。 需要在 Lync Server 用户帐户上指定的电话**线路 URI**才能进行身份验证。

本主题中的过程介绍如何为单个用户帐户分配“**线路 URI**”。 如果需要为多个用户帐户分配“**线路 URI**”，则可以创建使用 **Set-CsUser** cmdlet 的脚本。 有关使用示例脚本为多个用户帐户分配**行 URI**的详细信息，请参阅 "为多个用户分配行 uri [http://go.microsoft.com/fwlink/p/?linkId=196945](http://go.microsoft.com/fwlink/p/?linkid=196945)"。

<div>

## <a name="to-configure-user-account-settings"></a>配置用户帐户设置

1.  以 RTCUniversalServerAdmins 组成员或者 **Cs-UserAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左导航栏中，单击“用户”****。

4.  在搜索字段中，键入要为其配置电话拨入式会议的用户的名称，或单击“**添加筛选器**”以指定搜索字段，然后单击“**查找**”。

5.  双击该用户名以打开 "**编辑 Lync Server 用户**" 对话框。

6.  在“**电话**”下的“**线路 URI**”字段中，键入唯一的规范化电话号码（例如，tel:+14255550200）。
    
    <div>
    

    > [!NOTE]  
    > 仅当将“<STRONG>电话</STRONG>”设置为“<STRONG>仅限 PC 到 PC</STRONG>”、“<STRONG>企业语音</STRONG>”、“<STRONG>远程呼叫控制</STRONG>”或“<STRONG>仅远程呼叫控制</STRONG>”时，才可以指定“<STRONG>线路 URI</STRONG>”。

    
    </div>

7.  单击“**提交**”。

</div>

</div>

<span> </span>

</div>

</div>

</div>

