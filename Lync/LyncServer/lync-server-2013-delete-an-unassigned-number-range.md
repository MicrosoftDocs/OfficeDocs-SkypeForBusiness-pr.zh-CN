---
title: Lync Server 2013：删除未分配的号码范围
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an unassigned number range
ms:assetid: a8141bfb-b94d-4d0f-a7a9-2e60d10b103a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182565(v=OCS.15)
ms:contentKeyID: 48185090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 452eea98fee3dc70fa88d637893c0136c7edf8d6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-unassigned-number-range-in-lync-server-2013"></a>在 Lync Server 2013 中删除未分配号码范围

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

使用以下其中一个过程删除通知的未分配号码范围。

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-unassigned-number-range"></a>使用 Lync Server 控制面板删除未分配的号码范围

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“语音功能”****，然后单击“未分配号码”****。

4.  在“未分配号码”**** 页上的搜索字段中，键入要删除的未分配号码范围的全部或部分名称。

5.  在号码范围的结果列表中，单击名称，再单击“编辑”****，然后单击“删除”****。

6.  单击“全部提交”****。

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-unassigned-number-range"></a>使用 Windows PowerShell 删除未分配的号码范围

1.  登录到安装了 Lync Server 命令行管理程序的计算机，作为 RTCUniversalServerAdmins 组的成员或具有必要的用户权限（如在[Lync Server 2013 中委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述）。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  在命令行中键入：
    
        Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
    
    例如：
    
        Remove-CsUnassignedNumber -Identity "Unassigned range 1"
    
    <div>
    

    > [!NOTE]  
    > 有关更多选项的详细信息，请参阅<A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">CsCallParkOrbit</A>。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中创建或修改未分配号码范围](lync-server-2013-create-or-modify-an-unassigned-number-range.md)  


[CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsUnassignedNumber)  
[CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

