---
title: 정확한 데이터 매치를 사용한 사용자 지정 중요한 정보 유형 만들기
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 정확한 데이터 매치 기반 분류를 사용하여 사용자 지정 중요한 정보 유형을 만드는 방법을 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 141178db0ba221d6e8ef9c5f3d4d85bb90607fb1
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60160067"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a>분류에 기반한 정확한 데이터 매치를 사용한 사용자 지정 중요한 정보 유형 만들기

[사용자 지정 중요한 정보 유형](sensitive-information-type-learn-about.md)은 중요한 항목을 식별하는 데 도움을 주어 해당 항목이 실수로 또는 부적절하게 공유되는 것을 방지할 수 있습니다. 다음을 기반으로 사용자 지정 SIT(중요한 정보 유형)를 정의합니다.

- 패턴
- *직원*, *배지* 또는 *ID* 와 같은 키워드 증명 정보
- 특정 패턴의 증거에 대한 문자 근접성
- 신뢰 수준

 이러한 사용자 지정 중요한 정보 유형은 대부분의 조직에 필요한 비즈니스 요구 사항을 충족합니다.

하지만 일반적인 패턴을 기반으로 일치 항목을 찾는 대신 정확한 데이터 값을 사용하는 사용자 지정 SIT(중요한 정보 유형)을 원한다면 어떻게 해야 할까요? 정확한 데이터 매치(EDM) 기반 분류를 사용하여 다음과 같이 설계된 사용자 지정 중요한 정보 유형을 만들 수 있습니다.

- 역동적이며 쉽게 새로 고침
- 확장성 향상
- 가양성 수 감소
- 구조화된 중요한 데이터 사용
- 중요한 정보를 더 안전하게 처리
- 여러 Microsoft 클라우드 서비스와 함께 사용 가능

![EDM 기반 분류.](../media/EDMClassification.png)

EDM 기반 분류를 사용하면 중요한 정보 데이터베이스의 정확한 값을 참조하는 사용자 지정 중요한 정보 유형을 만들 수 있습니다. 데이터베이스는 매일 새로 고칠 수 있으며 최대 1억 행의 데이터를 포함할 수 있습니다. 직원, 환자 또는 고객이 계속 이동하고 기록이 변경됨에 따라 사용자 지정 중요한 정보 유형을 적절하고 최신인 상태로 유지합니다. 또한 EDM 기반 분류를 [데이터 손실 방지 정책](dlp-learn-about-dlp.md) 또는 [Microsoft Cloud App Security 파일 정책](/cloud-app-security/data-protection-policies) 등의 정책과 사용할 수 있습니다.

> [!NOTE]
> Microsoft 365 Information Protection은 다음의 더블 바이트 문자 집합 언어를 지원합니다.
>
> - 중국어(간체)
> - 중국어(번체)
> - 한국어
> - 일본어
>
> 이 지원은 중요한 정보 유형에 대해 사용할 수 있습니다. 자세한 정보는 [더블 바이트 문자 집합 릴리스 정보(미리 보기)에 대한 정보 보호 지원](mip-dbcs-relnotes.md)을 참조하세요.

## <a name="required-licenses-and-permissions"></a>필수 라이선스 및 사용 권한

