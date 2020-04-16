---
title: Microsoft 365 보안 포털의 장치 프로필
description: 조직의 장치에 대 한 위험 및 노출 수준을 확인 합니다. 이전의 및 현재 위협을 분석 하 고 최신 업데이트를 사용 하 여 장치를 보호 합니다.
keywords: 보안, 맬웨어, Microsoft 365, M365, Microsoft 위협 보호, MTP, 보안 센터, Microsoft Threat ATP, Office 365 ATP, Azure ATP, 장치 페이지, 장치 프로필, 컴퓨터 페이지, 컴퓨터 프로필
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: db6109fb73f0e208ab4403e2469bc955a1a01b38
ms.sourcegitcommit: d767c288ae34431fb046f4cfe36cec485881385f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/15/2020
ms.locfileid: "43517039"
---
# <a name="device-profile-page"></a>장치 프로필 페이지

Microsoft 365 보안 포털은 장치 프로필 페이지를 제공 하므로 네트워크의 장치 상태를 빠르게 평가할 수 있습니다.

> [!IMPORTANT]
> 장치가 Microsoft Defender ATP, Azure ATP 또는 둘 다에 등록 되어 있는지에 따라 장치 프로필 페이지가 약간 다르게 표시 될 수 있습니다.

장치가 Microsoft Defender ATP에 등록 되어 있는 경우 장치 프로필 페이지를 사용 하 여 몇 가지 일반적인 보안 작업을 수행할 수도 있습니다.

## <a name="navigating-the-device-profile-page"></a>장치 프로필 페이지 탐색

프로필 페이지는 여러 광범위 한 섹션으로 나뉩니다.

![장치 프로필 페이지 이미지 (1) 탭 영역 (2) 보충 기사 및 (3) 작업이 빨간색으로 강조 표시 됨](../../media/mtp-device-profile/hybrid-device-overall.png)

사이드바 (1)에는 장치에 대 한 기본 세부 정보가 나열 됩니다.

기본 콘텐츠 영역 (2)에는 장치에 대 한 다양 한 종류의 정보를 보기 위해 전환할 수 있는 탭이 있습니다.

장치가 Microsoft Defender ATP에 등록 되어 있는 경우 응답 작업 목록도 표시 됩니다 (3). 응답 동작을 사용 하 여 일반적인 보안 관련 작업을 수행할 수 있습니다.

## <a name="sidebar"></a>기사의

장치 프로필 페이지의 기본 콘텐츠 영역 옆에는 사이드바가 있습니다.

