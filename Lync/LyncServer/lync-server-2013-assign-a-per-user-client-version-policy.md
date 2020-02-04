---
title: Lync Server 2013：分配每个用户的客户端版本策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user client version policy
ms:assetid: f7e8ba2f-62dc-4e7d-8b63-682986f10240
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182607(v=OCS.15)
ms:contentKeyID: 48185868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e509427b6d2651f84b96a96c87fbe7cfd6177a7d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738372"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a>在 Lync Server 2013 中分配每用户客户端版本策略

 


客户端版本策略是你可以在 Lync Server 控制面板中配置的用户帐户的个人设置之一。

部署一个或多个每用户客户端版本策略是可选的。 你还可以仅部署全局级别的客户端版本策略，或者部署网站级或池级别的客户端版本策略。 如果要部署每用户策略，则必须将其明确分配给用户、组或联系人对象。 如果未分配特定的网站级别、池级别或每用户策略，则允许注册 Lync Server 2013 的默认客户端是全局级客户端版本策略中定义的客户端。

创建至少一个每用户客户端版本策略后，请使用本主题中的过程来分配指定你希望允许向 Lync Server 注册的客户端版本的策略。

有关创建基于用户的客户端版本策略的详细信息，请参阅[指定可用于登录 Lync Server 2013 的客户端应用程序](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md)。

## <a name="to-assign-a-per-user-client-version-policy"></a>分配每个用户的客户端版本策略

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
    > 如果想要将同一每用户客户端版本策略应用于多个用户，请在搜索结果中选择 "多个用户"，然后单击 "<STRONG>操作</STRONG>"，然后单击 "<STRONG>分配策略</STRONG>"。



7.  在 "**分配策略**" 下的 "**客户端版本策略**" 下，执行下列操作之一：
    

    > [!NOTE]  
    > 由于有多个策略可以使用 "<STRONG>分配策略</STRONG>" 对话框进行配置，因此默认情况下为对话框中的每个策略选中 " <STRONG> &lt;保持&gt; </STRONG>原样"。 如果不对此设置进行任何更改，则将继续使用先前分配给用户的策略。

    
      - 允许 Lync Server 自动选择全局级别策略或网站级策略或池级别策略（如果已定义）。
    
      - 单击您以前在 "**客户端版本策略**" 页面上定义的每用户客户端版本策略的名称。
        

        > [!TIP]  
        > 为帮助您确定要分配的策略，请在单击策略名称后单击“查看”<STRONG></STRONG>以查看策略中定义的用户权限。



8.  完成后，单击“确定”****。

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 分配基于每个用户的客户端版本策略

你可以使用 CsClientVersionPolicy cmdlet 分配基于每个用户的客户端版本策略。 你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a>将每个用户的客户端版本策略分配给单个用户

  - 以下命令将每用户客户端版本策略 RedmondClientVersionPolicy 分配给用户 Ken Myer。
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a>将每个用户的客户端版本策略分配给多个用户

  - 此命令将每用户客户端版本策略 RedmondClientVersionPolicy 分配给当前分配了语音策略 RedmondVoicePolicy 的所有用户。 有关此命令中使用的 Filter 参数的详细信息，请参阅[move-csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet 的文档。
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a>取消分配每用户客户端版本策略

  - 以下命令取消之前分配给 Ken Myer 的任何每用户客户端版本策略。 在未分配每用户策略后，Ken Myer 将通过使用全局策略、其本地网站策略（如果有）或分配给其注册机构的服务范围策略自动进行管理。 服务范围策略优先于任何网站策略，并且网站策略优先于全局策略。
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

有关详细信息，请参阅[CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/gg412903\(v=ocs.15\)) cmdlet 的帮助主题。

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中分配每个用户的策略](lync-server-2013-assigning-per-user-policies.md)  
[在 Lync Server 2013 中管理设备、电话和客户端应用程序](lync-server-2013-managing-devices-phones-and-client-applications.md)

