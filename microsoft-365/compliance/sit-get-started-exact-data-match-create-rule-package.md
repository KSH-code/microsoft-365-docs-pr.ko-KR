---
title: 정확한 데이터 일치 중요한 정보 유형/규칙 패키지 만들기
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
description: 정확한 데이터 일치 중요한 정보 유형/규칙 패키지 만들기
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b7f5ed48fa588bed7cbbd22a737873c5f54a83b4
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914907"
---
# <a name="create-exact-data-match-sensitive-information-typerule-package"></a>정확한 데이터 일치 중요한 정보 유형/규칙 패키지 만들기

준수 센터에서 EDM 및 SIT 마법사를 사용하여 정확한 [EDM(데이터](#use-the-edm-schema-and-sit-wizard) 일치) 중요한 정보 유형(SIT)을 만들거나 규칙 패키지 XML 파일을 수동으로 만들 수 [있습니다.](#create-a-rule-package-manually) 한 메서드를 사용하여 두 메서드를 결합한 다음 나중에 다른 메서드를 사용하여 해당 메서드를 편집할 수도 있습니다.

EDM 기반 SITS 또는 해당 구현에 익숙하지 않은 경우 다음을 익히세요.

- [중요한 정보 유형에 대해 알아보기](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)
- [정확한 데이터 일치 기반 중요한 정보 유형에 대해 자세히 알아보기](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
- [정확한 데이터 일치 기반 중요한 정보 유형 시작](sit-get-started-exact-data-match-based-sits-overview.md#get-started-with-exact-data-match-based-sensitive-information-types)

## <a name="use-the-edm-schema-and-sit-wizard"></a>EDM 및 SIT 마법사 사용

이 마법사를 사용하여 중요한 SIT(정보 유형) 파일을 만들어 프로세스를 간소화할 수 있습니다.

EDM 중요한 정보 유형은 하나 이상의 패턴으로 구성됩니다. 각 패턴은 문서 또는 전자 메일에서 중요한 콘텐츠를 식별하는 데 사용되는 증거(schema의 필드)의 조합을 기술합니다. 

## <a name="pre-requisites"></a>필수 구성 요소

다음 문서의 단계를 수행합니다.

1. [정확한 데이터 일치 기반의 중요한 정보 유형에 대한 원본 데이터 내보내기](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)
2. [정확한 데이터 일치 기반의 중요한 정보 유형에 대한 스마마 만들기](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types)
3. [정확한 데이터 일치 중요한 정보 유형에 대한 중요한 정보 원본 테이블 해시 및 업로드](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types)

- 마법사를 사용하여 EDM 중요한 정보 유형을 만들든, PowerShell을 통해 규칙 패키지 XML 파일을 만들든, UI를 통해 사용자 지정 중요한 정보 유형을 만들고 테스트하고 배포하려면 전역 관리자 또는 준수 관리자 권한이 있어야 합니다. 에서 [관리자 역할 Office 365.](/office365/admin/add-users/about-admin-roles)
- Primary 요소 중요한 정보 유형으로 사용할 기본 제공 SITS 중 하나를 식별합니다.
    - 기본 제공 중요한 정보 유형이 선택한 열의 데이터와 일치하지 않는 경우 사용자 지정 중요한 정보 유형을 만들어야 합니다.
    - schema의 기본 요소 열에 대해 무시된 Delimiters 옵션을 선택한 경우 만든 사용자 지정 SIT가 선택한 디지타이터와 일치하거나 없는 데이터와 일치해야 합니다. 
    - 기본 제공 SIT를 사용하는 경우 선택하려는 문자열을 정확히 검색하고 주변 문자를 포함하지 말고 중요한 정보 테이블에 저장된 문자열의 유효한 부분을 제외해야 합니다. 중요한 [정보 유형 엔터티 정의](sensitive-information-type-entity-definitions.md#sensitive-information-type-entity-definitions) 및 사용자 지정 중요한 정보 유형 [시작을 참조하세요.](create-a-custom-sensitive-information-type.md#get-started-with-custom-sensitive-information-types) 
     
### <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a>정확한 데이터 일치 스키마 및 중요한 정보 유형 패턴 마법사 사용

1. 테넌트에 대한 Microsoft 365 규정 준수 센터에서 **데이터 분류** > **일치 데이터 추출** 로 이동하세요.

2. **EDM 중요한 정보 유형** 과 **EDM 중요한 정보 유형** 을 선택하고 중요한 정보 유형 구성 마법사를 선택합니다.

3. Choose **an existing EDM schema** and choose the schema you created [in Create the schema for exact data match based sensitive information types](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types).

4. **다음** 을 선택하고 **패턴 생성** 을 선택합니다.

5. **신뢰 수준** 및 **기본 요소** 를 선택합니다.  신뢰 수준에 대한 자세한 내용은 중요한 정보 [유형에 대한 자세한 정보를 참조하세요.](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)

6.  Primary **요소의** 중요한 정보 유형을 선택하면 문서에서 기본 요소 필드의 모든 값과 비교할 텍스트를 정의할 수 있습니다. 사용 가능한 중요한 정보 유형에 대한 자세한 내용은 [중요한 정보 유형 엔티티 정의](sensitive-information-type-entity-definitions.md)를 참조하세요.

> [!IMPORTANT]
> 찾을 콘텐츠 형식과 밀접하게 일치하는 중요한 정보 유형을 선택합니다. 모든 텍스트 문자열과 일치하는 콘텐츠와 같은 불필요한 콘텐츠와 일치하는 중요한 정보 유형을 선택하거나 모든 숫자를 선택하면 시스템에 과도한 부하가 발생하여 중요한 정보가 누락될 수 있습니다. 여기에서 사용할 중요한 정보 유형을 선택하는 데 필요한 권장 사항은 이 설명서의 정확한 데이터 일치 소개 문서의 모범 사례 섹션을 참조하세요. 

7. 지원 **요소 및** 일치 옵션을 선택합니다.

7. 완료 **및** 다음 **을 선택 합니다.**

8. 원하는 **신뢰 수준 및 문자 근접성** 을 선택합니다.  이 값은 전체 EDM 중요한 정보 유형에 대한 기본값입니다.

9. EDM 중요한 **정보** 유형에 대한 추가 패턴을 만들 경우 패턴 만들기를 선택하십시오.

10. **다음** 을 선택하고 **이름** 과 **관리자 설명** 을 입력합니다.

11. 검토하고 **제출** 을 선택합니다.

### <a name="edit-or-delete-the-sensitive-information-type-pattern"></a>중요한 정보 유형 패턴 편집 또는 삭제

1. 개방형 **준수 센터**  >  **데이터 분류** 정확한 데이터가  >  **일치합니다.**

2. **EDM 중요한 정보 유형 을 선택 합니다.**

3. 편집할 EDM SIT를 선택 합니다.

4. **EDM 중요한 정보** 유형 편집 또는 플라이아웃에서 **EDM 중요한 정보** 유형 삭제를 선택하세요.

## <a name="create-a-rule-package-manually"></a>수동으로 규칙 패키지 만들기

이 절차에서는 유니코드 인코딩을 사용하여 규칙 패키지라는 XML 형식으로 파일을 만든 다음 준수 센터 PowerShell cmdlet을 사용하여 파일을 Microsoft 365 방법을 보여 주며,

> [!NOTE]
> 매핑하는 SIT가 여러 단어 증분 증거를 검색할 수 있는 경우 수동으로 만든 규칙 패키지에서 정의하는 보조 요소를 SIT에 매핑할 수 있습니다. 예를 들어 해당 증분 증거 필드가 해당 패턴을 검색할 수 있는 SIT에 매핑되지 않은 경우 콘텐츠에서 필드 중 하나에 업로드된 용어와 별도로 비교하여 찾을 것이기 때문에 이름이 보조 요소로 일치하지 `John Smith` `John` `Smith` `John Smith` 않습니다.

> [!NOTE]
> 테넌트의 규칙 패키지는 10개까지만 Microsoft 365 있습니다. 규칙 패키지에는 임의 개수의 중요한 정보 유형이 포함될 수 있습니다. 이 방법을 사용하여 새 중요한 정보 유형을 정의할 때마다 새 규칙 패키지를 만들지 않고 기존 규칙 패키지를 내보내고 중요한 정보 유형을 XML에 추가한 후 다시 업로드할 수 있습니다. 


1. 다음 예제와 같이 in XML 형식(유니코드 인코딩 사용)에 규칙 패키지를 생성하세요. (여기에 있는 예제를 복사, 수정 및 사용할 수 있습니다.)

규칙 패키지를 설정할 때 .csv, .tsv 또는 파이프(|) 구분된 중요한 정보 원본 테이블 파일 및edm.xml참조해야 합니다.  (여기에 있는 예제를 복사, 수정 및 사용할 수 있습니다.) 이 샘플 xml에서 EDM 중요한 유형을 만들 수 있도록 다음 필드를 사용자 지정해야 합니다.

- **RulePack ID & ExactMatch ID**:[New-GUID](/powershell/module/microsoft.powershell.utility/new-guid)를 사용하여 GUID를 생성합니다.

- **Datastore**: 이 필드는 사용할 EDM 조회 데이터 저장소를 지정합니다. 구성된 EDM Schema의 데이터 원본 이름을 입력합니다.

- **idMatch**: 이 필드는 EDM의 기본 요소를 가리킵니다.
- **일치:** 정확한 Lookup에 사용할 필드를 지정합니다. 데이터 저장소의 EDM 스키마에서 검색 가능한 필드 이름을 입력합니다.
- **분류:** 이 필드는 EDM lookup을 트리거하는 중요한 정보 유형 일치를 지정합니다. 기존 기본 제공 또는 사용자 지정 중요한 정보 유형의 이름 또는 GUID를 사용할 수 있습니다. 
        
> [!NOTE]
> 제공된 SIT와 일치하는 문자열은 해시된 후 중요한 정보 원본 테이블의 모든 항목과 비교됩니다. 분류 요소에 대해 사용자 지정 SIT를 선택하는 경우 성능 문제를 방지하기 위해 콘텐츠의 많은 비율과 일치하는 요소를 사용하지 않도록 합니다. 예를 들어 "any number" 또는 "any5-letter word"가 일치하는 단어를 예로 들 수 있습니다. 지원 키워드를 추가하거나 사용자 지정 분류 SIT 정의에 서식을 포함하여 구분할 수 있습니다.

- **일치:** 이 필드는 idMatch의 근접성에서 발견된 추가 증거를 포인트로 합니다.
- **일치:** DataStore에 대한 EDM Schema에서 필드 이름을 입력합니다.
- **리소스 idRef:** 이 섹션에서는 여러 개의 로컬에서 중요한 유형에 대한 이름과 설명을 지정합니다.
    - ExactMatch ID에 대한 GUID를 제공해야 합니다.
    - **이름**  &  **description**: 필요에 따라 사용자 지정합니다.

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

> [!NOTE]
> 규칙 패키지 파일의 구문은 다른 중요한 정보 유형과 동일합니다. 규칙 패키지 파일의 구문과 추가 구성 옵션에 대한 자세한 내용과 PowerShell을 사용하여 중요한 정보 유형을 수정 및 삭제하는 방법에 대한 지침은 [PowerShell을](create-a-custom-sensitive-information-type-in-scc-powershell.md#create-a-custom-sensitive-information-type-using-powershell)사용하여 사용자 지정 중요한 정보 유형 만들기 를 참조하세요.

## <a name="next-step"></a>다음 단계

-  [중요한 정보 유형과 일치하는 정확한 데이터 테스트](sit-get-started-exact-data-match-test.md#test-an-exact-data-match-sensitive-information-type)