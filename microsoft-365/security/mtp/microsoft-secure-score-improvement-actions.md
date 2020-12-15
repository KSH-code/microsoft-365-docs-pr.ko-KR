---
title: Microsoft 보안 점수를 통해 보안 환경 평가
description: Microsoft 365 보안 센터에서 Microsoft 보안 점수를 개선하기 위한 조치를 취하는 방법을 설명 합니다.
keywords: Microsoft 보안 점수, 보안 점수, Office 365 보안 점수, Microsoft 보안 점수, Microsoft 365 보안 센터, 개선 작업
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 8ebfe5746a69cc0161c38f0467954fabb3839240
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683346"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a>Microsoft 보안 점수를 통해 보안 환경 평가

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft 보안 점수는 조직의 보안 자세를 측정한 결과로, 수치가 높을수록 개선 작업이 더 많이 수행됩니다. Microsoft https://security.microsoft.com/securescore [365](overview-security-center.md)보안 센터에서 찾을 수 있습니다.

필요한 정보를 보다 빠르게 지원하기 위해 Microsoft 개선 작업은 그룹으로 구성됩니다.

* ID(Azure Active Directory 계정 &)
* 장치(장치용 Microsoft 보안 점수라고도 [하는 끝점용 Microsoft Defender)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices)
* 앱(Office 365 및 Microsoft Cloud App Security를 포함한 전자 메일 및 클라우드 앱)

>[!NOTE]
>Microsoft 보안 점수의 최근 릴리스에서는 Microsoft 보안 점수가 ID 보안 점수 및 Graph API와 일시적으로 양자화되지 않는 향상된 점수 매기기 모델이 릴리스되었습니다. [자세히 보기](microsoft-secure-score-whats-new.md)

Microsoft 보안 점수 개요 페이지에서 이러한 그룹 간에 점수가 분할된 방식과 사용 가능한 포인트를 참조하세요. 또한 전체 점수, 벤치마크 비교를 사용하여 보안 점수의 기록 추세, 점수를 개선하기 위해 수행할 수 있는 우선 순위가 높은 개선 작업을 모두 볼 수 있습니다.

