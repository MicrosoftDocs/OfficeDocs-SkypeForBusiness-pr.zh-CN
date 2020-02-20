---
title: Lync Server 2013：配置不使用媒体旁路的中继
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk without media bypass
ms:assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425831(v=OCS.15)
ms:contentKeyID: 48183825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e3b8f0c14ca916c7a4920a4399df441fb61bc48
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146605"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-without-media-bypass-in-lync-server-2013"></a>在 Lync Server 2013 中配置无媒体旁路功能的中继

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-24_

如果要配置禁用媒体旁路功能的中继，请执行以下步骤。 如果要配置启用了媒体旁路的中继，请参阅[在 Lync Server 2013 中配置具有媒体旁路的中继](lync-server-2013-configure-a-trunk-with-media-bypass.md)。

如下所述，中继配置可对应用于已分配此中继配置的中继的一组参数进行分组。特定中继配置的作用域可以是全局中继（针对没有更多特定站点或池配置的所有中继）、站点或者池。池级中继配置用于将特定中继配置的作用域限制为单个中继。

<span id="BKMK_ConfigTrunkGenericSteps"></span>

<div>

## <a name="to-configure-a-trunk-without-media-bypass"></a>配置无媒体旁路功能的中继

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“语音路由”****，然后单击“Trunk 配置”****。

4.  在“Trunk 配置”**** 页上，使用以下方法之一配置中继：
    
      - 双击某个现有的中继（例如“全局”**** 中继）以显示“编辑 Trunk 配置”**** 对话框。
    
      - 单击“新建”****，然后为新的中继配置选择作用域：
        
          - **站点中继：** 在 "**选择网站**" 中选择此中继配置的网站，然后单击 **"确定"**。 请注意，如果已经为站点创建了中继配置，则该站点不会显示在“选择站点”**** 中。 此中继配置将应用于站点中的所有中继。
        
          - **池中继：** 在 "**选择服务**" 中选择要应用此中继配置的中继的名称，然后单击 **"确定"**。 此中继可以是根中继，也可以是拓扑生成器中定义的任何其他中继。 请注意，如果已经为特定中继创建了中继配置，则该中继不会显示在“选择服务”**** 中。
    
    <div>
    

    > [!NOTE]  
    > 选择中继配置的作用域后，无法对其进行更改。<BR>“名称”<STRONG></STRONG>字段将使用中继配置的关联站点或服务的名称进行预填充，且不能更改。

    
    </div>

5.  选择以下“加密支持级别”**** 选项之一：
    
      - **必需：** 安全实时传输协议（SRTP）加密必须用于帮助保护中介服务器与网关或专用交换机（PBX）之间的通信。
    
      - **可选：** 如果服务提供商或设备制造商支持，则使用 SRTP 加密。
    
      - **不支持：** SRTP 加密不受服务提供商或设备制造商支持，因此不会使用。

6.  确保已清除“启用媒体旁路”**** 复选框。

7.  如果存在一个已知的媒体端点（例如公用电话交换网 (PSTN) 网关，其中媒体终端与信号终端具有相同的 IP），则选中“集中式媒体处理”**** 复选框。如果中继没有已知的媒体端点，则清除该复选框。

8.  如果中继对等方支持接收来自中介服务器的 SIP 引用请求，请选中 "**启用发送引用到网关"** 复选框。

