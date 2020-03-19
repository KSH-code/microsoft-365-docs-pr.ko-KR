---
title: Office 365에서 격리 된 메시지 및 파일을 관리자 권한으로 관리
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
description: 관리자는 모든 사용자에 대해 모든 유형의 격리 된 메시지를 보고, 해제 하 고, 삭제할 수 있습니다. 관리자만 맬웨어, 높은 신뢰도 피싱 또는 메일 흐름 규칙 (전송 규칙)의 결과로 격리 된 메시지를 관리할 수 있습니다.
ms.openlocfilehash: fdab820d2ccedaf8e4f51ba71b15d2c807d06dd1
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857081"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-office-365"></a>Office 365에서 격리 된 메시지 및 파일을 관리자 권한으로 관리

격리는 exchange Online 사서함이 없는 Exchange Online 또는 독립 실행형 EOP (Exchange Online Protection)의 사서함을 포함 하는 Office 365 조직에서 위험할 수도 있고 원치 않는 메시지를 보관 합니다. 자세한 내용은 [Office 365의 격리](quarantine-email-messages.md)를 참조 하세요.

관리자는 모든 사용자에 대해 모든 유형의 격리 된 메시지를 보고, 해제 하 고, 삭제할 수 있습니다. 관리자만 맬웨어, 높은 신뢰도 피싱 또는 메일 흐름 규칙 (전송 규칙이 라고도 함)의 결과로 격리 된 메시지를 관리할 수 있습니다. 관리자는 가양성을 Microsoft에 보고할 수도 있습니다.

Office 365의 조직에 있는 관리자는 ATP (고급 위협 방지) 에서도 SharePoint Online, 비즈니스용 OneDrive 및 Microsoft 팀에서 격리 된 파일을 보고, 다운로드 하 고, 삭제할 수 있습니다.

보안 & 준수 센터 또는 PowerShell (Office 365 고객을 위한 Exchange Online PowerShell)에서 격리 된 메시지를 보고 관리 합니다. 독립 실행형 EOP 고객을 위한 Exchange Online Protection PowerShell

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용

- Office 365 보안 & 준수 센터를 열려면로 <https://protection.office.com>이동 합니다. 격리 페이지를 바로 열려면로 <https://protection.office.com/quarantine>이동 합니다.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)을 참조하세요. Exchange Online Protection PowerShell에 연결 하려면 [Exchange Online Protection powershell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)을 참조 하세요.

- 관리자로 격리를 관리 하려면 먼저 사용 권한을 할당 받아야 합니다. 사용 권한은 보안 & 준수 센터에서 **격리** 역할에 의해 제어 됩니다. 기본적으로이 역할은 보안 & 준수 센터의 **조직 관리** (전역 관리자), **격리 관리자**및 **보안 관리자** 역할 그룹에 할당 됩니다. 자세한 내용은 [Office 365 보안 & 준수 센터의 사용 권한을](permissions-in-the-security-and-compliance-center.md)참조 하세요.

- 격리 된 메시지는 자동으로 삭제 되기 전에 기본 기간 동안 보존 됩니다.

  - 스팸 방지 정책 (스팸, 피싱 및 대량 전자 메일)에 의해 격리 된 메시지: 30 일 이 값은 기본값 및 최대값입니다. 이 값을 구성 하려면 [Office 365에서 스팸 방지 정책 구성을](configure-your-spam-filter-policies.md)참조 하세요.

  - 메일 흐름 규칙에 의해 격리 된 메시지 (규칙 동작은 **메시지를 호스트 된 격리로 배달**): 30 일 이 값은 변경할 수 없습니다.

  - 맬웨어가 포함 된 메시지: 15 일

  메시지가 격리에서 만료 되는 경우에는 복구할 수 없습니다.

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a>보안 & 준수 센터를 사용 하 여 격리 된 전자 메일 메시지 관리

### <a name="view-quarantined-email"></a>격리 된 전자 메일 보기

1. 보안 및 준수 센터에서 **위협 관리** \> **검토** \> **격리**로 이동 합니다.

