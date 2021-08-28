---
title: 使用 Skype for Business Server 2015 压力和性能工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 2/13/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 93f42230-24a2-418d-9770-bf4670a9d78f
description: 若要运行 Skype for Business Server 2015 压力和性能工具，你需要能够管理用户、联系人和用户配置文件，配置该工具以运行，然后查看该工具产生的输出或结果。
ms.openlocfilehash: 6db23c259aa19e8ec9e590218ff233461c677aa0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58586874"
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a>使用 Skype for Business Server 2015 压力和性能工具
 
若要运行 Skype for Business Server 2015 压力和性能工具，你需要能够管理用户、联系人和用户配置文件，配置该工具以运行，然后查看该工具产生的输出或结果。
  
运行 2015 Stress and Performance Tool Skype for Business Server涉及四个方面 (可执行文件LyncPerfTool.exe) ：
  
- [创建用户和联系人](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [配置用户配置文件](using-the-tool.md#BKMK_UserProfile)
    
- [运行 LyncPerfTool](using-the-tool.md#BKMK_RunTool)
    
- [解释结果](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a>创建用户和联系人
<a name="BKMK_CreateUsersAndContacts"> </a>

你需要使用 Skype for Business Server 2015 (SB 2015) 用户预配工具 (UserProvisioningTool.exe) 来创建用户和联系人，以便进行压力和性能测试。
  
这是在阅读以下主题时可能有用的有用术语列表：
  
- **组织单位** - Active Directory 域服务 (AD DS) 组织单位 (OU) 。
    
- **联盟/跨池** - 可以与其他即时消息和 IM 服务中的 (通信) 用户。
    
- **通讯组列表** - 或 DLL。 这些是 AD DS 中包含 AD DS 用户列表的对象。 它们用于促进各组人员之间的通信。
    
- **位置信息** 服务 - Skype for Business Server 2015 服务，在按电话启用和配置该服务时，允许检索增强型 911 (E911) 服务的物理位置。
    
- **美国** 电话号码 - 分配给用户的 电话 号码，以及用于在反向号码查找 RNL) 中路由入站和出站呼叫的 SIP URI (。
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>使用"用户"和"联系人"UserProvisioningTool.exe

> [!NOTE]
> 在开始之前，请务必确保以 Domain Admins 安全组的成员身份登录以运行此工具。 您需要这样做，因为您将创建 Active Directory 用户。 
  
您必须使用 Skype for Business Server设置工具创建用户和联系人进行负载模拟。
  
The **Skype for Business Server User Provisioning Tool** is installed with the Skype for Business Server Stress and Performance **Tool** package. 请确保程序包安装程序 (CapacityPlanningTool.msi) 已在前端服务器或要测试的 Standard Edition 服务器上运行。
  
可以通过在前端服务器或 Standard Edition 服务器上运行位于 %InstalledDirectory%LyncStressAndPerfTool\LyncStress) 中的文件 UserProvisioningTool.exe (来启动 Skype for Business Server 用户设置工具。
  
> [!IMPORTANT]
> 当您创建大量用户 (例如，10，000 名或更多的用户) ，请运行UserProvisioningTool.exe。 你将需要这样做，因为该工具将创建  *和配置新的*  AD 用户。
  
当用户预配工具打开时，单击配置并选择加载配置。 
  
若要开始配置用户和联系人，请加载程序包中包含的默认文件，称为"SampleData.xml"。 这将使用需要更改的示例数据预填充字段，使其与部署相关。
  
如果您有一个已包含自定义设置的预配置 XML 文件，您可以改为加载该文件。 在用户设置工具中填写字段，如以下部分所述。
  
### <a name="to-configure-server-options"></a>配置服务器选项：

1. 在"前端池 **FQDN"** 字段中，键入要承载用户的 Standard Edition 服务器的完全限定域名 (FQDN) 或前端池。
    
2. 在 **"用户名前缀** "字段中，键入要用于为测试目的对用户名进行 (例如"TestUser") 。
    
3. 在 **"密码** "字段中，键入将用于所有测试用户帐户的密码。
    
4. 在 **"帐户域** "字段中，键入当前 AD 域 (要创建测试用户的域的域名) 。
    
5. 在 **"组织单位"** 字段中，键入要创建这些测试用户的 AD 域的名称。  (如果 OU 不存在，系统将会为用户创建) 。
    
6. 在 **"电话区** 号"字段中，键入要在所有测试用户帐户中使用的三位数区号。 确保你选择的区号不会与 AD 中其他用户的区号发生冲突。
    
7. 如果要 **为测试用户** 启用语音功能，请单击选中"启用语音企业语音。
    
8. 在 **"用户数"** 字段中，提供要创建的测试用户的总数。
    
9. 在" **开始** 索引"字段中，为用作用户名前缀 (前缀的后缀提供起始号码，例如，前缀为"TestUser"，在下面的示例中，第一个名称以"0"结尾。) 
    
     ![显示用户创建选项卡的用户预配工具。](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a>"创建用户"按钮

单击"创建 **用户"** 按钮时，将验证已输入的输入参数。 如果存在任何验证错误，系统将提示你修复错误。 或者，如果所有值都正确，用户将开始显示在 AD (您指定的 OU 中) 。 在工具运行时，你将在工具底部看到一个进度栏。 当进度栏处于活动状态时，不要关闭应用程序。
  
用户创建需要时间，因此请进行相应的规划。 对于少数用户，此过程可能需要几分钟，而对于大量用户，此过程可能需要几个小时。
  
如果您无法访问测试环境中 AD 域控制器，您仍可以通过以指定要创建的用户范围中的用户之一登录来验证用户创建。 请记住，使用前缀和后缀以及 @sipDomain 作为用户名。 下面是一个示例  <em>：TestUser20@contoso.net</em>  。
  
> [!NOTE]
> 如果用户已存在，单击"创建用户"按钮将用任何配置更改更新用户。 
  
#### <a name="delete-users-button"></a>"删除用户"按钮

单击"删除 **用户"** 按钮时，将验证选项卡的输入参数。 如果存在验证错误，系统将提示你修复错误，如果输入值正确，指定的测试用户将被禁用，并且将从 Active Directory 中删除。 同样，进度栏将显示在此选项卡的底部，并且不应在进度栏处于活动状态时关闭应用程序。
  
> [!NOTE]
> 仅支持美国格式的电话号码。 电话号码始终分配给用户，默认情况下，UserProvisioningTool.exe创建的所有用户企业语音用户。 使用电话号码的任何方案（如会议自动助理 UC-PSTN 呼叫）使用此电话号码可以正确路由呼叫。 因此，  *每个用户都必须*  有唯 *一的电话号码*  。
  
> [!NOTE]
> **如果您必须创建两次用户，则该命令将失败，除非您使用不同的区号，或者之前的用户已使用 Disable-CsUser cmdlet 禁用。**
  
> [!IMPORTANT]
> 创建联系人之前，首先需要完成用户 (从"用户"选项卡) 。 
  
> [!IMPORTANT]
> 如果刚刚创建了用户，则需要等到复制完成Skype for Business Server并在数据库中填充用户帐户。 **如果用户尚未完成复制，你将看到一个错误。** 如果 Skype for Business Server 2015 前端服务已启动，或者在您指定的总数的最后一个用户上成功运行 Get-CsUser cmdlet，则您将知道用户何时完成复制。
  
#### <a name="contacts-creation-tab"></a>"联系人创建"选项卡

此选项卡允许你为测试提供用户的联系人详细信息。
  
![显示"内容创建"选项卡的用户预配工具。](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a>若要配置用户的联系人，请执行下列操作：

1. 在" **每个用户的平均联系人** 数"字段中，输入每个用户的联系人列表中要填充的平均联系人数。
    
2. 如果要 **为** 每个用户创建同等数量的联系人，请选中"固定"复选框。 如果要更改为用户创建的联系人数，请清除该复选框。
    
3. 在" **每个用户的平均联系人组数"** 字段中，输入每个用户的联系人组数。 此数字需要小于每个用户 **的平均联系人数**。
    
4. 在" **联盟/跨池联系人** 百分比"字段中，提供一个介于 0 和 100 之间的数字。 将用联盟用户创建此百分比的联系人。
    
5. 在 **"联合/跨** 池用户前缀"字段中，为将添加到本地用户的联系人列表的联合用户提供用户名。
    
6. 在 **"联盟/跨池用户 SIP 域** "字段中，提供联盟用户的 SIP 域名。
    
7. 在 **"用户创建** "选项卡中，确保信息正确。 你的联系人将基于"用户创建"选项卡上的值创建。
    
8. 单击 **"创建联系人"** 开始创建联系人。 此过程可能需要几分钟时间。 完成后，将显示一个对话框，消息为"操作已成功完成"。 可以以从"用户创建"选项卡创建的用户登录来验证所创建的联系人。
    
    > [!NOTE]
    > 创建联系人后，此工具将重新启动目标池中的所有前端服务器。 前端服务器启动 (最多需要 2) ，具体取决于此操作创建的联系人数量。 
  
#### <a name="distribution-list"></a>通讯组列表

The Skype for Business Server 2015 Stress and Performance Tool can simulate the Distribution List (DL) expansion feature in the Skype for Business 2015 client. 如果您不打算在用户设置工具中启用 DL 扩展，可以跳过此步骤。
  
![显示"创建通讯组列表"选项卡的用户设置工具。](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
"通讯组列表"选项卡允许您创建压力和性能工具用于通讯组列表扩展功能的 DLL。 在创建 DLL 之前，Skype for Business Server部署 2015，包括运行 ForestPrep。 如果不这样做，则 AD 架构中将不存在 DL 属性，因此该工具无法创建 DLL。
  
### <a name="to-configure-distribution-lists"></a>配置通讯组列表：

1. 在"通讯组列表数"字段中，提供要创建的 (建议从一个值开始，该值是拥有的用户数的两倍。) 。
    
2. 在" **通讯组列表前缀** "字段中，输入您创建的所有 DLL 都将具有的前缀，例如 *testDL*  。 这意味着，在 100 个 DLL 下，DLL 名称将如下所示：testDL0、testDL1，最多为 testDL99。
    
3. 在 **"Dist. List"** 字段中的"最小成员"字段中，输入要放入每个 DL 的最小用户数。
    
4. 在 **"Dist. List"** 字段中，输入要在每个 DL 中添加的最大用户数。
    
#### <a name="create-distribution-lists-button"></a>"创建通讯组列表"按钮

单击"创建通讯组列表"按钮时，该工具会查询 Active Directory，以查看是否存在与前缀和号码匹配的通讯组列表。 该工具将创建任何不存在的 DLL。 向这些新创建的通讯组列表添加成员时，它将从"用户创建"选项卡上指定的范围中选择用户。
  
#### <a name="location-info-service-config-tab"></a>"位置信息服务配置"选项卡

The Skype for Business Server 2015 Stress and Performance Tool can also generate 虚拟 configuration files for the Location Information Service. 请注意，位置信息服务通常对服务器没有明显的性能影响。 
  
![显示"位置信息服务配置"选项卡的用户预配工具。](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
如果选择测试此功能，请填写表单中的值，然后单击"生成 LIS 配置文件"按钮，这将创建名为.CSV文件：
  
- LIS_Subnet.csv
    
- LIS_Switches.csv
    
- LIS_Ports.csv
    
- LIS_WAP.csv
    
若要将这些文件导入 LIS 数据库，请使用以下 PowerShell cmdlet：
  
- Set-CsLisSubnet
    
- Set-CsLisSwitch
    
- Set-CsLisPort
    
- Set-CsWirelessAccessPoint
    
## <a name="configure-user-profile"></a>配置用户配置文件
<a name="BKMK_UserProfile"> </a>

通过用户创建工具 (创建用户) 可以使用 Skype for Business Server 2015 Load Configuration 工具配置 (UserProfileGenerator.exe) 。
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a>运行 Skype for Business Server 2015 Load Configuration 工具

启动"加载配置" (UserProfileGenerator.exe) 并填写选项卡。 此工具为运行模拟所需的每台客户端计算机创建一个目录。 每个客户端目录都附带一个脚本，用于启动 Skype for Business Server 2015 压力和性能工具 (LyncPerfTool.exe) 。 以下各节将举例说明如何填写"Skype for Business Server 2015 Load Configuration"工具的每个选项卡上的字段。
  
> [!IMPORTANT]
> "负载配置"工具 (UserProfileGenerator.exe) 中使用的用户特定值必须与池的 Skype for Business Server 2015 用户创建工具 (UserProvisioningTool.exe) 指定的值匹配。 
  
#### <a name="common-configuration-tab"></a>"通用配置"选项卡

" **加载配置** 工具"的"常见配置"选项卡如下所示。 填写"通用配置"选项卡的字段，如以下步骤所述。
  
![显示"通用配置"选项卡的"用户设置"选项卡。](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. 在 **"可用计算机数** "字段中，键入要用于运行"压力和性能"工具的计算机 (LyncPerfTool.exe) 。 我们建议你每 4500 个用户有一台计算机进行模拟，但是如果你减少负载级别，或者仅在"常规方案"选项卡上设置一部分工具的可用功能 () "负载级别"，此数字可能会有所不同。
    
2. 在" **用户名前缀"** 字段中，为所有用户的用户名字段输入前缀。 要登录到统一资源标识符 (URI) 将为 *：UserPrefix[用户启动索引... (用户-1) 数量]@User 域*  ，例如 myUser009@Contoso.com。
    
3. 在 **"所有用户的密码"** 字段中，输入创建用户期间使用的密码。 如果将此字段留空，用户名将被设置为密码。
    
4. 在 **"用户启动索引** "字段中，输入要配置的第一个用户的索引。 您可以为不同类型的负载配置不同的范围，但必须为每个要配置 (UserProfileGenerator.exe) 运行一次负载配置工具。
    
5. 在 **"用户数"** 字段中，输入要配置的用户总数。
    
6. 在 **"用户域** "字段中，输入用于 SIP URI 的域。 这用于构造每个用户登录到 Skype for Business Server 2015 前端服务器或 Standard Edition 服务器的 SIP URI，并且可能不同于帐户域。
    
7. 在" **帐户域** "字段中，输入 AD DS 域登录名。
    
8. 在 **"MPOP** 百分比 (多点状态百分比) "字段中，为从多台计算机或设备登录的用户百分比提供一个值，例如 10%。
    
9. 在"每个实例登录每秒登录数"字段中 **(并发**) 数。 这是您的用户的最大登录数，建议是每秒小于/等于 2 的速率 (<=2) 。
    
10. 在" **访问代理"或"池 FQDN"** 字段中，输入希望 (连接到) 服务器的完全限定域名"FQDN"。 如果用户在外部登录，则需要键入访问代理。 如果用户为内部用户，则提供其 Enterprise 池或Standard Edition的 FQDN。
    
11. 在 **"端口** "字段中，输入希望用户用于 SIP 的端口 (此处的默认值为 5061) 。
    
12. 对于"**外部网络服务器设置，** 请为"访问代理"或"池 FQDN"提供"端口 **"。** 这些设置仅用于外部终结点负载模拟。
    
#### <a name="general-scenarios-tab"></a>"常规方案"选项卡

![显示"常规方案"选项卡的"加载配置工具"。](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
您可以为通过确定要运行或保持禁用状态而提供的每个常规方案配置负载级别和参数。 以下是常规选项：
  
> [!NOTE]
> 所有字段的负载级别值，但本地信息服务为 Disabled、Low、Medium、High 或 **Custom。**     如果选择任何已禁用的设置，则针对每个客户端生成配置。 高会导致服务器上支持的最大负载;中是高负载的 60% ;low 为 30%。 
  
- **即时消息 -** 这包括对等和会议;为"负载级别"选择适当的值。
    
- **音频会议 -** 仅选择音频会议负载 *级别*  。 稍后将在"语音方案"部分处理 **对等呼叫。** 打开" **高级"** 选项卡以启用 MultiView。
    
- **应用程序共享 -** 选择应用程序共享的加载级别。
    
- **数据协作 -** 选择数据协作的负载级别，其中包括数据会议。
    
- **通讯组列表扩展 -** 单击 **"高级** "按钮，使用"用户创建工具"选项卡的"DL"选项卡上配置的相同值填写 (UserProvisioningTool.exe) 。 选择加载级别。
    
- **通讯簿 Web 查询 -** 这是通讯簿查找服务，而不是通讯簿文件下载。 如果要为通讯簿文件下载启用此功能，请单击"高级"按钮，将 **EnableABSDownload** 设置为 True。 为加载级别提供值。
    
- **响应组服务 -** 单击 **"高级**"按钮，并指定在预配代理时已创建的响应响应组服务 URI。 必须至少选择一个响应组。 若要使用更多信息，请使用分号分隔响应组。 将 **RGSUriSuffixStartIndex** 和 **RGSUriSuffixEndIndex** 更新为实际值。 选择加载级别。
    
- **位置信息服务 -** 选择"已启用"或"已禁用"的加载级别。
    
> [!NOTE]
> 每个方案旁边都有一个"高级"按钮，以及一组启用默认设置变体的复选框。 
  
- 选择  *"临时*  "将允许工具生成将在整个一小时内创建的会议的模拟。
    
- 选择  *"大型*  会议"意味着将模拟大型会议方案。
    
-  *外部*  通知工具还要模拟外部用户。
    
这些按钮和复选框是特定于每个方案的额外值，将更改压力和性能工具的行为，并可能进行自定义。
  
对于"常规方案"选项卡上的每个方案 (位置信息服务) 除外，如果"负载级别"的值为 **"** 自定义"，则使用"高级"对话框中的相应字段计算对话速率。 字段名称可能会有所不同，具体取决于方案，但字段说明将状态：注意 只有在从下拉菜单中选择了"自定义"时，才能使用  *此数字*  。
  
值 **High、Medium** 和 **Low** 将按照用户模型（即平衡所有方案的用户模型）来更改每个形式的对话速率。  如果由于预期使用量不同而需要更改每个模态的负载级别，请使用自定义对话速率。
  
#### <a name="voice-scenarios-tab"></a>"语音方案"选项卡

这是配置所有语音相关方案的选项卡。
  
!["加载配置"工具"语音方案"选项卡。](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
可用的选项包括：
  
- **VoIP -** 单击" **高级"** 按钮，并添加 PhoneAreaCode 和 LocationProfile (拨号计划) 值。 你还将为"负载级别"提供一个值。 如果选择启用 VoIP 或 UC/PSTN 网关的负载级别，将生成公用电话交换网 (PSTN) 统一通信 (UC) 配置文件以模拟外部呼叫。
    
- **UC/PSTN 网关 -** 你需要选择一个"负载级别"值，当你选择"已禁用"外的其他内容时，你还必须通过单击"高级"按钮为 PSTN 区号 **提供** 值。 单击 **中介** 服务器和 PSTN 下的"添加"。 请确保为区号配置了路由。
    
    > [!TIP]
    > 可以使用命令行管理Skype for Business命令行管理Skype for Business验证语音路由配置。 
  
- **会议助理 -** 提供 Load Level 的值。 除 Disabled 外的任何值都将启用 **"电话号码"** 字段。 输入要使用的自动助理的电话号码。 单击 **"高级** "，然后为 **LocationProfile 字段提供** 值。
    
- **呼叫 Parking Service -** 此处，提供"负载级别"。
    
- **中介服务器和 PSTN -** 想要使用的每个中介服务器都需要自己的 PSTN 模拟器。 确定要用于模拟器的客户端后，配置中介服务器以将呼叫路由到已配置的 PSTN 模拟器上的该计算机。 单击" **添加** "按钮以配置中介服务器的值。
    
    > [!NOTE]
    > 每个方案旁边都有一个"高级"按钮。 "高级"对话框包含特定于每个方案的设置，这些设置可更改"压力和性能工具"的行为并启用自定义。 > 对于"语音方案"选项卡上的每个方案，如果"负载级别"的值为 **"** 自定义"，则使用"高级"对话框中的相应字段计算对话速率。 字段名称可能会有所不同，具体取决于方案，但字段说明将状态：注意 只有在从下拉菜单中选择了"自定义"时，才能使用  *此数字*  。
  
#### <a name="web-app-tab"></a>"Web 应用"选项卡

!["加载配置"工具，"Web 应用"选项卡。](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
Web App 支持通过安装在前端服务器上 (UCWA) 统一通信 Web API 会议方案。 使用"Web 应用"选项卡配置所有与 Web 应用相关的方案。 选项有：
  
- **常规 Web App 设置 -** 单击 **"设置"** 按钮，将 **ReachTargetServerUrl** 设置为前端池 VIP 的目录池虚拟 IP (VIP) 。
    
- **应用程序共享 -** 选择"负载级别"的值。
    
- **数据协作 -** 选择"负载级别"的值。
    
- **即时消息 -** 选择"负载级别"的值。
    
- **语音会议 -** 选择"负载级别"的值。
    
> [!NOTE]
> 每个方案旁边都有一个 **"** 高级"按钮。 高级对话框包含特定于每个方案的值，这些值将更改压力和性能工具的行为并启用自定义。> 对于每个 Web 应用方案，如果"负载级别"为 **"** 自定义"，则使用 **ConversationsPerHour** 字段中指定的值，而不是默认值。
  
#### <a name="mobility-tab"></a>"移动性"选项卡

使用此选项卡可配置所有与移动相关的方案。
  
!["加载配置"工具"移动性"选项卡。](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
此处的选项包括：
  
- **通用移动性设置 -** 单击 **"设置"，** 将字段 UcwaTargetServerUrl 设置为控制器池虚拟 IP (VIP) 或前端池 VIP。
    
- **状态和 P2P 即时消息/音频 -** 选择"负载级别"的值以启用移动模拟。
    
> [!NOTE]
> 每个方案旁边都有一个 **"** 高级"按钮。 高级对话框包含特定于每个方案的值，这些值将更改压力和性能工具的行为并启用自定义。> 对于每个移动方案，如果"负载级别"为 **"** 自定义"，则使用 **ConversationsPerHour** 字段中指定的值，而不是默认值。
  
#### <a name="summary-tab"></a>"摘要"选项卡

"摘要"选项卡指示要用于每种方案的用户。
  
!["加载配置"工具"摘要"选项卡。](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
"摘要"选项卡指示要用于每种方案的用户。 
  
可以手动配置用户编号范围，方法是选中"启用自定义用户范围生成"复选框，然后双击表中包含要自定义的用户范围的方案。
  
Check **(RunClient.bat) Add sign-in delay when starting** in order to include delay in the generated batch files to correspond to the sign-in rate. 这有助于防止登录大量用户时出现服务器过载。
  
单击 **"生成** 文件"，然后选择要生成配置的文件夹。 成功创建文件后，将显示一个对话框。
  
!["已成功生成加载配置文件"消息框。 只需单击"确定"。](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a>运行 LyncPerfTool
<a name="BKMK_RunTool"> </a>

在运行 2015 Stress and Performance Tool Skype for Business Server 之前，你需要创建用户、联系人和 (LyncPerfTool.exe) 。 有关使用工具执行这些操作的详细信息，[请参阅本文前面](using-the-tool.md#BKMK_CreateUsersAndContacts)介绍的创建用户和联系人和[](using-the-tool.md#BKMK_UserProfile)配置用户配置文件。 运行这些工具还会生成一个文件，该文件将随 Stress and Performance 工具一起运行，作为包含所需参数的批处理文件的一部分。
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a>运行 Skype for Business Server 2015 压力和性能工具

Load Configuration (UserProfileGenerator.exe) 创建一个批处理文件，该文件通过注册性能计数器和加载 XML 配置文件 (LyncPerfTool.exe) 运行 Stress and Performance tool (LyncPerfTool.exe) 。 批处理文件将运行每个配置文件LyncPerfTool.exe一个数据库实例。 若要运行批处理文件，请按照以下步骤操作：
  
### <a name="run-the-stress-and-performance-test"></a>运行压力和性能测试

1. 将包含配置文件夹和文件的文件夹复制到每个客户端计算机LyncPerfTool.exe目录中。  (例如，如果您在名为 1.28_13.16.16 的文件夹中生成了配置文件，请将其复制到包含 LyncPerfTool.exe 的文件夹。 在每个客户端上执行) 
    
2. 导航到客户端文件夹并运行 **RunClient 批处理** 脚本。 You can double-click the batch file in Windows Explorer and it will run all of the configuration files for that client. 您也可以使用下面的语法从客户端文件夹运行脚本：
    
   ```console
   RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
   ```

若要直接运行 Stress and Performance 工具，请打开命令提示符，在命令行 (并首次执行此操作时，请确保注册性能计数器，如本主题稍后的注释  `regsvr32 /i /n /s LyncPerfToolPerf.dll`) ：
  
```console
LyncPerfTool.exe /file:IM_client0.xml
```

若要让该工具显示配置文件中的值，请包含上述命令中的 参数  `/displayfile` ，以便其外观如下所示：
  
```console
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

若要  *结束*  该过程，请按 Ctrl+C。
  
> [!NOTE]
> 在直接运行 Stress and Performance 工具之前，必须通过以下命令注册性能计数器：  `regsvr32 /i /n /s LyncPerfToolPerf.dll`
  
> [!NOTE]
> 你启动的"压力和性能"工具的每一个实例将立即开始登录用户，通常以每秒一个用户的速度登录。 
  
池的用户登录峰值速率大约是每秒 12 个。 这意味着，当用户仍在登录时，不应同时启动 LyncPerfTool.exe 12 个实例。 1，000 个用户大约需要 20 分钟才能以每秒一个的速度完全登录。
  
## <a name="interpreting-the-results"></a>解释结果
<a name="BKMK_Interpret"> </a>

The Skype for Business Server 2015 Stress and Performance Tool has many counters that can help you understand what the client is doing， and whether it's encountering issues.
  
### <a name="client-counters"></a>客户端计数器

每个运行LyncPerfTool.exe实例都有一个单独的计数器实例。 每个实例都按其进程 ID 命名。 如果客户端过载，则可能会发生其他问题。 若要防止这些问题：
  
- 监视客户端计算机上的 CPU 和内存使用率。 如果 CPU 始终超过 90%，请减少用户数。
    
- 当内存占用量较高时，如果页面文件的空间开始不足，则可能会遇到问题。 验证"提交费用"未达到计算机上的限制。 如果运行的是内存限制，请考虑增加页面文件大小或减少用户数。
    
以下是关键性能计数器的列表：
  
**常规信息**

|**性能计数器**|**说明**|
|:-----|:-----|
|花费的时间（以分钟数表示）  <br/> |启动流程后所花的时间。  <br/> |
|Active Endpoints  <br/> |当前连接到服务器的终结点数。  <br/> |
|无法进行徽标  <br/> |终结点登录失败总数。  <br/> |
|登录尝试  <br/> |终结点登录尝试总数。  <br/> |
|Endpoints Disconnected  <br/> |已断开连接的终结点总数。  <br/> |
   
**状态信息**

|**性能计数器**|**说明**|
|:-----|:-----|
|SetPresence 调用  <br/> |总状态更改尝试次数。 有关不同类型的状态更改，请参阅 SetPresence (Presence Type) Calls Performance Counter。  <br/> |
|SetPresence 的 NNN 响应  <br/> |从服务器收到的 nnn 响应代码总数。  <br/> |
|GetPresence 调用  <br/> |获取状态请求尝试总数。  <br/> |
|GetPresence 的 NNN 响应  <br/> |从服务器收到的 nnn 响应代码总数。  <br/> |
   
**通讯簿服务信息**

|**性能计数器**|**说明**|
|:-----|:-----|
|ABS Full/Delta File Downloads Attempted  <br/> |尝试的完整或增量文件下载请求总数。  <br/> |
|ABS 完整/增量文件下载成功  <br/> |尝试的完整或增量文件下载请求总数。  <br/> |
|通讯簿 Web 查询服务相关计数器  <br/> |通讯簿文件下载相关计数器。  <br/> |
|ABS WS 调用已尝试  <br/> |尝试的通讯簿 Web 查询服务请求总数。  <br/> |
|ABS WS 调用成功  <br/> |返回成功响应代码的通讯簿 Web 查询服务请求总数。  <br/> |
|ABS WS 调用失败  <br/> |返回错误响应代码的通讯簿 Web 查询服务请求总数。  <br/> |
   
> [!NOTE]
> 此类别包括用于监视通讯簿服务 (ABS) 下载和通讯簿 Web 查询服务请求的计数器。 
  
**通讯组列表 (DL) 信息**

|**性能计数器**|**说明**|
|:-----|:-----|
|尝试的呼叫  <br/> |尝试的 DLX (展开) 的通讯组列表扩展总数。  <br/> |
|Calls Succeeded  <br/> |返回成功响应代码的 DLX Web 服务请求总数。  <br/> |
|呼叫失败  <br/> |返回错误响应代码的 DLX Web 服务请求总数。  <br/> |
   

  
> [!NOTE]
> 下面列出的性能计数器报告启用这些方案时所有 IP 语音 (VoIP) 呼叫（包括中介服务器、A/V 会议服务器、边缘服务器、响应组应用程序和会议 自动助理 的呼叫）的号码。 
  
**VoIP 基本信息**

|**性能计数器**|**说明**|
|:-----|:-----|
|呼叫活动  <br/> |当前正在进行的传入/传出语音呼叫总数。  <br/> |
|已终止呼叫  <br/> |已终止的传入/传出语音呼叫总数。  <br/> |
|拒绝呼叫  <br/> |拒绝的传入语音呼叫总数。  <br/> |
|已尝试传入/传出呼叫  <br/> |尝试传入/传出语音呼叫的总数。  <br/> |
|建立的传入/传出呼叫  <br/> |建立的传入/传出语音呼叫总数。  <br/> |
|收到的呼叫 NNN  <br/> |从服务器收到的 nnn 响应代码总数。  <br/> |
|VoIP 传递 (%)   <br/> |已建立呼叫总数/已尝试呼叫总数。  <br/> |
   
**响应组服务呼叫信息**

|**性能计数器**|**说明**|
|:-----|:-----|
|呼叫活动  <br/> |响应组应用程序的活动呼叫总数。  <br/> |
|尝试的呼叫  <br/> |尝试的呼叫总数。  <br/> |
   
**即时消息 (IM) 呼叫信息**

|**性能计数器**|**说明**|
|:-----|:-----|
|呼叫活动  <br/> |正在进行的传入/传出即时消息呼叫总数。  <br/> |
|已终止呼叫  <br/> |已终止的传入/传出即时消息呼叫总数。  <br/> |
|收到的呼叫 NNN  <br/> |从服务器收到的 nnn 响应代码总数。  <br/> |
|IM 消息接收/发送  <br/> |所有会话接收或发送的消息总数。  <br/> |
|已尝试传入/传出呼叫  <br/> |尝试传入/传出即时消息呼叫的总数。  <br/> |
|建立的传入/传出呼叫  <br/> |建立的传入/传出即时消息呼叫总数。  <br/> |
   
**应用共享呼叫信息**

|**性能计数器**|**说明**|
|:-----|:-----|
|呼叫活动  <br/> |正在进行的传入/传出应用程序共享呼叫总数。  <br/> |
|已终止呼叫  <br/> |已终止的传入/传出应用程序共享呼叫总数。  <br/> |
|收到的呼叫 NNN  <br/> |从服务器收到的 nnn 响应代码总数。  <br/> |
|已尝试传入/传出呼叫  <br/> |尝试传入/传出应用程序共享呼叫的总数。  <br/> |
|建立的传入/传出呼叫  <br/> |建立的传入/传出应用程序共享呼叫总数。  <br/> |
   
**CAA 呼叫信息**

|**性能计数器**|**说明**|
|:-----|:-----|
|呼叫活动  <br/> |当前正在进行的 PSTN 呼叫的传入/传出公用 (电话) 呼叫总数。  <br/> |
|已终止呼叫  <br/> |已终止的传入/传出 PSTN 呼叫总数。  <br/> |
|已尝试传入/传出呼叫  <br/> |尝试传入/传出 PSTN 呼叫的总数。  <br/> |
|建立的传入/传出呼叫  <br/> |建立的传入/传出 PSTN 呼叫总数。  <br/> |
   
**会议信息**

|**性能计数器**|**说明**|
|:-----|:-----|
|活动即时消息会议  <br/> |正在进行的即时消息会议总数。  <br/> |
|活动音频/视频会议  <br/> |A/V 会议持续 (音频/视频) 总数。  <br/> |
|活动应用程序共享会议  <br/> |正在进行的应用程序共享会议的总数。  <br/> |
|参与者数量  <br/> |当前连接到会议的参与者总数。  <br/> |
|会议计划失败  <br/> |尝试安排会议时的总失败次数。  <br/> |
|加入会议失败  <br/> |尝试连接到会议时的总失败次数。  <br/> |
   
**UCWA 客户端计数器**

|**性能计数器**|**说明**|
|:-----|:-----|
|IMMCU 联接成功总数  <br/> |已加入即时消息会议的总数。  <br/> |
|DMCU 联接成功总数  <br/> |加入的 A/V 会议总数。  <br/> |
   

