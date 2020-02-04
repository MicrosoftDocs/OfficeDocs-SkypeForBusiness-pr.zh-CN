---
title: Lync Server 2013：为用户启用托管语音邮件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for hosted voice mail
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413062(v=OCS.15)
ms:contentKeyID: 48185919
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e0ce9ee4da6ee0a36e5e5f0028371aab8af523f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a>在 Lync Server 2013 中为用户启用托管语音邮件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-24_

按照在托管 Exchange 统一消息（UM）服务上为语音邮件启用 Lync Server 2013 用户的过程进行操作。

有关详细信息，请参阅规划文档中的[Lync Server 2013 中的 "托管 Exchange 用户管理](lync-server-2013-hosted-exchange-user-management.md)"。

有关[move-csuser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet 的详细信息，请参阅 Lync Server Management Shell 文档。

<div>


> [!IMPORTANT]  
> 在 Lync Server 2013 用户可启用托管语音邮件之前，必须部署适用于其用户帐户的托管语音邮件策略。 有关详细信息，请参阅<A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中的托管语音邮件策略</A>。



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a>为用户启用托管语音邮件

1.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

2.  运行 Move-csuser cmdlet 以配置托管语音邮件的用户帐户。 例如，运行：
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    上述示例设置了以下参数：
    
      - **HostedVoiceMail**使用户的语音邮件呼叫能够路由到托管 Exchange UM。 它还会向 Microsoft Lync 2013 发出信号，以突出 "呼叫语音邮件" 指示器。
    
      - **标识**指定要修改的用户帐户。 可以使用以下任意格式指定标识值：
        
          - 用户的 SIP 地址
        
          - 用户的 Active Directory 用户主体-名称
        
          - 用户的域\\登录名（例如，contoso\\kenmyer）
        
          - 用户的 Active Directory 域服务显示名称（如 Ken Myer）。 如果使用显示名称作为标识值，则可以使用星号（\*）通配符。 例如，标识 "\* smith" 将返回具有以字符串值 "smith" 结尾的显示名称的所有用户。
        
        <div>
        

        > [!NOTE]  
        > 用户的 Active Directory SAM-帐户名称不能用作标识值，因为 SAM 帐户名称不一定在林中唯一。

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