![장치 프로필에 대 한 사이드바 탭 이미지](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

보조 기사에는 장치의 전체 이름 및 노출 수준이 나열 됩니다. 또한 다음과 같이 열리거나 닫을 수 있는 작은 하위 섹션의 몇 가지 중요 한 기본 정보를 제공 합니다.

* **Tag** -장치에 연결 된 MICROSOFT Defender Atp, Azure ATP 또는 사용자 지정 태그입니다. Azure ATP의 태그는 편집할 수 없습니다.
* **보안 정보** -인시던트 및 활성 알림을 엽니다. Microsoft Defender ATP에 등록 되어 있는 장치에도 노출 수준 및 위험 수준도 표시 됩니다.

> [!TIP]
> 노출 수준은 장치가 보안 권장 사항을 준수 하는 양과 관련 된 반면 위험 수준은 활성 알림의 유형과 심각도를 비롯 한 다양 한 요인에 따라 계산 됩니다.

* **장치 정보** -도메인, OS, 장치가 처음 표시 된 타임 스탬프, IP 주소, 리소스입니다. Microsoft Defender ATP에 등록 되어 있는 장치에도 상태 상태가 표시 됩니다. Azure ATP에 등록 된 장치는 디바이스를 처음 만들 때의 SAM 이름 및 타임 스탬프를 표시 합니다.
* **네트워크 활동** -네트워크에서 장치를 마지막으로 본 시간에 대 한 타임 스탬프입니다.
* **디렉터리 데이터** (*Azure ATP에 등록 된 장치에만*해당)- [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) 플래그, [spn](https://docs.microsoft.com/windows/win32/ad/service-principal-names)및 그룹 멤버 자격

## <a name="response-actions"></a>응답 작업

응답 동작은 위협을 보호 하 고 분석 하는 빠른 방법을 제공 합니다.

![장치 프로필에 대 한 작업 모음 이미지](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * [응답 작업](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) 은 장치가 MICROSOFT Defender ATP에 등록 되어 있는 경우에만 사용할 수 있습니다.
> * Microsoft Defender ATP에 등록 된 장치는 장치의 OS 및 버전 번호에 따라 다양 한 응답 작업을 표시할 수 있습니다.

장치 프로필 페이지에서 사용할 수 있는 작업은 다음과 같습니다.

* **Manage tags** -이 장치에 적용 한 사용자 지정 태그를 업데이트 합니다.
* **장치 격리** -Microsoft Defender Advanced Threat Protection에 연결 된 상태로 장치를 조직의 네트워크에서 격리 합니다. 통신 목적으로, 장치가 격리 된 상태에서 Outlook, 팀 및 비즈니스용 Skype가 실행 되도록 허용할 수 있습니다.
* **동작 센터** -전송 된 작업의 상태를 확인 합니다. 이미 다른 작업을 선택한 경우에만 사용할 수 있습니다.
* **앱 실행 제한** -Microsoft에서 서명 하지 않은 응용 프로그램이 실행 되지 않도록 합니다.
* **바이러스** 검사 프로그램 실행-Windows Defender 바이러스 백신 정의를 업데이트 하 고 바이러스 백신 검사를 즉시 실행 합니다. 빠른 검색 또는 전체 검사 중에서 선택 합니다.
* **Collect 조사 패키지** -장치에 대 한 정보를 수집 합니다. 조사가 완료 되 면이를 다운로드할 수 있습니다.
* **Initiate Live Response Session** - [심층 보안 조사](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)를 위해 장치에서 원격 셸을 로드 합니다.
* **자동화 된 조사 시작** - [위협 자동 조사 및 remediates](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) 자동 조사를 수동으로 트리거하여이 페이지에서 실행할 수는 있지만 [특정 경고 정책이](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) 자동 조사를 자체적으로 트리거합니다.
* **알림 센터** -현재 실행 중인 모든 응답 작업에 대 한 정보를 표시 합니다.

## <a name="tabs-section"></a>Tabs 섹션

장치 프로필 탭을 사용 하 여 장치에 대 한 보안 세부 정보 개요와 경고 목록을 포함 하는 테이블을 전환할 수 있습니다.

Microsoft Defender ATP에 등록 된 장치에는 시간 표시 막대, 보안 권장 사항 목록, 소프트웨어 인벤토리, 검색 된 취약점 목록, 빠진 Kb (보안 업데이트) 등을 나타내는 탭이 표시 됩니다.

### <a name="overview-tab"></a>개요 탭

기본 탭은 **개요**입니다. 이를 통해 장치에 대 한 가장 중요 한 보안 팩트를 빠르게 확인할 수 있습니다.

![장치 프로필에 대 한 개요 탭 이미지](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

여기서는 장치의 활성 알림과 현재 로그온 한 사용자를 빠르게 확인할 수 있습니다.

장치가 Microsoft Defender ATP에 등록 되어 있으면 장치의 위험 수준 및 보안 평가에 대 한 사용 가능한 모든 데이터도 표시 됩니다. 보안 평가에서는 장치의 노출 수준, 보안 권장 사항 및 영향을 받는 소프트웨어 나열 및 발견 된 취약점을 설명 합니다.

### <a name="alerts-tab"></a>알림 탭

**알림** 탭에는 Azure Atp 및 MICROSOFT Defender atp에서 장치에 대해 발생 한 경고 목록이 포함 되어 있습니다.

![장치 프로필에 대 한 알림 탭 이미지](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

표시 되는 항목 수와 각 항목에 표시 되는 열을 사용자 지정할 수 있습니다. 기본 동작은 페이지당 항목 30 개를 나열 하는 것입니다.

이 탭의 열에는 경고를 트리거한 위협의 심각도, 상태, 조사 상태 및 경고가 할당 된 사용자에 대 한 정보가 포함 됩니다.

영향을 받는 *엔터티* 열은 현재 보고 있는 장치 (엔터티)와 네트워크에 있는 다른 모든 장치를 참조 합니다.

이 목록에서 항목을 선택 하면 선택한 경고에 대 한 더 많은 정보가 포함 된 플라이 아웃이 열립니다.

이 목록은 심각도, 상태 또는 경고가 할당 된 사람에 따라 필터링 될 수 있습니다.

### <a name="timeline-tab"></a>시간 표시 막대 탭

**시간 표시 막대** 탭에는 장치에서 발생 한 모든 이벤트의 대화형 시간 차트가 포함 되어 있습니다. 차트에서 강조 표시 된 영역을 왼쪽 이나 오른쪽으로 이동 하면 여러 기간에 걸쳐 이벤트를 볼 수 있습니다. 대화형 차트와 이벤트 목록 사이에 있는 드롭다운 메뉴에서 사용자 지정 날짜 범위를 선택할 수도 있습니다.

차트 아래에는 선택한 날짜 범위에 대 한 이벤트 목록이 나와 있습니다.

![장치 프로필에 대 한 시간 표시 막대 탭 이미지](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

표시 되는 항목 수와 목록에 있는 열을 모두 사용자 지정할 수 있습니다. 기본 열에는 이벤트 시간, 활성 사용자, 작업 유형, 엔터티 (프로세스) 및 이벤트에 대 한 추가 정보가 나열 됩니다.

이 목록에서 항목을 선택 하면 이벤트 엔터티 그래프가 표시 되는 플라이 아웃이 열리며 여기에는이 이벤트가 관련 된 부모 및 하위 프로세스가 표시 됩니다.

이 목록은 특정 유형의 이벤트로 필터링 될 수 있습니다. 예를 들면 레지스트리 이벤트 또는 스마트 스크린 이벤트가 있습니다.

이 목록은 다운로드를 위해 CSV 파일로 내보낼 수도 있습니다. 파일은 이벤트 수로 제한 되지 않지만 내보낼 수 있는 최대 시간 범위는 7 일입니다.

### <a name="security-recommendations-tab"></a>보안 권장 사항 탭

**보안 권장 사항** 탭에는 장치를 보호 하기 위해 수행할 수 있는 작업이 나열 되어 있습니다. 이 목록에서 항목을 선택 하면 권장 사항을 적용 하는 방법에 대 한 지침을 얻을 수 있는 플라이 아웃이 열립니다.

![장치 프로필에 대 한 보안 권장 사항 탭 이미지](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

이전 탭과 마찬가지로, 페이지 별로 표시 되는 항목 수와 표시 되는 열을 사용자 지정할 수 있습니다.

기본 보기에는 보안 약점, 관련 위협, 위협에 영향을 받는 구성 요소 또는 소프트웨어를 자세히 설명 하는 열이 포함 되어 있습니다. 추천 상태를 기준으로 항목을 필터링 할 수 있습니다.

### <a name="software-inventory"></a>소프트웨어 인벤토리

**소프트웨어 인벤토리** 탭에는 장치에 설치 된 소프트웨어가 나열 됩니다.

![장치 프로필의 소프트웨어 인벤토리 탭 이미지](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

기본 보기에는 소프트웨어 공급 업체, 설치 된 버전 번호, 알려진 소프트웨어 약점 수, 위협 정보, 제품 코드 및 태그가 표시 됩니다. 표시 되는 항목 수와 표시 되는 열이 모두 사용자 지정 될 수 있습니다.

이 목록에서 항목을 선택 하면 선택한 소프트웨어에 대 한 세부 정보를 포함 하는 플라이 아웃이 열리고, 소프트웨어를 마지막으로 찾은 시간에 대 한 경로 및 타임 스탬프가 열립니다.

이 목록은 제품 코드를 기준으로 필터링 할 수 있습니다.

### <a name="discovered-vulnerabilities-tab"></a>검색 된 취약성 탭

**검색 된 취약성** 탭에는 장치에 영향을 줄 수 있는 모든 일반 취약성 및 악용 (cves)이 나열 됩니다.

![장치 프로필에 대 한 검색 된 취약성 탭의 이미지](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

기본 보기에는 CVE, 일반적인 취약성 점수 (CVS), cve와 관련 된 소프트웨어, cve가 마지막으로 업데이트 된 날짜, CVE와 관련 된 위협 등이 나열 됩니다.

이전 탭과 마찬가지로 표시 되는 항목의 수와 표시할 수 있는 열이 사용자 지정 가능 합니다.

이 목록에서 항목을 선택 하면 CVE를 설명 하는 플라이 아웃이 열립니다.

### <a name="missing-kbs"></a>누락 된 Kb

**누락 된 kb** 탭에는 장치에 아직 적용 되지 않은 Microsoft 업데이트 목록이 표시 됩니다. "Kb"는 이러한 업데이트를 설명 하는 [기술 자료 문서](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) 입니다. 예: [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).

![장치 프로필에 대 한 누락 된 kb 탭 이미지](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

기본 보기에는 업데이트, OS 버전, 영향을 받는 제품, CVEs 주소, 수 및 태그가 포함 된 게시판이 표시 됩니다.

페이지당 표시 되는 항목 수와 표시 되는 열을 사용자 지정할 수 있습니다.

항목을 선택 하면 업데이트에 연결 되는 플라이 아웃이 열립니다.

## <a name="related-topics"></a>관련 항목

* [Microsoft 위협 방지 개요](microsoft-threat-protection.md)
* [Microsoft 위협 방지 설정](mtp-enable.md)
* [라이브 응답을 사용 하 여 장치의 엔터티 조사](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [Office 365의 자동화 된 조사 및 응답 (AIR)](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
