---
title: Lync Server 2013：设置用户的电话拨入式会议 PIN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a user's dial-in conferencing PIN
ms:assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520985(v=OCS.15)
ms:contentKeyID: 48183970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c344a848050d53027c094ad549f0285fbae09489
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-users-dial-in-conferencing-pin-in-lync-server-2013"></a>在 Lync Server 2013 中设置用户的电话拨入式会议 PIN

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-06-10_

若要以已通过身份验证的用户身份加入电话拨入式会议，则具有 Active Directory 域服务（AD DS）凭据的 Lync Server 2013 用户需要一个个人标识号（PIN）。 如果用户忘记了电话拨入式会议 PIN，或者没有使用 Lync Server 设置 PIN，则可以从 Lync Server 控制面板设置用户的 PIN。 可以自动生成 PIN，或手动创建 PIN。

<div>


> [!NOTE]  
> 可以将 PIN 的具体特征（如 PIN 的最小长度）配置为策略。 除了全局策略，您还可以为各个站点或用户配置 PIN 策略。 有关配置 PIN 策略的详细信息，请参阅<A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">在 Lync Server 2013 中配置电话拨入式会议个人标识号码（PIN）规则</A>。



</div>

<div>

## <a name="to-set-a-users-pin"></a>设置用户的 PIN

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“用户”****。

4.  使用下列方法之一查找用户：
    
      - 在“搜索用户”**** 框中，键入用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”****。
    
      - 如果具有保存的查询，请单击“打开查询”**** 图标，使用“打开”**** 对话框来检索该查询（.usf 文件），然后单击“查找”****。

5.  （可选）指定附加搜索条件以缩小结果的范围：
    
    1.  单击“添加筛选器”****。
    
    2.  通过键入用户属性，或单击下拉列表中的箭头选择属性来输入用户属性。
    
    3.  在“等于”**** 下拉列表中，单击运算符（例如“等于”**** 或“不等于”****）。
    
    4.  根据所选的用户属性，通过键入条件或单击下拉列表中的箭头输入用于筛选搜索结果的条件。
        
        <div>
        

        > [!TIP]  
        > 要向查询中添加附加搜索子句，请单击“添加筛选器”<STRONG></STRONG>。

        
        </div>
    
    5.  单击“查找”****。
    
    <div>
    

    > [!NOTE]  
    > 如果锁定了 PIN，则必须解锁 PIN，然后才能对其进行设置。要解锁 PIN，请单击用户，再单击“操作”<STRONG></STRONG>，然后单击“解锁 PIN”<STRONG></STRONG>。

    
    </div>

6.  在搜索结果中单击某个用户，再单击“操作”****，然后单击“设置 PIN”****。

7.  在“设置 PIN”**** 对话框中，执行下列操作之一：
    
      - 若要允许 Lync Server 2013 生成用户的 PIN，请选择 "**自动生成有效 PIN** （默认值）"。
    
      - 要创建您自己的 PIN，请单击“手动输入特定 PIN”****，单击文本框，然后键入满足 PIN 策略设置中指定的 PIN 要求的 PIN。

8.  单击“确定”****。

9.  在“设置 PIN”**** 中，执行下列操作之一：
    
      - 选中“显示 PIN”**** 复选框以查看 PIN，然后复制 PIN，并使用组织的首选方法将其传达给用户。
    
      - 单击“打开我的电子邮件应用程序以将新 PIN 发送给用户”**** 以通过电子邮件发送 PIN。如果您使用 Microsoft Office Outlook 作为电子邮件客户端，则会自动将 PIN 复制到新的电子邮件。如果使用其他电子邮件客户端，请选中“显示 PIN”**** 复选框以查看 PIN，然后将其复制到电子邮件。

10. 单击“关闭”****。

</div>

<div>

## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 分配用户 PIN

您还可以使用 Unlock-csclientpin cmdlet 分配 PIN 号码。 您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>

## <a name="to-auto-assign-a-pin-number-to-a-user"></a>将 PIN 号码自动分配给用户

  - 以下命令可将 PIN 号码分配给用户 Ken Myer。 由于不包含 Pin 参数，因此 Lync Server 将自动生成并分配 PIN 号码。
    
        Set-CsClientPin -Identity "Ken Myer" 

</div>

<div>

## <a name="to-assign-a-specific-pin-number-to-a-user"></a>为用户分配特定的 PIN 号码

  - 此命令使用 Pin 参数为用户 Ken Myer 分配 PIN 号码 121989。
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

</div>

有关详细信息，请参阅[unlock-csclientpin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) cmdlet 的帮助主题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[拨入访问号码](https://technet.microsoft.com/library/gg133674\(v=ocs.15\))  


[在 Lync Server 2013 中配置电话拨入式会议个人标识号码（PIN）规则](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

