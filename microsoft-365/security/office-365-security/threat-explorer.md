---
title: 위협 탐색기 및 실시간 검색
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 보안 및 준수 센터에서 탐색기 및 실시간 & 사용하여 위협을 효과적으로 조사하고 대응하는 방법을 알아보십시오.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4328bfc52497f911c57256f8366b3742523b17b0
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615567"
---
# <a name="threat-explorer-and-real-time-detections"></a>위협 탐색기 및 실시간 검색

조직에 [Microsoft Defender for Office 365가](office-365-atp.md) [](#required-licenses-and-permissions)있으며 필요한 권한이 있는 경우  **탐색기** 또는 실시간 검색(이전의 실시간 [](#new-features-in-threat-explorer-and-real-time-detections)보고서 *)* 중 하나를 사용할 수 있습니다. 새로운 기능 확인 보안 & 준수 센터에서 **위협** 관리로 이동한 다음 **탐색기**  또는 실시간 검색을 **선택 합니다.**

|Microsoft Defender for Office 365 요금제 2를 사용하면 다음을 볼 수 있습니다.|Microsoft Defender for Office 365 요금제 1을 사용하면 다음이 볼 수 있습니다.|
|---|---|
|![위협 탐색기](../../media/threatmgmt-explorer.png)|![실시간 탐지](../../media/threatmgmt-realtimedetections.png)|
|

탐색기(또는 실시간 검색)를 사용하면 보안 운영 팀이 위협을 효과적으로 조사하고 대응할 수 있는 강력한 보고서가 있습니다. 보고서는 다음 이미지와 같습니다.

![위협 관리 \> 탐색기로 이동](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

이 보고서를 사용하여 다음을 할 수 있습니다.

- [Microsoft 365 보안 기능에서 검색된 맬웨어 보기](#see-malware-detected-in-email-by-technology)
- [피싱 URL에 대한 데이터 보기 및 판정 클릭](#view-data-about-phishing-urls-and-click-verdict)
- [탐색기 보기에서](#start-automated-investigation-and-response) 자동화된 조사 및 응답 프로세스 시작(Office 365 계획 2용 Defender만 해당)
- ... [악의적인 전자 메일 조사 등!](#more-ways-to-use-explorer-or-real-time-detections)

## <a name="experience-improvements-to-threat-explorer-and-real-time-detections"></a>위협 탐색기 및 실시간 검색 기능 개선

### <a name="tags-in-threat-explorer"></a>위협 탐색기에서 태그

> [!NOTE]
> 사용자 태그 기능은 미리 보기에 있으며 모든 사용자가 사용할 수 있으며 변경될 수 있습니다. 릴리스 일정에 대한 자세한 내용은 Microsoft 365 로드맵을 참조하십시오.

사용자 태그는 Office 365용 Microsoft Defender의 특정 사용자 그룹에 대한 식별자입니다. 태그, 라이선스 및 태그 구성에 대한 자세한 내용은 [사용자 태그를 참조하세요.](user-tags.md)

위협 탐색기 내에서 다음 환경의 사용자 태그 관련 정보를 볼 수 있습니다.

#### <a name="email-grid-view"></a>전자 메일 그리드 보기

전자 메일 표에 표시된 태그 열에는 보낸 사람 또는 받는 사람 사서함에 적용된 모든 태그가 포함되어 있습니다. 기본적으로 우선 순위 계정과 같은 시스템 태그가 먼저 표시됩니다.

> [!div class="mx-imgBorder"]
> ![전자 메일 그리드 보기에서 태그 필터링](../../media/tags-grid.png)

#### <a name="filtering"></a>필터링

이제 태그를 필터로 사용하여 우선 순위 계정 또는 특정 사용자 태그 시나리오를 검색할 수 있습니다(이 환경의 일부로 특정 태그가 있는 결과를 제외). 이러한 필터를 제공하는 여러 다른 필터와 결합하면 조사 범위를 좁히는 데 도움이 됩니다.

[![필터 태그](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)

> [!div class="mx-imgBorder"]
> ![필터 태그 아미](../../media/tags-filter-not.png)

#### <a name="email-detail-flyout"></a>전자 메일 세부 정보 플라이아웃
보낸 사람 및 받는 사람에 대한 개별 태그를 보려면 제목을 클릭합니다. 메시지 세부 정보 플라이아웃이 열립니다. 요약 탭에서 보낸 사람 및 받는 사람 태그가 전자 메일에 대해 표시되는 경우 별도로 표시됩니다.
보낸 사람 및 받는 사람에 대한 개별 태그에 대한 정보도 내보낼 수 있는 CSV로 확장되어 두 개의 개별 열에서 이러한 세부 정보를 볼 수 있습니다.

> [!div class="mx-imgBorder"]
> ![전자 메일 세부 정보 태그](../../media/tags-flyout.png)

태그 정보는 URL 클릭 플라이아웃에도 표시됩니다. URL 클릭 플라이아웃으로 이동하려면 피싱 또는 모든 전자 메일 보기로 이동한 다음 URL 또는 URL 클릭 탭으로 이동해야 합니다. 개별 URL 플라이아웃을 클릭하면 해당 URL의 클릭에 대한 자세한 정보가 표시될 수 있으며 해당 클릭과 태그가 연결됩니다.

> [!div class="mx-imgBorder"]
> ![URL 태그](../../media/tags-urls.png)

## <a name="improvements-to-threat-hunting-experience-upcoming"></a>위협 헌팅 환경 개선(예정)

### <a name="updated-threat-information-for-emails"></a>전자 메일에 대한 위협 정보 업데이트

당사는 전자 메일 레코드에 대한 데이터 정확도 및 일관성을 높이기 위해 플랫폼 및 데이터 품질 개선에 집중하고 있습니다. 이러한 업데이트 집합에는 배달 전 정보 및 배달 후 정보(예: ZAP 프로세스의 일부로 전자 메일에서 실행된 작업)를 단일 레코드로 통합하고 스팸 판정, 엔터티 수준 위협(예: 악의적인 URL) 및 최신 배달 위치와 같은 풍부한 기능을 포함합니다.

이러한 업데이트 후 메시지에 대해 진행된 다양한 배달 후 이벤트에 관계없이 각 메시지에 대한 단일 항목이 표시됩니다. 작업에는 ZAP, 수동 수정(관리자 작업), 동적 배달 등이 포함됩니다.

맬웨어 및 피싱 위협을 표시하는 것 외에도 이제 전자 메일과 관련된 스팸 판정을 볼 수 있습니다. 전자 메일 내에서 해당 검색 기술과 함께 전자 메일과 관련된 모든 위협을 볼 수 있습니다. 각 전자 메일에는 0, 1 또는 여러 위협이 있을 수 있습니다. 전자 메일 플라이아웃의 세부 정보 섹션에 현재 위협이 표시됩니다. 또한 여러 위협(예: 맬웨어와 피싱이 모두 있는 전자 메일)의 경우 검색 기술 필드는 Threat-Detection 매핑을 제공하게 하여 위협 식별을 이행한 검색 기술을 제공합니다.

새로운 검색 방법과 스팸 검색 기술을 포함하기 위해 업데이트된 검색 기술 집합은 모든 다른 전자 메일 보기(맬웨어, 피싱, 모든 전자 메일)에서 동일하고 일관된 검색 기술 집합을 사용하여 결과를 필터링할 수 있습니다.

> [!NOTE]
> 결과 분석이 반드시 엔터티에 연결되지 않을 수도 있습니다. 예를 들어 전자 메일은 피싱 또는 스팸으로 분류될 수 있지만 피싱/스팸 판정이 스탬프 처리된 URL은 없습니다. 이는 결과를 할당하기 전에 필터가 전자 메일의 콘텐츠 및 기타 세부 정보도 평가하기 때문에입니다.

#### <a name="threats-in-urls"></a>URL의 위협

전자 메일 플라이아웃 > 세부 정보 탭에서 URL에 대한 특정 위협을 볼 수 있습니다(URL에 대한 위협은 맬웨어, 피싱, 스팸 또는 없음일 수 있습니다).

> [!div class="mx-imgBorder"]
> ![URL 위협](../../media/URL_Threats.png)

### <a name="updated-timeline-view-upcoming"></a>업데이트된 시간 표시 막대 보기(예정된)

> [!div class="mx-imgBorder"]
> ![업데이트된 시간 표시 막대 보기](../../media/Email_Timeline.png)

타임라인 보기는 모든 배달 및 배달 후 이벤트를 식별하는 것 외에도 이러한 이벤트의 하위 집합에 대해 해당 시점에 식별된 위협에 대한 정보도 제공합니다. 또한 추가 작업(예: ZAP, 수동 수정)과 해당 작업의 결과에 대한 자세한 정보도 제공합니다. 시간 표시 막대 보기에는 원래 배달 및 이후에 전자 메일에서 수행된 모든 배달 후 이벤트에 대한 정보가 포함되어 있습니다.

- 원본: 이벤트의 원본에 따라 관리자/시스템/사용자일 수 있습니다.
- 이벤트: 여기에는 원본 배달, 수동 수정, ZAP, 제출 및 동적 배달과 같은 최상위 이벤트가 포함됩니다.
- 작업: ZAP 또는 관리자 작업의 일부로 수행된 특정 작업(예: 소프트 삭제)에 대해 다를 수 있습니다.
- 위협: 시점에서 식별된 위협(맬웨어, 피싱, 스팸)을 다 처리합니다.
- 결과/세부 정보: ZAP/관리자 작업의 일부로 수행된지 여부에 대한 작업의 결과에 대한 자세한 내용을 제공합니다.

### <a name="original-and-latest-delivery-location"></a>원본 및 최신 배달 위치

현재, 전자 메일 그리드 및 전자 메일 플라이아웃 내에 배달 위치가 표시됩니다. 앞으로 배달 위치 필드의 이름을 원래 배달 위치로 변경합니다. 또한 최신 배달 위치라는 다른 필드도 소개합니다.

원래 배달 위치는 처음에 전자 메일이 배달된 위치에 대한 자세한 정보를 제공합니다. 최신 배달 위치에는 ZAP와 같은 시스템 작업 또는 삭제된 항목으로 이동과 같은 관리자 작업 후 전자 메일이 전송될 수 있는 **위치가 포함됩니다.** 최신 배달 위치는 메시지의 배달 후 또는 시스템/관리자 작업을 관리자에게 알리기 위한 것입니다. 기본적으로 전자 메일에 대한 최종 사용자 관련 작업은 포함하지 않습니다. 예를 들어 사용자가 메시지를 삭제하거나 메시지를 보관/pst로 이동하면 "배달" 메시지가 업데이트되지 않습니다. 그러나 시스템 작업이 위치를 업데이트한 경우(예: ZAP로 인해 전자 메일이 Quarantine으로 이동) 최신 배달 위치가 Quarantine으로 표시됩니다.

> [!div class="mx-imgBorder"]
> ![업데이트된 배달 위치](../../media/Updated_Delivery_Location.png)

> [!NOTE]
> 배달 위치 및 배달 작업이 값으로 '알 수 없음'을 표시하는 경우도 있습니다.
>
> - 배달 위치가 배달된 위치로 표시될 수 있으며 배달 위치는 알 수 없음으로 표시될 수 있습니다. 이 문제는 메시지가 배달되지만 받은 편지함 규칙이 메시지를 받은 편지함 또는 정크 메일 폴더 대신 기본 폴더(임시, 보관 등)로 이동한 경우 발생합니다.
>
> - 관리자/시스템 작업(예: ZAP, 관리자 작업)을 시도했지만 메시지를 찾을 수 없는 경우 최신 배달 위치를 알 수 없습니다. 일반적으로 이 작업은 사용자가 메시지를 이동하거나 삭제한 후에 수행됩니다. 이러한 경우 시간 표시 막대 보기에서 결과/세부 정보 열을 확인해야 합니다. 메시지를 찾아야 합니다. 사용자가 이동하거나 삭제한 메시지입니다.

> [!div class="mx-imgBorder"]
> ![시간 표시 막대의 배달 위치](../../media/Updated_Timeline_Delivery_Location.png)

### <a name="additional-actions"></a>추가 작업

추가 작업은 전자 메일 배달 후 적용된 작업으로 구성되고 ZAP, 수동 수정(예: 관리자가 수행한 작업( 예: 소프트 삭제), 동적 배달 및 다시 처리(전자 메일이 소급적으로 양호한 것으로 감지)를 포함할 수 있습니다.

> [!NOTE]
>
> - 이 변경의 일부로 현재 배달 작업 필터에 표시되어 있는 ZAP에서 제거됨 값이 제거됩니다. 추가 작업을 통해 ZAP가 시도된 모든 전자 메일을 검색할 수 있습니다.
>
> - 검색 기술 및 추가 작업(특히 ZAP 시나리오의 경우)에 대한 새 필드와 값이 있습니다. 기존 저장된 쿼리 및 추적된 쿼리를 평가하여 새 값으로 작동하게 합니다.

> [!div class="mx-imgBorder"]
> ![탐색기에서 추가 작업](../../media/Additional_Actions.png)

### <a name="system-overrides"></a>시스템 오버라이드

시스템 다시 설정은 시스템에서 제공한 배달 위치(필터링 스택에서 식별된 위협 및 기타 검색에 따라)를 다시 설정하여 메시지의 의도된 배달 위치에 예외를 만드는 방법입니다. 시스템 오버라이드는 테넌트 또는 사용자 정책을 통해 정책에서 제안한 메시지를 배달하도록 설정할 수 있습니다. 다시 설정은 구성 간격(예: 사용자가 설정한 매우 광범위한 수신 -보낸 사람 정책)으로 인해 의도하지 않은 악성 메시지 배달을 식별하는 데 유용합니다. 이러한 은(는) 다음 값이 될 수 있습니다.

- 사용자 정책에서 허용: 사용자가 사서함 수준에서 정책을 만들어 도메인 또는 보낸 사람이 허용하는 경우입니다.
- 사용자 정책에 의해 차단: 사용자가 사서함 수준에서 정책을 만들어 도메인 또는 보낸 사람 차단을 하는 경우입니다.
- 조직 정책에서 허용: 조직의 보안 팀에서 조직의 사용자에 대해 보낸 사람 및 도메인을 허용하도록 정책 또는 Exchange 메일 흐름 규칙(전송 규칙)을 설정하는 경우입니다. 사용자 집합 또는 전체 조직에 사용할 수 있습니다.
- 조직 정책에 의해 차단: 조직의 보안 팀에서 정책 또는 메일 흐름 규칙을 설정하여 조직의 사용자에 대한 보낸 사람, 도메인, 메시지 언어 또는 원본 IPS를 차단하는 경우입니다. 사용자 집합이나 전체 조직에 대한 설정일 수도 있습니다.
- 조직 정책에 의해 차단되는 파일 확장명: 맬웨어 방지 정책 설정을 통해 조직의 보안 팀에 의해 파일 형식 확장명을 차단하는 경우입니다. 이제 조사에 도움이 될 수 있도록 이러한 값이 전자 메일 세부 정보로 표시됩니다. 또한 Secops 팀은 다양한 필터링 기능을 사용하여 차단된 파일 확장명을 필터링할 수 있습니다.

[![탐색기에서 시스템 오버라이드](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)

> [!div class="mx-imgBorder"]
> ![탐색기에서 시스템 눈금을 오버라이드](../../media/System_Overrides_Grid.png)

### <a name="improvements-around-url-and-clicks-experience"></a>URL 및 클릭 경험 개선

URL 및 URL 클릭 데이터에 초점을 맞추는 개선 사항 집합은 다음과 같습니다.

- URL 플라이아웃의 Clicks 섹션 내에 전체 클릭된 URL(URL의 일부인 쿼리 매개 변수 포함)을 표시 현재 제목 표시줄에 URL 도메인 및 경로가 표시됩니다. 전체 URL을 표시하기 위해 해당 정보를 확장하고 있습니다.

- 여러 URL 필터(URL과 URL 도메인 및 URL 도메인 및 경로) 픽스: URL/클릭 결과를 포함하는 메시지 검색에 대한 업데이트를 적용했습니다. 그 일환으로 프로토콜에 대한 무관한 검색 지원을 사용하도록 설정했습니다(즉, http가 없는 URL을 직접 검색할 수 있습니다). 기본적으로 URL 검색은 명시적으로 지정되지 않은 경우 http에 매핑됩니다. 예시:

  1. "URL", "URL 도메인" 및 "URL 도메인 및 경로" 필터 필드에 있는 경우와 없이 `http://` 검색합니다. 이 동작은 일관성이 있으며 동일한 결과를 표시해야 합니다.

  1. `https://`"URL"에서 사전을 검색합니다. 이 두 개가 없는 경우, 이 `http://` 전제가 사용되지 않습니다.

  1. `/` "URL 경로", "URL 도메인", "URL 도메인 및 경로" 필드의 시작과 끝은 무시됩니다. `/` 끝에 있는 "URL" 필드는 무시됩니다.

### <a name="phish-confidence-level"></a>피싱 지수

피싱 신뢰 수준은 전자 메일이 피싱으로 분류된 신뢰 수준을 식별하는 데 도움이 됩니다. 가능한 두 값은 높음과 보통입니다. 초기 단계에서 이 필터는 위협 탐색기 피싱 보기에서만 사용할 수 있습니다.

[![탐색기에서 피싱 지수](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)

### <a name="zap-url-signal"></a>ZAP URL 신호

일반적으로 전자 메일이 피싱으로 식별되고 배달 후 제거된 ZAP 피싱 경고 시나리오에 사용됩니다. 이 설정은 경고를 탐색기에서 해당 결과와 연결하는 데 사용됩니다. 이 이벤트는 경고에 대한 IOC 중 하나입니다.

헌팅 프로세스 개선의 일환으로 위협 탐색기 및 실시간 검색을 몇 가지 업데이트했습니다. 다음은 헌팅 환경을 보다 일관되게 만드는 데 중점을 두는 '환경' 개선입니다. 이러한 변경 내용은 아래에서 간략하게 설명합니다.

- [개선된 시간제](#timezone-improvements)
- [새로 고침 프로세스에서 업데이트](#update-in-the-refresh-process)
- [필터에 추가할 차트 드릴다운](#chart-drilldown-to-add-to-filters)
- [제품 정보 업데이트](#in-product-information-updates)

### <a name="filter-by-user-tags"></a>사용자 태그로 필터링

이제 시스템 또는 사용자 지정 사용자 태그별로 정렬 및 필터링하여 위협 범위를 빠르게 파악할 수 있습니다. 자세한 [내용은 사용자 태그를](user-tags.md) 참조합니다.

> [!IMPORTANT]
> 사용자 태그별 필터링 및 정렬은 현재 공개 미리 보기에 있습니다.
> 상업적으로 출시되기 전에 상당수 수정될 수 있습니다. Microsoft는 해당 정보에 대해 제공된 정보에 대해 표현적 또는 암시적 보증을하지 않습니다.

![탐색기에서 태그 열](../../media/threat-explorer-tags.png)

### <a name="timezone-improvements"></a>개선된 시간제

내보낼 데이터뿐만 아니라 포털 내의 전자 메일 레코드에 대한 타임존도 볼 수 있습니다. 전자 메일 그리드, 세부 정보 플라이아웃, 전자 메일 타임라인 및 유사한 전자 메일과 같은 환경 전반에 걸쳐 표시되어 결과 집합의 시간대가 사용자에게 명확해집니다.

> [!div class="mx-imgBorder"]
> ![탐색기에서 Timezone 보기](../../media/TimezoneImprovements.png)

### <a name="update-in-the-refresh-process"></a>새로 고침 프로세스에서 업데이트

자동 새로 고침(예: 날짜를 변경하는 즉시 페이지가 새로 고쳐지기) 및 수동 새로 고침(다른 필터의 경우)과 혼동에 대한 피드백을 들어보아야 합니다. 마찬가지로 필터를 제거하면 자동 새로 고침이 발생하여 쿼리를 수정하는 동안 다른 필터를 변경하면 검색 환경이 불일치할 수 있는 상황이 발생할 수 있습니다. 이를 해결하기 위해 수동 필터링 메커니즘으로 이동하고 있습니다.

환경 관점에서 사용자는 다양한 필터 범위(필터 집합 및 날짜)를 적용 및 제거하고 새로 고침 단추를 눌러 쿼리 정의가 완료되면 결과를 필터링할 수 있습니다. 화면에서 새로 고침 단추를 명확하게 호출하기 위해 새로 고침 단추도 업데이트되었습니다. 또한 이 변경에 대한 도구 설명 및 제품 내 설명서도 업데이트되었습니다.

> [!div class="mx-imgBorder"]
> ![새로 고침을 클릭하여 결과 필터링](../../media/ManualRefresh.png)

### <a name="chart-drilldown-to-add-to-filters"></a>필터에 추가할 차트 드릴다운

이제 차트 범례 값을 클릭하여 해당 값을 필터로 추가할 수 있습니다. 위에서 설명한 변경의 일부로 결과를 필터링하려면 새로 고침 단추를 클릭해야 합니다.

> [!div class="mx-imgBorder"]
> ![차트를 통해 필터링할 드릴다운](../../media/ChartDrilldown.png)

### <a name="in-product-information-updates"></a>제품 정보 업데이트

제품 내에 추가 세부 정보도 표시해야 합니다. 예를 들어 필터, 검색 환경 및 결과 집합에 대한 자세한 정보를 제공하려면 표 내의 총 검색 결과 수(아래 참조) 및 레이블, 오류 메시지 및 도구 설명에 대한 개선된 기능을 제공합니다.

> [!div class="mx-imgBorder"]
> ![제품 내 정보 보기](../../media/ProductInfo.png)

## <a name="extended-capabilities-in-threat-explorer"></a>위협 탐색기에서 확장된 기능

### <a name="top-targeted-users"></a>상위 대상 사용자

오늘은 전자 메일용 맬웨어 보기(상위 맬웨어 패밀리 섹션 내에서)의 상위 대상 사용자 목록을 노출합니다. 피싱 및 모든 전자 메일 보기 내에서 이 보기를 확장합니다. 여기서 상위 5개의 대상 사용자를 해당 보기에 대한 각 사용자에 대한 시도 횟수와 함께 볼 수 있습니다(예: 피싱 보기의 경우 피싱 시도 횟수를 볼 수 있습니다).
또한 각 전자 메일 보기에 대한 오프라인 분석 시도 횟수와 함께 대상 사용자 목록을 최대 3000개까지 내보낼 수 있습니다. 이 외에도 아니요를 선택합니다. 시도의 수(예: 아래 13회 시도)는 위협 탐색기에서 필터링된 보기를 열기 때문에 해당 사용자의 전자 메일 및 위협에 대한 자세한 정보를 볼 수 있습니다.

> [!div class="mx-imgBorder"]
> ![상위 대상 사용자](../../media/Top_Targeted_Users.png)

### <a name="exchange-transport-rules"></a>Exchange 전송 규칙

데이터 강화의 일부로 메시지에 적용된 다양한 전송 규칙도 모두 볼 수 있습니다. 이 정보는 전자 메일의 세부 정보 플라이아웃뿐만 아니라 전자 메일 그리드 보기(표에서 열 옵션을 선택하고 그리드의 열 옵션에서 Exchange 전송 규칙 추가)에 표시됩니다.
메시지에 적용된 전송 규칙의 이름과 GUID를 모두 볼 수 있습니다. 또한 전송 규칙의 이름을 사용하여 메시지를 검색할 수 있습니다. This would be a 'Contains' search which will be able to search using partial searches as well.

#### <a name="important-note"></a>중요 참고 사항:

ETR 검색 및 이름 사용 가능 여부는 사용자에게 할당된 특정 역할에 따라 달라집니다. ETR 이름을 보고 검색하려면 다음 역할/권한 중 하나를 설정해야 합니다.  다음 역할이 할당되지 않은 경우 전송 규칙의 이름을 보고 ETR 이름을 사용하여 메시지를 검색할 수 없습니다. 그러나 전자 메일 세부 정보 내에서 ETR 레이블 및 GUID 정보를 볼 수 있습니다. 전자 메일 그리드, 전자 메일 플라이아웃, 필터 및 내보내기에서 레코드를 보는 다른 환경은 영향을 겪지 않습니다.

- EXO 전용 - 데이터 손실 방지: 모두
- EXO 전용 - O365SupportViewConfig: 모두
- AAD 또는 EXO - 보안 관리자: 모두
- AAD 또는 EXO - 보안 판독기: 모두
- EXO 전용 - 전송 규칙: 모두
- EXO 전용 - View-Only 구성: 모두

전자 메일 그리드, 세부 정보 플라이아웃 및 내보낼 CSV 내에서 ETRS는 아래와 같이 이름/GUID와 함께 표시됩니다.

> [!div class="mx-imgBorder"]
> ![Exchange 전송 규칙](../../media/ETR_Details.png)

### <a name="inbound-connectors"></a>인바운드 커넥터

커넥터는 보안 제한 또는 제어를 적용할 수 있는 기능을 사용하여 Microsoft 365 또는 Office 365 조직에서 전자 메일이 흐르는 방법을 사용자 지정하는 지침 모음입니다. 위협 탐색기 내에서 이제 전자 메일과 관련된 커넥터를 보고 커넥터 이름을 사용하여 전자 메일을 검색하는 기능을 사용할 수 있습니다.
커넥터 검색은 본질적으로 '포함'으로, 부분 키워드 검색도 작동해야 한다는 의미입니다.
기본 그리드 보기, 세부 정보 플라이아웃 및 내보낼 CSV 내에서 커넥터는 아래와 같이 이름/GUID 형식으로 표시됩니다.

> [!div class="mx-imgBorder"]
> ![커넥터 세부 정보](../../media/Connector_Details.png)

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a>위협 탐색기 및 실시간 검색의 새로운 기능

위협 탐색기 및 실시간 검색에 추가된 세 가지 새로운 기능:

- [전자 메일 헤더 미리 보기 및 전자 메일 본문 다운로드](#preview-email-header-and-download-email-body)
- [전자 메일 타임라인](#email-timeline)
- [URL 클릭 데이터 내보내기](#export-url-click-data)

이러한 새로운 기능은 아래에서 간략하게 설명합니다.

### <a name="preview-email-header-and-download-email-body"></a>전자 메일 헤더 미리 보기 및 전자 메일 본문 다운로드

전자 메일 헤더를 미리 보고 전자 메일 본문을 다운로드하는 기능은 위협 탐색기에서 사용할 수 있는 새로운 기능입니다. 관리자는 다운로드한 헤더/전자 메일 메시지에서 위협을 분석할 수 있습니다. 전자 메일 메시지를 다운로드하면 정보가 노출될 위험이 있기 때문에 이 프로세스는 RBAC(역할 기반 액세스 제어)에 의해 제어됩니다. 모든 전자 메일 메시지 보기에서 메일 및 미리 보기 헤더를 다운로드할 수 있는 기능을 부여하려면 새 역할 미리 보기를 보안 작업 또는 보안 관리자와 같은 다른 역할 그룹에 추가해야 합니다.

그러나 탐색기(및 실시간 검색)는 전자 메일 메시지가 시작되는 위치를 보다 완전한 그림으로 표시하도록 설계된 새로운 필드도 추가합니다. 이러한 변경의 목표는 보안 Ops 사용자에 대한 헌팅을 보다 쉽게 만드는 것이지만, 결과적으로 문제 전자 메일 메시지의 위치를 한 눈에 알 수 있습니다.

어떻게 하면 하나요? 배달 상태가 이제 두 개의 열로 나어집니다.

- **배달 작업** - 이 전자 메일의 상태는 무엇입니까?
- **배달 위치** - 이 전자 메일이 어디에서 라우팅된 결과인가요?

배달 작업은 기존 정책 또는 검색으로 인해 전자 메일에서 수행된 작업입니다. 전자 메일이 수행할 수 있는 가능한 작업은 다음과 같습니다.

|배달|정크|차단됨|바꾸기|
|---|---|---|---|
|전자 메일이 사용자의 받은 편지함 또는 폴더로 배달된 경우 사용자가 직접 액세스할 수 있습니다.|전자 메일이 사용자의 정크 폴더 또는 삭제된 폴더로 전송된 경우 사용자는 해당 폴더의 전자 메일에 액세스할 수 있습니다.|중단되거나 실패했거나 삭제된 모든 전자 메일입니다. 이 설정은 사용자가 완전히 사용할 수 없습니다!|악의적인 첨부 파일이 첨부 파일이 악성 상태인 .txt 파일로 대체되는 모든 전자 메일입니다.|

|배달|정크|차단됨|바꾸기|
|---|---|---|---|
|전자 메일이 사용자의 받은 편지함이나 다른 폴더로 배달된 경우 사용자가 직접 액세스할 수 있습니다.|전자 메일이 사용자의 정크 폴더 또는 삭제된 폴더로 전송된 경우 사용자는 해당 폴더의 전자 메일 메시지에 액세스할 수 있습니다.|사용자가 액세스할 수 없는, 실패했거나 삭제된 전자 메일 메시지입니다.|악의적인 첨부 파일이 첨부 파일이 악성 상태인 .txt 파일로 대체된 모든 전자 메일 메시지입니다.|
|

사용자가 볼 수 있는 것은 다음과 같습니다.

|최종 사용자가 액세스할 수 있습니다.|최종 사용자가 사용할 수 없습니다.|
|---|---|
|배달|차단됨|
|정크|바꾸기|

배달 위치는 배달 후 실행된 정책 및 검색의 결과를 보여줍니다. 배달 동작에 연결됩니다. 이 필드는 문제가 메일이 발견될 때 수행된 작업을 파악하기 위해 추가되었습니다. 배달 위치의 가능한 값은 다음과 같습니다.

- **받은 편지함 또는 폴더:** 전자 메일이 받은 편지함 또는 폴더입니다(전자 메일 규칙에 따라).
- **On-prem or external**: the mailbox doesn't exist on cloud but is on-premises.
- **정크 폴더:** 전자 메일이 사용자의 정크 폴더에 있습니다.
- **지우기 항목 폴더:** 사용자의 지우기 항목 폴더에 있는 전자 메일입니다.
- **Quarantine:** The email in quarantine, and is not in a user's mailbox.
- **실패:** 전자 메일이 사서함에 도달하지 못했습니다.
- **삭제:** 메일 흐름에서 전자 메일이 손실됩니다.

### <a name="email-timeline"></a>전자 메일 타임라인

전자 **메일 타임라인은** 관리자에게 더 나은 헌팅 환경을 만들기 위한 또 다른 새로운 탐색기 기능입니다. 다양한 위치를 확인하여 이벤트를 파악하는 데 소요되는 시간이 적기 때문에 임의 지정이 끊어지게 됩니다. 전자 메일에서 동시에 여러 이벤트가 발생하거나 닫히면 타임라인 보기에 해당 이벤트가 표시됩니다. 실제로 메일 배달 후 발생 하는 일부 이벤트는 '특수 작업' 열에 캡처 됩니다. 해당 메일 타임라인의 정보를 메일 사후 배달에 대해 수행한 특수한 작업과 결합하면 관리자가 정책 작동 방식, 메일이 마지막으로 라우팅된 위치 및 경우에 따라 최종 평가가 수행된 방식에 대한 정보를 얻을 수 있습니다.

악의적인 전자 메일 메시지 조사에 대한 자세한 내용은 [Office 365에서](investigate-malicious-email-that-was-delivered.md)배달된 악성 전자 메일 조사 및 수정을 참조하세요.

### <a name="export-url-click-data"></a>URL 클릭 데이터 내보내기

또한 이제 URL 클릭에 대한 보고서를 Microsoft Excel로 내보낼 수 있습니다. 그러면 네트워크 메시지 ID와 해당 클릭 결과 모두를 볼 수 있어 URL 클릭 트래픽이 시작된 위치를 보다 쉽게 이해할 수 있습니다. 작동 방식은 다음과 있습니다. Office 365 빠른 실행의 위협 관리부터 다음 체인을 클릭합니다.

**탐색기** \> **피싱 보기** \> **클릭 수** \> **상위 URL 또는 URL 상위 클릭 수** \> **아무 레코드나 클릭하여 URL 플라이아웃 열기**

목록에서 URL을 클릭하면 플라이아웃 패널에 새 내보내기 단추가 표시됩니다. 이 단추를 사용하여 데이터를 Excel 스프레드시트로 이동하여 보다 쉽게 보고할 수 있습니다.

실시간 검색 보고서에서 동일한 위치에 다음과 같이 얻을 수 있습니다.

**탐색기** \> **실시간 검색** \> **피싱 보기** \> **URL** \> **상위 URL 또는 위쪽 클릭 수** \> **아무 레코드나 클릭하여 URL 플라이아웃 열기** \> **클릭 탭으로 이동합니다.**

> [!TIP]
> 네트워크 메시지 ID는 탐색기 또는 네트워크 메시지 ID를 통해 관련 타사 도구를 검색할 때 클릭을 특정 메일에 매핑합니다. 네트워크 메시지 ID를 검색하면 관리자에게 클릭 결과와 관련된 특정 전자 메일이 표시됩니다. 내보내기 시 네트워크 메시지 ID의 상호 관련 ID를 사용하면 보다 빠르고 강력한 분석이 수행됩니다.

> [!div class="mx-imgBorder"]
> ![탐색기에서 클릭 탭](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a>기술로 전자 메일에서 검색된 맬웨어 확인

Microsoft 365 기술로 전자 메일에서 검색된 맬웨어를 확인하려는 경우를 가정해 봐야 합니다. 이렇게하려면 전자 메일 [탐색기](threat-explorer-views.md#email--malware) > 맬웨어 보기(또는 실시간 검색)를 사용합니다.

1. 보안 & 준수 센터()에서 위협 관리 탐색기(또는 실시간 검색)를 <https://protection.office.com>  \>  **선택하십시오.** (이 예제에서는 Explorer를 사용합니다.)

2. 보기 **메뉴에서** 전자  메일 맬웨어를 \> **선택합니다.**

   > [!div class="mx-imgBorder"]
   > ![탐색기 보기 메뉴](../../media/ExplorerViewEmailMalwareMenu.png)

3. 보낸 **사람 클릭한** 다음 기본 검색 **기술을** \> **선택하세요.**

   이제 검색 기술을 보고서의 필터로 사용할 수 있습니다.

   > [!div class="mx-imgBorder"]
   > ![맬웨어 감지 기술](../../media/ExplorerEmailMalwareDetectionTech.png)

4. 옵션을 선택한 다음 새로  고침 단추를 클릭하여 해당 필터를 적용합니다.

   > [!div class="mx-imgBorder"]
   > ![선택한 검색 기술](../../media/ExplorerEmailMalwareDetectionTechATP.png)

보고서가 새로 고쳐서 선택한 기술 옵션을 사용하여 전자 메일에서 맬웨어가 검색된 결과를 보여 주게 됩니다. 여기에서 추가 분석을 진행할 수 있습니다.

## <a name="view-data-about-phishing-urls-and-click-verdict"></a>피싱 URL에 대한 데이터 보기 및 판정 클릭

허용, 차단 및 재지정된 URL 목록을 포함하여 전자 메일의 URL을 통해 피싱 시도를 확인하려는 경우를 가정해 봐야 합니다. 클릭한 URL을 식별하려면 안전한 링크를 [구성해야](atp-safe-links.md) 합니다. 클릭 시간 보호 및 [](set-up-atp-safe-links-policies.md) 안전한 링크로 클릭 판정 로깅에 대해 안전한 링크 정책을 설정해야 합니다.

메시지의 피싱 URL을 검토하고 피싱 메시지의 URL을 클릭하려면 전자 [](threat-explorer-views.md#email--phish) 메일 > 탐색기 보기(또는 실시간 검색)를 사용합니다.

1. 보안 & 준수 센터()에서 위협 관리 탐색기(또는 실시간 검색)를 <https://protection.office.com>  \>  **선택하십시오.** (이 예제에서는 Explorer를 사용합니다.)

2. 보기 **메뉴에서** **전자** 메일 \> **피싱을 선택합니다.**

   > [!div class="mx-imgBorder"]
   > ![피싱 컨텍스트에서 탐색기 메뉴 보기](../../media/ExplorerViewEmailPhishMenu.png)

3. 보낸 **사람 클릭한** 다음 **URL** 클릭 \> **verdict를 클릭합니다.**

4. 차단 및 다시 설정 차단과 같은 하나 이상의 옵션을 선택한  다음 해당 필터를 적용하는 옵션과 같은 줄에 있는 새로 고침 단추를 클릭합니다.  (브라우저 창을 새로 고치지 않습니다.)

   > [!div class="mx-imgBorder"]
   > ![URL 및 클릭 판정](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

   보고서가 새로 고쳐지며 보고서 아래에 있는 URL 탭에 두 개의 서로 다른 URL 테이블이 표시됩니다.

   - **상위 URL은** 필터링한 메시지에 포함된 URL과 각 URL에 대한 전자 메일 배달 작업 수입니다. 피싱 전자 메일 보기에서 이 목록에는 일반적으로 합법적인 URL이 포함되어 있습니다. 공격자는 메시지에 좋은 URL과 잘못된 URL을 혼합하여 배달하려고 시도하지만 악의적인 링크를 클릭하면 더 흥미로우게 됩니다. URL 표는 총 전자 메일 수에 따라 정렬됩니다(보기를 단순화하기 위해 이 열은 숨겨져 있습니다).

   - **위쪽 클릭은** 클릭한 안전한 링크 래핑 URL로, 총 클릭 횟수별로 정렬됩니다(이 열은 보기를 단순화하기 위해 표시되지도 않습니다). 열별로 총 개수는 클릭한 각 URL에 대한 안전한 링크 클릭 결과 수를 나타냅니다. 피싱 전자 메일 보기에서 이러한 URL은 더 자주 의심스러우거나 악의적인 URL이지만 위협이 아닌 피싱 메시지에 있는 URL을 포함할 수 있습니다. 래핑되지 않은 링크의 URL 클릭은 여기에 표시되지 않습니다.

   두 URL 테이블은 배달 작업 및 위치를 통해 피싱 전자 메일 메시지의 상위 URL을 표시하며, 차단된(또는 경고에도 불구하고 방문한) URL 클릭을 표시하여 사용자가 수신하고 사용자와 상호 작용하는 잠재적인 잘못된 링크를 이해할 수 있습니다. 여기에서 추가 분석을 진행할 수 있습니다. 예를 들어 차트 아래에서 조직의 환경에서 차단된 전자 메일 메시지의 상위 URL을 볼 수 있습니다.

   > [!div class="mx-imgBorder"]
   > ![차단된 탐색기 URL](../../media/ExplorerPhishClickVerdictURLs.png)

   URL을 선택하여 자세한 정보를 확인합니다.

   > [!NOTE]
   > URL 플라이아웃 대화 상자에서 환경의 URL 노출에 대한 전체 보기를 표시하기 위해 전자 메일 메시지에 대한 필터링이 제거됩니다. 이렇게 하면 탐색기에서 전자 메일 메시지를 우려하는 메시지로 필터링하고 잠재적 위협이 될 수 있는 특정 URL을 찾은 다음 탐색기 보기 자체에 URL 필터를 추가하지 않고도 URL 세부 정보 대화 상자를 통해 환경의 URL 노출에 대한 이해를 확장할 수 있습니다.

### <a name="interpretation-of-different-click-verdicts"></a>다른 클릭 판정 해석

전자 메일 또는 URL 플라이아웃, Top Clicks 및 필터링 환경 내에서 다양한 클릭 값이 헌팅 환경의 일부로 표시됩니다. 다음은 클릭 판정 및 해당 해석의 가능한 값입니다.

- **없음**: URL에 대한 판정을 캡처할 수 없습니다. 사용자가 URL을 클릭한 것일 수 있습니다.
- **허용:** 사용자가 URL로 이동할 수 있습니다.
- **차단:** 사용자가 URL로 이동하지 않습니다.
- **보류 중인 판정:** 사용자에게 데토네이트 보류 페이지가 표시됩니다.
- **차단된 은(는)**: 사용자가 URL로 이동하지 않습니다. 그러나 사용자는 URL로 이동하기 위해 차단을 오버라이드합니다.
- **보류 중인 판정 우회:** 사용자에게 데토네이트 페이지가 표시 그러나 사용자가 URL로 이동하기 위해 페이지를 오버라이드합니다.
- **오류:** 사용자에게 오류 페이지가 표시됩니다. 이는 또한 판정을 캡처하는 동안 오류가 발생했다는 의미일 수도 있습니다.
- **실패:** 판정을 캡처하는 동안 알 수 없는 예외가 발생했습니다. 사용자가 URL을 클릭한 것일 수 있습니다.

## <a name="review-email-messages-reported-by-users"></a>사용자가 보고한 전자 메일 메시지 검토

조직의 사용자가 웹용 Outlook 및 Outlook용 보고서 메시지 추가 기능을 사용하여 정크 메일, 정크 메일 아님 또는 피싱으로 보고한 전자 메일 메시지를 확인하려는 경우를 가정해 [봐야 합니다.](enable-the-report-message-add-in.md) 이렇게하려면 전자 메일 [](threat-explorer-views.md#email--submissions) > 제출 보기(또는 실시간 검색)를 사용합니다.

1. 보안 & 준수 센터()에서 위협 관리 탐색기(또는 실시간 검색)를 <https://protection.office.com>  \>  **선택하십시오.** (이 예제에서는 Explorer를 사용합니다.)

2. 보기 **메뉴에서** 전자 메일  \> **제출을 선택합니다.**

   > [!div class="mx-imgBorder"]
   > ![전자 메일용 탐색기 메뉴 보기](../../media/explorer-view-menu-email-user-reported.png)

3. 보낸 **사람 클릭한** 다음 기본 보고서 **유형을** \> **선택 합니다.**

4. 피싱과 같은 옵션을 선택하고 새로 **고침 단추를** 클릭합니다.

   > [!div class="mx-imgBorder"]
   > ![사용자가 보고한 피싱](../../media/EmailUserReportedReportType.png)

조직의 사용자들이 피싱 시도로 보고한 전자 메일 메시지에 대한 데이터를 표시하기 위해 보고서가 새로 고쳐서 표시됩니다. 이 정보를 사용하여 추가 분석을 수행하고 필요한 경우 [Office 365용 Microsoft Defender에서](configure-atp-anti-phishing-policies.md)피싱 방지 정책을 조정할 수 있습니다.

## <a name="start-automated-investigation-and-response"></a>자동화된 조사 및 대응 시작

> [!NOTE]
> 자동화된 조사 및 응답 기능은 **Office 365 계획 2 및 Office 365 E5용 Microsoft Defender에서** 사용할 수 **있습니다.**

(신규!) [자동화된 조사 및 대응을](automated-investigation-response-office.md) 통해 보안 운영 팀이 사이버 공격을 조사하고 완화하는 데 많은 시간과 노력을 절약할 수 있습니다. 보안 플레이북을 트리거할 수 있는 경고를 구성하는 것 외에도 탐색기 보기에서 자동화된 조사 및 응답 프로세스를 시작할 수 있습니다.

이에 대한 자세한 내용은 예제: 보안 관리자가 [Explorer에서 조사를 트리거합니다.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a>탐색기(또는 실시간 검색)를 사용하는 더 많은 방법

이 문서에 설명된 시나리오 외에도 탐색기(또는 실시간 검색)에서 더 많은 보고 옵션을 사용할 수 있습니다.

- [배달된 악성 전자 메일 찾기 및 조사](investigate-malicious-email-that-was-delivered.md)
- [SharePoint Online, OneDrive 및 Microsoft Teams에서 검색된 악성 파일 보기](malicious-files-detected-in-spo-odb-or-teams.md)
- [위협 탐색기(및 실시간 검색)에서 보기에 대한 개요를 얻습니다.](threat-explorer-views.md)
- [위협 방지 상태 보고서](view-email-security-reports.md#threat-protection-status-report)
- [Microsoft Threat Protection의 자동화된 조사 및 대응](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

## <a name="required-licenses-and-permissions"></a>필수 라이선스 및 사용 권한

탐색기 또는 실시간 검색을 [사용하려면 Office 365용 Microsoft Defender가](office-365-atp.md) 있어야 합니다.

- 탐색기는 Office 365 계획 2용 Defender에 포함되어 있습니다.
- 실시간 검색 보고서는 Office 365 계획 1용 Defender에 포함되어 있습니다.
- Office 365용 Defender에서 보호해야 하는 모든 사용자에 대한 라이선스 할당을 계획합니다. 탐색기 또는 실시간 검색은 사용이 허가된 사용자에 대한 검색 데이터를 보여줍니다.

탐색기 또는 실시간 검색을 보고 사용하려면 보안 관리자 또는 보안 읽기 권한자에 부여된 권한과 같은 적절한 권한이 있어야 합니다.

- 보안 및 & 센터의 경우 다음 역할 중 하나를 할당해야 합니다.

  - 조직 관리
  - 보안 관리자(Azure Active Directory 관리 센터에서 할당할 수 있습니다. <https://aad.portal.azure.com> )
  - 보안 읽기 권한자

- Exchange Online의 경우 Exchange 관리 센터() 또는 <https://admin.protection.outlook.com/ecp/> [Exchange Online PowerShell에서](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)다음 역할 중 하나를 할당해야 합니다.

  - 조직 관리
  - 보기 전용 조직 관리
  - 보기 전용 받는 사람
  - 준수 관리

역할 및 사용 권한에 대한 자세한 내용은 다음 리소스를 참조합니다.

- [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)
- [Exchange Online의 기능 사용 권한](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="some-differences-between-threat-explorer-and-real-time-detections"></a>위협 탐색기 및 실시간 검색 간의 몇 가지 차이점

- 실시간  검색 보고서는 Office 365 계획 1용 Defender에서 사용할 수 있는 반면 **위협** 탐색기는 Office 365 계획 2용 Defender에서 사용할 수 있습니다.
- 실시간 **검색 보고서를 사용하면** 검색을 실시간으로 볼 수 있습니다. **위협 탐색기에서도** 이 기능을 하지만 주어진 공격에 대한 추가 세부 정보를 볼 수도 있습니다.
- 위협 **탐색기에서** 모든  전자 메일 보기를 사용할 수 있으며 실시간 검색 보고서에는 **없습니다.**
- 위협 탐색기에는 더 많은 필터링 기능과 사용 가능한 **작업이 포함되어 있습니다.**

자세한 내용은 Office [365용 Microsoft Defender 서비스 설명: Office 365 계획용 Defender의 기능 가용성을 참조하세요.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)
