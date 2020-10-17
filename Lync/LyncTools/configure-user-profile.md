---
title: 配置用户配置文件
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure User Profile
ms:assetid: 52713245-e502-4539-a238-66ff1aca26b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945594(v=OCS.15)
ms:contentKeyID: 51541419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63e00301a01920cc836ccc4d227952de4e9a4c78
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505259"
---
# <a name="configure-user-profile"></a>配置用户配置文件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2018-10-11_

Lync Server 2013 应力和性能工具包中包含的工具使您能够创建和配置可用于运行负载模拟的测试用户帐户。 使用 Lync Server 2013 用户创建工具来创建用户。  (有关详细信息，请参阅 [创建用户和联系人](create-users-and-contacts.md)。 ) 创建用户后，使用 Lync Server 2013 加载配置工具配置用户配置文件。

<div>

## <a name="running-the-lync-server-2013-load-configuration-tool"></a>运行 Lync Server 2013 加载配置工具

若要配置用户配置文件，请运行 Lync Server 2013 加载配置工具 ( # A0) 并填写每个选项卡。 UserProfileGenerator.exe 为需要运行模拟的每台客户端计算机生成一个目录。 每个客户端目录还附带一个脚本来启动 Lync Server 2013 压力和性能工具 ( # A0) 的所有实例。

<div>


> [!IMPORTANT]  
> 在 UserProfileGenerator 中指定的用户特定值必须与在 "Lync Server 2013 用户创建" 工具中指定的值匹配， (UserProvisioningTool) 为池。



</div>

在 "Lync Server 2013 加载配置" 工具的每个选项卡上填写字段，如以下各节所述。

<div>

## <a name="common-configuration"></a>常见配置

下图显示了 Lync Server 2013 加载配置工具的 " **常见配置** " 选项卡。 按照以下步骤中所述，填写 " **通用配置** " 选项卡的字段。

!["常见配置" 选项卡。](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg ""常见配置" 选项卡。")

1.  在 " **可用计算机数**" 中，键入或单击要用于运行 LyncPerfTool.exe 的计算机数。 我们建议您对每个要模拟的4500用户拥有一台计算机。 如果您降低负载级别或仅使用可用功能的子集，该数字可能会有所不同。  (负载级别在 " **常规方案** " 选项卡上设置。 ) 

2.  在 " **用户名的前缀**" 中，键入用户用户名的前缀。 若要登录，统一资源标识符 (URI) 将为： UserPrefix \[ User Start Index ... (用户数-1) \] @User Domain。

3.  在 " **所有用户的密码**" 中，输入用于创建用户的密码。 如果将此字段留空，将使用用户名作为密码。

4.  在 " **用户启动索引**" 中，单击或键入要配置的第一个用户的索引。 您可以为不同的负载类型或级别配置不同的范围，但必须针对要配置的范围运行一次 UserProfileGenerator.exe。

5.  在 " **用户数**" 中，单击或键入要配置的用户总数。

6.  在 " **用户域**" 中，键入用于 SIP URI 的域。 这用于构造每个用户登录到 Lync Server 2013 前端服务器或 Standard Edition server 的 SIP URI。 它可以不同于帐户域。

7.  在 " **帐户域**" 中，键入 Active Directory 域服务域登录。

8.  输入您希望该工具在所有终结点/用户中为其登录的每 **秒 (每个实例) ** 的并发终结点的最大数量。 建议的速率为 \< = 每秒 2/标准 SKU FE。

9.  在 " **访问代理服务器" 或 "池 FQDN**" 中，键入您希望客户端连接到的服务器的完全限定的域名 (FQDN) 。 如果用户在外部登录，请指定访问代理服务器。 如果用户是内部用户，请指定其池或 Standard Edition server 的 FQDN。

10. 在 " **端口**" 中，单击或键入您希望用户用于 SIP 的端口 (默认值为 5061) 。

对于 "外部网络服务器设置"，请指定 **访问代理服务器或池 FQDN** 和 **端口**。 这些设置仅用于外部终结点负载模拟。

</div>

<div>

## <a name="general-scenarios"></a>常规方案

下图显示了 Lync Server 2013 加载配置工具的 " **常规方案** " 选项卡。

为要运行的每个常规方案配置加载级别和参数，或保持禁用状态。

!["常规方案" 选项卡。](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg ""常规方案" 选项卡。")

1.  在包含对等和会议的 **即时消息**中，为加载级别指定适当的值。
    
    <div>
    

    > [!NOTE]  
    > 所有字段的负载级别值 (除 Location 信息服务) <STRONG>禁用</STRONG>、 <STRONG>低</STRONG>、 <STRONG>中</STRONG>、 <STRONG>高</STRONG>和 <STRONG>自定义</STRONG>之外。 如果选择 "低"、"中"、"高" 或 "自定义"，则将为每个模态和客户端生成配置。 "高" 将导致为服务器生成最大支持的负载，"中" 对应于60% 的负载，"低" 对应于负载的30%。

    
    </div>

2.  在仅音频会议的 **音频会议**中，为负载级别指定适当的值。 对等呼叫在本主题后面的 "语音方案" 一节中介绍。 若要启用 "可查看"，请打开该模态的 " **高级** " 选项卡。

3.  在 " **应用程序共享**" 中，为加载级别指定适当的值。

4.  在包含数据会议的 **数据协作**中，为负载级别指定适当的值。

5.  在 " **通讯组列表展开**" 中，为 "加载级别" 指定适当的值。 您还必须单击 " **高级** " 按钮，然后使用在 Lync Server 用户创建工具的 " **通讯组列表** " 选项卡上配置的值相同的字段 ( # A0) 进行填充。 有关这些字段的详细信息，请参阅 [创建用户和联系人](create-users-and-contacts.md)

6.  在通讯 **簿 Web 查询**（即通讯簿查找服务 (不是通讯簿文件下载) 中，为 "加载级别" 指定适当的值。 若要启用通讯簿下载，请单击相应的 " **高级** " 按钮，然后将 **EnableABSDownload** 设置为 true。

7.  在 " **响应组服务**" 中，为 "加载级别" 指定适当的值。 您还必须单击相应的 " **高级** " 按钮，然后指定在设置响应组服务代理时已创建的响应组的 uri。 您必须指定至少一个响应组。 使用分号分隔多个响应组。 将 RGSUriSuffixStartIndex 和 RGSUriSuffixEndIndex 更新为实际值。

8.  在 " **位置信息服务**" 中，为 "加载级别" 选择适当的值。 必须 **启用** 或 **禁用**Location 信息服务的负载级别。

<div>


> [!NOTE]  
> 每个方案都有一个位于其旁边的 " <STRONG>高级</STRONG> " 按钮，以及一组启用方案变体的复选框。 <STRONG>临时方式生成</STRONG> 将在一小时内创建的会议的模拟。 <STRONG>大型</STRONG> 会议意味着将模拟大型会议方案。 <STRONG>外部</STRONG> 方式也模拟外部用户。<BR>这些按钮和复选框允许访问特定于每个方案的值，这些值将更改 Lync Server 2013 压力和性能工具 (LyncPerfTool) 并使自定义成为可能。 对于 " <STRONG>常规方案</STRONG> " 选项卡上的每个方案 (除 Location 信息服务) 之外，如果 Load Level 的值是 <STRONG>Custom</STRONG>，则将使用 " <STRONG>高级</STRONG> " 对话框中对应的字段计算会话速率。 字段名称不同，具体取决于方案，但字段说明将声明 "注意：仅在从下拉菜单中选择自定义项时，才使用此号码。" 通常情况下， <STRONG>高</STRONG>、 <STRONG>中</STRONG>和 <STRONG>低</STRONG> 值将通过与所有方案之间的平衡的用户模型来更改每个模态的会话速率。 如果由于预期使用率不同而需要更改每个模态的负载级别，建议使用 <STRONG>自定义</STRONG> 对话速率。<BR>



</div>

</div>

<div>

## <a name="voice-scenarios"></a>语音方案

下图显示了 Lync Server 2013 加载配置工具的 " **语音方案** " 选项卡。

使用 " **语音方案** " 选项卡配置所有与语音相关的方案。

!["语音方案" 选项卡。](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg ""语音方案" 选项卡。")

1.  在 **VoIP**中，单击 " **高级** " 按钮，然后为 " **PhoneAreaCode** " 和 " **LocationProfile** " ("拨号计划) " 字段提供值。 此外，还必须为 **加载级别**指定值。 如果启用了 **VoIP** 和 **UC/PSTN 网关** 的负载级别，则将始终生成一个公共交换电话网络 (PSTN) 到统一通信 (UC) 配置文件将模拟外部调用。

2.  在 **UC/PSTN 网关上**，为加载级别指定值。 如果选择 "**禁用**" 以外的加载级别，则必须通过单击 "中介服务器" 和 "PSTN" 下的 "**添加**" 按钮来为**PSTN 区域代码**提供一个值。 验证是否为该区号配置了路由。
    
    <div>
    

    > [!NOTE]  
    > 您可以使用 Lync Server 控制面板或 Lync Server 命令行管理程序验证语音路由配置。

    
    </div>

3.  在 **会议助理**中，为加载级别指定值。 选择非 **禁用**) 之外的加载级别将启用 " **电话号码** " 字段 (。 输入要使用的自动助理的电话号码。 此外，单击 " **高级** " 按钮，然后为 " **LocationProfile** " 域指定一个值。

4.  在 " **呼叫寄存服务**" 中，为 **负载级别**指定适当的值。

5.  在 **中介服务器和 PSTN**中，对于要使用的每个中介服务器，您必须具有单独的 PSTN 模拟器。 确定要用作模拟器的客户端之后，您需要将中介服务器配置为在您配置的 PSTN 模拟器端口上将呼叫路由到该计算机。 单击 " **添加** " 以配置中介服务器的值。

<div>


> [!NOTE]  
> 每个方案都有一个位于它旁边的 " <STRONG>高级</STRONG> " 按钮。 这些按钮允许访问特定于每个方案的值，这些值将更改 Lync Server 2013 压力和性能工具 (LyncPerfTool) 的行为，并启用自定义。 对于 " <STRONG>语音方案</STRONG> " 选项卡上的每个方案，如果 " <STRONG>加载级别</STRONG> " 的值是 " <STRONG>自定义</STRONG>"，则使用 " <STRONG>高级</STRONG> " 对话框中对应的字段计算会话速率。 字段名称不同，具体取决于方案，但字段说明将声明 "注意：仅在从下拉菜单中选择自定义项时，才使用此号码。"



</div>

</div>

<div>

## <a name="reach"></a>到达

在 Lync Server 2013 中，通过在 Front-End 服务器上安装的统一通信 Web API (UCWA) 服务器支持会议方案，达到新的体验。 下图显示了 Lync Server 2013 加载配置工具的 " **访问** " 选项卡。

使用 "转至 **" 选项卡** 可配置所有与相关的应用场景。

!["访问" 选项卡。](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg ""访问" 选项卡。")

1.  单击 "**常规到达设置**" 旁的 "**高级**" 按钮。 将字段 **UcwaTargetServerUrl** 设置为控制器池虚拟 IP (VIP) 或前端池 VIP。

2.  在 " **应用程序共享**"、" **数据协作**" 和 " **IM**" 中，为 " **负载级别**" 选择适当的值。

<div>


> [!NOTE]  
> 每个方案都有一个位于它旁边的 " <STRONG>高级</STRONG> " 按钮。 这些按钮允许访问特定于每个方案的值，这些值将更改 Lync Server 2013 压力和性能工具 (LyncPerfTool) 的行为，并启用自定义。 对于每个访问方案，如果 <STRONG>加载级别</STRONG> 是 <STRONG>自定义</STRONG>的，则使用 <STRONG>ConversationsPerHour</STRONG> 字段中指定的值，而不是默认值



</div>

使用 " **移动** " 选项卡配置所有移动性相关的方案。

![移动选项卡。](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "移动选项卡。")

1.  单击**移动 (UCWA) **旁边的 "**高级**" 按钮。 将字段 **UcwaTargetServerUrl** 设置为控制器池虚拟 IP (VIP) 或前端池 VIP。

2.  在 **状态和 P2P 即时消息 \\ 音频**中，选择适当的 **负载级别** 值以启用移动方案模拟。

<div>


> [!NOTE]  
> 每个方案都有一个位于它旁边的 " <STRONG>高级</STRONG> " 按钮。 这些按钮允许访问特定于每个方案的值，这些值将更改 Lync Server 2013 压力和性能工具 (LyncPerfTool) 的行为，并启用自定义。 对于每个访问方案，如果 <STRONG>加载级别</STRONG> 是 <STRONG>自定义</STRONG>的，则使用 <STRONG>ConversationsPerHour</STRONG> 字段中指定的值，而不是默认值。



</div>

</div>

<div>

## <a name="summary"></a>摘要

下图显示了 Lync Server 2013 加载配置工具的 " **摘要** " 选项卡。

![摘要 "选项卡。](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "摘要 "选项卡。")

" **摘要** " 选项卡指示要对每个方案使用的用户。 通过选中 " **启用自定义用户范围生成** " 复选框，然后双击表中具有您要自定义的 **用户区域** 的方案，可以手动配置用户号码范围。 检查 ( # A0) 在启动时添加登录延迟，以便在生成的批处理文件中包含延迟以与登录速率相对应。 这有助于在登录大量用户时防止服务器超载。 单击 " **生成文件**"，然后选择要在其中生成配置的文件夹。 成功创建文件后，将显示与下图类似的对话框。

![确认已创建文件。](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "确认已创建文件。")

</div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[创建用户和联系人](create-users-and-contacts.md)  
</div>
</div>
<span></span>
</div>
</div>
</div>
