---
title: Lync Server 2013：创建语音策略和配置 PSTN 用法记录
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice policy and configure PSTN usage records
ms:assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399027(v=OCS.15)
ms:contentKeyID: 48185693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7596a9efb95436452144cf2cf0cacc53cd89a9be
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191755"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a>在 Lync Server 2013 中创建语音策略和配置 PSTN 用法记录

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

如果要创建新的语音策略，请执行以下步骤。 如果要编辑语音策略，请参阅[在 Lync Server 2013 中修改语音策略和配置 PSTN 用法记录中](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)的过程。

<div>


> [!NOTE]  
> 每个语音策略必须至少有一个关联的公用电话交换网（PSTN）用法记录。 若要查看企业语音部署中提供的所有 PSTN 用法记录的列表并查看其属性，请参阅<A href="lync-server-2013-view-pstn-usage-records.md">在 Lync Server 2013 中查看 pstn 用法记录</A>。



</div>

<div>

## <a name="to-create-a-voice-policy"></a>创建语音策略

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击 "**语音路由**"，然后单击 "**语音策略**"。

4.  在 "**语音策略**" 页上，单击 "**新建**"，然后选择新策略的范围：
    
      - **网站策略**适用于整个网站，但分配给用户策略的任何用户或组除外。 如果为策略作用域选择 "站点"，请从 "**选择站点**" 对话框中选择站点。 如果已为网站创建了语音策略，则该网站不会显示在 "**选择网站**" 对话框中。
    
      - **用户策略**可应用于指定的用户或组。

5.  如果语音策略作用域为 User，请在 "**名称**" 字段中为策略输入一个描述性名称。
    
    <div>
    

    > [!NOTE]  
    > 如果语音策略作用域为 "网站"，则<STRONG>新语音策略</STRONG>中的 "<STRONG>名称</STRONG>" 字段将预填充网站名称，且不能更改。

    
    </div>

6.  Optional输入语音策略的其他描述性信息。

7.  选中或清除以下复选框以启用或禁用此语音策略的每个**呼叫功能**：
    
      - **语音邮件规避**可在配置了同时响铃且移动电话已关机、没电或接收不到信号时，阻止将呼叫立即路由到用户移动电话的语音邮件系统。
        
        <div>
        

        > [!NOTE]  
        > 此功能只能通过 Lync Server 命令行管理程序进行配置

        
        </div>
    
      - 通过**呼叫转接**，用户可以将呼叫转接到其他电话或客户端设备。 Lync Server 2013 提供了范围更广的呼叫转发配置选项。 例如，如果组织不允许将传入呼叫外部转接到 PSTN，则管理员可应用特定语音策略来部署此限制。 默认为启用。
    
      - 通过**委派**，用户可以指定其他用户代表他们发送和接收呼叫。 在 Lync Server 2013 中，代理可以配置同时响铃，使传入呼叫他或她的经理能够拨打所有代理同时拨打的目标。 这为代理提供了极大地灵活性以响应定向至管理员的呼叫。 默认为启用。
    
      - 通过**呼叫转移**，用户可以将呼叫转移到其他用户。 默认为启用。
    
      - 通过**呼叫寄存**，用户可以寄存呼叫处于保留状态，然后从其他电话或客户端接听呼叫。 默认情况下处于禁用状态。
    
      - **同时响铃**使传入呼叫可以在其他电话（如手机）或其他终结点设备上响铃。 Lync Server 2013 为同时响铃提供了更为广泛的配置选项。 默认为启用。
    
      - 通过**团队呼叫**，指定团队中的用户可以为团队中的其他成员应答呼叫。默认为启用。
    
      - 如果 WAN 拥堵或不可用，通过 **PSTN 重新路由**，可以在公用电话交换网 (PSTN) 上重新路由分配有此策略的用户向其他企业用户发出的呼叫。默认为启用。
    
      - 通过**带宽策略覆盖**，管理员可以覆盖特定用户的呼叫允许控制策略决策。 默认为禁用。
        
        <div>
        

        > [!NOTE]  
        > 只能覆盖向用户发出的传入呼叫的策略，而不能覆盖由用户发出的传出呼叫的策略。 建立会话后，将准确记录带宽消耗。 应谨慎使用此设置，应为适当的呼叫允许控制决定预留此设置。

        
        </div>
    
      - 通过**恶意呼叫跟踪**，用户可以通过使用客户端 UI 报告恶意呼叫（如炸弹威胁），后者又对呼叫详细信息记录（cdr）中的呼叫进行了标记。 默认情况下处于禁用状态。