2. 격리 된 **보기가** 기본값 **전자 메일로**설정 되어 있는지 확인 합니다.

3. 사용 가능한 열 머리글을 클릭 하 여 결과를 정렬할 수 있습니다. **열 수정을** 클릭 하 여 최대 7 개의 열을 표시 합니다. 기본값은 별표 (<sup>\*</sup>)로 표시 됩니다.

   - **Received**<sup>\*</sup>

   - **보낸 사람**<sup>\*</sup>

   - **제목**<sup>\*</sup>

   - **격리 이유**<sup>\*</sup>

   - **해제할?**<sup>\*</sup>

   - **정책 유형**<sup>\*</sup>

   - **Expires**<sup>\*</sup>

   - **받는 사람**

   - **메시지 ID**

   - **정책 이름**

   - **크기**

   - **방향**

   작업이 끝나면 **저장**을 클릭 하거나 **기본값으로 설정을**클릭 합니다.

4. 결과를 필터링 하려면 **필터**를 클릭 합니다. 사용 가능한 필터는 다음과 같습니다.

   - **만료 시간**: 격리에서 만료 될 때에 따라 메시지를 필터링 합니다.

     - **근래**

     - **다음 2 일**

     - **다음 7 일**

     - **사용자 지정**: **시작 날짜** 와 **끝 날짜**를 입력 합니다.

   - **받은 시간**: **시작 날짜** 와 **끝 날짜**를 입력 합니다.

   - **격리 이유**:

     - **정책**: 메시지가 메일 흐름 규칙 (전송 규칙이 라고도 함)의 조건과 일치 합니다.

     - **대량 메일**

     - **피싱**

     - **맬웨어**

     - **스팸**

     - **높은 신뢰도 피싱**

   - **전자 메일 받는 사람**: 모든 사용자 또는 자신에 게 전송 되는 메시지에만 해당 합니다. 최종 사용자가 보낸 격리 된 메시지만 관리할 수 있습니다.

   필터를 지우려면 **지우기를**클릭 합니다. 필터 플라이 아웃을 숨기려면 다시 **필터링** 을 클릭 합니다.

5. **결과 정렬 기준** (기본적으로 **메시지 ID** 단추) 및 해당 값을 사용 하 여 특정 메시지를 찾습니다. 와일드카드는 지원되지 않습니다. 다음 값을 기준으로 검색할 수 있습니다.

   - **메시지 ID**: 메시지의 guid (globally unique identifier)입니다.

        예를 들어 [메시지 추적](message-trace-scc.md) 을 사용 하 여 조직의 사용자에 게 전송 된 메시지를 찾고 메시지가 배달 되지 않고 격리 되었음을 확인 했습니다. 전체 메시지 ID 값에는 꺾쇠 괄호 (\<\>)가 포함 될 수 있습니다. 예: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.

   - **보낸 사람 전자 메일 주소**: 보낸 사람의 전자 메일 주소입니다.

   - **받는 사람 전자 메일 주소**: 받는 사람의 전자 메일 주소입니다.

   - **제목**: 메시지의 전체 제목을 사용 합니다. 검색에서 대/소문자를 구분 하지 않습니다.

   검색 조건을 입력 한 후 새로 고침 단추 ![](../media/scc-quarantine-refresh.png) **새로** 고침을 클릭 하 여 결과를 필터링 합니다.

격리 된 특정 메시지를 찾은 후에는 메시지를 선택 하 여 자세한 정보를 확인 하 고 메시지에 대 한 작업을 수행 (예: 보기, 릴리스, 다운로드 또는 삭제) 합니다.

#### <a name="export-message-results"></a>메시지 결과 내보내기

1. 관심 있는 메시지를 선택 하 고 **결과 내보내기를**클릭 합니다.

2. 브라우저 창을 열어 둘 것을 경고 하는 확인 메시지에서 **예** 를 클릭 합니다.

3. 내보내기가 준비 되 면 .csv 파일의 이름을 선택 하 고 다운로드 위치를 선택할 수 있습니다.

