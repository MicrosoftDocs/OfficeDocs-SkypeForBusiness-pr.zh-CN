---
title: 'Lync Server 2013: 禁用企业语音用户'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disable a user for Enterprise Voice
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49733635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dabe378f07cbca263ba3b32257c310b01bd922c0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-a-user-for-enterprise-voice-in-lync-server-2013"></a>在 Lync Server 2013 中禁用企业语音用户

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-21_

使用以下过程为已启用 Lync Server 2013 的用户帐户禁用企业语音。

<div>

## <a name="to-disable-a-user-account-for-enterprise-voice"></a>禁用企业语音的用户帐户

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左导航栏中，单击“用户”****。

4.  在“搜索用户”**** 框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”****。

5.  在表中, 单击要为企业语音启用的用户帐户。

6.  在“编辑”**** 菜单上，单击“显示详细信息”****。

7.  在 "**编辑 Lync Server 用户**" 页面上的 "**电话服务**" 下, 单击除**企业语音**之外的任何选项。
    
    <div>
    

    > [!NOTE]  
    > 若要限制用户使用 Lync 进行音频或视频呼叫, 请在 "<STRONG>电话服务</STRONG>" 下, 单击 "<STRONG>音频/视频已禁用</STRONG>"。

    
    </div>

8.  单击“**提交**”。

用户现在无法使用企业语音功能。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中启用企业语音用户](lync-server-2013-enable-users-for-enterprise-voice.md)  


[在 Lync Server 2013 中管理用户的企业语音语音](lync-server-2013-managing-enterprise-voice-for-users.md)  
[Lync Server 2013 命令行管理程序](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

