---
title: Skype for Business Server：配置具有媒体旁路的中继
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
description: 摘要：配置启用了媒体旁路功能的中继Skype for Business Server。 这将可以最大程度地减少中介服务器的数量，假设 SIP 中继提供商支持中介服务器的数量。
ms.openlocfilehash: f009cc15279cde28b531747adf77a7adf89fa407efaa9a30ff731e37f2f23f0e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54287621"
---
# <a name="skype-for-business-server-configure-a-trunk-with-media-bypass"></a>Skype for Business Server：配置具有媒体旁路的中继

**摘要：** 配置启用了媒体旁路功能的中继Skype for Business Server。 这将可以最大程度地减少中介服务器的数量，假设 SIP 中继提供商支持中介服务器的数量。

按照以下步骤配置启用了媒体旁路功能的中继。 若要配置禁用媒体旁路的中继，请参阅在 Skype for Business Server 中[配置无媒体旁路的中继](configure-trunk-without-media-bypass.md)。

如果希望将部署的中介服务器数目降至最低，媒体绕过非常有用。 有关详细信息，请参阅规划[媒体旁路Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)

我们强烈建议您启用媒体旁路。 但是，在 SIP 中继上启用媒体旁路之前，请确认您的合格 SIP 中继提供商支持媒体旁路，并能够满足成功启用方案的要求。 具体而言，提供商必须具有组织内部网络中服务器的 IP 地址。

> [!NOTE]
> 媒体旁路将不会与 SBC (每个公用电话交换网) IP-PBX 和会话边界控制器 (交互) 。 Microsoft 已与认证合作伙伴一起测试了一组 PSTN 网关和 SDC。 媒体旁路仅在"电话基础结构 for [Skype for Business Server"页上列出的产品和版本](../../../SfbPartnerCertification/certification/infra-gateways.md)受支持。

如下所述中继配置对应用于分配了此中继配置的中继的一组参数进行分组。 特定中继配置的作用域可以是全局中继（针对没有更多特定站点或池配置的所有中继）、站点或者池。 池级中继配置用于将特定中继配置的作用域限制为单个中继。

### <a name="to-configure-a-trunk-with-media-bypass"></a>配置带媒体旁路的中继

1. 打开Skype for Business Server控制面板

2. 在左侧导航栏中，单击“语音路由”，然后单击“Trunk 配置”。

3. 在“Trunk 配置”页上，使用以下方法之一配置中继：

   - 双击某个现有的中继（例如“全局”中继）以显示“编辑 Trunk 配置”对话框。

   - 单击“新建”，然后为新的中继配置选择作用域：

   - **站点中继**：从"选择站点"中选择此中继 **配置的** 站点，然后单击"确定 **"。** 请注意，如果已经为站点创建了中继配置，则该站点不会显示在“选择站点”中。 此中继配置将应用于站点中的所有中继。

   - **池中继**：选择应用此中继配置的中继的名称。 此中继可以是根中继或在拓扑生成器中定义的任何附加中继。 从 **"选择服务"中，** 单击"确定 **"。** 请注意，如果已经为特定中继创建了中继配置，则该中继不会显示在“选择服务”中。

      > [!NOTE]
      > 选择中继配置的作用域后，无法对其进行更改。 >" **名称** "字段会使用中继配置的关联站点或服务的名称预先填充，并且无法更改。

4. 在"支持的最大 **早期对话数"中指定值**。 这是公用电话交换网 (PSTN) 网关、IP-PBX 或 ITSP 会话边界控制器 (SBC) 可以接收的分叉响应的最大数目，这些响应发送到中介服务器。 默认值为 20。

    > [!NOTE]
    > 在更改此值之前，请咨询您的服务提供商或设备制造商，以了解有关所用系统功能的详细信息。

5. 选择以下“加密支持级别”选项之一：

   - **必需**：必须使用安全实时传输协议 (SRTP) 加密以帮助保护中介服务器与网关或专用交换机 (PBX) 之间的通信。

   - **可选**：如果服务提供商或设备制造商支持 SRTP，则使用 SRTP 加密。

   - **不支持**：SRTP 加密不受服务提供商或设备制造商支持，因此不使用。

