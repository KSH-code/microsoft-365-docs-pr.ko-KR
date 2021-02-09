---
title: 위협 탐색기 및 실시간 검색
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 보안 준수 센터의 탐색기 및 실시간 검색을 사용하여 위협을 효율적으로 조사하고 &amp; 대응합니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3c07ea4a44eb965ab6df834260c9dcef6e79c02a
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142328"
---
# <a name="threat-explorer-and-real-time-detections"></a>위협 탐색기 및 실시간 검색


**적용 대상**
- [Microsoft Defender for Office 365 요금제 1 및 계획 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

조직에 [Microsoft Defender for Office 365가](office-365-atp.md) [](#required-licenses-and-permissions)있으며 필요한 권한이 있는 경우  **탐색기** 또는 실시간 검색(이전의 실시간 [](#new-features-in-threat-explorer-and-real-time-detections)보고서 *)* 중 하나를 사용할 수 있습니다. 새로운 기능 확인 보안 & 준수 센터에서 **위협** 관리로 이동한 다음 **탐색기**  또는 실시간 검색을 **선택 합니다.**


|Microsoft Defender for Office 365 요금제 2를 사용하면 다음을 볼 수 있습니다.|Microsoft Defender for Office 365 요금제 1을 사용하면 다음이 볼 수 있습니다.|
|---|---|
|![위협 탐색기](../../media/threatmgmt-explorer.png)|![실시간 탐지](../../media/threatmgmt-realtimedetections.png)|
|

탐색기 또는 실시간 검색은 보안 운영 팀이 위협을 효율적으로 조사하고 대응하는 데 도움이 됩니다. 보고서는 다음 이미지와 같습니다.

![위협 관리 \> 탐색기로 이동](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

이 보고서를 사용하여 다음을 할 수 있습니다.

- [Microsoft 365 보안 기능에서 검색된 맬웨어 보기](#see-malware-detected-in-email-by-technology)
- [피싱 URL 보기 및 판정 데이터 클릭](#view-phishing-url-and-click-verdict-data)
- [탐색기 보기에서](#start-automated-investigation-and-response) 자동화된 조사 및 응답 프로세스 시작(Office 365 계획 2용 Defender만 해당)
- [악성 전자 메일 조사 등](#more-ways-to-use-explorer-and-real-time-detections)

## <a name="improvements-to-threat-explorer-and-real-time-detections"></a>위협 탐색기 및 실시간 검색 개선

### <a name="tags-in-threat-explorer"></a>위협 탐색기에서 태그

> [!NOTE]
> 사용자 태그 기능은 *미리* 보기에 있으며 모든 사용자가 사용할 수 있으며 변경될 수 있습니다. 릴리스 일정에 대한 자세한 내용은 Microsoft 365 로드맵을 참조하십시오.

사용자 태그는 Office 365용 Microsoft Defender의 특정 사용자 그룹을 식별합니다. 라이선스 및 구성을 비롯한 태그에 대한 자세한 내용은 [사용자 태그를 참조하세요.](user-tags.md)

위협 탐색기에서 다음 환경의 사용자 태그에 대한 정보를 볼 수 있습니다.

#### <a name="email-grid-view"></a>전자 메일 그리드 보기

전자 **메일 그리드의** 태그 열에는 보낸 사람 또는 받는 사람 사서함에 적용된 모든 태그가 포함되어 있습니다. 기본적으로 우선 순위 계정과 같은 시스템 태그가 먼저 표시됩니다.

> [!div class="mx-imgBorder"]
> ![전자 메일 그리드 보기에서 태그 필터링](../../media/tags-grid.png)

#### <a name="filtering"></a>필터링

태그를 필터로 사용할 수 있습니다. 우선 순위 계정 또는 특정 사용자 태그 시나리오에서만 헌트 특정 태그가 있는 결과를 제외할 수도 있습니다. 이 기능을 다른 필터와 결합하여 조사 범위를 좁힐 수 있습니다.

[![필터 태그](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)

> [!div class="mx-imgBorder"]
> ![태그 필터링 안](../../media/tags-filter-not.png)

#### <a name="email-detail-flyout"></a>전자 메일 세부 정보 플라이아웃
보낸 사람 및 받는 사람에 대한 개별 태그를 확인하려면 제목을 선택하여 메시지 세부 정보 플라이아웃을 열 수 있습니다. 요약 **탭에서** 보낸 사람 및 받는 사람 태그가 전자 메일에 대해 표시되는 경우 별도로 표시됩니다.
보낸 사람 및 받는 사람에 대한 개별 태그에 대한 정보도 내보낼 CSV 데이터로 확장되어 두 개의 개별 열에서 이러한 세부 정보를 볼 수 있습니다.

> [!div class="mx-imgBorder"]
> ![전자 메일 세부 정보 태그](../../media/tags-flyout.png)

태그 정보는 URL 클릭 플라이아웃에도 표시됩니다. 이 보기를 보려면 피싱 또는 모든 전자 메일 보기로 이동한 다음 **URL** 또는 **URL 클릭 탭으로** 이동하십시오. 개별 URL 플라이아웃을 선택하여 해당 클릭에 연결된 태그를 포함하여 해당 URL의 클릭에 대한 추가 세부 정보를 볼 수 있습니다.

> [!div class="mx-imgBorder"]
> ![URL 태그](../../media/tags-urls.png)

## <a name="improvements-to-the-threat-hunting-experience-upcoming"></a>위협 헌팅 환경 개선(예정)

### <a name="updated-threat-information-for-emails"></a>전자 메일에 대한 위협 정보 업데이트

당사는 전자 메일 레코드에 대한 데이터 정확도와 일관성을 높이기 위해 플랫폼 및 데이터 품질 개선에 중점을 두어 왔다. 향상된 기능으로는 ZAP 프로세스의 일부로 전자 메일에서 실행되는 작업과 같은 배달 전 정보와 배달 후 정보를 단일 레코드로 통합하는 작업이 포함됩니다. 스팸 판정, 엔터티 수준 위협(예: 악의적인 URL) 및 최신 배달 위치와 같은 추가 세부 정보도 포함됩니다.

이러한 업데이트 후 메시지에 영향을 주는 다양한 배달 후 이벤트에 관계없이 각 메시지에 대한 단일 항목이 표시됩니다. 작업에는 ZAP, 수동 수정(관리자 작업), 동적 배달 등을 포함할 수 있습니다.

맬웨어 및 피싱 위협을 표시하는 것 외에도 전자 메일과 관련된 스팸 판정이 있습니다. 전자 메일 내에서 해당 검색 기술과 함께 전자 메일과 관련된 모든 위협을 참조하세요. 전자 메일에는 0, 1 또는 여러 위협이 있을 수 있습니다. 전자 메일 플라이아웃의 **세부** 정보 섹션에 현재 위협이 표시됩니다. 맬웨어 및 피싱과 같은 여러  위협에 대한 검색 기술 필드에는 위협을 식별한 감지 기술인 위협 감지 매핑이 표시될 수 있습니다.

이제 다양한 검색 기술에는 새로운 검색 방법과 스팸 감지 기술이 포함되어 있습니다. 동일한 검색 기술 집합을 사용하여 여러 전자 메일 보기(맬웨어, 피싱, 모든 전자 메일)에서 결과를 필터링할 수 있습니다.

> [!NOTE]
> 결과 분석이 반드시 엔터티에 연결되지 않을 수도 있습니다. 예를 들어 전자 메일은 피싱 또는 스팸으로 분류될 수 있지만 피싱/스팸 판정으로 스탬프 처리된 URL은 없습니다. 이는 필터가 결과를 할당하기 전에 전자 메일의 콘텐츠 및 기타 세부 정보도 평가하기 때문에입니다.

#### <a name="threats-in-urls"></a>URL의 위협

이제 전자 메일 플라이아웃 세부 정보 탭에서 URL에 대한 특정 위협을 볼 **수** 있습니다. 위협은  *맬웨어,* *피싱, 스팸* 또는 *없음일 수* 있습니다.

> [!div class="mx-imgBorder"]
> ![URL 위협](../../media/URL_Threats.png)

### <a name="updated-timeline-view-upcoming"></a>업데이트된 시간 표시 막대 보기(예정된)

> [!div class="mx-imgBorder"]
> ![업데이트된 시간 표시 막대 보기](../../media/Email_Timeline.png)

시간 표시 막대 보기는 모든 배달 및 배달 후 이벤트를 식별합니다. 여기에는 이러한 이벤트의 하위 집합에 대해 해당 시점에 식별된 위협에 대한 정보가 포함됩니다. 시간 표시 막대 보기는 추가 작업(예: ZAP 또는 수동 수정)에 대한 정보와 해당 작업의 결과도 제공합니다. 시간 표시 막대 보기 정보에는 다음이 포함됩니다.

- **원본:** 이벤트의 원본입니다. 관리자/시스템/사용자일 수 있습니다.
- **이벤트:** 원본 배달, 수동 수정, ZAP, 제출 및 동적 배달과 같은 최상위 이벤트를 포함합니다.
- **작업:** ZAP 또는 관리자 작업의 일부로 수행된 특정 작업(예: 소프트 삭제)입니다.
- **위협:** 이 시점에서 식별된 위협(맬웨어, 피싱, 스팸)을 다 표시합니다.
- **결과/세부 정보:** 작업의 결과에 대한 자세한 정보(예: ZAP/관리자 작업의 일부로 수행 여부)

### <a name="original-and-latest-delivery-location"></a>원본 및 최신 배달 위치

현재 전자 메일 그리드 및 전자 메일 플라이아웃에 배달 위치가 표시됩니다. 배달 **위치 필드의** 이름을 원래 배달 위치 **_로 _변경합니다._*또한 다른 필드인 _* 최신 배달 _위치가 도입됩니다._**

**원래 배달 위치는** 처음에 전자 메일이 배달된 위치에 대한 자세한 정보를 제공합니다. **최신 배달 위치는** *ZAP와* 같은 시스템 작업 또는 삭제된 항목으로 이동과 같은 관리자 작업 후 전자 메일이 전송된 *위치를 알 수 있습니다.* 최신 배달 위치는 메시지의 배달 후 또는 시스템/관리자 작업을 관리자에게 알려 주기 위한 것입니다. 전자 메일에 대한 최종 사용자 작업은 포함하지 않습니다. 예를 들어 사용자가 메시지를 삭제하거나 메시지를 보관/pst로 이동한 경우 메시지 "배달" 위치가 업데이트되지 않습니다. 그러나 시스템 작업이 위치를 업데이트한 경우(예: ZAP로 인해 전자 메일이  검소로 이동) 최신 배달 위치는 "quarantine"으로 표시됩니다.

> [!div class="mx-imgBorder"]
> ![업데이트된 배달 위치](../../media/Updated_Delivery_Location.png)

> [!NOTE]
> 배달 위치 및  배달 작업이  "알 수 없음"으로 표시될 수 있는 경우도 있습니다.
>
> - 메시지가 배달된 경우 배달 위치가 "배달" 및 배달 위치를 "알 수 없음"으로 표시될 수 있지만 받은 편지함 규칙은 메시지를 받은 편지함 또는 정크 메일 폴더 대신 기본 폴더(예: 임시 또는 보관함)로 이동했습니다.  
>
> - **관리자/시스템** 작업(예: ZAP)을 시도했지만 메시지를 찾을 수 없는 경우 최신 배달 위치를 알 수 없습니다. 일반적으로 이 작업은 사용자가 메시지를 이동하거나 삭제한 후에 수행됩니다. 이러한 경우 시간 표시 막대 보기에서 **결과/세부 정보** 열을 확인해야 합니다. "사용자가 이동하거나 삭제한 메시지"라는 문을 찾아 봐야 합니다.

> [!div class="mx-imgBorder"]
> ![시간 표시 막대의 배달 위치](../../media/Updated_Timeline_Delivery_Location.png)

### <a name="additional-actions"></a>추가 작업

*전자 메일을 배달한* 후 추가 작업이 적용되었습니다. 여기에는 *ZAP,*  수동 수정(즉, 관리자가 수행한 작업(예: 소프트  *삭제),* 동적 배달 및 다시 처리(소급적으로 좋은 것으로 감지된 전자 메일)가 포함됩니다.

> [!NOTE]
> - 보류 중인 변경 내용의 일부로 현재 배달 작업 필터에 표시되어 있는 "ZAP에서 제거됨" 값이 제거됩니다. 추가 작업을 통해 ZAP 시도가 있는 모든 전자 메일을 검색할 **수 있습니다.**
>
> - 검색 기술 및 추가  작업(특히  ZAP 시나리오의 경우)에 대한 새 필드와 값이 있습니다. 기존 저장된 쿼리 및 추적된 쿼리를 평가하여 새 값으로 작동할 수 있도록 해야 합니다.

> [!div class="mx-imgBorder"]

> ![탐색기에서 추가 작업](../../media/Additional_Actions.png)

### <a name="system-overrides"></a>시스템 오버라이드

*시스템 다시 설정을 사용하면* 메시지의 의도된 배달 위치에 대한 예외를 만들 수 있습니다. 필터링 스택으로 식별된 위협 및 기타 검색에 따라 시스템에서 제공하는 배달 위치를 다시 정합니다. 시스템 오버라이드는 테넌트 또는 사용자 정책을 통해 정책에서 제안한 메시지를 배달하도록 설정할 수 있습니다. 다시미는 사용자가 설정한 과도하게 광범위한 수신 -보낸 사람 정책과 같은 구성 간격으로 인해 의도하지 않은 악성 메시지 배달을 식별할 수 있습니다. 이러한 은(는) 다음 값이 될 수 있습니다.

- 사용자 정책에서 허용: 사용자는 사서함 수준에서 도메인 또는 보낸 사람이 허용하는 정책을 만듭니다.
- 사용자 정책에 의해 차단: 사용자는 메일 상자 수준에서 도메인 또는 보낸 사람 차단 정책을 만듭니다.
- 조직 정책에서 허용: 조직의 보안 팀은 조직의 사용자에 대해 보낸 사람 및 도메인을 허용하도록 정책 또는 Exchange 메일 흐름 규칙(전송 규칙)을 설정합니다. 사용자 집합 또는 전체 조직에 사용할 수 있습니다.
- 조직 정책에 의해 차단: 조직의 보안 팀은 정책 또는 메일 흐름 규칙을 설정하여 조직의 사용자에 대한 보낸 사람, 도메인, 메시지 언어 또는 원본 IPS를 차단합니다. 이 설정은 사용자 집합 또는 전체 조직에 적용할 수 있습니다.
- 조직 정책에 의해 차단된 파일 확장명: 조직의 보안 팀이 맬웨어 방지 정책 설정을 통해 파일 이름 확장명을 차단합니다. 이제 조사에 도움이 될 수 있도록 이러한 값이 전자 메일 세부 정보로 표시됩니다. Secops 팀은 다양한 필터링 기능을 사용하여 차단된 파일 확장명을 필터링할 수도 있습니다.

[![탐색기에서 시스템 오버라이드](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)

> [!div class="mx-imgBorder"]
> ![탐색기에서 시스템 눈금을 오버라이드](../../media/System_Overrides_Grid.png)

### <a name="improvements-for-the-url-and-clicks-experience"></a>URL 및 클릭 환경 개선

개선된 기능으로는 다음이 포함됩니다.

- URL 플라이아웃의 **Clicks** 섹션에 전체 클릭된 URL(URL의 일부인 쿼리 매개 변수 포함)을 보여 줄 수 있습니다. 현재 URL 도메인 및 경로는 제목 표시줄에 표시됩니다. 전체 URL을 표시하기 위해 해당 정보를 확장하고 있습니다.

- URL  *필터(URL과* URL 도메인 및 경로의 픽스): 업데이트는 URL/클릭 결과를 포함하는 메시지 검색에 영향을 미치게 됩니다. 프로토콜에 무관한 검색에 대한 지원을 사용하도록 설정했습니다. 따라서 를 사용하지 않고도 URL을 검색할 수 `http` 있습니다. 다른 값이 명시적으로 지정되지 않은 경우 기본적으로 URL 검색은 http에 매핑됩니다. 예:

   -  URL, URL 도메인 및 URL 도메인 및 경로 필터 필드에 있는 주소와 없이 `http://` 검색합니다.    검색에서 동일한 결과를 표시해야 합니다.

   -  `https://`URL에서 prefix를 **검색합니다.** 값을 지정하지 않으면 `http://` 전제가 됩니다.

   - `/`는 URL 경로, **URL** 도메인, **URL** 도메인 및 경로 필드의 시작과 끝에서 **무시됩니다.** `/` URL 필드의 끝에 있는 **것은** 무시됩니다.

### <a name="phish-confidence-level"></a>피싱 지수

피싱 신뢰 수준은 전자 메일이 "피싱"으로 분류된 신뢰 수준을 식별하는 데 도움이 됩니다. 가능한 두 값은 *높음과* *보통입니다.* 초기 단계에서 이 필터는 위협 탐색기 피싱 보기에서만 사용할 수 있습니다.

[![탐색기에서 피싱 지수](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)

### <a name="zap-url-signal"></a>ZAP URL 신호

ZAP URL 신호는 일반적으로 전자 메일이 피싱으로 식별되고 배달 후 제거된 ZAP 피싱 경고 시나리오에 사용됩니다. 이 신호는 경고를 탐색기에서 해당 결과와 연결합니다. 경고에 대한 IOC 중 하나입니다.

헌팅 프로세스를 개선하기 위해 헌팅 환경의 일관성을 높이기 위해 위협 탐색기 및 실시간 검색을 업데이트했습니다. 변경 내용은 다음과 같이 간략하게 설명됩니다.

- [개선된 시간제](#timezone-improvements)
- [새로 고침 프로세스에서 업데이트](#update-in-the-refresh-process)
- [필터에 추가할 차트 드릴다운](#chart-drilldown-to-add-to-filters)
- [제품 정보 업데이트](#in-product-information-updates)

### <a name="filter-by-user-tags"></a>사용자 태그로 필터링

이제 시스템 또는 사용자 지정 사용자 태그를 정렬하고 필터링하여 위협 범위를 빠르게 파악할 수 있습니다. 자세한 내용은 [사용자 태그를 참조합니다.](user-tags.md)

> [!IMPORTANT]
> 사용자 태그별 필터링 및 정렬은 현재 공개 미리 보기에 있습니다. 이 기능은 상업적으로 출시되기 전에 상당수 수정될 수 있습니다. Microsoft는 해당 정보에 대해 제공된 정보에 대해 표현적 또는 암시적 보증을하지 않습니다.

![탐색기에서 태그 열](../../media/threat-explorer-tags.png)

### <a name="timezone-improvements"></a>개선된 시간제

내보낼 데이터뿐만 아니라 포털의 전자 메일 레코드에 대한 표준 시간대가 볼 수 있습니다. 전자 메일 그리드, 세부 정보 플라이아웃, 전자 메일 타임라인 및 유사한 전자 메일과 같은 환경 전체에서 표시될 것이기 때문에 결과 집합의 표준 시간대가 명확합니다.

> [!div class="mx-imgBorder"]
> ![탐색기에서 표준 시간대 보기](../../media/TimezoneImprovements.png)

### <a name="update-in-the-refresh-process"></a>새로 고침 프로세스에서 업데이트

일부 사용자는 자동 새로 고침(예: 날짜를 변경하는 즉시 페이지가 새로 고쳐지기) 및 수동 새로 고침(다른 필터의 경우)과 혼동하는 것을 설명했습니다. 마찬가지로 필터를 제거하면 자동 새로 고침이 수행됩니다. 쿼리를 수정하는 동안 필터를 변경하면 검색 환경이 불일치할 수 있습니다. 이러한 문제를 해결하기 위해 수동 필터링 메커니즘으로 이동하고 있습니다.

환경 관점에서 사용자는 다양한 필터 범위(필터 집합 및 날짜)를 적용 및 제거하고 새로 고침 단추를 선택하여 쿼리를 정의한 후 결과를 필터링할 수 있습니다. 이제 화면에서 새로 고침 단추도 강조 표시됩니다. 관련 도구 설명 및 제품 내 설명서도 업데이트되었습니다.

> [!div class="mx-imgBorder"]
> ![새로 고침을 선택하여 결과 필터링](../../media/ManualRefresh.png)

### <a name="chart-drilldown-to-add-to-filters"></a>필터에 추가할 차트 드릴다운

이제 범례 값을 차트에 필터로 추가할 수 있습니다. 새로 **고침 단추를** 선택하여 결과를 필터링합니다.

> [!div class="mx-imgBorder"]
> ![차트를 드릴다운하여 필터링](../../media/ChartDrilldown.png)

### <a name="in-product-information-updates"></a>제품 내 정보 업데이트

이제 제품 내에서 표 내의 총 검색 결과 수와 같은 추가 세부 정보를 사용할 수 있습니다(아래 참조). 필터, 검색 환경 및 결과 집합에 대한 자세한 정보를 제공하기 위해 레이블, 오류 메시지 및 도구 탐색이 개선되어 있습니다.

> [!div class="mx-imgBorder"]
> ![제품 내 정보 보기](../../media/ProductInfo.png)

## <a name="extended-capabilities-in-threat-explorer"></a>위협 탐색기에서 확장된 기능

### <a name="top-targeted-users"></a>상위 대상 사용자

오늘은 전자 메일에 대한 맬웨어 보기의 상위 맬웨어  패밀리 섹션에 상위 대상 사용자 목록을 노출합니다. 피싱 및 모든 전자 메일 보기에서 이 보기를 확장할 것입니다. 상위 5개 대상 사용자와 해당 보기에 대한 각 사용자에 대한 시도 횟수를 볼 수 있습니다. 예를 들어 피싱 보기의 경우 피싱 시도 횟수가 표시됩니다.

각 전자 메일 보기에 대한 오프라인 분석 시도 횟수와 함께 최대 3,000명까지 대상 사용자 목록을 내보낼 수 있습니다. 또한 시도 횟수(예: 아래 이미지에서 13회 시도)를 선택하면 위협 탐색기에서 필터링된 보기가 열리기 때문에 해당 사용자의 전자 메일 및 위협에 대한 더 많은 세부 정보를 볼 수 있습니다.

> [!div class="mx-imgBorder"]
> ![상위 대상 사용자](../../media/Top_Targeted_Users.png)

### <a name="exchange-transport-rules"></a>Exchange 전송 규칙

데이터 강화의 일부로 메시지에 적용된 모든 다른 ETR(Exchange 전송 규칙)을 볼 수 있습니다. 이 정보는 전자 메일 그리드 보기에서 사용할 수 있습니다. 표시하려면 표에서 **열** 옵션을 선택한 다음 열 옵션에서 **Exchange 전송** 규칙을 추가합니다. 전자 메일의 **세부** 정보 플라이아웃에도 표시됩니다.

메시지에 적용된 전송 규칙의 GUID와 이름을 모두 볼 수 있습니다. 전송 규칙의 이름을 사용하여 메시지를 검색할 수 있습니다. 이는 부분 검색도 할 수 있는 "포함" 검색입니다.

#### <a name="important-note"></a>중요 참고 사항:

ETR 검색 및 이름 가용성은 사용자에게 할당된 특정 역할에 따라 달라집니다. ETR 이름을 보고 검색하려면 다음 역할/권한 중 하나를 설정해야 합니다. 이러한 역할이 할당되지 않은 경우 전송 규칙의 이름을 보거나 ETR 이름을 사용하여 메시지를 검색할 수 없습니다. 그러나 전자 메일 세부 정보에서 ETR 레이블 및 GUID 정보를 볼 수 있습니다. 전자 메일 그리드, 전자 메일 플라이아웃, 필터 및 내보내기에서 다른 레코드 보기 환경은 영향을 받지 않습니다.

- EXO 전용 - 데이터 손실 방지: 모두
- EXO 전용 - O365SupportViewConfig: 모두
- Microsoft Azure Active Directory 또는 EXO - 보안 관리자: 모두
- AAD 또는 EXO - 보안 판독기: 모두
- EXO 전용 - 전송 규칙: 모두
- EXO 전용 - View-Only 구성: 모두

전자 메일 그리드, 세부 정보 플라이아웃 및 내보낼 CSV 내에서 ETRS는 아래와 같이 이름/GUID와 함께 표시됩니다.

> [!div class="mx-imgBorder"]
> ![Exchange 전송 규칙](../../media/ETR_Details.png)

### <a name="inbound-connectors"></a>인바운드 커넥터

커넥터는 Microsoft 365 또는 Office 365 조직과 전자 메일이 흐르는 방법을 사용자 지정하는 지침 모음입니다. 보안 제한 또는 컨트롤을 적용할 수 있습니다. 위협 탐색기 내에서 이제 전자 메일과 관련된 커넥터를 보고 커넥터 이름을 사용하여 전자 메일을 검색할 수 있습니다.

커넥터 검색은 본질적으로 "포함"으로, 즉 부분 키워드 검색도 작동해야 합니다. 기본 그리드 보기, 세부 정보 플라이아웃 및 내보낼 CSV 내에서 커넥터는 다음과 같이 이름/GUID 형식으로 표시됩니다.

> [!div class="mx-imgBorder"]
> ![커넥터 세부 정보](../../media/Connector_Details.png)

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a>위협 탐색기 및 실시간 검색의 새로운 기능

위협 탐색기 및 실시간 검색에서는 다음과 같은 세 가지 새로운 기능을 사용할 수 있습니다.

- [전자 메일 헤더 미리 보기 및 전자 메일 본문 다운로드](#preview-email-header-and-download-email-body)
- [전자 메일 타임라인](#email-timeline)
- [URL 클릭 데이터 내보내기](#export-url-click-data)

이러한 새로운 기능은 아래에서 간략하게 설명합니다.

### <a name="preview-email-header-and-download-email-body"></a>전자 메일 헤더 미리 보기 및 전자 메일 본문 다운로드

이제 전자 메일 헤더를 미리 보고 위협 탐색기 관리자의 전자 메일 본문을 다운로드하여 다운로드한 헤더/전자 메일 메시지를 위협에 대해 분석할 수 있습니다. 전자 메일 메시지를 다운로드하면 정보가 노출될 위험이 있기 때문에 이 프로세스는 RBAC(역할 기반 액세스 제어)에 의해 제어됩니다. 모든 전자 메일 메시지 보기에서 메일 및 미리 보기 헤더를 다운로드할 수 있는 기능을 부여하려면 새 역할 미리 보기를 보안 작업 또는 보안 관리자와 같은 다른 역할 그룹에 추가해야 합니다.

탐색기 및 실시간 검색에는 전자 메일 메시지가 도착하는 위치를 보다 완전한 그림으로 제공하는 새 필드도 표시됩니다. 이러한 변경 내용을 통해 보안 연산에서 더 쉽게 헌팅할 수 있습니다. 그러나 주요 결과는 문제 전자 메일 메시지의 위치를 한 눈에 알 수 있습니다.

어떻게 하면 하나요? 배달 상태가 이제 두 개의 열로 나어집니다.

- **배달 작업** - 전자 메일의 상태입니다.
- **배달 위치** - 전자 메일이 라우팅된 위치입니다.

*배달 작업은* 기존 정책 또는 검색으로 인해 전자 메일에 대해 수행된 작업입니다. 전자 메일에 대해 가능한 작업은 다음과 같습니다.

|배달|정크|차단됨|바꾸기|
|---|---|---|---|
|전자 메일이 사용자의 받은 편지함 또는 폴더로 배달된 경우 사용자는 액세스할 수 있습니다.|전자 메일이 사용자의 정크 또는 삭제된 폴더로 전송되고 사용자가 액세스할 수 있습니다.|메일이 중단되거나, 실패했거나 삭제된 전자 메일입니다. 이러한 메일은 사용자가 사용할 수 없습니다.|전자 메일에 악의적인 첨부 파일이 첨부 파일이 악성 상태인 .txt 파일로 대체됩니다.|

다음은 사용자가 볼 수 있는 일과 볼 수 없는 것입니다.

|최종 사용자가 액세스할 수 있습니다.|최종 사용자가 사용할 수 없습니다.|
|---|---|
|배달|차단됨|
|정크|바꾸기|

**배달 위치는** 배달 후 실행된 정책 및 검색의 결과를 보여줍니다. 배달 동작에 **_연결됩니다._** 다음은 가능한 값입니다.

- *받은 편지함 또는 폴더:* 전자 메일이 받은 편지함 또는 폴더에 있습니다(전자 메일 규칙에 따라).
- *On-prem or external*: the mailbox doesn't exist on cloud but is on-premises.
- *정크 폴더:* 전자 메일이 사용자의 정크 폴더에 있습니다.
- *지우기 항목 폴더:* 사용자의 지우기 항목 폴더에 있는 전자 메일입니다.
- *Quarantine:* The email is in quarantine and not in a user's mailbox.
- *실패:* 전자 메일이 사서함에 도달하지 못했습니다.
- *삭제:* 메일 흐름에서 전자 메일이 손실됩니다.

### <a name="email-timeline"></a>전자 메일 타임라인

전자 **메일 타임라인은** 관리자를 위한 헌팅 환경을 개선하는 새로운 탐색기 기능입니다. 이벤트를 이해하기 위해 여러 위치를 검사하는 데 소요되는 시간을 줄입니다. 전자 메일이 도착할 때 여러 이벤트가 발생하거나 그에 근접하면 타임라인 보기에 해당 이벤트가 표시됩니다. 전자 메일 배달 후 발생 하는 일부 이벤트는 특수 작업 **열에 캡처** 됩니다. 관리자는 타임라인의 정보를 메일 배달 후 수행된 특수 작업과 결합하여 정책의 작동 방식, 메일이 마지막으로 라우팅된 위치 및 경우에 따라 최종 평가가 수행된 방식에 대한 정보를 얻을 수 있습니다.

자세한 내용은 [Office 365에서](investigate-malicious-email-that-was-delivered.md)배달된 악성 전자 메일 조사 및 수정을 참조하세요.

### <a name="export-url-click-data"></a>URL 클릭 데이터 내보내기

이제 URL 클릭에 대한 보고서를 Microsoft Excel로 내보내 네트워크 메시지 **ID를** 보고 결과(URL 클릭 트래픽의 원래 위치를 설명하는 데 도움이 되는 결과)를 볼 수 있습니다. 작동 방식은 다음과 같습니다. Office 365 빠른 실행 표시줄의 위협 관리에서 다음 체인을 따르세요.

**탐색기** \> **피싱 보기** \> **클릭 수** \> **상위 URL 또는** **URL 위쪽 클릭은** URL 플라이아웃을 \> 열 레코드를 선택합니다.

목록에서 URL을 선택하면 플라이아웃 패널에  새 내보내기 단추가 표시됩니다. 이 단추를 사용하여 데이터를 Excel 스프레드시트로 이동하여 보다 쉽게 보고할 수 있습니다.

이 경로를 따라 실시간 검색 보고서의 동일한 위치로 이동하십시오.

**탐색기** \> **실시간 검색** \> **피싱 보기** \> **URL** \> **상위 URL** 또는 위쪽 클릭 **중** 원하는 레코드를 선택하여 URL 플라이아웃을 \> \> 열고 클릭 **탭으로** 이동합니다.

> [!TIP]
> 네트워크 메시지 ID는 탐색기 또는 관련 타사 도구를 통해 ID를 검색할 때 클릭을 특정 메일에 매핑합니다. 이러한 검색은 클릭 결과와 연결된 전자 메일을 식별합니다. 상호 관련 네트워크 메시지 ID를 사용하면 보다 빠르고 강력한 분석이 수행됩니다.

> [!div class="mx-imgBorder"]
> ![탐색기에서 클릭 탭](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a>기술로 전자 메일에서 검색된 맬웨어 확인

Microsoft 365 기술을 통해 정렬된 전자 메일에서 검색된 맬웨어를 확인하려는 경우를 가정해 봐야 합니다. 이렇게하려면 전자 메일 [탐색기](threat-explorer-views.md#email--malware) > 맬웨어 보기(또는 실시간 검색)를 사용합니다.

1. 보안 & 준수 센터()에서 위협 관리 탐색기(또는 실시간 검색)를 <https://protection.office.com>  \>  **선택하십시오.** (이 예제에서는 Explorer를 사용합니다.)

2. 보기 **메뉴에서** 전자  메일 맬웨어를 \> **선택합니다.**

   > [!div class="mx-imgBorder"]
   > ![탐색기 보기 메뉴](../../media/ExplorerViewEmailMalwareMenu.png)

3. 보낸 **사람 클릭한** 다음 기본 검색 **기술을** \> **선택하세요.**

   이제 검색 기술을 보고서의 필터로 사용할 수 있습니다.

   > [!div class="mx-imgBorder"]
   > ![맬웨어 감지 기술](../../media/ExplorerEmailMalwareDetectionTech.png)

4. 옵션을 선택합니다. 그런 다음 새로 **고침 단추를** 선택하여 해당 필터를 적용합니다.

   > [!div class="mx-imgBorder"]
   > ![선택한 검색 기술](../../media/ExplorerEmailMalwareDetectionTechATP.png)

보고서가 새로 고쳐서 선택한 기술 옵션을 사용하여 전자 메일에서 맬웨어가 검색된 결과를 보여 주게 됩니다. 여기에서 추가 분석을 진행할 수 있습니다.

## <a name="view-phishing-url-and-click-verdict-data"></a>피싱 URL 보기 및 판정 데이터 클릭

허용, 차단 및 재지정된 URL 목록을 포함하여 전자 메일의 URL을 통해 피싱 시도를 확인하려는 경우를 가정해 봐야 합니다. 클릭한 URL을 식별하려면 안전한 [](atp-safe-links.md) 링크를 구성해야 합니다. 클릭 시 보호 [](set-up-atp-safe-links-policies.md) 및 안전한 링크로 클릭 판정 로깅에 대해 안전한 링크 정책을 설정해야 합니다.

메시지의 피싱 URL을 검토하고 피싱 메시지의 URL을 클릭하려면 탐색기 또는 실시간 검색의 전자 메일 피싱 보기를 사용합니다. [   >   ](threat-explorer-views.md#email--phish)

1. 보안 & 준수 센터()에서 위협 관리 탐색기(또는 실시간 검색)를 <https://protection.office.com>  \>  **선택하십시오.** (이 예제에서는 Explorer를 사용합니다.)

2. 보기 **메뉴에서** **전자** 메일 \> **피싱을 선택합니다.**

   > [!div class="mx-imgBorder"]
   > ![피싱 컨텍스트에서 탐색기 메뉴 보기](../../media/ExplorerViewEmailPhishMenu.png)

3. 보낸 **사람 클릭한** 다음 **URL** 클릭 \> **verdict를 클릭합니다.**

4. 차단 및 다시 설정 차단과 같은 하나 이상의 옵션을 선택한  다음 해당 필터를 적용할 옵션과 같은 줄에서 새로 고침 단추를 선택합니다.  (브라우저 창을 새로 고치지 않습니다.)

   > [!div class="mx-imgBorder"]
   > ![URL 및 클릭 판정](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

   보고서가 새로 고쳐지며 보고서 아래에 있는 URL 탭에 두 개의 서로 다른 URL 테이블이 표시됩니다.

   - **상위 URL은** 필터링한 메시지의 URL과 각 URL에 대한 전자 메일 배달 작업 수입니다. 피싱 전자 메일 보기에서 이 목록에는 일반적으로 합법적인 URL이 포함되어 있습니다. 공격자는 배달을 시도하기 위해 좋은 URL과 잘못된 URL을 메시지에 혼합하여 포함하지만 악의적인 링크가 더 흥미로워 보이게 합니다. URL 표는 총 전자 메일 수에 따라 정렬되지만 보기를 단순화하기 위해 이 열은 숨겨집니다.

   - **위쪽 클릭은** 총 클릭 수별로 정렬된 클릭한 안전한 링크로 래핑된 URL입니다. 보기를 단순화하기 위해 이 열도 표시되지 않습니다. 열별로 총 개수는 클릭한 각 URL에 대한 안전한 링크 클릭 결과 수를 나타냅니다. 피싱 전자 메일 보기에서 이러한 URL은 일반적으로 의심스러우거나 악의적인 URL입니다. 그러나 이 보기에는 위협이 아닌 피싱 메시지에 있는 URL이 포함되어 있을 수 있습니다. 래핑되지 않은 링크의 URL 클릭은 여기에 표시되지 않습니다.

   두 URL 테이블에는 배달 작업 및 위치로 피싱 전자 메일 메시지의 상위 URL이 표시됩니다. 표에는 경고에도 불구하고 차단되거나 방문한 URL 클릭이 표시될 수 있으므로 사용자에게 표시될 수 있는 잘못된 링크와 사용자의 클릭을 볼 수 있습니다. 여기에서 추가 분석을 진행할 수 있습니다. 예를 들어 차트 아래에서 조직의 환경에서 차단된 전자 메일 메시지의 상위 URL을 볼 수 있습니다.

   > [!div class="mx-imgBorder"]
   > ![차단된 탐색기 URL](../../media/ExplorerPhishClickVerdictURLs.png)

   URL을 선택하여 자세한 정보를 확인합니다.

   > [!NOTE]
   > URL 플라이아웃 대화 상자에서 환경의 URL 노출에 대한 전체 보기를 표시하기 위해 전자 메일 메시지에 대한 필터링이 제거됩니다. 이렇게 하면 탐색기에서 우려하는 전자 메일 메시지를 필터링하고 잠재적 위협이 될 수 있는 특정 URL을 찾은 다음 탐색기 보기 자체에 URL 필터를 추가하지 않고도 URL 세부 정보 대화 상자를 통해 환경의 URL 노출에 대한 이해를 확장할 수 있습니다.

### <a name="interpretation-of-click-verdicts"></a>클릭 판정 해석

전자 메일 또는 URL 플라이아웃, Top Clicks 및 필터링 환경 내에서 다양한 클릭 판정 값이 표시됩니다.

- **없음:** URL에 대한 판정을 캡처할 수 없습니다. 사용자가 URL을 클릭한 것일 수 있습니다.
- **허용:** 사용자가 URL로 이동할 수 있습니다.
- **차단된:** 사용자가 URL로 이동하지 않습니다.
- **보류 중인 판정:** 사용자에게 확인 대기 중인 페이지가 표시됩니다.
- **차단된 은(는)** 사용자가 URL로 직접 이동하지 않습니다. 그러나 사용자가 URL로 이동하기 위해 차단을 오버라이드합니다.
- **보류 중인 판정이 무시됩니다.** 사용자에게 데토니타이트 페이지가 표시됩니다. 그러나 사용자가 URL에 액세스하기 위해 메시지를 오버라이드합니다.
- **오류:** 사용자에게 오류 페이지가 표시되거나, 판정을 캡처하는 중 오류가 발생했습니다.
- **실패:** 판정을 캡처하는 동안 알 수 없는 예외가 발생했습니다. 사용자가 URL을 클릭한 것일 수 있습니다.

## <a name="review-email-messages-reported-by-users"></a>사용자가 보고한 전자 메일 메시지 검토

조직의 사용자가 보고서 메시지 추가 기능 또는 피싱 보고서 추가 기능을 통해  정크 메일, 정크 메일 아님 또는 피싱으로 보고한 전자 메일 메시지를 확인하려는 경우를 가정해 봐야 [합니다.](enable-the-report-phish-add-in.md)  [](enable-the-report-message-add-in.md) 이를 확인하려면 탐색기(또는 실시간 검색)의 전자 메일 제출 보기를 사용합니다. [   >   ](threat-explorer-views.md#email--submissions)

1. 보안 & 준수 센터()에서 위협 관리 탐색기(또는 실시간 검색)를 <https://protection.office.com>  \>  **선택하십시오.** (이 예제에서는 Explorer를 사용합니다.)

2. 보기 **메뉴에서** 전자 메일  \> **제출을 선택합니다.**

   > [!div class="mx-imgBorder"]
   > ![전자 메일용 탐색기 메뉴 보기](../../media/explorer-view-menu-email-user-reported.png)

3. 보낸 **사람 클릭한** 다음 기본 보고서 **유형을** \> **선택 합니다.**

4. 피싱과 같은 옵션을 선택한 다음 새로 고침 **단추를** 선택합니다.

   > [!div class="mx-imgBorder"]
   > ![사용자가 보고한 피싱](../../media/EmailUserReportedReportType.png)

조직의 사용자들이 피싱 시도로 보고한 전자 메일 메시지에 대한 데이터를 표시하기 위해 보고서가 새로 고쳐서 표시됩니다. 이 정보를 사용하여 추가 분석을 수행하고, 필요한 경우 [Office 365용 Microsoft Defender에서](configure-atp-anti-phishing-policies.md)피싱 방지 정책을 조정할 수 있습니다.

## <a name="start-automated-investigation-and-response"></a>자동화된 조사 및 대응 시작

> [!NOTE]
> 자동화된 조사 및 응답 기능은 *Office 365 계획 2 및 Office 365 E5용 Microsoft Defender에서* *사용할 수 있습니다.*

[자동화된 조사 및 대응을](automated-investigation-response-office.md) 통해 사이버 공격을 조사하고 완화하는 데 들이는 시간과 노력을 절약할 수 있습니다. 보안 플레이북을 트리거할 수 있는 경고를 구성하는 것 외에도 탐색기 보기에서 자동화된 조사 및 응답 프로세스를 시작할 수 있습니다. 자세한 내용은 [예제: 보안 관리자가 Explorer에서 조사를 트리거합니다.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)

## <a name="more-ways-to-use-explorer-and-real-time-detections"></a>탐색기 및 실시간 검색을 사용하는 더 많은 방법

이 문서에 설명된 시나리오 외에도 탐색기(또는 실시간 검색)에서 더 많은 보고 옵션을 사용할 수 있습니다. 다음 문서를 참조합니다.

- [배달된 악성 전자 메일 찾기 및 조사](investigate-malicious-email-that-was-delivered.md)
- [SharePoint Online, OneDrive 및 Microsoft Teams에서 검색된 악성 파일 보기](malicious-files-detected-in-spo-odb-or-teams.md)
- [위협 탐색기(및 실시간 검색)에서 보기에 대한 개요를 얻습니다.](threat-explorer-views.md)
- [위협 방지 상태 보고서](view-email-security-reports.md#threat-protection-status-report)
- [Microsoft Threat Protection의 자동화된 조사 및 대응](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

## <a name="required-licenses-and-permissions"></a>필수 라이선스 및 사용 권한

탐색기 또는 실시간 검색을 사용하려면 [Office 365용 Microsoft Defender가](office-365-atp.md) 있어야 합니다.

- 탐색기는 Office 365 계획 2용 Defender에 포함되어 있습니다.
- 실시간 검색 보고서는 Office 365 계획 1용 Defender에 포함되어 있습니다.
- Office 365용 Defender에서 보호해야 하는 모든 사용자에 대한 라이선스 할당을 계획합니다. 탐색기 및 실시간 검색은 사용이 허가된 사용자에 대한 검색 데이터를 보여 주며,

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

## <a name="differences-between-threat-explorer-and-real-time-detections"></a>위협 탐색기와 실시간 검색 간의 차이점

- 실시간 *검색* 보고서는 Office 365 계획 1용 Defender에서 사용할 수 있습니다. *위협 탐색기는* Office 365 계획 2용 Defender에서 사용할 수 있습니다.
- 실시간 검색 보고서를 사용하면 검색을 실시간으로 볼 수 있습니다. 위협 탐색기에서도 이 기능을 하지만, 주어진 공격에 대한 추가 세부 정보도 제공합니다.
- 위협 *탐색기에서는* 모든 전자 메일 보기를 사용할 수 있지만 실시간 검색 보고서에서는 사용할 수 없습니다.
- 더 많은 필터링 기능 및 사용 가능한 작업이 위협 탐색기에 포함되어 있습니다. 자세한 내용은 [Office 365용 Microsoft Defender 서비스 설명: Office 365 계획용 Defender의 기능 가용성을 참조하세요.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)
