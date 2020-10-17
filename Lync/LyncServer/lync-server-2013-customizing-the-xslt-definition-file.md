---
title: Lync Server 2013：自定义 XSLT 定义文件
description: Lync Server 2013：自定义 XSLT 定义文件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Customizing the XSLT definition file
ms:assetid: f18dd78c-3598-4f38-b496-96b750c6e518
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ679898(v=OCS.15)
ms:contentKeyID: 49557733
ms.date: 09/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b248b44c9257fa9f30cc99a3773abf71ddbd8651
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553798"
---
# <a name="customizing-the-xslt-definition-file-in-lync-server-2013"></a><span data-ttu-id="87b00-103">在 Lync Server 2013 中自定义 XSLT 定义文件</span><span class="sxs-lookup"><span data-stu-id="87b00-103">Customizing the XSLT definition file in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87b00-104">_**上次修改的主题：** 2014-09-11_</span><span class="sxs-lookup"><span data-stu-id="87b00-104">_**Topic Last Modified:** 2014-09-11_</span></span>

<span data-ttu-id="87b00-105">合规性服务记录和存档与每个 Lync Server 2013、持久聊天服务器对话相关的数据，包括参与者：</span><span class="sxs-lookup"><span data-stu-id="87b00-105">The Compliance service records and archives data related to each Lync Server 2013, Persistent Chat Server conversation, including when a participant:</span></span>

  - <span data-ttu-id="87b00-106">加入持久聊天室</span><span class="sxs-lookup"><span data-stu-id="87b00-106">Joins a Persistent Chat room</span></span>

  - <span data-ttu-id="87b00-107">离开聊天室</span><span class="sxs-lookup"><span data-stu-id="87b00-107">Leaves a chat room</span></span>

  - <span data-ttu-id="87b00-108">发布消息</span><span class="sxs-lookup"><span data-stu-id="87b00-108">Posts a message</span></span>

  - <span data-ttu-id="87b00-109">查看聊天历史记录</span><span class="sxs-lookup"><span data-stu-id="87b00-109">Views chat history</span></span>

  - <span data-ttu-id="87b00-110">上载文件</span><span class="sxs-lookup"><span data-stu-id="87b00-110">Uploads a file</span></span>

  - <span data-ttu-id="87b00-111">下载文件</span><span class="sxs-lookup"><span data-stu-id="87b00-111">Downloads a file</span></span>

<span data-ttu-id="87b00-p101">数据以 XML 格式（可通过 XSLT 定义文件将其转换为最适合组织的格式）传送。本主题介绍合规性服务创建的 XML 文件。它还提供 XSLT 定义和输出文件的示例。</span><span class="sxs-lookup"><span data-stu-id="87b00-p101">The data is delivered as XML, which you can transform into the format that best fits your organization, by using an XSLT definition file. This topic describes the XML file that the Compliance service creates. It also provides samples of XSLT definition and output files.</span></span>

<div>

## <a name="output-format"></a><span data-ttu-id="87b00-115">输出格式</span><span class="sxs-lookup"><span data-stu-id="87b00-115">Output Format</span></span>

<span data-ttu-id="87b00-116">合规性服务输出按对话（Conversation 元素）进行分类，然后再按消息（Messages 元素）分类，如以下代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="87b00-116">The Compliance service output is categorized by conversation (the Conversation element) and then by message (the Messages element), as shown in the following code sample.</span></span>

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

<span data-ttu-id="87b00-p102">一个 Conversation 元素包含四个元素（Channel、FirstMessage、StartTimeUTC 和 EndTimeUTC）。Channel 元素包含聊天室的统一资源标识符 (URI)，而 FirstMessage 元素描述 Messages 元素中的第一条消息。StartTimeUTC 和 EndTimeUTC 元素提供对话的开始和结束时间，如以下代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="87b00-p102">A Conversation element contains four elements (Channel, FirstMessage, StartTimeUTC, and EndTimeUTC). The Channel element contains the Uniform Resource Identifier (URI) of the chat room, and the FirstMessage element describes the first message in the Messages element. The StartTimeUTC and EndTimeUTC elements provide the start and end times for the conversation, as shown in the following code sample.</span></span>

    <<FirstMessage type="JOIN" content="" id="0">
          <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
          <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
    </FirstMessage>

<span data-ttu-id="87b00-p103">一个 Message 元素包含两个元素（Sender 和 DateTimeUTC）和三个属性（Type、Content 和 ID）。Sender 元素表示发送消息的用户，而 DateTimeUTC 元素表示事件发生的时间，如以下代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="87b00-p103">A Message element contains two elements (Sender and DateTimeUTC) and three attributes (Type, Content, and ID). The Sender element represents the user who sends the message, and the DateTimeUTC element represents when an event occurs, as shown in the following code sample.</span></span>

    <Message type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
    </Message>

<span data-ttu-id="87b00-122">下表描述了消息属性类型、内容和 ID。</span><span class="sxs-lookup"><span data-stu-id="87b00-122">The following table describes the message attributes Type, Content, and ID.</span></span>

