---
title: 为 Skype for Business Server 2015 中的持久聊天服务器配置合规性服务
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24e36ea3-fb8a-45a4-b6b7-38c2e256b218
description: 摘要： 了解如何在 Skype for Business Server 2015 配置持久聊天服务器合规性服务。
ms.openlocfilehash: 8364719f7d42b0627de579c7a0aa94c1e6370c45
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222078"
---
# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="fb3bf-103">为 Skype for Business Server 2015 中的持久聊天服务器配置合规性服务</span><span class="sxs-lookup"><span data-stu-id="fb3bf-103">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>

<span data-ttu-id="fb3bf-104">**摘要：** 了解如何在 Skype for Business Server 2015 配置持久聊天服务器合规性服务。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-104">**Summary:** Learn how to configure the Persistent Chat Server Compliance service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="fb3bf-105">持久聊天合规性允许管理员保留持久聊天消息和活动的存档。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-105">Persistent Chat compliance lets administrators maintain an archive of Persistent Chat messages as well as activities.</span></span> <span data-ttu-id="fb3bf-106">合规性服务记录并存档与每个持久聊天服务器对话，包括当参与者相关的数据：</span><span class="sxs-lookup"><span data-stu-id="fb3bf-106">The Compliance service records and archives data related to each Persistent Chat Server conversation, including when a participant:</span></span>

- <span data-ttu-id="fb3bf-107">加入持久聊天聊天室</span><span class="sxs-lookup"><span data-stu-id="fb3bf-107">Joins a Persistent Chat room</span></span>

- <span data-ttu-id="fb3bf-108">离开聊天室</span><span class="sxs-lookup"><span data-stu-id="fb3bf-108">Leaves a chat room</span></span>

- <span data-ttu-id="fb3bf-109">发布消息</span><span class="sxs-lookup"><span data-stu-id="fb3bf-109">Posts a message</span></span>

- <span data-ttu-id="fb3bf-110">查看聊天历史记录</span><span class="sxs-lookup"><span data-stu-id="fb3bf-110">Views chat history</span></span>

- <span data-ttu-id="fb3bf-111">上载文件</span><span class="sxs-lookup"><span data-stu-id="fb3bf-111">Uploads a file</span></span>

- <span data-ttu-id="fb3bf-112">下载文件</span><span class="sxs-lookup"><span data-stu-id="fb3bf-112">Downloads a file</span></span>

<span data-ttu-id="fb3bf-113">可根据需要，从合规性 SQL 数据库检索此信息。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-113">This information can be retrieved from the Compliance SQL database as needed.</span></span> 

> [!NOTE]
> <span data-ttu-id="fb3bf-114">持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="fb3bf-115">中团队提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="fb3bf-116">有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-116">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="fb3bf-117">如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-the-compliance-service-by-using-windows-powershell"></a><span data-ttu-id="fb3bf-118">使用 Windows PowerShell 配置合规性服务</span><span class="sxs-lookup"><span data-stu-id="fb3bf-118">Configure the Compliance service by using Windows PowerShell</span></span>

<span data-ttu-id="fb3bf-119">使用拓扑生成器启用合规性服务后，您可以使用 **Set-CsPersistenChatComplianceConfiguration** cmdlet 配置服务：</span><span class="sxs-lookup"><span data-stu-id="fb3bf-119">After the Compliance service has been enabled by using the Topology Builder, you can configure the service by using the **Set-CsPersistenChatComplianceConfiguration** cmdlet:</span></span>

```
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

<span data-ttu-id="fb3bf-120">或者</span><span class="sxs-lookup"><span data-stu-id="fb3bf-120">or</span></span>

```
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

<span data-ttu-id="fb3bf-121">您可以设置以下参数：</span><span class="sxs-lookup"><span data-stu-id="fb3bf-121">You can set the following parameters:</span></span>

- <span data-ttu-id="fb3bf-122">AdapterType - 允许您指定适配器类型。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-122">AdapterType - Lets you specify the adapter type.</span></span> <span data-ttu-id="fb3bf-123">适配器是一个第三方产品，可将合规性数据库中的数据转换为特定格式。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-123">An adapter is a third-party product that converts the data in the compliance database to a specific format.</span></span> <span data-ttu-id="fb3bf-124">XML 为默认格式。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-124">XML is the default.</span></span>

