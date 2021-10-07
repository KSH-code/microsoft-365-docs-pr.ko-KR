---
title: 보안 포털의 Microsoft 365 프로필
description: 조직에서 장치에 대한 위험 및 노출 수준을 확인합니다. 과거 및 현재 위협을 분석하고 최신 업데이트로 장치를 보호합니다.
keywords: 보안, 맬웨어, Microsoft 365, M365, Microsoft 365 Defender, 보안 센터, 끝점용 Microsoft Defender, Office 365용 Microsoft Defender, ID용 Microsoft Defender, 장치 페이지, 장치 프로필, 컴퓨터 페이지, 컴퓨터 프로필
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 9838d7f3ffed46c62891822c6e3761e36d49baf5
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60181214"
---
# <a name="device-profile-page"></a>디바이스 프로필 페이지

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Microsoft 365 보안 포털은 장치 프로필 페이지를 제공하며, 네트워크에서 디바이스의 상태를 빠르게 평가할 수 있습니다.

> [!IMPORTANT]
> 디바이스 프로필 페이지는 장치가 Endpoint용 Microsoft Defender, ID용 Microsoft Defender 또는 둘 다에 등록된지 여부에 따라 약간 다를 수 있습니다.

장치가 끝점용 Microsoft Defender에 등록된 경우 장치 프로필 페이지를 사용하여 몇 가지 일반적인 보안 작업을 수행할 수도 있습니다.

## <a name="navigating-the-device-profile-page"></a>장치 프로필 페이지 이동

프로필 페이지는 여러 광범위한 섹션으로 나됩니다.

![(1) 탭 영역 (2) 사이드바 및 (3) 작업이 빨간색으로 강조 표시된 장치 프로필 페이지의 이미지입니다.](../../media/mtp-device-profile/hybrid-device-overall.png)

사이드바(1)에는 장치에 대한 기본 세부 정보가 나열됩니다.

기본 콘텐츠 영역(2)에는 디바이스에 대한 다양한 종류의 정보를 보기 위해 전환할 수 있는 탭이 포함되어 있습니다.

장치가 끝점용 Microsoft Defender에 등록된 경우 응답 작업 목록(3)도 표시됩니다. 응답 작업을 사용하면 일반적인 보안 관련 작업을 수행할 수 있습니다.

## <a name="sidebar"></a>사이드바

디바이스 프로필 페이지의 기본 콘텐츠 영역 옆에 사이드바가 있습니다.

