---
title: 관리자 전송
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 관리자는 보안 & 준수 센터에서 전송 포털을 사용 하 여 의심 스러운 전자 메일, 의심 되는 피싱 메일, 스팸 및 기타 해로운 메시지, Url 및 파일을 검색을 위해 Microsoft에 제출 하는 방법에 대해 알아볼 수 있습니다.
ms.openlocfilehash: be2fc8e41e3b53923b0297f30dfb102bbabd7489
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877270"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>관리자 제출을 사용하여 의심스러운 스팸, 피싱, URL 및 파일을 Microsoft에 제출

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online의 사서함이 있는 Microsoft 365 조 직에서는 관리자가 보안 & 준수 센터의 전송 포털을 사용 하 여 검색을 위해 전자 메일 메시지, Url 및 첨부 파일을 Microsoft에 제출할 수 있습니다.

전자 메일을 제출 하면 메일에 포함 된 Url 및 첨부 파일을 검사 하는 것은 물론 수신 전자 메일을 허용 했을 수 있는 모든 정책에 대 한 정보를 받게 됩니다. 메일을 허용할 수 있는 정책에는 개별 사용자의 수신 허용-보낸 사람 목록 뿐 아니라 Exchange 메일 흐름 규칙 (전송 규칙이 라고도 함)과 같은 테 넌 트 수준 정책이 포함 됩니다.

전자 메일 메시지, Url 및 첨부 파일을 Microsoft에 전송 하는 다른 방법에 대 한 자세한 내용은 [Report messages and files In microsoft](report-junk-email-messages-to-microsoft.md)를 참조 하십시오.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 준수 센터를 엽니다. **제출** 페이지로 바로 이동 하려면을 사용 <https://protection.office.com/reportsubmission> 합니다.