- <span data-ttu-id="fb3bf-125">OneChatRoomPerOutputFile-此参数允许您指定的分隔每个聊天室创建的报告。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-125">OneChatRoomPerOutputFile - This parameter lets you specify that separate reports to be created for each chat room.</span></span>

- <span data-ttu-id="fb3bf-126">AddChatRoomDetails - 启用时，此参数会在数据库中记录有关每个聊天室的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-126">AddChatRoomDetails - When enabled, this parameter records additional details about each chat room in the database.</span></span> <span data-ttu-id="fb3bf-127">由于此设置可大幅增加数据库的规模，默认将予以禁用。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-127">Because this setting can greatly increase the size of the database, it is disabled by default.</span></span>

- <span data-ttu-id="fb3bf-128">AddUserDetails - 启用时，此参数会在数据库中记录有关每个聊天室用户的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-128">AddUserDetails - When enabled, this parameter records additional details about each chat room user in the database.</span></span> <span data-ttu-id="fb3bf-129">由于此设置可大幅增加数据库的规模，默认将予以禁用。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-129">Because this setting can greatly increase the size of the database, it is disabled by default.</span></span>

- <span data-ttu-id="fb3bf-130">Identity - 此参数允许将合规性设置的作用范围限定为特定的集合，包括全局、站点和服务级别。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-130">Identity - This parameter allows compliance settings to be scoped for a particular collection, including the global, site, and service levels.</span></span> <span data-ttu-id="fb3bf-131">默认为全局级别。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-131">The default is the global level.</span></span> 

- <span data-ttu-id="fb3bf-132">RunInterval - 此参数确定了在服务器创建下一个合规性输出文件之前的时间量（默认为 15 分钟）。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-132">RunInterval - This parameter dictates the amount of time before the server creates the next compliance output file (the default is 15 minutes).</span></span>

## <a name="use-a-customized-compliance-adapter"></a><span data-ttu-id="fb3bf-133">使用自定义的合规性适配器</span><span class="sxs-lookup"><span data-stu-id="fb3bf-133">Use a customized compliance adapter</span></span>

<span data-ttu-id="fb3bf-134">您可以编写自定义而不是使用随持久聊天服务器一起安装 XmlAdapter 适配器。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-134">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="fb3bf-135">若要实现此目的，您必须提供包含实现 **IComplianceAdapter** 接口的公共类的 .NET Framework 程序集。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-135">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="fb3bf-136">您必须先在每台服务器的持久聊天服务器安装文件夹中将此程序集，在持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-136">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="fb3bf-137">任一合规性服务器都可以为您的适配器提供合规性数据，但合规性服务器不会为您的适配器的多个实例提供重复的合规性数据。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-137">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>

<span data-ttu-id="fb3bf-138">Compliance.dll 程序集中的命名空间中定义接口`Microsoft.Rtc.Internal.Chat.Server.Compliance`。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-138">The interface is defined in the Compliance.dll assembly in the namespace  `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="fb3bf-139">该接口定义您的自定义适配器必须实现的两种方法。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-139">The interface defines two methods that your custom adapter must implement.</span></span>

<span data-ttu-id="fb3bf-140">首次加载适配器时，持久聊天合规性服务器将调用以下方法。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-140">The Persistent Chat Compliance server will call the following method when the adapter first loads.</span></span> <span data-ttu-id="fb3bf-141">`AdapterConfig`包含与合规性适配器相关的持久聊天合规性配置：</span><span class="sxs-lookup"><span data-stu-id="fb3bf-141">The  `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter:</span></span>

```
void SetConfig(AdapterConfig config)
```

<span data-ttu-id="fb3bf-142">持久聊天合规性服务器定期调用以下方法，只要没有要翻译的新数据。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-142">The Persistent Chat Compliance server calls the following method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="fb3bf-143">此时间间隔等于`RunInterval`中的持久聊天合规性配置设置：</span><span class="sxs-lookup"><span data-stu-id="fb3bf-143">This time interval is equal to the  `RunInterval` as set in the Persistent Chat Compliance configuration:</span></span>

```
void Translate(ConversationCollection conversations)
```

