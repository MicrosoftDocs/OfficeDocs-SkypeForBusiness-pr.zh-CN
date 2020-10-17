---
title: Lync Server 2013：分配每用户托管的语音邮件策略
description: Lync Server 2013：分配每用户托管的语音邮件策略。
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
ms.openlocfilehash: 071d504c452b4d3adb1b636cb5c4ff8835200107
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559888"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>在 Lync Server 2013 中分配每用户托管的语音邮件策略

 


部署一个或多个每用户托管语音邮件策略是可选的。如果要部署每用户策略，则必须将其显式分配给用户、组或联系人对象。

有关分配或删除每用户托管语音邮件策略分配的详细信息，请参阅以下 cmdlet 的 Lync Server 命令行管理程序文档：

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a>分配每用户托管语音邮件策略

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  运行 Grant-CsHostedVoicemailPolicy cmdlet 将每用户托管语音邮件策略分配给各个用户、组和联系人对象。例如，运行：
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    此示例将 ExRedmond 托管语音邮件策略分配给用户 Ken Myer。
    
    **Identity** 指定要修改的用户帐户。可以使用以下任意格式指定 Identity 值：
    
      - 用户的 SIP 地址
    
      - 用户的 Active Directory 用户主体名称
    
      - 用户的域 \\ 登录名 (例如，contoso \\ kenmyer) 
    
      - 用户的 Active Directory 域服务显示名称（例如，Ken Myer）。 如果使用 Display-Name 作为 Identity 值，则可以使用星号 (\*) 通配符。 例如，标识 " \* smith" 将返回其 Display-Name 以字符串值 "smith" 结尾的所有用户。
    

    > [!NOTE]  
    > 用户的 Active Directory SAM 帐户名不能用作 Identity 值，因为 SAM 帐户名在林中不一定是唯一的。


