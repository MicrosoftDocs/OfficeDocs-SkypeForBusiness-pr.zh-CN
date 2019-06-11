---
title: 'Lync Server 2013: 分配每个用户的语音策略'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user voice policy
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49733758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e74bebc202a9e8d9fbc7b925c14bbe030e4c577
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845943"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a>在 Lync Server 2013 中分配每用户语音策略

 


全局策略和网站级语音策略将自动分配给所有启用企业语音的 Lync Server 2013 用户帐户。 您还可以使用 Lync Server 2013 控制面板或 Lync Server 2013 管理外壳程序将语音策略分配给特定用户。 使用本主题中的过程将每个用户策略显式分配给 Lync Server 用户。

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a>使用 Lync Server "控制面板" 分配特定于用户的语音策略

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“**用户**”，然后搜索要配置的用户帐户。

4.  在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。

5.  在 "在**语音策略**中**编辑 Lync 服务器用户**" 下, 选择要应用的用户策略。
    

    > [!NOTE]  
    > " <STRONG> &lt;自动&gt; </STRONG>设置" 将应用默认服务器或全局策略设置。



## <a name="assigning-a-per-user-voice-policy-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 分配每用户语音策略

你可以使用 Windows PowerShell 和**CsVoicePolicy** cmdlet 分配每用户语音策略。 你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## <a name="to-assign-a-per-user-voice-policy-to-a-single-user"></a>将每用户语音策略分配给单个用户

  - 以下命令将每用户语音策略 RedmondVoicePolicy 分配给用户 Ken Myer。
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="to-assign-a-per-user-voice-policy-to-multiple-users"></a>将每个用户的语音策略分配给多个用户

  - 此命令将每用户语音策略 FinanceVoicePolicy 分配给在 Active Directory 的财务 OU 中拥有帐户的所有用户。 有关此命令中使用的 OU 参数的详细信息, 请参阅[move-csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet 的文档。
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="to-unassign-a-per-user-voice-policy"></a>取消分配每用户语音策略

  - 以下命令取消之前分配给 Ken Myer 的任何每用户语音策略。 取消分配每用户策略后，将自动使用全局策略或本地站点策略（如果存在）管理 Ken Myer。 站点策略优先于全局策略。
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

有关详细信息, 请参阅[CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\)) cmdlet 的帮助主题。

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中禁用企业语音用户](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[Lync Server 2013 命令行管理程序](lync-server-2013-lync-server-management-shell.md)