6. 如果您要绕过中介服务器而通过中继对等方处理媒体，请选中 **“启用媒体绕过”** 复选框。

    > [!IMPORTANT]
    > 为使媒体绕过功能成功发挥作用，PSTN 网关、IP-PBX 或 ITSP 会话边界控制器必须支持某些功能。 有关详细信息，请参阅规划[媒体旁路Skype for Business。](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)

7. 如果存在一个已知的媒体端点（例如 PSTN 网关，其中媒体终端与信号终端具有相同的 IP），则选中 **“集中媒体处理”** 复选框。如果中继没有已知的媒体端点，则清除该复选框。

8. 如果中继对等方支持接收来自中介服务器的 SIP REFER 请求，请选中" **允许向** 网关发送参考"复选框。

    > [!NOTE]
    > 如果禁用此选项而选中 **“启用媒体绕过”** 选项，则需要其他设置。 如果中继对等方不支持接收来自中介服务器的 SIP REFER 请求且启用了媒体绕过，则为了支持媒体绕过的适当条件，还必须运行 **Set-CsTrunkConfiguration** cmdlet 以禁用活动呼叫和保留呼叫的 RTCP。 或者，如果要使转接的呼叫绕过媒体，并且网关不支持 SIP REFER 请求，可以选择"使用第三方 **呼叫** 控制启用参考"。

9. （可选）若要启用中继间路由，请对此中继配置关联和配置 PSTN 用法记录。 与此中继配置关联的 PSTN 用法将应用于通过并非来自 Skype for Business Server 终结点的中继的所有传入呼叫。 若要管理与中继配置关联的 PSTN 用法记录，请使用以下方法之一：

   - 若要从部署中提供的所有 PSTN 用法记录列表中选择一个或多个企业语音，请单击"选择 **"。** 突出显示要与此中继配置关联的记录，然后单击“确定”。

   - 要删除此中继配置中的某个 PSTN 用法记录，请选择相应的记录，然后单击“删除”。

   - 要定义新的 PSTN 用法记录并将其与此中继配置相关联，请执行以下操作：

     a. 单击"新建"。

     b. 在“名称”字段中，指定记录的唯一描述性名称。

     > [!NOTE]
     > PSTN 用法记录名称在企业语音部署中必须是唯一的。保存记录后，将无法编辑“名称”字段。

     c. 使用以下方法之一为此 PSTN 用法记录关联和配置路由：

     - 若要从部署中所有可用路由列表中选择一个或多个路由企业语音，请单击"选择 **"。** 突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”。

     - 要删除 PSTN 用法记录中的某个路由，请选择相应的路由，然后单击“删除”。

   - 要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”。 有关详细信息，请参阅 Create [or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md)。

     - 要编辑与此 PSTN 用法记录相关联的路由，请选择相应的路由，然后单击“显示详细信息”。

     d. 单击“确定”。

     - 要编辑已经与此中继配置相关联的 PSTN 用法记录，请执行以下操作：

       a. 选择要编辑的 PSTN 用法记录，然后单击“显示详细信息”。

       b. 使用以下方法之一为此 PSTN 用法记录关联和配置路由：

   - 若要从部署中所有可用路由列表中选择一个或多个路由企业语音，请单击"选择 **"。** 突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”。

   - 要删除 PSTN 用法记录中的某个路由，请选择相应的路由，然后单击“删除”。

   - 要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”。 有关详细信息，请参阅 Create [or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md)。

   - 要编辑与此 PSTN 用法记录相关联的路由，请选择相应的路由，然后单击“显示详细信息”。

     c. 单击“**确定**”。

     > [!IMPORTANT]
     > 根据与要配置的中继关联的中介服务器对等方关联 PSTN 用法记录非常重要。 如果中介服务器对等方是 PSTN 网关或会话边界控制器 (SBC) ，则强烈建议不要将中继配置与路由到 PSTN 目标或通过 Skype for Business Server 连接的其他下游系统的 PSTN 用法记录关联。

10. 排列 PSTN 用法记录以获得最佳性能。 若要更改记录在列表中的位置，请选择 PSTN 用法记录，然后单击向上或向下箭头。

    > [!IMPORTANT]
    > PSTN 用法记录在中继配置中的列出顺序十分重要。 Skype for Business Server从上到下遍历列表。

11. **应选择"启用 RTP** 闭锁"，为网络地址转换 (NAT) 防火墙和支持闭锁的 SBC 后面的客户端启用旁路媒体。

