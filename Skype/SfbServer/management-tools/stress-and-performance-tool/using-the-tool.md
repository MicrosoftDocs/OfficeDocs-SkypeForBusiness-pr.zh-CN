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
  
### <a name="to-configure-server-options"></a>To configure server options:

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
  
#### <a name="create-users-button"></a>创建用户按钮

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
> **If you have to create users twice, the command will fail unless you use a different area code, or if the previous users have been disabled by using the Disable-CsUser cmdlet.**
  
> [!IMPORTANT]
> 创建联系人之前，需要首先完成用户复制 （这通过用户选项卡）。 
  
> [!IMPORTANT]
> If you've just created your users, you'll need to wait until Skype for Business Server replication completes and populates the user accounts in the database. **If the users haven't finished replicating, you'll see an error.** 当用户完成复制如果 Skype 业务服务器 2015年前端服务已启动，或者成功上您指定的总数的最后用户运行 Get CsUser cmdlet，您就知道。
  
#### <a name="contacts-creation-tab"></a>联系人创建选项卡

此选项卡让您可以赋予用户的联系人详细信息的测试。
  
![显示“创建内容”选项卡的“用户设置”工具。](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a>要配置用户的联系人，请执行以下操作：

1. In the **Average Contacts per User** field, enter the average number of contacts to populate in contact lists for each user.
    
2. Select the **Fixed** check box if you want to create an equal number of contacts for every user. 如果您想要为用户创建的联系人的数目而有所不同，请清除该复选框。
    
3. In the **Average Contact Groups per User** field, enter the number of contact groups per user. This number needs to be smaller than **Average Contacts per User**.
    
4. In the **Federated / Cross Pool Contacts Percentage** field, give a number between 0 and 100. 将与联盟用户创建联系人的百分比。
    
5. 在**联合 / 交叉池用户前缀**字段中，为联盟将被添加到本地用户的联系人列表的用户提供用户名。
    
6. 在**联合 / 交叉池用户的 SIP 域**字段中，提供联盟用户的 SIP 域的名称。
    
7. In **User Creation** tab make sure the information is correct. Your contacts will be created from values on the User Creation tab.
    
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

The Skype for Business Server 2015 Stress and Performance Tool can also generate dummy configuration files for the Location Information Service. Note that the Location Information Service typically doesn't have significant performance impact on the servers. 
  
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
    
#### <a name="general-scenarios-tab"></a>General Scenarios tab

![显示“常规方案”选项卡的“加载配置”工具。](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
您可以确定您想要运行或将禁用所提供的一般方案的每个配置的负载水平和参数。 下面是您的常规选项：
  
> [!NOTE]
> Load level values for all fields but Local Information Services are **Disabled**, **Low**, **Medium**, **High**, or **Custom**. 如果您选择但已禁用任何设置，都生成每个客户端配置。 High results in the max supported load on the server; medium is 60% of high load; low is 30%. 
  
- **Instant Messaging -** This includes peer-to-peer and conferencing; choose the appropriate value for Load Level.
    
- **音频会议的**选择音频会议*只有*一个负载级别。 Peer-to-peer calls will be tackled a little later in the **Voice Scenarios** section. Open the **Advanced** tab to enable MultiView.
    
- **Application Sharing -** Choose a load level for application sharing.
    
- **数据协作-**选择数据协作，其中包括数据会议的负载级别。
    
- **通讯组列表扩展-**单击**高级**按钮，并使用相同用户创建工具 (UserProvisioningTool.exe) DL 选项卡上配置的值填充该字段。 Choose a load level.
    
- **Address Book Web Query -** This is the address book lookup service rather than the address book file download. 如果您想要启用此通讯簿文件下载，请单击**高级**按钮，并将**EnableABSDownload**设置为 True。 Give a value for load level.
    
- **Response Group Service -** Click the **Advanced** button and specify the URIs of the response groups you already created when you provisioned Response Group Service agents. 您必须选择至少一个响应组。 To use more, separate the response groups with semicolons. Update **RGSUriSuffixStartIndex** and **RGSUriSuffixEndIndex** to the actual values. Choose a load level.
    
- **Location Information Services -** Select a load level of either Enabled or Disabled.
    
> [!NOTE]
> Each of the scenarios has an Advanced button located next to it, and a set of check boxes that enable variations to the default setting. 
  
- Choosing  *Ad-hoc*  will allow the tool to generate simulation of conferences that will be created throughout the hour.
    
- Choosing  *Large Conf*  means that a Large Conference Scenario will be simulated.
    
-  *外部*通知还模拟外部用户工具。
    
These buttons and check boxes are extra values specific to each scenario and will change the behavior of the Stress and Performance Tool and make customization possible.
  
For each scenario on the General Scenarios tab (except for Location Information Services), if the value of Load Level is **Custom**, then the conversation rate will be calculated using the corresponding field in the Advanced dialog box. The field name may differ, depending on the scenario, but the field description will state:  *NOTE This number will only be used if Custom is selected from the drop-down menu*  .
  
The values **High**, **Medium**, and **Low**, will alter the conversation rates per modality in line with the User Model that is a balance of all the scenarios. If there's a need to change the load level per modality due to a difference in expected usage, use a Custom conversation rate.
  
#### <a name="voice-scenarios-tab"></a>声音方案选项卡

这是您所有与语音相关的方案的配置的选项卡。
  
![“加载配置”工具“语音方案”选项卡。](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
Your options are:
  
- **VoIP -** Click the **Advanced** button and add values for the PhoneAreaCode and LocationProfile (dial plan) fields. You'll also give a value for Load Level. If you choose a load level for VoIP or UC/PSTN Gateway enabled, then a public-switched telephone network (PSTN) to unified communications (UC) configuration file will be generated to simulate external calls.
    
- **UC/PSTN Gateway -** You need to choose a Load Level value, and when you choose anything other than Disabled, you've also got to supply a value for PSTN area code by clicking the **Advanced** button. Click **Add** under the Mediation Server and PSTN. Make sure you have a route configured for the area code.
    
    > [!TIP]
    > You can use either the Skype for Business Control Panel or Skype for Business Management Shell to verify your voice route configuration. 
  
- **Conferencing Attendant -** Supply a value for Load Level. Any value other than Disabled will enable the **Telephone Number** field. Enter the phone number of the Auto Attendant you want to use. Click **Advanced** and give a value for the **LocationProfile** field.
    
- **Call Parking Service -** Here, supply a Load Level.
    
- **Mediation Server and PSTN -** Each Mediation Server that you want to use needs its own PSTN simulator. After you've determined which client you're going to use for the simulator, configuration your Mediation Server to route calls to that computer on the PSTN Simulator you configured. Click the **Add** button to configure a value for the Mediation Server.
    
    > [!NOTE]
    > Each scenario has an Advanced button located next to it. Advanced dialog boxes contain settings specific to each scenario that change the behavior of the Stress and Performance Tool and enable customization. > For each scenario on the Voice Scenarios tab, if the value of Load Level is **Custom**, then the conversation rate will be calculated by using the corresponding field in the Advanced dialog box. The field name may differ, depending on the scenario, but the field description will state:  *NOTE This number will only be used if Custom is selected from the drop-down menu*  .
  
#### <a name="web-app-tab"></a>Web App tab

![“加载配置”工具“Web 应用”选项卡。](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
Web App supports conferencing scenarios through the Unified Communications Web API (UCWA) server that's installed on a Front End server. 使用 Web 应用程序选项卡来配置所有 web 应用程序相关的方案。 选项包括：
  
- **General Web App Settings -** Click the **Additional Settings** button and set the **ReachTargetServerUrl** to the Directory Pool virtual IP (VIP) of the Front End pool VIP.
    
- **Application Sharing -** Select a value for Load Level.
    
- **Data Collaboration -** Select a value for Load Level.
    
- **Instant Messaging -** Select a value for Load Level.
    
- **Voice Conferencing -** Select a value for Load Level.
    
> [!NOTE]
> Each of the scenarios has an **Advanced** button located next to it. 高级的对话框包含特定于每个方案的值将更改的压力和性能工具的行为，并启用自定义项。 > 对于每个 Web 应用程序方案，如果负载级别**自定义**、 然后指定的值在**ConversationsPerHour**字段使用而不是默认值。
  
#### <a name="mobility-tab"></a>Mobility tab

Use this tab to configure all of the mobility-related scenarios.
  
![“加载配置”工具“移动性”选项卡。](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
The options here are:
  
- **General Mobility Settings -** Click **Additional Settings** and set the field UcwaTargetServerUrl to the Director Pool virtual IP (VIP) or the Front End pool VIP.
    
- **Presence and P2P Instant Messaging/Audio -** Select a value for Load Level to enable the Mobility simulation.
    
> [!NOTE]
> Each of the scenarios has an **Advanced** button located next to it. Advanced dialogs contain values specific to each scenario that will change the behavior of the Stress and Performance Tool and enable customization.> For each of the Mobility scenarios, if the Load Level is **Custom**, then the value specified in the **ConversationsPerHour** field is used instead of the default.
  
#### <a name="summary-tab"></a>Summary tab

The Summary tab indicates which users to use for each of the scenarios.
  
![“加载配置”工具“摘要”选项卡。](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
The Summary tab indicates which users to use for each of the scenarios. 
  
It's possible to manually configure user number ranges by selecting the **Enable Custom User Range Generation** check box, and then double-clicking the scenario in the table that has the User Range that you want to customize.
  
Check **(RunClient.bat) Add sign-in delay when starting** in order to include delays in the generated batch files to correspond to the sign-in rate. This is useful to prevent server overload when signing in a large number of users.
  
Click **Generate Files** and select the folder where you want to generate the configuration. A dialog box will appear when your files have been successfully created.
  
![“已成功生成加载配置文件”消息框。只需单击“确定”。](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a>Run LyncPerfTool
<a name="BKMK_RunTool"> </a>

You'll need to create users, contacts, and scenarios before running the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool.exe). For details about using the tools to perform these actions, see [Create Users and Contacts](using-the-tool.md#BKMK_CreateUsersAndContacts) and [Configure User Profile](using-the-tool.md#BKMK_UserProfile) previously in this article. 运行这些工具还将生成的文件，将压力和性能工具作为的一部分运行一个批处理文件与包含所需的参数。
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a>运行业务服务器 2015年压力和性能工具 Skype

加载配置工具 (UserProfileGenerator.exe) 创建的批处理文件中，您可以通过注册性能计数器和加载 XML 配置文件来运行压力和性能工具 (LyncPerfTool.exe)。 The batch file runs one instance of LyncPerfTool.exe per configuration file. To run the batch file follow these steps:
  
### <a name="run-the-stress-and-performance-test"></a>Run the Stress and Performance test

1. Copy the folder with the configuration folders and files inside to the directory that has LyncPerfTool.exe on each client computer. (For example, if you generated the configuration files in the folder named 1.28_13.16.16, copy that folder to the folder with LyncPerfTool.exe in it. Do this on each client.)
    
2. 导航至客户端文件夹，然后运行**RunClient**批处理脚本。 您可以双击 Windows 资源管理器中的批处理文件，它将为该客户端运行的所有配置文件。 您可以通过使用以下语法从一个客户端文件夹运行脚本：
    
  ```
  RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
  ```

若要直接运行压力和性能工具，打开一个命令提示符并在命令行键入以下命令 (当第一次执行此操作，请务必注册的性能计数器和`regsvr32 /i /n /s LyncPerfToolPerf.dll`，如本主题中后面的注释中所示):
  
```
LyncPerfTool.exe /file:IM_client0.xml
```

To have the tool display the values in the configuration file, include the  `/displayfile` parameter on the preceding command, so that it looks like this:
  
```
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

To  *end*  the process, press Ctrl+C.
  
> [!NOTE]
> 直接运行压力和性能工具之前, 您必须注册性能计数器通过下面的命令：`regsvr32 /i /n /s LyncPerfToolPerf.dll`
  
> [!NOTE]
> 启动压力和性能工具的每个实例将立即开始登录用户，通常以一个用户每秒的速率。 
  
The peak user sign-in rate for the pool is about 12 per second. This means that you shouldn't start more than 12 LyncPerfTool.exe instances at the same time while users are still signing in. 一千的用户大约需要 20 分钟完全在一个每秒登录。
  
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
|SetPresence Calls  <br/> |Total number of presence change attempts. 不同类型的状态更改，请参见 SetPresence （存在类型） 调用的性能计数器。  <br/> |
|SetPresence 的 NNN 响应  <br/> |Nnn 响应代码从服务器接收到的总数量。  <br/> |
|GetPresence 调用  <br/> |状态请求尝试获取的总数。  <br/> |
|GetPresence 的 NNN 响应  <br/> |Nnn 响应代码从服务器接收到的总数量。  <br/> |
   
**通讯簿服务信息**

|**性能计数器**|**说明**|
|:-----|:-----|
|ABS Full/Delta File Downloads Attempted  <br/> |Total number of full or delta file download requests attempted.  <br/> |
|ABS Full/Delta File Downloads Succeeded  <br/> |Total number of full or delta file download requests attempted.  <br/> |
|Address Book Web Query service related counters  <br/> |Address book file download related counters.  <br/> |
|ABS WS 调用尝试  <br/> |尝试的地址簿 Web 查询服务请求的总数。  <br/> |
|成功的 ABS WS 调用  <br/> |返回一个成功的响应代码的地址簿 Web 查询服务请求的总数。  <br/> |
|ABS WS 调用失败  <br/> |返回了错误响应代码的地址簿 Web 查询服务请求的总数。  <br/> |
   
> [!NOTE]
> 此类别包括一些计数器来监视通讯簿服务 (ABS) 文件下载和地址簿 Web 查询服务请求。 
  
**通讯组列表 (DL) 信息**

|**性能计数器**|**说明**|
|:-----|:-----|
|Calls Attempted  <br/> |Total number of distribution list expansion (DLX) web service requests attempted.  <br/> |
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
|Calls Active  <br/> |Total number of active calls to the Response Group application.  <br/> |
|Calls Attempted  <br/> |Total number of calls attempted.  <br/> |
   
**Instant Messaging (IM) Call Information**

|**Performance Counter**|**说明**|
|:-----|:-----|
|调用活动  <br/> |不断传入/传出即时消息调用总数。  <br/> |
|终止呼叫  <br/> |传入/传出即时消息调用的总次数已终止。  <br/> |
|调用接收的 NNN  <br/> |Nnn 响应代码从服务器接收到的总数量。  <br/> |
|IM Messages Received/Sent  <br/> |Total number of messages received or sent for all sessions.  <br/> |
|传入/传出呼叫尝试  <br/> |传入/传出即时消息调用尝试的总数。  <br/> |
|传入/传出呼叫建立  <br/> |传入/传出建立即时消息调用的总次数。  <br/> |
   
**应用程序共享的呼叫信息**

|**Performance Counter**|**说明**|
|:-----|:-----|
|Calls Active  <br/> |不断传入/传出的应用程序共享的调用总数。  <br/> |
|终止呼叫  <br/> |Total number of incoming/outgoing application sharing calls already terminated.  <br/> |
|Calls Received NNN  <br/> |Total number of nnn response codes received from the server.  <br/> |
|Incoming/Outgoing Calls Attempted  <br/> |Total number of incoming/outgoing application sharing calls attempted.  <br/> |
|Incoming/Outgoing Calls Established  <br/> |传入/传出的应用程序共享建立的调用总数。  <br/> |
   
**CAA Call Information**

|**Performance Counter**|**说明**|
|:-----|:-----|
|Calls Active  <br/> |Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.  <br/> |
|Calls Terminated  <br/> |Total number of incoming/outgoing PSTN calls already terminated.  <br/> |
|Incoming/Outgoing Calls Attempted  <br/> |Total number of incoming/outgoing PSTN calls attempted.  <br/> |
|Incoming/Outgoing Calls Established  <br/> |Total number of incoming/outgoing PSTN calls established.  <br/> |
   
**Conference Information**

|**Performance Counter**|**说明**|
|:-----|:-----|
|Active Instant Messaging Conferences  <br/> |Total number of ongoing instant messaging conferences.  <br/> |
|Active Audio/Video Conferences  <br/> |Total number of ongoing audio/video (A/V) conferences.  <br/> |
|Active Application Sharing Conferences  <br/> |Total number of ongoing application sharing conferences.  <br/> |
|Number of Participants  <br/> |Total number of participants currently connected to conferences.  <br/> |
|Conference Schedule Failure  <br/> |Total number of failures while trying to schedule a conference.  <br/> |
|Join Conference Failure  <br/> |Total number of failures while trying to connect to a conference.  <br/> |
   
**UCWA Client Counters**

|**Performance Counter**|**说明**|
|:-----|:-----|
|Total Number of IMMCU Joins Succeeded  <br/> |Total number of instant messaging conferences joined.  <br/> |
|Total Number of DMCU Joins Succeeded  <br/> |Total number of A/V conferences joined.  <br/> |
   

