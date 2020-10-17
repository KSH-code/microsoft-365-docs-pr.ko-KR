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
description: 보안 및 준수 센터에서 Explorer 및 실시간 검색을 사용 하 여 위협에 효과적이 고 효율적으로 대응 하는 방법에 대해 알아봅니다 &amp; .
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 89708efa6a34b5ca7a302ba0ad331a2dac99f5d9
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477181"
---
# <a name="threat-explorer-and-real-time-detections"></a>위협 탐색기 및 실시간 검색

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


조직에 [office 365 Advanced Threat Protection](office-365-atp.md) (OFFICE 365 ATP)이 있고 [필요한 사용 권한이](#required-licenses-and-permissions)있는 경우에는 **Explorer** 또는 **실시간** 검색 (이전에는 [새로운 기능을 참조 하세요](#new-features-in-threat-explorer-and-real-time-detections) *.)을* 수행 해야 합니다. 보안 & 준수 센터에서 **위협 관리**로 이동한 다음 **Explorer** _또는_ **실시간**검색을 선택 합니다.

|ATP 계획 2를 사용 하는 경우 다음을 확인할 수 있습니다.|ATP 계획 1을 사용 하는 경우 다음을 확인할 수 있습니다.|
|---|---|
|![위협 탐색기](../../media/threatmgmt-explorer.png)|![실시간 탐지](../../media/threatmgmt-realtimedetections.png)|
|

Explorer (또는 실시간 검색)를 사용 하는 경우 보안 운영 팀이 효과적이 고 효율적으로 위협을 조사 하 고 대응 하는 데 사용할 수 있는 강력한 보고서가 있습니다. 보고서는 다음 이미지와 유사 합니다.

![위협 관리 탐색기로 이동 \>](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

이 보고서를 사용 하 여 다음을 수행할 수 있습니다.

- [Microsoft 365 보안 기능으로 검색 된 맬웨어를 참조 하세요.](#see-malware-detected-in-email-by-technology)
- [피싱 Url에 대 한 데이터를 확인 하 고 결과를 클릭 합니다.](#view-data-about-phishing-urls-and-click-verdict)
- [탐색기에서 보기 로부터 자동화 된 조사 및 응답 프로세스 시작](#start-automated-investigation-and-response) (ATP 요금제 2에만 해당)
- ... [악성 전자 메일을 조사 하 고 더 많은 방법을 확인해](#more-ways-to-use-explorer-or-real-time-detections)보세요.

## <a name="tags-in-threat-explorer"></a>위협 탐색기의 태그

> [!NOTE] 
> 사용자 태그 기능은 미리 보기에서 모든 사용자가 사용할 수 없으며 변경할 수 있습니다. 릴리스 일정에 대 한 자세한 내용은 Microsoft 365 로드맵를 참조 하세요.

사용자 태그는 Microsoft Defender for Office 365의 특정 사용자 그룹에 대 한 식별자입니다. 태그에 대 한 자세한 내용, 태그 라이선스 및 구성에 대 한 자세한 내용은 [Office 365 ATP의 사용자 태그](user-tags.md)를 참조 하세요.

위협 탐색기 내에서 사용자 태그에 대 한 정보를 볼 수 있는 경험은 다음과 같습니다.

#### <a name="email-grid-view"></a>전자 메일 표 보기

전자 메일 표에 표시 되는 태그 열에는 보낸 사람 또는 받는 사람 사서함에 적용 된 모든 태그가 포함 되어 있습니다. 기본적으로 우선 순위 계정과 같은 시스템 태그가 먼저 표시 됩니다.

![필터 태그](../../media/tags-grid.png)

#### <a name="filtering"></a>필터링
이제는 태그를 필터로 사용 하 여 우선 순위 계정 또는 특정 사용자 태그 시나리오를 검색 하 고 특정 태그에서 결과를이 환경의 일부로 제외할 수 있습니다. 이러한 정보를 제공 하는 여러 필터를 결합 하 여 조사 범위를 좁히는 데 도움이 될 수 있습니다.

![필터 태그](../../media/tags-filter-normal.png)

![필터 태그 아님](../../media/tags-filter-not.png)

#### <a name="email-detail-flyout"></a>전자 메일 세부 정보 플라이 아웃
보낸 사람과 받는 사람에 대 한 개별 태그를 보려면 제목을 클릭 합니다. 메시지 세부 정보 플라이 아웃이 열립니다. 요약 탭에서는 전자 메일을 보낼 때 보낸 사람 및 받는 사람 태그가 별도로 표시 됩니다.
보낸 사람과 받는 사람에 대 한 개별 태그에 대 한 정보는 내보낸 CSV로 확장 되며, 이러한 세부 정보를 두 개의 개별 열에 볼 수 있습니다. 

![전자 메일 세부 정보 태그](../../media/tags-flyout.png)

태그 정보는 URL 클릭 시 플라이 아웃에도 표시 됩니다. URL로 이동 하려면 플라이 아웃을 클릭 하 고, url 또는 URL 클릭 탭에 대 한 자세한 정보를 보려면 개별 URL 플라이 아웃을 클릭 하 여 해당 URL의 클릭에 대 한 자세한 내용을 표시 하 고, 해당 클릭과 관련 된 태그를 사용 해야 합니다. 

![URL 태그](../../media/tags-urls.png)

## <a name="improvements-to-threat-hunting-experience-upcoming"></a>위협 요소 구하기 환경 개선 (다가오는 예정)

### <a name="updated-threat-information-for-emails"></a>전자 메일에 대 한 업데이트 된 위협 정보

전자 메일 레코드의 데이터 정확성과 일관성을 높이기 위해 플랫폼 및 데이터 품질 개선에 중점을 두었습니다. 이러한 업데이트 집합에는 배달 전 및 배달 전 정보 (예: 전자 메일에 대해 ZAP 프로세스의 일부로 실행 되는 작업)가 단일 레코드에 포함 되어 있으며,이는 스팸 결과, 엔터티 수준 위협 (URL은 악성) 및 최신 배달 위치와 같은 추가 된 다양성과 함께 사용 됩니다. 

이러한 업데이트 후에는 메시지에 대해 발생 한 다른 배달 후 이벤트에 관계 없이 각 메시지에 대해 단일 항목이 표시 됩니다. 작업에는 ZAP, 수동 재구성 (관리 작업을 의미), 동적 배달 등이 포함 될 수 있습니다. 

이제 맬웨어 및 피싱 위협을 표시 하는 것 외에도 전자 메일과 연결 된 스팸 결과 볼 수 있습니다. 전자 메일 내에서 전자 메일과 관련 된 모든 위협을 해당 검색 기술과 함께 볼 수 있습니다. 각 전자 메일에는 0 개, 1 개 또는 여러 개의 위협이 있을 수 있습니다. 전자 메일 플라이 아웃의 세부 정보 섹션에 현재 위협이 표시 됩니다. 또한 여러 위협의 경우 (예: 맬웨어 및 피싱이 둘 다 있는 전자 메일) 검색 기술 필드는 Threat-Detection 매핑을 제공 하 여 위협 식별을 위한 검색 기술에 대 한 정보를 반환 합니다.

검색 기술 집합은 새로운 검색 방법 뿐 아니라 스팸 감지 기술 및 모든 다른 전자 메일 보기 (맬웨어, 피싱, 모든 전자 메일)에 걸쳐 결과를 필터링 할 수 있는 동일한 수준의 검색 기술이 제공 되도록 업데이트 되었습니다. 

> [!NOTE]
> 결과 분석이 반드시 엔터티에 연결 되는 것은 아닙니다. 예를 들어 전자 메일은 피싱 또는 스팸으로 분류 되지만 피싱/스팸 결과 스탬프를 포함 하는 Url은 없습니다. 이는 결과를 할당 하기 전에 필터에서 콘텐츠와 전자 메일에 대 한 기타 세부 정보를 평가 하기 때문입니다. 
 
#### <a name="threats-in-urls"></a>Url의 위협

이제 전자 메일 플라이 아웃-> 세부 정보 탭에서 URL에 대 한 특정 위협을 볼 수 있습니다 (URL에 대 한 위협: 맬웨어, 피싱, 스팸 또는 없음).

> [!div class="mx-imgBorder"]
> ![URL 위협](../../media/URL_Threats.png)

### <a name="updated-timeline-view-upcoming"></a>업데이트 된 시간 표시 막대 보기 (예정 됨)

> [!div class="mx-imgBorder"]
> ![업데이트 된 시간 표시 막대 보기](../../media/Email_Timeline.png)

시간 표시 막대 보기는 모든 배달 및 배달 후 이벤트를 식별 하는 것 외에도 이러한 이벤트의 하위 집합에 대 한 해당 시점에 식별 된 위협에 대 한 정보도 제공 합니다. 또한이 작업의 결과와 함께 ZAP, 수동 재구성 등의 추가 작업에 대 한 자세한 정보도 제공 됩니다. 시간 표시 막대 보기에는 원래 배달에 대 한 정보와 이후에 전자 메일에 대해 수행 된 배달 후 이벤트가 포함 됩니다.

-   원본:이는 이벤트의 출처를 기반으로 하는 관리자/시스템/사용자 일 수 있습니다.
-   이벤트: 원래 배달, 수동 재구성, ZAP, 전송, 동적 배달과 같은 최상위 이벤트가 포함 됩니다.
-   작업:이 작업은 ZAP 또는 관리 작업 (예: 소프트 삭제)의 일부로 수행 된 특정 동작에 대해 설명 합니다.
-   위협: 해당 시점에 식별 된 위협 (맬웨어, 피싱, 스팸)을 다룹니다.
-   Result/Details: 작업 결과에 대 한 자세한 내용은 ZAP/Admin 작업의 일부로 수행 되었는지 여부에 대해 설명 합니다.

### <a name="original-and-latest-delivery-location"></a>원본 및 최신 배달 위치

오늘날에는 전자 메일 표 및 전자 메일 플라이 아웃 내에 배달 위치가 표시 됩니다. 전달 되는 경우 배달 위치 필드의 이름이 원래 배달 위치로 변경 됩니다. 또한 최신 배달 위치 라는 다른 필드도 소개 하 고 있습니다. 

원래 배달 위치는 처음에 전자 메일이 배달 된 위치에 대 한 추가 정보를 제공 합니다. 최신 배달 위치에는 전자 메일에서 **삭제 된 항목으로 이동**같은 ZAP 또는 관리 작업 등의 시스템 작업을 수행 하 여 마법사로 돌아갑니다 수 있는 위치가 포함 됩니다. 최신 배달 위치는 메시지의 마지막으로 알려진 위치, 배달 후 또는 시스템/관리자 작업을 관리자에 게 알리기 위한 것입니다. 기본적으로 전자 메일에는 최종 사용자 관련 작업이 포함 되지 않습니다. 예를 들어 사용자가 메시지를 삭제 하거나 메시지를 보관/pst로 옮기면 메시지 "배달" 위치가 업데이트 되지 않습니다. 그러나 시스템 작업에서 위치를 업데이트 하는 경우 (예: 전자 메일을 격리로 이동 하는 ZAP) 최신 배달 위치가 격리로 표시 됩니다. 

> [!div class="mx-imgBorder"]
> ![업데이트 된 배달 위치](../../media/Updated_Delivery_Location.png)

> [!NOTE]
> 배달 위치 및 배달 작업에서 ' 알 수 없음 '이 값으로 표시 되는 경우가 있습니다.
> 
> - 배달 위치가 배달 됨 및 알 수 없는 배달 위치로 표시 될 수 있습니다. 메시지가 배달 되었지만 받은 편지함 규칙에서 받은 편지함 또는 정크 메일 폴더 대신 기본 폴더 (임시, 보관 등)로 메시지를 이동한 경우에 이러한 상황이 발생 합니다. 
> 
> - 최신 배달 위치는 관리/시스템 작업 (예: ZAP, 관리 작업)을 시도 했지만 해당 메시지가 없는 경우 알 수 없습니다. 일반적으로이 작업은 사용자가 메시지를 이동 하거나 삭제 한 후에 발생 합니다. 이러한 경우 시간 표시 막대 보기에서 결과/세부 정보 열을 확인 합니다. 메시지가 사용자에 의해 이동 또는 삭제 된 메시지를 찾습니다.

> [!div class="mx-imgBorder"]
> ![시간 표시 막대의 배달 위치](../../media/Updated_Timeline_Delivery_Location.png)

### <a name="additional-actions"></a>추가 작업 

추가 작업은 적용 된 작업으로 구성 되며 전자 메일 배달이 진행 되 고 ZAP, 수동 재구성 (관리자가 수행 하는 작업 (예: 일시 삭제), 동적 배달 및 다시 처리 (전자 메일이 retroactively 검색 됨)이 포함 될 수 있습니다. 

> [!NOTE]
>
> - 이러한 변경의 일환으로 배달 작업 필터에 현재 표시 된 ZAP 값이 제거 됩니다. 추가 작업을 통해 ZAP을 시도 하는 모든 전자 메일을 검색할 수 있습니다.
>
> - 검색 기술 및 추가 작업에 대 한 새로운 필드와 값 (특히 ZAP 시나리오)이 있습니다. 기존의 저장 된 쿼리 및 추적 한 쿼리를 평가 하 여 새 값으로 작동 하는지 확인 합니다. 

> [!div class="mx-imgBorder"]
> ![Additional_Actions](../../media/Additional_Actions.png)

### <a name="system-overrides"></a>시스템 재정의 

시스템 재정의는 필터링 스택에서 식별 된 위협 및 기타 검색에 따라 시스템에서 제공 하는 배달 위치를 재정의 하 여 메시지의 원하는 배달 위치를 예외로 만드는 방법입니다. 정책에서 권장 하는 대로 메시지를 배달 하기 위해 테 넌 트 또는 사용자 정책을 통해 시스템 재정의를 설정할 수 있습니다. 재정의는 구성 간격 (예: 사용자가 설정 하는 매우 광범위 한 안전한 보낸 사람 정책)으로 인해 악의적인 메시지가 예기치 않게 배달 되는 것을 식별 하는 데 유용 합니다. 이러한 재정의 값은 다음이 될 수 있습니다.

- 사용자 정책에 의해 허용 됨: 사용자가 사서함 수준에서 정책을 만들어 도메인 이나 보낸 사람을 허용 하는 경우입니다.
- 사용자 정책에 의해 차단 됨: 사용자가 사서함 수준에서 정책을 만들어 도메인 이나 보낸 사람을 차단 하는 경우입니다.
- 조직 정책에서 허용: 조직의 보안 팀이 조직의 사용자에 게 보낸 사람 및 도메인을 허용 하는 정책 또는 Exchange 메일 흐름 규칙 (전송 규칙이 라고도 함)을 설정 하는 경우 이는 사용자 집합 또는 전체 조직에 대 한 일 수 있습니다.
- 조직 정책에 의해 차단 됨: 조직의 보안 팀이 조직의 사용자에 대 한 보낸 사람, 도메인, 메시지 언어 또는 원본 Ip를 차단 하는 정책 또는 메일 흐름 규칙을 설정 합니다. 이는 사용자 집합 또는 전체 조직에도 해당 될 수 있습니다.
- 조직 정책에 의해 차단 된 파일 확장명:이는 파일 형식 확장이 맬웨어 방지 정책 설정을 통해 조직의 보안 팀에 의해 차단 되는 경우입니다. 이러한 값은 조사를 지원 하기 위해 이제 전자 메일 세부 정보에 표시 됩니다. Secops 팀은 다양 한 필터링 기능을 사용 하 여 차단 된 파일 확장명을 기준으로 필터링 할 수도 있습니다.

![System_Overrides](../../media/System_Overrides.png)

> [!div class="mx-imgBorder"]
> ![System_Overrides_Grid](../../media/System_Overrides_Grid.png)


### <a name="improvements-around-url-and-clicks-experience"></a>URL 및 클릭 환경에 대 한 개선 사항

URL 및 URL 클릭 데이터를 중심으로 하는 향상 된 기능 집합은 다음과 같습니다.

 - Url 플라이 아웃의 클릭 섹션 내에서 URL의 일부인 쿼리 매개 변수를 포함 하 여 클릭 한 전체 URL을 표시 합니다. 현재 URL 도메인과 경로가 제목 표시줄에 표시 됩니다. 이 정보를 확장 하 여 전체 URL을 표시 합니다.
 
 - Url 필터 (URL vs url 도메인 vs URL 도메인 및 경로): URL이 포함 된 메시지를 검색 하는 과정에서 업데이트를 수행 하 고 결과를 클릭 합니다. 이 작업의 일부로, 프로토콜에 관계 없이 검색을 지원 하도록 설정 했습니다 (http를 사용 하지 않고 URL을 직접 검색할 수 있음). 기본적으로 URL 검색은 명시적으로 지정 된 경우를 제외 하 고 http에 매핑됩니다. 예시:

   1. `http://`"Url", "Url 도메인" 및 "Url 도메인 및 경로" 필터 필드에서 접두사를 사용 하지 않고 검색 합니다. 이 동작은 일관적 이며 같은 결과를 표시 합니다.
   
   1. `https://`"URL"에서 접두사를 검색 합니다. 이 매개 변수를 제공 하지 않으면 `http://` 접두사를 가정 합니다.
   
   1. `/` "URL 경로", "url 도메인 및 경로" 필드의 시작과 끝에는 무시 됩니다. `/` "URL" 필드 끝에는 무시 됩니다. 

### <a name="phish-confidence-level"></a>피싱 신뢰 수준

피싱 신뢰 수준에서는 전자 메일이 피싱로 분류 되는 신뢰도를 식별 하는 데 도움이 됩니다. 두 가지 가능한 값은 High 및 Normal입니다. 초기 단계에서이 필터는 Threat Explorer의 피싱 보기 에서만 사용할 수 있습니다.

![Phish_Confidence_Level](../../media/Phish_Confidence_Level.png)

### <a name="zap-url-signal"></a>ZAP URL 신호 

일반적으로 전자 메일이 피싱로 식별 되 고 배달 후 제거 된 ZAP 피싱 경고 시나리오에 사용 됩니다. 이는 해당 경고를 탐색기의 해당 결과와 연결 하는 데 사용 됩니다. 이는 경고에 대 한 IOCs 중 하나입니다. 

## <a name="experience-improvements-to-threat-explorer-and-real-time-detections"></a>위협 탐색기 및 Real-Time 검색 기능이 향상 되었습니다.

검색 프로세스를 개선 하는 과정에서 위협 탐색기와 Real-Time 검색을 몇 가지 업데이트 했습니다. 이러한 기능은 개선 된 경험을 보다 일관성 있게 만드는 데 중점을 둔 ' 경험 ' 향상 기능입니다. 이러한 변경 내용은 아래에 설명 되어 있습니다.

- [향상 된 표준 시간대](#timezone-improvements)
- [새로 고침 프로세스의 업데이트](#update-in-the-refresh-process)
- [필터에 추가할 차트 드릴 다운](#chart-drilldown-to-add-to-filters)
- [제품 정보 업데이트](#in-product-information-updates)

### <a name="timezone-improvements"></a>향상 된 표준 시간대

내보낸 데이터 뿐만 아니라 포털 내의 전자 메일 레코드에 대 한 표준 시간대가 표시 됩니다. 표준 시간대는 전자 메일 표, 세부 정보 플라이 아웃, 전자 메일 일정 및 유사한 전자 메일 같은 경험을 통해 표시 되므로 결과 집합에 대 한 표준 시간대가 사용자에 게 분명 하 게 제공 됩니다.

> [!div class="mx-imgBorder"]
> ![탐색기에서 표준 시간대 보기](../../media/TimezoneImprovements.png)

### <a name="update-in-the-refresh-process"></a>새로 고침 프로세스의 업데이트

자동 새로 고침을 사용한 혼동에 대 한 의견을 들었습니다 (예: 날짜를 변경 하는 즉시, 페이지를 새로 고치는 작업) 및 수동 새로 고침 (기타 필터에 대 한 경우). 마찬가지로, 필터를 제거 하면 자동 새로 고침이 실행 되므로 쿼리를 수정 하는 동안 다른 필터를 변경 하면 검색 환경이 일치 하지 않을 수 있습니다. 이를 해결 하기 위해 수동 필터링 메커니즘으로 이동 하 고 있습니다.

경험 측면에서 볼 때 사용자는 필터 집합 및 날짜에서 서로 다른 필터 범위를 적용 하 고 제거할 수 있으며, 새로 고침 단추를 눌러 쿼리 정의 작업을 완료 한 후에 결과를 필터링 할 수도 있습니다. 화면에서 명확 하 게 전화를 걸기 위해 새로 고침 단추도 업데이트 되었습니다. 또한이 변경 사항에 대 한 도구 설명 및 제품 설명서도 업데이트 되었습니다.

> [!div class="mx-imgBorder"]
> ![새로 고침을 클릭 하 여 결과를 필터링 합니다.](../../media/ManualRefresh.png)

### <a name="chart-drilldown-to-add-to-filters"></a>필터에 추가할 차트 드릴 다운

이제 차트 범례 값을 클릭 하 여 해당 값을 필터로 추가할 수 있습니다. 위에서 설명한 변경 내용의 일부로 결과를 필터링 하려면 새로 고침 단추를 클릭 해야 합니다.

> [!div class="mx-imgBorder"]
> ![차트에서 필터링으로 드릴 다운](../../media/ChartDrilldown.png)

### <a name="in-product-information-updates"></a>제품 정보 업데이트

제품 내에 추가 정보도 표시 해야 합니다. 예를 들어 표 내에 있는 총 검색 결과 수 (아래 참조)와 레이블 주위의 향상 된 기능, 필터, 검색 환경 및 결과 집합에 대 한 자세한 정보를 제공 하기 위해 오류 메시지와 도구 설명이 표시 됩니다.

> [!div class="mx-imgBorder"]
> ![제품 내 정보 보기](../../media/ProductInfo.png)

## <a name="extended-capabilities-in-threat-explorer"></a>위협 탐색기의 확장 기능

### <a name="top-targeted-users"></a>상위 대상 사용자

현재는 전자 메일에 대 한 맬웨어 보기에서 가장 많이 대상으로 지정 된 사용자의 목록을 최상위 맬웨어 제품군 내에서 노출 합니다. 여기서는 피싱 및 모든 전자 메일 보기에서이 보기를 확장 하 고 해당 하는 보기에 대 한 각 사용자의 시도 횟수 (예: 피싱 보기에서 피싱 시도 횟수를 볼 수 있음)와 함께 상위 5 개 사용자를 볼 수 있습니다.
또한 각 전자 메일 보기에 대 한 오프 라인 분석 시도 횟수와 함께 대상 사용자 목록을 최대 3000까지 내보낼 수 있습니다. 이 외에도 아니요를 선택 합니다. (예: 아래의 13 번 시도)은 위협 탐색기에서 필터링 된 보기를 열고 해당 사용자의 전자 메일 및 위협에 대 한 세부 정보를 확인할 수 있습니다.

> [!div class="mx-imgBorder"]
> ![상위 대상 사용자](../../media/Top_Targeted_Users.png)


### <a name="exchange-transport-rules"></a>Exchange 전송 규칙
또한 데이터 향상의 일부로, 메시지에 적용 된 다른 전송 규칙도 모두 볼 수 있습니다. 이 정보는 전자 메일 표 보기 내에 표시 되며,이를 확인 하려면 표에서 열 옵션을 선택 하 고 표에 있는 열 옵션에서 Exchange 전송 규칙 추가와 전자 메일의 세부 정보 플라이 아웃을 함께 클릭 합니다.
메시지에 적용 된 전송 규칙의 이름 뿐 아니라 GUID도 볼 수 있습니다. 또한 전송 규칙의 이름을 사용 하 여 메시지를 검색할 수 있습니다. 이는 ' 포함 ' 검색으로, 부분 검색을 사용 하 여 검색할 수 있다는 것을 의미 합니다.

#### <a name="important-note"></a>중요 참고 사항:
ETR 검색 및 이름 사용 가능 여부는 자신에 게 할당 된 특정 역할에 따라 달라 집니다. ETR 이름과 검색을 보려면 다음 역할/사용 권한 중 하나가 있어야 합니다.  사용자에 게 할당 된 다음 역할이 없는 경우 전송 규칙의 이름을 확인 하 고 ETR 이름을 사용 하 여 메시지를 검색할 수 없게 됩니다. 그러나 전자 메일 세부 정보 내에서 ETR 레이블과 GUID 정보를 볼 수 있습니다. 전자 메일 표에서 레코드를 보는 경우의 다른 경험에는 영향을 주지 않습니다 (전자 메일 flyouts, 필터 및 내보내기).

- EXO Only-데이터 손실 방지: 모두
- EXO Only-O365SupportViewConfig: All
- AAD 또는 EXO-보안 관리자: 모두
- AAD 또는 EXO-보안 읽기 권한자: 모두
- EXO Only-전송 규칙: 모두
- EXO Only-View-Only 구성: 모두

전자 메일 표, 세부 정보 플라이 아웃 및 내보낸 CSV에는 아래와 같이 이름/GUID와 함께 ETRs가 표시 됩니다.

> [!div class="mx-imgBorder"]
> ![Exchange 전송 규칙](../../media/ETR_Details.png)

### <a name="inbound-connectors"></a>인바운드 커넥터

커넥터는 Microsoft 365 또는 Office 365 조 직에서 전자 메일이 들어오고 나가는 방식을 사용자 지정 하는 지침 모음으로, 보안 제한이 나 제어를 적용할 수 있습니다. 이제는 위협 탐색기 내에서 전자 메일과 관련 된 커넥터를 확인 하 고 커넥터 이름을 사용 하 여 전자 메일을 검색할 수 있습니다.
커넥터 검색은 부분적인 키워드 검색도 작동 하도록 ' 포함 ' 되어 있습니다.
기본 눈금 보기, 세부 정보 플라이 아웃 및 내보낸 CSV에서 커넥터는 아래와 같이 이름/GUID 형식으로 표시 됩니다.

> [!div class="mx-imgBorder"]
> ![커넥터 세부 정보](../../media/Connector_Details.png)

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a>위협 탐색기 및 실시간 검색의 새로운 기능

위협 탐색기 및 실시간 검색에 다음과 같은 세 가지 새로운 기능이 추가 되었습니다.

- [전자 메일 머리글 미리 보기 및 전자 메일 본문 다운로드](#preview-email-header-and-download-email-body)
- [전자 메일 시간 표시 막대](#email-timeline)
- [URL 내보내기 데이터 클릭](#export-url-click-data)

이러한 새로운 기능은 아래에 설명 되어 있습니다.

### <a name="preview-email-header-and-download-email-body"></a>전자 메일 머리글 미리 보기 및 전자 메일 본문 다운로드

전자 메일 머리글을 미리 보고 전자 메일 본문을 다운로드 하는 기능은 위협 탐색기에서 사용할 수 있는 새로운 기능입니다. 관리자가 다운로드 한 헤더/전자 메일 메시지를 분석 하 여 위협을 분석할 수 있습니다. 전자 메일 메시지를 다운로드 하면 정보의 노출을 초래할 수 있으므로이 프로세스는 RBAC (역할 기반 액세스 제어)를 통해 제어 됩니다. 모든 전자 메일 메시지 보기에서 메일을 다운로드 하 고 머리글을 미리 볼 수 있도록 하려면 새 역할인 *미리 보기*를 다른 역할 그룹 (예: 보안 작업 또는 보안 관리자)에 추가 해야 합니다.

그러나 Explorer (및 실시간 검색)도 새로운 새 필드를 추가 하 여 전자 메일 메시지가 있는 위치를 보다 완전 하 게 파악할 수 있습니다. 이러한 변경 목표의 일환으로는 보안 Ops 사용자에 게 더 쉽게 사냥을 제공할 수 있지만 문제 전자 메일 메시지의 위치를 한눈에 파악 하는 것은 아닙니다.

어떤 작업을 수행 하나요? 배달 상태는 이제 다음과 같은 두 개의 열로 나뉩니다.

- **배달 작업** -이 전자 메일의 상태는 무엇입니까?
- **배달 위치** -이 전자 메일의 경로가 어떻게 설정 되었습니까?

배달 작업은 기존 정책 또는 검색으로 인해 전자 메일에 대해 수행 되는 작업입니다. 다음은 전자 메일에 사용할 수 있는 작업입니다.

|배달|Junked|차단됨|바뀌면|
|---|---|---|---|
|전자 메일이 사용자의 받은 편지함 또는 폴더에 배달 되었으며 사용자가 직접 액세스할 수 있습니다.|사용자의 정크 폴더 또는 삭제 된 폴더에 전자 메일이 전송 되 고 해당 폴더의 전자 메일에 대 한 액세스 권한이 사용자에 게 있습니다.|격리 되거나, 실패 했거나, 삭제 된 전자 메일입니다. 사용자가이를 완전히 액세스할 수 없습니다.|첨부 파일이 악성 인 .txt 파일로 악의적 첨부 파일이 교체 되는 모든 전자 메일|

|배달|Junked|차단됨|바뀌면|
|---|---|---|---|
|전자 메일이 사용자의 받은 편지함 또는 다른 폴더로 배달 되었으며 사용자가 직접 액세스할 수 있습니다.|사용자의 정크 폴더 또는 삭제 된 폴더로 전자 메일이 전송 되 고 해당 폴더의 전자 메일 메시지에 대 한 액세스 권한이 사용자에 게 있습니다.|격리 되거나, 실패 했거나, 삭제 되었으며 사용자가 액세스할 수 없는 전자 메일 메시지가 표시 됩니다.|첨부 파일이 악성 인 .txt 파일로 악의적 첨부 파일을 바꾼 전자 메일 메시지|
|

다음은 사용자가 볼 수 있는 것과 그렇지 않은 항목입니다.

|최종 사용자가 액세스할 수 있음|최종 사용자가 액세스할 수 없음|
|---|---|
|배달|차단됨|
|Junked|바뀌면|

배달 위치는 배달 후 실행 되는 정책 및 검색의 결과를 표시 합니다. 배달 작업에 연결 됩니다. 이 필드는 문제 메일을 찾은 경우 수행 되는 작업에 대 한 통찰력을 제공 하기 위해 추가 되었습니다. 배달 위치의 가능한 값은 다음과 같습니다.

- **받은 편지함 또는 폴더**: 전자 메일이 받은 편지함 또는 폴더 (전자 메일 규칙에 따라)에 있습니다.
- **온-프레미스 또는 external**: 사서함이 클라우드에는 없지만 온-프레미스에 있는 경우
- **정크 폴더**: 전자 메일이 사용자의 정크 메일 폴더에 있습니다.
- **지운 편지함 폴더**: 사용자의 지운 편지함 폴더에 있는 전자 메일입니다.
- **격리**: 사용자의 사서함에 없는 전자 메일 격리
- **실패**: 전자 메일이 사서함에 연결 하지 못했습니다.
- **삭제**됨: 메일 흐름의 어딘가에 메일이 손실 됩니다.

### <a name="email-timeline"></a>전자 메일 시간 표시 막대

**전자 메일 시간 표시 막대** 는 관리자에 게 더 적합 한 사냥 환경을 구현 하기 위한 또 다른 새로운 탐색기 기능입니다. 다른 위치를 확인 하는 데 소요 되는 시간이 감소 하 여 이벤트를 이해 하기 위해 임의 시간에 대해 자세히 설명 합니다. 전자 메일에서 여러 이벤트가 발생 하거나 같은 시간에 발생할 경우 해당 이벤트가 시간 표시 막대 보기에 표시 됩니다. 실제로 메일에 대해 배달이 발생 하는 일부 이벤트는 ' 특수 동작 ' 열에 캡처됩니다. 해당 메일의 시간 표시줄에 있는 정보를 메일 발송에 대해 수행 된 특수 작업과 함께 사용 하면 관리자가 정책이 작동 하는 방식, 메일을 최종적으로 라우팅된 위치, 그리고 경우에 따라 최종 평가가 수행 된 방식을 파악할 수 있습니다.

악성 전자 메일 메시지를 조사 하는 방법에 대 한 자세한 내용은 [Office 365에서 제공 된 악성 전자 메일 조사 및 재구성](investigate-malicious-email-that-was-delivered.md)을 참조 하십시오.

### <a name="export-url-click-data"></a>URL 내보내기 데이터 클릭

또한 이제는 URL 클릭에 대 한 보고서를 Microsoft Excel로 내보내 해당 네트워크 메시지 ID를 확인 하 고, 결과 클릭 하 여 URL이 더 쉽게 전송 되는 위치를 이해 하는 작업을 수행할 수 있습니다. 작동 방식은 다음과 같습니다. Office 365 빠른 실행의 위협 관리에서이 체인을 통해를 클릭 합니다.

**탐색기** \> **피싱 보기** \> **클릭** \> 상위 **url 또는 위쪽 Url 클릭** \> **임의의 레코드를 클릭 하 여 URL 플라이 아웃을 엽니다** .

목록에서 URL을 클릭 하면 플라이 아웃 패널에 새 내보내기 단추가 표시 됩니다. 이 단추를 사용 하 여 데이터를 보다 쉽게 보고 하도록 Excel 스프레드시트로 이동 합니다.

실시간 검색 보고서의 동일한 위치를 다음과 같이 가져올 수 있습니다.

**탐색기** \> **실시간 검색** \> **피싱 보기** \> **Url** \> **상위 url 또는 위쪽 클릭** \> **임의의 레코드를 클릭 하 여 URL 플라이 아웃** \> 을 엽니다. **클릭 탭으로 이동 합니다.**

> [!TIP]
> Network Message ID는 네트워크 메시지 ID를 통해 탐색기나 연결 된 타사 도구를 검색할 때 클릭을 특정 메일에 다시 매핑합니다. 네트워크 메시지 ID를 통해 검색 하면 관리자가 클릭 결과와 연결 된 특정 전자 메일을 제공 합니다. 내보낼 때 네트워크 메시지 ID의 일치 확인을 통해 더 빠르고 강력한 분석이 가능 합니다.

> [!div class="mx-imgBorder"]
> ![탐색기의 클릭 탭](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a>기술 별로 전자 메일에서 발견 된 맬웨어를 참조 하세요.

Microsoft 365 기술을 통해 전자 메일로 검색 된 맬웨어를 확인 하려는 경우를 가정해 보겠습니다. 이 작업을 수행 하려면 [전자 메일 > 맬웨어](threat-explorer-views.md#email--malware) 보기 Explorer (또는 실시간 검색)를 사용 합니다.

1. 보안 & 준수 센터 ()에서 [https://protection.office.com](https://protection.office.com) **Threat management**  >  **Explorer** (또는 **실시간**검색)를 선택 합니다. (이 예제에서는 탐색기를 사용 합니다.)

2. **보기** 메뉴에서 **전자 메일**  >  **맬웨어**를 선택 합니다.

   > [!div class="mx-imgBorder"]
   > ![탐색기에 대 한 보기 메뉴](../../media/ExplorerViewEmailMalwareMenu.png)

3. **보낸 사람**을 클릭 한 다음 **기본**  >  **검색 기술을**선택 합니다.

   이제 검색 기술을 보고서에 대 한 필터로 사용할 수 있습니다.

   > [!div class="mx-imgBorder"]
   > ![맬웨어 검색 기술](../../media/ExplorerEmailMalwareDetectionTech.png)

4. 옵션을 선택한 다음 **새로 고침** 단추를 클릭 하 여 해당 필터를 적용 합니다.

   > [!div class="mx-imgBorder"]
   > ![선택한 검색 기술](../../media/ExplorerEmailMalwareDetectionTechATP.png)

선택한 기술 옵션을 사용 하 여 전자 메일로 검색 된 결과 맬웨어가 표시 되도록 보고서가 새로 고쳐집니다. 여기서는 추가 분석을 수행할 수 있습니다.

## <a name="view-data-about-phishing-urls-and-click-verdict"></a>피싱 Url에 대 한 데이터를 확인 하 고 결과를 클릭 합니다.

허용, 차단 및 재정의 된 Url 목록을 비롯 하 여 전자 메일의 Url을 통한 피싱 시도를 확인 하려는 경우를 가정해 봅니다. 클릭 한 Url을 식별 하려면 [안전한 링크](atp-safe-links.md) 를 구성 해야 합니다. 클릭 시간 보호에 대 한 [안전한 링크 정책을](set-up-atp-safe-links-policies.md) 설정 해야 하며 안전한 링크를 클릭 하 여 verdicts을 클릭할 수 있습니다.

메시지에서 피싱 Url을 검토 하 고 피싱 메시지의 Url을 클릭 하려면 [전자 메일 > 피싱](threat-explorer-views.md#email--phish) Explorer 보기 (실시간 검색)를 사용 합니다.

1. 보안 & 준수 센터 ()에서 [https://protection.office.com](https://protection.office.com) **Threat management**  >  **Explorer** (또는 **실시간**검색)를 선택 합니다. (이 예제에서는 탐색기를 사용 합니다.)

2. **보기** 메뉴에서 **전자 메일**  >  **피싱**을 선택 합니다.

   > [!div class="mx-imgBorder"]
   > ![탐색기에 대 한 보기 메뉴](../../media/ExplorerViewEmailPhishMenu.png)

3. **보낸 사람**을 클릭 한 다음 **url**을 선택  >  합니다**결과를 클릭**합니다.

4. **차단** 됨 및 **무시 된 블록과**같은 옵션을 하나 이상 선택 하 고 해당 필터를 적용 하는 옵션과 같은 줄에 있는 **새로 고침** 단추를 클릭 합니다. (브라우저 창을 새로 고치지 않습니다.)

   > [!div class="mx-imgBorder"]
   > ![Url을 선택 하 고 verdicts을 클릭 합니다.](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

   보고서를 새로 고치면 보고서 아래의 URL 탭에 서로 다른 두 개의 URL 테이블이 표시 됩니다.

   - **상위 url** 은 필터링 된 메시지에 포함 된 url 및 각 URL에 대 한 전자 메일 배달 작업 수입니다. 피싱 전자 메일 보기에서 일반적으로이 목록에는 합법적인 Url이 포함 됩니다. 공격자는 메시지에 효과적이 고 잘못 된 Url을 함께 사용 하 여 배달 하려고 할 수 있지만, 사용자가 클릭 하는 데 더 흥미로운 악성 링크를 만들 수 있습니다. Url의 테이블은 총 전자 메일 수로 정렬 되지만 보기를 단순하게 하기 위해이 열이 숨겨집니다.

   - **위쪽** 클릭은 클릭 한 안전한 링크 래핑된 url이 총 클릭 횟수에 따라 정렬 되며 보기를 단순화 하기 위해이 열도 표시 되지 않습니다. 총 개수 열에서 안전한 링크를 나타냅니다. 클릭 한 각 URL에 대해 결과 count를 클릭 합니다. 피싱 email (전자 메일 보기)에서 이러한 메시지는 일반적으로 의심 되거나 악성 Url 이지만 위협이 아닌 Url을 포함할 수 있지만 피싱 메시지가 있습니다. 래핑 해제 한 링크의 URL 클릭은 여기에 표시 되지 않습니다.

   두 개의 URL 테이블은 배달 작업 및 위치로 피싱 전자 메일 메시지의 상위 Url을 표시 하 고, 사용자가 사용자와 상호 작용 한 잘못 된 링크를 확인할 수 있도록 차단 된 (또는 경고에 따라 방문) URL 클릭을 보여 줍니다. 여기서는 추가 분석을 수행할 수 있습니다. 예를 들어 차트 아래에서 조직의 환경에서 차단 된 전자 메일 메시지의 최상위 Url을 볼 수 있습니다.

   > [!div class="mx-imgBorder"]
   > ![차단 된 탐색기 Url](../../media/ExplorerPhishClickVerdictURLs.png)

   자세한 정보를 보려면 URL을 선택 합니다.

   > [!NOTE]
   > URL 플라이 아웃 대화 상자에서 전자 메일 메시지에 대 한 필터링이 제거 되어 사용자 환경에 표시 되는 URL의 전체 보기를 보여 줍니다. 이를 통해 탐색기의 전자 메일 메시지를 관심 있는 항목으로 필터링 하 고, 잠재적인 위협이 되는 특정 Url을 찾은 다음, url 필터 대화 상자를 통해 해당 환경의 URL 노출에 대 한 이해를 탐색기 보기 자체에 추가 하지 않아도 됩니다.

### <a name="interpretation-of-different-click-verdicts"></a>다른 클릭 verdicts 해석

전자 메일 또는 URL flyouts에서 위쪽 클릭을 비롯 하 여 필터링 환경 내에서 찾기 환경의 일부로 다른 클릭 값이 표시 됩니다. 다음은 Verdicts 클릭 가능한 값과 해석 방법입니다.

- **없음**: URL에 대 한 결과를 캡처할 수 없습니다. 사용자가 URL을 클릭 했을 수 있습니다.
- **허용**: 사용자가 URL로 이동할 수 있습니다.
- **차단 됨**: 사용자가 URL로 이동할 수 없도록 차단 되었습니다.
- **보류 중인 결과**: 사용자에 게 샌드 박싱 Pending 페이지와 함께 제공 됩니다.
- **차단 된 재정의**: 사용자가 URL로 이동할 수 없도록 차단 되었습니다. 그러나 사용자가이 블록에서 URL로 이동 하는 것을 중단 했습니다.
- **결과 바이패스 보류**: 사용자에 게 샌드 박싱 페이지와 함께 제공 됩니다. 그러나 사용자가 페이지를 제거 하 여 URL로 이동할 수 있습니다.
- **오류**: 사용자에 게 오류 페이지가 표시 됩니다. 또한 결과를 캡처하는 중에 오류가 발생 했을 수 있습니다.
- **실패**: 결과를 캡처하는 동안 알 수 없는 예외가 발생 했습니다. 사용자가 URL을 클릭 했을 수 있습니다.

## <a name="review-email-messages-reported-by-users"></a>사용자가 보고 한 전자 메일 메시지 검토

조직의 사용자가 [outlook 및 웹용 outlook에 대 한 보고서 메시지 추가 기능](enable-the-report-message-add-in.md)을 사용 하 여 정크 메일 또는 피싱이 아닌 메시지를 보고 한다고 가정 합니다. 이 작업을 수행 하려면 [전자 메일 > 전송](threat-explorer-views.md#email--submissions) Explorer (또는 실시간 검색)를 사용 합니다.

1. 보안 & 준수 센터 ()에서 [https://protection.office.com](https://protection.office.com) **Threat management**  >  **Explorer** (또는 **실시간**검색)를 선택 합니다. (이 예제에서는 탐색기를 사용 합니다.)

2. **보기** 메뉴에서 **전자 메일**  >  **제출을**선택 합니다.

   > [!div class="mx-imgBorder"]
   > ![탐색기에 대 한 보기 메뉴](../../media/explorer-view-menu-email-user-reported.png)

3. **보낸 사람**을 클릭 한 다음 **기본**  >  **보고서 유형을**선택 합니다.

4. **피싱**등의 옵션을 선택 하 고 **새로 고침** 단추를 클릭 합니다.

   > [!div class="mx-imgBorder"]
   > ![사용자가 보고 한 피싱](../../media/EmailUserReportedReportType.png)

보고서가 새로 고쳐지고 조직의 사용자가 피싱 시도로 보고 한 전자 메일 메시지에 대 한 데이터가 표시 됩니다. 이 정보를 사용 하 여 추가 분석을 수행 하 고, 필요한 경우 [ATP 피싱 방지 정책을](configure-atp-anti-phishing-policies.md)조정할 수 있습니다.

## <a name="start-automated-investigation-and-response"></a>자동 조사 및 응답 시작

> [!NOTE]
> 자동화 된 조사 및 응답 기능은 **office 365 ATP 계획 2** 및 **Office 365 E5**에서 사용할 수 있습니다.

(새로운 방법!) [자동화 된 조사 및 응답](automated-investigation-response-office.md) 을 통해 보안 운영 팀이 고 사이버 공격을 조사 및 완화할 때 필요한 시간과 노력을 많이 절감할 수 있습니다. 보안 playbook 트리거될 수 있는 알림을 구성 하는 것 외에도 탐색기의 보기에서 자동화 된 조사 및 응답 프로세스를 시작할 수 있습니다.

이에 대 한 자세한 내용은 [예제: 보안 관리자가 탐색기에서 조사를 트리거하는 예](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)를 참조 하십시오.

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a>Explorer (또는 실시간 검색)를 사용 하는 여러 방법

이 문서에서 설명 하는 시나리오 외에도 Explorer (또는 실시간 검색)에서 사용할 수 있는 보고 옵션이 더 많이 있습니다.

- [배달된 악성 전자 메일 찾기 및 조사](investigate-malicious-email-that-was-delivered.md)
- [위협 방지 상태 보고서](view-email-security-reports.md#threat-protection-status-report)
- [위협 탐색기 및 실시간 검색의 보기에 대 한 개요 보기](threat-explorer-views.md)
- [Microsoft Threat Protection의 자동화된 조사 및 대응](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

## <a name="required-licenses-and-permissions"></a>필수 라이선스 및 사용 권한

Explorer 또는 실시간 검색을 하려면 [Office 365 ATP](office-365-atp.md) 가 있어야 합니다.

- Explorer는 Office 365 ATP 계획 2에 포함 되어 있습니다.
- 실시간 검색 보고서는 Office 365 ATP 계획 1에 포함 되어 있습니다.
- Office 365 ATP로 보호 해야 하는 모든 사용자에 대해 라이선스를 할당 하도록 계획 합니다. (탐색기 또는 실시간 검색은 사용이 허가 된 사용자에 대 한 검색 데이터를 표시 합니다.)

탐색기 또는 실시간 검색을 보고 사용 하려면 보안 관리자 또는 보안 판독기에 부여 된 것과 같은 적절 한 사용 권한이 있어야 합니다.

- 보안 &amp; 및 준수 센터에는 다음 역할 중 하나가 할당 되어 있어야 합니다.

  - 조직 관리
  - 보안 관리자 (Azure Active Directory 관리 센터에서 할당할 수 [https://aad.portal.azure.com](https://aad.portal.azure.com) 있음)
  - 보안 읽기 권한자

- Exchange Online의 경우 Exchange 관리 센터 ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) 또는 PowerShell cmdlet ( [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)참조)에서 다음 역할 중 하나를 할당 받아야 합니다.

  - 조직 관리
  - 보기 전용 조직 관리
  - 보기 권한만 있는 받는 사람 역할
  - 준수 관리

역할 및 사용 권한에 대 한 자세한 내용은 다음 리소스를 참조 하십시오.

- [보안 및 준수 센터의 사용 권한 &amp;](permissions-in-the-security-and-compliance-center.md)
- [Exchange Online의 기능 사용 권한](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="some-differences-between-threat-explorer-and-real-time-detections"></a>위협 탐색기와 실시간 감지 간의 약간의 차이점

- **실시간** 검색 보고서는 OFFICE 365 atp 계획 1에서 사용할 수 있지만, **Threat Explorer** 는 office 365 atp 계획 2에서 사용할 수 있습니다.
- **실시간** 검색 보고서를 사용 하면 검색을 실시간으로 확인할 수 있습니다. **위협 탐색기** 도이를 수행 하지만 지정 된 공격에 대 한 추가 세부 정보를 볼 수도 있습니다.
- **모든 전자 메일** 보기는 **위협 탐색기** 에서 사용할 수 있으며 **실시간** 검색 보고서에는 없습니다.
- **위협 탐색기**에는 추가 필터링 기능 및 사용 가능한 작업이 포함 되어 있습니다.

자세한 내용은 [Office 365 Atp 서비스 설명: atp (Advanced Threat Protection) 계획에서의 기능 사용 가능 여부](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)를 참조 하세요.
