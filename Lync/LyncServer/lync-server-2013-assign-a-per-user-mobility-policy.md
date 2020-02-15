---
title: Lync Server 2013：分配每用户移动策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user mobility policy
ms:assetid: d8bf997f-4bc7-48d3-973b-323505f55e9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721902(v=OCS.15)
ms:contentKeyID: 49733836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1014bce74e0e7dcd789c9b2948c029f4b40ecb9a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030135"
---
# <a name="assign-a-per-user-mobility-policy-in-lync-server-2013"></a>在 Lync Server 2013 中分配每用户移动策略

 


移动策略是您可以在 Lync Server 控制面板或 Lync Server 命令行管理程序中配置的用户帐户的个人设置之一。

## <a name="to-assign-a-per-user-mobility-policy-with-lync-server-control-panel"></a>使用 Lync Server 控制面板分配每用户移动策略

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
        

        > [!TIP]  
        > 要向查询中添加附加搜索子句，请单击“添加筛选器”<STRONG></STRONG>。

    
    5.  单击“查找”****。

6.  在搜索结果中单击某个用户，再单击“操作”****，然后单击“分配策略”****。
    

    > [!TIP]  
    > 如果要将相同的每用户移动策略应用于多个用户，请在搜索结果中选择 "多个用户"，然后单击 "<STRONG>操作</STRONG>"，然后单击 "<STRONG>分配策略</STRONG>"。



7.  在 "**分配策略**" 中的 "**移动策略**" 下，执行下列操作之一：
    

    > [!NOTE]  
    > 由于可以在 "<STRONG>分配策略</STRONG>" 中配置多个策略，因此默认情况下将为对话框中的每个策略选择 " <STRONG> &lt;保持为&gt; </STRONG> "。 如果不对此设置进行任何更改，则将继续使用先前分配给用户的策略。

    
      - 选择** \<"\>自动**" 以允许 Lync Server 2013 自动选择全局级别策略或网站级别策略（如果已定义）。
    
      - 单击先前在**移动策略**页上定义的每用户移动性策略的名称。
        

        > [!TIP]  
        > 为帮助您确定要分配的策略，请在单击策略名称后单击“查看”<STRONG></STRONG>以查看策略中定义的用户权限。



8.  完成后，单击“确定”****。

## <a name="assigning-a-per-user-mobility-policy-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 分配每用户移动策略

您可以使用 Windows PowerShell 和**set-csmobilitypolicy** cmdlet 分配每用户移动性策略。 您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

## <a name="to-assign-a-per-user-mobility-policy-to-a-single-user"></a>向单个用户分配每用户移动策略

  - 以下命令将每用户移动策略 RedmondMobilityPolicy 分配给用户 Ken Myer。
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName "RedmondMobilityPolicy"

## <a name="to-assign-a-per-user-mobility-policy-to-multiple-users"></a>为多个用户分配每用户移动策略

  - 以下命令将每用户移动策略 RedmondMobilityPolicy 分配给当前分配了 policy NorthAmericaMobilityPolicy 的所有用户。 有关此命令中使用的 Filter 参数的详细信息，请参阅[get-csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\))。
    
        Get-CsUser -Filter {MobilityPolicy -eq "NorthAmericaMobilityPolicy"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## <a name="to-unassign-a-per-user-mobility-policy"></a>取消分配每用户移动策略

  - 以下命令取消分配之前分配给 Ken Myer 的任何每用户移动性策略。 取消分配每用户策略后，将使用全局策略或其本地站点策略（如果存在）自动管理 Ken Myer。 站点策略优先于全局策略。
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName $Null

有关详细信息，请参阅[set-csmobilitypolicy](https://technet.microsoft.com/library/hh690038\(v=ocs.15\))。

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中配置移动策略](lync-server-2013-configuring-mobility-policy.md)

