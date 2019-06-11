---
title: 'Lync Server 2013: 修改语音策略和配置 PSTN 使用记录'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify a voice policy and configure PSTN usage records
ms:assetid: 6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398511(v=OCS.15)
ms:contentKeyID: 48184419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb7c4cdc47c0624b3d94d0dc52c527310f803d83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a>在 Lync Server 2013 中修改语音策略和配置 PSTN 使用记录

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

如果要修改语音策略, 请执行以下步骤。 如果要创建新的语音策略, 请参阅[在 Lync Server 2013 中为该过程创建语音策略和配置 PSTN 使用记录](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)。

<div>


> [!NOTE]  
> 如果向某个语音策略分配的用户没有关联的公共交换电话网络 (PSTN) 使用记录, 则用户无法发出出站呼叫。 有关企业语音部署中可用的所有 PSTN 使用记录的列表和查看其属性, 请参阅<A href="lync-server-2013-view-pstn-usage-records.md">在 Lync Server 2013 中查看 pstn 使用情况记录</A>。



</div>

<div>

## <a name="to-modify-a-voice-policy"></a>修改语音策略

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息, 请参阅[在 Lync Server 2013 中委派设置权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“语音路由”****，然后单击“语音策略”****。

4.  在“语音策略”**** 页上，双击某个语音策略名称。
    
    <div>
    

    > [!NOTE]  
    > 作用域和名称是在创建语音策略时设置的，且不能更改。

    
    </div>

5.  （可选）在“编辑语音策略”**** 中，输入语音策略的其他描述性信息。

6.  选中或清除以下复选框以启用或禁用每种“呼叫功能”****：
    
      - 当配置同时响铃，且电话关闭，电池耗尽或超出服务范围时，**语音邮件转义**可阻止立即将呼叫路由到用户的移动电话语音电子邮件系统。
        
        <div>
        

        > [!NOTE]  
        > 此功能只能通过 Lync Server 命令行管理程序进行配置

        
        </div>
    
      - 通过**呼叫转接**，用户可以将呼叫转接到其他电话或客户端设备。 Lync Server 2013 为呼叫转接提供了一系列更广泛的配置选项。 例如，如果组织不允许将传入呼叫外部转接到 PSTN，则管理员可应用特定语音策略来部署此限制。 默认为启用。
    
      - 通过**委派**，用户可以指定其他用户代表他们发送和接收呼叫。 在 Lync Server 2013 中, 代理人可以配置同时拨打的电话, 让他/她的经理拨出所有代理人同时拨打的目标电话。 这会向委派提供极大的灵活性以响应直接传到经理的呼叫。 默认为启用。
    
      - 通过**呼叫转移**，用户可以将呼叫转移到其他用户。默认为启用。
    
      - 通过**呼叫寄存**，用户可以寄存呼叫，将其置于保持状态，然后从其他电话或客户端接听呼叫。默认为禁用。
    
      - **同时响铃**使来电可以在其他电话（例如，移动电话）或其他终结点设备上响铃。 Lync Server 2013 为同时拨打的配置选项提供了明显范围的更广泛的配置选项。 默认为启用。
    
      - 通过**团队呼叫**，指定团队中的用户可以为团队中的其他成员应答呼叫。 默认为启用。
    
      - **PSTN 重新路由**允许向其他企业用户分配此策略的用户发出呼叫, 如果 WAN 拥挤或不可用, 则将其重新路由到公共交换电话网络 (PSTN)。 默认为启用。
    
      - **带宽策略替代**使管理员能够覆盖特定用户的呼叫许可控制 (CAC) 策略决策。 默认情况下处于禁用状态。
        
        <div>
        

        > [!NOTE]  
        > 只能覆盖向用户发出的传入呼叫的策略，而不能覆盖由用户发出的传出呼叫的策略。建立会话后，将准确记录带宽消耗。应慎用此设置。

        
        </div>
    
      - **恶意呼叫跟踪**使用户能够使用客户端 UI 报告恶意呼叫 (如炸弹威胁), 后者又将呼叫详细记录 (CDRs) 中的呼叫标记为。 默认为禁用。

7.  要为此语音策略关联和配置 PSTN 用法记录，请执行以下任意操作：
    
      - 要从企业语音部署中提供的所有 PSTN 用法记录列表中选择一个或多个记录，请单击“选择”****。突出显示要与此语音策略关联的记录，然后单击“确定”****。
    
      - 要删除此语音策略中的某个 PSTN 用法记录，请突出显示相应的记录，然后单击“删除”****。
    
      - 要定义新的 PSTN 用法记录并将其与此语音策略相关联，请执行以下操作：
        
        1.  单击“新建”****。
        
        2.  在“名称”**** 字段中，输入记录的唯一描述性名称。例如，您可能要为 Redmond 的全职员工创建一个名为 **Redmond** 的 PSTN 用法记录，并为临时员工创建另一个名为 **RedmondTemps** 的 PSTN 用法记录。
            
            <div>
            

            > [!NOTE]  
            > PSTN 用法记录名称在企业语音部署中必须是唯一的。保存记录后，将无法编辑“名称”<STRONG></STRONG>字段。

            
            </div>
        
        3.  使用以下任意方法为此 PSTN 用法记录关联和配置路由：
            
              - 要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”****，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”****。
            
              - 要删除 PSTN 用法记录中的某个路由，请突出显示相应的路由，然后单击“删除”****。
            
              - 要定义新路由并将其与此 PSTN 用法记录关联，请单击“新建”****。 有关详细信息, 请参阅[在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。
            
              - 要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”****。 有关详细信息, 请参阅[在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)。
        
        4.  单击“**确定**”。
    
      - 要编辑已经与此语音策略相关联的 PSTN 用法记录，请执行以下操作：
        
        1.  突出显示要编辑的 PSTN 用法记录，然后单击“显示详细信息”****。
        
        2.  使用以下任意方法为此 PSTN 用法记录关联和配置路由：
            
              - 要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”****，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”****。
            
              - 要删除此 PSTN 用法记录中的某个路由，请突出显示相应的路由，然后单击“删除”****。
            
              - 要定义新路由并将其与此 PSTN 用法记录关联，请单击“新建”****。 有关详细信息, 请参阅[在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。
            
              - 要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”****。 有关详细信息, 请参阅[在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)。
        
        3.  单击“**确定**”。

8.  排列 PSTN 用法记录以获得最佳性能。要更改记录在列表中的位置，请突出显示相应的记录名称，然后单击向上箭头或向下箭头。
    
    <div>
    

    > [!NOTE]  
    > PSTN 用法记录在语音策略中的列出顺序十分重要。 Lync 服务器从上到下遍历列表。 建议按使用频率来组织该列表，例如：RedmondLocal、RedmondLongDist、RedmondInternational 和 RedmondBackup。

    
    </div>

9.  要在此语音策略中为呼叫转接和同时响铃关联和配置 PSTN 用法记录，请执行以下任意操作：
    
      - 要作为此语音策略将相同的 PSTN 用法记录用于呼叫转接和同时响铃，请从下拉菜单选择“使用呼叫 PSTN 用法进行路由”****。
    
      - 若要仅允许呼叫转接和同时拨打内部 Lync 用户, 请从下拉菜单中选择 "**仅向内部 lync 用户路由**"。 Calls will not be forwarded to external PSTN numbers.
    
      - 若要为呼叫转接和同时响铃指定与此语音策略所用的 PSTN 用法记录不同的 PSTN 用法记录，请从下拉菜单中选择“使用自定义 PSTN 用法进行路由”****。此选项显示一个控件，此控件专用于为呼叫转接和同时响铃选择现有 PSTN 用法记录或创建新的 PSTN 用法记录。
        
          - 要从用于呼叫转接和同时响铃 PSTN 用法记录列表中选择一个或多个记录，请单击“选择”****。突出显示要与此呼叫转接和同时响铃策略关联的记录，然后单击“确定”****。
        
          - 要从此呼叫转接和同时响铃策略删除 PSTN 用法记录，请突出显示该记录，然后单击“删除”****。
        
          - 要定义新的 PSTN 用法记录并将其与此呼叫转接和同时响铃策略相关联，请执行以下操作：
            
            1.  单击“新建”****。
            
            2.  在“名称”**** 字段中，输入记录的唯一描述性名称。
                
                <div>
                

                > [!NOTE]  
                > PSTN 用法记录名称在企业语音部署中必须是唯一的。保存记录后，将无法编辑“名称”<STRONG></STRONG>字段。

                
                </div>
            
            3.  使用以下任意方法为此 PSTN 用法记录关联和配置路由：
                
                  - 要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”****，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”****。
                
                  - 要删除 PSTN 用法记录中的某个路由，请突出显示相应的路由，然后单击“删除”****。
                
                  - 要定义新路由并将其与此 PSTN 用法记录关联，请单击“新建”****。 有关详细信息, 请参阅[在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。
                
                  - 要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”****。 有关详细信息, 请参阅[在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)。
            
            4.  单击“**确定**”。
        
          - 要编辑已经与此语音策略相关联的 PSTN 用法记录，请执行以下操作：
            
            1.  突出显示要编辑的 PSTN 用法记录，然后单击“显示详细信息”****。
            
            2.  使用以下任意方法为此 PSTN 用法记录关联和配置路由：
                
                  - 要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”****，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”****。
                
                  - 要删除此 PSTN 用法记录中的某个路由，请突出显示相应的路由，然后单击“删除”****。
                
                  - 要定义新路由并将其与此 PSTN 用法记录关联，请单击“新建”****。 有关详细信息, 请参阅[在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。
                
                  - 要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”****。 有关详细信息, 请参阅[在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)。
            
            3.  单击“**确定**”。

10. （可选）输入一个号码来测试语音策略，然后单击“执行”****。测试结果会显示在“要测试的转换号码”**** 下。
    
    <div>
    

    > [!NOTE]  
    > 你可以保存尚未通过测试的语音策略, 然后在稍后重新配置它。 有关详细信息, 请参阅<A href="lync-server-2013-test-voice-routing.md">在 Lync Server 2013 中测试语音路由</A>。

    
    </div>

11. 单击“**确定**”。

12. 在“语音策略”**** 页上，单击“提交”****，然后单击“全部提交”****。
    
    <div>
    

    > [!NOTE]  
    > 只要创建或修改语音策略，就必须运行“全部提交”<STRONG></STRONG>命令以发布配置更改。 有关详细信息, 请参阅操作文档中的<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中的 "发布待处理的语音路由配置更改"</A> 。

    
    </div>

13. （可选）语音邮件规避检测到用户的手机语音邮件立即应答了一个呼叫，因此将断开至移动电话语音邮件的呼叫。 这将允许此呼叫继续在用户的其他终结点上响铃，以使用户能够应答呼叫。 有关如何配置语音邮件策略的详细信息, 请参阅[在 Lync Server 2013 中配置语音邮件转义](lync-server-2013-configuring-voice-mail-escape.md)。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中创建语音策略和配置 PSTN 使用记录](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[在 Lync Server 2013 中查看 PSTN 使用记录](lync-server-2013-view-pstn-usage-records.md)  
[在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)  
[在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)  
[将挂起的更改发布到 Lync Server 2013 中的语音路由配置](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[在 Lync Server 2013 中配置语音邮件转义](lync-server-2013-configuring-voice-mail-escape.md)  


[在 Lync Server 2013 中测试语音路由](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