9.  （可选）若要启用中继间路由，请对此中继配置关联和配置 PSTN 用法记录。与此中继配置关联的 PSTN 用法将通过源自 Lync 终结点以外终结点的中继应用于所有传入呼叫。若要管理与中继配置关联的 PSTN 用法记录，请使用以下方法之一：
    
      - 若要从企业语音部署中提供的所有 PSTN 用法记录列表中选择一个或多个记录，请单击 "**选择**"。 突出显示要与此中继配置关联的记录，然后单击“确定”****。
    
      - 要删除此中继配置中的某个 PSTN 用法记录，请选择相应的记录，然后单击“删除”****。
    
      - 要定义新的 PSTN 用法记录并将其与此中继配置相关联，请执行以下操作：
        
        1.  单击“新建”****。
        
        2.  在“名称”**** 字段中，指定记录的唯一描述性名称。
            
            <div>
            

            > [!NOTE]  
            > PSTN 用法记录名称在企业语音部署中必须是唯一的。保存记录后，将无法编辑“名称”<STRONG></STRONG>字段。

            
            </div>
        
        3.  使用以下方法之一为此 PSTN 用法记录关联和配置路由：
            
              - 若要从企业语音部署中的所有可用路由列表中选择一个或多个路由，请单击 "**选择**"。 突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”****。
            
              - 要删除 PSTN 用法记录中的某个路由，请选择相应的路由，然后单击“删除”****。
            
              - 要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”****。 有关详细信息，请参阅[在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。
            
              - 要编辑与此 PSTN 用法记录相关联的路由，请选择相应的路由，然后单击“显示详细信息”****。 有关详细信息，请参阅[在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)。
        
        4.  单击“确定”****。
    
      - 要编辑已经与此中继配置相关联的 PSTN 用法记录，请执行以下操作：
        
        1.  选择要编辑的 PSTN 用法记录，然后单击“显示详细信息”****。
        
        2.  使用以下方法之一为此 PSTN 用法记录关联和配置路由：
            
              - 若要从企业语音部署中的所有可用路由列表中选择一个或多个路由，请单击 "**选择**"。 突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”****。
            
              - 要删除 PSTN 用法记录中的某个路由，请选择相应的路由，然后单击“删除”****。
            
              - 要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”****。 有关详细信息，请参阅[在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。
            
              - 要编辑与此 PSTN 用法记录相关联的路由，请选择相应的路由，然后单击“显示详细信息”****。 有关详细信息，请参阅[在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)。
        
        3.  单击“确定”。
    
    <div>
    

    > [!IMPORTANT]  
    > 根据与要配置的中继关联的中介服务器对，关联 PSTN 用法记录非常重要。 如果中介服务器对等是 PSTN 网关或会话边界控制器（SBC），强烈建议不要将中继配置与路由到 PSTN 目标或通过 Lync 连接的任何其他下游系统的 PSTN 用法记录相关联。服务器主板.

    
    </div>

10. 排列 PSTN 用法记录可获得最佳性能。要更改记录在列表中的位置，请选择 PSTN 用法记录，然后单击向上或向下箭头。
    
    <div>
    

    > [!IMPORTANT]  
    > PSTN 用法记录在中继配置中的列出顺序十分重要。 Lync Server 从上到下遍历列表。

    
    </div>

11. 应选择“启用 RTP 闭锁”****，以便为 NAT 或防火墙之后的客户端以及支持闭锁的 SBC 启用媒体旁路。

12. 应选择 "**启用转接呼叫历史记录**"，以允许向中介服务器的网关对等方发送呼叫历史记录信息。

13. 应选择 "**启用前向 P 声明标识数据**"，以便在中介服务器端和网关端（反之亦然）（如果存在）之间将 PAI 调用发起人信息转发。

14. 应选择“启用出站路由故障转移计时器”**** 以支持快速故障转移。 与此中继关联的网关可以在 10 秒内发出正在处理出站呼叫的通知。 如果中介服务器未收到此通知，则将重新路由到另一个中继。 在延迟设置可能延迟响应时间或网关需要 10 秒以上时间进行响应的网络中，应禁用快速故障转移。

15. （可选）关联和配置中继的“呼叫号码转换规则”****。 这些转换规则适用于出站呼叫的呼叫号码
    
      - 若要从企业语音部署中可用的所有转换规则列表中选择一个或多个规则，请单击 "**选择**"。 在“选择转换规则”**** 中，单击要与中继关联的规则，然后单击“确定”****。
    
      - 要定义新的转换规则并将其与中继关联，请单击“新建”****。 有关定义新规则的详细信息，请参阅部署文档中的[在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md)。
    
      - 要编辑已经与中继关联的转换规则，请单击相应的规则名称，然后单击“显示详细信息”****。 有关详细信息，请参阅部署文档中的[在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md)。
    
      - 要复制现有的转换规则以作为定义新规则的起点，请单击相应的规则名称，再单击“复制”****，然后单击“粘贴”****。 有关详细信息，请参阅[在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md)。
    
      - 要从中继中删除某个转换规则，请突出显示相应的规则名称，然后单击“删除”****。
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="保护" alt="security" />安全说明：</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>如果已在关联的中继对等方上配置了转换规则，则不要将任何转换规则与中继相关联，因为这两种规则可能会发生冲突。</td>
    </tr>
    </tbody>
    </table>
    
    </div>

16. （可选）关联和配置中继的“已呼叫号码转换规则”****。这些转换规则适用于出站呼叫中的已呼叫号码。
    
      - 若要从企业语音部署中可用的所有转换规则列表中选择一个或多个规则，请单击 "**选择**"。 在“选择转换规则”**** 中，单击要与中继关联的规则，然后单击“确定”****。
    
      - 要定义新的转换规则并将其与中继关联，请单击“新建”****。 有关定义新规则的详细信息，请参阅部署文档中的[在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md)。
    
      - 要编辑已经与中继关联的转换规则，请单击相应的规则名称，然后单击“显示详细信息”****。 有关详细信息，请参阅部署文档中的[在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md)。
    
      - 要复制现有的转换规则以作为定义新规则的起点，请单击相应的规则名称，再单击“复制”****，然后单击“粘贴”****。 有关详细信息，请参阅[在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md)。
    
      - 要从中继中删除某个转换规则，请突出显示相应的规则名称，然后单击“删除”****。
    
    <div>
    

    > [!WARNING]  
    > 如果已在关联的中继对等方上配置了转换规则，则不要将任何转换规则与中继相关联，因为这两种规则可能会发生冲突。

    
    </div>

17. 请确保该中继的转换规则按正确的顺序排列。 要更改规则在列表中的位置，请突出显示相应的规则名称，然后单击向上或向下箭头。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 从上到下遍历转换规则列表，并使用第一个与拨打的号码相匹配的规则。 如果要配置中继以使拨打号码可以匹配多个转换规则，请确保限制较严格的规则排在限制较宽松的规则上方。 例如，如果具有与任何 11 位数字相匹配的转换规则和只与以 +1425 开头的 11 位数字相匹配的转换规则，请确保与任何 11 位数字相匹配的规则排在更加严格的规则<EM>下方</EM>。

    
    </div>

18. 完成中继的配置后，单击“确定”****。

19. 在“Trunk 配置”**** 页上，单击“提交”****，然后单击“全部提交”****。
    
    <div>
    

    > [!NOTE]  
    > 任何时候创建或修改中继配置，都必须运行“全部提交”<STRONG></STRONG>命令以发布配置更改。 有关详细信息，请参阅操作文档中的在<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中发布待处理的语音路由配置的更改</A>。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中配置具有媒体旁路功能的中继](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