12. **应选择"** 启用前向呼叫历史记录"以允许将呼叫历史记录信息发送到中介服务器的对等网关。

13. 应选择"启用转发 **P-Asserted-Identity"** 数据，以使 P-Asserted-Identity (PAI) 呼叫发起方信息可以在中介服务器端和网关端 (之间转发，反之亦然) （存在）。

14. 应选择“启用出站路由故障转移计时器”以支持快速故障转移。 与此中继关联的网关可以在 10 秒内发出正在处理出站呼叫的通知。 如果中介服务器未收到此通知，将重新路由到另一个中继。 在延迟设置可能延迟响应时间或网关需要 10 秒以上时间进行响应的网络中，应禁用快速故障转移。

15. （可选）关联和配置中继的“呼叫号码转换规则”。这些转换规则适用于出站呼叫的呼叫号码

    - 若要从您的部署中提供的所有转换规则列表中选择一个或多个企业语音，请单击"选择 **"。** 在“选择转换规则”中，单击要与中继关联的规则，然后单击“确定”。

    - 要定义新的转换规则并将其与中继关联，请单击“新建”。 有关转换规则的详细信息，请参阅 translation [rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)。

    - 要编辑已经与中继关联的转换规则，请单击相应的规则名称，然后单击“显示详细信息”。

    - 要复制现有的转换规则以作为定义新规则的起点，请单击相应的规则名称，再单击“复制”，然后单击“粘贴”。

    - 要从中继中删除某个转换规则，请突出显示相应的规则名称，然后单击“删除”。

    > [!CAUTION]
    > 如果已在关联的中继对等方上配置了转换规则，则不要将任何转换规则与中继相关联，因为这两种规则可能会发生冲突。

16. （可选）关联和配置中继的“已呼叫号码转换规则”。这些转换规则适用于出站呼叫中的已呼叫号码。

    - 若要从您的部署中提供的所有转换规则列表中选择一个或多个企业语音，请单击"选择 **"。** 在“选择转换规则”中，单击要与中继关联的规则，然后单击“确定”。

    - 要定义新的转换规则并将其与中继关联，请单击“新建”。 有关转换规则的详细信息，请参阅 translation [rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)。

    - 要编辑已经与中继关联的转换规则，请单击相应的规则名称，然后单击“显示详细信息”。

    - 要复制现有的转换规则以作为定义新规则的起点，请单击相应的规则名称，再单击“复制”，然后单击“粘贴”。

    - 要从中继中删除某个转换规则，请突出显示相应的规则名称，然后单击“删除”。

    > [!CAUTION]
    > 如果已在关联的中继对等方上配置了转换规则，则不要将任何转换规则与中继相关联，因为这两种规则可能会发生冲突。

17. 确保中继的转换规则按正确的顺序排列。 若要更改规则在列表中的位置，请突出显示规则名称，然后单击向上箭头或向下箭头。

    > [!IMPORTANT]
    > Skype for Business Server从上到下遍历转换规则列表，并使用第一个匹配拨打号码的规则。 如果要配置中继以使拨打号码可以匹配多个转换规则，请确保限制较严格的规则排在限制较宽松的规则上方。 例如，如果包含的转换规则与任意 11 位数字匹配，而转换规则仅与以 +1425 开头的 11 位数字匹配，请确保匹配任意 11 位数字的规则排序在限制较严格的规则下面。 

18. 完成中继的配置后，单击“确定”。

19. 在“Trunk 配置”页上，单击“提交”，然后单击“全部提交”。

    > [!NOTE]
    > 任何时候创建或修改中继配置，都必须运行“全部提交”命令以发布配置更改。 有关详细信息，请参阅操作[文档中](voice-route-config-changes.md)的 Publish pending changes to the voice routing configuration in Skype for Business in the Operations documentation。

配置中继后，通过选择全局媒体旁路选项继续配置媒体旁路，如部署文档中的在 Skype for Business Server[](deploy-media-bypass.md)部署媒体旁路中所述。
## <a name="see-also"></a>另请参阅

[在客户端中配置无媒体旁路Skype for Business Server](configure-trunk-without-media-bypass.md)

[部署媒体旁路Skype for Business Server](deploy-media-bypass.md)

[定义转换规则](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules)

[配置媒体绕过](/previous-versions/office/lync-server-2013/lync-server-2013-configure-media-bypass)