- 메시지 및 파일을 Microsoft에 전송 하려면 다음 역할 그룹 중 하나의 구성원 이어야 합니다.

  - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**

  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리**

    이 항목의 뒷부분에 설명 된 대로 사용자 [지정 사서함에 대 한 사용자 제출을 확인](#view-user-submissions-to-the-custom-mailbox) 하려면이 역할 그룹의 구성원 이어야 합니다.

- 사용자가 메시지 및 파일을 Microsoft에 전송 하는 방법에 대 한 자세한 내용은 [Report messages and files In microsoft를](report-junk-email-messages-to-microsoft.md)참조 하십시오.

## <a name="report-suspicious-content-to-microsoft"></a>의심 스러운 콘텐츠를 Microsoft에 보고

1. 보안 & 준수 센터에서 **위협 관리** \> **전송** 으로 이동 하 여 **관리자의 제안** 탭에 있는지 확인 하 고 **새 제출을** 클릭 합니다.

2. 다음 섹션에 설명 된 대로 메시지, URL 또는 첨부 파일을 전송 하는 것 처럼 보이는 **새 전송** 플라이 아웃을 사용 합니다.

### <a name="submit-a-questionable-email-to-microsoft"></a>Microsoft에 의심 스러운 전자 메일 제출

1. **개체 유형** 섹션에서 **전자 메일** 을 선택 합니다. **전송 형식** 섹션에서 다음 옵션 중 하나를 사용 합니다.

   - **네트워크 메시지 id** : 메시지의 **X-Exchange-네트워크 메시지 ID** 헤더에서 사용할 수 있는 GUID 값입니다.

   - **파일** : **파일 선택을** 클릭 합니다. 대화 상자가 열리면 .eml 또는 .msg 파일을 찾아 선택한 다음 **열기** 를 클릭 합니다.

2. **받는 사람** 섹션에서 정책을 확인 하기 위해 실행할 받는 사람을 한 명 이상 지정 합니다. 정책 확인에서는 사용자 또는 조직 정책으로 인해 전자 메일에서 검색을 통과 하지 않는지 확인 합니다.

3. **제출 사유** 섹션에서 다음 옵션 중 하나를 선택 합니다.

   - **차단 되지 않아야 합니다.**

   - **차단 됨** : **스팸** , **피싱** 또는 **맬웨어** 를 선택 합니다. 확실히 모르겠으면 가장 좋은 판단을 사용 하세요.

4. 전송 시 정책으로 인해 필터가 생략 되 면 해당 정책에 대 한 정보를 볼 수 있습니다.

   하나 이상의 정책으로 인해 필터가 무시 되지 않으면 몇 분 안에 검색이 완료 됩니다. 상태 링크를 클릭 하 여 전송에 대 한 추가 정보를 볼 수 있습니다. 여기에는 정책 확인 및 다시 검사 결과의 결과가 포함 됩니다. 참고 Microsoft Defender for Office 365 full 필터링 스택을 통해 전자 메일을 다시 실행 하지만 메일, URL 또는 파일의 특정 특성에 따라 부분 다시 검사를 실행 하는 것은 아닙니다.

5. 작업이 끝나면 **Submit (제출** ) 단추를 클릭 합니다.

![URL 전송 예](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>Microsoft에 의심 스러운 URL 보내기

1. **개체 유형** 섹션에서 **URL** 을 선택 합니다. 상자가 나타나면 전체 URL (예:)을 입력 합니다 `https://www.fabrikam.com/marketing.html` .

2. **제출 사유** 섹션에서 다음 옵션 중 하나를 선택 합니다.

   - **차단 되지 않아야 합니다.**

   - **차단 되어야** 하는 경우: **피싱** 또는 **맬웨어** 를 선택 합니다.

3. 작업이 끝나면 **Submit (제출** ) 단추를 클릭 합니다.

![전자 메일 전송 예](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a>Microsoft에 의심 스러운 파일 제출

1. **개체 유형** 섹션에서 **첨부 파일** 을 선택 합니다.

2. **파일 선택을** 클릭 합니다. 대화 상자가 열리면 파일을 찾아 선택한 다음 **열기** 를 클릭 합니다.

3. **제출 사유** 섹션에서 다음 옵션 중 하나를 선택 합니다.

   - **차단 되지 않아야 합니다.**

   - **차단 됨** : **맬웨어가** 유일한 선택 항목 이며 자동으로 선택 됩니다.

4. 작업이 끝나면 **Submit (제출** ) 단추를 클릭 합니다.

![첨부 파일 전송 예](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a>관리자 전송 보기

보안 & 준수 센터에서 **위협 관리** \> **전송** 으로 이동 하 여 **관리자의 제안** 탭에 있는지 확인 하 고 **새 제출을** 클릭 합니다.

페이지 맨 위에 있는 시작 날짜와 끝 날짜를 입력할 수 있으며, 기본적으로 상자에 값을 입력 하 고 새로 고침 단추를 클릭 하 여 **전송 ID** (모든 전송에 할당 된 GUID 값)를 기준으로 필터링 할 수 있습니다 ![ ](../../media/scc-quarantine-refresh.png) . Update

필터 조건을 변경 하려면 **제출 ID** 단추를 클릭 하 고 다음 값 중 하나를 선택 합니다.

- **보낸 사람**
- **제목/u i/파일 이름**
- **제출한 사람**
- **전송 유형**
- **상태**

![관리자 전송에 대 한 필터 옵션](../../media/admin-submission-email-filter-options.png)

결과를 내보내려면 페이지 위쪽에서 **내보내기를** 클릭 하 고 **차트 데이터** 또는 **표** 를 선택 합니다. 대화 상자가 나타나면 .csv 파일을 저장 합니다.

그래프 아래에는 **전자 메일** (기본값), **URL** 및 **첨부 파일** 의 세 가지 탭이 있습니다.

### <a name="view-admin-email-submissions"></a>관리자 전자 메일 전송 보기

**전자 메일** 탭을 클릭 합니다.

페이지 아래쪽에 있는 **열 옵션** 단추를 클릭 하 여 보기에서 열을 추가 하거나 제거할 수 있습니다.

- **날짜**
- **전송 ID** : 모든 전송에 할당 되는 GUID 값입니다.
- **제출한 사람**<sup>\*</sup>
- **제목**<sup>\*</sup>
- **보낸 사람**
- **보낸 사람 IP**<sup>\*</sup>
- **전송 유형**
- **배달 이유**
- **상태별**<sup>\*</sup>
- **컨트롤 형식**
- **컨트롤 원본**

  <sup>\*</sup> 이 값을 클릭 하면 자세한 정보가 플라이 아웃에 표시 됩니다.

### <a name="view-admin-url-submissions"></a>관리자 URL 전송 보기

**URL** 탭을 클릭 합니다.

페이지 아래쪽에 있는 **열 옵션** 단추를 클릭 하 여 보기에서 열을 추가 하거나 제거할 수 있습니다.

- **날짜**
- **전송 ID**
- **제출한 사람**<sup>\*</sup>
- **URL**<sup>\*</sup>
- **전송 유형**
- **상태별**<sup>\*</sup>

  <sup>\*</sup> 이 값을 클릭 하면 자세한 정보가 플라이 아웃에 표시 됩니다.

### <a name="view-admin-attachment-submissions"></a>관리자 첨부 파일 전송 보기

**첨부 파일** 탭을 클릭 합니다.

페이지 아래쪽에 있는 **열 옵션** 단추를 클릭 하 여 보기에서 열을 추가 하거나 제거할 수 있습니다.

- **날짜**
- **전송 ID**
- **제출한 사람**<sup>\*</sup>
- **파일 이름**<sup>\*</sup>
- **전송 유형**
- **상태별**<sup>\*</sup>

  <sup>\*</sup> 이 값을 클릭 하면 자세한 정보가 플라이 아웃에 표시 됩니다.

## <a name="view-user-submissions-to-microsoft"></a>Microsoft에 대 한 사용자 제출을 확인 합니다.

[보고서 메시지 추가 기능](enable-the-report-message-add-in.md)을 배포 했거나 사용자가 [웹에서 Outlook의 기본 제공 보고](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)를 사용 하는 경우 **사용자 전송** 탭에서 사용자에 게 보고 하는 항목을 확인할 수 있습니다.

1. 보안 & 준수 센터에서 **위협 관리** \> **전송** 으로 이동 합니다.

2. **사용자 전송** 탭을 선택한 다음 **새 제출을** 클릭 합니다.

페이지 아래쪽에 있는 **열 옵션** 단추를 클릭 하 여 보기에서 열을 추가 하거나 제거할 수 있습니다.

- **제출 된 날짜**
- **제출한 사람**<sup>\*</sup>
- **제목**<sup>\*</sup>
- **보낸 사람**
- **보낸 사람 IP**<sup>\*</sup>
- **전송 유형**

<sup>\*</sup> 이 값을 클릭 하면 자세한 정보가 플라이 아웃에 표시 됩니다.

페이지 맨 위에 있는 시작 날짜와 끝 날짜를 입력할 수 있으며, 기본적으로 상자에 값을 입력 하 고 새로 고침 단추를 클릭 하 여 **보낸 사람** 을 기준으로 필터링 할 수 있습니다 ![ ](../../media/scc-quarantine-refresh.png) . Update

필터 조건을 변경 하려면 **보낸 사람** 단추를 클릭 하 고 다음 값 중 하나를 선택 합니다.

- **보낸 사람 도메인**
- **제목**
- **제출한 사람**
- **전송 유형**
- **보낸 사람 IP**

![사용자 전송에 대 한 필터 옵션](../../media/user-submissions-filter-options.png)

결과를 내보내려면 페이지 위쪽에서 **내보내기를** 클릭 하 고 **차트 데이터** 또는 **표** 를 선택 합니다. 대화 상자가 나타나면 .csv 파일을 저장 합니다.

## <a name="view-user-submissions-to-the-custom-mailbox"></a>사용자 지정 사서함에 대 한 사용자 전송 보기

사용자가 보고 한 메시지를 수신 하도록 [사용자 지정 사서함을 구성한](user-submission.md) **경우** 보고 사서함으로 배달 된 메시지를 확인 하 고 제출할 수 있습니다.

1. 보안 & 준수 센터에서 **위협 관리** \> **전송** 으로 이동 합니다.

2. **사용자 지정 사서함** 탭을 선택 합니다.

페이지 아래쪽에 있는 **열 옵션** 단추를 클릭 하 여 보기에서 열을 추가 하거나 제거할 수 있습니다.

- **제출 된 날짜**
- **제출한 사람**<sup>\*</sup>
- **제목**<sup>\*</sup>
- **보낸 사람**
- **보낸 사람 IP**<sup>\*</sup>
- **전송 유형**

페이지 위쪽에 있는 시작 날짜, 종료 날짜를 입력 하 고 상자에 값을 입력 하 고 새로 고침 단추를 **클릭 하 여** 필터링 하 여 필터할 수 있습니다 ![ ](../../media/scc-quarantine-refresh.png) . Update

결과를 내보내려면 페이지 위쪽에서 **내보내기를** 클릭 하 고 **차트 데이터** 또는 **표** 를 선택 합니다. 대화 상자가 나타나면 .csv 파일을 저장 합니다.

## <a name="undo-user-submissions"></a>사용자 전송 실행 취소

사용자가 의심 스러운 전자 메일을 사용자 지정 사서함에 전송 하면 사용자 및 관리자에 게 제출을 취소할 수 있는 옵션이 표시 되지 않습니다. 사용자가 전자 메일을 복구 하려는 경우에는 삭제 된 항목 또는 정크 메일 폴더에서 복구할 수 있습니다. 

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>사용자 지정 사서함에서 Microsoft로 메시지 전송

Microsoft에 메시지를 보내지 않고 사용자가 보고 한 메시지를 가로채는 사용자 지정 사서함을 구성한 경우 분석을 위해 특정 메시지를 찾아서 Microsoft로 보낼 수 있습니다. 이렇게 하면 사용자 제출을 관리자 제출으로 이동 됩니다.

**사용자 지정 사서함** 탭의 목록에서 메시지를 선택 하 고 **실행** 단추를 클릭 한 후 다음 중 하나를 선택 합니다.

- **보고서 정리**
- **신고 피싱**
- **맬웨어 보고**
- **스팸 보고**

![실행 단추 옵션](../../media/user-submission-custom-mailbox-action-button.png)
