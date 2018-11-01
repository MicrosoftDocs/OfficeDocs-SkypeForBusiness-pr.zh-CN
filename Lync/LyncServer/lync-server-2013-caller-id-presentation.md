---
title: Lync Server 2013：来电显示
TOCTitle: 来电显示
ms:assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204980(v=OCS.15)
ms:contentKeyID: 49313153
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的来电显示

 

_**上一次修改主题：** 2013-02-22_

使用 Lync Server 2010，可将被呼叫者的电话号码（即呼叫的电话号码）从 E.164 格式转换为 *trunk peer*（即关联的网关、专用交换机 (PBX) 或 SIP 中继）需要的本地拨号格式。为此，必须定义一个或多个转换规则，以便在将请求 URI 路由至中继对等方之前对其执行转换。

Lync Server 2013 引入的选项也可将呼叫者的电话号码（即呼叫者用来呼叫的电话号码）从 E.164 格式转换为中继对等方需要的本地拨号格式。例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。

**使用 Lync Server 控制面板配置呼叫者 ID**

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“语音路由”，然后单击“Trunk 配置”。

4.  在“Trunk 配置”页上，双击一个现有中继（例如，“全局”中继）以显示“编辑 Trunk 配置”对话框。

5.  配置呼叫者 ID 显示：
    
      - 要从 企业语音部署中提供的所有转换规则列表中选择一个或多个规则，请单击“选择”。在“主叫号码转换规则”中，单击要与中继关联的规则，然后单击“确定”。
    
      - 要定义新的转换规则并将其与中继相关联，请单击“新建”。有关定义新规则的详细信息，请参阅部署文档中的[在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md)。
    
      - 要编辑已与中继关联的转换规则，请单击相应的规则名称，然后单击“显示详细信息”。有关详细信息，请参阅部署文档中的[在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md)。
    
      - 要复制现有的转换规则以作为定义新规则的起点，请单击相应的规则名称，再单击“复制”，然后单击“粘贴”。有关详细信息，请参阅[在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md)。
    
      - 要从中继删除某个转换规则，请突出显示相应的规则名称，然后单击“删除”。
    
    > [!WARNING]
    > 如果已在关联的中继对等方上配置了转换规则，则不要将任何转换规则与中继相关联，因为这两种规则可能会发生冲突。

