---
title: 앱 위협 탐지 및 수정 시작
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
description: 앱 위협 탐지 및 수정을 시작합니다.
ms.openlocfilehash: 7bf3e716bfa84161503ad656264ada82adc2bd6b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60188376"
---
# <a name="get-started-with-app-threat-detection-and-remediation"></a>앱 위협 탐지 및 수정 시작

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*

Microsoft 앱 거버넌스는 사용자가 만든 활성 앱 정책이 생성하는 악의적인 앱 활동 및 정책 기반 경고를 기반으로 기본 제공 앱 거버넌스 탐지 방법이 생성하는 위협 경고를 수집합니다.

가장 먼저 앱 경고가 표시되는 곳은 [https://aka.ms/appgovernance](https://aka.ms/appgovernance)의 앱 거버넌스 대시보드입니다.

![탐지 및 정책 경고 섹션이 강조 표시된 Microsoft 365 준수 센터의 앱 거버넌스 개요 페이지.](..\media\manage-app-protection-governance\mapg-cc-overview-alerts.png)

이 개요 페이지의 **탐색 및 정책 경고** 섹션에는 최신 경고가 나열됩니다. 이를 사용하여 사용자는 테넌트의 최신 앱 경고 활동을 빠르게 확인할 수 있습니다.

모든 경고를 보려면 **경고** 탭을 선택합니다.

## <a name="whats-available-on-the-alerts-page"></a>경고 페이지에서 제공되는 내용

**경고** 페이지에는 테넌트의 모든 앱 거버넌스 기반 경고가 나열됩니다.

![Microsoft 365 준수 센터의 앱 거버넌스 경고 요약 페이지.](..\media\manage-app-protection-governance\mapg-cc-alerts.png)

나열된 각 경고는 다음 정보를 포함합니다.

- **경고 이름**: 비정상적인 행위의 유형입니다.
- **앱 이름**: 경고를 생성한 앱입니다.
- **심각도**: 앱 거버넌스가 생성하는 경고에 앱 거버넌스가 할당하는 심각도 또는 경고를 생성하는 앱 정책의 심각도입니다.
- **원본**: 경고의 출처이며, 정책(사용자가 만든 정책), 탐지(기본 제공 탐지 정책) 또는 MCAS의 결과일 수 있습니다.
- **상태**: **신규** 는 상태가 할당되지 않은 경고를 나타냅니다. 상태가 할당되면 조사가 진행 중일 때는 **진행 중** 으로, 자동 또는 수동 교정을 통해 문제가 해결된 경고의 경우에는 **해결됨** 으로 표시됩니다.
- **만든 날짜**: 앱 거버넌스 탐지 또는 앱 정책을 통해 경고가 생성된 날짜입니다. 모든 날짜는 Microsoft 365 규정 준수 센터의 현지 표준 시간대로 표시됩니다.
- **마지막 활동**: 경고 상태가 마지막으로 변경된 날짜입니다. 모든 날짜는 Microsoft 365 규정 준수 센터의 현지 표준 시간대로 표시됩니다.

경고 목록은 기본적으로 **만든 날짜** 별로 정렬됩니다. 목록을 다른 앱 특성별로 정렬하려면 특성 이름을 선택합니다.

현재 경고 목록을 CSV(쉼표로 구분된 값) 파일로 내보낼 수도 있습니다. 예를 들어 Microsoft Excel에서 CVS 파일을 열고 **심각도** 별에 이어 **만든 날짜** 별로 정렬할 수 있습니다.

## <a name="next-step"></a>다음 단계

[변칙 검색 경고 조사](app-governance-anomaly-detection-alerts.md)
