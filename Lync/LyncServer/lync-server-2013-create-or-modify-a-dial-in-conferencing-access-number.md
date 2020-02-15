---
title: Lync Server 2013：创建或修改电话拨入式会议访问号码
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a dial-in conferencing access number
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398126(v=OCS.15)
ms:contentKeyID: 48183304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6406fe5c2f1183b39966902ee2fa5273f509bf2d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048923"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改电话拨入式会议访问号码

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-17_

如果要创建或修改电话拨入式会议访问号码，请按照以下步骤操作。

<div>


> [!IMPORTANT]  
> 在创建新的拨入访问号码之前，必须在与新的拨入访问号码相关联的拨号计划中设置电话拨入式会议区域。 多个拨号计划可以使用同一个区域。



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a>创建或修改拨入访问号码

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“会议”****，然后单击“拨入访问号码”****。

4.  在 "**拨入访问号码**" 页上，执行下列操作之一：
    
      - 单击 "**新建**" 打开 "**新建拨入访问号码**"。
    
      - 单击列表中的某个拨入访问号码，再单击 "**编辑**"，然后单击 "**显示详细信息**"。
        
        <div>
        

        > [!NOTE]  
        > 使用搜索字段搜索拨入访问号码列表中某一列的内容可能不会产生预期的结果。 而是按感兴趣的列对列表进行排序，以标识要查看或更改的拨入访问号码。

        
        </div>

5.  在 "**显示号码**" 中，键入公共交换电话网络（PSTN）电话用户拨打以加入会议的电话号码。
    
    <div>
    

    > [!NOTE]  
    > 此号码显示在 "会议邀请" 和 "电话拨入式会议设置" 网页上。

    
    </div>

6.  在 "**显示名称**" 中，键入拨入访问号码的说明。 这是与 Lync 搜索结果中的电话拨入访问号码相关联的名称。
    
    <div>
    

    > [!NOTE]  
    > 当用户呼叫访问号码时，此名称将显示在客户端中。

    
    </div>

7.  在 "**线路 uri**" 中，使用电话 URI 格式键入拨入访问号码的 e.164 号码，包括号码前面的 + 符号，不包括空格。 例如电话： + 14255550200。
    
    <div>
    

    > [!NOTE]  
    > 同一行 URI 不能由其他电话拨入式会议访问号码重复使用。

    
    </div>

8.  在 " **SIP URI**" 中，执行以下操作：
    
      - 在文本框中，为此电话拨入式会议访问号码键入唯一的 SIP URI。 此 SIP URI 显示在各种位置，包括但不限于呼叫通知邮件和以前版本的 Communicator 客户端。
        
        <div>
        

        > [!NOTE]  
        > 同一 SIP URI 不能由其他电话拨入式会议访问号码重复使用。 在创建访问号码后，不能修改 SIP URI。 更改 SIP URI 的唯一方法是删除并重新创建访问号码。

        
        </div>
    
      - 在下拉列表框中，单击支持此拨入访问号码的会议助理应用程序所在的域。

9.  在 "**池**" 中，单击运行支持此拨入访问号码的会议助理实例的池。
    
    <div>
    

    > [!NOTE]  
    > 如果您在创建访问号码后需要更改池，则必须使用<STRONG>CsApplicationEndpoint</STRONG> cmdlet 或删除并重新创建访问号码。

    
    </div>

10. 在 "**主要语言**" 中，单击针对此拨入访问号码播放提示时使用的语言。
    
    <div>
    

    > [!NOTE]  
    > 主要语言是会议助理用来应答呼叫的语言。 在 "电话拨入式会议设置" 网页上，每个访问电话号码旁都会显示支持的语言。

    
    </div>

11. Optional在**辅助语言（最多四个）** 中，单击 "**添加**"，选择要为呼叫者支持此拨入访问号码的一种或多种其他语言，然后单击 **"确定"**。
    
    <div>
    

    > [!NOTE]  
    > 您最多可以为每个拨入访问号码选择四种辅助语言。 用户在拨入会议时，可以在进入会议 ID 之前选择辅助语言。

    
    </div>

12. 若要为拨入访问号码添加区域，请在 "**关联区域**" 下，单击 "**添加**"，单击与此拨入访问号码的拨号计划关联的一个或多个区域，然后单击 **"确定"**。

13. 若要从拨入访问号码中删除某个区域，请在 "**关联区域**" 下，单击要删除的区域，然后单击 "**删除**"。

14. 单击“提交”****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