<span data-ttu-id="fb3bf-144">`ConversationCollection`包含的上次调用此方法时收集的对话信息。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-144">The  `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>

## <a name="customize-the-xslt-definition-file"></a><span data-ttu-id="fb3bf-145">自定义 XSLT 定义文件</span><span class="sxs-lookup"><span data-stu-id="fb3bf-145">Customize the XSLT definition file</span></span>

<span data-ttu-id="fb3bf-p111">合规性数据以 XML 格式（可通过 XSLT 定义文件将其转换为最适合组织的格式）传送。本主题介绍合规性服务创建的 XML 文件。它还提供 XSLT 定义和输出文件的示例。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-p111">The compliance data is delivered as XML, which you can transform into the format that best fits your organization, by using an XSLT definition file. This topic describes the XML file that the Compliance service creates. It also provides samples of XSLT definition and output files.</span></span>

### <a name="output-format"></a><span data-ttu-id="fb3bf-149">输出格式</span><span class="sxs-lookup"><span data-stu-id="fb3bf-149">Output format</span></span>

<span data-ttu-id="fb3bf-150">合规性服务输出按对话（Conversation 元素）进行分类，然后再按消息（Messages 元素）分类，如以下代码示例所示：</span><span class="sxs-lookup"><span data-stu-id="fb3bf-150">The Compliance service output is categorized by conversation (the Conversation element) and then by message (the Messages element), as shown in the following code sample:</span></span>

```
<?xml version="1.0" encoding="utf-8" ?> 
<Conversations xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Conversation>
    <Channel uri="ma-chan://litwareinc.com/300" name="ma-chan://litwareinc.com/300" islogged="" /> 
    <!--FirstMessage goes here --!>
    <Messages> 
      <!—Messages go here--!>
    </Messages>
    <StartTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
    <EndTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
  </Conversation>
</Conversations>
```

<span data-ttu-id="fb3bf-p112">一个 Conversation 元素包含四个元素（Channel、FirstMessage、StartTimeUTC 和 EndTimeUTC）。Channel 元素包含聊天室的统一资源标识符 (URI)，而 FirstMessage 元素描述 Messages 元素中的第一条消息。StartTimeUTC 和 EndTimeUTC 元素提供对话的开始和结束时间，如以下代码示例所示：</span><span class="sxs-lookup"><span data-stu-id="fb3bf-p112">A Conversation element contains four elements (Channel, FirstMessage, StartTimeUTC, and EndTimeUTC). The Channel element contains the Uniform Resource Identifier (URI) of the chat room, and the FirstMessage element describes the first message in the Messages element. The StartTimeUTC and EndTimeUTC elements provide the start and end times for the conversation, as shown in the following code sample:</span></span>

```
<<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

<span data-ttu-id="fb3bf-p113">一个 Message 元素包含两个元素（Sender 和 DateTimeUTC）和三个属性（Type、Content 和 ID）。Sender 元素表示发送消息的用户，而 DateTimeUTC 元素表示事件发生的时间，如以下代码示例所示：</span><span class="sxs-lookup"><span data-stu-id="fb3bf-p113">A Message element contains two elements (Sender and DateTimeUTC) and three attributes (Type, Content, and ID). The Sender element represents the user who sends the message, and the DateTimeUTC element represents when an event occurs, as shown in the following code sample:</span></span>

```
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

<span data-ttu-id="fb3bf-156">下表描述了消息属性类型、内容和 ID。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-156">The following table describes the message attributes Type, Content, and ID.</span></span>

<span data-ttu-id="fb3bf-157">**Messages 元素属性**</span><span class="sxs-lookup"><span data-stu-id="fb3bf-157">**Messages Element Attributes**</span></span>

