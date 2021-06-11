---
title: 사용자로 격리된 메시지 찾기 및 릴리스
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 사용자에게 전달되었어야 하는 EOP(Exchange Online Protection)에 격리된 메시지를 보고 관리하는 방법에 대해 알아볼 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 60b319b81362b9d88afcd734021db227969b04d0
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52877875"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a>EOP에서 사용자 권한으로 격리된 메시지 찾기 및 해제하기

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange online Protection) 조직에서 격리는 위험할 가능성이 있거나 원치 않는 메시지를 보유합니다. 자세한 내용은 [EOP에 격리](quarantine-email-messages.md)를 참조하세요.

격리된 메시지 수신자가 일반 사용자로서 메시지에 할 수 있는 작업이 다음 표에 설명되어 있습니다.

<br>

****

|격리 이유:|보기|릴리스|삭제|
|---|:---:|:---:|:---:|
|대량|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|
|스팸|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|
|피싱(높은 신뢰도 피싱은 해당 안 됨)|![확인 표시](../../media/checkmark.png)||![확인 표시](../../media/checkmark.png)|
|

Microsoft 365 Defender 포털 또는 [최종 사용자 스팸 알림](use-spam-notifications-to-release-and-report-quarantined-messages.md)(관리자가 설정한 경우)에서 격리된 메시지를 보고 관리합니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용

- Microsoft 365 Defender 포털을 열려면 <https://security.microsoft.com>(으)로 이동합니다. 격리 페이지를 바로 열려면 <https://security.microsoft.com/quarantine>(으)로 이동합니다.