![보안 점수 홈페이지](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a>현재 점수 확인

현재 점수를 확인한 후 Microsoft 보안 점수 개요 페이지로 이동하여 보안 점수가 표시되어 있는 **타일을 찾아 봐야 합니다.** 점수는 가능한 총 점수에서 달성한 점수 수와 함께 백분율로 표시됩니다.

또한 점수 옆에 있는  포함 단추를 선택하는 경우 점수의 다양한 보기를 선택할 수 있습니다. 이러한 서로 다른 점수 보기는 점수 타일 및 점 분석 차트의 그래프에 표시됩니다.

다음은 전체 점수의 보기에 추가하여 전체 점수에 대한 더 많은 그림을 제공 할 수 있는 점수입니다.

- **계획된 점수**: 계획된 작업이 완료된 경우의 예정된 점수 표시
- **현재 라이선스 점수:** 현재 Microsoft 라이선스로 달성할 수 있는 점수 표시
- **달성 가능한 점수:** Microsoft 라이선스 및 현재 위험 수용으로 달성할 수 있는 점수 표시

이 보기는 가능한 모든 점수 보기를 포함하면 다음과 같습니다.

![계획된 점수, 현재 라이선스 점수 및 달성 가능한 점수를 포함한 보안 점수](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a>점수 향상을 위한 조치 수행

개선 **작업 탭에는** 가능한 공격 표면을 해결하기 위한 보안 권장 사항이 나열됩니다. 또한 해당 상태(해결, 계획, 위험 수락, 타사를 통해 해결, 대체 완화를 통해 해결 및 완료)도 포함됩니다. 모든 개선 작업을 검색, 필터링 및 그룹화할 수 있습니다.  

### <a name="ranking"></a>순위

순위는 달성하기 위해 남은 점수 수, 구현 난이도, 사용자 영향 및 복잡성을 기반으로 합니다. 순위가 가장 높은 개선 작업은 난이도, 사용자 영향 및 복잡성이 낮은 점수로 남습니다.

### <a name="view-improvement-action-details"></a>개선 작업 세부 정보 보기

특정 개선 작업을 선택하면 전체 페이지 플라이아웃이 나타납니다.  

![개선 작업 플라이아웃 예제 ](../../media/secure-score/secure-score-improvement-action-details.png)
 *그림 2: 개선 작업 플라이아웃 예제*

작업을 완료하기 위해 다음과 같은 몇 가지 옵션이 있습니다.

* 구성 **화면으로** 이동하여 변경하려면 관리를 선택합니다. 그런 다음 작업을 플라이아웃에서 볼 수 있는 가치가 있는 포인트를 얻게 됩니다. 일반적으로 포인트는 업데이트하는 데 24시간 정도 소요됩니다.

* **공유를** 선택하여 개선 작업으로 직접 링크를 복사합니다. 전자 메일, Microsoft Teams, Microsoft Planner 또는 ServiceNow와 같은 링크를 공유할 플랫폼을 선택할 수도 있습니다. ServiceNow를 선택하면 ServiceNow 및 Microsoft 365 보안 센터 홈에 표시되는 변경 티켓을 만들 수 있습니다. 자세한 내용은 Microsoft 365 보안 센터 및 [ServiceNow 통합을 참조합니다.](tickets-security-center.md)

### <a name="choose-an-improvement-action-status"></a>개선 작업 상태 선택

상태를 선택하고 개선 작업과 관련한 메모를 기록합니다.

- **주소 -** 개선 작업이 필요하다는 사실과 향후에 해결될 계획입니다. 이 상태는 부분적으로 검색되지만 완전히 완료되지 않은 작업에도 적용됩니다.
- **계획** - 개선 작업을 완료하기 위한 구체적인 계획이 있습니다.
- **위험 수락** - 보안은 항상 사용 가능성과 균형을 유지해야 합니다. 모든 권장이 사용자 환경에 작동하지는 않습니다. 이 경우 위험 또는 남은 위험을 수용할 수 있으며 개선 작업을 제정하지 않을 수 있습니다. 점수는 부여되지 않지만 작업이 개선 작업 목록에 더 이상 표시되지 않습니다. 이 동작은 기록으로 보거나 실행 취소할 수 있습니다.
- **타사를** 통해 해결되고 대체 완화를 통해 **해결되었습니다.** 개선 작업은 타사 응용 프로그램 또는 소프트웨어 또는 내부 도구를 통해 이미 해결되었습니다. 작업의 가치가 있는 점수를 얻을 수 있으므로 점수가 전반적인 보안 자세를 더 잘 반영합니다. 타사 또는 내부 도구가 더 이상 컨트롤을 다루지 못하면 다른 상태를 선택할 수 있습니다. 개선 작업이 이러한 상태 중 하나로 표시되어 있는 경우 Microsoft는 구현의 완성도에 대한 가시성을 확보하지 못합니다.

#### <a name="threat--vulnerability-management-improvement-actions"></a>위협 & 관리 개선 작업

"장치" 범주의 개선 작업의 경우 상태를 선택할 수 없습니다. 대신 Microsoft [Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) 보안 센터의 관련 위협 & [취약성 관리(취약점 관리)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) 보안 권장 지침으로 연결하여 조치를 취하게 됩니다. 선택한 예외 및 작성 사당성은 해당 포털과 관련이 있습니다. Microsoft 보안 점수 포털에는 존재하지 않습니다.

#### <a name="completed-improvement-actions"></a>개선 작업 완료

개선 작업의 가능한 모든 지점이 달성된 경우 개선 작업이 "완료" 상태가 됩니다. 완료된 개선 작업은 Microsoft 데이터를 통해 확인하며 상태를 변경할 수 없습니다.

### <a name="assess-information-and-review-user-impact"></a>정보 평가 및 사용자 영향 검토

이 **섹션에서는** 범주, 공격으로부터 보호할 수 있는 공격 및 제품을 한눈에 알 수 있습니다.

사용자 **영향은** 개선 작업이 제정된 경우 사용자에게 어떤  영향을 주는지 보여 주며 영향을 받는 사용자에게는 해당 작업을 경험할 수 있는 사람이 표시될 수 있습니다.

### <a name="implement-the-improvement-action"></a>개선 작업 구현

구현 **섹션에는** 개선 작업을 완료하기 위한 모든 선행 작업, 단계별 다음 단계, 개선 작업의 현재 구현 상태 및 자세한 링크가 표시됩니다.

선행 요구에는 획득해야 하는 라이선스 또는 개선 조치가 해결되기 전에 완료해야 하는 작업이 포함됩니다. 라이선스에 사용자 수가 충분한지 확인하여 개선 작업을 완료하고 해당 라이선스가 필요한 사용자에게 적용해야 합니다.  

## <a name="we-want-to-hear-from-you"></a>의견을 보내 주세요.

문제가 있는 경우 보안, 개인 정보 보호 및 규정 준수 커뮤니티에 게시하여 [& 알려주세요.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 커뮤니티를 모니터링하고 있으며 도움을 제공할 것입니다.

## <a name="related-resources"></a>관련 리소스

- [Microsoft 보안 점수 개요](microsoft-secure-score.md)
- [Microsoft 보안 점수 기록 추적 및 목표 충족](microsoft-secure-score-history-metrics-trends.md)
- [향후 계획](microsoft-secure-score-whats-coming.md)
- [새로운 기능](microsoft-secure-score-whats-new.md)
