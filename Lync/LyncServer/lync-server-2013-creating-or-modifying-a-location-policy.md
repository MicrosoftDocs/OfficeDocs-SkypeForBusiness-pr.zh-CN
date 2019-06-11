---
title: 'Lync Server 2013: 创建或修改位置策略'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying a location policy
ms:assetid: 10338418-4da4-42df-b231-f52098c08dae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687971(v=OCS.15)
ms:contentKeyID: 49733557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 173cfd6ce158a089e03a9eded12c3c6920183463
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830772"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-a-location-policy-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改位置策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

在 Lync Server 2013 中, 你可以使用位置策略应用与增强的 9-1-1 (E9) 功能以及用户或联系人的位置设置相关的设置。 位置策略确定用户是否启用了 E9-1, 如果是紧急呼叫, 该行为是什么。 例如, 您可以使用位置策略定义哪个号码构成紧急呼叫 (例如, 美国 911)、是否应自动通知企业安全以及如何路由呼叫。

你可以从 Lync Server 2013 控制面板中的 "**网络配置**" 组配置位置策略。 从 Lync Server 控制面板, 您可以查看、创建、修改或删除位置策略。 使用此部分中的过程创建或修改位置策略。 有关删除位置策略的详细信息, 请参阅[在 Lync Server 2013 中删除位置策略](lync-server-2013-deleting-a-location-policy.md)。

在 Lync Server 2013 中, 你可以覆盖来自位置信息服务的位置更新的客户端请求之间的默认时间量。 默认值为4小时。 将**CsLocationPolicy** Cmdlet 与 LocationRefreshInterval 参数配合使用, 以替代默认值。

<div>

## <a name="to-create-a-new-location-policy-in-lync-server-control-panel"></a>在 Lync Server "控制面板" 中创建新的位置策略

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**位置策略**"。

4.  在 "**位置策略**" 页面上, 单击 "**新建**", 然后选择要创建的策略类型:
    
      - 若要创建网站策略, 请单击 "**网站策略**"。 在 "**选择网站**" 中, 选择要应用策略的网站, 然后单击 **"确定"**。 在 "**新建位置策略**" 页上, "**范围**" 字段包含 "值"**网站**, "**名称**" 字段包含您选择的网站的名称。 您不能修改这些字段中的任何一个。 网站策略将自动应用到指定网站上的所有用户, 并替代这些用户的全局策略。
    
      - 若要创建**用户策略**, 请单击 "**用户策略**"。 在**新的位置策略**中, "**范围**" 域包含 "**用户**" 值。 您不能修改此值。 在 "**名称**" 字段中, 键入要赋予此策略的名称。 用户策略不会自动应用到任何用户。 创建用户策略后, 必须手动向要应用策略的用户或网络网站授予该策略。

