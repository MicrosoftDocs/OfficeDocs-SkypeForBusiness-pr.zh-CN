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
ms.openlocfilehash: 6dc71125b42fab144b1c6ba15064e84c6be50b57
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a>在 Lync Server 2013 中为用户启用托管语音邮件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-24_

按照在托管 Exchange 统一消息（UM）服务上为语音邮件启用 Lync Server 2013 用户的过程操作。

有关详细信息，请参阅规划文档中的在[Lync Server 2013 中托管 Exchange 用户管理](lync-server-2013-hosted-exchange-user-management.md)。

有关[get-csuser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档。

<div>


> [!IMPORTANT]  
> 在可以对 Lync Server 2013 用户启用托管语音邮件之前，必须部署适用于其用户帐户的托管语音邮件策略。 有关详细信息，请参阅<A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中的托管语音邮件策略</A>。



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a>为用户启用托管语音邮件

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  运行 Get-csuser cmdlet 以配置托管语音邮件的用户帐户。 例如，运行：
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    上述示例设置了以下参数：
    
      - **HostedVoiceMail**允许将用户的语音邮件呼叫路由到托管 Exchange UM。 它还向 Microsoft Lync 2013 发出信号，以亮出 "呼叫语音邮件" 指示器。
    
      - **Identity** 指定要修改的用户帐户。可以使用以下任意格式指定 Identity 值：
        
          - 用户的 SIP 地址
        
          - 用户的 Active Directory 用户主体名称
        
          - 用户的域\\登录名（例如，contoso\\kenmyer）
        
          - 用户的 Active Directory 域服务显示名称（例如，Ken Myer）。 如果使用显示名称作为标识值，则可以使用星号（\*）通配符。 例如，标识 "\* smith" 将返回显示名称以字符串值 "smith" 结尾的所有用户。
        
        <div>
        

        > [!NOTE]  
        > 用户的 Active Directory SAM 帐户名不能用作 Identity 值，因为 SAM 帐户名在林中不一定是唯一的。

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

