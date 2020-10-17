---
title: Lync Server 2013：会议的计划详细信息
description: Lync Server 2013：会议的计划详细信息。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scheduling details
ms:assetid: 39ca6fff-2c15-4347-9f1f-6c8687a39a49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204823(v=OCS.15)
ms:contentKeyID: 48183910
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef7a6907aedbc880731b3fb474c9294c1c111b80
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561978"
---
# <a name="scheduling-details-for-meetings-in-lync-server-2013"></a>Lync Server 2013 中会议的日程安排详细信息

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-04_

检查确保在请求的时间没有安排其他会议后，处理请求的大型会议支持人员将在大型会议池中安排会议。 使用与 Lync Server 2013 客户端一起安装的 lync 的联机会议外接程序，以使用在专用大型会议池中启用了 Lync Server 的用户的凭据来执行此任务。

若要确保最佳用户体验，应使用适用于会议组织者的需求的合适访问级别和会议设置安排大型会议，这点很重要。 建议在 Lync 会议选项中配置以下计划设置：

  - 对每个大型会议使用新的会议空间而不重用专用会议空间。

  - 按以下方式指定会议访问级别：
    
      - 如果至少有一个被邀请者在组织外部，则将会议访问类型设置为**任何人（无限制**）。这样，您在会议过程中便无需管理可能较大的会议厅。
    
      - 如果会议是仅针对内部的会议，则将会议访问类型设置为**我的组织中的任何人**。
        
        <div>
        

        > [!NOTE]  
        > 避免将会议访问类型设置为<STRONG>从我的公司邀请的人员</STRONG>，因为当您使用此设置时，组织者必须将所有用户电子邮件地址添加到被邀请者列表，且您无法邀请通讯组。<BR>避免将会议访问类型设置为<STRONG>只有我（会议组织者）</STRONG>，因为此设置要求在会议运行时必须将每个会议参与者（包括演示者）置于会议厅中。负责主持大型会议的人员随后必须持续监视会议厅名单并允许位于会议厅中的新用户加入会议。

        
        </div>

  - 允许用电话拨入的用户通过选中“呼叫者直接参与”**** 设置自动进入会议。

  - 显式邀请以下用户：
    
      - 会议组织者和代理人（请求者）
    
      - 会议请求者提供的演示者的列表
    
    <div>
    

    > [!NOTE]  
    > 如果会议访问类型设置为<STRONG>我选择的人员</STRONG>，则需要将大型会议的每个参与者作为会议的被邀请者显式添加。

    
    </div>

  - 显式管理演示者，而不用将演示者选项设置为自动升级值之一。确保将以下用户作为演示者添加：
    
      - 会议组织者和代理人（请求者）
    
      - 大型会议请求者提供的演示者的列表
    
    <div>
    

    > [!NOTE]  
    > 通过显式管理演示者，您可以控制演示者的数量，以便将其限制为足够小的数量，从而有可能获得有效的大型会议。如果大多数会议参与者都具有与会者角色，则有助于减少人员意外获得对演示的控制权、删除 PowerPoint 演示、将演示者设为静音/取消静音以及对会议的其他中断的机会。

    
    </div>

  - 选中“将所有与会者设为静音”**** 设置以确保只有演示者能将音频广播到会议中。

  - 选中“阻止与会者的视频”**** 设置以确保只有参与者能将视频广播到会议中。

下图显示了适用于 Lync 的联机会议外接程序的推荐设置。

![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")

</div>

<span> </span>

</div>

</div>

</div>

