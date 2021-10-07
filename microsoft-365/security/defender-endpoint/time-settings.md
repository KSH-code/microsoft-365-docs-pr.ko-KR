---
title: Microsoft 365 Defender 표준 시간대 설정
description: 여기에 포함된 정보를 사용하여 표준 시간대 설정을 Microsoft 365 Defender 라이선스 정보를 볼 수 있습니다.
keywords: 설정, Microsoft Defender, 사이버 보안 위협 인텔리전스, 끝점용 Microsoft Defender, 표준 시간대, utc, 현지 시간, 라이선스
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 461b87750b40e37493ff88acfa2b4a5521494841
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60151821"
---
# <a name="microsoft-365-defender-time-zone-settings"></a>Microsoft 365 Defender 표준 시간대 설정

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)


> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-settings-abovefoldlink)

표준 시간대 **메뉴** 표준 시간대 ![ 설정 아이콘1을 사용합니다.](images/atp-time-zone.png) 표준 시간대를 구성하고 라이선스 정보를 볼 수 있습니다.

## <a name="time-zone-settings"></a>표준 시간대 설정

시간 측면은 인식된 사이버 공격과 실제 사이버 공격의 평가 및 분석에서 중요합니다.

사이버 포렌식 조사는 종종 타임스탬프를 통해 일련의 이벤트를 구성합니다. 시스템이 올바른 표준 시간대 설정을 반영하는 것이 중요합니다.

끝점용 Microsoft Defender는 UTC(협정 세계시) 또는 현지 시간을 표시할 수 있습니다.

현재 표준 시간대 설정은 끝점용 Microsoft Defender 메뉴에 표시됩니다. 표준 시간대 메뉴에서 표시된 표준 시간대를 **변경할 수** 있습니다.

![표준 시간대 설정 아이콘2.](images/atp-time-zone-menu.png).

### <a name="utc-time-zone"></a>UTC 표준 시간대

Microsoft Defender for Endpoint는 기본적으로 UTC 시간을 사용 합니다.

끝점 표준 시간대에 대한 Microsoft Defender를 UTC로 설정하면 모든 사용자에 대한 모든 시스템 타임스탬프(경고, 이벤트 등)가 UTC로 표시됩니다. 이를 통해 전 세계 여러 위치에서 작업하는 보안 분석가가 이벤트를 조사하는 동안 동일한 타임스탬프를 사용하는 데 도움이 될 수 있습니다.

### <a name="local-time-zone"></a>현지 표준 시간대

끝점용 Microsoft Defender가 현지 표준 시간대 설정을 사용하게 선택할 수 있습니다. 모든 경고 및 이벤트는 현지 표준 시간대를 사용하여 표시됩니다.

로컬 표준 시간대는 장치의 국가별 설정에서 이동합니다. 국가별 설정을 변경하면 끝점용 Microsoft Defender 표준 시간대도 변경됩니다. 이 설정을 선택하면 끝점용 Microsoft Defender에 표시되는 타임스탬프가 모든 끝점 사용자에 대한 현지 시간으로 정렬됩니다. 다른 전역 위치에 있는 분석가에게는 이제 해당 국가별 설정에 따라 끝점용 Microsoft Defender 경고가 표시됩니다.

분석가가 단일 위치에 있는 경우 현지 시간을 사용하기로 선택하는 것이 유용할 수 있습니다. 이 경우 로컬 사용자가 의심스러운 전자 메일 링크를 클릭하는 경우와 같은 현지 시간으로 이벤트를 보다 쉽게 상관 관계화할 수 있습니다.

### <a name="set-the-time-zone"></a>표준 시간대 설정

끝점용 Microsoft Defender 표준 시간대는 기본적으로 UTC로 설정됩니다. 표준 시간대를 설정하면 모든 끝점 보기에 대한 Microsoft Defender의 시간도 변경됩니다.

표준 시간대를 설정하는 경우:

1. 표준 시간대 **메뉴** 표준 시간대 ![ 설정 아이콘3을 ](images/atp-time-zone.png) 클릭합니다.
2. **Timezone UTC indicator(시간 표시기)를** 선택합니다.
3. 표준 **시간대 UTC** 또는 로컬 표준 시간대(예: -7:00)를 선택합니다.

### <a name="regional-settings"></a>국가별 설정

끝점용 Microsoft Defender에 다른 날짜 형식을 적용하려면 IE(Internet Explorer) 및 에지(Edge)에 Microsoft Edge 설정을 사용합니다. Google Chrome과 같은 다른 브라우저를 사용하는 경우 필요한 단계에 따라 해당 브라우저의 시간 및 날짜 설정을 변경합니다. 

#### <a name="internet-explorer-ie-and-microsoft-edge"></a>Internet Explorer(IE) 및 Microsoft Edge

IE 및 Microsoft Edge 제어판의 **시계,** 언어 및 지역 옵션에 구성된 지역 설정을 사용합니다.  

#### <a name="known-issues-with-regional-formats"></a>지역별 형식의 알려진 문제

##### <a name="date-and-time-formats"></a>날짜 및 시간 형식

시간 및 날짜 형식에 몇 가지 알려진 문제가 있습니다. 지원되는 형식이 아닌 다른 형식으로 국가별 설정을 구성하는 경우 포털에 설정이 올바르게 반영되지 않을 수 있습니다.

다음 날짜 및 시간 형식이 지원됩니다.

- 날짜 형식 MM/dd/yyyy
- 날짜 형식 dd/MM/yyyy
- 시간 형식 hh:mm:ss(12시간 형식)

다음 날짜 및 시간 형식은 현재 지원되지 않습니다.

- 날짜 형식 yyyy-MM-dd
- 날짜 형식 dd-MMM-yy
- 날짜 형식 dd/MM/yy
- 날짜 형식 MM/dd/yy
- 날짜 형식(yy) yyyy만 표시
- 시간 형식 HH:mm:ss(24시간 형식)

##### <a name="decimal-symbol-used-in-numbers"></a>숫자에 사용되는 소수 기호

사용되는 소수점 기호는 지역 설정의 숫자 형식 설정에서 콤보가 선택되어 있는 경우에도 항상 **점입니다.**  예를 들어 15,5K는 15.5K로 표시됩니다.
