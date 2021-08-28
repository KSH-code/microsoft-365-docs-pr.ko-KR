---
title: 가시성 및 인사이트 시작
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 가시성 및 인사이트를 시작합니다.
ms.openlocfilehash: 30871804c9e8cf4e548698ecb326917baef36c37
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58569660"
---
# <a name="get-started-with-visibility-and-insights"></a>가시성 및 인사이트 시작

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*

가장 먼저 시작할 곳은 [https://aka.ms/appgovernance](https://aka.ms/appgovernance)의 앱 거버넌스 대시보드입니다. 앱 거버넌스 데이터를 보려면 로그인 계정에 [이와 같은 앱 거버넌스 관리자 역할 ](app-governance-get-started.md#administrator-roles) 중 하나가 있어야 합니다.

![Microsoft 365 준수 센터의 앱 거버넌스 개요 페이지.](..\media\manage-app-protection-governance\mapg-cc-overview.png)

**Office 365 > Microsoft 365 준수 센터 > 앱 거버넌스 > 개요 페이지** 에서 앱 거버넌스 대시보드에 액세스할 수도 있습니다.

## <a name="whats-available-on-the-dashboard"></a>대시보드에서 사용할 수 있는 기능

대시보드에는 테넌트에서 Microsoft 365 앱 에코시스템의 구성 요소에 대한 요약이 포함되어 있습니다.

- **테넌트 요약**: 주요 앱 및 경고 범주의 수
- **상위 경고**: 테넌트에서 가장 최근의 활성 경고 10개
- **데이터 및 리소스 액세스**: 그래프의 매월 열을 마우스로 클릭하여 해당 값을 확인합니다.
    - **지난 4개월 동안의 데이터 액세스**: 지난 4개월 동안 Graph API 통해 테넌트에서 모든 앱이 액세스한 총 데이터를 추적합니다. 현재 메일 및 파일 업로드/다운로드 사용량만 포함됩니다.
    - **지난 4개월 동안의 상위 리소스 데이터 액세스**: 지난 4개월 동안 데이터 사용량이 리소스 종류별로 세분화됩니다. 현재 메일 및 파일 업로드/다운로드 사용량만 포함됩니다.
- **앱 보호 및 거버넌스 개선**: 앱 사용 또는 권한 정책 만들기와 같은 권장 조치입니다.
- **범주별 상위 앱**: 다음 범주별로 정렬된 상위 앱:
  
  - **모든 범주**: 사용 가능한 모든 범주를 정렬합니다.
  - **높은 권한**: 높은 권한은 플랫폼 기계 학습 및 신호를 기반으로 내부적으로 결정되는 범주입니다.
  - **과도한 권한 부여**: 앱 거버넌스가 지난 90일 동안 애플리케이션에 부여된 사용 권한이 사용되지 않았음을 나타내는 원격 분석을 수신하면 해당 애플리케이션에 과도한 권한이 부여되지 않습니다. 앱 거버넌스가 90일 이상 작동하여 앱이 초과 권한이 있는지 확인해야 합니다.  
  - **확인되지 않음**: [게시자 인증](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview)을 받지 못한 응용 프로그램은 확인되지 않은 것으로 간주됩니다.
  - **앱만 해당**: [애플리케이션 사용 권한](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#permission-types)은 로그인한 사용자 없이 실행할 수 있는 앱에서 사용됩니다. 테넌트 전체에서 데이터에 액세스할 수 있는 권한이 있는 앱은 잠재적으로 더 높은 위험 요소입니다.
  - **새 앱**: 지난 7일 동안 등록된 새 Microsoft 365 앱입니다.  

## <a name="next-step"></a>다음 단계

[특정 앱에 대한 자세한 인사이트를 가져옵니다](app-governance-visibility-insights-view-apps.md).