|<span data-ttu-id="fb3bf-158">**属性**</span><span class="sxs-lookup"><span data-stu-id="fb3bf-158">**Attribute**</span></span>|<span data-ttu-id="fb3bf-159">**说明**</span><span class="sxs-lookup"><span data-stu-id="fb3bf-159">**Description**</span></span>|<span data-ttu-id="fb3bf-160">**可选/必需**</span><span class="sxs-lookup"><span data-stu-id="fb3bf-160">**Optional/Required**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fb3bf-161">类型</span><span class="sxs-lookup"><span data-stu-id="fb3bf-161">Type</span></span>  <br/> |<span data-ttu-id="fb3bf-p114">指定消息类型。消息类型将在" Message 元素消息类型"表中进行介绍。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-p114">Specifies the message type. The message types are described in the Message Elements Message Types table.</span></span>  <br/> |<span data-ttu-id="fb3bf-164">是否必需</span><span class="sxs-lookup"><span data-stu-id="fb3bf-164">Required</span></span>  <br/> |
|<span data-ttu-id="fb3bf-165">内容</span><span class="sxs-lookup"><span data-stu-id="fb3bf-165">Content</span></span>  <br/> |<span data-ttu-id="fb3bf-p115">包含消息的内容。具有 Join 或 Part 类型的消息不使用此属性。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-p115">Contains the content of the message. Messages with a Type of Join or Part do not use this attribute.</span></span>  <br/> |<span data-ttu-id="fb3bf-168">可选</span><span class="sxs-lookup"><span data-stu-id="fb3bf-168">Optional</span></span>  <br/> |
|<span data-ttu-id="fb3bf-169">ID</span><span class="sxs-lookup"><span data-stu-id="fb3bf-169">ID</span></span>  <br/> |<span data-ttu-id="fb3bf-p116">指定内容的唯一 ID。此属性仅用于具有 Chat 类型的消息。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-p116">Specifies the unique ID of the content. This attribute is used only with messages with a Type of Chat.</span></span>  <br/> |<span data-ttu-id="fb3bf-172">可选</span><span class="sxs-lookup"><span data-stu-id="fb3bf-172">Optional</span></span>  <br/> |

<span data-ttu-id="fb3bf-p117">每个 Sender 元素包含五个属性：用户名、ID、电子邮件、Internal 和 URI。这些属性将在下表中进行介绍。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-p117">Each Sender element contains five attributes: the user name, ID, email, internal, and URI. These attributes are described in the following table.</span></span>

<span data-ttu-id="fb3bf-175">**Sender 元素属性**</span><span class="sxs-lookup"><span data-stu-id="fb3bf-175">**Sender Element Attributes**</span></span>

|<span data-ttu-id="fb3bf-176">**属性**</span><span class="sxs-lookup"><span data-stu-id="fb3bf-176">**Attribute**</span></span>|<span data-ttu-id="fb3bf-177">**说明**</span><span class="sxs-lookup"><span data-stu-id="fb3bf-177">**Description**</span></span>|<span data-ttu-id="fb3bf-178">**可选/必需**</span><span class="sxs-lookup"><span data-stu-id="fb3bf-178">**Optional/Required**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fb3bf-179">Username</span><span class="sxs-lookup"><span data-stu-id="fb3bf-179">Username</span></span>  <br/> |<span data-ttu-id="fb3bf-180">发送者的名称。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-180">The name of the sender.</span></span>  <br/> |<span data-ttu-id="fb3bf-181">可选</span><span class="sxs-lookup"><span data-stu-id="fb3bf-181">Optional</span></span>  <br/> |
|<span data-ttu-id="fb3bf-182">ID</span><span class="sxs-lookup"><span data-stu-id="fb3bf-182">ID</span></span>  <br/> |<span data-ttu-id="fb3bf-183">发件人的唯一 id。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-183">The sender's unique ID.</span></span>  <br/> |<span data-ttu-id="fb3bf-184">是否必需</span><span class="sxs-lookup"><span data-stu-id="fb3bf-184">Required</span></span>  <br/> |
|<span data-ttu-id="fb3bf-185">电子邮件</span><span class="sxs-lookup"><span data-stu-id="fb3bf-185">Email</span></span>  <br/> |<span data-ttu-id="fb3bf-186">发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-186">The sender's email address.</span></span>  <br/> |<span data-ttu-id="fb3bf-187">可选</span><span class="sxs-lookup"><span data-stu-id="fb3bf-187">Optional</span></span>  <br/> |
|<span data-ttu-id="fb3bf-188">内部</span><span class="sxs-lookup"><span data-stu-id="fb3bf-188">Internal</span></span>  <br/> |<span data-ttu-id="fb3bf-p118">确定用户是内部用户还是联盟用户。如果值设为 True，则用户为内部用户。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-p118">Determines whether the user is an internal user or a federated user. If the value is set to true, the user is internal.</span></span>  <br/> |<span data-ttu-id="fb3bf-191">可选</span><span class="sxs-lookup"><span data-stu-id="fb3bf-191">Optional</span></span>  <br/> |
|<span data-ttu-id="fb3bf-192">Uri</span><span class="sxs-lookup"><span data-stu-id="fb3bf-192">Uri</span></span>  <br/> |<span data-ttu-id="fb3bf-193">用户的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-193">The user's SIP URI.</span></span>  <br/> |<span data-ttu-id="fb3bf-194">必需</span><span class="sxs-lookup"><span data-stu-id="fb3bf-194">Required</span></span>  <br/> |

