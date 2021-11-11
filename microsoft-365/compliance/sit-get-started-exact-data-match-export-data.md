---
title: 정확한 데이터 일치 기반의 중요한 정보 유형에 대한 원본 데이터 내보내기
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
description: 정확한 데이터 일치 기반 중요한 정보 유형에 대한 원본 데이터를 내보내는 방법을 배워야 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b2009687e52e4911345daed1b3c16c0942fc1a65
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914900"
---
# <a name="export-source-data-for-exact-data-match-based-sensitive-information-type"></a>정확한 데이터 일치 기반의 중요한 정보 유형에 대한 원본 데이터 내보내기


중요한 데이터 테이블은 문서의 콘텐츠를 비교하여 중요한 데이터를 식별할 값 행을 포함하는 텍스트 파일입니다. 이러한 값은 콘텐츠에서 검색하고 보호 조치를 취하려는 텍스트 양식의 개인 식별 정보, 제품 레코드 또는 기타 중요한 데이터일 수 있습니다.

지원되는 형식 중 하나에서 데이터를 내보낼 경우 EDM schema 만들기를 계속할 수 있습니다.

## <a name="defining-your-edm-sensitive-type"></a>EDM 중요 유형 정의

EDM 중요한 유형을 정의할 때 가장 중요한 결정 중 하나는 기본 필드가 될 필드입니다. 기본 필드는 검색 가능한 패턴을 따르고 EDM schema에서 검색 가능한 필드(열)로 정의해야 합니다. 보조 필드는 기본 필드와 일치하는 모든 텍스트와 비교하기 때문에 패턴을 따를 필요가 없습니다.

다음 규칙을 사용하여 기본 필드로 사용할 열을 결정하는 데 도움이 됩니다.

- 중요한 데이터 테이블에 있는 필드와 일치하는 단일 값이 있는 경우 주변에 다른 중요한 데이터가 있는 경우와 관계없이 해당 열을 EDM 형식의 기본 요소로 정의해야 합니다. 
- 중요한 데이터 테이블의 여러 필드 조합을 콘텐츠에서 검색해야 하는 경우 이러한 조합에 공통적인 열을 식별하고 다른 필드를 보조 요소로 기본 요소 및 조합으로 지정합니다.
- 기본 필드로 사용하려는 열이 텍스트 문자열과 같이 검색 가능한 패턴을 따르지 않는 경우 또는 문서 또는 전자 메일의 많은 비율로 어딘가에 표시될 감지 가능한 패턴을 따르는 경우 다른 더 나은 구조화된 열을 기본 요소로 선택해 보세요.

예를 들어 , , 및 열이 있는 경우, 이름과 성 을 검색하려는 여러 데이터 조합에 공통적으로 사용되는 열이라도 이러한 문자열은 쉽게 식별할 수 있는 패턴을 따르지 못하며 중요한 정보 유형으로 정의하기 어려울 수 `full name` `date of birth` `account number` `Social Security Number` 있습니다. 일부 이름은 대문자부터 시작하지 않을 수도 있으며, 2, 3개 이상의 단어로 구성될 수 있으며 숫자나 다른 영문자도 포함할 수 있기 때문에입니다. 생년월일을 보다 쉽게 식별할 수 있지만, 모든 전자 메일과 대부분의 문서에는 적어도 하나의 날짜가 포함되어야 하기 때문에 이 역시 좋은 후보가 되지 않습니다. 주민 등록 번호와 계정 번호는 기본 필드로 사용하기에 좋은 후보입니다.

## <a name="save-sensitive-data-in-csv-tsv-or-pipe-separated-format"></a>.tsv .csv 구분된 형식으로 중요한 데이터를 저장합니다.

1. 사용하려는 중요한 정보를 식별합니다. 데이터를 앱에 내보낼 수 Microsoft Excel 텍스트 파일에 저장합니다. 이 파일은 파일 형식(.csv), .tsv(탭으로 구분된 값) 또는 파이프 구분(|) 형식으로 저장할 수 있습니다. 데이터 값에 주소와 같은 콤보가 포함될 수 있는 경우 .tsv 형식을 지정하는 것이 좋습니다.
데이터 파일에는 최대 다음을 포함할 수 있습니다.
   - 최대 1억 개의 중요한 데이터 행
   - 데이터 원본당 최대 32개의 열(필드)
   - 검색 가능으로 표시된 최대 5개의 열(필드)

2. 첫 번째 행에 EDM 기반 분류에 사용되는 필드 이름이 .csv 또는 .tsv 파일의 중요한 데이터를 구조화합니다. 파일에 "ssn", "birthdate", "firstname", "lastname" 등의 필드 이름이 있을 수 있습니다. 열 머리글 이름에는 공백이나 밑줄이 포함될 수 없습니다. 예를 들어, 이 문서에서 사용하는 샘플 .csv 파일은 *PatientRecords.csv* 라고 하며, 해당 열에는 *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN* 등이 포함되어 있습니다.

3. 중요한 데이터 필드의 형식에 유의하세요. 특히 콘텐츠에 콤보가 포함될 수 있는 필드(예: "Seattle,WA" 값이 포함된 주소)는 구문 분석할 때 .csv 필드로 구문 분석됩니다. 이를 방지하기 위해 .tsv 형식을 사용하거나 중요한 데이터 테이블에서 값이 들어 있는 콤보를 두 번 따옴표로 둘러싸습니다. 값을 포함하는 콤보에 공백도 포함되어 있는 경우 해당 형식과 일치하는 사용자 지정 SIT를 만들어야 합니다. 예를 들어 콤보 및 공백이 있는 여러 단어 문자열을 검색하는 SIT입니다.

## <a name="next-step"></a>다음 단계

- [정확한 데이터 일치 기반의 중요한 정보 유형에 대한 스마마 만들기](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types)

## <a name="see-also"></a>참고 항목

- [정확한 데이터 일치 기반 중요한 정보 유형 시작](sit-get-started-exact-data-match-based-sits-overview.md#get-started-with-exact-data-match-based-sensitive-information-types)
- [정확한 데이터 일치 기반 중요한 정보 유형에 대해 자세히 알아보기](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)