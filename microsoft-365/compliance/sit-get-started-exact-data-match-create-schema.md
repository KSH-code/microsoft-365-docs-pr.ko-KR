---
title: 정확한 데이터 일치 기반의 중요한 정보 유형에 대한 스마마 만들기
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 정확한 데이터 일치 기반의 중요한 정보 유형에 대한 스마마 만들기
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d01aee9a89e363f8c9140b2a0e59643e69be94bf
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914910"
---
# <a name="create-the-schema-for-exact-data-match-based-sensitive-information-types"></a>정확한 데이터 일치 기반의 중요한 정보 유형에 대한 스마마 만들기

정확한 데이터 일치 및 중요한 정보 유형 패턴 사용 마법사를 사용하여 또는 수동으로 를 사용하여 [Schema](#use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard) 및 EDM SIT를 만들 수 [있습니다.](#create-exact-data-match-schema-manually-and-upload) 한 메서드를 사용하여 두 메서드를 결합한 다음 나중에 다른 메서드를 사용하여 해당 메서드를 편집할 수도 있습니다.

EDM 기반 SITS 또는 해당 구현에 익숙하지 않은 경우 다음을 익히세요.

- [중요한 정보 유형에 대해 알아보기](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)
- [정확한 데이터 일치 기반 중요한 정보 유형에 대해 자세히 알아보기](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
- [정확한 데이터 일치 기반 중요한 정보 유형 시작](sit-get-started-exact-data-match-based-sits-overview.md#get-started-with-exact-data-match-based-sensitive-information-types)

하나의 EDM schema는 동일한 중요한 데이터 테이블을 사용하는 여러 중요한 정보 유형에서 사용할 수 있습니다. 테넌트에서 최대 10개까지 EDM Microsoft 365 수 있습니다.

## <a name="working-with-specific-types-of-data"></a>특정 데이터 형식 작업

성능상의 이유로 불필요한 일치 횟수를 최소화하는 패턴을 사용하는 것이 중요합니다. 예를 들어 정규식에 따라 중요한 정보 유형을 사용할 수 있습니다. 

`\b\w*\b`

이는 문서나 전자 메일의 모든 개별 단어나 번호와 일치합니다. 이로 인해 일치하는 일치로 서비스가 오버로드되고 실제 일치 검색이 누락됩니다. 보다 정확한 패턴을 사용하여 이러한 상황을 방지할 수 있습니다. 다음은 몇 가지 일반적인 유형의 데이터에 대한 올바른 구성을 식별하기 위한 몇 가지 권장 사항입니다.

**전자 메일 주소:** 전자 메일 주소는 쉽게 식별할 수 있지만 콘텐츠에서 매우 일반적이기 때문에 기본 필드로 사용되는 경우 시스템에 상당한 부하가 발생할 수 있습니다. 2차 증거로만 사용 기본 증거로 사용되어야 하는 경우 논리를 사용하여 전자 메일의 필드로 사용을 제외하고 회사의 전자 메일 주소가 있는 정보를 제외하여 일치해야 하는 불필요한 문자열의 수를 줄이는 사용자 지정 중요한 정보 유형을 정의해 보아야 `From` `To` 합니다.

**전화** 번호: 전화 번호는 국가 prefixes, area codes, separators를 포함하거나 제외하는 다양한 형식으로 입력할 수 있습니다. 최소한의 부하를 유지하면서 거짓 부정을 줄이면 보조 요소로만 사용합니다. 괄호 및 대시와 같이 가능한 모든 구분 요소를 제외하고 중요한 데이터 테이블에 항상 전화 번호에 표시될 부분만 포함합니다.

사용자 **이름:** 일반 단어와 구분하기 어렵기 때문에 정규식을 기반으로 하는 중요한 정보 유형을 이 EDM 유형의 분류 요소로 사용하는 경우 사람의 이름을 기본 요소로 사용하지 않습니다. 

처리해야 할 많은 일치를 생성할 수 있는 프로젝트 코드 이름과 같이 특정 패턴으로 식별하기 어려운 기본 요소를 사용하려면 EDM 형식의 분류 요소로 사용하는 중요한 정보 유형에 키워드를 포함해야 합니다. 예를 들어 정규어일 수 있는 프로젝트 코드 이름을 사용하는 경우 EDM 형식의 분류 요소로 사용되는 중요한 형식의 프로젝트 이름 정규식 기반 패턴과 근접한 추가 증거로 단어를 사용할 수 `project` 있습니다. 또는 일반 사전을 기반으로 하는 중요한 유형을 EDM SIT의 분류 요소로 사용할 수 있습니다.

숫자 문자열을 일치하려고 할 때 자릿수 또는 시작 숫자(알려진 경우)처럼 허용되는 숫자 범위를 지정합니다. 비교적 유연한 숫자 범위를 일치해야 하는 경우 기본 SIT에서 키워드를 사용하여 일치 횟수를 줄일 수 있습니다. 예를 들어 7-11자리 숫자로 구성된 계정 번호를 일치하려는 경우 , 를 필요한 추가 증거로 `account` `customer` `acct.` SIT에 추가합니다. 이렇게 하면 EDM에서 처리될 일치의 제한을 초과할 수 있는 불필요하게 일치할 가능성이 줄어듭됩니다.

기본 요소로 사용해야 하는 필드가 많은 일치를 유발할 수 있는 간단한 패턴을 따르고 키워드의 존재를 중요한 정보 유형에 추가 증거로 추가할 수 없는 경우 해당 패턴의 최소 발생 횟수를 요구할 수도 있습니다. 예를 들어 다음 방법으로 정의된 사용자 지정 중요한 정보 유형을 사용하여 EDM과 일치할 가능성이 있는 5자리 숫자를 둘러싼 29자리 이상의 다른 5자리 숫자를 검색할 수 있습니다.

```xml
 <Entity id="98703510-18b3-43d4-961f-15317594beb7"
                  patternsProximity="300"
                  recommendedConfidence="85"
                  relaxProximity="false">
                  <Pattern confidenceLevel="85"
                              proximity="300">
                              <IdMatch idRef="MRN"/>
                              <Match idRef="30 AccountNrs"
                                    minCount="30"
                                    proximity="3000"
                                    uniqueResults="true"/>
                  </Pattern>
      </Entity>
      <Regex id="30 AccountNrs">\d{5}</Regex>
```
     

경우에 따라 특정 계정을 식별하거나 기록상의 이유로 표준화된 패턴을 따르지 않는 ID 번호를 기록해야 할 수 있습니다. 예를 들어 같은 조직 내의 여러 문자와 숫자로 `Medical Record Numbers` 구성될 수 있습니다. 처음에는 패턴을 식별하기 어려우지만 좀 더 자세히 검사하면 잘못된 일치를 과도하게 발생하지 않고 모든 유효한 값을 설명하는 패턴의 범위를 좁힐 수 있습니다. 예를 들어 "모든 MRNS는 7자 이상 길이로, 숫자 자릿수가 두 개 이상 있으며 문자가 있는 경우 1부터 시작"으로 검색될 수 있습니다. 이러한 조건에 따라 정규식을 만들면 원하는 모든 값을 캡처하면서 불필요한 일치를 최소화할 수 있으며, 추가 분석을 통해 서로 다른 형식을 설명하는 별도의 패턴을 정의하여 정밀도를 높이는 데 사용할 수 있습니다.

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a>정확한 데이터 일치 스키마 및 중요한 정보 유형 마법사 사용

이 마법사를 사용하여 스마마 파일 만들기 프로세스를 단순화할 수 있습니다.

## <a name="pre-requisites"></a>필수 구성 요소

- 정확한 데이터 일치 기반 중요한 정보 유형에 대한 원본 데이터 [내보내기의 단계를 수행합니다.](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a>정확한 데이터 일치 스키마 및 중요한 정보 유형 패턴 마법사 사용

1. 테넌트의 Microsoft 365 준수 센터에서 데이터 분류 EDM 스마크와 일치하는 정확한  >    >  **데이터로 이동하십시오.**

2. **EDM 스키마 생성** 을 선택하여 스키마 마법사 구성 플라이아웃을 선택합니다.

![EDM schema creation wizard configuration flyout.](../media/edm-schema-wizard-1.png)

3. 적절한 **이름** 과 **설명** 을 입력합니다.

4. 전체 **schema에** 대해 해당 동작을 사용하려는 경우 모든 Schema 필드에 대해 문장 부호 및 문장 부호 무시를 선택 합니다. 대소문자나 개별 정보를 무시하기 위해 EDM을 구성하는 방법을 알아보는 자세한 내용은 이 기능에 대한 자세한 내용은 [caseInsensitive 및 ignoredDelimiters](#using-the-caseinsensitive-and-ignoreddelimiters-fields) 필드 사용을 참조합니다. 

5. **Schema 필드 #1** 에 대해 원하는 값을 입력하고 필요에 따라 필드를 추가합니다. 각 schema 필드는 중요한 정보 원본 파일의 열 헤더와 동일해야 합니다.

6. 원하는 경우 다음에 대한 필드당 값을 설정해야 합니다.
    1. **필드를 검색할 수 있습니다.**
    1. **필드의 대소문자 미지정**
    1. **이 필드에 대해 무시할 delimiters 및 문장 부호 선택**
    1. **이 필드에 대한 사용자 지정 디지타이터 및 문장 부호 입력**

> [!IMPORTANT]
> 하나 이상의 스키마 필드를 검색 가능으로 지정해야 합니다.

6. **저장** 을 선택합니다. 이제 스마마가 나열되어 사용할 수 있습니다.

> [!IMPORTANT]
> 스키마를 제거하려면 해당 스키마가 EDM에 중요한 정보 유형과 이미 연결되어 있는 경우 먼저 EDM에 중요한 정보 유형을 삭제한 후 스키마를 삭제할 수 있습니다. 데이터 저장소가 연결된 Schema를 삭제하면 24시간 이내에 데이터 저장소도 삭제됩니다. 

## <a name="export-of-the-edm-schema-file-in-xml-format"></a>XML 형식으로 EDM schema 파일 내보내기

EDM schema 마법사에서 EDM Schema를 만든 경우 XML 형식으로 EDM schema 파일을 내보내야 합니다. 해시에서 이 정보가 필요하며 정확한 데이터 일치 중요한 정보 유형 단계에 대한 중요한 정보 원본 [테이블을 업로드해야](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types) 합니다.

1. 커넥트 보안 & 준수 센터 PowerShell에 대한 커넥트 절차를 사용하여 보안 & [PowerShell에 보호합니다.](/powershell/exchange/connect-to-scc-powershell)

2. EDM schema 파일을 내보내기 위해 다음 cmdlet을 사용 합니다.

```powershell
$Schema = Get-DlpEdmSchema -Identity "[your EDM Schema name]"
Set-Content -Path ".\Schemafile.xml" -Value $Schema.EdmSchemaXML
```
3. 나중에 사용하기 위해 이 파일을 저장합니다.

## <a name="create-exact-data-match-schema-manually-and-upload"></a>수동으로 정확한 데이터 일치 Schema 만들기 및 업로드

Schema 파일에서 구문을 사용하여 중요한 정보 원본 테이블의 각 열에 대한 항목을 구성합니다. 

```xml
<Field name="FieldName" searchable="true/false" caseInsensitive="true/false" ignoredDelimiters="delimiter characters" />
```
### <a name="using-the-caseinsensitive-and-ignoreddelimiters-fields"></a>caseInsensitive 및 ignoredDelimiters 필드 사용

다음 schema XML 샘플에서는 *caseInsensitive* 및 *ignoredDelimiters* 필드를 활용합니다.

*caseInsensitive* 필드를 schema 정의의 값으로 설정하면 EDM에서 대소문자 차이에 따라 항목을 `true` 제외하지 않습니다. 예를 들어 EDM은 **필드에 대해 FOO-1234** 및 **fOo-1234** 값을 동일하게 `PatientID` 볼 수 있습니다.

지원되는 문자가 *있는 ignoredDelimiters* 필드를 포함하면 EDM에서 해당 문자를 무시합니다. 따라서 EDM은 **필드에 대해 FOO-1234** 및 **FOO#1234** 값을 동일하게 `PatienID` 볼 수 있습니다. 

이 예에서 `caseInsensitive` 및 `ignoredDelimiters` 모두 사용되는 경우, EDM은 **FOO-1234** 및 **fOo#1234** 가 동일하다고 보고, 환자 기록을 중요한 정보 유형으로 분류합니다.  

이러한 매개 변수는 모두 필드에 따라 사용됩니다.

> [!IMPORTANT]
> 공백을  무시하도록 구성하면 기본 필드 열과 여러 단어 문자열을 검색할 수 있는 중요한 정보 유형이 정의되어 있는 경우 이 설정이 효과적입니다. 그렇지 않으면 분석되는 콘텐츠의 각 개별 단어에 대해 비교가 이행됩니다.

*ignoredDelimiters* 플래그는 영문이 아닌 모든 문자를 지원합니다. 다음은 몇 가지 예입니다.

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

> [!IMPORTANT]
> EDM 중요한 정보 유형을 정의할 때 *ignoreDelimiters는* EDM 패턴의 기본 요소와 연결된 분류 중요한 정보 유형이 항목의 콘텐츠를 식별하는 방법에 영향을 주지 않습니다. 따라서 검색 가능한 필드에 *대해 ignoreDelimiters를* 구성하는 경우 해당 필드를 기반으로 기본 요소에 사용되는 중요한 정보 유형이 해당 문자가 있는 문자열과 없는 문자열을 모두 선택해야 합니다.

> [!IMPORTANT]
> 중요한 정보 원본 테이블의 열 수와 해당 schema의 필드 수가 일치해야 합니다. 순서는 중요하지 않습니다.

1. XML 형식(아래 예제와 유사)으로 Schema를 정의합니다. 이 schema 파일의 이름을 **edm.xml** 으로 지정하고, 중요한 정보 원본 테이블의 각 열에 대해 구문을 사용하는 줄이 있도록 구성합니다.

      `\<Field name="" searchable=""/\>`.

      - *필드 이름* 값에 열 이름을 사용합니다.
      - 검색할 *수 있는 필드에 searchable="true"를* 사용하고 기본 필드는 최대 5개까지 사용할 수 있습니다. 하나 이상의 필드를 검색할 수 있어야 합니다.

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

XML 형식으로 EDM 스마 파일을 만든 후 클라우드 서비스에 업로드해야 합니다. 

2. 커넥트 보안 & 준수 센터 PowerShell에 대한 커넥트 절차를 사용하여 보안 & [PowerShell에 보호합니다.](/powershell/exchange/connect-to-scc-powershell)

3. 데이터베이스 스키마를 업로드 하려면 다음과 같은 cmdlet을 한 번에 하나씩 실행하십시오:

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
> 확인 없이 변경 내용을 적용하려는 경우 2단계에서 대신 이 cmdlet을 사용합니다. New-DlpEdmSchema -FileData $edmSchemaXml

> [!NOTE]
> EDMSchema를 추가 사항으로 업데이트하는 데 10~60분이 소요될 수 있습니다. 추가 사항을 사용하는 단계를 실행하기 전에 업데이트를 완료해야 합니다.

## <a name="next-step"></a>다음 단계

- [정확한 데이터 일치 중요한 정보 유형에 대한 중요한 정보 원본 테이블 해시 및 업로드](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types)