#### <a name="view-quarantined-message-details"></a>격리 된 메시지 세부 정보 보기

목록에서 전자 메일 메시지를 선택 하면 **세부 정보** 플라이 아웃 창에 다음과 같은 메시지 정보가 표시 됩니다.

- **메시지 ID**: 메시지의 guid입니다.

- **보낸 사람 주소**

- **Received**: 메시지를 받은 날짜/시간입니다.

- **제목**

- **격리 이유**: 메시지가 **스팸으로**식별 되었는지, **대량**, **피싱**, 일치 하는 메일 흐름 규칙 (**전송 규칙**) 인지 또는 **악성 프로그램**을 포함 하는 것으로 확인 된 경우를 표시 합니다.

- **받는 사람**: 메시지에 받는 사람이 여러 개 있는 경우 **메시지 미리 보기** 또는 **메시지 헤더 보기** 를 클릭 하 여 받는 사람의 전체 목록을 확인 해야 합니다.

- **Expires**: 메시지를 자동으로 제거 하 고 격리에서 영구적으로 삭제 하는 날짜/시간입니다.

- **해제 대상**: 메시지가 해제된 모든 전자 메일 주소(해당되는 경우)입니다.

- **아직 릴리스되지**않음: 메시지가 아직 릴리스되지 않은 모든 전자 메일 주소 (있는 경우)입니다.

### <a name="take-action-on-quarantined-email"></a>격리 된 전자 메일에 대해 작업 수행

메시지를 선택한 후에는 **세부 정보** 플라이 아웃 창에서 메시지에 대해 수행할 작업을 여러 가지 방법으로 사용할 수 있습니다.

- **릴리스 메시지**: 표시 된 플라이 아웃 창에서 다음 옵션을 선택 합니다.

  - **Microsoft에 분석을 위해 메시지를 보고**:이 기능은 기본적으로 선택 되며 잘못 격리 된 메시지를 microsoft에 가양성으로 보고 합니다. 메시지가 스팸으로, 대량, 피싱 또는 맬웨어를 포함 하는 것으로 격리 된 경우 메시지는 Microsoft 스팸 분석 팀에도 보고 됩니다. 분석에 따라 메시지를 통과 하도록 허용 하도록 서비스 수준 스팸 필터 규칙을 조정할 수 있습니다.

  - 다음 옵션 중 하나를 선택 합니다.

    - **모든 받는 사람에 게 메시지를 놓습니다.**

    - **특정 받는 사람에 게 메시지를 놓습니다.**

    - **다른 사람에 게 메시지를 놓습니다.**

  작업이 끝나면 **메시지 릴리스**를 클릭 합니다.

  메시지 해제에 대 한 참고 사항:

  - 메시지를 동일한 받는 사람에 게 두 번 이상 릴리스할 수 없습니다.

  - 메시지를 받지 않은 받는 사람만 잠재 받는 사람 목록에 표시 됩니다.

- **메시지 헤더 보기**: 메시지 헤더 텍스트를 보려면이 링크를 선택 합니다. 머리글 필드 및 값을 깊이로 분석 하려면 메시지 헤더 텍스트를 클립보드에 복사한 다음, **Microsoft 메시지 헤더 분석기** 를 선택 하 여 원격 연결 분석기로 이동 합니다 (Office 365에서이 작업을 완료 하도록 하려면 **새 탭에서 열기** 를 선택 합니다). 메시지 헤더 분석기 섹션의 페이지에 메시지 헤더를 붙여 넣은 다음 **헤더 분석**을 선택 합니다.

- **Preview message**: 표시 된 플라이 아웃 창에서 다음 옵션 중 하나를 선택 합니다.

  - **원본 보기**: 모든 링크가 사용 하지 않도록 설정 된 메시지 본문의 HTML 버전을 표시 합니다.
  
  - **텍스트 보기**: 메시지 본문을 일반 텍스트로 표시 합니다.

- **격리에서 제거**: 표시 되는 경고에서 **예** 를 클릭 하면 메시지가 원래 받는 사람에 게 전송 되지 않고 즉시 삭제 됩니다.

