---
title: Lync Server 2013：分配每用户托管的语音邮件策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user hosted voice mail policy
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398919(v=OCS.15)
ms:contentKeyID: 48185456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95413733a9b23ce1f749ebb16521a3349b00165d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722952"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>在 Lync Server 2013 中分配每用户托管语音邮件策略

 


部署一个或多个每用户托管的语音邮件策略是可选的。 如果你确实要部署每用户策略，则必须将它们显式分配给用户、组或联系人对象。

有关分配或删除每用户托管语音邮件策略分配的详细信息，请参阅以下 cmdlet 的 Lync Server Management Shell 文档：

  - 授权-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a>分配每用户托管的语音邮件策略

1.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

2.  运行 CsHostedVoicemailPolicy cmdlet，将每用户托管语音邮件策略分配给单个用户、组和联系人对象。 例如，运行：
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    此示例将 ExRedmond 托管语音邮件策略分配给用户 Ken Myer。
    
    **标识**指定要修改的用户帐户。 可以使用以下任意格式指定标识值：
    
      - 用户的 SIP 地址
    
      - 用户的 Active Directory 用户主体-名称
    
      - 用户的域\\登录名（例如，contoso\\kenmyer）
    
      - 用户的 Active Directory 域服务显示名称（如 Ken Myer）。 如果使用显示名称作为标识值，则可以使用星号（\*）通配符。 例如，标识 "\* smith" 将返回具有以字符串值 "smith" 结尾的显示名称的所有用户。
    

    > [!NOTE]  
    > 用户的 Active Directory SAM-帐户名称不能用作标识值，因为 SAM 帐户名称不一定在林中唯一。


