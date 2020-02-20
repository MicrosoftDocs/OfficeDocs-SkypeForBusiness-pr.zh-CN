---
title: Lync Server 2013：管理通讯簿服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering the Address Book Service
ms:assetid: 801e4243-9670-4477-aa2f-88b61ecf5351
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429711(v=OCS.15)
ms:contentKeyID: 48184649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45dbc2c71cf34515f8f6176e4f579e6683ad319e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="administering-the-address-book-service-in-lync-server-2013"></a>在 Lync Server 2013 中管理通讯簿服务

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-02-05_

作为 Lync Server、Enterprise Edition 或 Standard Edition Server 部署的一部分，默认情况下会安装通讯簿服务。 通讯簿服务（RTCab）使用的数据库是在 SQL Server 上创建的（对于 Enterprise Edition，这是后端 SQL Server; 对于 Standard Edition server，则为并置 SQL Server）。

<div>


> [!NOTE]  
> 有关使用<STRONG>ADSI 编辑</STRONG>编辑 Active Directory 域服务对象属性的信息，请参阅<A href="https://go.microsoft.com/fwlink/?linkid=330427">ADSI edit</A>。 有关特定于通讯簿服务的资源工具包中的工具的信息，请参阅<A href="https://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 资源工具包工具</A>。



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a>通讯簿服务器电话号码规范化

Lync Server 需要标准化 RFC 3966/e.164 电话号码。 若要使用非结构化或格式不一致的电话号码，Lync Server 依靠通讯簿服务器对电话号码进行预处理，然后再将其传递给规范化规则。 当从通讯簿中使用电话号码且应用规范化规则时，客户端（如 Lync Phone Edition 和 Lync Mobile）可以使用这些规范化的数字。

对于以前版本中使用的规范化规则，如果不进行某些调整，可能无法正常使用。由于在规范化规则之前删除了空格和非必需的字符，因此如果正则表达式专门查找已删除的短划线或其他字符，则规范化规则可能失败。应检查规范化规则以确保它们不查找这些非必需字符，或者允许规则在期望字符出现但未出现的情况下正常中止并继续执行。

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a>用户复制程序和通讯簿服务器

通讯簿服务器使用由用户复制程序提供的数据来更新最初从全局地址列表 (GAL) 中获取的信息。 用户复制程序将每个用户、联系人和组的 Active Directory 域服务属性写入数据库中的 AbUserEntry 表，通讯簿服务器将数据库中的用户数据同步到通讯簿服务器文件存储中的文件，并导入通讯簿数据库 RTCab。 AbUserEntry 表的架构使用两列：**UserGuid** 和 **UserData**。 **UserGuid**是索引列，其中包含 Active Directory 对象的16字节 GUID。 **UserData**是一个图像列，其中包含了该联系人的所有上述 Active Directory 域服务属性。

用户复制程序通过读取位于基于 SQL Server 的实例中的配置表来确定要写入的 Active Directory 属性，AbUserEntry 表。 AbAttribute 表包含四列：**ID**、**Name**、**Flags** 和 **Enable**。 该表在数据库安装期间创建。 如果 AbAttribute 表为空，用户复制程序将跳过其 AbUserEntry 表处理逻辑。 通讯簿服务器属性是动态的，可以从 AbAttribute 表中检索，该表最初在通讯簿服务器激活时由通讯簿服务器写入。

