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
ms.openlocfilehash: 799d532ca1f0abd5fa6234052d4875a79d629601
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48287299"
---
# <a name="privacy-controls-for-productivity-score"></a>생산성 점수에 대 한 개인 정보 제어

생산성 점수 조직은 조직이 Microsoft 365를 사용 하는 방법 및 사용자가 지 원하는 기술 환경에 대 한 정보를 활용 하 여 작업 수행 방식을 변환할 수 있도록 합니다. 점수는 직원 및 기술 경력에 대 한&#39;s 성과를 반영 하 고 사용자의 점수를 자신과 같은 조직과 비교 합니다. 자세한 내용은 [생산성 점수 개요](productivity-score.md) 항목을 참조 하세요.

개인 정보 보호는 Microsoft의 개인 정보 [취급 방침을](https://privacy.microsoft.com/privacystatement)볼 수 있습니다. 생산성 점수에는 조직의 사용자가 작업 하는 방식에 대 한 중요 한 정보가 나와 있습니다. 따라서 정보를 의미 있는 방식으로 제대로 작동 가능 하 게 하 고 우리에 게 제공 하는 트러스트를 손상 시 키 지 않도록 제어 하는 데 목적이 있습니다.

데이터를 보다 안전 하 게 처리할 수 있도록 다음 컨트롤을 제공 합니다.

- 유연한 관리자 역할-생산성 성과에서 정보를 볼 수 있는 사용자를 제어 합니다.
- 사용자 수준 메트릭에 대 한 익명화입니다.
- 직원 경험을 옵트아웃 하는 기능

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>생산성 성과에서 정보를 볼 수 있는 사용자를 제어 하기 위한 유연한 관리 역할

테 넌 트 수준 insights와 사용자 단위 수준 세부 정보를 비롯 하 여 관리자 역할을 사용 하 여 전체 생산성 점수 환경을 확인 하려면 역할이 다음 중 하나 여야 합니다.

- 전역 관리자
- Exchange 관리자
- SharePoint 관리자
- 비즈니스용 Skype 관리자
- Teams 관리자
- 전역 읽기 권한자
- 보고서 구독자

변경 관리 및 채택을 담당 하는 사용자를 초대 하지만 IT 관리자는 작업을 수행할 수는 없지만, 테 넌 트 수준 insights 및 사용자별 수준 세부 정보를 비롯 하 여 전체 환경에 대 한 액세스 권한을 부여 하려면 보고서 독자 역할을 제공 하면 됩니다.

직원 환경 내에서는 각 범주 세부 정보 페이지에 대 한 표 형식으로 사용자별 수준 활동 세부 정보를 제공 합니다. 이 세부 정보 수준은 생산성 점수가 모든 잠재적인 방문객에 게 적합 하지는 않으므로 Azure AD – 사용 요약 보고서 독자 역할 내에 사용자 지정 역할을 만들어 조직 내의 보다 넓은 방문자 집합에 대 한 액세스를 집계 메트릭만을 사용 하 고 환경 내의 수준별 세부 정보를 사용할 수 있도록 합니다.

:::image type="content" source="../../media/communicationspage.jpg" alt-text="생산성 보고서의 통신 페이지":::

## <a name="anonymization-of-user-level-metrics"></a>사용자 수준 메트릭 익명화

모든 보고서에 대해 수집 되는 데이터를 익명으로 만들려면 전역 관리자 여야 합니다. 이렇게 하면 생산성 점수와 Microsoft 365 사용을 포함 하 여 모든 보고서에서 사용자, 그룹 및 사이트 이름과 같은 식별 가능한 정보가 숨겨집니다.

1. 관리 센터에서 조직 설정 **설정**으로 이동 하   >   **Org Settings** 고 **서비스** 탭에서 **보고서**를 선택 합니다.
2. **보고서** 를 선택한 다음 **생산성 점수 및 사용 현황 보고서의 사용자, 그룹 및 사이트 이름에 대 한 익명 식별자를 표시**하도록 선택 합니다. 이 설정은 사용 현황 보고서와 서식 파일 앱에 모두 적용 됩니다.
3. **변경 내용 저장**을 선택 합니다.

:::image type="content" source="../../media/orgsettings_anonymous.jpg" alt-text="보고서에 대해 사용자 정보를 익명으로 설정 합니다.":::

## <a name="capability-to-opt-out-of-employee-experience"></a>직원 경험을 옵트아웃 하는 기능

또한 일반적으로는 생산성 점수가 높은 직원 경험 분야를 제공할 수 있는 기능을 제공 합니다. 이 설정을 켜면 조직의 모든 사용자가 이러한 메트릭을 보고, 통신, 모임, 팀 작업, 콘텐츠 공동 작업 및 이동성 범주와 관련 된 계산에서 조직을 제거할 수 없게 됩니다.

1. 관리 센터에서 조직 설정 **설정**으로 이동 하   >   **Org Settings** 고 **서비스** 탭에서 **보고서**를 선택 합니다.
2. **보고서** 를 선택 하 고 **org&#39;s 데이터를 생산성 성과**에 지 정보를 공유 하는 확인란의 선택을 취소 합니다. Intune 구성 관리자에서 끝점 분석에 대 한 데이터 공유 설정을 수정 하는 방법을 이해 하려면 **자세한 정보**를 클릭 합니다.
3. **변경 내용 저장**을 선택 합니다.

:::image type="content" source="../../media/orgsettingspageoptout.jpg" alt-text="직원 경험을 제외할 수 있는 조직 설정 페이지":::