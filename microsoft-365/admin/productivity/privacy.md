---
title: Microsoft 생산성 점수-개인 정보
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ROBOTS: NOINDEX, NOFOLLOW
description: 개인 정보를 생산성 점수가 보호 되는 방식입니다.
ms.openlocfilehash: 1af2553e67b4f14e9783c23d679a7ac96443512a
ms.sourcegitcommit: e8b3855302fc34d09b6df6c737033a2f326d6eee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48770050"
---
# <a name="privacy-controls-for-productivity-score"></a>생산성 점수에 대 한 개인 정보 제어

생산성 점수 조직은 사용자 및 기술 환경을 측정 하 고 향상 시키는 데 도움이 되는 메트릭으로 작업을 수행 하는 방식을 변환 합니다. 이를 통해 조직의 작동 방식을 파악 하는 데 도움이 되며 향상 된 경험을 사용 하기 위해 집중할 수 있는 메트릭이 제공 됩니다.  또한 모든 사용자가 최상의 작업을 수행할 수 있도록 메트릭을 작업에 연결 하 여 기술 및 시스템을 업데이트할 수 있습니다. 점수가 조직의 성과를 반영 하며 점수를 사용자와 같은 다른 조직과 안전 하 게 비교할 수도 있습니다.  자세한 내용은 [생산성 점수 개요](productivity-score.md)를 참조 하세요.

개인 정보를 보호 하는 것이 중요 합니다. 개인 정보를 보호 하는 방법에 대 한 자세한 내용은 [Microsoft의 개인 정보 취급](https://privacy.microsoft.com/privacystatement)방침를 참조 하세요. 생산성 점수 조직의 사용자가 Microsoft에 설치한 트러스트를 손상 시 키 지 않고 정보에 대 한 작업을 수행 하는 방법에 대 한 중요 한 정보를 제공 합니다.

사용자의 경험 분야 내에서 메트릭은 조직 수준에서 사용할 수 있으며 Microsoft 365 테 넌 트의 모든 사용자를 포함 합니다. 이 영역에서는 콘텐츠 공동 작업, 모바일, 회의, 팀 작업 및 통신 범주를 확인 하 여 사용자가 Microsoft 365을 사용 하는 방법을 살펴봅니다. 제품에 대 한 지원이 필요할 수 있는 올바른 사용자 집합에 대 한 교육 및 인식을 유도 하는 데 도움이 되도록 개별 수준에 대 한 정보를 제공 했습니다. 이 수준의 투명도를 제공 하지만 내부 개인 정보 보호 정책 요구 사항을 충족 하는 데 도움이 되는 다양 한 수준의 컨트롤을 사용할 수도 있습니다.
다음 컨트롤을 통해 다음을 확인할 수 있습니다.

- 유연한 관리자 역할-생산성 성과에서 정보를 볼 수 있는 사용자를 제어 합니다.
- 사용자 수준 메트릭 확인을 취소할 수 있는 기능
- 사용자 환경에 대 한 경험을 옵트아웃 하는 기능입니다.
- 사용자의 경험 분야를 옵트아웃 하는 기능

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>생산성 성과에서 정보를 볼 수 있는 사용자를 제어 하기 위한 유연한 관리 역할

테 넌 트 수준 메트릭 및 사용자별 세부 정보를 포함 하 여 전체 생산성 점수를 확인 하려면 역할이 다음 관리자 역할 중 하나 여야 합니다.

- 전역 관리자
- Exchange 관리자
- SharePoint 관리자
- 비즈니스용 Skype 관리자
- Teams 관리자
- 전역 읽기 권한자
- 보고서 구독자

변경 관리 및 채택을 담당 하는 모든 사용자에 게 보고서 독자 역할을 할당 합니다. 이 역할을 사용 하면 테 넌 트 수준 메트릭 및 사용자별 수준 세부 정보를 비롯 하 여 전체 환경에 액세스할 수 있습니다.

사용자 경험 보고서에는 각 범주 세부 정보 페이지에 대 한 사용자별 활동 세부 정보가 포함 되어 있습니다. 사용자 환경에 대 한 집계 메트릭에만 액세스할 수 있도록 사용 현황 요약 보고서 읽기 권한자 (사용 가능한 시작 29 년 10 월 2020)를 할당 합니다.

:::image type="content" source="../../media/communicationspage.jpg" alt-text="생산성 보고서의 통신 페이지":::

## <a name="de-identification-of-user-level-metrics"></a>사용자 수준 메트릭 식별 취소

모든 보고서에 대해 수집 되는 데이터를 익명으로 만들려면 전역 관리자 여야 합니다. 이 작업은 생산성 점수 및 Microsoft 365 사용량을 비롯 하 여 모든 보고서에서 사용자, 그룹 및 사이트 이름과 같은 식별 가능한 정보를 숨깁니다.

1. 관리 센터에서 조직 설정 **설정** 으로 이동 하   >   **Org Settings** 고 **서비스** 탭에서 **보고서** 를 선택 합니다.
2. **보고서** 를 선택한 다음 **생산성 점수 및 사용 현황 보고서의 사용자, 그룹 및 사이트 이름에 대 한 익명 식별자를 표시** 하도록 선택 합니다. 이 설정은 사용 현황 보고서와 서식 파일 앱에 모두 적용 됩니다.
3. **변경 내용 저장** 을 선택 합니다.

:::image type="content" source="../../media/orgsettings_anonymous.jpg" alt-text="생산성 보고서의 통신 페이지":::

## <a name="capability-to-opt-out-of-people-experiences"></a>사용자 환경에 대 한 경험을 옵트아웃 하는 기능

일반적으로 생산성 점수를 사용할 수 있는 경우에도 생산성 점수가 사용자에 게 주는 분야를 거부할 수 있습니다. 옵트아웃 하는 경우 조직에서 이러한 메트릭을 볼 수 없으며, 조직이 통신, 회의, 팀 작업, 콘텐츠 공동 작업 및 이동성과 관련 된 모든 계산에서 제거 됩니다.

1. 관리 센터에서 조직 설정 **설정** 으로 이동 하   >   **Org Settings** 고 **서비스** 탭에서 **보고서** 를 선택 합니다.
2. **보고서** 를 선택한 다음 **Microsoft 365 사용 현황 데이터를 사용 하는 사용자에 게 유용한 정보** 를 제공 하는 확인란을 선택 취소 합니다. Intune 구성 관리자에서 끝점 분석에 대 한 데이터 공유 설정을 수정 하는 방법을 이해 하려면 **자세한 정보** 를 클릭 합니다.
3. **변경 내용 저장** 을 선택 합니다.

:::image type="content" source="../../media/orgsettingspageoptout.jpg" alt-text="생산성 보고서의 통신 페이지":::