通讯簿服务器激活将使用下表中显示的值填充 AbAttribute 表。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID</th>
<th>名称</th>
<th>Flags</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>givenName</p></td>
<td><p>0x01400000</p></td>
</tr>
<tr class="even">
<td><p>双面</p></td>
<td><p>Sn</p></td>
<td><p>0x02400000</p></td>
</tr>
<tr class="odd">
<td><p>第三章</p></td>
<td><p>displayName</p></td>
<td><p>0x03420000</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>标题</p></td>
<td><p>0x04000000</p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>mailNickname</p></td>
<td><p>0x05400000</p></td>
</tr>
<tr class="even">
<td><p>6 </p></td>
<td><p>Company</p></td>
<td><p>0x06000000</p></td>
</tr>
<tr class="odd">
<td><p>7 </p></td>
<td><p>physicalDeliveryOfficeName</p></td>
<td><p>0x07000000</p></td>
</tr>
<tr class="even">
<td><p>8 </p></td>
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>0x08520C00</p></td>
</tr>
<tr class="odd">
<td><p>9 </p></td>
<td><p>telephoneNumber</p></td>
<td><p>0x09022800</p></td>
</tr>
<tr class="even">
<td><p>10 </p></td>
<td><p>homePhone</p></td>
<td><p>0x0A302800</p></td>
</tr>
<tr class="odd">
<td><p>11 </p></td>
<td><p>移动设备</p></td>
<td><p>0x0B622800</p></td>
</tr>
<tr class="even">
<td><p>12</p></td>
<td><p>otherTelephone</p></td>
<td><p>0x0C302000</p></td>
</tr>
<tr class="odd">
<td><p>13 </p></td>
<td><p>ipPhone</p></td>
<td><p>0x0D302000</p></td>
</tr>
<tr class="even">
<td><p>14 </p></td>
<td><p>邮件</p></td>
<td><p>0x0E500000</p></td>
</tr>
<tr class="odd">
<td><p>15 </p></td>
<td><p>groupType</p></td>
<td><p>0x0F010800</p></td>
</tr>
<tr class="even">
<td><p>16 </p></td>
<td><p>部门</p></td>
<td><p>0x10000000</p></td>
</tr>
<tr class="odd">
<td><p>17 </p></td>
<td><p>说明</p></td>
<td><p>0x11000100</p></td>
</tr>
<tr class="even">
<td><p>18 </p></td>
<td><p>Manager</p></td>
<td><p>0x12040001</p></td>
</tr>
<tr class="odd">
<td><p>合</p></td>
<td><p>proxyAddress</p></td>
<td><p>0x00500105</p></td>
</tr>
<tr class="even">
<td><p>20</p></td>
<td><p>msExchHideFromAddressLists</p></td>
<td><p>0xFF000003</p></td>
</tr>
<tr class="odd">
<td><p>99</p></td>
<td><p>entryID</p></td>
<td><p>0x99000000</p></td>
</tr>
</tbody>
</table>


