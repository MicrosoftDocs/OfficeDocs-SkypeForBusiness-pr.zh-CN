---
title: Lync Server 2013：创建或修改电话拨入式会议访问号码
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a dial-in conferencing access number
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398126(v=OCS.15)
ms:contentKeyID: 48183304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8372c8117f2e33594ae59b3eff15c6d7eee96ba6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改电话拨入式会议访问号码

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-17_

如果要创建或修改电话拨入式会议接入号码, 请按照以下步骤操作。

<div>


> [!IMPORTANT]  
> 在创建新的拨入访问号码之前, 必须在与新的拨入接入号码相关联的拨号计划中设置电话拨入式会议区域。 多个拨号计划可以使用同一区域。



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a>创建或修改拨入访问号码

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“会议”****，然后单击“拨入访问号码”****。

4.  在“拨入访问号码”**** 页上，执行下列某个操作：
    
      - 单击“新建”**** 打开“新建拨入访问号码”****。
    
      - 单击列表中的一个拨入访问号码，再单击“编辑”****，然后单击“显示详细信息”****。
        
        <div>
        

        > [!NOTE]  
        > 使用搜索字段搜索拨入访问号码列表中某一列的内容时，可能得不到预期结果。此时，可以按照列的关注度对列表进行排序，以识别要查看或更改的拨入访问号码。

        
        </div>

5.  在“**显示号码**”中，键入相应的电话号码，以便公用电话交换网 (PSTN) 电话用户可拨打此号码加入会议。
    
    <div>
    

    > [!NOTE]  
    > 该号码会显示在会议邀请和电话拨入式会议设置网页中。

    
    </div>

6.  在“显示名称”**** 中，键入拨入访问号码的说明。 这是与 Lync 搜索结果中的拨入访问号码相关联的名称。
    
    <div>
    

    > [!NOTE]  
    > 用户呼叫访问号码时，此名称会显示在客户端上。

    
    </div>

7.  在“线路 URI”**** 中，使用 TEL URI 格式键入拨入访问号码的 E.164 号码，请在此号码前添加 + 符号，不要添加空格。例如：tel:+14255550200。
    
    <div>
    

    > [!NOTE]  
    > 同一线路 URI 不能由其他电话拨入式会议访问号码重复使用。

    
    </div>

8.  在“SIP URI”**** 中，执行下列操作：
    
      - 在文本框中，为此电话拨入式会议访问号码键入唯一的 SIP URI。 SIP URI 显示在不同的位置, 其中包括但不限于呼叫通知消息和以前版本的 Communicator 客户端。
        
        <div>
        

        > [!NOTE]  
        > 同一 SIP URI 不能由其他电话拨入式会议访问号码重复使用。创建访问号码之后，将不能修改 SIP URI。更改 SIP URI 的唯一方法是删除并重新创建访问号码。

        
        </div>
    
      - 在下拉列表框中, 单击支持此拨入访问号码的会议助理应用程序所在的域。

9.  在“池”**** 中，单击运行支持此拨入访问号码的会议助理实例的池。
    
    <div>
    

    > [!NOTE]  
    > 创建访问号码后，如果需要更改池，必须使用  <STRONG>Move-CsApplicationEndpoint</STRONG> cmdlet 或删除并重新创建访问号码。

    
    </div>

10. 在“主要语言”**** 中，单击针对此拨入访问号码播放提示时使用的语言。
    
    <div>
    

    > [!NOTE]  
    > 主要语言是会议助理应答呼叫时使用的语言。支持的语言显示在电话拨入式会议设置网页上的每个访问电话号码旁边。

    
    </div>

11. （可选）在“辅助语言（最多 4 个）”**** 中，单击“添加”****，选择一个或多个要为此拨入访问号码的呼叫者提供支持的其他语言，然后单击“确定”****。
    
    <div>
    

    > [!NOTE]  
    > 最多可以为每个拨入访问号码选择四种辅助语言。用户通过电话拨入加入会议时，在输入会议 ID 之前可以选择一种辅助语言。

    
    </div>

12. 若要为拨入访问号码添加区域, 请在 "**关联区域**" 下, 单击 "**添加**", 单击与此拨入访问号码的拨号计划相关联的一个或多个区域, 然后单击 **"确定"**。

13. 要从拨入访问号码中删除某个区域，请在“关联区域”**** 下，单击要删除的区域，然后单击“删除”****。

14. 单击“**提交**”。

</div>

</div>

<span> </span>

</div>

</div>

</div>

