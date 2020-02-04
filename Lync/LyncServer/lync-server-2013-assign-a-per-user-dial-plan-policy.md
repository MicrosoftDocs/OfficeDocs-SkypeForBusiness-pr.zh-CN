---
title: Lync Server 2013：分配每个用户的拨号计划策略
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
ms.openlocfilehash: f2bc62981a69b1260ba5f2fbaeabc112553b85f5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722962"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a>在 Lync Server 2013 中分配每个用户的拨号计划策略

 


若要为企业语音的用户和电话拨入式会议的用户完成用户帐户配置，必须为用户分配一个拨号计划。 用户帐户将自动使用全局拨号计划，或者，如果存在，则当你没有明确分配现有的每用户拨号计划时，网站级别的拨号计划将自动使用。 如果要对所有已启用企业语音的用户使用全局或网站拨号计划，则可以跳过此部分。

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a>使用 Lync Server 2013 "控制面板" 分配拨号计划

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左导航栏中，单击“用户”****。

4.  在“搜索用户”**** 框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”****。

5.  在表中，单击要分配拨号计划的用户帐户。

6.  在“编辑”**** 菜单上，单击“显示详细信息”****。

7.  在 "**编辑 Lync Server 用户**" 页面上的 "**电话服务**" 下，单击 "**企业语音**"。

8.  单击 "**拨号计划策略**"，然后选择所需的拨号计划。

9.  单击“**提交**”。

有关配置拨号计划的详细信息，请参阅[在 Lync Server 2013 中配置拨号计划](lync-server-2013-configuring-dial-plans.md)主题。

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 分配每用户拨号计划

你可以使用 Windows PowerShell 和**CsdialPlan** cmdlet 分配每用户拨号计划。 你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>将每用户拨号计划分配给单个用户

  - 以下命令将每用户拨号计划 RedmondDialPlan 分配给用户 Ken Myer。
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>将每用户拨号计划分配给多个用户

  - 此命令将每个用户的拨号计划 RedmondDialPlan 分配给在雷蒙德市的所有工作用户。 有关此命令中使用的 LdapFilter 参数的详细信息，请参阅[move-csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet 的文档。
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a>取消分配每用户拨号计划

  - 以下命令取消之前分配给 Ken Myer 的任何每用户拨号计划。 未分配每用户拨号计划后，Ken Myer 将通过使用全局拨号计划、本地网站拨号计划（如果有）或分配给其注册机构或 PSTN 网关的服务范围内的拨号计划自动进行管理。 服务范围拨号计划优先于任何网站拨号计划，并且网站拨号计划优先于全局拨号计划。
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

有关详细信息，请参阅[CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\)) cmdlet 的帮助主题。

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中配置拨号计划](lync-server-2013-configuring-dial-plans.md)  
[为 Lync Server 2013 启用的用户帐户](lync-server-2013-user-accounts-enabled-for-lync-server.md)