<span data-ttu-id="fb3bf-195">下面的示例演示了 Messages 元素可以包含邮件类型。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-195">The following examples show the message types that the Messages element can contain.</span></span> <span data-ttu-id="fb3bf-196">它还提供了如何使用每个元素的示例。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-196">It also provides examples of how each element is used.</span></span>

<span data-ttu-id="fb3bf-197">加入的用户加入聊天室。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-197">Join - A user joins a chat room.</span></span>

```
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

<span data-ttu-id="fb3bf-198">部件-用户离开聊天室。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-198">Part - A user leaves a chat room.</span></span>

```
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

<span data-ttu-id="fb3bf-199">聊天-发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-199">Chat - The sender's email address.</span></span>

```
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

<span data-ttu-id="fb3bf-200">聊天记录-用户请求聊天历史记录中的内容。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-200">Backchat - A user requests content from chat history.</span></span>

```
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

<span data-ttu-id="fb3bf-201">文件上载-用户上载文件。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-201">File upload - A user uploads a file.</span></span>

```
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

<span data-ttu-id="fb3bf-202">文件下载-用户下载文件。</span><span class="sxs-lookup"><span data-stu-id="fb3bf-202">File download - A user downloads a file.</span></span>

```
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a><span data-ttu-id="fb3bf-203">默认持久聊天输出 XSD 和示例 XSL 转换</span><span class="sxs-lookup"><span data-stu-id="fb3bf-203">Default Persistent Chat Output XSD and Example XSL Transform</span></span>

<span data-ttu-id="fb3bf-204">以下代码示例包含合规性服务器中的默认输出：</span><span class="sxs-lookup"><span data-stu-id="fb3bf-204">The following code sample contains the default output from the Compliance Server:</span></span>

