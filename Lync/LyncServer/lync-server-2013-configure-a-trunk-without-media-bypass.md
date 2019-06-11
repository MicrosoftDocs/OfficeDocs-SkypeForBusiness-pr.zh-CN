---
title: 'Lync Server 2013: 在不使用媒体旁路的情况下配置中继'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a trunk without media bypass
ms:assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425831(v=OCS.15)
ms:contentKeyID: 48183825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e6508fe88a585c22b9936e787be2ee99b8f9b7c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-without-media-bypass-in-lync-server-2013"></a>在 Lync Server 2013 中配置不使用 "媒体旁路" 的主干

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-24_

如果要配置禁用媒体旁路功能的中继，请执行以下步骤。 如果你想要配置支持媒体旁路的主干, 请参阅[在 Lync Server 2013 中使用 "媒体绕过" 配置主干](lync-server-2013-configure-a-trunk-with-media-bypass.md)。

如下所述，中继配置可对应用于已分配此中继配置的中继的一组参数进行分组。特定中继配置的作用域可以是全局中继（针对没有更多特定站点或池配置的所有中继）、站点或者池。池级中继配置用于将特定中继配置的作用域限制为单个中继。

<span id="BKMK_ConfigTrunkGenericSteps"></span>

<div>

## <a name="to-configure-a-trunk-without-media-bypass"></a>配置无媒体旁路功能的中继

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息, 请参阅[在 Lync Server 2013 中委派设置权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“语音路由”****，然后单击“Trunk 配置”****。

4.  在“Trunk 配置”**** 页上，使用以下方法之一配置中继：
    
      - 双击某个现有的中继（例如“全局”**** 中继）以显示“编辑 Trunk 配置”**** 对话框。
    
      - 单击“新建”****，然后为新的中继配置选择范围：
        
          - **网站主干:** 在 "**选择网站**" 中选择此中继配置的网站, 然后单击 **"确定"**。 请注意，如果已经为站点创建了中继配置，则该站点不会显示在“选择站点”**** 中。 此中继配置将应用于站点中的所有中继。
        
          - **池干线:** 在 "**选择服务**" 中选择此中继配置所适用的主干的名称, 然后单击 **"确定"**。 此主干可以是根主干, 也可以是拓扑生成器中定义的任何其他中继。 请注意，如果已经为特定中继创建了中继配置，则该中继不会显示在“选择服务”**** 中。
    
    <div>
    

    > [!NOTE]  
    > 选择中继配置的范围后无法更改该范围。<BR>“名称”<STRONG></STRONG>字段会使用中继配置的关联站点或服务的名称进行预填充，且不能更改。

    
    </div>

5.  选择以下“加密支持级别”**** 选项之一：
    
      - **必需:** 安全实时传输协议 (SRTP) 加密必须用于帮助保护中介服务器与网关或专用分支交换 (PBX) 之间的流量。
    
      - **可选:** 如果服务提供商或设备制造商支持, 则使用 SRTP 加密。
    
      - **不支持:** SRTP 加密不受服务提供商或设备制造商支持, 因此不会使用。

6.  确保已清除“启用媒体旁路”**** 复选框。

7.  如果有已知媒体终结点 (例如, 媒体终结的公共交换电话网络 (PSTN) 网关与信号终止相同), 请选中 "**集中媒体处理**" 复选框。 如果中继没有已知的媒体端点，则清除该复选框。

8.  如果中继对等支持接收来自中介服务器的 SIP, 请选中 "**启用发送指向网关**的请求" 复选框。

9.  （可选）若要启用中继间路由，请将 PSTN 用法记录关联到此中继配置并进行相应的配置。 与此干线配置关联的 PSTN 用法将应用于所有传入呼叫, 该主干不是从 Lync 终结点发起的。 若要管理与中继配置关联的 PSTN 用法记录，请使用下列方法之一：
    
      - 若要从您的企业语音部署中可用的所有 PSTN 使用记录列表中选择一个或多个记录, 请单击 "**选择**"。 突出显示要与此中继配置关联的记录，然后单击“确定”****。
    
      - 要删除此中继配置中的某个 PSTN 用法记录，请选择此记录，并单击“删除”****。
    
      - 要定义新的 PSTN 用法记录并将其与此中继配置相关联，请执行以下操作：
        
        1.  单击“新建”****。
        
        2.  在“名称”**** 字段中，为记录指定唯一的描述性名称。
            
            <div>
            

            > [!NOTE]  
            > PSTN 用法记录名称在企业语音部署中必须是唯一的。保存记录后，将无法编辑“名称”<STRONG></STRONG>字段。

            
            </div>
        
        3.  使用下列方法之一为此 PSTN 用法记录关联和配置路由：
            
              - 若要从您的企业语音部署中的所有可用路由列表中选择一个或多个路由, 请单击 "**选择**"。 突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”****。
            
              - 要删除 PSTN 用法记录中的某个路由，请选择此路由，然后单击“删除”****。
            
              - 要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”****。 有关详细信息, 请参阅[在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。
            
              - 要编辑与此 PSTN 用法记录相关联的路由，请选择此路由，然后单击“显示详细信息”****。 有关详细信息, 请参阅[在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)。
        
        4.  单击“**确定**”。
    
      - 要编辑已经与此中继配置相关联的 PSTN 用法记录，请执行以下操作：
        
        1.  选择要编辑的 PSTN 用法记录，然后单击“显示详细信息”****。
        
        2.  使用下列方法之一为此 PSTN 用法记录关联和配置路由：
            
              - 若要从您的企业语音部署中的所有可用路由列表中选择一个或多个路由, 请单击 "**选择**"。 突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”****。
            
              - 要删除 PSTN 用法记录中的某个路由，请选择此路由，然后单击“删除”****。
            
              - 要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”****。 有关详细信息, 请参阅[在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。
            
              - 要编辑与此 PSTN 用法记录相关联的路由，请选择此路由，然后单击“显示详细信息”****。 有关详细信息, 请参阅[在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)。
        
        3.  单击“**确定**”。
    
    <div>
    

    > [!IMPORTANT]  
    > 根据与正在配置的主干相关联的中介服务器对, 关联 PSTN 使用记录非常重要。 如果中介服务器对等是 PSTN 网关或会话边界控制器 (SBC), 强烈建议不要将干线配置与路由到 PSTN 目标或通过 Lync 连接的任何其他下游系统的 PSTN 使用记录相关联服务.

    
    </div>

10. 排列 PSTN 用法记录以获得最佳性能。要更改记录在列表中的位置，请选择 PSTN 用法记录，并单击向上箭头或向下箭头。
    
    <div>
    

    > [!IMPORTANT]  
    > PSTN 用法记录在中继配置中列出的顺序很重要。 Lync 服务器从上到下遍历列表。

    
    </div>

11. 应选择“启用 RTP 闭锁”****，以便为 NAT 或防火墙之后的客户端以及支持闭锁的 SBC 启用媒体旁路。

12. 应选择 "**启用转发呼叫" 历史记录**, 以便为中介服务器的网关对等发送呼叫历史记录信息。

13. **启用前向 P 声明的标识数据**应选中以启用 PAI 呼叫发起人信息, 以便在中介服务器端和网关端 (反之亦然) 之间转发。

14. 应选择“启用出站路由故障转移计时器”**** 以启用快速故障转移。 与此中继关联的网关会在 10 秒内发送通知，告知正在处理出站呼叫。 如果中介服务器未收到此通知, 将会重新路由到另一个主干。 在延迟可能推迟响应时间或网关需要花费 10 秒以上的时间才能响应，应禁用快速故障转移。

15. （可选）为中继关联和配置“主叫号码转换规则”****。 这些转换规则适用于出站呼叫的主叫号码
    
      - 若要从您的企业语音部署中可用的所有翻译规则列表中选择一个或多个规则, 请单击 "**选择**"。 在“选择转换规则”**** 中，单击要与中继关联的规则，然后单击“确定”****。
    
      - 要定义新的转换规则并将其与中继相关联，请单击“新建”****。 有关定义新规则的详细信息, 请参阅部署文档中[Lync Server 2013 中的 "定义翻译规则](lync-server-2013-defining-translation-rules.md)"。
    
      - 要编辑已与中继关联的转换规则，请单击相应的规则名称，然后单击“显示详细信息”****。 有关详细信息, 请参阅部署文档中[Lync Server 2013 中的 "定义翻译规则](lync-server-2013-defining-translation-rules.md)"。
    
      - 要复制现有的转换规则以作为定义新规则的起点，请单击相应的规则名称，再单击“复制”****，然后单击“粘贴”****。 有关详细信息, 请参阅[在 Lync Server 2013 中定义翻译规则](lync-server-2013-defining-translation-rules.md)。
    
      - 要从中继删除某个转换规则，请突出显示相应的规则名称，然后单击“删除”****。
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="安全" alt="security" />安全说明:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>如果已在关联的中继对等方上配置了转换规则，则不要将任何转换规则与中继相关联，因为这两种规则可能会发生冲突。</td>
    </tr>
    </tbody>
    </table>
    
    </div>

16. （可选）为中继关联和配置“被叫号码转换规则”****。这些转换规则适用于出站呼叫的被叫号码。
    
      - 若要从您的企业语音部署中可用的所有翻译规则列表中选择一个或多个规则, 请单击 "**选择**"。 在“选择转换规则”**** 中，单击要与中继关联的规则，然后单击“确定”****。
    
      - 要定义新的转换规则并将其与中继相关联，请单击“新建”****。 有关定义新规则的详细信息, 请参阅部署文档中[Lync Server 2013 中的 "定义翻译规则](lync-server-2013-defining-translation-rules.md)"。
    
      - 要编辑已与中继关联的转换规则，请单击相应的规则名称，然后单击“显示详细信息”****。 有关详细信息, 请参阅部署文档中[Lync Server 2013 中的 "定义翻译规则](lync-server-2013-defining-translation-rules.md)"。
    
      - 要复制现有的转换规则以作为定义新规则的起点，请单击相应的规则名称，再单击“复制”****，然后单击“粘贴”****。 有关详细信息, 请参阅[在 Lync Server 2013 中定义翻译规则](lync-server-2013-defining-translation-rules.md)。
    
      - 要从中继删除某个转换规则，请突出显示相应的规则名称，然后单击“删除”****。
    
    <div>
    

    > [!WARNING]  
    > 如果已在关联的中继对等方上配置了转换规则，则不要将任何转换规则与中继相关联，因为这两种规则可能会发生冲突。

    
    </div>

17. 确保中继的转换规则按正确的顺序排列。要更改规则在列表中的位置，请突出显示相应的规则名称，然后单击向上箭头或向下箭头。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync 服务器从上到下遍历翻译规则列表, 并使用与所拨号码匹配的第一个规则。 如果要配置中继以使拨打号码可以匹配多个转换规则，则确保限制较严格的规则排在限制较宽松的规则上方。 例如，如果具有与任何 11 位数字相匹配的转换规则和只与以 +1425 开头的 11 位数字相匹配的转换规则，则确保与任何 11 位数字相匹配的规则排在更加严格的规则<EM>下方</EM>。

    
    </div>

18. 完成中继的配置后，单击“确定”****。

19. 在“Trunk 配置”**** 页上，单击“提交”****，然后单击“全部提交”****。
    
    <div>
    

    > [!NOTE]  
    > 任何时候创建或修改中继配置，都必须运行“全部提交”<STRONG></STRONG>命令以发布配置更改。 有关详细信息, 请参阅操作文档中的<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中的 "发布待处理的语音路由配置更改"</A> 。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