이 문서에 설명된 작업을 수행하려면 전역 관리자, 준수 관리자 또는 Exchange Online 관리자여야 합니다. DLP 권한에 관한 자세한 내용은 [권한](data-loss-prevention-policies.md#permissions)을 참조하세요.

EDM 기반 분류가 이 구독에 포함되어 있습니다

- Office 365 E5
- Microsoft 365 E5
- Microsoft 365 E5 Compliance
- Microsoft E5/A5 Information Protection 및 거버넌스

## <a name="portal-links-for-your-subscription"></a>구독을 위한 포털 링크

|포털|전세계/GCC|GCC-High|DOD|
|---|---|---|---|
|Office SCC|compliance.microsoft.com|scc.office365.us|scc.protection.apps.mil|
|Microsoft 365 보안 센터|security.microsoft.com|security.microsoft.us|security.apps.mil|
|Microsoft 365 규정 준수 센터|compliance.microsoft.com|compliance.microsoft.us|compliance.apps.mil|

## <a name="the-work-flow-at-a-glance"></a>워크플로 한 눈에 보기

|단계|필요한 사항|
|---|---|
|[1단계: EDM 기반 분류 설정](#part-1-set-up-edm-based-classification)<br/><br/>(필요한 대로 수행)<br/>- [데이터베이스 스키마 편집](#editing-the-schema-for-edm-based-classification) <br/>- [스키마 제거](#removing-the-schema-for-edm-based-classification)|- 중요한 데이터에 대한 읽기 액세스 권한<br/>- XML 형식의 데이터베이스 스키마(예제 제공)<br/>- XML 형식의 규칙 패키지(예제 제공)<br/>- 보안 및 준수 센터에 대한 관리자 권한(Windows PowerShell 사용)|
|[2부: 중요 한 데이터를 해시하고 업로드](#part-2-hash-and-upload-the-sensitive-data)<br/><br/>(필요한 대로 수행)<br/>[데이터 새로 고침](#refreshing-your-sensitive-information-database)|- 사용자 지정 보안 그룹 및 사용자 계정<br/>- EDM 업로드 에이전트가 있는 컴퓨터에 대한 로컬 관리자 액세스 권한<br/>- 중요한 데이터에 대한 읽기 액세스 권한<br/>- 데이터를 새로 고치는 프로세스 및 일정|
|[3단계: Microsoft 클라우드 서비스로 EDM 기반 분류 사용](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services)|- DLP를 포함하는 Microsoft 365 구독<br/>- EDM 기반 분류 기능 사용|

### <a name="part-1-set-up-edm-based-classification"></a>1단계: EDM 기반 분류 설정

EDM 기반 분류 설정 및 구성에는 다음이 포함됩니다.

1. [중요한 데이터를 .csv .tsv 형식으로 저장](#save-sensitive-data-in-csv-or-tsv-format)
2. [중요한 정보 데이터베이스 스키마 정의](#define-the-schema-for-your-database-of-sensitive-information)
3. [규칙 패키지 만들기](#set-up-a-rule-package)

#### <a name="save-sensitive-data-in-csv-or-tsv-format"></a>중요한 데이터를 .csv .tsv 형식으로 저장

1. 사용하려는 중요한 정보를 식별합니다. 데이터를 앱에 내보낼 수 Microsoft Excel 텍스트 파일에 저장합니다. 이 파일은 파일 형식(.csv), .tsv(탭으로 구분된 값) 또는 파이프 구분(|) 형식으로 저장할 수 있습니다. 데이터 값에 주소와 같은 콤보가 포함될 수 있는 경우 .tsv 형식을 지정하는 것이 좋습니다.
데이터 파일에는 최대 다음을 포함할 수 있습니다.
   - 최대 1억 개의 중요한 데이터 행
   - 데이터 원본당 최대 32개의 열(필드)
   - 검색 가능으로 표시된 최대 5개의 열(필드)

2. 첫 번째 행에 EDM 기반 분류에 사용되는 필드 이름이 .csv 또는 .tsv 파일의 중요한 데이터를 구조화합니다. 파일에 "ssn", "birthdate", "firstname", "lastname" 등의 필드 이름이 있을 수 있습니다. 열 머리글 이름에는 공백이나 밑줄이 포함될 수 없습니다. 예를 들어, 이 문서에서 사용하는 샘플 .csv 파일은 *PatientRecords.csv* 라고 하며, 해당 열에는 *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN* 등이 포함되어 있습니다.

3. 중요한 데이터 필드의 형식에 유의하세요. 특히 콘텐츠에 콤보가 포함될 수 있는 필드(예: "Seattle,WA" 값이 포함된 주소)는 구문 분석할 때 .csv 필드로 구문 분석됩니다. 이를 방지하기 위해 .tsv 형식을 사용하거나 중요한 데이터 테이블에서 값이 들어 있는 콤보를 두 번 따옴표로 둘러싸습니다. 값을 포함하는 콤보에 공백도 포함되어 있는 경우 해당 형식과 일치하는 사용자 지정 SIT를 만들어야 합니다. 예를 들어 콤보 및 공백이 있는 여러 단어 문자열을 검색하는 SIT입니다.

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a>중요한 정보 데이터베이스의 스키마 정의

비즈니스 또는 기술상의 이유로 PowerShell 또는 명령줄을 사용하여 스키마 및 EDM에 중요한 정보 유형 패턴(규칙 패키지)을 생성하지 않는 것을 선호하는 경우 [정확한 데이터 일치 스키마 및 중요한 정보 유형 마법사](sit-edm-wizard.md)를 사용하여 스키마를 생성할 수 있습니다. 스키마 및 EDM 중요한 정보 유형 패턴을 생성했으면 EDM 기반 중요한 정보 유형을 사용할 수 있도록 하는 데 필요한 모든 단계를 완료하세요.

1. 중요한 정보 데이터의 스키마를 XML 형식으로 정의합니다(아래 예제와 비슷). 이 스키마 파일의 이름을 **edm.xml** 로 지정하고 데이터베이스의 각 열에 구문을 사용하는 줄이 있도록 구성합니다.

      `\<Field name="" searchable=""/\>`.

      - *필드 이름* 값에 열 이름을 사용합니다.
      - 최대 5개의 필드까지 검색할 수 있게 하려는 필드에 *searchable="true"* 를 사용합니다. 하나 이상의 필드를 검색할 수 있어야 합니다.

      예를 들어 다음 XML 파일은 검색 가능하도록 지정된 5개의 필드(*PatientID*, *MRN*, *SSN*, *Phone* 및 *DOB*)가 있는 환자 레코드 데이터베이스의 스키마를 정의합니다.

      (여기에 있는 예제를 복사, 수정 및 사용할 수 있습니다.)

      ```xml
      <EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
            <DataStore name="PatientRecords" description="Schema for patient records" version="1">
                  <Field name="PatientID" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
                  <Field name="MRN" searchable="true" />
                  <Field name="FirstName" />
                  <Field name="LastName" />
                  <Field name="SSN" searchable="true" />
                  <Field name="Phone" searchable="true" />
                  <Field name="DOB" searchable="true" />
                  <Field name="Gender" />
                  <Field name="Address" />
            </DataStore>
      </EdmSchema>
      ```

##### <a name="configurable-match-using-the-caseinsensitive-and-ignoreddelimiters-fields"></a>caseInsensitive 및 ignoredDelimiters 필드를 사용하여 구성 가능한 일치

위의 XML 샘플은 `caseInsensitive` 및 `ignoredDelimiters` 필드를 사용합니다.

스키마 정의에서 `true` 값에 설정된 ***caseInsensitive** _ 필드를 포함하면 EDM은 `PatientID` 필드의 대소문자 차이에 기반한 항목을 제외하지 않습니다. 따라서 EDM은 `PatientID` _ *FOO-1234** 및 **fOo-1234** 가 동일하다고 볼 것입니다.

지원되는 문자와 함께  ***ignoredDelimiters** _ 필드를 포함하면 EDM은 `PatientID`에서 해당 문자를 무시합니다. 따라서 EDM은 `PatientID` _ *FOO-1234** 및 `PatientID` **FOO#1234** 가 동일하다고 볼 것입니다. `ignoredDelimiters` 플래그는 영숫자가 아닌 모든 문자를 지원하며 다음은 몇 가지 예입니다.

- \.
- \-
- \/
- \_
- \*
- \^
- \#
- \!
- \?
- \[
- \]
- \{
- \}
- \\
- \~
- \;

`ignoredDelimiters` 플래그는 지원하지 않습니다.

- 0~9 사이 문자
- A-Z
- a-z
- \"
- \,

이 예에서 `caseInsensitive` 및 `ignoredDelimiters` 모두 사용되는 경우, EDM은 **FOO-1234** 및 **fOo#1234** 가 동일하다고 보고, 환자 기록을 중요한 정보 유형으로 분류합니다. 

1. 커넥트 보안 & 준수 센터 PowerShell에 대한 커넥트 절차를 사용하여 보안 & [PowerShell에 보호합니다.](/powershell/exchange/connect-to-scc-powershell)

2. 데이터베이스 스키마를 업로드 하려면 다음과 같은 cmdlet을 한 번에 하나씩 실행하십시오:

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      다음과 같이 확인하라는 메시지가 표시됩니다.

      > 확인
      >
      > 이 작업을 수행하시겠습니까?
      >
      > 'patientrecords' 데이터 저장소의 새로운 EDM 스키마를 가져옵니다.
      >
      > \[Y\] 예 \[A\] 모두 예 \[N\] 아니요 \[L\] 모두 아니요 \[?\] 도움말(기본값: "Y"):

> [!TIP]
> 확인하지 않고 변경 사항을 적용하려면, 5단계에서 New-DlpEdmSchema -FileData $edmSchemaXml 대신 이 cmdlet을 사용하십시오.

> [!NOTE]
> EDMSchema를 추가 사항으로 업데이트하는 데 10~60분이 소요될 수 있습니다. 추가 사항을 사용하는 단계를 실행하기 전에 업데이트를 완료해야 합니다.

#### <a name="set-up-a-rule-package"></a>규칙 패키지 설정

1. 다음 예제와 같이 in XML 형식(유니코드 인코딩 사용)에 규칙 패키지를 생성하세요. (여기에 있는 예제를 복사, 수정 및 사용할 수 있습니다.)

      규칙 패키지를 설정할 때 .csv .tsv 파일을 올바르게 참조하고 파일을edm.xml **합니다.** (여기에 있는 예제를 복사, 수정 및 사용할 수 있습니다.) 이 샘플 xml에서 EDM 중요 유형을 만들려면 다음 필드를 사용자 지정해야 합니다.

      - **RulePack ID & ExactMatch ID**:[New-GUID](/powershell/module/microsoft.powershell.utility/new-guid)를 사용하여 GUID를 생성합니다.

      - **Datastore**: 이 필드는 사용할 EDM 조회 데이터 저장소를 지정합니다. 구성된 EDM 스키마의 데이터 원본 이름을 입력합니다.

      - **idMatch**: 이 필드는 EDM의 기본 요소를 가리킵니다.
        - Matches: 정확한 조회에 사용할 필드를 지정합니다. 데이터 저장소의 EDM 스키마에서 검색 가능한 필드 이름을 입력합니다.
        - Classification: 이 필드는 EDM 조회를 트리거하는 중요한 유형 일치를 지정합니다. 기존 기본 제공 이름이나 GUID 또는 사용자 지정 중요 유형 정보를 제공할 수 있습니다. 제공된 중요 정보 유형과 일치하는 문자열은 해시되고 중요 정보 테이블의 모든 항목과 비교됩니다. 성능 문제가 발생하지 않도록 하려면 EDM에서 사용자 지정 중요 정보 유형을 분류 요소로 사용하는 경우 지원 키워드를 추가하거나 사용자 지정 분류에 중요한 정보 유형의 정의에 형식을 포함하여 많은 비율(예: "임의의 숫자" 또는 "임의의 5글자")과 일치하는 내용을 사용하지 않도록 하세요.

      - **Match:** 이 필드는 idMatch의 근접성에서 찾은 추가 증명을 가리킵니다.
        - Matches: 데이터 저장소의 EDM 스키마에 필드 이름을 입력합니다.
      - **리소스:** 이 섹션에서는 여러 로캘에서 중요한 유형의 이름과 설명을 지정합니다.
        - idRef: ExactMatch ID의 GUID를 입력합니다.
        - 이름 및 설명: 필요에 따라 사용자 지정합니다.

      ```xml
      <RulePackage xmlns="http://schemas.microsoft.com/office/2018/edm">
        <RulePack id="fd098e03-1796-41a5-8ab6-198c93c62b11">
          <Version build="0" major="2" minor="0" revision="0" />
          <Publisher id="eb553734-8306-44b4-9ad5-c388ad970528" />
          <Details defaultLangCode="en-us">
            <LocalizedDetails langcode="en-us">
              <PublisherName>IP DLP</PublisherName>
              <Name>Health Care EDM Rulepack</Name>
              <Description>This rule package contains the EDM sensitive type for health care sensitive types.</Description>
            </LocalizedDetails>
          </Details>
        </RulePack>
        <Rules>
          <ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
            <Pattern confidenceLevel="65">
              <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
            </Pattern>
            <Pattern confidenceLevel="75">
              <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
              <Any minMatches ="3" maxMatches ="6">
                <match matches="PatientID" />
                <match matches="MRN"/>
                <match matches="FirstName"/>
                <match matches="LastName"/>
                <match matches="Phone"/>
                <match matches="DOB"/>
              </Any>
            </Pattern>
          </ExactMatch>
          <LocalizedStrings>
            <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB371">
              <Name default="true" langcode="en-us">Patient SSN Exact Match.</Name>
              <Description default="true" langcode="en-us">EDM Sensitive type for detecting Patient SSN.</Description>
            </Resource>
          </LocalizedStrings>
        </Rules>
      </RulePackage>
      ```

2. 다음의 PowerShell cmdlet을 한 번에 하나씩 실행하여 규칙 패키지를 업로드하세요.

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

이 시점에서 EDM 기반 분류를 설정합니다. 다음 단계는 중요 한 데이터를 해시한 다음 인덱싱하는 해시를 업로드하는 것입니다.

PatientRecords 스키마가 검색 가능한 5개의 필드를 정의한 이전 절차에서 *PatientID*, *MRN*, *SSN*, *Phone*, 및 *DOB* 를 불러오십시오. 예제 규칙 패키지에는 이러한 필드가 포함되어 있으며 검색 가능한 필드 당 하나의 *ExactMatch* 항목과 함께 데이터베이스 스키마 파일(**edm.xml**)을 참조합니다. 다음의 ExactMatch 항목을 고려하세요.

```xml
<ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
      <Pattern confidenceLevel="65">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
        <Any minMatches ="3" maxMatches ="100">
          <match matches="PatientID" />
          <match matches="MRN"/>
          <match matches="FirstName"/>
          <match matches="LastName"/>
          <match matches="Phone"/>
          <match matches="DOB"/>
        </Any>
      </Pattern>
    </ExactMatch>
```

이 예에서는 다음 사항에 유의하세요.

- 데이터 저장소 이름은 이전에 생성한 .csv 파일을 참조합니다(**데이터 저장소 = "PatientRecords"**).

- idmatch 값은 데이터베이스 스키마 파일(**idMatch matches = "SSN"**)에 나열된 검색 가능한 필드를 참조합니다.

- 분류 값이 기존 또는 사용자 지정 중요한 정보 유형(**분류 = "미국 주민 등록 번호 (SSN)"**)을 참조합니다. (이 경우 미국 주민 등록 번호의 기존의 중요한 정보 유형을 사용합니다.)

> [!NOTE]
> EDMSchema를 추가 사항으로 업데이트하는 데 10~60분이 소요될 수 있습니다. 추가 사항을 사용하는 단계를 실행하기 전에 업데이트를 완료해야 합니다.

EDM 중요한 정보 유형으로 규칙 패키지를 가져와 중요한 데이터 테이블을 가져온 후 규정 준수 센터의 EDM 마법사에서 **테스트** 함수를 사용하여 새로 만든 유형을 테스트할 수 있습니다. 이 기능의 사용 지침은 [정확한 데이터 일치 스키마 및 중요한 정보 유형 마법사 사용](sit-edm-wizard.md)을 참조하세요.

#### <a name="editing-the-schema-for-edm-based-classification"></a>EDM 기반 분류에 대한 스키마 편집

EDM 기반 분류에 사용되는 필드를 변경하는 것과 같이 **edm.xml** 파일을 변경하려면 다음 단계를 수행하세요.

> [!TIP]
> **구성 가능한 일치** 의 장점을 얻기 위해 EDM 스키마 및 데이터 파일을 변경할 수 있습니다. 구성된 경우, EDM은 항목을 평가할 때 대소문자 차이 및 일부 구분 기호를 무시합니다. 이렇게 하면 XML 스키마와 중요한 데이터 파일을 더 쉽게 정의할 수 있습니다. 자세한 내용은 [구성 가능한 일치를 사용하도록 정확한 데이터 일치 스키마 수정](sit-modify-edm-schema-configurable-match.md)을 참조하세요.

1. **edm.xml** 파일을 편집하십시오(이 문서의 [스키마 정의](#define-the-schema-for-your-database-of-sensitive-information) 섹션에서 논의한 파일입니다).

2. [보안 및 준수 센터 PowerShell](/powershell/exchange/connect-to-scc-powershell)의 연결 절차를 사용하여 보안 및 준수 센터에 연결

3. 데이터베이스 스키마를 업데이트하려면 다음과 같은 cmdlet을 한 번에 하나씩 실행하십시오:

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      다음과 같이 확인하라는 메시지가 표시됩니다.

      > 확인
      >
      > 이 작업을 수행하시겠습니까?
      >
      > 'patientrecords' 데이터 저장소의 새로운 EDM 스키마를 업데이트합니다.
      >
      > \[Y\] 예 \[A\] 모두 예 \[N\] 아니요 \[L\] 모두 아니요 \[?\] 도움말(기본값: "Y"):

      > [!TIP]
      > 확인하지 않고 변경 사항을 적용하려면, 3단계에서 Set-DlpEdmSchema -FileData $edmSchemaXml 대신 이 cmdlet을 사용하십시오.

      > [!NOTE]
      > EDMSchema를 추가 사항으로 업데이트하는 데 10~60분이 소요될 수 있습니다. 추가 사항을 사용하는 단계를 실행하기 전에 업데이트를 완료해야 합니다.

#### <a name="removing-the-schema-for-edm-based-classification"></a>EDM 기반 분류에 대한 스키마 제거

(필요한 경우) EDM 기반 분류에 사용 중인 스키마를 제거하려면 다음 단계를 따르십시오:

1. [보안 및 준수 센터 PowerShell](/powershell/exchange/connect-to-scc-powershell)의 연결 절차를 사용하여 보안 및 준수 센터에 연결

2. 다음의 PowerShell cmdlet을 실행하여 "patientrecords"의 데이터 저장소 이름을 제거하려는 저장소 이름으로 대체하세요.

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      다음을 확인하라는 메시지가 표시됩니다.

      > 확인
      >
      > 이 작업을 수행하시겠습니까?
      >
      > 'patientrecords' 데이터 저장소의 EDM 스키마를 제거합니다.
      >
      > \[Y\] 예 \[A\] 모두 예 \[N\] 아니요 \[L\] 모두 아니요 \[?\] 도움말(기본값: "Y"):

      > [!TIP]
      >  확인하지 않고 변경 사항을 적용하려면, 2단계에서 Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false 대신 이 cmdlet을 사용하십시오.

### <a name="part-2-hash-and-upload-the-sensitive-data"></a>2부: 중요한 데이터를 해시하고 업로드

이 단계에서는 사용자 지정 보안 그룹 및 사용자 계정을 설정하고 EDM 업로드 에이전트 도구를 설정합니다. 그런 다음 이 도구를 사용하여 중요한 데이터를 해시하고 해시한 데이터를 업로드합니다.

해시 및 업로드는 한 대의 컴퓨터를 사용하여 수행하거나 보안 강화를 위해 업로드 단계에서 해싱 단계를 분리할 수 있습니다.

한 대의 컴퓨터에서 해시하고 업로드하려면 Microsoft 365 테넌트에 직접 연결할 수 있는 컴퓨터에서 수행해야 합니다. 이렇게하려면 해싱을 위해 일반 텍스트 중요 데이터 파일이 해당 컴퓨터에 있어야합니다.

일반 텍스트 중요 데이터 파일을 노출하지 않으려면 안전한 위치에 있는 컴퓨터에서 해당 파일에서 해시한 다음 업로드를 위해 Microsoft 365 테넌트에 직접 연결할 수 있는 컴퓨터에 해시 파일과 솔트 파일을 복사할 수 있습니다. 이 시나리오의 경우 두 대의 컴퓨터 모두 EDMUploadAgent가 필요합니다.

> [!IMPORTANT]
> 정확한 데이터 일치 스키마 및 중요한 정보 유형 마법사를 사용하여 스키마 및 패턴 파일을 만든 경우 이 절차에 대한 스키마를 ***다운로드해야*** 합니다.

> [!NOTE]
> 조직에서 테넌트 [](customer-key-overview.md)Microsoft 365 사용자에 대한 고객 키를 설정한 경우 정확한 데이터 일치는 암호화 기능을 자동으로 사용합니다. 상업용 클라우드의 E5 라이선스 테넌트에서만 사용할 수 있습니다.

#### <a name="prerequisites"></a>필수 구성 요소

- **EDM\_DataUploaders** 보안 그룹에 추가될 Microsoft 365용 회사 또는 학교 계정
- EDMUploadAgent 실행을 위한 .NET 버전 4.6.2가있는 Windows 10 또는 Windows Server 2016 시스템
- 다음에 대한 업로드 컴퓨터의 디렉토리 :
  - EDMUploadAgent
  - 예제에 설명된 .csv 또는 .tsv 형식의PatientRecords.csv파일 
  - 출력 해시 및 솔트 파일
  - **edm.xml** 파일의 데이터 저장소 이름(이 예에서는 `PatientRecords`)
- [정확한 데이터 일치 스키마 및 중요한 정보 유형 마법사](sit-edm-wizard.md)를 사용한 경우 ****다운로드해야만*** 합니다.

#### <a name="set-up-the-security-group-and-user-account"></a>보안 그룹 및 사용자 계정 설정

1. 전역 관리자로서 [구독에 대한 적절한 링크](#portal-links-for-your-subscription)를 사용하여 관리 센터로 이동하고 **EDM\_ DataUploaders** 라는 [보안 그룹을 만듭니다](/office365/admin/email/create-edit-or-delete-a-security-group).

2. 한 명 이상의 사용자를 **EDM\_DataUploaders** 보안 그룹에 추가합니다. (이러한 사용자가 중요한 정보 데이터베이스를 관리합니다.)

#### <a name="hash-and-upload-from-one-computer"></a>한 대의 컴퓨터에서 해시 및 업로드

이 컴퓨터는 Microsoft 365 테넌트에 직접 액세스할 수 있어야 합니다.

> [!NOTE]
>
> 이 절차를 시작하기 전에 본인이 **EDM\_DataUploaders** 보안 그룹의 구성원인지 확인하세요.
>
> 원하는 경우 업로드하기 전에 .csv .tsv 파일에 대해 유효성 검사를 실행할 수 있습니다.
>
> `EdmUploadAgent.exe /ValidateData /DataFile [data file] /Schema [schema file]`
>
> 모든 EdmUploadAgent.exe >에서 지원되는 매개 변수에 대한 자세한 내용은 다음을 실행합니다
>
> `EdmUploadAgent.exe /?`

#### <a name="links-to-edm-upload-agent-by-subscription-type"></a>구독 유형별 EDM 업로드 에이전트에 대한 링크

- [상업용 + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - 대부분의 상업용 고객이 사용
- [GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - 특히 높은 보안 정부 클라우드 구독자용
- [DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - 특히 미국 국방부 클라우드 고객용

1. EDMUploadAgent에 대한 작업 디렉터리를 만듭니다. 예를 들어, **C:\EDM\Data**. 여기에 **PatientRecords.csv** 파일을 배치하세요.

2. 구독에 적합한 [EDM 업로드 에이전트](#links-to-edm-upload-agent-by-subscription-type)를 1단계에서 만든 디렉토리에 다운로드하여 설치합니다.

   > [!NOTE]
   > 위 링크의 EDMUploadAgent는 해시된 데이터에 솔트 값을 자동으로 추가하도록 업데이트되었습니다. 또는 자신의 솔트 값을 입력할 수 있습니다. 이 버전을 사용한 후에는 이전 버전의 EDMUploadAgent를 사용할 수 없습니다.
   >
   > EDMUploadAgent를 사용하여 하루에 두 번만 지정된 데이터 저장소에 데이터를 업로드할 수 있습니다.

   > [!TIP]
   > 지원되는 명령 매개 변수에 대한 목록을 얻으려면 에이전트(인수 없음)를 실행하세요. 예를 들면 'EdmUploadAgent.exe'가 있습니다.

3. EDM 업로드 에이전트에 권한을 부여하고 명령 프롬프트 창을 열고 (관리자 권한으로) **C:\EDM\Data** 디렉토리로 전환한 후 다음 명령을 실행합니다.

   `EdmUploadAgent.exe /Authorize`

4. EDM_DataUploaders 보안 그룹에 추가된 Microsoft 365용 회사 또는 학교 계정으로 로그인합니다. 테넌트 정보는 연결을 위해 사용자 계정에서 추출됩니다.

   선택 사항: 정확한 데이터 일치 스키마 및 중요한 정보 유형 마법사를 사용하여 스키마 및 패턴 파일을 생성한 경우 명령 프롬프트 창에서 다음 명령을 실행합니다.

   ```dos
   EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>
   ```

5. 중요한 데이터를 해시하고 업로드하려면 명령 프롬프트 창에서 다음 명령을 실행하세요.

   ```dos
   EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file] /ColumnSeparator ["{Tab}"|"|"] /AllowedBadLinesPercentage [value]
   ```

   예: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml /AllowedBadLinesPercentage 5**

   중요한 데이터 파일의 기본 형식은 콤보로 구분된 값입니다. /ColumnSeparator 매개 변수를 사용하여 "{Tab}" 옵션을 지정하여 탭으로 구분된 파일을 지정하거나 "|" 옵션을 지정하여 파이프로 구분된 파일을 지정할 수 있습니다.
   중요한 정보 테이블에 형식이 잘못 지정되어 있지만 잘못된 행을 아우르는 동안 나머지 데이터를 가져오고자 하는 경우 명령에서 /AllowedBadLinesPercentage 매개 변수를 사용할 수 있습니다. 위의 예제에서는 5% 임계값을 지정합니다. 즉, 행의 최대 5%가 유효하지 않은 경우에도 도구가 중요한 정보 테이블을 해시하고 업로드합니다. 이 설정의 기본값은 1%입니다. 
   이 명령은 보안을 강화하기 위해 임의로 생성된 솔트 값을 해시에 자동으로 추가합니다. 선택에 따라, 고유한 솔트 값을 사용하려면 **/Salt <saltvalue>** 를 명령에 추가하세요. 이 값은 길이가 64자여야 하며 a-z 문자와 0-9만 포함할 수 있습니다.

6. 다음 명령을 실행하여 업로드 상태를 확인하세요.

   ```dos
   EdmUploadAgent.exe /GetSession /DataStoreName \<DataStoreName\>
   ```

   예: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**

   상태가 **ProcessingInProgress** 인지 확인합니다. 상태가 **완료** 로 변경될 때까지 몇 분마다 다시 확인하세요. 상태가 완료되면 EDM 데이터를 사용할 수 있습니다.

#### <a name="separate-hash-and-upload"></a>별도의 해시 및 업로드

안전한 환경의 컴퓨터에서 해시를 수행합니다.

선택 사항: 정확한 데이터 일치 스키마 및 중요한 정보 유형 마법사를 사용하여 스키마 및 패턴 파일을 생성한 경우 명령 프롬프트 창에서 다음 명령을 실행합니다.

```dos
EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>
````

1. 명령 프롬프트 창에서 다음 명령을 실행합니다.

   ```dos
   EdmUploadAgent.exe /CreateHash /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file] /AllowedBadLinesPercentage [value]
   ```

   예를 들면 :

   ```dos
   EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml /AllowedBadLinesPercentage 5
   ```

   **/Salt <saltvalue>** 옵션을 지정하지 않은 경우 해시 파일과 이러한 확장자를 가진 솔트 파일이 출력됩니다.

   - .EdmHash
   - .EdmSalt

2. 테넌트에 중요한 항목.csv .tsv 파일(PatientRecords)을 업로드하는 데 사용할 컴퓨터에 안전한 .csv 파일을 복사합니다.

   해시된 데이터를 업로드하려면 Windows 명령 프롬프트에서 다음 명령을 실행합니다.

   ```dos
   EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>
   ```

   예를 들어,

   ```dos
   EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**
   ```

   중요한 데이터가 업로드 되었는지 확인하려면 명령 프롬프트 창에서 다음 명령을 실행합니다.

   ```dos
   EdmUploadAgent.exe /GetDataStore
   ```

   데이터 저장소 목록 및 마지막 업데이트 날짜를 볼 수 있습니다.

   특정 저장소에 대한 모든 데이터 업로드를 표시하려면 Windows 명령 프롬프트에서 다음 명령을 실행 합니다.

   ```dos
   EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>
   ```

   계속하여 [중요한 정보 데이터베이스 새로 고침](#refreshing-your-sensitive-information-database)의 프로세스 및 일정을 설정합니다.

이제 Microsoft 클라우드 서비스로 EDM 기반 분류를 사용할 준비가 되었습니다. 예를 들어 [EDM 기반 분류를 사용하여 DLP 정책을 설정](#to-create-a-dlp-policy-with-edm)할 수 있습니다.

#### <a name="refreshing-your-sensitive-information-database"></a>중요한 정보 데이터베이스 새로 고침

중요한 정보 데이터베이스를 매일 새로 고칠 수 있으며, EDM 업로드 도구를 사용하여 중요한 데이터를 다시 색인화한 다음 색인화된 데이터를 다시 업로드할 수 있습니다.

1. 중요한 정보 데이터베이스를 새로 고치는 빈도(매일 또는 매주)와 프로세스를 판별합니다.

2. 중요한 데이터를 앱으로 다시 내보내고(예: Microsoft Excel) 파일을 .csv .tsv 형식으로 저장합니다. [중요한 데이터 해시 및 업로드](#part-2-hash-and-upload-the-sensitive-data)에 설명된 단계를 따를 때 사용한 것과 동일한 파일 이름과 위치를 유지합니다.

      > [!NOTE]
      > .csv 또는 .tsv 파일의 구조(필드 이름)가 변경되지 않은 경우 데이터를 새로 고칠 때 데이터베이스 체계 파일을 변경할 필요가 없습니다. 하지만 변경해야 하는 경우 데이터베이스 스키마와 규칙 패키지를 적절하게 편집해야 합니다.

3. [작업 스케줄러](/windows/desktop/TaskSchd/task-scheduler-start-page)를 사용하여 [중요한 데이터 해시 및 업로드](#part-2-hash-and-upload-the-sensitive-data) 절차의 2단계와 3단계를 자동화합니다. 다음과 같은 여러 방법을 사용하여 작업을 예약할 수 있습니다.

   |메서드|수행할 작업|
   |---|---|
   |Windows PowerShell|[ScheduledTasks](/powershell/module/scheduledtasks/) 문서와 이 문서에 있는 [예제 Windows PowerShell 스크립트](#example-powershell-script-for-task-scheduler)를 참조하세요.|
   |작업 스케줄러 API|[작업 스케줄러](/windows/desktop/TaskSchd/using-the-task-scheduler) 문서를 참조하세요.|
   |Windows 사용자 인터페이스|Windows에서 **시작** 을 클릭하고 작업 스케줄러를 입력합니다. 그런 다음 결과 목록에서 **작업 스케줄러** 를 마우스 오른쪽 단추로 클릭하고 **관리자로 실행** 을 선택합니다.|

#### <a name="example-powershell-script-for-task-scheduler"></a>작업 스케줄러의 예제 Windows PowerShell 스크립트

이 섹션에는 데이터를 해시하고 해시 데이터를 업로드하는 작업을 예약하는 데 사용할 수 있는 예제 PowerShell 스크립트가 포함되어 있습니다.

##### <a name="to-schedule-hashing-and-upload-in-a-combined-step"></a>해시를 예약하고 결합된 단계로 업로드하려면

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$schemaext = '.xml'
\# Assuming file name is same as data store name and file is in .csv format
$dataFile = "$fileLocation\\$dataStoreName$csvext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
\# Assuming Schema file name is same as data store name
$schemaFile = "$fileLocation\\$dataStoreName$schemaext"
$uploadDataArgs = '/UploadData /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ' /HashLocation' + $hashLocation + ' /Schema ' + $schemaFile
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadDataArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```

#### <a name="to-schedule-hashing-and-upload-as-separate-steps"></a>해시를 예약하고 별도의 단계로 업로드하려면

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$edmext = '.EdmHash'
$schemaext = '.xml'
\# Assuming file name is same as data store name and file is in .csv format
$dataFile = "$fileLocation\\$dataStoreName$csvext"
$hashFile = "$fileLocation\\$dataStoreName$edmext"
\# Assuming Schema file name is same as data store name
$schemaFile = "$fileLocation\\$dataStoreName$schemaext "

\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$createHashArgs = '/CreateHash' + ' /DataFile ' + $dataFile + ' /HashLocation ' + $hashLocation + ' /Schema ' + $schemaFile
$uploadHashArgs = '/UploadHash /DataStoreName ' + $dataStoreName + ' /HashFile ' + $hashFile
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $createHashArgs -WorkingDirectory $edminstallpath
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadHashArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a>3단계: Microsoft 클라우드 서비스로 EDM 기반 분류 사용

이러한 위치는 지원 EDM 중요 정보 유형입니다.

- Exchange Online용 DLP(전자 메일)
- 비즈니스용 OneDrive(파일)
- Microsoft Teams(대화)
- SharePoint용 DLP(파일)
- Microsoft Cloud App Security DLP 정책
- 서버 쪽 자동 레이블 지정 정책 - 상업용 클라우드 고객 및 정부 클라우드 고객이 사용할 수 있습니다.
- 클라이언트 쪽 자동 레이블 지정 정책 - 정부 클라우드 고객이 사용할 수 있습니다.  

#### <a name="to-create-a-dlp-policy-with-edm"></a>EDM으로 DLP 정책 만들기

1. [구독에 적합한 링크](#portal-links-for-your-subscription)를 사용하여 보안 및 규정 준수 센터로 이동합니다.

2. **데이터 손실 방지** \>**정책** 을 선택합니다.

3. **정책 만들기** \> **사용자 지정** \> **다음** 을 선택합니다.

4. **정책 이름 지정** 탭에서 이름과 설명을 지정한 후 **다음** 을 선택합니다.

5. **위치 선택** 탭에서 **특정 위치 선택 허용** 을 선택한 후 **다음** 을 선택합니다.

6. **상태** 열에서 **Exchange 전자 메일, OneDrive 계정, Teams 채팅 및 채널 메시지** 를 선택한 후 **다음** 을 선택합니다.

7. **정책 설정** 탭에서 **고급 설정 사용** 을 선택한 후 **다음** 을 선택합니다.

8. **+ 새 규칙** 을 선택합니다.

9. **이름** 섹션에서 규칙의 이름과 설명을 지정합니다.

10. **조건** 섹션의 **+ 조건 추가** 목록에서 **콘텐츠가 중요한 유형을 포함** 을 선택합니다.

      ![콘텐츠에는 중요한 정보 유형이 포함되어 있습니다.](../media/edm-dlp-newrule-conditions.png)

11. 규칙 패키지를 설정할 때 만든 중요한 정보 유형을 검색한 다음 **+ 추가** 를 선택합니다.
    그런 다음 **완료** 를 선택합니다.

12. **사용자 알림**, **사용자 재정의**, **인시던트 보고서** 등의 규칙에 관한 옵션 선택을 완료한 다음 **저장** 을 선택합니다.

13. **정책 설정** 탭에서 규칙을 검토하고 **다음** 을 선택합니다.

14. 정책을 바로 설정할지, 테스트할지, 아니면 설정 해제한 상태로 유지할지 지정합니다. 그런 후 **다음** 을 선택합니다.

15. **설정 검토** 탭에서 정책을 검토합니다. 필요한 대로 변경합니다. 준비가 되면 **만들기** 를 선택합니다.

> [!NOTE]
> 새로운 DLP 정책이 데이터 센터에 적용되는 데 1시간 정도 걸립니다.

## <a name="related-articles"></a>관련 문서

- [중요한 정보 유형 엔터티 정의](sensitive-information-type-entity-definitions.md)
- [중요한 정보 유형에 대해 자세히 알아보기](sensitive-information-type-learn-about.md)
- [데이터 손실 방지에 대해 자세한 알아보기](dlp-learn-about-dlp.md)
- [Microsoft Cloud App Security](/cloud-app-security)
- [New-DlpEdmSchema](/powershell/module/exchange/new-dlpedmschema)
- [구성 가능한 일치를 사용하도록 정확한 데이터 일치 스키마 수정](sit-modify-edm-schema-configurable-match.md)
