---
title: 구성 가능한 일치를 사용하도록 정확한 데이터 일치 스키마 수정
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 구성 가능한 일치를 사용하도록 EDM 스키마를 수정하는 방법을 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a409b8bad43b6a6ade81c96ae14f691289e11cec
ms.sourcegitcommit: be074f57e33c811bb3857043152825209bc8af07
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2021
ms.locfileid: "60336049"
---
# <a name="modify-exact-data-match-schema-to-use-configurable-match"></a>구성 가능한 일치를 사용하도록 정확한 데이터 일치 스키마 수정

EDM(정확한 데이터 일치) 기반 분류를 사용하면 중요한 정보 데이터베이스의 정확한 값을 참조하는 사용자 지정 중요한 정보 유형을 만들 수 있습니다. 정확한 문자열의 변형을 허용해야 하는 경우, *구성 가능한* 일치를 사용하여 Microsoft 365가 일부 구분 기호를 무시하도록 지시할 수 있습니다. 

> [!IMPORTANT]
> 이 절차를 사용하여 기존 EDM 스키마 및 데이터 파일을 수정합니다.

1. EDM 스키마 및 데이터 파일 업로드 목적으로 Microsoft 365에 연결하는 데 사용하는 컴퓨터에서 **EdmUploadAgent.exe** 를 제거합니다.

2. 아래 링크를 사용하여 구독에 적합한 **EdmUploadAgent.exe** 파일을 다운로드합니다.
    - [상업용 + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - 대부분의 상업용 고객이 사용
    - [GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - 특히 높은 보안 정부 클라우드 구독자용
    - [DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - 특히 미국 국방부 클라우드 고객용

3. EDM 업로드 에이전트에 권한을 부여하고 명령 프롬프트 창을 열어(관리자 권한으로) 다음 명령을 실행합니다.

   `EdmUploadAgent.exe /Authorize`

4. 기존 스키마의 현재 복사본이 없는 경우, 다음 명령을 실행하려면 기존 스키마의 복사본을 다운로드해야 합니다.

    `EdmUploadAgent.exe /SaveSchema /DataStoreName <dataStoreName> [/OutputDir [Output dir location]]`

5. 각 열이 “caseInsensitive” 및/또는 “ignoredDelimiters”를 활용하도록 스키마를 사용자 지정합니다.  “caseInsensitive”의 기본값은 “false”이며 “ignoredDelimiters”의 경우는 빈 문자열입니다. 

> [!NOTE]
> 일반 정규직 패턴을 감지하는 데 사용되는 기본 제공되는 사용자 지정 중요한정보 유형 및 기본 중요한 정보 유형은 ignoredDelimiters로 나열된 변형 입력 감지를 지원해야 합니다. 예를 들어, 기본 제공되는 SSN(미국 사회 보장 번호) 중요한 정보 유형은 SSN을 구성하는 그룹 번호 간의 대시, 공백 또는 공백 부족을 포함하는 데이터 변형을 감지할 수 있습니다. 따라서, SSN에 대한 EDM의 ignoredDelimiters에 포함되는 것과 관련된 유일한 구분 기호는 대시와 공백입니다.

다음은 중요한 데이터에서 대소문자 변형을 인식하는 데 필요한 추가 열을 만들어서 대소문자 일치를 시뮬레이션하는 샘플 스키마입니다.

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
           <Field name="PolicyNumber" searchable="true" />
           <Field name="PolicyNumberLowerCase" searchable="true" />
           <Field name="PolicyNumberUpperCase" searchable="true" />
           <Field name="PolicyNumberCapitalLetters" searchable="true" />
  </DataStore>
</EdmSchema>
```

위의 예에서 `caseInsensitive` 및 `ignoredDelimiters` 모두 추가되는 경우, 원래 `PolicyNumber`열의 변형은 더 이상 필요하지 않습니다. 

EDM이 구성 가능한 일치를 사용하도록 스키마를 업데이트하려면 `caseInsensitive` 및 `ignoredDelimiters` 플래그를 사용합니다. 형태는 다음과 같습니다.

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
         <Field name="PolicyNumber" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
  </DataStore>
</EdmSchema>
```

`ignoredDelimiters` 플래그는 영숫자가 아닌 모든 문자를 지원하며 다음은 몇 가지 예입니다.
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
- |

6. [보안 및 준수 센터 PowerShell](/powershell/exchange/connect-to-scc-powershell)의 연결 절차를 사용하여 보안 및 준수 센터에 연결

> [!NOTE]
> 조직에서 [테넌트 수준(공개 미리 보기)에서 Microsoft 365용 고객 키](customer-key-tenant-level.md#overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview)를 설정한 경우 정확한 데이터 일치는 자동으로 암호화 기능을 사용합니다. 이는 상업용 클라우드의 E5 라이선스 테넌트에게만 제공됩니다.

7. cmdlets를 한 번에 하나씩 실행하여 다음과 같이 스키마를 업데이트합니다.

`$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0`

`Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

8. 필요한 경우, 새 스키마 버전과 일치하도록 데이터 파일을 업데이트합니다.

> [!TIP]
> 선택적으로 다음을 실행하여 업로드하기 전에 csv 파일에 대해 유효성 검사를 실행할 수 있습니다.
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] [schema file]`
>
>모든 EdmUploadAgent.exe >에서 지원되는 매개 변수에 대한 자세한 내용은 다음을 실행합니다
>
> `EdmUploadAgent.exe /?`

9. 명령 프롬프트 창을 열고(관리자 권한으로) 다음 명령을 실행하여 중요한 데이터를 해시하고 업로드합니다.

    `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Salt [custom salt] /Schema [Schema file]`


## <a name="related-articles"></a>관련 문서

- [분류에 기반한 정확한 데이터 일치를 사용한 사용자 지정 중요한 정보 유형 만들기](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [중요한 정보 유형 엔터티 정의](sensitive-information-type-entity-definitions.md)
- [사용자 지정 중요한 정보 유형](./sensitive-information-type-learn-about.md)
- [데이터 손실 방지에 대해 알아보기](dlp-learn-about-dlp.md)
- [Microsoft Cloud App Security](/cloud-app-security)
- [New-DlpEdmSchema](/powershell/module/exchange/new-dlpedmschema)
