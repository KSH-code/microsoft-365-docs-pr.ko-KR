---
title: 자동화 조사 세부정보 및 결과 보기
description: '자동화 조사가 진행 되는 동한 혹은 진행 완료된 후 주요 사항 및 결과를 확인할 수 있습니다. '
keywords: 자동화, 조사, 결과, 분속, 세부정보, 재구성, 오토에어
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom:
- autoir
- admindeeplinkDEFENDER
ms.reviewer: evaldm, isco
ms.openlocfilehash: dd5a8d4db47eb0f26f7bdf7ef992fba18a6c3aa5
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2021
ms.locfileid: "60963194"
---
# <a name="view-the-details-and-results-of-an-automated-investigation"></a>자동화 조사 세부정보 및 결과 보기

**적용 대상:**
- 엔드포인트용 Microsoft Defender

끝점용 Microsoft Defender를 [](automated-investigations.md) 통해 자동화된 조사가 실행되는 경우 자동화된 조사 프로세스 중 및 이후에 조사에 대한 세부 정보를 사용할 수 있습니다. 필수 권한이있는 경우 조사 세부 정보 보기에서 해당 정보를 확인할 수 있습니다.  조사 세부정부 보기에서 최신 상태를 확인하거나 보류중인 작업을 승인할 수 있습니다.

## <a name="new-unified-investigation-page"></a>(NEW!) 통합 조사 페이지

조사 페이지가 최근에 장치, 전자 메일 및 공동 작업 콘텐츠에 대한 정보를 포함하기 위해 업데이트되었습니다. 새로운 통합 조사 페이지는 공통 언어를 정의하고 끝점용 [Microsoft Defender](microsoft-defender-endpoint.md) 및 Microsoft [Defender](/microsoft-365/security/office-365-security/office-365-atp)for Office 365.

> [!TIP]
> 변경에 대한 자세한 내용은 [(NEW!)를 참조하세요. 통합 조사 페이지.](/microsoft-365/security/mtp/mtp-autoir-results)

## <a name="open-the-investigation-details-view"></a>조사 세부정보 보기 열기 

다음 방법 중 하나를 사용 하여 조사 세부정보 보기를 열 수 있습니다.

- [작업 센터에서 항목 선택](#select-an-item-in-the-action-center)
- [문제 세부정보 페이지에서 조사 선택](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>작업 센터에서 항목 선택

향상된 [알림](auto-investigation-action-center.md) 센터는 [](manage-auto-investigation.md#remediation-actions) 장치, 전자 메일 및 공동 작업 콘텐츠 및 & 수정 작업을 함께 제공합니다. 나열된 작업에는 자동으로 또는 수동으로 수행된 수정 작업이 포함됩니다. 알림 센터에서 승인 대기 중인 작업과 이미 승인되거나 완료된 작업을 볼 수 있습니다. 조사 페이지와 같은 자세한 정보로 이동할 수 있습니다.

1. 이동하여 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> 로그인합니다.
2. 탐색 창에서 **작업 센터** 를 선택합니다.
3. **보류 중인** 또는 **기록** 탭에서 항목을 선택 합니다. 플라이아웃 창이 열립니다.
4. 플라이아웃 창의 정보를 검토한 후 다음 단계 중 하나를 수행합니다.
   - 조사에 대한 자세한 내용을 **확인하려면** 조사 페이지 열기 를 선택합니다.
   - **승인을** 선택하여 보류 중인 작업을 초기화합니다.
   - 보류 **중인** 작업이 수행되지 않도록 방지하려면 거부를 선택합니다.
   - 이동을 **선택하여** 고급 헌팅으로 [이동합니다.](advanced-hunting-overview.md)

### <a name="open-an-investigation-from-an-incident-details-page"></a>문제 세부정보 페이지에서 조사 오픈 

세부정보 페이지를 통해 알람 원인 장치, 사용자, 사서함 등 사건에 대한 세부 정보를 확인할 수 있습니다. 

1. 이동하여 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> 로그인합니다.
2. 탐색 창에서 인시던트 및 **인시던트** & \> **를 선택 합니다.**
3. 목록에서 항목을 선택한 다음 문제 페이지 **열기 를 선택합니다.**
4. 조사 **탭을** 선택한 다음 목록에서 조사를 선택합니다. 플라이아웃 창이 열립니다.
5. 조사 **페이지 열기 를 선택합니다.**

## <a name="investigation-details"></a>조사 세부정보

조사 세부정보 보기를 사용 하여 과거, 현재 및 보류 중인 활동을 확인하고 조사합니다. 조사 세부정보 보기는 다음 이미지와 유사 합니다.

조사 세부정보 보기에서 아래 테이블에 설명되어 있는 것 처럼 **조사 그래프**, **알람**, **장치**, **항목**, **주요 발견 사항**, **대상**, **로그** 및 **보류 활동** 을 확인할 수 있습니다. 

> [!NOTE]
> 조사 세부 정보 페이지에 볼 수 있는 특정 탭은 구독에 포함된 내용에 따라 다를 수 있습니다. 예를 들어 구독에 Office 365 요금제 2에 대한 Microsoft Defender가 포함되어 있지 않은 경우 사서함 탭이 **표시되지** 않습니다.

|Tab|설명|
|---|---|
|**조사 그래프**|조사 내용이 시각적으로 표시 됩니다. 위협 대상과 목록 알람과 현재 활동이나 보류중인 활동을 보여줍니다.  <p> 그래프에서 항목을 선택하여 세부 정보를 볼 수 있습니다. 예를 들어 증거  아이콘을 선택하면 검색된 엔터티와 해당 판정을 볼 수 있는 증거 탭으로 이동됩니다. |
|**알람**|조사와 관련 된 알람목록을 보여줍니다.  경고는 사용자 장치의 Office 앱, Cloud App Security, 기타 Microsoft 365 Defender 기능의 위협 방지 기능에서 발생할 수 있습니다.|
|**장치**|조사에 포함된 장치를 수정 수준과 함께 나열합니다. 재구성 수준은 장치 그룹의 [자동화 수준에 해당합니다.](automation-levels.md)|
|**사서함**|검색된 위협의 영향을 받는 사서함을 나열합니다.|
|**사용자**|검색된 위협의 영향을 미치는 사용자 계정을 나열합니다.|
|**증거**|경고/조사에서 제기된 증거 조각을 나열합니다. *판정(악성,* *의심스러운* 또는 위협 *없음)* 및 수정 상태를 포함합니다.|
|**항목**|각 엔터티 유형(악성, 의심스러운 또는 위협이 없음)에 대한 판정을 포함하여 분석된 각 엔터티에 대한 세부 *정보를 제공합니다.* |
|**로그**|경고가 트리거된 후 수행된 모든 조사 작업을 연대적으로 상세하게 볼 수 있습니다.|
|**보류 중인 작업**|진행 하려면 승인이 필요한 항목을 나열 합니다. 작업 센터()로 <https://security.microsoft.com/action-center> 이동하여 보류 중인 작업을 승인합니다.|

## <a name="see-also"></a>참고 항목

- [자동화된 조사 후 수정 작업 검토](manage-auto-investigation.md)
- [엔드포인트용 Microsoft Defender 인시던트 큐 보기 및 구성](view-incidents-queue.md)