- **다운로드 메시지**: 표시 되는 플라이 아웃 창에서 **이 메시지를 다운로드할** 때 발생할 수 있는 위험을 이해 합니다 .를 선택 하 여 메시지의 로컬 복사본을 .eml 형식으로 저장 합니다.

- **전송 메시지**: 표시 된 플라이 아웃 창에서 다음 옵션을 선택 합니다.

  - **개체 유형**: **Email** (기본값), **URL**또는 **Attachment**

  - **전송 형식**: **네트워크 메시지 id** (기본값으로, **네트워크 메시지 id** 상자의 해당 값 포함) 또는 **파일** (로컬 .eml 또는 .msg 파일 찾아보기) **파일** 을 선택한 다음 **네트워크 메시지 ID**를 선택 하면 초기 값이 사라집니다.

  - **받는 사람**: 메시지의 원래 받는 사람 하나를 임대에 입력 하거나, **모두 선택을** 클릭 하 여 모든 받는 사람을 식별 합니다. **모두 선택을** 클릭 한 다음 개별 받는 사람을 선택적으로 제거할 수도 있습니다.

  - **전송 사유**: **차단** 되지 않았거나 (기본값) **차단**되어 있어야 합니다.

  작업이 완료 되 면 **제출을**클릭 합니다.

메시지를 해제 하거나 제거 하지 않으면 기본 격리 보존 기간이 만료 된 후에 삭제 됩니다.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>격리 된 여러 전자 메일 메시지에 대해 작업 수행

목록에서 격리 된 메시지를 여러 개 (최대 100 개) 선택 하면 다음 작업을 수행할 수 있는 **대량 작업** 플라이 아웃 창이 나타납니다.

- **릴리스 메시지**: 옵션은 **특정 받는 사람에 대 한 메시지 릴리스**를 선택할 수 없다는 점을 제외 하 고는 단일 메시지를 놓을 때와 동일 합니다. **모든 받는 사람에 대 한 메시지 릴리스를** 선택 하거나 **다른 사용자에 게 메시지를 놓을**수만 있습니다.

- **메시지 삭제**: 표시 되는 경고에서 **예** 를 클릭 하면 원래 받는 사람에 게 메시지를 보내지 않고 메시지가 즉시 삭제 됩니다.

작업이 완료 되 면 **닫기를**클릭 합니다.

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a>ATP 전용: 보안 & 준수 센터를 사용 하 여 격리 된 파일 관리

> [!NOTE]
> 이 섹션에서 격리 된 파일의 절차는 ATP 계획 1 및 계획 2 구독자만 사용할 수 있습니다.

ATP가 있는 조직에서는 관리자가 격리 된 파일을 SharePoint Online, 비즈니스용 OneDrive 및 Microsoft 팀에서 관리할 수 있습니다.

### <a name="view-quarantined-files"></a>격리 된 파일 보기

1. 보안 및 준수 센터에서 **위협 관리** \> **검토** \> **격리**로 이동 합니다.

2. **격리 된 보기** 를 기본 값 **파일로**변경 합니다. 사용 가능한 열 머리글을 클릭 하 여 필드를 정렬할 수 있습니다.

3. 사용 가능한 열 머리글을 클릭 하 여 결과를 정렬할 수 있습니다. **열 수정을** 클릭 하 여 최대 7 개의 열을 표시 합니다. 기본 열에는 별표 (<sup>\*</sup>)가 표시 됩니다.

   - **사용자**<sup>\*</sup>

   - **위치나**<sup>\*</sup>

   - **파일 이름**<sup>\*</sup>

   - **파일 URL**<sup>\*</sup>

   - **파일 크기**<sup>\*</sup>

   - **Expires**<sup>\*</sup>

   - **해제할?**<sup>\*</sup>

   - **검색 기준**

   - **시간별로 수정한 날짜**