**ID** 列中的数字必须唯一，并且绝对不能重复使用。 另外，使 ID 值低于 256 可以节省通讯簿服务器写入的输出文件的空间。 然而，最大 ID 值是 65535。 "**名称**" 列对应于用户复制程序应在每个联系人的 "AbUserEntry" 表中放置的 Active Directory 属性名称。 **Flags** 列中的值用于定义属性类型。 以下类型的通讯簿服务器属性由用户复制程序标识，并由 **Flags** 列中的值的低位字节指示。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>属性</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0x0</p></td>
<td><p>字符串属性。用户复制程序在将此类型存储在 AbUserEntry 表中之前，先将其转换成 UTF-8。</p></td>
</tr>
<tr class="even">
<td><p>0x1</p></td>
<td><p>二进制属性。用户复制程序不进行任何转换即将此类型存储在 blob 中。</p></td>
</tr>
<tr class="odd">
<td><p>0x2</p></td>
<td><p>一个字符串属性，但仅当属性值以&quot;电话：&quot;时才包含该属性。 此类型主要用于多值字符串属性，特别是 <strong>proxyAddresses</strong>。 在这种情况下，通讯簿服务器只对<strong></strong>以&quot;电话开始的 proxyAddresses 条目感&quot;兴趣：。 因此，在节省空间的情况下，用户复制程序仅存储以&quot;电话开头的条目：&quot;。</p></td>
</tr>
<tr class="even">
<td><p>0x3</p></td>
<td><p>布尔字符串属性，如果为 TRUE，用户复制程序不会将此联系人包含在 AbUserEntry 表中。如果为 FALSE，用户复制程序会将此联系人的属性包含在 AbUserEntry 表中，但不包含具有此标志的特定属性。这是另一种特殊类型，主要用于 <strong>msExchHideFromAddressLists</strong> 属性。</p></td>
</tr>
<tr class="odd">
<td><p>0x4</p></td>
<td><p>一个字符串属性，但仅当属性&quot;值以 smtp：&quot;开头并包含符号时才包含&quot; @ &quot;该属性。</p></td>
</tr>
<tr class="even">
<td><p>0x5</p></td>
<td><p>String 属性，但仅&quot;当属性值以电话：&quot;或&quot;smtp：&quot;开头并包含&quot; @ &quot;符号时才包含该属性。</p></td>
</tr>
<tr class="odd">
<td><p>0x100</p></td>
<td><p>如果设置，则是可针对每个联系人出现多次的多值属性。</p></td>
</tr>
<tr class="even">
<td><p>0x400</p></td>
<td><p>如果设置，将标识联系人的电子邮件用户帐户名属性。通讯簿服务器使用此标志来标识在电话规范化事件日志条目中显示的属性值。</p></td>
</tr>
<tr class="odd">
<td><p>0x800</p></td>
<td><p>如果设置，将标识联系人的必需属性。仅当在 Active Directory 中存在此属性的值时，通讯簿服务器才会在 AbUserEntry 表中包含用户。如果存在多个必需属性，只需其中一个属性具有值即会在 AbUserEntry 表中包含用户。</p></td>
</tr>
<tr class="even">
<td><p>0x1000</p></td>
<td><p>如果设置，通讯簿服务器将始终规范化此属性的值。</p></td>
</tr>
<tr class="odd">
<td><p>0x2000</p></td>
<td><p>如果设置并且 <strong>UseNormalizationRules</strong> CMS 设置为 FALSE，通讯簿服务器将使用 <strong>proxyAddresses</strong> 中的规范化号码；否则通讯簿服务器的行为将与标志位是 0x1000 时相同。</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>如果设置，通讯簿服务器不会在 AbUserEntry 表中包含为指定属性设置了此值的对象。例如，如果 <strong>msRTCSIP-PrimaryUserAddress</strong> 属性设置了此标志位，则不会将具有此属性的联系人写入数据库。</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>如果设置，通讯簿服务器不会在 AbUserEntry 表中包含没有为指定属性设置此值的对象。如果在一个对象上设置了 0x4000 和 0x8000 标志位，则标志位值设置为 0x4000 的属性优先，并且会在 AbUserEntry 表中排除该对象。</p></td>
</tr>
<tr class="even">
<td><p>0x10000</p></td>
<td><p>如果设置，则代表组对象。用户复制程序使用此标志位包含具有 <strong>groupType</strong> 属性且状态指示组（例如，通讯组列表或安全组）的联系人。</p></td>
</tr>
<tr class="odd">
<td><p>0x20000</p></td>
<td><p>如果设置，用户复制程序将使用此标志位在特定于设备的通讯簿服务器文件（即扩展名为 .dabs 的文件）中包含此属性。</p></td>
</tr>
</tbody>
</table>


在 Lync Server 的早期版本中，将更改应用于 Active Directory 时，管理员需要运行**CSUserDatabase**和**update – CSAddressBook** Windows PowerShell cmdlet，以立即将更改保存到 Lync Server 用户数据库和 RTCab 数据库中。 在 Lync Server 2013 中，Lync Server 用户复制器将从 Active Directory 中获取更改，并根据配置的间隔更新 Lync Server 用户数据库。 Lync Server 用户复制程序还会快速将更改传播到 RTCab 数据库，而管理员必须运行更新-CSAddressBook。 如果启用了通讯簿 Web 查询，则更改将在 Lync 客户端的搜索结果中反映出来。 只有在启用了通讯簿文件下载时，管理员才需要运行 CSAddressBook 更新。

<div>


> [!NOTE]  
> 默认情况下，Lync Server 用户复制程序每5分钟自动运行一次。 您可以使用 CSUserReplicatorConfiguration-ReplicationCycleInterval &lt; &gt;配置此间隔。



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a>筛选通讯簿

可以基于 AbAttribute 表中列出的某些 Active Directory 域服务属性来控制在通讯簿服务器文件中填充的用户。 **msExchangeHideFromAddressBook** 属性是一个用于筛选的此类属性。 这是由 Exchange 架构添加的用户属性。 如果将此属性的值为 TRUE，Exchange Server 将使用此属性隐藏 Outlook 全局地址列表 (GAL) 中的联系人。 同样，如果此属性的值为 TRUE，用户复制程序不会在 AbUserEntry 表中包含该用户，并且该用户不会包含在通讯簿服务器文件中。

