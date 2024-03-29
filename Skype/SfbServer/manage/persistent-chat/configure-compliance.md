---
title: 在 2015 年 10 月为持久聊天服务器Skype for Business Server合规性服务
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 24e36ea3-fb8a-45a4-b6b7-38c2e256b218
description: 摘要：了解如何在 Skype for Business Server 2015 中配置持久聊天服务器合规性服务。
ms.openlocfilehash: de70e131526033b46b69359a231b158d93accfbf
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62396454"
---
# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a>在 2015 年 10 月为持久聊天服务器Skype for Business Server合规性服务

**摘要：** 了解如何在 Skype for Business Server 2015 中配置持久聊天服务器合规性服务。

持久聊天合规性使管理员能够维护持久聊天消息以及活动的存档。 合规性服务记录和存档与每个持久聊天服务器对话相关的数据，包括参与者：

- 加入持久聊天室

- 离开聊天室

- 发布消息

- 查看聊天历史记录

- 上载文件

- 下载文件

可根据需要从合规性数据库SQL此信息。 

> [!NOTE]
> 持久聊天在 Skype for Business Server 2015 中可用，但在 2019 年 2 Skype for Business Server不再受支持。 相同的功能在 Teams。 有关详细信息，请参阅[开始升级Microsoft Teams升级](/microsoftteams/upgrade-start-here)。 如果您需要使用持久聊天，您的选择是迁移需要此功能的用户以Teams或继续使用 Skype for Business Server 2015。 

## <a name="configure-the-compliance-service-by-using-windows-powershell"></a>使用合规性服务配置Windows PowerShell

在使用拓扑生成器启用合规性服务后，可以使用 **Set-CsPersistenChatComplianceConfiguration** cmdlet 配置该服务：

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

或

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

可以设置以下参数：

- AdapterType - 允许你指定适配器类型。 适配器是一种第三方产品，可将合规性数据库中的数据转换为特定格式。 XML 为默认值。

- OneChatRoomPerOutputFile - 此参数允许您指定要为每个聊天室创建单独的报告。

- AddChatRoomDetails - 启用后，此参数将记录有关数据库中每个聊天室的其他详细信息。 由于此设置可以大大增加数据库的大小，因此默认情况下将禁用它。

- AddUserDetails - 启用后，此参数将记录有关数据库中每个聊天室用户的其他详细信息。 由于此设置可以大大增加数据库的大小，因此默认情况下将禁用它。

- Identity - 此参数允许将合规性设置的范围设定为特定集合，包括全局、站点和服务级别。 默认值为全局级别。 

- RunInterval - 此参数指示服务器创建下一个合规性输出文件之前 (默认值为 15 分钟) 。

## <a name="use-a-customized-compliance-adapter"></a>使用自定义合规性适配器

您可以编写自定义适配器，而不是使用随持久聊天服务器一起安装的 XmlAdapter。 若要实现此目的，您必须提供包含实现 **IComplianceAdapter** 接口的公共类的 .NET Framework 程序集。 必须将此程序集放在持久聊天服务器池中每台服务器的持久聊天服务器安装文件夹中。 任一合规性服务器都可以为您的适配器提供合规性数据，但合规性服务器不会为您的适配器的多个实例提供重复的合规性数据。

接口在命名空间 中的 Compliance.dll 程序集中定义  `Microsoft.Rtc.Internal.Chat.Server.Compliance`。 该接口定义您的自定义适配器必须实现的两个方法。

持久聊天合规性服务器将在适配器首次加载时调用以下方法。 包含  `AdapterConfig` 与合规性适配器相关的持久聊天合规性配置：

```cpp
void SetConfig(AdapterConfig config)
```

只要有新数据要转换，持久聊天合规性服务器就定期调用以下方法。 此时间间隔等于在  `RunInterval` 持久聊天合规性配置中设置的：

```cpp
void Translate(ConversationCollection conversations)
```

包含  `ConversationCollection` 上次调用此方法时收集的对话信息。

## <a name="customize-the-xslt-definition-file"></a>自定义 XSLT 定义文件

合规性数据以 XML 形式提供，您可以使用 XSLT 定义文件将其转换为最适合贵组织的格式。 本主题介绍合规性服务创建的 XML 文件。 它还提供 XSLT 定义和输出文件的示例。

### <a name="output-format"></a>输出格式

合规性服务输出按 Conversation 元素 (会话) 然后按消息 (Messages 元素) 进行分类，如以下代码示例所示：

```XML
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

一个 Conversation 元素包含四个元素（Channel、FirstMessage、StartTimeUTC 和 EndTimeUTC）。 Channel 元素包含聊天室的统一资源标识符 (URI)，而 FirstMessage 元素描述 Messages 元素中的第一条消息。 StartTimeUTC 和 EndTimeUTC 元素提供对话的开始时间和结束时间，如以下代码示例所示：

```xml
<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

一个 Message 元素包含两个元素（Sender 和 DateTimeUTC）和三个属性（Type、Content 和 ID）。 Sender 元素表示发送邮件的用户，DateTimeUTC 元素表示事件发生的时间，如以下代码示例所示：

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

下表描述了消息属性类型、内容和 ID。

**Messages 元素属性**

|**属性**|**说明**|**可选/必需**|
|:-----|:-----|:-----|
|类型  <br/> |指定消息类型。消息类型将在“Message 元素消息类型”表中进行介绍。  <br/> |必需  <br/> |
|Content  <br/> |包含消息的内容。具有 Join 或 Part 类型的消息不使用此属性。  <br/> |可选  <br/> |
|ID  <br/> |指定内容的唯一 ID。此属性仅用于具有 Chat 类型的消息。  <br/> |可选  <br/> |

每个 Sender 元素包含五个属性：用户名、ID、电子邮件、Internal 和 URI。这些属性将在下表中进行介绍。

**Sender 元素属性**

|**属性**|**说明**|**可选/必需**|
|:-----|:-----|:-----|
|用户名  <br/> |发送者的名称。  <br/> |可选  <br/> |
|ID  <br/> |发件人的唯一 ID。  <br/> |必需  <br/> |
|电子邮件  <br/> |发件人的电子邮件地址。  <br/> |可选  <br/> |
|内部  <br/> |确定用户是内部用户还是联盟用户。如果值设为 True，则用户为内部用户。  <br/> |可选  <br/> |
|Uri  <br/> |用户的 SIP URI。  <br/> |必需  <br/> |

以下示例显示 Messages 元素可以包含的消息类型。 它还提供了如何使用每个元素的示例。

Join - 用户加入聊天室。

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

Part - 用户离开聊天室。

```xml
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

聊天 - 发件人的电子邮件地址。

```xml
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

Backchat - 用户从聊天历史记录请求内容。

```xml
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

文件上载 - 用户上载文件。

```xml
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

文件下载 - 用户下载文件。

```xml
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a>默认持久聊天输出 XSD 和示例 XSL 转换

以下代码示例包含合规性服务器的默认输出：

```xml
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

下面的代码示例包含示例 XSL 转换：

```xml
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
