---
title: 관리자로 격리된 메시지 및 파일 관리
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection)의 모든 사용자에 대해 분리된 메시지를 보고 관리하는 방법을 배울 수 있습니다. Office 365용 Microsoft Defender를 사용하여 조직의 관리자는 SharePoint Online, 비즈니스용 OneDrive 및 Microsoft Teams에서 분리된 파일을 관리할 수도 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7dc7fd26d7a81bc76850af4799363c8d17fc1c83
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599538"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a>EOP에서 관리자 권한으로 격리된 메시지 및 파일 관리하기

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange online Protection) 조직에서 격리는 위험할 가능성이 있거나 원치 않는 메시지를 보유합니다. 자세한 내용은 [EOP에서 Quarantined email messages를 참조하세요.](quarantine-email-messages.md)

관리자는 모든 사용자에 대해 모든 유형의 메시지를 보고, 해제하고, 삭제할 수 있습니다. 관리자만 맬웨어, 높은 신뢰도 피싱 또는 메일 흐름 규칙(전송 규칙)의 결과로 고지된 메시지를 관리할 수 있습니다. 관리자는 Microsoft에 가의성도 보고할 수 있습니다.

Office 365용 Microsoft Defender를 사용하여 조직의 관리자는 SharePoint Online, 비즈니스용 OneDrive 및 Microsoft Teams에서 분리된 파일을 보고, 다운로드하고, 삭제할 수도 있습니다.

보안 & 준수 센터 또는 PowerShell(Exchange Online에 사서함이 있는 Microsoft 365 조직용 Exchange Online PowerShell, Exchange Online 사서함이 없는 조직의 독립 실행형 EOP PowerShell)에서 분리된 메시지를 보고 관리합니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 사항은 무엇인가요?

