---
title: 중요한 정보 유형과 일치하는 정확한 데이터 테스트
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
description: 서비스 구성
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3030a97e3ed80524d2170e74b3d35f897b6ed74c
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914890"
---
# <a name="test-an-exact-data-match-sensitive-information-type"></a>중요한 정보 유형과 일치하는 정확한 데이터 테스트

EDM(정확한 데이터 일치) 중요한 정보 유형(SIT)이 생성되고 1시간 후에 중요한 정보 테이블의 업로드 및 인덱싱이 완료된 후 준수 센터의 중요한 정보 유형 섹션에서 테스트 기능을 사용하여 검색하려는 정보를 검색하는지 테스트할 수 있습니다.
 
>[! 참고:] 이미 만들어진 EDM SIT의 변경 내용을 시스템 전체에 전파하는 데 시간이 걸릴 수 있습니다. 검색 문제 해결을 위해 EDM 중요한 정보 유형을 변경하는 경우 테스트 함수를 사용하여 영향의 유효성을 검사하기 전에 해당 변경을 수행한 후 1시간 이상 기다려야 합니다.

## <a name="test-your-edm-sit-in-the-compliance-center"></a>준수 센터에서 EDM SIT 테스트

1. 개방형 **준수 센터**  >  **데이터 분류 중요한** 정보  >  **유형입니다.**

2. 목록에서 EDM SIT를 선택한  다음 플라이아웃 창에서 테스트를 선택합니다. 이 옵션은 중요한 정보 유형에서만 SIT에 제공됩니다.
 
3. 업로드 데이터가 포함된 항목을 검색합니다. 예를 들어 중요한 정보 표에 행의 하위 집합이 포함된 항목을 만들 수 있습니다. Schema에서 구성 가능한 일치 기능을 사용하여 무시된 개별 항목을 정의한 경우 항목에 해당 개별 항목과 함께 및 포함하지 않는 예제를 포함해야 합니다.

4. 파일을 업로드하고 검사한 후 EDM SIT와 일치하는지 검사합니다.

5. SIT의 **Test** 함수가 일치를 검색하는 경우 해당 일치를 잘라 내거나 올바르게 추출하지 않는지 유효성을 검사합니다. 예를 들어 전체 문자열의 하위 문자열만 추출하여 검색하거나 다중 단어 문자열의 첫 번째 단어만 선택하거나 추출에 추가 기호나 문자를 포함해야 합니다. 정규식 [언어 참조에](/dotnet/standard/base-types/regular-expression-language-quick-reference) 대한 자세한 내용은 정규식 언어 - 빠른 참조를 참조합니다. 

5. 또는 다음 PowerShell cmdlet을 사용할 수 있습니다.

```powershell
Test-DataClassification  -ClassificationNames “[Your EDM sensitive info type]” -TexttoClassify “[your own text to scan for matches]” 
```

> [!NOTE]
 EDM 중요한 정보 유형 또는 EDM 형식의 기반이 될 기본 SIT를 만들거나 편집하는 경우, SITS 변경 후 수정된 모든 새 콘텐츠와 콘텐츠는 새 정의와 일치하는 텍스트에 대해 크롤링되지만, 수정하거나 다시 인덱스할 때까지는 보존 콘텐츠가 크롤링되지 않습니다. 

SharePoint 사이트 또는 라이브러리 또는 OneDrive 기존 콘텐츠를 강제로 다시 크롤링하려면 [사이트,](/sharepoint/crawl-site-content)라이브러리 또는 목록의 크롤링 및 다시 인덱싱을 수동으로 요청의 지침을 따릅니다.

## <a name="test-your-edm-sit-in-mip-policies"></a>MIP 정책에서 EDM SIT 테스트

정책에서 EDM SIT를 사용하여 EDM SIT가 사용되는 위치와 프로덕션에서 EDM SIT가 얼마나 정확한지 알 수 있습니다.

1. 자동 레이블 [지정 정책을 만들고](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) 시뮬레이션 개요 **에서 실행합니다.**

1. EDM SIT를 트리거하는 일부 콘텐츠와 EDM SIT를 트리거하지 않는 일부 콘텐츠를 정책이 모니터링하는 위치에 추가합니다.

1. 검토할 **항목 탭을** 열고 일치 항목을 검사합니다.

1. 정책을 적절하게 조정합니다. 

테스트 및 조정 결과에 만족하면 EDM 기반 사용자 지정 SIT를 정보 보호 정책에 사용할 준비가 됩니다.