4. 결과를 필터링 하려면 **필터**를 클릭 합니다. 사용 가능한 필터는 다음과 같습니다.

   - **만료 시간**: 격리에서 만료 될 때에 따라 메시지를 필터링 합니다.

     - **근래**

     - **다음 2 일**

     - **다음 7 일**

     - 사용자 지정 날짜/시간 범위입니다.

   - **받은 시간**

   - **격리 이유**: **맬웨어**는 사용 가능한 유일한 값입니다.

격리 된 특정 파일을 찾은 후 파일을 선택 하 여 자세한 정보를 확인 하 고 메시지에 대 한 작업을 수행 (예: 보기, 릴리스, 다운로드 또는 삭제) 합니다.

#### <a name="export-file-results"></a>파일 내보내기 결과

1. 관심 있는 파일을 선택 하 고 **결과 내보내기를**클릭 합니다.

2. 브라우저 창을 열어 둘 것을 경고 하는 확인 메시지에서 **예** 를 클릭 합니다.

3. 내보내기가 준비 되 면 .csv 파일의 이름을 선택 하 고 다운로드 위치를 선택할 수 있습니다.

#### <a name="view-quarantined-file-details"></a>격리 된 파일 세부 정보 보기

목록에서 파일을 선택 하면 **세부 정보** 플라이 아웃 창에 다음과 같은 파일 세부 정보가 표시 됩니다.

- **File Name**

- **파일 URL**: 파일의 위치 (예: SharePoint Online)를 정의 하는 url입니다.

- **에서 발견 된 악의적인 콘텐츠** 파일을 격리 한 날짜/시간입니다.

- **Expires**: 파일이 격리에서 삭제 되는 날짜입니다.

- **검색 한 사람**: ATP (Advanced Threat Protection) 또는 Microsoft의 맬웨어 방지 엔진

- **해제할?**

- **맬웨어 이름**

- **문서 ID**: 문서에 대 한 고유 식별자입니다.

- **파일 크기**(kb)입니다.

- **조직** 조직의 고유한 ID입니다.

- **마지막으로 수정한 날짜**

- **수정한 사람**: 파일을 마지막으로 수정한 사용자입니다.

- **보안 해시 알고리즘 256 비트 (SHA-256) 값**:이 해시 값을 사용 하 여 다른 신뢰도 저장소 또는 환경의 다른 위치에서 파일을 식별할 수 있습니다.

### <a name="take-action-on-quarantined-files"></a>격리 된 파일에 대 한 작업 수행

목록에서 파일을 선택 하면 **세부 정보** 플라이 아웃 창에서 파일에 대해 다음 작업을 수행할 수 있습니다.

- **파일 릴리스**: **분석을 위해 Microsoft에 보고서 파일을**선택 하거나 선택을 취소 한 다음 **파일 릴리스**를 클릭 합니다.

- **파일 다운로드**

- **격리에서 파일 제거**

파일을 해제 하거나 제거 하지 않으면 기본 격리 보존 기간이 만료 된 후에 파일이 삭제 됩니다.

#### <a name="actions-on-multiple-quarantined-files"></a>여러 격리 된 파일에 대 한 작업

목록에서 격리 된 파일을 여러 개 선택 하면 (최대 100) 다음과 같은 작업을 수행할 수 있는 **대량 작업** 플라이 아웃 창이 나타납니다.

- **파일 릴리스**

- **파일 삭제**: 표시 되는 경고에서 **예** 를 클릭 하면 파일이 즉시 삭제 됩니다.

작업이 완료 되 면 **닫기를**클릭 합니다.

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-view-and-manage-quarantined-messages-and-files"></a>Exchange Online PowerShell 또는 독립 실행형 Exchange Online Protection PowerShell을 사용 하 여 격리 된 메시지 및 파일 보기 및 관리

격리에서 메시지와 파일을 보고 관리 하는 데 사용 하는 cmdlet은 다음과 같습니다.

- [Delete-Get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/delete-quarantinemessage)

- [Get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/export-quarantinemessage)

- [Get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)

- [Preview-get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage):이 Cmdlet은 SharePoint Online, 비즈니스용 OneDrive 또는 팀에 대 한 ATP 파일이 아닌 메시지에만 해당 합니다.

- [Get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)
