---
title: Lync Server 2013：分配每用户拨号计划策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user dial plan policy
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49733760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bd4d46e2cd41c972258a84a1e8fb34549dc8b4e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134438"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a>在 Lync Server 2013 中分配每用户拨号计划策略

 


要完成企业语音用户或电话拨入式会议用户的用户帐户配置，必须为用户分配拨号计划。如果没有显式分配现有每用户拨号计划，则用户帐户将自动使用全局拨号计划或站点级别拨号计划（如果存在）。如果要为所有启用企业语音的用户使用全局或站点拨号计划，可以跳过这一节。

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a>使用 Lync Server 2013 控制面板分配拨号计划

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“用户”****。

4.  在“搜索用户”**** 框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”****。

5.  在表中，单击要分配拨号计划的用户帐户。

6.  在“编辑”**** 菜单上，单击“显示详细信息”****。

7.  在“编辑 Lync Server 用户”**** 页的“电话”**** 下，单击“企业语音”****。

8.  单击“拨号计划策略”****，然后选择所需的拨号计划。

9.  单击“提交”****。

有关配置拨号计划的详细信息，请参阅[在 Lync Server 2013 中配置拨号计划](lync-server-2013-configuring-dial-plans.md)主题。

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 分配每用户拨号计划

您可以使用 Windows PowerShell 和**grant-csdialplan** cmdlet 分配每用户拨号计划。 您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>为单个用户分配每用户拨号计划

  - 以下命令向用户 Ken Myer 分配每用户拨号计划 RedmondDialPlan。
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>将每用户拨号计划分配给多个用户

  - 此命令向在 Redmond 市工作的所有用户分配每用户拨号计划 RedmondDialPlan。 有关此命令中使用的 LdapFilter 参数的详细信息，请参阅[get-csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet 的文档。
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a>取消分配每用户拨号计划

  - 以下命令取消分配之前为 Ken Myer 分配的任何每用户拨号计划。在取消分配每用户拨号计划后，将通过以下方式自动管理 Ken Myer：使用全局拨号计划，使用其本地站点拨号计划（如果有）或使用分配给其注册器或 PSTN 网关的服务范围的拨号计划。服务范围的拨号计划优先于任何站点拨号计划，而站点拨号计划优先于全局拨号计划。
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

有关详细信息，请参阅[grant-csdialplan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\)) cmdlet 的帮助主题。

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中配置拨号计划](lync-server-2013-configuring-dial-plans.md)  
[为 Lync Server 2013 启用的用户帐户](lync-server-2013-user-accounts-enabled-for-lync-server.md)