5.  按如下方式填写其余字段:
    
      - **启用增强的紧急服务**   选中此复选框可启用与此策略关联的用户 E9-1。 启用紧急服务时, Lync Server 客户将在注册时检索位置信息, 并在进行紧急呼叫时包含该信息。
    
      - **位置**   指定下列值之一:
        
          - **必填**   当客户端注册到新位置时, 系统会提示用户输入位置信息。 用户可以在不输入任何信息的情况下关闭提示。 如果输入了信息, 紧急服务提供商将首先答复紧急电话, 以便在将位置路由到公共安全应答点 (PSAP) 运算符 (即911接线员) 之前对该位置进行验证。
        
          - **不要求**   用户将不会提示用户输入位置。 当拨打没有位置信息的电话时, 紧急服务提供商将接听呼叫并请求一个位置。
        
          - **免责声明**   此选项与**必需**的相同, 只是用户无法在不输入位置信息的情况下取消提示。 用户仍然可以完成紧急呼叫, 但无需输入信息即可完成任何其他通话。 此外, 将向用户显示免责声明文本, 可向用户发出提示, 提醒他们注意您拒绝输入位置信息的后果。 若要设置免责声明文本, 必须使用 Lync Server Management Shell 使用 EnhancedEmergencyServiceDisclaimer 参数运行**CsLocationPolicy** Cmdlet 或**CsLocationPolicy** cmdlet。 有关详细信息, 请参阅 Lync Server Management Shell 文档中的 "[设置 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) " 或 "[新建-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy) "。
            
            <div>
            

            > [!NOTE]  
            > 在 Lync Server 2013 中, 你可以使用位置策略为不同的区域设置或不同的用户集设置不同的免责声明, 与 Lync Server 2010 中不同, 你可以仅为整个组织指定全局免责声明。

            
            </div>
    
      - **针对紧急服务的使用位置只有**   Lync 可以出于各种原因而使用位置信息 (例如, 通知团队成员当前位置)。 选中此复选框以确保位置信息仅可用于紧急呼叫。
    
      - **PSTN 使用**   公共交换电话网络 (PSTN) 使用, 用于确定将使用此配置文件从客户端路由紧急呼叫的语音路线。 与此使用关联的路由应指向专用于紧急呼叫的 SIP 中继, 或者指向紧急位置标识号码 (ELIN) 网关, 该网关将紧急呼叫路由到最近的公共安全应答点 (PSAP)。
    
      - **紧急电话号码**   拨打的电话号码, 以达到紧急服务。 在美国, 此值为911。 该字符串必须由数字0到9组成, 并且长度可以介于1到10个数字之间。
    
      - **紧急拨号屏蔽**   拨号时要转换为 "紧急电话拨号码" 值的号码。 例如, 如果您在此字段中输入了212的值, "紧急电话拨号码" 字段的值为 911, 则如果用户212拨打电话, 将对911发出呼叫。 这样就允许拨打备用紧急号码，并且仍可接通紧急服务（例如，来自使用不同紧急号码的国家/地区的人员可以尝试拨打自己国家/地区的号码，而不是拨打其当前所在国家/地区的号码）。 可以通过使用分号分隔值来定义多个紧急拨号掩码。 例如，212;414。 字符串的最大长度为100个字符。 每个字符都必须为 0 到 9 的数字。
        
        <div>
        

        > [!IMPORTANT]  
        > 确保指定的拨号掩码值与 "呼叫驻留" 轨道范围中的数字不同。 呼叫寄存路由将优先于紧急拨号字符串转换。 若要查看现有的呼叫公园轨道范围, 请单击左侧导航栏中的 "<STRONG>语音功能</STRONG>", 然后单击 "<STRONG>呼叫寄存</STRONG>"。 有关详细信息, 请参阅<A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">在 Lync Server 2013 中配置停车通话的电话号码扩展</A>。

        
        </div>
    
      - ****   发出紧急呼叫时通知的一个或多个 SIP 统一资源标识符 (uri) 的通知 URI。 例如, 只要进行紧急呼叫, 公司安全办公室就会收到即时消息通知。 如果呼叫者的位置可用, 将在通知中包含该位置。 多个 SIP Uri 可以包含为以逗号分隔的列表。 例如, "sip: security@litwareinc.com", "sip: kmyer@litwareinc.com"。 支持通讯组列表。 字符串的长度必须介于1到256个字符之间, 并且必须以前缀 "sip:" 开头。 在通知 URI 字段中单击之前, 将显示一个示例。
    
      - **会议 uri**   将 conferenced 进行任何紧急调用的第三方的电话号码的 SIP uri (如电话号码)。 例如, 公司安全 office 可以在进行紧急呼叫时接收呼叫, 并接听或参与该呼叫 (具体取决于**会议模式**字段中提供的值)。 该字符串的长度必须介于1到256个字符之间, 并且必须以前缀 sip: 开头。 将显示一个示例, 直到您在此字段内单击。
    
      - **会议模式**   如果在 "**会议 URI** " 字段中指定一个值, 则**会议模式**确定第三方是否可以参与呼叫或只能接听。 指定下列选项之一:
        
          - **单向**   第三方只能侦听呼叫方和 PSAP 运营商之间的对话。
        
          - **** 第三方可以在呼叫者和 PSAP 操作员之间接听并参与呼叫。   

6.  单击“**提交**”。
    
    <div>
    

    > [!IMPORTANT]  
    > 创建用户策略时, 最初不会将该策略应用于任何用户或网络网站。 若要将策略应用于用户, 请单击左侧导航栏中的 "<STRONG>用户</STRONG>"。 查找要对其应用策略的用户。 在“编辑”<STRONG></STRONG>菜单上，单击“显示详细信息”<STRONG></STRONG>。 在 "<STRONG>编辑 Lync Server 用户</STRONG>" 页面上, 从 "<STRONG>位置策略</STRONG>" 下拉列表中选择新的位置策略, 然后单击 "<STRONG>提交</STRONG>"。<BR>若要将策略应用于网络网站, 请在左侧导航栏中单击 "<STRONG>网络配置</STRONG>", 然后单击 "<STRONG>网站</STRONG>"。 查找要对其应用策略的网络站点。 在“编辑”<STRONG></STRONG>菜单上，单击“显示详细信息”<STRONG></STRONG>。 在 "<STRONG>编辑网站</STRONG>" 中, 从 "<STRONG>位置策略</STRONG>" 下拉列表中选择新的位置策略, 然后单击 "<STRONG>提交</STRONG>"。

    
    </div>

</div>

<div>

## <a name="to-modify-a-location-policy-in-lync-server-control-panel"></a>在 Lync Server "控制面板" 中修改位置策略

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**位置策略**"。

4.  在 "**位置策略**" 页面上, 选择要修改的位置策略。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在 "**编辑位置策略**" 页面上, 根据需要修改字段 (有关详细信息, 请参阅本主题前面的 "创建新的位置策略中的步骤 5"。

7.  单击“**提交**”。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中删除位置策略](lync-server-2013-deleting-a-location-policy.md)  


[定义 Lync Server 2013 的位置策略](lync-server-2013-defining-the-location-policy.md)  


[在 Lync Server 2013 中配置停车通话的电话号码扩展](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