8.  要为此语音策略关联和配置 PSTN 用法记录，请执行以下任意操作：
    
      - 要从企业语音部署中提供的所有 PSTN 用法记录列表中选择一个或多个记录，请单击“选择”****。突出显示要与此语音策略关联的记录，然后单击“确定”****。
    
      - 要删除此语音策略中的某个 PSTN 用法记录，请突出显示相应的记录，然后单击“删除”****。
    
      - 要定义新的 PSTN 用法记录并将其与此语音策略相关联，请执行以下操作：
        
        1.  单击“新建”****。
        
        2.  在“名称”**** 字段中，输入记录的唯一描述性名称。 例如，您可能希望为位于 Redmond 的全职员工创建名为**redmond**的 PSTN 用法记录，并为临时员工创建另一个已命名的**RedmondTemps** 。
            
            <div>
            

            > [!NOTE]  
            > PSTN 用法记录名称在企业语音部署中必须是唯一的。保存记录后，将无法编辑“名称”<STRONG></STRONG>字段。

            
            </div>
        
        3.  使用以下任意方法为此 PSTN 用法记录关联和配置路由：
            
              - 要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”****，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”****。
            
              - 若要从 PSTN 用法记录中删除路由，请突出显示该路由，然后单击 "**删除**"。
            
              - 要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”****。 有关详细信息，请参阅[在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。
            
              - 要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”****。 有关详细信息，请参阅[在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)。
        
        4.  单击“确定”。
    
      - 要编辑已经与此语音策略相关联的 PSTN 用法记录，请执行以下操作：
        
        1.  突出显示要编辑的 PSTN 用法记录，然后单击 "**显示详细信息**"。
        
        2.  使用以下任意方法为此 PSTN 用法记录关联和配置路由：
            
              - 要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”****，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”****。
            
              - 若要从此 PSTN 用法记录中删除路由，请突出显示该路由，然后单击 "**删除**"。
            
              - 要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”****。 有关详细信息，请参阅[在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。
            
              - 若要编辑已与此 PSTN 用法记录相关联的路由，请突出显示该路由并单击**显示详细信息**。 有关详细信息，请参阅[在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)。
        
        3.  单击“确定”****。

9.  排列 PSTN 用法记录以获得最佳性能。要更改记录在列表中的位置，请突出显示相应的记录名称，然后单击向上箭头或向下箭头。
    
    <div>
    

    > [!IMPORTANT]  
    > PSTN 用法记录在语音策略中的列出顺序十分重要。 Lync Server 从上到下遍历列表。 建议按使用频率来组织该列表，例如：RedmondLocal、RedmondLongDist、RedmondInternational 和 RedmondBackup。

    
    </div>

10. 要为此语音策略中的呼叫转接和同时响铃关联和配置 PSTN 用法记录，请执行以下任一操作：
    
      - 若要对呼叫转接和同时响铃使用与此语音策略相同的 PSTN 用法记录，请从下拉菜单中选择“使用呼叫 PSTN 用法进行路由”****。
    
      - 若要仅允许呼叫转接和同时响铃到内部 Lync 用户，请从下拉菜单中选择 "**仅发送到内部 lync 用户**" 的选项。 呼叫将不会转接到外部 PSTN 号码。
    
      - 若要为呼叫转接和同时响铃指定不同的 PSTN 用法记录，而不是用于此语音策略，请从下拉菜单中选择 "**使用自定义 PSTN**使用的选项" 路由。 此选项显示用于选择现有 PSTN 用法记录或创建专用于呼叫转接和同时响铃的新 PSTN 用法记录的控件。
        
          - 要从呼叫转接和同时响铃的 PSTN 用法记录列表中选择一个或多个记录，请单击“选择”****。突出显示要与此呼叫转接和同时响铃策略关联的记录，然后单击“确定”****。
        
          - 要从此呼叫转接和同时响铃策略中删除某个 PSTN 用法记录，请突出显示相应的记录，然后单击“删除”****。
        
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
                
                  - 要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”****。 有关详细信息，请参阅[在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。
                
                  - 要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”****。 有关详细信息，请参阅[在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)。
            
            4.  单击“确定”。
        
          - 要编辑已经与此语音策略相关联的 PSTN 用法记录，请执行以下操作：
            
            1.  突出显示要编辑的 PSTN 用法记录，然后单击 "**显示详细信息**"。
            
            2.  使用以下任意方法为此 PSTN 用法记录关联和配置路由：
                
                  - 要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”****，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”****。
                
                  - 要删除此 PSTN 用法记录中的某个路由，请突出显示相应的路由，然后单击“删除”****。
                
                  - 要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”****。 有关详细信息，请参阅[在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。
                
                  - 要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”****。 有关详细信息，请参阅[在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)。
            
            3.  单击“确定”。

11. （可选）输入一个号码来测试语音策略，然后单击“执行”****。测试结果会显示在“要测试的转换号码”**** 下。
    
    <div>
    

    > [!NOTE]  
    > 您可以保存尚未通过测试的语音策略，并在稍后对其进行重新配置。 有关详细信息，请参阅<A href="lync-server-2013-test-voice-routing.md">在 Lync Server 2013 中测试语音路由</A>。

    
    </div>

12. 单击“确定”****。

13. 在“语音策略”**** 页上，单击“提交”****，然后单击“全部提交”****。
    
    <div>
    

    > [!NOTE]  
    > 无论何时创建或修改语音策略，都必须运行 "<STRONG>全部提交</STRONG>" 命令以发布配置更改。 有关详细信息，请参阅操作文档中的在<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中发布待处理的语音路由配置的更改</A>。

    
    </div>

14. （可选）语音邮件规避检测到用户的手机语音邮件立即应答了一个呼叫，因此将断开至移动电话语音邮件的呼叫。 这将允许此呼叫继续在用户的其他终结点上响铃，以使用户能够应答呼叫。 有关如何配置语音邮件策略的详细信息，请参阅[Lync Server 2013 中的配置语音邮件转义](lync-server-2013-configuring-voice-mail-escape.md)。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中修改语音策略和配置 PSTN 用法记录](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[在 Lync Server 2013 中查看 PSTN 用法记录](lync-server-2013-view-pstn-usage-records.md)  
[在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)  
[在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)  
[在 Lync Server 2013 中发布对语音路由配置所做的挂起更改](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[在 Lync Server 2013 中配置语音邮件转义](lync-server-2013-configuring-voice-mail-escape.md)  


[在 Lync Server 2013 中测试语音路由](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

