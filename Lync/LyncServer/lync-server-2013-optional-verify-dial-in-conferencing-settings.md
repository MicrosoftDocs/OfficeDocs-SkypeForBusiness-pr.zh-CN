---
title: Lync Server 2013：（可选）验证电话拨入式会议设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify dial-in conferencing settings
ms:assetid: a85efdda-97b0-4f3b-bd26-04416bee8ef5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412789(v=OCS.15)
ms:contentKeyID: 48185027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ae67001d7e041cf0b4e8f6a01fb9278f3d79300
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-verify-dial-in-conferencing-settings-in-lync-server-2013"></a>Optional在 Lync Server 2013 中验证电话拨入式会议设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2010-11-02_

作为对电话拨入式会议配置的最终验证，可以搜索电话拨入式会议区域未被任何访问号码和未指定电话拨入式会议区域的访问号码使用的拨号计划。 此为可选步骤。

<div>

## <a name="to-find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>使用未被访问号码使用的电话拨入式会议区域查找拨号计划

1.  以 RTCUniversalServerAdmins 组成员或者 **Cs-ServerAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  在命令提示符下，运行以下内容：
    
        Get-CsDialinConferencingAccessNumber -EmptyRegion
    
    此 cmdlet 返回具有未被访问号码使用的电话拨入式会议区域的所有拨号计划。

</div>

<div>

## <a name="to-find-access-numbers-without-assigned-regions"></a>查找未分配区域的访问号码

1.  以 RTCUniversalServerAdmins 组成员或者 **Cs-ServerAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  在命令提示符下，运行以下内容：
    
        Get-CsDialinConferencingAccessNumber -Region NULL
    
    此 cmdlet 返回未与区域关联的所有电话拨入式会议访问号码。

</div>

</div>

<span> </span>

</div>

</div>

</div>