```
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="Conversations" xmlns="" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">
   <xs:simpleType name="ComplianceMessageType">
      <xs:restriction base="xs:string">
        <xs:enumeration value="JOIN"/>
        <xs:enumeration value="PART"/>
        <xs:enumeration value="CHAT"/>
        <xs:enumeration value="BACKCHAT"/>
        <xs:enumeration value="FILEUPLOAD"/>
        <xs:enumeration value="FILEDOWNLOAD"/>
      </xs:restriction>
    </xs:simpleType>

  <xs:element name="Sender">
    <xs:complexType>
      <xs:attribute name="UserName" type="xs:string" />
      <xs:attribute name="id" type="xs:int" />
      <xs:attribute name="email" type="xs:string" use="optional" />
      <xs:attribute name="internal" type="xs:boolean" use="optional" >
        <xs:annotation><xs:documentation>If the user is internal or federated</xs:documentation></xs:annotation>
      </xs:attribute>
      <xs:attribute name="uri" type="xs:anyURI" use="optional" />
    </xs:complexType>
  </xs:element>
  <xs:element name="DateTimeUTC">
    <xs:complexType>
      <xs:attribute name="since1970" type="xs:long" />
      <xs:attribute name="string" type="xs:string" />
      <xs:attribute name="long" type="xs:long" />
    </xs:complexType>
  </xs:element>
  <xs:element name="Conversations" msdata:IsDataSet="true" msdata:UseCurrentLocale="true">
    <xs:complexType>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element ref="Sender" />
        <xs:element ref="DateTimeUTC" />
        <xs:element name="Conversation">
          <xs:complexType>
            <xs:sequence>
              <xs:element name="Channel" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="uri" type="xs:anyURI" />
                  <xs:attribute name="name" type="xs:string" use="optional" />
                </xs:complexType>
              </xs:element>
              <xs:element name="FirstMessage" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                    <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                  </xs:sequence>
                  <xs:attribute name="type" type="ComplianceMessageType" />
                  <xs:attribute name="content" type="xs:string" />
                  <xs:attribute name="id" type="xs:int" />
                </xs:complexType>
              </xs:element>
              <xs:element name="Messages" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element name="Message" minOccurs="0" maxOccurs="unbounded">
                      <xs:complexType>
                        <xs:sequence>
                          <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                          <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                        </xs:sequence>
                        <xs:attribute name="type" type="ComplianceMessageType" />
                        <xs:attribute name="content" type="xs:string" />
                        <xs:attribute name="id" type="xs:int" />
                      </xs:complexType>
                    </xs:element>
                  </xs:sequence>
                </xs:complexType>
              </xs:element>
              <xs:element name="StartTimeUTC" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="since1970" type="xs:long" />
                  <xs:attribute name="string" type="xs:string" />
                  <xs:attribute name="long" type="xs:long" />
                </xs:complexType>
              </xs:element>
              <xs:element name="EndTimeUTC" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="since1970" type="xs:long" />
                  <xs:attribute name="string" type="xs:string" />
                  <xs:attribute name="long" type="xs:long" />
                </xs:complexType>
              </xs:element>
            </xs:sequence>
          </xs:complexType>
        </xs:element>
      </xs:choice>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

<span data-ttu-id="fb3bf-205">以下代码示例包含一个示例 XSL 转换：</span><span class="sxs-lookup"><span data-stu-id="fb3bf-205">The following code sample contains a sample XSL transform:</span></span>

```
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xs="http://www.w3.org/2001/XMLSchema" exclude-result-prefixes="xs">
   <xsl:output method="xml" encoding="UTF-8" indent="yes" />

   <xsl:template match="/">
      <FileDump>
         <xsl:apply-templates />
      </FileDump>
   </xsl:template>

   <xsl:template match="Conversation">
      <xsl:variable name="chanName" select="Channel/@name" />
      <Conversation Perspective="{$chanName}_group_channel">
         <RoomID><xsl:value-of select="Channel/@name" /></RoomID>
         <StartTimeUTC><xsl:value-of select="StartTimeUTC/@since1970" /></StartTimeUTC>
         <xsl:apply-templates />
         <EndTimeUTC><xsl:value-of select="EndTimeUTC/@since1970" /></EndTimeUTC>
      </Conversation>
   </xsl:template>

   <xsl:template match="Message">
      <xsl:choose>
         <xsl:when test="@type='JOIN'">
            <ParticipantEntered>
               <xsl:call-template name="DateTimeAndLogin" />
               <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
               <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
               <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
            </ParticipantEntered>
         </xsl:when>

         <xsl:when test="@type='PART'">
            <ParticipantLeft>
               <xsl:call-template name="DateTimeAndLogin" />
               <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
               <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
               <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
            </ParticipantLeft>
         </xsl:when>

         <xsl:when test="@type='FILEUPLOAD' or @type='FILEDOWNLOAD'">
            <FileTransferStarted>
               <xsl:call-template name="DateTimeAndLogin" />
               <FileName><xsl:value-of select="@content" /></FileName>
            </FileTransferStarted>
            <FileTransferEnded>
               <xsl:call-template name="DateTimeAndLogin" />
               <FileName><xsl:value-of select="@content" /></FileName>
               <Status>Completed</Status>
            </FileTransferEnded>
         </xsl:when>

         <xsl:when test="@type='CHAT' or @type='BACKCHAT'">
            <Message>
               <xsl:call-template name="DateTimeAndLogin" />
               <Content><xsl:value-of select="@content" /></Content>
            </Message>
         </xsl:when>

         <xsl:otherwise />
      </xsl:choose>
   </xsl:template>

   <xsl:template name="DateTimeAndLogin">
      <LoginName><xsl:value-of select="Sender/@userName" /></LoginName>
      <DateTimeUTC><xsl:value-of select="DateTimeUTC/@since1970" /></DateTimeUTC>
   </xsl:template>
</xsl:stylesheet>
```
