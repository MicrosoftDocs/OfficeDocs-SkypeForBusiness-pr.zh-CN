---
title: Lync Server 2013：创建或修改位置策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying a location policy
ms:assetid: 10338418-4da4-42df-b231-f52098c08dae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687971(v=OCS.15)
ms:contentKeyID: 49733557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f87bf9aff433b70bc50b3fcff209ecd14ea268e0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516779"
---
# <a name="creating-or-modifying-a-location-policy-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改位置策略

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

在 Lync Server 2013 中，可以使用位置策略应用与增强的 9-1-1 (E9-1-1) 功能以及用户或联系人的位置设置相关的设置。 位置策略可确定用户是否启用了 E9-1-1，以及在启用了该服务时紧急呼叫的行为。 例如，您可以使用位置策略定义哪些数字构成紧急呼叫（例如，美国的 911）、是否应自动通知企业安全人员以及应如何路由该呼叫。

您可以在 Lync Server 2013 控制面板中的 " **网络配置** " 组中配置位置策略。 从 Lync Server 控制面板中，您可以查看、创建、修改或删除位置策略。 使用本节中的过程可创建或修改位置策略。 有关删除位置策略的详细信息，请参阅 [在 Lync Server 2013 中删除位置策略](lync-server-2013-deleting-a-location-policy.md)。

在 Lync Server 2013 中，可以在位置信息服务中覆盖客户端请求位置更新之间的默认时间长度。 默认值为 4 小时。 使用带 LocationRefreshInterval 参数的 **Set-CsLocationPolicy** cmdlet 可覆盖该默认值。

<div>

## <a name="to-create-a-new-location-policy-in-lync-server-control-panel"></a>在 Lync Server "控制面板" 中创建新位置策略

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“网络配置”****，然后单击“位置策略”****。

4.  在“位置策略”**** 页上，单击“新建”****，然后选择要创建的策略类型：
    
      - 要创建站点策略，请单击“站点策略”****。在“选择站点”**** 中，选择您希望应用此策略的站点，然后单击“确定”****。在“新建位置策略”**** 页上，“范围”**** 字段包含值“站点”****，“名称”**** 字段包含所选站点的名称。您无法修改上述任意字段。站点策略自动应用于指定站点上的所有用户，并且覆盖这些用户的全局策略。
    
      - 要创建用户策略****，请单击“用户策略”****。在“新建位置策略”**** 中，“范围”**** 字段包含值“用户”****。无法修改该值。在“名称”**** 字段中，键入要赋予此策略的名称。用户策略不会自动应用于任何用户。创建用户策略后，必须手动将此策略授予您希望应用此策略的用户或网络站点。