### <a name="messages-element-attributes"></a><span data-ttu-id="87b00-123">Messages 元素属性</span><span class="sxs-lookup"><span data-stu-id="87b00-123">Messages Element Attributes</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87b00-124">属性</span><span class="sxs-lookup"><span data-stu-id="87b00-124">Attribute</span></span></th>
<th><span data-ttu-id="87b00-125">说明</span><span class="sxs-lookup"><span data-stu-id="87b00-125">Description</span></span></th>
<th><span data-ttu-id="87b00-126">可选/必需</span><span class="sxs-lookup"><span data-stu-id="87b00-126">Optional/Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87b00-127">类型</span><span class="sxs-lookup"><span data-stu-id="87b00-127">Type</span></span></p></td>
<td><p><span data-ttu-id="87b00-p104">指定消息类型。消息类型将在“Message 元素消息类型”表中进行介绍。</span><span class="sxs-lookup"><span data-stu-id="87b00-p104">Specifies the message type. The message types are described in the Message Elements Message Types table.</span></span></p></td>
<td><p><span data-ttu-id="87b00-130">必需</span><span class="sxs-lookup"><span data-stu-id="87b00-130">Required</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87b00-131">内容</span><span class="sxs-lookup"><span data-stu-id="87b00-131">Content</span></span></p></td>
<td><p><span data-ttu-id="87b00-p105">包含消息的内容。具有 Join 或 Part 类型的消息不使用此属性。</span><span class="sxs-lookup"><span data-stu-id="87b00-p105">Contains the content of the message. Messages with a Type of Join or Part do not use this attribute.</span></span></p></td>
<td><p><span data-ttu-id="87b00-134">可选</span><span class="sxs-lookup"><span data-stu-id="87b00-134">Optional</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87b00-135">ID</span><span class="sxs-lookup"><span data-stu-id="87b00-135">ID</span></span></p></td>
<td><p><span data-ttu-id="87b00-p106">指定内容的唯一 ID。此属性仅用于具有 Chat 类型的消息。</span><span class="sxs-lookup"><span data-stu-id="87b00-p106">Specifies the unique ID of the content. This attribute is used only with messages with a Type of Chat.</span></span></p></td>
<td><p><span data-ttu-id="87b00-138">可选</span><span class="sxs-lookup"><span data-stu-id="87b00-138">Optional</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="87b00-p107">每个 Sender 元素包含五个属性：用户名、ID、电子邮件、Internal 和 URI。这些属性将在下表中进行介绍。</span><span class="sxs-lookup"><span data-stu-id="87b00-p107">Each Sender element contains five attributes: the user name, ID, email, internal, and URI. These attributes are described in the following table.</span></span>

### <a name="sender-element-attributes"></a><span data-ttu-id="87b00-141">Sender 元素属性</span><span class="sxs-lookup"><span data-stu-id="87b00-141">Sender Element Attributes</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87b00-142">属性</span><span class="sxs-lookup"><span data-stu-id="87b00-142">Attribute</span></span></th>
<th><span data-ttu-id="87b00-143">说明</span><span class="sxs-lookup"><span data-stu-id="87b00-143">Description</span></span></th>
<th><span data-ttu-id="87b00-144">可选/必需</span><span class="sxs-lookup"><span data-stu-id="87b00-144">Optional/Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87b00-145">用户名</span><span class="sxs-lookup"><span data-stu-id="87b00-145">Username</span></span></p></td>
<td><p><span data-ttu-id="87b00-146">发送者的名称。</span><span class="sxs-lookup"><span data-stu-id="87b00-146">The name of the sender.</span></span></p></td>
<td><p><span data-ttu-id="87b00-147">可选</span><span class="sxs-lookup"><span data-stu-id="87b00-147">Optional</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87b00-148">ID</span><span class="sxs-lookup"><span data-stu-id="87b00-148">ID</span></span></p></td>
<td><p><span data-ttu-id="87b00-149">发送者的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="87b00-149">The sender’s unique ID.</span></span></p></td>
<td><p><span data-ttu-id="87b00-150">必需</span><span class="sxs-lookup"><span data-stu-id="87b00-150">Required</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87b00-151">电子邮件</span><span class="sxs-lookup"><span data-stu-id="87b00-151">Email</span></span></p></td>
<td><p><span data-ttu-id="87b00-152">发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="87b00-152">The sender’s email address.</span></span></p></td>
<td><p><span data-ttu-id="87b00-153">可选</span><span class="sxs-lookup"><span data-stu-id="87b00-153">Optional</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87b00-154">内部</span><span class="sxs-lookup"><span data-stu-id="87b00-154">Internal</span></span></p></td>
<td><p><span data-ttu-id="87b00-p108">确定用户是内部用户还是联盟用户。如果值设为 True，则用户为内部用户。</span><span class="sxs-lookup"><span data-stu-id="87b00-p108">Determines whether the user is an internal user or a federated user. If the value is set to true, the user is internal.</span></span></p></td>
<td><p><span data-ttu-id="87b00-157">可选</span><span class="sxs-lookup"><span data-stu-id="87b00-157">Optional</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87b00-158">Url</span><span class="sxs-lookup"><span data-stu-id="87b00-158">Uri</span></span></p></td>
<td><p><span data-ttu-id="87b00-159">用户的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="87b00-159">The user’s SIP URI.</span></span></p></td>
<td><p><span data-ttu-id="87b00-160">必需</span><span class="sxs-lookup"><span data-stu-id="87b00-160">Required</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="87b00-p109">下表介绍了 Messages 元素可包含的消息类型。它还提供了如何使用每个元素的示例。</span><span class="sxs-lookup"><span data-stu-id="87b00-p109">The following table describes the message types that the Messages element can contain. It also provides examples of how each element is used.</span></span>