- 보안 및 준수 센터를 열려면 <https://protection.office.com>로 이동하세요. 격리 페이지를 바로 열려면 <https://protection.office.com/quarantine>으로 이동하세요.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요. 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- 이 게시물의 절차를 수행하려면 먼저 **Exchange Online** 에서 사용 권한을 할당받아야 합니다.
  - 모든 사용자에 대해 검역된 메시지에 대해 작업을 수행하려면 조직 **관리,** 보안 관리자 또는 **Quarantine Administrator** 역할 그룹의 <sup>\*</sup> 구성원일 수 있습니다.
  - 모든 사용자에 대해 정식으로 전송된 메시지에 대한 읽기 전용 액세스의  경우 전역 읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이면** 됩니다.

  자세한 내용은 [Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo)을 참조하세요.

  **참고**:

  - Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다. 자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.
  - <sup>\*</sup>Exchange Online PowerShell에서 절차를 수행하려면 **Quarantine Administrator** 역할 그룹의 구성원도 [Exchange Online의](/Exchange/permissions-exo/permissions-exo#role-groups) **Hygiene Management** 역할 그룹의 구성원이 해야 합니다.

- Quarantined messages are retained for a default period of time before they're automatically deleted:
  - 스팸 방지 정책(스팸, 피싱 및 대량 전자 메일)으로 차단된 메시지에 대해 30일 이 값은 기본값 및 최대값입니다. 이 값을 구성(더 낮음)으로 설정하는 내용은 스팸 방지 정책 [구성을 참조합니다.](configure-your-spam-filter-policies.md)
  - 맬웨어가 포함된 메시지의 경우 15일
  - Office 365용 Defender의 SharePoint, OneDrive 및 Microsoft Teams에 대한 안전한 첨부 파일로 15일간의 파일

  메시지가 검지에서 만료되면 복구할 수 없습니다.

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a>보안 및 & 센터를 사용하여 고지된 전자 메일 메시지 관리

### <a name="view-quarantined-email"></a>quarantined email 보기

1. 보안 및 준수 센터에서 **위협 관리** \> **검토** \> **격리** 로 이동합니다.

2. View **quarantined가** 기본값 전자 메일로 설정되어 있는지 **확인**

3. 사용 가능한 열 헤더를 클릭하여 결과를 정렬할 수 있습니다. **열 수정** 을 클릭하여 최대 7개의 열을 표시합니다. 기본값은 별표(<sup>\*</sup>)로 표시됩니다.

   - **수신됨**<sup>\*</sup>
   - **보낸 사람**<sup>\*</sup>
   - **제목**<sup>\*</sup>
   - **격리 이유**<sup>\*</sup>
   - **해제되었나요?**<sup>\*</sup>
   - **정책 유형**<sup>\*</sup>
   - **만료**
   - **받는 사람**
   - **메시지 ID**
   - **정책 이름**
   - **크기**
   - **방향**

   작업을 마쳤으면 **저장** 을 클릭하거나 **기본으로 설정** 을 클릭합니다.

4. 결과를 필터링하려면 **필터** 를 클릭합니다. 사용 가능한 필터:

   - **만료 시간**: 메시지가 격리에서 만료되는 때를 기준으로 필터링:
     - **오늘**
     - **다음 2일**
     - **다음 7일**
     - **사용자 지정**: **시작 날짜** 와 **종료 날짜** 를 입력합니다.

   - **받은 시간**: **시작 날짜** 와 **종료 날짜** 를 입력합니다.

   - **격리 이유**:
     - **정책:** 메시지가 메일 흐름 규칙의 조건과 일치합니다(전송 규칙).
     - **대량 전자 메일**
     - **피싱:** 스팸 필터 판정이 피싱 전자 메일 또는 피싱 방지 보호 [](set-up-anti-phishing-policies.md#spoof-settings) 기능으로 메시지(스푸핑 설정 또는 가장 보호)를 통해 [확인되었습니다.](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 
     - **맬웨어**
     - **스팸**
     - **높은 신뢰도 피싱**

   - **정책 유형**: 정책 유형별로 메시지를 필터링합니다.
     - **맬웨어 방지 정책**
     - **안전한 첨부 파일 정책**
     - **피싱 방지 정책**
     - **호스트된 필터 정책**(스팸 방지 정책)
     - **전송 규칙**

   - **전자 메일 받는** 사람: 모든 사용자 또는 사용자에게 보낸 메시지만 최종 사용자는 해당 사용자에게 전송된 분리된 메시지만 관리할 수 있습니다.

   필터를 지우려면 **지우기** 를 클릭합니다. 필터 플라이아웃을 숨기려면 다시 **필터** 를 클릭합니다.

5. 특정 메시지를 찾으려면 **결과 정렬 기준**(기본적으로 **메시지 ID** 단추) 및 해당 값을 사용합니다. 와일드카드는 지원되지 않습니다. 다음 값을 기준으로 검색할 수 있습니다.

   - **메시지 ID**: 메시지의 GUID(Globally Unique Identifier)입니다.

     예를 들어 메시지 [](message-trace-scc.md) 추적을 사용하여 조직의 사용자에게 전송된 메시지를 찾아 메시지가 배달된 것이 아니라 메시지에 대해 중단된 것으로 확인한 경우를 예로 들 수 있습니다. 괄호( )를 포함할 수 있는 전체 메시지 ID 값을 포함해야 \<\> 합니다. 예: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>` .

   - **보낸 사람 전자 메일 주소**: 보낸 사람 한 명의 전자 메일 주소입니다.

   - **정책 이름**: 메시지의 전체 정책 이름을 사용합니다. 검색은 대/소문자를 구분하지 않습니다.

   - **받는 사람 전자 메일 주소**: 받는 사람 한 명의 전자 메일 주소입니다.

   - **제목**: 메시지의 전체 제목을 사용합니다. 검색은 대/소문자를 구분하지 않습니다.

   - **정책 이름:** 메시지를 대리한 정책의 이름입니다.

   검색 조건을 입력한 후 ![새로 고침 단추](../../media/scc-quarantine-refresh.png) **새로 고침** 을 클릭하여 결과를 필터링합니다.

격리된 특정 메시지를 찾은 후 해당 메시지를 선택하여 세부 정보를 확인하고 메시지에 대한 작업을 수행합니다(예를 들어 메시지를 보거나, 해제하거나, 다운로드하거나, 삭제하기).

#### <a name="view-quarantined-message-details"></a>격리된 메시지 세부 정보 보기

목록에서 전자 메일 메시지를 선택하면 **세부 정보** 플라이아웃 창에 다음 메시지 세부 정보가 표시됩니다.

- **메시지 ID**: 메시지의 GUID(Globally Unique Identifier)입니다.

- **보낸 사람 주소**

- **수신됨**: 메시지를 수신한 날짜/시간입니다.

- **제목**

- **Quarantine reason:** 메시지가 **스팸,** 대량,  **피싱,** 메일 흐름 **규칙(전송** 규칙)과 일치했거나 맬웨어가 포함된 것으로 확인된 **경우를 보여 주며,**

- **받는 사람 수**

- **받는 사람**: 메시지에 받는 사람이 여러 명 있는 경우 **미리 보기 메시지** 또는 **메시지 헤더 보기** 를 클릭하여 전체 받는 사람의 목록을 확인해야 합니다.

- **만료**: 격리에서 메시지가 자동으로 영구적으로 삭제되는 날짜/시간입니다.

- **해제 대상**: 메시지가 해제된 모든 전자 메일 주소(해당되는 경우)입니다.

- **아직 해제되지 않음**: 메시지가 아직 해제되지 않은 모든 전자 메일 주소(있는 경우)입니다.

### <a name="take-action-on-quarantined-email"></a>격리된 전자 메일에 대한 작업 수행하기

메시지를 선택한 후 세부 정보 플라이아웃 창에서 메시지로  할 작업을 위한 몇 가지 옵션이 있습니다.

- **릴리스 메시지:** 나타나는 플라이아웃 창에서 다음 옵션을 선택합니다.

  - **분석을 위해 Microsoft에** 메시지 보고: 이 설정은 기본적으로 선택되어 있으며, 잘못된 메시지는 오판정으로 Microsoft에 보고합니다. 메시지가 스팸, 대량, 피싱 또는 맬웨어를 포함하는 것으로 확인된 경우 메시지도 Microsoft 스팸 분석 팀에 보고됩니다. 분석에 따라 메시지 통과를 허용하도록 서비스 전체 스팸 필터 규칙이 조정될 수 있습니다.

  - 다음 옵션 중 하나를 선택합니다.
    - **모든 받는 사람에게 메시지 릴리스**
    - **특정 받는 사람에게 메시지 릴리스**
    - **다른 사람에게** 메시지 릴리스: 원래 받는 사람이 아닌 다른 사람에게 맬웨어 메시지를 릴리스할 수 없습니다.

  작업을 마쳤으면 **메시지 해제** 를 클릭합니다.

  메시지 표시에 대한 참고 사항:

  - 같은 받는 사람에게 메시지를 두 번 이상 릴리스할 수 없습니다.
  - 메시지를 받지 않은 받는 사람만 잠재적인 받는 사람 목록에 표시됩니다.

- **메시지 헤더 보기**: 메시지 헤더 텍스트를 보려면 이 링크를 선택합니다. 헤더 필드와 값을 자세히 분석하려면 메시지 헤더 텍스트를 클립보드에 복사한 다음 **Microsoft 메시지 헤더 분석기** 를 선택하여 원격 연결 분석기로 이동합니다.(이 작업을 완료하기 위해 Microsoft 365를 닫지 않으려면 마우스 오른쪽 단추를 클릭하고 **새 탭에서 열기** 를 선택합니다.) 메시지 헤더 분석기 섹션의 페이지에 메시지 헤더를 붙여넣고 **헤더 분석** 을 선택합니다.

- **메시지 미리 보기**: 표시되는 플라이아웃 창에서 다음 옵션 중 하나를 선택합니다.
  - **원본 보기**: 모든 링크를 사용하지 않도록 설정한 HTML 버전의 메시지 본문을 표시합니다.
  - **텍스트 보기**: 일반 텍스트로 메시지 본문을 표시합니다.

- **분리에서** 제거: 나타나는 경고에서 **예를** 클릭하면 메시지가 원래 받는 사람에게 전송되지 않고 즉시 삭제됩니다.

- **메시지 다운로드하기**: 표시되는 플라이아웃 창에서 **이 메시지를 다운로드하는 데 따르는 위험을 알고 있습니다.** 를 선택하여 메시지의 로컬 복사본을 .eml 형식으로 저장합니다.

- **보낸 사람** 차단 : 보낸 사람이 조직의 받는 사람에게 메시지를 보낼 수 없습니다.

- **메시지 제출:** 플라이아웃 창이 나타나면 다음 옵션을 선택합니다.

  - **개체 유형:** **전자 메일(기본값),** **URL** 또는 첨부 **파일입니다.**

  - **전송 형식:** **네트워크 메시지** ID(기본값, 네트워크 메시지 **ID** 상자에 해당 값 사용) 또는 **파일(로컬** .eml 또는 .msg 파일 찾아보기)입니다. 파일을 **선택한** 다음 네트워크 메시지 **ID를** 선택하면 초기 값이 사라집니다.

  - **받는 사람:** 메시지를 받는 사람 한 명을  임대할 때 입력하거나 모두 선택을 클릭하여 모든 받는 사람을 식별합니다. 모두 선택을 **클릭한** 다음 개별 받는 사람을 선택적으로 제거할 수도 있습니다.

  - **제출 사유:** **차단되지** 않은 경우(기본값) 또는 **차단된 을(를) 차단해야 합니다.**

  완료되면 제출을 **클릭합니다.**

메시지를 해제하거나 제거하지 않으면 기본 격리 보존 기간이 만료된 후에 삭제됩니다.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>여러 개의 격리된 전자 메일 메시지에 대한 작업 수행하기

목록에서 격리된 메시지를 여러 개(최대 100개) 선택하면 다음 **대량 전자 메일 작업** 플라이아웃 창이 나타나 다음 작업을 수행할 수 있습니다.

- **메시지 해제하기**:이 옵션은 **특정 받는사람에게 메시지 해제하기** 를 선택할 수 없는 점을 제외하고 메시지를 하나만 해제할 때와 동일합니다. **모든 받는 사람에게 메시지 해제하기** 또는 **다른 사람에게 메시지 해제하기** 만 선택할 수 있습니다.

  > [!NOTE]
  > 다음 시나리오를 고려합니다. john@gmail.com 메시지를 faith@contoso.com john@subsidiary.contoso.com. Gmail은 이 메시지를 Microsoft에서 피싱으로 모두 검역으로 라우팅된 두 개의 복사본으로 쌍으로 처리합니다. 관리자는 이러한 두 메시지를 모두 릴리스하여 admin@contoso.com. 관리자 사서함에 도달하는 첫 번째 릴리스된 메시지가 배달됩니다. 두 번째 릴리스된 메시지는 중복 배달으로 식별되어 건너뜁니다. 메시지는 동일한 메시지 ID와 수신 시간이 있는 경우 중복 항목으로 식별됩니다.

- **메시지 삭제:** 나타나는 경고에서 **예를** 클릭하면 메시지가 원래 받는 사람에게 전송되지 않고 즉시 삭제됩니다.

작업을 마쳤으면 **닫기** 를 클릭합니다.

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a>Office 365용 Microsoft Defender만: 보안 & 준수 센터를 사용하여 분리된 파일 관리

> [!NOTE]
> 이 섹션의 quarantined files에 대한 절차는 Microsoft Defender for Office 365 계획 1 및 계획 2 구독자만 사용할 수 있습니다.

Office 365용 Defender가 있는 조직에서 관리자는 SharePoint Online, 비즈니스용 OneDrive 및 Microsoft Teams에서 분리된 파일을 관리할 수 있습니다. 이러한 파일에 대한 보호를 사용하도록 설정하려면 [SharePoint, OneDrive](turn-on-mdo-for-spo-odb-and-teams.md)및 Microsoft Teams에 대한 안전한 첨부 파일 설정을 참조합니다.

### <a name="view-quarantined-files"></a>quarantined files(Quarantined Files 보기)

1. 보안 및 준수 센터에서 **위협 관리** \> **검토** \> **격리** 로 이동합니다.

2. 값 **파일로 quarantined 보기를** **변경합니다.** 사용 가능한 열 헤더를 클릭하여 필드를 정렬할 수 있습니다.

3. 사용 가능한 열 헤더를 클릭하여 결과를 정렬할 수 있습니다. **열 수정** 을 클릭하여 최대 7개의 열을 표시합니다. 기본 열에는 다음이 표시되어 있습니다. <sup>\*</sup>

   - **사용자**<sup>\*</sup>
   - **위치**<sup>\*</sup>
   - **파일 이름**<sup>\*</sup>
   - **파일 URL**<sup>\*</sup>
   - **파일 크기**<sup>\*</sup>
   - **만료**<sup>\*</sup>
   - **해제되었나요?**<sup>\*</sup>
   - **검색한 경우**
   - **시간으로 수정**

4. 결과를 필터링하려면 **필터** 를 클릭합니다. 사용 가능한 필터:

   - **만료 시간**: 메시지가 격리에서 만료되는 때를 기준으로 필터링:
     - **오늘**
     - **다음 2일**
     - **다음 7일**
     - 사용자 지정 날짜/시간 범위입니다.
   - **받은 시간**
   - **Quarantine reason**: The only available value is **Malware**.
   - **정책 유형**

특정 고지된 파일을 찾은 후 해당 파일을 선택하여 해당 파일에 대한 세부 정보를 보고 메시지 보기, 릴리스, 다운로드 또는 삭제와 같은 작업을 수행하십시오.

#### <a name="view-quarantined-file-details"></a>quarantined file details 보기

목록에서 파일을 선택하면 세부 정보 플라이아웃 창에 다음 파일 **세부** 정보가 표시됩니다.

- **File Name**
- **파일 URL:** 파일 위치(예: SharePoint Online)를 정의하는 URL입니다.
- **검색된 악성 콘텐츠** 파일이 대리된 날짜/시간입니다.
- **만료 날짜:** 파일이 검지에서 삭제되는 날짜입니다.
- **검색:** Office 365용 Defender 또는 Microsoft의 맬웨어 방지 엔진입니다.
- **해제되었나요?**
- **맬웨어 이름**
- **문서 ID:** 문서의 고유 식별자입니다.
- **파일 크기:** KB(킬로바이트)
- **조직** 조직의 고유 ID입니다.
- **마지막으로 수정한 날짜**
- **수정한 사람:** 파일을 마지막으로 수정한 사용자입니다.
- **Secure Hash Algorithm 256비트(SHA-256) 값:** 이 해시 값을 사용하여 다른 신뢰도 저장소 또는 환경의 다른 위치에서 파일을 식별할 수 있습니다.

### <a name="take-action-on-quarantined-files"></a>고지된 파일에 대한 작업 수행

목록에서 파일을 선택하면 세부 정보 플라이아웃 창의 파일에  대해 다음 작업을 수행할 수 있습니다.

- **파일 릴리스:** 분석을 위해 **Microsoft에 보고** 파일 선택(기본값)을 선택하거나 선택을 해제한 다음 파일 **릴리스를 클릭합니다.**
- **파일 다운로드**
- **파일 제거**

파일을 해제하거나 제거하지 않는 경우 기본 검지 보존 기간이 만료된 후 삭제됩니다.

#### <a name="actions-on-multiple-quarantined-files"></a>여러 개의 고지된 파일에 대한 작업

목록에서 여러 개의 고지된 파일(최대 100개)을 선택하면 다음 작업을 수행할 수 있는 대량 작업 **플라이아웃** 창이 나타납니다.

- **파일 릴리스**
- **파일 삭제:** 나타나는 경고에서 **예를** 클릭하면 파일이 즉시 삭제됩니다.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a>Exchange Online PowerShell 또는 독립 실행형 EOP PowerShell을 사용하여 독립 실행형 메시지 및 파일 보기 및 관리

메시지와 파일을 확인 및 관리하는 데 사용하는 cmdlet은 다음을 제공합니다.

- [Delete-QuarantineMessage](/powershell/module/exchange/delete-quarantinemessage)

- [Export-QuarantineMessage](/powershell/module/exchange/export-quarantinemessage)

- [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage)

- [Preview-QuarantineMessage:](/powershell/module/exchange/preview-quarantinemessage)이 cmdlet은 메시지 전용으로, SharePoint, OneDrive 및 Microsoft Teams에 대한 안전한 첨부 파일에서 고지된 파일이 아니라 메시지에 한합니다.

- [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage)