5.  按如下所示填写剩余字段：
    
      - **启用增强的紧急服务**    选中此复选框可为与此策略关联的用户启用 E9-1-1。 启用紧急服务后，Lync Server 客户端将在注册时检索位置信息，并在发出紧急呼叫时包含该信息。
    
      - **位置**    指定下列值之一：
        
          - **必需**    当客户端注册到新位置时，系统将提示用户输入位置信息。 用户可以消除提示，而不输入任何信息。 如果输入了信息，紧急呼叫将首先由紧急服务提供商应答，以验证在路由到公共安全应答点 (PSAP) operator (即911运算符) 之前的位置。
        
          - **不需要**    将不会提示用户输入位置。 在不使用位置信息的情况下进行呼叫时，紧急服务提供商将应答呼叫并要求提供一个位置。
        
          - **免责声明**    此选项与**必需**的相同，只是用户无法在不输入位置信息的情况下取消提示。 用户仍可以完成紧急呼叫，但无需输入信息即可完成任何其他呼叫。 此外，还会向用户显示免责声明文本，以向用户发出警告，指出拒绝输入位置信息的后果。 若要设置免责声明文本，必须使用 Lync Server 命令行管理 **程序运行 new-cslocationpolicy** cmdlet 或带有 EnhancedEmergencyServiceDisclaimer 参数的 **new-cslocationpolicy** cmdlet。 有关详细信息，请参阅 Lync Server 命令行管理程序文档中的 [new-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) 或 [new-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy) 。
            
            <div>
            

            > [!NOTE]  
            > 在 Lync Server 2013 中，可以使用位置策略为不同的区域设置或不同的用户集设置不同的免责声明，这与在 Lync Server 2010 中不同，在这种情况下，您只能为整个组织指定全局免责声明。

            
            </div>
    
      - 仅对紧急**服务使用位置**    由于各种原因，Lync 可以使用位置信息 (例如，通知团队成员的当前位置) 。 选中该复选框可确保位置信息只能用于紧急呼叫。
    
      - **PSTN 用法**    公开交换电话网络 (PSTN) 使用，用于确定将使用此配置文件从客户端路由紧急呼叫的语音路由。 与此使用关联的路由应指向 "紧急呼叫专用" 的 SIP 中继或 "紧急位置标识号" (ELIN) 网关，该号码将紧急呼叫路由到最近的公共安全应答点 (PSAP) 。
    
      - **紧急拨号号码**    为达到紧急服务而拨打的号码。 在美国，该值为“911”。 该字符串必须由 0 到 9 的数字组成，其长度可以为 1 至 10 位数字。
    
      - **紧急拨号掩码**    拨号时要转换为 "紧急拨号号码" 值的号码。 例如，如果在此字段中输入值212，并且 "紧急拨号号码" 字段的值为911，如果用户212拨打电话，则会对911发出呼叫。 这样，就可以拨打备用紧急号码，并且仍然可以呼叫紧急服务 (例如，如果来自具有不同紧急号码的某个国家或地区的人尝试拨打该国家或地区的号码，而不是其当前在) 中的国家或地区号码。 您可以通过使用分号分隔值来定义多个紧急拨号掩码。 例如，212; 414。 该字符串的最大长度为 100 个字符。 每个字符都必须为 0 到 9 的数字。
        
        <div>
        

        > [!IMPORTANT]  
        > 请确保指定的拨号掩码值与呼叫寄存通道范围内的号码不同。 呼叫寄存路由将优先于紧急拨号字符串转换。 要查看现有呼叫寄存通道范围，请单击左侧导航栏中的“语音功能”<STRONG></STRONG>，然后单击“呼叫寄存”<STRONG></STRONG>。 有关详细信息，请参阅 <A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">在 Lync Server 2013 中配置停车呼叫的电话号码扩展</A>。

        
        </div>
    
      - **通知 URI**    发出紧急呼叫时，) 要通知的一个或多个 SIP 统一资源标识符 (Uri。 例如，只要发出紧急呼叫，就会通过即时消息通知公司安全办公室。 如果提供了呼叫者的位置，将在通知中包含该位置。 可以采用逗号分隔列表形式包括多个 SIP URI。 例如，"sip： security@litwareinc .com"，"sip： kmyer@litwareinc .com"。 支持通讯组列表。 该字符串的长度必须介于1到256个字符之间，且必须以前缀 "sip：" 开头。 在 "通知 URI" 字段中单击之前，将显示一个示例。
    
      - **会议 URI**    SIP URI，在此示例中，将 conferenced 的第三方的电话号码，以进行任何紧急呼叫。 例如，在发出紧急呼叫时，公司安全办公室可以接收呼叫，并根据 **会议模式** 字段) 中提供的值 (接听或参与呼叫。 该字符串的长度必须为 1 到 256 个字符，并且必须以前缀 sip: 开头。 在此字段中单击时，将显示一个示例。
    
      - **会议模式**    如果在 "**会议 URI** " 字段中指定一个值，则**会议模式**将确定第三方是否可以参与呼叫或只能接听。 指定以下选项之一：
        
          - **单向**    第三方只能侦听呼叫方和 PSAP 运算符之间的对话。
        
          - **双向**    第三方可以侦听和参与呼叫方和 PSAP 操作员之间的呼叫。

6.  单击“提交”****。
    
    <div>
    

    > [!IMPORTANT]  
    > 创建用户策略时，起初该策略不会应用于任何用户或网络站点。要将此策略应用于某个用户，请单击左侧导航栏中的“用户”<STRONG></STRONG>。查找您希望应用此策略的用户。在“编辑”<STRONG></STRONG>菜单上，单击“显示详细信息”<STRONG></STRONG>。在“编辑 Lync Server 用户”<STRONG></STRONG>页上，从“位置策略”<STRONG></STRONG>下拉列表中选择新的位置策略，然后单击“提交”<STRONG></STRONG>。<BR>要将此策略应用于某个网络站点，请单击左侧导航栏中的“网络配置”<STRONG></STRONG>，然后单击“站点”<STRONG></STRONG>。查找您希望应用此策略的网络站点。在“编辑”<STRONG></STRONG>菜单上，单击“显示详细信息”<STRONG></STRONG>。在“编辑站点”<STRONG></STRONG>中，从“位置策略”<STRONG></STRONG>下拉列表中选择新的位置策略，然后单击“提交”<STRONG></STRONG>。

    
    </div>

</div>

<div>

## <a name="to-modify-a-location-policy-in-lync-server-control-panel"></a>在 Lync Server 控制面板中修改位置策略

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“网络配置”****，然后单击“位置策略”****。

4.  在“位置策略”**** 页上，选择要修改的位置策略。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在“编辑位置策略”**** 页上，根据需要修改相应的字段（有关详细信息，请参阅本主题前面介绍的“创建新的位置策略”过程中的步骤 5）。

7.  单击“提交”****。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中删除位置策略](lync-server-2013-deleting-a-location-policy.md)  


[定义 Lync Server 2013 的位置策略](lync-server-2013-defining-the-location-policy.md)  


[在 Lync Server 2013 中配置停车呼叫的电话号码分机](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