- 관리자는 스팸 방지 정책에서 메시지를 영구적으로 삭제하기 전에 얼마 동안 메시지를 격리 상태로 유지할지 구성할 수 있습니다. 격리에서 만료되는 메시지는 복구할 수 없습니다. 자세한 내용은 [EOP에서 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.

- 관리자는 스팸 방지 정책에서 [최종 사용자 스팸 알림을 사용하도록 설정](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)할 수도 있습니다. 사용자는 격리된 스팸 메시지를 해제할 수 있지만 이 알림에서 격리된 피싱 메시지를 직접 해제할 수 없습니다. 사용자는 이러한 알림에서 직접 검역된 피싱 메시지(고신뢰 피싱 메시지가 아님)를 검토할 수 있습니다. 자세한 내용은 [EOP의 최종 사용자 스팸 통지](use-spam-notifications-to-release-and-report-quarantined-messages.md)를 참조합니다.

- 높은 신뢰도 피싱, 악성 프로그램 또는 메일 흐름 규칙(트랜스포트 규칙이라고도 함)으로 검역된 메시지는 관리자만 사용할 수 있으며 사용자에게 표시되지 않습니다. 자세한 내용은 [EOP에서 관리자로 격리된 메시지 관리하기](manage-quarantined-messages-and-files.md)를 참조하세요.

- 메시지를 해제하고 가양성으로(정크 아님) 한 번만 보고할 수 있습니다.

## <a name="view-your-quarantined-messages"></a>격리된 메시지 보기

1. Microsoft 365 Defender 포털에서 **전자 메일 및 공동 작업** \> **검토** \> **격리** 로 이동합니다.

2. 사용 가능한 열 헤더를 클릭하여 결과를 정렬할 수 있습니다. **열 수정** 을 클릭하여 최대 7개의 열을 표시합니다. 기본값은 별표(<sup>\*</sup>)로 표시됩니다.

   - **수신됨**<sup>\*</sup>
   - **보낸 사람**<sup>\*</sup>
   - **제목**<sup>\*</sup>
   - **격리 이유**<sup>\*</sup>
   - **해제되었나요?**<sup>\*</sup>
   - **정책 유형**<sup>\*</sup>
   - **만료**<sup>\*</sup>
   - **받는 사람**
   - **메시지 ID**
   - **정책 이름**
   - **크기**
   - **방향**

   작업을 마쳤으면 **저장** 을 클릭하거나 **기본으로 설정** 을 클릭합니다.

3. 결과를 필터링하려면 **필터** 를 클릭합니다. 사용 가능한 필터:

   - **만료 시간**: 메시지가 격리에서 만료되는 때를 기준으로 필터링:
     - **오늘**
     - **다음 2일**
     - **다음 7일**
     - **사용자 지정**: **시작 날짜** 와 **종료 날짜** 를 입력합니다.

   - **받은 시간**: **시작 날짜** 와 **종료 날짜** 를 입력합니다.

   - **격리 이유**:
     - **대량 전자 메일**
     - **스팸**
     - **피싱**

   - **정책 유형**: 정책 유형별로 메시지를 필터링합니다.
     - **맬웨어 방지 정책**
     - **안전한 첨부 파일 정책**(Office 365용 Defender)
     - **피싱 방지 정책**
     - **호스트된 필터 정책**(스팸 방지 정책)
     - **전송 규칙**

     <sup>\*</sup>

   필터를 지우려면 **지우기** 를 클릭합니다. 필터 플라이아웃을 숨기려면 다시 **필터** 를 클릭합니다.

4. 특정 메시지를 찾으려면 **결과 정렬 기준**(기본적으로 **메시지 ID** 단추) 및 해당 값을 사용합니다. 와일드카드는 지원되지 않습니다. 다음 값을 기준으로 검색할 수 있습니다.

   - **메시지 ID**: 메시지의 GUID(Globally Unique Identifier)입니다. 목록에서 메시지를 선택하면 표시되는 **세부 정보** 플라이아웃 창에 **메시지 ID** 값이 표시됩니다. 관리자는 [메시지 추적](message-trace-scc.md)을 사용하여 메시지와 해당 메시지 ID 값을 찾을 수 있습니다.
   - **보낸 사람 전자 메일 주소**: 보낸 사람 한 명의 전자 메일 주소입니다.
   - **정책 이름**: 메시지의 전체 정책 이름을 사용합니다. 검색은 대/소문자를 구분하지 않습니다.
   - **받는 사람 전자 메일 주소**: 받는 사람 한 명의 전자 메일 주소입니다.
   - **제목**: 메시지의 전체 제목을 사용합니다. 검색은 대/소문자를 구분하지 않습니다.

   검색 조건을 입력한 후 ![새로 고침 단추](../../media/scc-quarantine-refresh.png) **새로 고침** 을 클릭하여 결과를 필터링합니다.

격리된 특정 메시지를 찾은 후 해당 메시지를 선택하여 세부 정보를 확인하고 메시지에 대한 작업을 수행합니다(예를 들어 메시지를 보거나, 해제하거나, 다운로드하거나, 삭제하기).

### <a name="export-message-results"></a>메시지 결과 내보내기

1. 원하는 메시지를 선택하고 **결과 내보내기** 를 클릭합니다.

2. 브라우저를 열어 두라고 경고하는 확인 메시지에서 **예** 를 클릭합니다.

3. 내보내기가 준비되면 .csv 파일에 이름을 지정하고 다운로드 위치를 선택할 수 있습니다.

### <a name="view-quarantined-message-details"></a>격리된 메시지 세부 정보 보기

목록에서 전자 메일 메시지를 선택하면 **세부 정보** 플라이아웃 창에 다음 메시지 세부 정보가 표시됩니다.

- **메시지 ID**: 메시지의 GUID(Globally Unique Identifier)입니다.
- **보낸 사람 주소**
- **수신됨**: 메시지를 수신한 날짜/시간입니다.
- **제목**
- **격리 이유**: 메시지가 **스팸**, **대량 메일** 또는 **피싱** 으로 구분되었는지를 표시합니다.
- **받는 사람**: 메시지에 받는 사람이 여러 명 있는 경우 **미리 보기 메시지** 또는 **메시지 헤더 보기** 를 클릭하여 전체 받는 사람의 목록을 확인해야 합니다.
- **만료**: 격리에서 메시지가 자동으로 영구적으로 삭제되는 날짜/시간입니다.
- **해제 대상**: 메시지가 해제된 모든 전자 메일 주소(해당되는 경우)입니다.
- **아직 해제되지 않음**: 메시지가 아직 해제되지 않은 모든 전자 메일 주소(있는 경우)입니다.

### <a name="take-action-on-quarantined-email"></a>격리된 전자 메일에 대한 작업 수행하기

메시지를 선택하면 **세부 정보** 플라이아웃 창에 메시지로 수행할 작업에 대한 옵션이 있습니다.

- **해제 메시지**: 표시되는 플라이아웃 창에서 **분석을 위해 Microsoft에 메시지를 보고** 할 것인지 선택합니다. 이 옵션은 기본적으로 선택되어 있으며 잘못 격리된 메시지를 가양성으로 Microsoft에 보고합니다.

  작업을 마쳤으면 **메시지 해제** 를 클릭합니다.

- **메시지 헤더 보기**: 메시지 헤더 텍스트를 보려면 이 링크를 선택합니다. 헤더 필드와 값을 자세히 분석하려면 메시지 헤더 텍스트를 클립보드에 복사한 다음 **Microsoft 메시지 헤더 분석기** 를 선택하여 원격 연결 분석기로 이동합니다.(이 작업을 완료하기 위해 Microsoft 365를 닫지 않으려면 마우스 오른쪽 단추를 클릭하고 **새 탭에서 열기** 를 선택합니다.) 메시지 헤더 분석기 섹션의 페이지에 메시지 헤더를 붙여넣고 **헤더 분석** 을 선택합니다.

- **메시지 미리 보기**: 표시되는 플라이아웃 창에서 다음 옵션 중 하나를 선택합니다.
  - **원본 보기**: 모든 링크를 사용하지 않도록 설정한 HTML 버전의 메시지 본문을 표시합니다.
  - **텍스트 보기**: 일반 텍스트로 메시지 본문을 표시합니다.

- **격리에서 제거하기**: 표시되는 경고에서 **예** 를 클릭하면 메시지가 즉시 삭제됩니다.

- **보낸 사람 차단**: 사서함의 수신 거부 목록에 보낸 사람을 추가합니다. 자세한 내용은 [메일 보낸 사람 차단](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)을 참조하세요.

사서함의 수신 거부 목록에 보낸 사람을 추가합니다. 자세한 내용은 [메일 보낸 사람 차단](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)을 참조하세요.

작업을 마쳤으면 **닫기** 를 클릭합니다.

메시지를 해제하거나 제거하지 않으면 기본 격리 보존 기간이 만료된 후에 삭제됩니다.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>여러 개의 격리된 전자 메일 메시지에 대한 작업 수행하기

목록에서 격리된 메시지를 여러 개(최대 100개) 선택하면 다음 **대량 전자 메일 작업** 플라이아웃 창이 나타나 다음 작업을 수행할 수 있습니다.

- **메시지 해제하기**:이 옵션은 **특정 받는사람에게 메시지 해제하기** 를 선택할 수 없는 점을 제외하고 메시지를 하나만 해제할 때와 동일합니다. **모든 받는 사람에게 메시지 해제하기** 또는 **다른 사람에게 메시지 해제하기** 만 선택할 수 있습니다.
- **메시지 삭제하기**: 표시되는 경고에서 **예** 를 클릭하면 메시지는 원래 받는 사람에게 보내지지 않고 즉시 삭제됩니다.

작업을 마쳤으면 **닫기** 를 클릭합니다.