可以使用某些标志位定义用于通讯簿服务器属性的筛选器。例如，某些标志位的状态可以将属性标识为包含属性或排除属性。用户复制程序筛选出包含排除属性的联系人，并筛选出不包含包含属性的联系人。

<div>


> [!WARNING]  
> 有关筛选通讯簿的详细信息，请参阅<A href="https://technet.microsoft.com/library/gg415643(v=ocs.15)">Lync server 2013 中的通讯簿服务器 cmdlet</A>和<A href="https://go.microsoft.com/fwlink/?linkid=330430">筛选器 lync 2013 通讯簿</A>



</div>

目前，存在三种不同的筛选器。下表列出了这些筛选器。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>属性</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0x800</p></td>
<td><p>如果设置，将标识联系人的必需属性。用户复制程序使用此标志位筛选出未包含至少一个必需属性的联系人。OuPathId 是必需属性，始终会设置。因此，应至少设置一个其他必需属性。否则，仍无法将联系人（即具有必需属性 OuPathId 的值）写入数据库。例如，如果将 <strong>telephoneNumber</strong> 和 <strong>homePhone</strong> 定义为必需属性，则只有至少具有其中一个属性的联系人才会写入数据库。</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>如果设置，将标识排除属性。用户复制程序使用此标志位筛选出包含此属性的联系人。例如，如果将 <strong>msRTCSIP-PrimaryUserAddress</strong> 定义为排除属性，则不会将具有此属性的联系人写入数据库。</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>如果设置，将标识包含属性。用户复制程序使用此标志位筛选出不包含此属性的联系人。例如，如果将 <strong>msRTCSIP-PrimaryUserAddress</strong> 定义为包含属性，则仅将具有此属性的联系人写入数据库。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 如果同时设置了 0x4000（排除属性）和 0x8000（包含属性）标志位，0x4000 位将覆盖 0x8000 位，并且将排除联系人。



</div>

尽管可以筛选通讯簿以仅包含特定用户，但是限制条目不会限制其他用户联系筛选出的用户或查看其状态的能力。通过输入用户的完整登录名，用户始终可以查找通讯簿中不存在的用户，手动向这些用户发送即时消息或者手动发起呼叫。此外，还可以在 Outlook 中找到用户的联系人信息。

通过通讯簿文件中的完整联系人记录，您可以使用 Lync Server 启动电子邮件、电话或企业语音呼叫（即，如果在服务器上启用企业语音）和未配置为进行会话初始化的用户协议（SIP），某些组织更喜欢在其通讯簿服务器条目中包含启用了 SIP 的用户。 您可以通过清除以下必需属性的**Flags**列中的0x800 位来筛选通讯簿，使其仅包含启用了 SIP 的用户： **mailNickname**、 **telephoneNumber**、 **homePhone**和**mobile**。 您还可以将通讯簿筛选为仅包含启用了 SIP 的用户，方法是在**msRTCSIP-PrimaryUserAddress**属性的**Flags**列中设置0x8000 （include 属性）。 这还有助于从通讯簿文件中排除服务帐户。

修改 AbAttribute 表后，可以通过运行 cmdlet **Update-CsUserDatabase** 命令刷新 AbUserEntry 表中的数据。 UR 复制完成后，可以通过手动运行 cmdlet **UpdateCsAddressBook** 命令更新通讯簿服务器文件存储中的文件。

<div>


> [!NOTE]  
> 不能以管理方式配置通讯簿服务器所在的前端服务器。 在部署过程中选择一个（通常是部署第一台前端服务器）。 如果出现故障，通讯簿服务将移至另一台前端服务器，并且不需要管理方面的注意力。



</div>

<div>


> [!IMPORTANT]  
> 如果已从多林部署或父/子部署（例如，在移动到 Lync Server 之前合并基础结构）对基础结构进行了合并或其他修改，则可能会发现某些用户的通讯簿服务下载和通讯簿 Web 查询失败。 在包含多个域或林的部署中时，将在出现此问题的用户对象上填充 <STRONG>MsRTCSIP-OriginatorSid</STRONG> 属性。 为了解决此问题，必须在这些对象上将 <STRONG>MsRTCSIP-OriginatorSid</STRONG> 属性设置为 NULL。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

