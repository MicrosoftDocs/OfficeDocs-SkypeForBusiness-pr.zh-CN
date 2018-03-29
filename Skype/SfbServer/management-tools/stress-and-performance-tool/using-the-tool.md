---
title: Using the Skype for Business Server 2015 Stress and Performance Tool
ms.author: heidip
author: microsoftheidi
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93f42230-24a2-418d-9770-bf4670a9d78f
description: To run the Skype for Business Server 2015 Stress and Performance Tool, you'll need to be able to manage both users, contacts and user profiles, configure the tool for running, and then review the output or results that are produced by the tool.
ms.openlocfilehash: 5f73ef6733c2f09cdf3e06bc8a6495c743d8b423
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Using the Skype for Business Server 2015 Stress and Performance Tool
 
To run the Skype for Business Server 2015 Stress and Performance Tool, you'll need to be able to manage both users, contacts and user profiles, configure the tool for running, and then review the output or results that are produced by the tool.
  
There are four areas involved with running the Skype for Business Server 2015 Stress and Performance Tool (the executable is LyncPerfTool.exe):
  
- [Create Users and Contacts](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [Configure User Profile](using-the-tool.md#BKMK_UserProfile)
    
- [Run LyncPerfTool](using-the-tool.md#BKMK_RunTool)
    
- [Interpreting the Results](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a>Create Users and Contacts
<a name="BKMK_CreateUsersAndContacts"> </a>

You need to use the Skype for Business Server 2015 (SB 2015) User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts for your stress and performance testing.
  
This is a list of helpful terms that might be useful as you read through the topics:
  
- **Organizational Unit** - The Active Directory Domain Services (AD DS) organizational unit (OU).
    
- **Federated / Cross Pool** - Users who can communicate with users from other Instant Messaging (IM) services.
    
- **Distribution Lists** - Or DLs. These are objects in AD DS that contain a list of AD DS users. They're used to facilitate communications across groups of people.
    
- **Location Info Service** - The Skype for Business Server 2015 service that, when it's enabled and configured per phone, allows for the retrieval of physical location for Enhanced 911 (E911) services.
    
- **U.S. Phone Numbers** - Phone numbers assigned to user in addition to the SIP URI that's used for routing inbound and outbound calls in Reverse Number Lookup (RNL).
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Create Users and Contacts by using UserProvisioningTool.exe

> [!NOTE]
> Before you even begin, be absolutely sure you're logged in as a member of the Domain Admins security group to run this tool. You need to do this, because you're going to be creating Active Directory users. 
  
You have to use the Skype for Business Server User Provisioning Tool to create users and contacts for load simulation.
  
The **Skype for Business Server User Provisioning Tool** is installed with the **Skype for Business Server Stress and Performance Tool** package. Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server you intend to test.
  
You can start the Skype for Business Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\LyncStress) on the Front End Server or on the Standard Edition server.
  
> [!IMPORTANT]
> When you create a large number of users (for example, 10,000 or more), run the UserProvisioningTool.exe. You'll need to do this because the tool will be creating and configuring  *new*  AD users.
  
When the User Provisioning Tool opens, click Configuration and select the Load Configuration. 
  
To begin configuring users and contacts, load the default file included with the package, called "SampleData.xml". This will prepopulate fields with sample data that you'll need to change to make it relevant for your deployment.
  
If you have a preconfigured XML file that already contains your customized settings, you can load that file instead. Fill in the fields in the User Provisioning Tool, as described in the sections below.
  
### <a name="to-configure-server-options"></a>要配置服务器选项：

1. In the **Front End Pool FQDN** field, type the fully qualified domain name (FQDN) of the Standard Edition server, or the Front End pool where you want to host the users.
    
2. In the **User Name Prefix** field, type a prefix that you want to use to bust your user names for testing purposes (such as "TestUser").
    
3. In the **Password** field, type a password that will be used across all the test user accounts.
    
4. In the **Account Domain** field, type the domain name of your current AD domain (the one in which you want to create your test users).
    
5. In the **Organizational Unit** field, type the name of the AD domain where you want to create these test users. (If the OU doesn't already exist, it'll be created for you).
    
6. In the **Phone Area Code** field, type the three-digit area code to be used across all test user accounts. Make certain that the area code you chose doesn't conflict with other users' area codes in AD.
    
7. Click to select the **Voice Enabled** check box, if you want to enable the test users for Enterprise Voice.
    
8. In the **Number of Users** field, give the total number of test users you want to create.
    
9. In the **Start Index** field, give the starting number that'll be used as a suffix to the user name prefix (for example, the prefix is "TestUser", and the first name will end in "0" in the example below.)
    
     ![显示“创建用户”选项卡的“用户设置”工具。](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a>Create Users button

When you click on the **Create Users** button, the input parameters you've entered are validated. If there are any validation errors, you'll be prompted to fix them. Or, if all the values are correct, users will start appearing in AD (in whichever OU you specified). You'll see a progress bar at the bottom of the tool as it runs. Don't close the application while the progress bar is active.
  
User creation takes time, so please plan accordingly. This process can take anywhere from several minutes for a few users, to a few hours for a large number of users.
  
If you don't have access to the AD Domain Controller in your test environment, you can still validate user creation by logging in as one of the users in the range of users you specified to create. Remember to use the prefix, and the suffix, along with the @sipDomain as the username. Here is an example:  *TestUser20@contoso.net*  .
  
> [!NOTE]
> If the users already exist, clicking the Create Users button will update them with any configuration changes. 
  
#### <a name="delete-users-button"></a>Delete Users button

When you click on the **Delete Users** button, the tab's input parameters will be validated. If there are validation errors, you'll be prompted to fix them, and if the input values are correct, the specified test users will be disabled and deleted from Active Directory. Again, a progress bar will appear on the bottom of this tab, and you shouldn't close the application while the progress bar is active.
  
> [!NOTE]
> Only U.S.-formatted phone numbers are supported. Phone numbers are always assigned to users, and all users created by UserProvisioningTool.exe are enabled for Enterprise Voice by default. Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls. For this reason,  *every user*  must have a *unique phone number*  .
  
> [!NOTE]
> **如果您需要两次创建用户时，该命令将失败，除非您使用不同的区号，或如果以前的用户已禁用通过禁用 CsUser cmdlet。**
  
> [!IMPORTANT]
> Before you create contacts, you first need to complete user replication (which is done from the Users tab). 
  
> [!IMPORTANT]
> If you've just created your users, you'll need to wait until Skype for Business Server replication completes and populates the user accounts in the database. **If the users haven't finished replicating, you'll see an error.** You'll know when users have finished replicating if the Skype for Business Server 2015 Front End service has started, or by successfully running the Get-CsUser cmdlet on the last user of the total number you specified.
  
#### <a name="contacts-creation-tab"></a>联系人创建选项卡

This tab lets you give users' contacts details for your testing.
  
![显示“创建内容”选项卡的“用户设置”工具。](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a>To configure users' contacts, do the following:

1. In the **Average Contacts per User** field, enter the average number of contacts to populate in contact lists for each user.
    
2. 如果您想要创建相同数量的每个用户的联系人，请选择**固定**复选框。 If you want to vary the number of contacts created for users, clear that check box.
    
3. 在**每个用户的平均联系组**字段中，输入每个用户的联系人组的数目。 该数字必须小于**平均每个用户的联系人**。
    
4. In the **Federated / Cross Pool Contacts Percentage** field, give a number between 0 and 100. 将与联盟用户创建联系人的百分比。
    
5. 在**联合 / 交叉池用户前缀**字段中，为联盟将被添加到本地用户的联系人列表的用户提供用户名。
    
6. In the **Federated / Cross Pool User SIP Domain** field, give the SIP Domain Name of the federated users.
    
7. 在**创建用户**选项卡中确保信息正确无误。 您的联系人将从创建用户选项卡上的值进行创建。
    
8. 单击以开始创建联系人**创建联系人**。 此过程可能需要几分钟的时间。 它完成后，一个对话框将出现并显示消息之后,"操作已成功完成。" 您可以验证所创建的登录用户从创建用户选项卡创建的联系人。
    
> [!NOTE]
> 创建联系人后，此工具将所有前端服务器重新启动目标池中。 这取决于多少个联系人创建此操作可能需要更长的时间 （最多 2 小时） 的开始，前端服务器。 
  
#### <a name="distribution-list"></a>通讯组列表

Skype 业务服务器 2015年的压力和性能工具可以模拟 Skype 业务 2015年客户机中的通讯组列表 (DL) 扩展功能。 如果您不想要启用 DL 展开用户配置工具中的，您可以跳过此步骤。
  
![显示“创建通讯组列表”选项卡的“用户设置”工具。](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
通讯组列表选项卡允许您创建将用于通讯组列表扩展功能的压力和性能工具的 Dl。 在创建之前 DLs，业务服务器 2015年的 Skype 需要部署，包括在运行 ForestPrep。 如果不这样做，DL 特性将不存在于 AD 架构，因此，该工具将无法创建 Dl。
  
### <a name="to-configure-distribution-lists"></a>若要配置通讯组列表：

1. 在**数字通讯组列表中的**字段中，为您想要创建的 Dl 的总数 （这里的建议是开头是双倍数量的用户，您有一个值）。
    
2. 在**通讯组列表前缀**字段中，输入您创建的所有 Dl 都有，例如*testDL*的前缀。 这意味着，在 100 DLs DL 名称将如下所示： testDL0，testDL1，高达 testDL99。
    
3. 在**Dist.列表中最小的成员**字段中，输入用户放入每个 DL 中的最小数目。
    
4. 在**Dist.列表中的最大成员**字段中，输入要在每个 DL 中添加用户的最大的数目。
    
#### <a name="create-distribution-lists-button"></a>创建通讯组列表的按钮

当单击创建通讯组列表按钮时，该工具将查询活动目录，是否通讯组列表匹配的前缀和编号已经存在，请参阅。 该工具会创建不存在所有 Dl。 当这些新创建的通讯组列表中添加成员，它将从创建用户选项卡上指定的范围中选择的用户。
  
#### <a name="location-info-service-config-tab"></a>位置信息服务配置选项卡

为业务服务器 2015年压力和性能工具 Skype 的位置信息服务还可以生成虚拟配置文件。 注意，位置信息服务通常并不会显著影响性能的服务器上。 
  
![显示“位置信息服务配置”选项卡的“用户设置”工具。](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
如果选择此功能进行测试，填写在窗体中的值，然后单击生成 LIS 配置文件按钮，将创建。CSV 文件调用：
  
- LIS_Subnet.csv
    
- LIS_Switches.csv
    
- LIS_Ports.csv
    
- LIS_WAP.csv
    
若要导入这些文件到 LIS 数据库使用这些 PowerShell cmdlet:
  
- 一组 CsLisSubnet
    
- 一组 CsLisSwitch
    
- 一组 CsLisPort
    
- 一组 CsWirelessAccessPoint
    
## <a name="configure-user-profile"></a>配置用户配置文件
<a name="BKMK_UserProfile"> </a>

您的用户 （通过用户创建工具） 创建后可以具有的业务服务器 2015年负载配置工具 (UserProfileGenerator.exe) 的 Skype 来配置用户配置文件。
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a>运行业务服务器 2015年负载配置工具 Skype

启动加载配置工具 (UserProfileGenerator.exe)，并填写选项卡。 此工具创建一个目录为每个客户端计算机，您将需要运行您的模拟。 每个客户端目录附带了一个脚本来启动 Skype 业务服务器 2015年的压力和性能工具 (LyncPerfTool.exe)。 下面的章节将提供如何填写业务服务器 2015年负载配置工具 Skype 的每个选项卡上的字段的示例。
  
> [!IMPORTANT]
> 加载配置工具 (UserProfileGenerator.exe) 中使用的特定于用户的值必须与在 Skype 业务 2015年用户创建工具 (UserProvisioningTool.exe) 为指定的值匹配为池。 
  
#### <a name="common-configuration-tab"></a>常见的配置选项卡

负载配置工具的**通用配置**选项卡如下所示。 填写的字段的常见配置选项卡，如以下步骤所述。
  
![显示“常见配置”选项卡的“用户设置”选项卡。](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. 在**可用计算机数量**字段中，键入您想要使用运行压力和性能工具 (LyncPerfTool.exe) 的计算机的数量。 我们建议您拥有一台计算机，您可以模拟，每个 4500 用户，但该数目可能会有所不同，如果降低负载级别，或者使用工具的可用功能 （在一般情况下选项卡上设置负载级别） 的子集。
    
2. 在**用户名称的前缀**字段中，输入用户名字段的所有用户的前缀。 记录在统一资源标识符 (URI) 将是： *UserPrefix [用户启动索引...（用户 1 号]）@User 域*，例如 myUser009@Contoso.com。
    
3. 在**所有用户的密码**字段中，输入用户的创建期间使用的密码。 如果将此字段保留为空将作为密码设置用户名。
    
4. 在**用户开始索引**字段中，输入要配置的第一个用户的索引。 您可以配置不同的范围，为不同类型或级别的负载，但一旦您想要配置每个范围，您必须运行加载配置工具 (UserProfileGenerator.exe)。
    
5. 在**用户数量**字段中，输入您要配置的用户的总数。
    
6. 在**用户域**字段中，输入用于 SIP URI 的域。 这用来构造 SIP URI 的每个用户在登录 Skype 业务服务器 2015年前端服务器或标准版服务器，可能会有所不同从帐户域。
    
7. 在**帐户域**字段中，输入 AD DS 域登录。
    
8. **MPOP 百分比**（多个存在点百分比） 字段中，为提供值的多个机器或设备，例如 10%从登录的用户的百分比。
    
9. **登录 / 秒 （每个实例）**字段中输入并发的终结点的最大数量。 这是最大数目为您的用户记录单元和建议是小于 / 等于 2，每秒的速率 (< = 2)。
    
10. 在**访问代理服务器或池的 FQDN**字段中，输入所需的客户端连接到的服务器的完全合格的域名称 (FQDN)。 如果从外部登录的用户，您需要键入访问代理服务器。 如果用户是内部的给他们的企业版池或标准版服务器的 FQDN。
    
11. 在**端口**字段中，输入您想让用户使用的 SIP 的端口 （此处的默认值为 5061）。
    
12. 对于**外部网络服务器设置**字段中，提供访问代理服务器或池的 FQDN，再次，**端口**。 这些设置仅用于外部终结点的负载模拟。
    
#### <a name="general-scenarios-tab"></a>一般情况下选项卡

![显示“常规方案”选项卡的“加载配置”工具。](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
您可以确定您想要运行或将禁用所提供的一般方案的每个配置的负载水平和参数。 下面是您的常规选项：
  
> [!NOTE]
> 负载级别值的所有字段，但本地信息服务被**禁用**，**低**、**中**、**高**、 或**自定义**。 如果您选择但已禁用任何设置，都生成每个客户端配置。 高会导致最大支持服务器的负担;介质是 60%的高负载;低为 30%。 
  
- **即时消息的**这包括对等和会议;对于负载级别选择适当的值。
    
- **音频会议的**选择音频会议*只有*一个负载级别。 **声音方案**一节中，将稍后处理点到点调用。 打开**高级**选项卡启用多视图。
    
- **应用程序共享的**选择应用程序共享一个负载级别。
    
- **数据协作-**选择数据协作，其中包括数据会议的负载级别。
    
- **通讯组列表扩展-**单击**高级**按钮，并使用相同用户创建工具 (UserProvisioningTool.exe) DL 选项卡上配置的值填充该字段。 选择负载级别。
    
- **地址簿 Web 查询-**这是地址簿查找服务，而不是下载通讯簿文件。 如果您想要启用此通讯簿文件下载，请单击**高级**按钮，并将**EnableABSDownload**设置为 True。 对于负载级别赋予一个值。
    
- **响应组服务-**单击**高级**按钮并指定响应组已创建时设置响应组服务代理的 Uri。 您必须选择至少一个响应组。 若要使用的详细信息，请用分号分隔的响应组。 **RGSUriSuffixStartIndex**和**RGSUriSuffixEndIndex**更新为实际的值。 选择负载级别。
    
- **位置信息服务-**选择启用或禁用的负载程度。
    
> [!NOTE]
> 每个方案都有高级按钮旁边，和一套使变体设置为默认设置的复选框。 
  
- 选择*特别*将允许生成模拟的会议，将整个小时创建工具。
    
- 选择*大型会议*表示，将模拟一个大型的会议方案。
    
-  *外部*通知还模拟外部用户工具。
    
这些按钮和复选框都是特定于每个方案的额外值将更改的压力和性能工具的行为和使自定义项。
  
对于每个方案 （除了位置信息服务） 的一般方案选项卡上，如果负载级别的值是**自定义**、 然后对话速率将计算在高级对话框中使用的相应字段。 字段名称可能会有所不同，具体取决于该方案，但将状态字段的说明：*如果从下拉菜单中选择自定义只使用注意此数量*。
  
**高**、**中等**和**低**的值将改变每个嵌入的所有方案，一个都平衡的用户模型的模态的对话率。 如果需要更改每由于预期使用情况的不同成像设备的负载级别，请使用自定义对话速度。
  
#### <a name="voice-scenarios-tab"></a>声音方案选项卡

这是您所有与语音相关的方案的配置的选项卡。
  
![“加载配置”工具“语音方案”选项卡。](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
选项为：
  
- **VoIP 的**单击**高级**按钮，添加 PhoneAreaCode 和 LocationProfile （拨号计划） 字段的值。 对于负载级别，本文还提供一个值。 如果您选择为 VoIP 或 UC/PSTN 网关启用，然后公共交换电话网络 (PSTN) 为统一通信 (UC) 负载级别将生成配置文件来模拟外部调用。
    
- **UC/PSTN 网关-**您需要选择负载级别值，并且之外其他禁用选择任何内容，您还需要通过单击**高级**按钮提供 PSTN 区域代码的值。 中介服务器和 PSTN 下单击**添加**。 请确保已配置为区号的路由。
    
    > [!TIP]
    > 可用于任何一个 Skype 业务控制面板或 Skype 业务管理外壳程序的验证语音路由配置。 
  
- **会议助理-**对于负载级别提供一个值。 已禁用之外的任何值都将启用**电话号码**字段。 请输入您想要使用自动助理的电话号码。 单击**高级**，并为**LocationProfile**字段赋予一个值。
    
- **停车服务的调用**在这里，提供负载级别。
    
- **中介服务器和 PSTN 的**每个要使用的中介服务器需要自己 PSTN 模拟器。 已确定哪个客户端，您将使用的模拟器后，配置中介服务器来路由呼叫到该计算机在 PSTN 模拟器上您配置。 单击**添加**按钮以中介服务器的配置的值。
    
    > [!NOTE]
    > 每个方案都有它旁边位于高级按钮。 高级的对话框包含设置特定于每个方案，改变压力和性能工具的行为，并使自定义。 > 声音方案选项卡上的每种情况下，如果负载级别的值是**自定义**、 然后对话速率将计算通过使用在高级对话框中的相应字段。 字段名称可能会有所不同，具体取决于该方案，但将状态字段的说明：*如果从下拉菜单中选择自定义只使用注意此数量*。
  
#### <a name="web-app-tab"></a>Web 应用程序选项卡

![“加载配置”工具“Web 应用”选项卡。](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
Web 应用程序支持通过统一通信 Web API (UCWA) 服务器安装在前端服务器上的会议方案。 使用 Web 应用程序选项卡来配置所有 web 应用程序相关的方案。 选项包括：
  
- **常规 Web 应用程序设置-**单击**其他设置**按钮，将**ReachTargetServerUrl**设置为目录池虚拟 IP (VIP) 的前端池 VIP。
    
- **应用程序共享的**为负载级别中选择一个值。
    
- **数据协作-**为负载级别中选择一个值。
    
- **即时消息的**为负载级别中选择一个值。
    
- **语音会议-**为负载级别中选择一个值。
    
> [!NOTE]
> 每个方案都有位于它旁边的**高级**按钮。 高级的对话框包含特定于每个方案的值将更改的压力和性能工具的行为，并启用自定义项。 > 对于每个 Web 应用程序方案，如果负载级别**自定义**、 然后指定的值在**ConversationsPerHour**字段使用而不是默认值。
  
#### <a name="mobility-tab"></a>移动选项卡

使用此选项卡来配置所有的与移动相关的方案。
  
![“加载配置”工具“移动性”选项卡。](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
此处的选项是：
  
- **常规的移动设置-**单击**其他设置**，将 UcwaTargetServerUrl 字段设置为主任池虚拟 IP (VIP) 或前端池 VIP。
    
- **状态和 P2P 即时消息传递/音频-**选择要启用移动模拟负载级别的值。
    
> [!NOTE]
> 每个方案都有位于它旁边的**高级**按钮。 高级的对话框包含特定于每个方案的值将更改的压力和性能工具的行为，并启用自定义项。 > 对于每一个行动方案，如果负载级别**自定义**、 然后指定的值在**ConversationsPerHour**字段使用而不是默认值。
  
#### <a name="summary-tab"></a>摘要选项卡

摘要选项卡表明哪些用户可以使用每个方案。
  
![“加载配置”工具“摘要”选项卡。](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
摘要选项卡表明哪些用户可以使用每个方案。 
  
也可以手动配置用户的数字范围，通过选择**启用自定义用户范围生成**复选框，然后双击您要自定义的用户范围的表中的方案。
  
要包括在生成的批处理文件中对应的注册率延迟检查**(RunClient.bat) 添加登录延迟启动时**。 这将有助于在大量用户签名时可以防止服务器超载。
  
单击**生成文件**并选择要用来生成配置的文件夹。 已成功创建您的文件时，将出现一个对话框。
  
![“已成功生成加载配置文件”消息框。只需单击“确定”。](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a>运行 LyncPerfTool
<a name="BKMK_RunTool"> </a>

您将需要在运行 Skype 业务服务器 2015年的压力和性能工具 (LyncPerfTool.exe) 之前创建的用户、 联系人和方案。 有关使用这些工具来执行这些操作的详细信息，请参阅[创建用户和联系人](using-the-tool.md#BKMK_CreateUsersAndContacts)和[配置用户配置文件](using-the-tool.md#BKMK_UserProfile)以前在这篇文章。 运行这些工具还将生成的文件，将压力和性能工具作为的一部分运行一个批处理文件与包含所需的参数。
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a>运行业务服务器 2015年压力和性能工具 Skype

加载配置工具 (UserProfileGenerator.exe) 创建的批处理文件中，您可以通过注册性能计数器和加载 XML 配置文件来运行压力和性能工具 (LyncPerfTool.exe)。 每个配置文件，该批处理文件运行 LyncPerfTool.exe 的一个实例。 若要运行该批处理文件，请执行以下步骤：
  
### <a name="run-the-stress-and-performance-test"></a>运行压力和性能测试

1. 将配置文件夹中的文件与文件夹复制到每台客户端计算机的 LyncPerfTool.exe 目录。 （例如，如果名为 1.28_13.16.16 的文件夹中生成的配置文件，该将文件夹复制到 LyncPerfTool.exe 文件夹中。 执行此操作在每个客户端上。）
    
2. 导航至客户端文件夹，然后运行**RunClient**批处理脚本。 您可以双击 Windows 资源管理器中的批处理文件，它将为该客户端运行的所有配置文件。 您可以通过使用以下语法从一个客户端文件夹运行脚本：
    
  ```
  RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
  ```

若要直接运行压力和性能工具，打开一个命令提示符并在命令行键入以下命令 (当第一次执行此操作，请务必注册的性能计数器和`regsvr32 /i /n /s LyncPerfToolPerf.dll`，如本主题中后面的注释中所示):
  
```
LyncPerfTool.exe /file:IM_client0.xml
```

若要让该工具在配置文件中显示的值，包括`/displayfile`参数在上述命令中，以便使其如下所示：
  
```
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

到*结束*该进程，请按 Ctrl + C。
  
> [!NOTE]
> 直接运行压力和性能工具之前, 您必须注册性能计数器通过下面的命令：`regsvr32 /i /n /s LyncPerfToolPerf.dll`
  
> [!NOTE]
> 启动压力和性能工具的每个实例将立即开始登录用户，通常以一个用户每秒的速率。 
  
用户登录用于峰值速率池是大约每秒 12。 这意味着您不应启动超过 12 LyncPerfTool.exe 实例在同一时间同时仍然登录用户。 一千的用户大约需要 20 分钟完全在一个每秒登录。
  
## <a name="interpreting-the-results"></a>解释结果
<a name="BKMK_Interpret"> </a>

为业务服务器 2015年压力和性能工具 Skype 有多个计数器，可帮助您了解客户机正在做什么，以及是否它会遇到的问题。
  
### <a name="client-counters"></a>客户端计数器

LyncPerfTool.exe 运行每个的实例都有一个单独的计数器实例。 每个实例名称由其进程 id。 如果客户端是重载可以出现其他问题。 若要防止发生这些问题：
  
- 监视客户端计算机上的 CPU 和内存使用情况。 如果 CPU 90%以上是以一致的方式，减少用户的数量。
    
- 如果内存需求量非常大，您可能会遇到问题中，如果页面文件开始用完所有空间。 确认提交费用不按计算机上的限制。 如果您正在运行内存限制为考虑增加页面文件的大小或降低用户的数量。
    
这里是关键性能计数器的列表：
  
**一般信息**

|**性能计数器**|**说明**|
|:-----|:-----|
|以分钟为单位的时间  <br/> |自从启动进程以来，所用时间。  <br/> |
|活动的终结点  <br/> |当前连接到的服务器终结点的数量。  <br/> |
|失败的登录  <br/> |端点登录失败的总次数。  <br/> |
|登录尝试  <br/> |终结点的登录尝试的总数。  <br/> |
|终结点断开连接  <br/> |已断开连接的终结点的总数。  <br/> |
   
**出席信息**

|**性能计数器**|**说明**|
|:-----|:-----|
|SetPresence 调用  <br/> |总次数存在更改尝试。 不同类型的状态更改，请参见 SetPresence （存在类型） 调用的性能计数器。  <br/> |
|SetPresence 的 NNN 响应  <br/> |Nnn 响应代码从服务器接收到的总数量。  <br/> |
|GetPresence 调用  <br/> |状态请求尝试获取的总数。  <br/> |
|GetPresence 的 NNN 响应  <br/> |Nnn 响应代码从服务器接收到的总数量。  <br/> |
   
**通讯簿服务信息**

|**性能计数器**|**说明**|
|:-----|:-----|
|ABS 完全/增量文件下载尝试  <br/> |尝试执行完整备份或增量文件下载请求的总数。  <br/> |
|ABS 完全/增量文件下载成功  <br/> |尝试执行完整备份或增量文件下载请求的总数。  <br/> |
|地址簿 Web 查询与服务相关的计数器  <br/> |通讯簿文件下载相关的计数器。  <br/> |
|ABS WS 调用尝试  <br/> |尝试的地址簿 Web 查询服务请求的总数。  <br/> |
|成功的 ABS WS 调用  <br/> |返回一个成功的响应代码的地址簿 Web 查询服务请求的总数。  <br/> |
|ABS WS 调用失败  <br/> |返回了错误响应代码的地址簿 Web 查询服务请求的总数。  <br/> |
   
> [!NOTE]
> 此类别包括一些计数器来监视通讯簿服务 (ABS) 文件下载和地址簿 Web 查询服务请求。 
  
**通讯组列表 (DL) 信息**

|**性能计数器**|**说明**|
|:-----|:-----|
|尝试调用  <br/> |尝试的通讯组列表扩展 (DLX) web 服务请求的总数。  <br/> |
|成功调用  <br/> |返回一个成功的响应代码的 DLX web 服务请求的总数。  <br/> |
|调用失败  <br/> |返回了错误响应代码的 DLX web 服务请求的总数。  <br/> |
   

  
> [!NOTE]
> 性能计数器下面列出报表编号所有语音 IP (VoIP) 的调用，包括调用中介服务器，A / V 会议服务器、 边缘服务器、 响应组的应用程序，以及会议自动助理，启用这些方案。 
  
**VoIP 基本信息**

|**性能计数器**|**说明**|
|:-----|:-----|
|调用活动  <br/> |当前正在进行调用总数传入/传出的声音。  <br/> |
|终止呼叫  <br/> |传入/传出语音呼叫总数已终止。  <br/> |
|调用被拒绝  <br/> |拒绝的语音来电总数。  <br/> |
|传入/传出呼叫尝试  <br/> |传入/传出语音呼叫尝试的总数。  <br/> |
|传入/传出呼叫建立  <br/> |传入/传出语音呼叫建立的总数量。  <br/> |
|调用接收的 NNN  <br/> |Nnn 响应代码从服务器接收到的总数量。  <br/> |
|VoIP 通过率 （%）  <br/> |总调用尝试建立总调用。  <br/> |
   
**响应组服务调用信息**

|**性能计数器**|**说明**|
|:-----|:-----|
|调用活动  <br/> |为响应组应用程序的活动调用的总次数。  <br/> |
|尝试调用  <br/> |尝试调用的总次数。  <br/> |
   
**即时消息 (IM) 调用信息**

|**性能计数器**|**说明**|
|:-----|:-----|
|调用活动  <br/> |不断传入/传出即时消息调用总数。  <br/> |
|终止呼叫  <br/> |传入/传出即时消息调用的总次数已终止。  <br/> |
|调用接收的 NNN  <br/> |Nnn 响应代码从服务器接收到的总数量。  <br/> |
|接收/发送的 IM 消息  <br/> |消息总数接收或发送的所有会话。  <br/> |
|传入/传出呼叫尝试  <br/> |传入/传出即时消息调用尝试的总数。  <br/> |
|传入/传出呼叫建立  <br/> |传入/传出建立即时消息调用的总次数。  <br/> |
   
**应用程序共享的呼叫信息**

|**性能计数器**|**说明**|
|:-----|:-----|
|调用活动  <br/> |不断传入/传出的应用程序共享的调用总数。  <br/> |
|终止呼叫  <br/> |总数已共享调用传入/传出应用程序终止。  <br/> |
|调用接收的 NNN  <br/> |Nnn 响应代码从服务器接收到的总数量。  <br/> |
|传入/传出呼叫尝试  <br/> |传入/传出的应用程序共享尝试调用的总次数。  <br/> |
|传入/传出呼叫建立  <br/> |传入/传出的应用程序共享建立的调用总数。  <br/> |
   
**CAA 呼叫信息**

|**性能计数器**|**说明**|
|:-----|:-----|
|调用活动  <br/> |目前正在进行调用传入/传出公用交换的电话网 (PSTN) 的总数。  <br/> |
|终止呼叫  <br/> |传入/传出 PSTN 呼叫总数已终止。  <br/> |
|传入/传出呼叫尝试  <br/> |传入/传出 PSTN 呼叫尝试的总数。  <br/> |
|传入/传出呼叫建立  <br/> |传入/传出 PSTN 呼叫建立的总数。  <br/> |
   
**会议信息**

|**性能计数器**|**说明**|
|:-----|:-----|
|活动的即时消息会议  <br/> |正在进行的即时消息会议的总次数。  <br/> |
|当前的音频/视频会议  <br/> |总数持续音频/视频 (A / V) 会议。  <br/> |
|活动应用程序共享会议  <br/> |日常应用程序共享会议的总次数。  <br/> |
|参与者人数  <br/> |当前连接到会议参与者的总数。  <br/> |
|会议计划失败  <br/> |尝试安排会议时失败的总次数。  <br/> |
|加入会议失败  <br/> |尝试连接到会议时失败的总数量。  <br/> |
   
**UCWA 客户端计数器**

|**性能计数器**|**说明**|
|:-----|:-----|
|总数 IMMCU 连接成功  <br/> |加入了即时消息会议的总次数。  <br/> |
|总数 DMCU 连接成功  <br/> |总数的 A / V 会议加入。  <br/> |
   

