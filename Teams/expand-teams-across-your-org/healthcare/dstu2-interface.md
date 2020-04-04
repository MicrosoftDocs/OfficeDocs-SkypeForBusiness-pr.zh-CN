---
title: 患者应用和 EHR 集成 DSTU2 界面
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: 了解团队中的 DSTU2 界面规范，包括设置或重新配置 FHIR 服务器以使用 Microsoft 团队患者应用。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f09f43af431b3f0cc6d9f984171206f2549a550a
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136952"
---
# <a name="dstu2-interface-specification"></a>DSTU2 接口规范

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

设置或重新配置 FHIR 服务器以处理 Microsoft 团队患者应用需要了解应用需要访问的数据。 FHIR 服务器必须使用以下资源的捆绑包支持发布请求：

- [档案](#patient)
- [知识产权](#observation)
- [条件](#condition)
- [产生](#encounter)
- [过敏症 intolerance](#allergyintolerance)
- [内](#coverage)
- [药物订货](#medication-order)
- [位置](#location)

> [!NOTE]
> 患者资源是唯一必需的资源（根本不会加载应用程序）。 但是，建议合作伙伴针对 Microsoft 团队患者应用的最佳最终用户体验，针对以下提供的针对以上提及的所有资源提供支持。

来自 Microsoft 团队患者应用的来自多个资源的查询向 FHIR 服务器的 URL 发布一个捆绑（批处理）请求。 服务器处理每个请求，并返回每个请求所匹配的资源的捆绑包。 有关详细信息和示例，请[https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction)参阅。

所有以下 FHIR 资源应可通过直接资源参考访问。

## <a name="conformance-minimum-required-field-set"></a>一致性最低要求字段集

 FHIR 服务器必须实现一致性声明，才能为我们提供其功能的实际摘要。 我们期望 DSTU2 FHIR 服务器中的以下参数：

1. 余下
   1. 众
   2. 相交
   3. 资源：类型
   4. 安全性： [OAuth uri 的扩展](https://hl7.org/fhir/extension-oauth-uris.html)
2. FhirVersion （我们的代码需要此内容才能了解我们支持多个版本时应透视到的版本。）

有关[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)此字段集的其他详细信息，请参阅。

## <a name="patient"></a>档案

以下是 " [Argonaut" 患者档案](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)字段子集的最少必填字段：

1. 名称。家庭
2. 名称。给定
3. 性别
4. BirthDate
5. MRN （标识符）

除了 Argonaut 字段，为患者应用提供出色的用户体验还会读取以下字段：

1. 名称。使用
2. 名称。前缀
3. CareProvider （此对患者资源的参考应包括以下示例中所示的显示字段。）

* * *

    请求：获取 <fhir-服务器>/Patient/<患者 id>
    
    回复： {"resourceType"： "患者"，"id"： "<患者 id>"，。
      .
      .
      "名称"： [{"使用"： "官方"，"prefix"： ["Mr"]，"family"： ["Chau"]，"Hugh"： [""]}]，"标识符"： [{"使用"： "官方"，"类型"： {"编码"： [{"systemhttps://hl7.org/fhir/v2/0203"： "？"，"1234567"}]，"性别"： "男"，"出生日期"： "1957-06-05"，"careProvider"： [{"显示"： "Jane Doe"}]，}

* * *

资源搜索在/Patient/_search 使用 POST 方法，并使用以下参数：

1. 标识号
2. 系列：包含 = （搜索其系列名称包含该值的所有患者。）
3. 给定 =\<substring>
4. name =\<substring>
5. 出生日期 = （完全匹配）
6. \_计数（应返回的最大结果数） <br> 该响应应包含作为搜索结果返回的记录的总数，PatientsApp 将使用该\_计数来限制返回的记录数。
7. 标识符 =\<mrn>

目标是能够搜索和筛选患者，如下所示：

- ID：这是 FHIR 中的每个资源具有的资源 ID。
- MRN：这是临床人员将知道的患者的实际标识符。 我们理解此 MRN 基于 FHIR 中的标识符资源内的标识符类型
- 名称
- Birthdate

请参阅下面的此通话示例。

* * *

    请求： POST <fhir-server>/Patient/_search 请求正文：给定 = hugh&家族 = chau
    
    响应： {"resourceType"： "捆绑包"，"id"： "<捆绑包-id>"，。
      .
      .
      "entry"： [{"资源"： {"resourceType"： "患者"，"id"： "<患者 id>"，"名称"： [{"文本"： "Hugh Chau"，"family"： ["Hugh"]，""： [""]}]，"性别"： "男"，"出生日期"： "1957-06-05

* * *

有关[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)此字段集的其他详细信息，请参阅。

## <a name="observation"></a>知识产权

以下是最少的必填字段，这些字段是 Argonaut 的重要符号配置文件的子集：

 1. 有效（日期时间或周期）
 2. 编码代码
 3. ValueQuantity 值

除了 Argonaut 字段，为患者应用提供出色的用户体验还会读取以下字段：

 1. 代码编码。显示
 2. ValueQuantity 单位

如果使用组件观测值，则相同的逻辑适用于每个组件观察。

资源搜索使用 GET 方法和以下参数：

1. 患者 =\<患者 id\>
2. 排序： desc =\<field ex 状态\>

目标是能够检索患者的最新重要标志 [DSTU saz] （"VitalSigns"）。

* * *

    请求：获取 <fhir-服务器>/Observation？患者 =<患者 id>&_sort:d esc = 日期&category = 重要标志
    
    响应： {"resourceType"： "捆绑包"，"id"： "<捆绑包-id>"，"键入"： "searchset"，"total"：20，"entry"： [{"resource"： "<资源 id>"，"类别"： {"编码"： [{code "：" 关键签名 "}]，}，" code "： {" 编码 "： [{" system "："http://loinc.org"，" 代码 "：" 39156-5 "，" display "：" bmi "}]，}，" effectiveDateTime "：" 2009-12-01 "，" valueQuantity "： {" 值 "：34.4，" unit "：" 公斤/m2 "，" system "："http://unitsofmeasure.org"，" 代码 "：" 公斤/m2 "}}，}。
        .
        .
      ] }

* * *

有关[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)此字段集的其他详细信息，请参阅。

## <a name="condition"></a>条件

下面是[Argonaut 条件配置文件](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)子集的最少必填字段：

1. 代码。编码 [0]。画面

除了 Argonaut 字段外，还可以为患者应用提供出色的用户体验，还可以读取以下字段：

1. 录制日期
2. 严重性

资源搜索使用 GET 方法和以下参数：

1. 患者 =\<患者 id>
2. _count =\<最大结果>

请参阅下面的此呼叫示例：

* * *

    请求：获取 <fhir-服务器>/Condition？患者 =<患者 id>&_count = 10
    
    响应： {"resourceType"： "捆绑包"，"id"> <： "searchset"： ""，"total"：1，"entry"： [{"资源"： {""： "Condition"，"id"： "<资源 id>"，"代码"： {"编码"： [{"system"： "http://snomed.info/sct"，"代码"： "386033004"，"显示"： "Neuropathy （nerve 损坏）"}]}，"dateRecorded"： "2018-09-17"，"严重性"： {"编码"： [{"system"： "http://snomed.info/sct"，"代码"： "24484000"，"显示"： "严重"}]}}，}]}

* * *

有关[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)此字段集的其他详细信息，请参阅。

## <a name="encounter"></a>产生

以下是最少必填字段，这些字段是 "美国核心" 基本配置文件 "必须具有" 字段的子集：

1. 状态栏
2. 键入 [0]。编码 [0]。画面

此外，美国核心的以下字段会遇到配置文件的 "必须支持" 字段

1. 句号。开始
2. 位置 [0]。位置。显示

资源搜索使用 GET 方法和以下参数：

1. 患者 =\<患者 id>
2. _sort： desc =\<field （ex） 日期>
3. _count =\<最大结果>

目标是能够检索患者的最后一个已知位置。 每个遇到的都引用一个位置资源。 该引用还应包含位置的显示字段。 请参阅下面的此通话示例。
* * *

    请求：获取 <fhir-服务器>/Encounter？患者 =<患者 id>&_sort:d esc = 日期&_count = 1
    
    响应： {"resourceType"： "捆绑包"，"类型"： "searchset"，"total"：1，"entry"： [{"id"： "" 遇到 ""，"id"： "<资源 id>"，"标识符"： [{"使用"： "官方"，"值"： "<id>"}]，"状态"： "已到达"，"类型"： [{"编码"： [{"显示"： "约会"}]，}]，"患者"： {"参考"： "患者/<患者 id>"}，"时间段"： {"start"： "09/17/2018 1:00:00 PM"}，"位置"： [{"位置"： {"display"： [{"位置"： {"display"： "ENT"}，}]}}]}

* * *

有关[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)此字段集的其他详细信息，请参阅。

## <a name="allergyintolerance"></a>AllergyIntolerance

以下是最少的必填字段，它们是 Argonaut AllergyIntolerance 配置文件的子集：

1. 代码。文本
2. 代码。编码 [0]。画面
3. 状态栏

除了 Argonaut 字段，为患者应用提供出色的用户体验还会读取以下字段：

1. RecordedDate
2. 备注。文本
3. 反应 [...]。物质。文本
4. 反应 [...]。表现形式 [...]。文本
5. 文本 Div

资源搜索使用 GET 方法和以下参数：

1. 患者 = \<患者 id>

请参阅下面的此呼叫示例：

* * *

    请求：获取 <fhir-服务器>/AllergyIntolerance？患者 =<患者 id>
    
    响应： {"resourceType"： "捆绑包"，"id"> <： "searchset"： ""，"total"：1，"entry"： [{"资源"： {"resourceType"： "AllergyIntolerance"，"id"： "<资源 id>"，"recordedDate"： "2018 日-17T07：00： 00.000 Z"，"物质"： {"text"： "Cashew 螺母"}，"status"： "已确认"，"反应"： [{"物质"： {"文本"： "Cashew 螺母 allergenic 提取 Injectable 产品"}，"表现形式"： [{"文本"： "Anaphylactic 反应"}]}]}

* * *

有关[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)此字段集的其他详细信息，请参阅。

## <a name="medication-order"></a>药物订货

以下是最少的必填字段，它们是 Argonaut MedicationOrder 配置文件的子集：

1. DateWritten
2. Prescriber 显示
3. 药物的显示（如果参考）
4. 药物文本（如果概念）

除了 Argonaut 字段外，还可以为患者应用提供出色的用户体验，还可以读取以下字段：

1. DateEnded
2. DosageInstruction
3. 文本 Div

资源搜索使用 GET 方法和以下参数：

1. 患者 =\<患者 id>
2. _count =\<最大结果>

请参阅下面的此呼叫示例：

* * *

    请求：获取 <fhir-服务器>/MedicationOrder？患者 =<患者 id>&_count = 10
    
    响应： {"resourceType"： "捆绑包"，"id"： "<捆绑包-id>"，"type"： "searchset"，"total"：1，"entry"： [{"资源"： {"resourceType"： "MedicationOrder"，"id"： "<资源 id>"，"dateWritten"： "2018-09-17"，"medicationCodeableConcept"： {"text"： "Lisinopril 20 MG 平板电脑"}，"prescriber"： {"display"： "Jane Doe"}，"dosageInstruction"： [{"文本"： "1 天"}]}}]}

* * *  

有关[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)此字段集的其他详细信息，请参阅。

## <a name="coverage"></a>内

以下是 "最少必填字段"，不包含在美国 Core 或 Argonaut 配置文件中：

1. Payor

资源搜索使用 GET 方法和以下参数：

1. 患者 =\<患者 id>

请参阅下面的此呼叫示例：

* * *

    请求：获取 <fhir-服务器>/Coverage？患者 =<患者 id>
    
    响应： {"resourceType"： "捆绑包"，"键入"： "searchset"，"total"：1，"entry"： [{"resource"： "<资源 id>"，"计划"： "没有主保险"，"订阅"： {"reference"： "患者/<患者 id>"}}]}

* * *

有关[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)此字段集的其他详细信息，请参阅。

## <a name="location"></a>位置

此资源仅用作 "[遇到](#encounter)" 资源的参考。

有关[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)此字段集的其他详细信息，请参阅。
