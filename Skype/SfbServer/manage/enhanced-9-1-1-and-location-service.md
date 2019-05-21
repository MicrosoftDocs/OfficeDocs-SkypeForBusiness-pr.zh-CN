---
title: 管理增强的9-1-1 和位置服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for business 服务器支持来自 Skype for Business 客户端的增强 9-1-1 (E9-1) 呼叫。 将 Skype for business 服务器配置为 E9-1 时, 来自 Skype for Business 的紧急电话包括来自位置信息服务数据库的紧急响应位置 (ERL) 信息。
ms.openlocfilehash: a0cf7254e12f00a01082b7aad71ce350cb382b9c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280297"
---
# <a name="manage-enhanced-9-1-1-and-the-location-service-in-skype-for-busines-server"></a>在 Skype for 名片 Server 中管理增强的9-1-1 和位置服务

Skype for business 服务器支持来自 Skype for Business 客户端的增强 9-1-1 (E9-1) 呼叫。 将 Skype for business 服务器配置为 E9-1 时, 来自 Skype for Business 的紧急电话包括来自位置信息服务数据库的紧急响应位置 (ERL) 信息。 使用本文中的过程管理位置策略。

> [!Note]
> 有关部署高级企业语音功能 (如 E9-1-1 和位置信息服务) 的详细信息, 请参阅[部署高级企业语音功能](../deploy/deploy-enterprise-voice/deploy-advanced-enterprise-voice-features.md)。

在 Skype for Business Server 中, 你可以使用位置策略应用与增强的 9-1-1 (E9-1) 功能以及用户或联系人的位置设置相关的设置。 位置策略确定用户是否启用了 E9-1, 如果是紧急呼叫, 该行为是什么。 例如, 您可以使用位置策略定义哪个号码构成紧急呼叫 (例如, 美国 911)、是否应自动通知企业安全以及如何路由呼叫。

你可以在 Skype for Business Server 控制面板中的 "**网络配置**" 组中配置位置策略。 从 Skype for Business 服务器控制面板, 您可以查看、创建、修改或删除位置策略。 使用以下过程查看有关位置策略的信息。 


## <a name="view-location-policy-information"></a>查看位置策略信息 

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**位置策略**"。

4.  在 "**位置策略**" 页面上, 选择要修改的位置策略。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。
 
    > [!NOTE]  
    > 一次只能查看一个位置策略的相关信息。

默认情况下存在一个名为 Global 的策略, 不能删除或重命名。 但是, 你可以修改全局策略。 此政策将应用于所有用户和联系人, 除非你创建网站策略或每用户策略。 每用户策略必须应用于特定用户。


## <a name="create-or-modify-a-location-policy"></a>创建或修改位置策略 

在 Skype for Business Server 中, 你可以覆盖来自位置信息服务的位置更新的客户端请求之间的默认时间量。 默认值为4小时。 将**CsLocationPolicy** Cmdlet 与 LocationRefreshInterval 参数配合使用, 以替代默认值。


### <a name="to-create-a-new-location-policy-in-the-skype-for-business-server-control-panel"></a>在 "Skype for Business 服务器" 控制面板中创建新的位置策略

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**位置策略**"。

4.  在 "**位置策略**" 页面上, 单击 "**新建**", 然后选择要创建的策略类型:
    
      - 若要创建网站策略, 请单击 "**网站策略**"。 在 "**选择网站**" 中, 选择要应用策略的网站, 然后单击 **"确定"**。 在 "**新建位置策略**" 页上, "**范围**" 字段包含 "值"**网站**, "**名称**" 字段包含您选择的网站的名称。 您不能修改这些字段中的任何一个。 网站策略将自动应用到指定网站上的所有用户, 并替代这些用户的全局策略。
    
      - 若要创建**用户策略**, 请单击 "**用户策略**"。 在**新的位置策略**中, "**范围**" 域包含 "**用户**" 值。 您不能修改此值。 在 "**名称**" 字段中, 键入要赋予此策略的名称。 用户策略不会自动应用到任何用户。 创建用户策略后, 必须手动向要应用策略的用户或网络网站授予该策略。

