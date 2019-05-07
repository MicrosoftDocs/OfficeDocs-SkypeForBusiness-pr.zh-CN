---
title: " 患者应用程序和 EHR 集成 DSTU2 接口"
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Microsoft 团队患者 app EHR 集成
ms.openlocfilehash: 85fd90fb338f8b19762dc9433fa1dc281f3cedff
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2019
ms.locfileid: "33643071"
---
# <a name="dstu2-interface-specification"></a>DSTU2 接口规范

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

设置或重新配置 FHIR server 以使用 Microsoft 团队患者应用程序需要了解哪些应用程序需要访问的数据。 FHIR 服务器必须支持的以下资源使用捆绑的 POST 请求：

- [患者](#patient)
- [观察值](#observation)
- [条件](#condition)
- [遇到](#encounter)
- [过敏 intolerance](#allergyintolerance)
- [覆盖范围](#coverage)
- [用药顺序](#medication-order)
- [位置](#location)

> [!NOTE]
> 患者资源是唯一的必填资源 （该应用程序将不会加载根本。 但是，建议合作伙伴实现支持的每个规范下面提供的 Microsoft 团队患者 App 最佳最终用户体验的所有上面提到资源。

查询从多个资源的 Microsoft 团队患者应用程序发布到 FHIR 服务器的 URL 的请求的绑定 （批次）。 该服务器处理每个请求，并返回匹配的每个请求的资源的绑定。 有关详细信息和示例，请参阅[https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction)。

下列所有 FHIR 资源应都可访问的直接资源引用。

## <a name="conformance-minimum-required-field-set"></a>一致性声明最低必填的字段设置

 FHIR 服务器必须实现一致性的我们可以真实其功能的摘要。 我们期望 DSTU2 FHIR 服务器中的参数如下：

1. REST
   1. 模式
   2. 交互
   3. 资源： 类型
   4. 安全性：[扩展的 OAuth Uri](http://hl7.org/fhir/extension-oauth-uris.html)
2. FhirVersion （我们的代码需要此选项可了解我们应该因为我们支持多个版本侧重于哪个版本。）

请参阅[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)有关此字段的其他详细信息设置。

## <a name="patient"></a>患者

这是最小的必填的字段，它们是[Argonaut 患者配置文件](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)字段的子集：

1. Name.Family
2. Name.Given
3. 性别
4. 出生日期
5. MRN （标识符）

除了 Argonaut 字段中，对于出色的用户体验患者应用程序还读取以下字段：

1. Name.Use
2. Name.Prefix
3. CareProvider （对患者资源本参考应包含在以下示例中所示的显示字段）。

* * *

    请求： 获取 <fhir-server>/患者/<patient-id>
    
    响应: {"resourceType":"患者"，"id":"<patient-id>"。
      .
      .
      "名称": [{"使用":"正式"，"前缀":"Mr""系列":"Chau""授予":"Hugh"}]，"标识符": [{"使用":"正式"，"类型": {"编码": [{"系统":"http://hl7.org/fhir/v2/0203"，"代码":"MR"}]}，"value":"1234567"}]，"性别":"男"，"出生日期": 1957年"-06-05"，"careProvider": [{"显示":"Jane Doe"}]，}

* * *

资源搜索使用 POST 方法 /Patient/_search 和以下参数：

1. id
2. 系列： 包含 = （系列名称中包含值的所有患者搜索）。
3. 给定 =\<substring>
4. 名称 =\<substring>
5. 出生日期 =(exact match)
6. \_计数 （最大应返回的结果数） <br> 响应应包含的搜索，由于返回记录的总计数和\_计数将由 PatientsApp 以限制返回的记录数。
7. 标识符 =\<mrn>

目标是能够搜索和筛选由以下患者：

- ID： 这是每个资源 FHIR 中的包含的资源 ID。
- MRN： 这是患者临床人员自己知道的实际标识符。 我们了解此 MRN 基于内 FHIR 标识符资源的标识符的类型
- 名称
- 出生日期

请参阅下面的示例的此呼叫。

* * *

    请求： POST <fhir-server>/患者/_search 请求正文： 给定 = hugh&family = chau
    
    响应: {"resourceType":"捆绑"、"id":"<bundle-id>"。
      .
      .
      entry: [{"资源": {"resourceType":"患者"，"id":"<patient id>"、"name": [{"text":"Hugh Chau"，在"系列":"Chau""授予":"Hugh"}]，"性别":"男"，"出生日期":"1957年 06 05"}，"搜索": {"模式":"匹配"}}]}

* * *

请参阅[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)有关此字段的其他详细信息设置。

## <a name="observation"></a>观察值

这是最小必填的字段，是 Argonaut 重要征兆配置文件的子集：

 1. 有效 （日期时间或段）
 2. Code.Coding.Code
 3. ValueQuantity.Value

除了 Argonaut 字段中，对于出色的用户体验患者应用程序还读取以下字段：

 1. Code.Coding.Display
 2. ValueQuantity.Unit

如果使用组件观察，相同的逻辑将适用于每个组件观察值。

资源搜索使用 GET 方法并使用以下参数：

1. 患者 =\<患者 id\>
2. 排序： desc =\<ex 字段。 日期\>

目标是能够检索为患者，[VitalSigns.DSTU.saz] （观察？） 的最新的重要标志。

* * *

    请求： 获取观察值 <fhir-server>？ 患者 = <patient-id>&_sort:desc = date&category = 重要迹象
    
    响应: {"resourceType":"捆绑"、"id":"<bundle id>"、"类型":"searchset"，"total": 20，entry: [{"资源": {"resourceType":"观察值"、"id":"<resource id>"、"category": {"编码": [{代码":"重要迹象"}]，}，"代码": {"编码": [{"系统":"http://loinc.org"，"代码":"39156-5"，"显示":"bmi"}]，}，"effectiveDateTime":"2009年-12-01"，"valueQuantity": {"value": 34.4，"单位":"千克/m2"、"系统":"http://unitsofmeasure.org"，"代码":"千克/m2"}}，}。
        .
        .
      ] }

* * *

请参阅[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)有关此字段的其他详细信息设置。

## <a name="condition"></a>条件

这是最小必填的字段，是[Argonaut 条件配置文件](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)的子集：

1. Code.Coding[0]。显示

除了 Argonaut 字段中，为出色的用户体验患者应用程序还可以阅读以下字段：

1. 记录日期
2. 严重级别

资源搜索使用 GET 方法并使用以下参数：

1. 患者 =\<患者 id>
2. _count =\<最大 results>

请参阅下面的示例，此呼叫的：

* * *

    请求： 获取 <fhir server>/条件？ 患者 = <patient id>&_count = 10
    
    响应: {"resourceType":"捆绑"、"id":"<bundle id>"、"类型":"searchset"，"total": 1，entry: [{"资源": {"resourceType":"条件"、"id":"<resource id>"、"代码": {"编码": [{              "系统":"http://snomed.info/sct"，"代码":"386033004"，"显示":"Neuropathy （神经损害）"}]}，"dateRecorded":"2018年-09-17"，"severity": {"编码": [{"system":"http://snomed.info/sct"，"代码":"24484000"，"显示":"严重"}]}}，}]}

* * *

请参阅[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)有关此字段的其他详细信息设置。

## <a name="encounter"></a>遇到

这是最小的必填的字段，它们是美国核心遇到的配置文件"必须具有"字段的子集：

1. 状态
2. 类型 [0]。编码 [0]。显示

此外，从美国核心遇到配置文件的以下字段"必须支持"字段

1. Period.Start
2. 位置 [0]。Location.Display

资源搜索使用 GET 方法并使用以下参数：

1. 患者 =\<患者 id>
2. _sort:desc =\<ex 字段。 date>
3. _count =\<最大 results>

目标是能够检索患者的最后一个已知的位置。 每个遇到引用的位置资源。 引用还应包括的位置显示字段。 请参阅下面的示例的此呼叫。
* * *

    请求： 获取 <fhir-server>/遇到？ 患者 = <patient-id>&_sort:desc = date&_count = 1
    
    响应: {"resourceType":"绑定"，"类型":"searchset"，"total": 1，entry: [{"资源": {"resourceType":"遇到"、"id":"<resource id>"、"标识符": [{"使用":"正式"，"value":"<id>"}]，"状态":"访问"，"键入": [{"编码": [{"显示":"约会"}]，}]、"患者": {"参考":"<patient/患者-id>"}，"时间段": {"启动":"09/17/2018年 1:00:00"}，"位置": [{             "位置": {"显示":"培训班-企业"}，}]}}]}

* * *

请参阅[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)有关此字段的其他详细信息设置。

## <a name="allergyintolerance"></a>AllergyIntolerance

这是最小必填的字段，是 Argonaut AllergyIntolerance 配置文件的子集：

1. Code.Text
2. Code.Coding[0]。显示
3. 状态

除了 Argonaut 字段中，对于出色的用户体验患者应用程序还读取以下字段：

1. RecordedDate
2. Note.Text
3. [.] 的反应。Substance.Text
4. [.] 的反应。体现 [.]。文本
5. Text.Div

资源搜索使用 GET 方法并使用以下参数：

1. 患者 =\<患者 id>

请参阅下面的示例，此呼叫的：

* * *

    请求： 获取 <fhir-server>/AllergyIntolerance？ 患者 = <patient id>
    
    响应: {"resourceType":"捆绑"、"id":"<bundle id>"、"类型":"searchset"，"total": 1，entry: [{"资源": {"resourceType":"AllergyIntolerance"，"id":"<resource id>"、"recordedDate":"2018年-09-17T07:00:00.000Z"，"材料": {"text":"Cashew 具体"}，"状态":"确认"，"反应": [{"材料": {"text":"cashew 螺母 allergenic 提取注射产品"}，"manifestati在": [{"text":"Anaphylactic 反应"}]}]}}]}

* * *

请参阅[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)有关此字段的其他详细信息设置。

## <a name="medication-order"></a>用药顺序

这是最小必填的字段，是 Argonaut MedicationOrder 配置文件的子集：

1. DateWritten
2. Prescriber.Display
3. Medication.Display (如果引用)
4. Medication.Text (如果概念)

除了 Argonaut 字段中，为出色的用户体验患者应用程序还可以阅读以下字段：

1. DateEnded
2. DosageInstruction.Text
3. Text.Div

资源搜索使用 GET 方法并使用以下参数：

1. 患者 =\<患者 id>
2. _count =\<最大 results>

请参阅下面的示例，此呼叫的：

* * *

    请求： 获取 <fhir-server>/MedicationOrder？ 患者 = <patient id>&_count = 10
    
    响应: {"resourceType":"捆绑"、"id":"<bundle id>"、"类型":"searchset"，"total": 1，entry: [{"资源": {"resourceType":"MedicationOrder"，"id":"<resource id>"、"dateWritten":"2018年-09-17"，"媒体cationCodeableConcept": {"text":"Lisinopril 20 MG 口头 Tablet"}，"prescriber": {"显示":"Jane Doe"}，"dosageInstruction": [{"text":"1 每天"}]}}]}

* * *  

请参阅[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)有关此字段的其他详细信息设置。

## <a name="coverage"></a>覆盖范围

这是最小的必填的字段，不受美国核心或 Argonaut 配置文件：

1. 付款方

资源搜索使用 GET 方法并使用以下参数：

1. 患者 =\<患者 id>

请参阅下面的示例，此呼叫的：

* * *

    请求： 获取覆盖范围 <fhir-server>？ 患者 = <patient id>
    
    响应: {"resourceType":"绑定"，"类型":"searchset"，"total": 1，entry: [{"资源": {"resourceType":"覆盖"，"id":"<resource id>"、"计划":"无主保险"、"订阅者": {"参考":"患者 /<patient id>"}}}]}

* * *

请参阅[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)有关此字段的其他详细信息设置。

## <a name="location"></a>位置

此资源仅用作[遇到](#encounter)资源的引用。

请参阅[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)有关此字段的其他详细信息设置。
