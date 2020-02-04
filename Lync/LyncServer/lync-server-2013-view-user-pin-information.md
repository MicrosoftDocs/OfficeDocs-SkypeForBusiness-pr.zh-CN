---
title: Lync Server 2013：查看用户 PIN 信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View user PIN information
ms:assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688067(v=OCS.15)
ms:contentKeyID: 49733661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1e6f8e12e7b6d2dde684a4cf558eec0ece216a9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-user-pin-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看用户 PIN 信息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-23_

若要将电话拨入式会议作为经过身份验证的用户加入，使用 Active Directory 域服务（AD DS）凭据的 Lync Server 2013 用户需要一个个人识别码（PIN）。 您可以从 Lync Server 2013 控制面板查看用户的 PIN 信息。

<div>


> [!NOTE]  
> 您可以查看 PIN 状态信息（如是否已设置 PIN 或上次更改 PIN 的时间），但无法通过查看 PIN 状态来查看当前 PIN。 如果用户已丢失 PIN，则可以按照在<A href="lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md">Lync Server 2013 中设置用户的电话拨入式会议 PIN</A>中的过程重置它。



</div>

<div>

## <a name="to-view-a-users-pin-in-lync-server-control-panel"></a>在 Lync Server "控制面板" 中查看用户的 PIN

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左导航栏中，单击“用户”****。

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

6.  在搜索结果中单击某个用户，再单击“操作”****，然后单击“查看 PIN 状态”****。

</div>

<div>

## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell cmdlet 查看用户 PIN 信息

您可以使用 Get-CsClientPinInfo cmdlet 查看用户 PIN 信息。 此 cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-view-user-pin-information"></a>查看用户 PIN 信息

  - 若要查看用户的 PIN 信息，请在 Lync Server 命令行管理程序中键入类似于以下内容的命令，然后按 ENTER：
    
        Get-CsClientPinInfo -Identity "Ken Myer"
    
    这将返回与以下类似的信息：
    
        Identity          : sip:kenmyer@litwareinc.com
        IsPinSet          : False
        IsLockedOut       : False
        LastPinChangeTime : 9/25/2012 1:35:03 PM
        PinExpirationTime :

</div>

有关详细信息，请参阅[CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/Get-CsConferenceDisclaimer) cmdlet 的帮助主题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中设置用户的电话拨入式会议 PIN](lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md)  
[在 Lync Server 2013 中锁定或解锁用户 PIN](lync-server-2013-lock-or-unlock-a-user-pin.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

