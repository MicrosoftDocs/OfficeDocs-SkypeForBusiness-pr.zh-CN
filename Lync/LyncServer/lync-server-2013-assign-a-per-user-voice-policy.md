---
title: Lync Server 2013：分配每用户语音策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user voice policy
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49733758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1528ef6124193023a0e5938caac7b40c2c6187a2
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "44943925"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a>在 Lync Server 2013 中分配每用户语音策略

 


全局和网站级语音策略将自动分配给为企业语音启用的所有 Lync Server 2013 用户帐户。 您还可以使用 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序将语音策略分配给特定用户。 使用本主题中的过程将每个用户策略明确分配给 Lync Server 用户。

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a>使用 Lync Server 控制面板分配特定于用户的语音策略

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“用户”****，然后搜索要配置的用户帐户。

4.  在列出搜索结果的表中，单击相应的用户帐户，再单击“编辑”****，然后单击“显示详细信息”****。

5.  在“编辑 Lync Server 用户”**** 中的“语音策略”**** 下，选择要应用的用户策略。
    

    > [!NOTE]  
    > " <STRONG> &lt; 自动 &gt; </STRONG> " 设置将应用默认服务器或全局策略设置。



## <a name="assign-per-user-voice-policies"></a>分配每用户语音策略

您可以使用 Windows PowerShell 和**set-csvoicepolicy** cmdlet 分配每用户语音策略。 您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。 若要了解如何使用远程 Windows PowerShell 连接到 Lync Server，请阅读此 Lync Server Windows PowerShell 博客文章：[快速入门：使用远程 PowerShell 管理 Microsoft Lync server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)。

### <a name="assign-a-per-user-voice-policy-to-a-single-user"></a>为单个用户分配每用户语音策略

  - 以下命令向用户 Ken Myer 分配每用户语音策略 RedmondVoicePolicy。
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="assign-a-per-user-voice-policy-to-multiple-users"></a>为多个用户分配每用户语音策略

  - 此命令向在 Active Directory 的 Finance OU 中拥有帐户的所有用户分配每用户语音策略 FinanceVoicePolicy。 有关此命令中使用的 OU 参数的详细信息，请参阅[get-csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet 的相关文档。
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="unassign-a-per-user-voice-policy"></a>取消分配每用户语音策略

  - 以下命令取消分配之前为 Ken Myer 分配的任何每用户语音策略。在取消分配每用户策略后，将自动使用全局策略或本地站点策略（如果有）管理 Ken Myer。站点策略优先于全局策略。
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

有关详细信息，请参阅[set-csvoicepolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\)) cmdlet 的帮助主题。

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中禁用用户的企业语音](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[Lync Server 2013 命令行管理程序](lync-server-2013-lync-server-management-shell.md)

