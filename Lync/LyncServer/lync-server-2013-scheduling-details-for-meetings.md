---
title: Lync Server 2013：计划的会议详细信息
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
ms.openlocfilehash: a4a0f85e93588e725e825fee22a8c2e95b74095b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764950"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scheduling-details-for-meetings-in-lync-server-2013"></a>Lync Server 2013 中会议的计划详细信息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-04_

检查确保在请求的时间没有安排其他会议后，处理请求的大型会议支持人员将在大型会议池中安排会议。 使用使用 lync server 2013 客户端安装的适用于 lync 的联机会议加载项执行此任务，使用在专用大型会议池中启用 Lync Server 的用户的凭据。

若要确保最佳用户体验，应使用适用于会议组织者的需求的合适访问级别和会议设置安排大型会议，这点很重要。 我们建议在 Lync 会议选项中配置以下计划设置：

  - 对每个大型会议使用新的会议空间而不重用专用会议空间。

  - 按以下方式指定会议访问级别：
    
      - 如果组织外部至少有一个被邀请者，请将会议访问类型设置为 "**任何人" （无限制**）。 这样，您在会议过程中便无需管理可能较大的会议厅。
    
      - 如果会议是仅针对内部的会议，则将会议访问类型设置为“我的组织中的任何人”****。
        
        <div>
        

        > [!NOTE]  
        > 避免将会议访问类型设置为“从我的公司邀请的人员”<STRONG></STRONG>，因为当您使用此设置时，组织者必须将所有用户电子邮件地址添加到被邀请者列表，且您无法邀请通讯组。<BR>避免将会议访问类型设置为“只有我（会议组织者）”<STRONG></STRONG>，因为此设置要求在会议运行时必须将每个会议参与者（包括演示者）置于会议厅中。 负责主持大型会议的人员随后必须持续监视会议厅名单并允许位于会议厅中的新用户加入会议。

        
        </div>

  - 允许用电话拨入的用户选中“呼叫者直接参与”**** 设置自动进入会议。

  - 显式邀请以下用户：
    
      - 会议组织者和代理人（请求者）
    
      - 会议请求者提供的演示者的列表
    
    <div>
    

    > [!NOTE]  
    > 如果会议访问类型设置为“我选择的人员”<STRONG></STRONG>，则需要将大型会议的每个参与者显式添加为会议的受邀者。

    
    </div>

  - 显式管理演示者，而不用将演示者选项设置为自动升级值之一。确保将以下用户作为演示者添加：
    
      - 会议组织者和代理人（请求者）
    
      - 大型会议请求者提供的演示者的列表
    
    <div>
    

    > [!NOTE]  
    > 通过显式管理演示者，你可以控制演示者的数量，以便你可以将演示者限制为足够小的数字以使其可以拥有有效的大型会议。 如果大多数会议参与者都具有与会者角色，则有助于减少人员意外获得对演示的控制权、删除 PowerPoint 演示、将演示者设为静音/取消静音以及对会议的其他中断的机会。

    
    </div>

  - 选中“将所有与会者设为静音”**** 设置以确保只有演示者能将音频广播到会议中。

  - 选中“阻止与会者的视频”**** 设置以确保只有参与者能将视频广播到会议中。

下图显示了适用于 Lync 的联机会议加载项的推荐设置。

![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")

</div>

<span> </span>

</div>

</div>

</div>

