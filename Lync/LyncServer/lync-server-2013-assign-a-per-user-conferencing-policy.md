---
title: Lync Server 2013：分配每用户会议策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user conferencing policy
ms:assetid: 72f12c72-65f7-44fe-ab81-0f57cb2f87d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521015(v=OCS.15)
ms:contentKeyID: 48184475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d43bf1663a475bed93985b2257eefaaa07ff8c0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738362"
---
# <a name="assign-a-per-user-conferencing-policy-in-lync-server-2013"></a>在 Lync Server 2013 中分配每用户会议策略

 


会议策略是您可以在 Lync Server "控制面板" 中配置的用户帐户的个人设置之一。

部署一个或多个每用户会议策略是可选的。 您也可以仅部署全局级别的会议策略或网站级别的会议策略。 如果你确实要部署每用户策略，则必须将它们显式分配给用户、组或联系人对象。 会议用户权利和权限自动默认为在未分配特定网站级或每用户策略时全局级别会议策略中定义的用户。

创建至少一个每用户会议策略后，请使用本主题中的过程分配策略，该策略指定你希望服务器授予由特定用户组织的会议的用户权利和权限。

有关所有可用会议策略设置的列表，请参阅[Lync Server 2013 的会议策略设置参考](lync-server-2013-conferencing-policy-settings-reference.md)。

有关创建会议策略的详细信息，请参阅[在 Lync Server 2013 中创建或修改会议策略](lync-server-2013-create-or-modify-a-conferencing-policy.md)。

## <a name="to-assign-a-per-user-conferencing-policy"></a>分配每用户会议策略

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
        

        > [!TIP]  
        > 要向查询中添加附加搜索子句，请单击“添加筛选器”<STRONG></STRONG>。

    
    5.  单击“查找”****。

6.  在搜索结果中单击某个用户，再单击“操作”****，然后单击“分配策略”****。
    

    > [!TIP]  
    > 如果想要将同一每用户会议策略应用于多个用户，请在搜索结果中选择 "多个用户"，然后单击 "<STRONG>操作</STRONG>"，然后单击 "<STRONG>分配策略</STRONG>"。



7.  在 "**分配策略**" 下的 "**会议策略**" 下，执行下列操作之一：
    

    > [!NOTE]  
    > 由于有多个策略可在 "<STRONG>分配策略</STRONG>" 中进行配置，因此默认情况下为对话框中的每个策略选中 " <STRONG> &lt;保持&gt; </STRONG>原样"。 如果不对此设置进行任何更改，则将继续使用先前分配给用户的策略。

    
      - 选择** \<"\>自动**" 允许 Lync Server 2013 自动选择全局级别策略，或选择 "网站级别策略" （如果已定义）。
    
      - 单击您以前在 "**会议策略**" 页面上定义的每用户会议策略的名称。
        

        > [!TIP]  
        > 为帮助您确定要分配的策略，请在单击策略名称后单击“查看”<STRONG></STRONG>以查看策略中定义的用户权限。



8.  完成后，单击“确定”****。

## <a name="assigning-a-per-user-conferencing-policy-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 分配每用户会议策略

每用户会议策略可以使用 Windows PowerShell 和 CsConferencingPolicy cmdlet 进行分配。 此 cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## <a name="to-assign-a-per-user-conferencing-policy-to-a-single-user"></a>将每用户会议策略分配给单个用户

  - 以下命令将每用户会议策略 RedmondConferencingPolicy 分配给用户 Ken Myer。
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName "RedmondConferencingPolicy"

## <a name="to-assign-a-per-user-conferencing-policy-to-multiple-users"></a>将每用户会议策略分配给多个用户

  - 此命令将每用户会议策略 HRConferencingPolicy 分配给工作人力资源部门的所有用户。 有关此命令中使用的 LdapFilter 参数的详细信息，请参阅[move-csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet 的文档。
    
        Get-CsUser -LdapFilter "Department=Human Resources" | Grant-CsConferencingPolicy -PolicyName "HRConferencingPolicy"

## <a name="to-unassign-a-per-user-conferencing-policy"></a>取消分配每用户会议策略

  - 以下命令取消之前分配给 Ken Myer 的任何每用户会议策略。 取消分配每用户策略后，将自动使用全局策略或本地站点策略（如果存在）管理 Ken Myer。 站点策略优先于全局策略。
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName $Null

有关详细信息，请参阅[CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\)) cmdlet 的帮助主题。

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中创建或修改会议策略](lync-server-2013-create-or-modify-a-conferencing-policy.md)  


[在 Lync Server 2013 中分配每个用户的策略](lync-server-2013-assigning-per-user-policies.md)

