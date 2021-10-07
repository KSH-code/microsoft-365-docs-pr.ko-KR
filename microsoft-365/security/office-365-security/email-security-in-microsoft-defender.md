---
title: Microsoft Defender for Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 맬웨어 피싱 시도를 보고 조사합니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 06053911642e455df956de3a17e3e2f448023328
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60203906"
---
# <a name="email-security-with-threat-explorer-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

이 문서의 내용

- [전자 메일에서 검색된 맬웨어 보기](#view-malware-detected-in-email)
- [피싱 URL 보기 및 판정 데이터 클릭](#view-phishing-url-and-click-verdict-data)
- [자동화된 조사 및 대응 시작](#start-automated-investigation-and-response)

> [!NOTE]
> 이 문서는 위협 탐색기(탐색기) **,** 전자 메일 보안 및 **탐색기** 및 실시간 검색 기본(예: 도구 간 차이점 및 작동에 필요한 사용 권한)에 대한 **3개** 문서 시리즈의 일부입니다.  이 시리즈의 다른 두 문서는 위협 탐색기 및 [위협](threat-hunting-in-threat-explorer.md) 탐색기에서 위협 헌팅 및 실시간 검색 기본 [입니다.](real-time-detections.md)

이 문서에서는 보안 기능을 통해 전자 메일에서 감지된 맬웨어 및 피싱 시도를 보고 Microsoft 365 방법을 설명합니다.

**적용 대상:**

- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="view-malware-detected-in-email"></a>전자 메일에서 검색된 맬웨어 보기

전자 메일에서 검색된 맬웨어를 Microsoft 365 탐색기(또는 실시간 검색)의 전자 메일 맬웨어 보기를 사용합니다. [**\>**](threat-explorer-views.md#email--malware) 맬웨어는 기본 보기이기 때문에 탐색기를 여는 즉시 선택될 수 있습니다.

1. in the Microsoft 365 Defender portal ( <https://security.microsoft.com> ), choose Email & **collaboration** \> **Explorer** (or **Real-time detections**; 이 예제에서는 Explorer를 사용합니다.

   여기에서 보기에서 시작하여 조사할 특정 시간 프레임(필요한 경우)을 선택하고 탐색기에서 진행하는 에 따라 필터에 [집중합니다.](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through)

2. 보기 **드롭다운** 목록에서 전자  메일 맬웨어가 \>  선택되어 있는지 확인 합니다.

3. 보낸 **사람 을** 클릭한 다음 **드롭다운** 목록에서 기본 검색 기술을 \>  선택합니다.

   :::image type="content" source="../../media/exploreremailmalwaredetectiontech-newimg.png" alt-text="맬웨어 감지 기술.":::

   이제 검색 기술을 보고서의 필터로 사용할 수 있습니다.

4. 옵션을 선택한 다음 새로 고침을 **클릭하여** 해당 필터를 적용합니다(브라우저 창을 새로 고치지 않습니다).

   :::image type="content" source="../../media/exploreremailmalwaredetectiontech2-new.png" alt-text="선택된 검색 기술.":::

   보고서가 새로 고쳐서 선택한 기술 옵션을 사용하여 전자 메일에서 맬웨어가 검색된 결과를 보여 주며, 여기에서 추가 분석을 진행할 수 있습니다.

## <a name="view-phishing-url-and-click-verdict-data"></a>피싱 URL 보기 및 판정 데이터 클릭

허용, 차단 및 재지정된 URL 목록을 포함하여 전자 메일의 URL을 통해 피싱 시도를 볼 수 있습니다. 클릭된 URL을 식별하려면 링크 금고 [구성해야](safe-links.md) 합니다. 클릭 시간 보호 [](set-up-safe-links-policies.md) 및 금고 링크를 통해 클릭 판정 로깅에 대한 링크 금고 있는지 금고 합니다.

1. in the Microsoft 365 Defender portal ( <https://security.microsoft.com> ), choose Email & **collaboration** \> **Explorer** (or **Real-time detections**; 이 예제에서는 Explorer를 사용합니다.

2. 보기 **드롭다운** 목록에서 전자 **메일** \> **피싱 을 선택합니다.**

   > [!div class="mx-imgBorder"]
   > ![피싱 컨텍스트에서 탐색기 메뉴 보기](../../media/ExplorerViewEmailPhishMenu.png)

3. 보낸 **사람 을** 클릭한 다음 **드롭다운** 목록에서 URL \> **클릭** 판정을 선택합니다.

4. 나타나는 옵션에서 차단 및 다시 설정 차단과 같은 하나 이상의 옵션을 선택한  다음 새로 고침을 클릭합니다(브라우저 창을 새로 고치지 않습니다). 

    :::image type="content" source="../../media/threatexploreremailphishclickverdict-new.png" alt-text="URL 및 확인을 클릭합니다.":::

   보고서가 새로 고쳐지며 보고서 아래에 있는 URL 탭에 두 개의 서로 **다른** URL 테이블이 표시됩니다.

   - **상위 URL은** 필터링한 메시지의 URL과 각 URL에 대한 전자 메일 배달 작업 수입니다. 피싱 전자 메일 보기에서 이 목록에는 일반적으로 합법적인 URL이 포함되어 있습니다. 공격자는 메시지에 좋은 URL과 잘못된 URL을 혼합하여 배달하려고 시도하지만 악의적인 링크가 더 흥미로워 보이게 합니다. URL 표는 총 전자 메일 수를 통해 정렬되지만 보기를 단순화하기 위해 이 열은 숨겨집니다.

   - **위쪽 클릭은** 금고 총 클릭 수별로 정렬된 링크로 래핑된 URL의 수입니다. 보기를 단순화하기 위해 이 열도 표시되지 않습니다. 열당 총 개수는 클릭한 각 URL에 금고 링크 클릭 결과 수를 나타냅니다. 피싱 전자 메일 보기에서 이러한 URL은 일반적으로 의심스러우거나 악의적인 URL입니다. 그러나 보기에는 위협이 아닌 피싱 메시지에 있는 URL이 포함되어 있을 수 있습니다. Url clicks on unwrapped links don't show up here.

   두 URL 테이블에는 배달 작업 및 위치로 피싱 전자 메일 메시지의 상위 URL이 표시됩니다. 표에는 경고에도 불구하고 차단되거나 방문한 URL 클릭이 표시 있으므로 사용자에게 제공된 잠재적인 잘못된 링크와 사용자가 클릭한 잠재적인 링크를 볼 수 있습니다. 여기에서 추가 분석을 진행할 수 있습니다. 예를 들어 차트 아래에서 조직의 환경에서 차단된 전자 메일 메시지의 상위 URL을 볼 수 있습니다.

   > [!div class="mx-imgBorder"]
   > ![차단된 탐색기 URL입니다.](../../media/ExplorerPhishClickVerdictURLs.png)

   자세한 정보를 확인하려면 URL을 선택합니다.

   > [!NOTE]
   > URL 플라이아웃 대화 상자에서 전자 메일 메시지에 대한 필터링이 제거되어 작업 환경에서 URL 노출에 대한 전체 보기가 표시됩니다. 이렇게 하면 탐색기에서 우려하는 전자 메일 메시지를 필터링하고, 잠재적 위협이 될 수 있는 특정 URL을 찾은 다음 탐색기 보기 자체에 URL 필터를 추가하지 않고도 URL 세부 정보 대화 상자를 통해 환경의 URL 노출에 대한 이해를 확장할 수 있습니다.

### <a name="interpretation-of-click-verdicts"></a>클릭 판정 해석

전자 메일 또는 URL 플라이아웃, Top Clicks 및 필터링 환경의 다양한 클릭 판정 값이 표시됩니다.

- **없음:** URL에 대한 판정을 캡처할 수 없습니다. 사용자가 URL을 클릭한 것일 수 있습니다.
- **허용:** 사용자가 URL로 이동할 수 있습니다.
- **차단된:** 사용자가 URL로 이동하지 않습니다.
- **보류 중인 판정:** 사용자에게 확인 대기 중인 페이지가 표시됩니다.
- **차단된 은(는)** 사용자가 URL로 직접 이동하지 않습니다. 그러나 사용자가 URL로 이동하기 위해 차단을 어버렸다.
- **보류 중인 판정이 무시됩니다.** 사용자에게 데토톤 페이지가 표시됩니다. 그러나 사용자가 URL에 액세스하기 위해 메시지를 오버라이드합니다.
- **오류:** 사용자에게 오류 페이지가 표시되거나 판정을 캡처하는 중 오류가 발생했습니다.
- **실패:** 판정을 캡처하는 동안 알 수 없는 예외가 발생했습니다. 사용자가 URL을 클릭한 것일 수 있습니다.

## <a name="start-automated-investigation-and-response"></a>자동화된 조사 및 대응 시작

> [!NOTE]
> 자동화된 조사 및 대응 기능은 *Microsoft Defender for Office 365 Plan 2* *및* Office 365 E5.

[자동화된 조사 및 대응은](automated-investigation-response-office.md) 사이버 공격을 조사하고 완화하는 데 소요된 보안 운영 팀의 시간과 노력을 절약할 수 있습니다. 보안 플레이북을 트리거할 수 있는 경고를 구성하는 것 외에도 탐색기 보기에서 자동화된 조사 및 응답 프로세스를 시작할 수 있습니다. 자세한 내용은 예제: 보안 관리자가 Explorer에서 [조사를 트리거합니다.를 참조합니다.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)

## <a name="other-articles"></a>기타 문서

[전자 메일 엔터티 페이지를 통해 전자 메일 조사](mdo-email-entity-page.md)