### <a name="message-element-message-types"></a><span data-ttu-id="87b00-163">Message 元素消息类型</span><span class="sxs-lookup"><span data-stu-id="87b00-163">Message Element Message Types</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87b00-164">消息类型</span><span class="sxs-lookup"><span data-stu-id="87b00-164">Message Type</span></span></th>
<th><span data-ttu-id="87b00-165">说明</span><span class="sxs-lookup"><span data-stu-id="87b00-165">Description</span></span></th>
<th><span data-ttu-id="87b00-166">代码示例</span><span class="sxs-lookup"><span data-stu-id="87b00-166">Code example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87b00-167">加入</span><span class="sxs-lookup"><span data-stu-id="87b00-167">Join</span></span></p></td>
<td><p><span data-ttu-id="87b00-168">用户加入聊天室。</span><span class="sxs-lookup"><span data-stu-id="87b00-168">A user joins a chat room.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;JOIN&quot; content=&quot;&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1206211842612&quot; string=&quot;2008-03-22T18:50:42.6127374Z&quot; long=&quot;633418086426127374&quot; /&gt; 
&lt;/Message</code></pre></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87b00-169">Part</span><span class="sxs-lookup"><span data-stu-id="87b00-169">Part</span></span></p></td>
<td><p><span data-ttu-id="87b00-170">用户离开聊天室。</span><span class="sxs-lookup"><span data-stu-id="87b00-170">A user leaves a chat room.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;PART&quot; content=&quot;&quot; id=&quot;0&quot;&gt;
  &lt; Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1212610602532&quot; string=&quot;2008-06-04T20:16:42.5324614Z&quot; long=&quot;633482074025324614&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87b00-171">聊天</span><span class="sxs-lookup"><span data-stu-id="87b00-171">Chat</span></span></p></td>
<td><p><span data-ttu-id="87b00-172">发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="87b00-172">The sender’s email address.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;CHAT&quot; content=&quot;hello&quot; id=&quot;1&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1205351800522&quot; string=&quot;2008-03-12T19:56:40.522264Z&quot; long=&quot;633409486005222640&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87b00-173">Backchat</span><span class="sxs-lookup"><span data-stu-id="87b00-173">Backchat</span></span></p></td>
<td><p><span data-ttu-id="87b00-174">用户请求聊天历史记录中的内容。</span><span class="sxs-lookup"><span data-stu-id="87b00-174">A user requests content from chat history.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;BACKCHAT&quot; content=&quot;backchatcontent&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1206034385284&quot; string=&quot;2008-03-20T17:33:05.2841594Z&quot; long=&quot;633416311852841594&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87b00-175">File upload</span><span class="sxs-lookup"><span data-stu-id="87b00-175">File upload</span></span></p></td>
<td><p><span data-ttu-id="87b00-176">用户上载文件。</span><span class="sxs-lookup"><span data-stu-id="87b00-176">A user uploads a file.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;FILEUPLOAD&quot; content=&quot;0988239a-bb66-4616-90a4-b07771a2097c.txt&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1205351828975&quot; string=&quot;2008-03-12T19:57:08.9755711Z&quot; long=&quot;633409486289755711&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87b00-177">File download</span><span class="sxs-lookup"><span data-stu-id="87b00-177">File download</span></span></p></td>
<td><p><span data-ttu-id="87b00-178">用户下载文件。</span><span class="sxs-lookup"><span data-stu-id="87b00-178">A user downloads a file.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;FILEDOWNLOAD&quot; content=&quot;006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;kazuto@litwareinc.com&quot; id=&quot;10&quot; email=&quot;&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1212611141851&quot; string=&quot;2008-06-04T20:25:41.8518646Z&quot; long=&quot;633482079418518646&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a><span data-ttu-id="87b00-179">默认的持久聊天输出 XSD 和示例 XSL 转换</span><span class="sxs-lookup"><span data-stu-id="87b00-179">Default Persistent Chat Output XSD and Example XSL Transform</span></span>

<span data-ttu-id="87b00-180">以下代码示例包含合规性服务器中的默认输出。</span><span class="sxs-lookup"><span data-stu-id="87b00-180">The following code sample contains the default output from the Compliance Server.</span></span>

    <?xml version="1.0" encoding="utf-8"?>
    <xs:schema id="Conversations"  xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">
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

<span data-ttu-id="87b00-181">以下代码示例包含一个示例 XSL 转换。</span><span class="sxs-lookup"><span data-stu-id="87b00-181">The following code sample contains a sample XSL transform.</span></span>

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

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