- [DLP 정책](create-test-tune-dlp-policy.md#create-test-and-tune-a-dlp-policy)
- [자동 레이블 지정 정책](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)
- [Microsoft Cloud App Security 정책](/cloud-app-security/data-protection-policies)

## <a name="troubleshooting-tips"></a>문제 해결 팁

일치하는 일치가 없는 경우 다음을 시도합니다.

- EDM 도구를 사용하여 중요한 데이터를 업로드하기 위한 지침에 설명된 명령을 사용하여 중요한 데이터가 올바르게 업로드된지 확인합니다.

- 항목에 입력한 예제가 중요한 정보 표에 있으며 무시된 구분선이 올바른지 확인합니다.

- 각 패턴에서 기본 요소를 구성할 때 사용한 SIT를 테스트합니다. 그러면 SIT가 항목의 예제와 일치할 수 있습니다. 잘못 정의된 SIT를 EDM 중요한 정보 유형의 분류 요소로 사용하는 것이 EDM의 검색 실패의 가장 일반적인 원인입니다. 

- EDM 형식의 기본 요소에 대해 선택한 SIT가 항목에서 일치 항목을 찾지 못하거나 예상보다 적은 일치 항목을 찾으면 콘텐츠에 있는 구분 구분 및 구분기를 지원하는지 검사합니다. 해당 schema에 정의된 무시된 디지타이터를 포함해야 합니다.

- Test 함수에서 콘텐츠를 검색하지 못하면 선택한 SIT에 추가 키워드 또는 기타 유효성 검사에 대한 요구 사항이 포함되어 있지 않은지 확인합니다. 기본 제공 SITS에 대한 [](sensitive-information-type-entity-definitions.md#sensitive-information-type-entity-definitions) 자세한 내용은 중요한 정보 유형 엔터티 정의를 참조하여 각 유형과 일치하기 위한 최소 요구 사항을 확인합니다.

- 테스트 기능이 작동하지만 SharePoint 또는 OneDrive 항목이 DLP 또는 자동레이블 규칙에서 검색되지 않는 경우 일치하는 것으로 예상되는 문서가 콘텐츠 탐색기에 표시되어 있는지 검사합니다. 해당 콘텐츠가 없는 경우 중요한 정보 유형이 변경된 후에 만들어진 콘텐츠만 일치로 표시될 수 있습니다. 기존 항목을 표시하기 위해 사이트 및 라이브러리를 다시 크롤링해야 합니다. [사이트,](/sharepoint/crawl-site-content) 라이브러리 또는 목록의 크롤링 및 다시 인덱싱에 대한 자세한 내용은 수동으로 크롤링 및 다시 인덱싱 요청을 SharePoint OneDrive. 

- 여러 일치가 필요한 DLP 또는 자동레이블 규칙이 트리거되지 않는 경우 EDM 유형과 기본 중요한 정보 유형 둘 다에 대한 근접성 요구 사항이 충족되는지 확인합니다. 예를 들어 기본 요소와 지원 키워드 사이의 최대 거리가 300자이지만 키워드가 긴 테이블의 첫 번째 행에만 있는 경우 일치하는 값의 처음 몇 행만 근접성 요구 사항을 충족할 수 있습니다. 더 완화된 근접성 규칙을 지원하도록 SIT 정의를 수정하거나 추가 증거 조건에 대해 문서 옵션의 아무 곳이나 사용합니다. 

- EDM 유형의 검색이 불일치하거나 이상한 경우 EDM 형식에서 기본 요소의 기준으로 사용한 중요한 정보 유형이 불필요한 콘텐츠를 검색하지 않는지 검사합니다. 아무 단어, 숫자와 같이 관련이 없는 콘텐츠와 너무 많이 일치하는 SIT를 사용하는 경우 모든 전자 메일 주소로 인해 서비스가 관련 일치를 포화하고 무시할 수 있습니다. 콘텐츠 탐색기에서 기본 요소에 사용한 중요한 유형과 일치하는 콘텐츠 조각 수를 검사합니다. SIT가 너무 많은 콘텐츠와 일치하는지 예측하기 위해
    1. 콘텐츠 탐색기에서 콘텐츠 항목 수를 중요한 유형이 만들어진 이후의 일 수로 나중을 나타 내는 경우
    2. 일당 일치 횟수가 수만 개 또는 수백만 개 범위에 있는 경우 기본 SIT가 너무 광범위할 수 있습니다. [EDM](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types) 유형에 적합한 중요한 정보 유형을 선택하는 방법 및 권장 사항에 대한 자세한 내용은 정확한 데이터 일치 기반의 중요한 정보 유형에 대해 자세히 알아보고 모범 사례를 참조하세요. 

- 해시에 설명된 명령을 사용하여 중요한 데이터가 올바르게 업로드 지 확인하고 정확한 데이터 일치 중요한 정보 유형에 대한 중요한 정보 원본 테이블을 [업로드합니다.](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types)

- EDM 형식의 기본 요소에 대해 선택한 SIT가 항목에서 일치 항목을 찾지 못하거나 예상보다 적은 일치 항목을 찾으면 콘텐츠에 있는 구분 및 구분기를 지원하는지 검사합니다. 해당 schema에 정의된 무시된 디지타이터를 포함해야 합니다. 