![장치 프로필에 대한 사이드바 탭의 이미지입니다.](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

사이드바에는 장치의 전체 이름 및 노출 수준이 나열됩니다. 또한 다음과 같이 열리거나 닫을 수 있는 소규모 하위Ection에서 몇 가지 중요한 기본 정보를 제공합니다.

* **태그** - 끝점용 Microsoft Defender, ID용 Microsoft Defender 또는 장치와 연결된 사용자 지정 태그. Microsoft Defender for Identity의 태그는 편집할 수 없습니다.
* **보안 정보** - 인시던트 및 활성 경고 열기. 끝점용 Microsoft Defender에 등록된 디바이스에는 노출 수준 및 위험 수준도 표시됩니다.

> [!TIP]
> 노출 수준은 장치가 보안 권장 사항을 준수하는 정도와 관련이 있으며 위험 수준은 활성 경고의 유형 및 심각도 등 다양한 요인에 따라 계산됩니다.

* **장치 세부 정보** - 장치를 처음 본 시기에 대한 도메인, OS, 타임스탬프, IP 주소, 리소스. 끝점용 Microsoft Defender에 등록된 장치도 상태 표시 Id용 Microsoft Defender에 등록된 장치에는 장치를 처음 만든 시기에 대한 SAM 이름과 타임스탬프가 표시됩니다.
* **네트워크 활동** - 디바이스를 처음 및 마지막으로 네트워크에 본 타임스탬프입니다.
* **디렉터리** 데이터(ID용 *Microsoft Defender에* 등록된 장치만 해당) - [UAC](/windows/security/identity-protection/user-account-control/user-account-control-overview) 플래그, [SPNs](/windows/win32/ad/service-principal-names)및 그룹 구성원 자격.

## <a name="response-actions"></a>응답 작업

대응 조치는 위협을 신속하게 방어하고 분석하는 방법을 제공합니다.

![장치 프로필에 대한 작업 표시줄의 이미지입니다.](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * [응답 작업은](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) 장치가 끝점용 Microsoft Defender에 등록된 경우만 사용할 수 있습니다.
> * 끝점용 Microsoft Defender에 등록된 디바이스는 장치의 OS 및 버전 번호에 따라 다른 수의 응답 작업을 표시할 수 있습니다.

장치 프로필 페이지에서 사용할 수 있는 작업은 다음과 같습니다.

* **태그 관리** - 이 장치에 적용한 사용자 지정 태그를 업데이트합니다.
* **장치 격리** - 디바이스를 끝점용 Microsoft Defender에 계속 연결하면서 조직의 네트워크에서 격리합니다. 디바이스가 격리된 동안 통신을 위해 Outlook, Teams 및 비즈니스용 Skype 실행하도록 선택할 수 있습니다.
* **작업 센터** - 제출된 작업의 상태를 시청합니다. 다른 작업이 이미 선택된 경우만 사용할 수 있습니다.
* **앱 실행 제한** - Microsoft에서 서명하지 않은 응용 프로그램을 실행하지 못하도록 합니다.
* **바이러스 백신 검사** 실행 - Windows Defender 바이러스 백신 업데이트하고 바이러스 백신 검색을 즉시 실행합니다. 빠른 검사 또는 전체 검사 중 선택할 수 있습니다.
* **조사 패키지 수집** - 장치에 대한 정보를 수집합니다. 조사가 완료되면 다운로드할 수 있습니다.
* **라이브 응답** 세션 시작 - 심층 보안 조사를 위해 디바이스에 원격 [셸을 로드합니다.](/microsoft-365/security/defender-endpoint/live-response)
* **자동화된 조사 시작** - 위협을 자동으로 [조사하고 수정합니다.](../office-365-security/office-365-air.md) 이 페이지에서 자동화된 조사를 수동으로 트리거할 수 있지만 [특정](../../compliance/alert-policies.md#default-alert-policies) 경고 정책은 자체적인 자동 조사를 트리거합니다.
* **작업 센터** - 현재 실행 중인 모든 응답 작업에 대한 정보를 표시합니다.

## <a name="tabs-section"></a>Tabs 섹션

장치 프로필 탭을 사용하면 장치에 대한 보안 세부 정보 개요와 경고 목록이 포함된 테이블을 전환할 수 있습니다.

끝점용 Microsoft Defender에 등록된 장치에는 타임라인, 보안 권장 사항 목록, 소프트웨어 인벤토리, 검색된 취약성 목록 및 누락된 KB(보안 업데이트)가 있는 탭도 표시됩니다.

### <a name="overview-tab"></a>개요 탭

기본 탭은 **개요입니다.** 디바이스에 대한 가장 중요한 보안 팩트에 대한 빠른 보기를 제공합니다.

![장치 프로필에 대한 개요 탭의 이미지입니다.](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

여기서 장치의 활성 경고 및 현재 로그온한 모든 사용자를 빠르게 살펴 볼 수 있습니다.

장치가 끝점용 Microsoft Defender에 등록된 경우 장치의 위험 수준과 보안 평가에 대한 사용 가능한 데이터도 표시됩니다. 보안 평가는 장치의 노출 수준을 설명하고, 보안 권장 사항을 제공하고, 영향을 받는 소프트웨어 및 발견된 취약점을 나열합니다.

### <a name="alerts-tab"></a>경고 탭

경고 **탭에는** Id용 Microsoft Defender와 끝점용 Microsoft Defender 모두에서 장치에서 발생된 경고 목록이 포함되어 있습니다.

![장치 프로필에 대한 경고 탭의 이미지입니다.](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

표시되는 항목 수와 각 항목에 대해 표시되는 열을 사용자 지정할 수 있습니다. 기본 동작은 페이지당 30개 항목을 나열하는 것입니다.

이 탭의 열에는 경고를 트리거한 위협의 심각도, 상태, 조사 상태 및 경고가 할당된 사용자에 대한 정보가 포함됩니다.

영향을 *받는* 엔터티 열은 현재 보고 있는 프로필의 장치(엔터티)와 영향을 받는 네트워크의 다른 장치를 나타냅니다.

이 목록에서 항목을 선택하면 선택한 경고에 대한 추가 정보가 포함된 플라이아웃이 열립니다.

이 목록은 심각도, 상태 또는 경고가 할당된 사용자에 따라 필터링할 수 있습니다.

### <a name="timeline-tab"></a>시간 표시 막대 탭

시간 **표시 막대** 탭에는 디바이스에서 발생된 모든 이벤트의 대화형 시간 표시 막대형 차트가 포함되어 있습니다. 차트의 강조된 영역을 왼쪽 또는 오른쪽으로 이동하면 다양한 기간의 이벤트를 볼 수 있습니다. 대화형 차트와 이벤트 목록 사이에 있는 드롭다운 메뉴에서 날짜의 사용자 지정 범위를 선택할 수도 있습니다.

차트 아래에는 선택한 날짜 범위에 대한 이벤트 목록이 있습니다.

![장치 프로필에 대한 타임라인 탭의 이미지입니다.](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

표시되는 항목 수와 목록의 열을 모두 사용자 정의할 수 있습니다. 기본 열에는 이벤트 시간, 활성 사용자, 작업 유형, 엔터티(프로세스) 및 이벤트에 대한 추가 정보가 나열됩니다.

이 목록에서 항목을 선택하면 이벤트에 관련된 상위 및 자식 프로세스가 표시하는 이벤트 엔터티 그래프를 표시하는 플라이아웃이 열립니다.

목록을 특정 종류의 이벤트로 필터링할 수 있습니다. 예를 들어 레지스트리 이벤트 또는 Smart Screen 이벤트와 같습니다.

목록을 다운로드하기 위해 CSV 파일로 내보낼 수도 있습니다. 파일이 이벤트 수로 제한되지는는 하지만 내보낼 수 있는 최대 시간 범위는 7일입니다.

### <a name="security-recommendations-tab"></a>보안 권장 사항 탭

보안 **권장 사항** 탭에는 장치를 보호하기 위해 수행할 수 있는 작업이 나열됩니다. 이 목록에서 항목을 선택하면 추천을 적용하는 방법에 대한 지침을 얻을 수 있는 플라이아웃이 열립니다.

![장치 프로필에 대한 보안 권장 사항 탭의 이미지입니다.](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

이전 탭과 동일하게 페이지당 표시되는 항목 수와 표시되는 열을 사용자 정의할 수 있습니다.

기본 보기에는 해결된 보안 약점, 관련된 위협, 위협의 영향을 받는 관련 구성 요소 또는 소프트웨어 등 자세한 열이 포함되어 있습니다. 추천의 상태에 따라 항목을 필터링할 수 있습니다.

### <a name="software-inventory"></a>소프트웨어 인벤토리

소프트웨어 **인벤토리** 탭에는 장치에 설치된 소프트웨어가 나열됩니다.

![장치 프로필에 대한 소프트웨어 인벤토리 탭의 이미지입니다.](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

기본 보기에는 소프트웨어 공급업체, 설치된 버전 번호, 알려진 소프트웨어 약점 수, 위협 정보, 제품 코드 및 태그가 표시됩니다. 표시되는 항목 수와 표시되는 열을 모두 사용자 정의할 수 있습니다.

이 목록에서 항목을 선택하면 선택한 소프트웨어에 대한 자세한 내용과 마지막으로 소프트웨어를 찾은 시간의 경로 및 타임스탬프가 포함된 플라이아웃이 열립니다.

이 목록은 제품 코드로 필터링할 수 있습니다.

### <a name="discovered-vulnerabilities-tab"></a>발견된 취약성 탭

검색된 **취약성** 탭에는 장치에 영향을 줄 수 있는 일반 취약성 및 CV(Exploits)가 나열됩니다.

![장치 프로필에 대해 검색된 취약성 탭의 이미지입니다.](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

기본 보기에는 CVE의 심각도, CVS(Common Vulnerability Score), CVE 관련 소프트웨어, CVE가 게시된 때, CVE가 마지막으로 업데이트된 때 및 CVE와 관련된 위협이 나열됩니다.

이전 탭과 동일하게 표시되는 항목 수와 표시되는 열을 사용자 정의할 수 있습니다.

이 목록에서 항목을 선택하면 CVE를 설명하는 플라이아웃이 열립니다.

### <a name="missing-kbs"></a>KB 누락

누락된 **KB 탭에는** 장치에 아직 적용되지 않은 모든 Microsoft 업데이트가 나열됩니다. 해당 "KB"는 이러한 업데이트를 [설명하는 기술](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) 자료 문서입니다. 예를 들어 [KB4551762와 같습니다.](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762)

![장치 프로필에 대한 kbs 탭이 누락된 이미지입니다.](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

기본 보기에는 업데이트, OS 버전, 영향을 받는 제품, 주소가 지정되는 CV, KB 번호 및 태그가 포함된 공지가 나열됩니다.

페이지당 표시되는 항목 수와 표시할 열을 사용자 정의할 수 있습니다.

항목을 선택하면 업데이트에 연결되는 플라이아웃이 열립니다.

## <a name="related-topics"></a>관련 항목

* [Microsoft 365 Defender 개요](microsoft-365-defender.md)
* [Microsoft 365 Defender 켜기](m365d-enable.md)
* [라이브 응답을 사용하여 디바이스에서 엔터티 조사](../defender-endpoint/live-response.md)
* [자동화된 조사 및 대응(AIR)Office 365](../office-365-security/office-365-air.md)