5.  按如下方式填写其余字段:
    
      - **启用增强的紧急服务**   选中此复选框可启用与此策略关联的用户 E9-1。 启用紧急服务后, Skype for Business 服务器客户端将检索有关注册的位置信息, 并在进行紧急呼叫时包含该信息。
    
      - **位置**   指定下列值之一:
        
          - **必填**   当客户端注册到新位置时, 系统会提示用户输入位置信息。 用户可以在不输入任何信息的情况下关闭提示。 如果输入了信息, 紧急服务提供商将首先答复紧急电话, 以便在将位置路由到公共安全应答点 (PSAP) 运算符 (即911接线员) 之前对该位置进行验证。
        
          - **不要求**   用户将不会提示用户输入位置。 当拨打没有位置信息的电话时, 紧急服务提供商将接听呼叫并请求一个位置。
        
          - **免责声明**   此选项与**必需**的相同, 只是用户无法在不输入位置信息的情况下取消提示。 用户仍然可以完成紧急呼叫, 但无需输入信息即可完成任何其他通话。 此外, 将向用户显示免责声明文本, 可向用户发出提示, 提醒他们注意您拒绝输入位置信息的后果。 若要设置免责声明文本, 必须使用 Skype for Business Server Management Shell 使用 EnhancedEmergencyServiceDisclaimer 参数运行**CsLocationPolicy** Cmdlet 或**CsLocationPolicy** cmdlet。 有关详细信息, 请参阅[Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)或[CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)。
          
    
      - **仅使用紧急服务的位置**Skype for Business 可以出于各种原因使用位置信息 (例如, 通知团队成员您的当前位置)。 选中此复选框以确保位置信息仅可用于紧急呼叫。
    
      - **PSTN 使用**   公共交换电话网络 (PSTN) 使用, 用于确定将使用此配置文件从客户端路由紧急呼叫的语音路线。 与此使用关联的路由应指向专用于紧急呼叫的 SIP 中继, 或者指向紧急位置标识号码 (ELIN) 网关, 该网关将紧急呼叫路由到最近的公共安全应答点 (PSAP)。
    
      - **紧急电话号码**   拨打的电话号码, 以达到紧急服务。 在美国, 此值为911。 该字符串必须由数字0到9组成, 并且长度可以介于1到10个数字之间。
    
      - **紧急拨号屏蔽**   拨号时要转换为 "紧急电话拨号码" 值的号码。 例如, 如果您在此字段中输入了212的值, "紧急电话拨号码" 字段的值为 911, 则如果用户212拨打电话, 将对911发出呼叫。 这样就允许拨打备用紧急号码，并且仍可接通紧急服务（例如，来自使用不同紧急号码的国家/地区的人员可以尝试拨打自己国家/地区的号码，而不是拨打其当前所在国家/地区的号码）。 可以通过使用分号分隔值来定义多个紧急拨号掩码。 例如，212;414。 字符串的最大长度为100个字符。 每个字符都必须为 0 到 9 的数字。
      

        > [!IMPORTANT]  
        > 确保指定的拨号掩码值与 "呼叫驻留" 轨道范围中的数字不同。 呼叫寄存路由将优先于紧急拨号字符串转换。 若要查看现有的呼叫公园轨道范围, 请单击左侧导航栏中的 "**语音功能**", 然后单击 "**呼叫寄存**"。 

    
      - ****   发出紧急呼叫时通知的一个或多个 SIP 统一资源标识符 (uri) 的通知 URI。 例如, 只要进行紧急呼叫, 公司安全办公室就会收到即时消息通知。 如果呼叫者的位置可用, 将在通知中包含该位置。 多个 SIP Uri 可以包含为以逗号分隔的列表。 例如, "sip: security@litwareinc.com", "sip: kmyer@litwareinc.com"。 支持通讯组列表。 字符串的长度必须介于1到256个字符之间, 并且必须以前缀 "sip:" 开头。 在通知 URI 字段中单击之前, 将显示一个示例。
    
      - **会议 uri**   将 conferenced 进行任何紧急调用的第三方的电话号码的 SIP uri (如电话号码)。 例如, 公司安全 office 可以在进行紧急呼叫时接收呼叫, 并接听或参与该呼叫 (具体取决于**会议模式**字段中提供的值)。 该字符串的长度必须介于1到256个字符之间, 并且必须以前缀 sip: 开头。 将显示一个示例, 直到您在此字段内单击。
    
      - **会议模式**   如果在 "**会议 URI** " 字段中指定一个值, 则**会议模式**确定第三方是否可以参与呼叫或只能接听。 指定下列选项之一:
        
          - **单向**   第三方只能侦听呼叫方和 PSAP 运营商之间的对话。
        
          - **** 第三方可以在呼叫者和 PSAP 操作员之间接听并参与呼叫。   

6.  单击“**提交**”。


    > [!IMPORTANT]  
    > 创建用户策略时, 最初不会将该策略应用于任何用户或网络网站。 若要将策略应用于用户, 请单击左侧导航栏中的 "**用户**"。 查找要对其应用策略的用户。 在“编辑”**** 菜单上，单击“显示详细信息”****。 在 "**编辑服务器用户**" 页面上, 从 "**位置策略**" 下拉列表中选择新的位置策略, 然后单击 "**提交**"。<BR>若要将策略应用于网络网站, 请在左侧导航栏中单击 "**网络配置**", 然后单击 "**网站**"。 查找要对其应用策略的网络站点。 在“编辑”**** 菜单上，单击“显示详细信息”****。 在 "**编辑网站**" 中, 从 "**位置策略**" 下拉列表中选择新的位置策略, 然后单击 "**提交**"。


### <a name="to-modify-a-location-policy-in-the-skype-for-business-server-control-panel"></a>在 "Skype for Business 服务器" 控制面板中修改位置策略

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**位置策略**"。

4.  在 "**位置策略**" 页面上, 选择要修改的位置策略。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在 "**编辑位置策略**" 页面上, 根据需要修改字段 (有关详细信息, 请参阅本主题前面的 "创建新的位置策略中的步骤 5"。

7.  单击“**提交**”。

        
## <a name="delete-a-location-policy"></a>删除位置策略


1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**位置策略**"。

4.  在 "**位置策略**" 页面上, 选择要删除的位置策略。
   
    > [!NOTE]  
    > 您可以一次删除多个位置策略。 若要执行此操作, 请在按住 CTRL 键的同时按 CTRL 并选择多个策略。 或者, 若要选择所有策略, 请单击 "**编辑**" 菜单上的 "**全选**"。


5.  在 "**编辑**" 菜单上, 单击 "**删除**"。

6.  单击“**确定**”。

    > [!IMPORTANT]  
    > 您不能删除全局位置策略。 如果你尝试删除全局策略, 你将收到一条警告消息, 并且该策略将重置为其默认值。


## <a name="see-also"></a>另请参阅

[创建或修改网络站点](network-management/call-admission-control/managing-call-admission-control-for-sites.md#create-or-modify-network-sites)

[新-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  

[Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) 
 
[Remove-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  

[Get-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
