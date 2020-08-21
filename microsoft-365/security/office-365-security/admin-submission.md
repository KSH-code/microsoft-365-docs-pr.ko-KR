---
title: 관리자 제출
f1.keywords:
- NOCSH
ms.author: chrisda
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
ms.custom:
- seo-marvel-apr2020
description: 관리자는 보안 & 규정 준수 센터에서 제출 포털을 사용하여 의심스러운 전자 메일, 의심스러운 피싱 메일, 스팸 및 기타 잠재적으로 유해한 메시지, URL 및 파일을 검사하도록 Microsoft에 제출하는 방법을 학습할 수 있습니다.
ms.openlocfilehash: 1b3715e3ed6f0472d9202573ff0cab92f7240ffa
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845969"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>관리자 제출을 사용하여 의심스러운 스팸, 피싱, URL 및 파일을 Microsoft에 제출

Exchange Online의 사서함이 있는 Microsoft 365 조직에서 관리자는 보안 & 준수 센터의 전송 포털을 사용하여 스캐시팅을 위해 Microsoft에 전자 메일 메시지, URL 및 첨부 파일을 제출할 수 있습니다.

전자 메일을 제출하면 테넌트로 받는 전자 메일을 허용한 정책과 메일의 URL 및 첨부 파일을 검사하는 방법에 대한 정보를 얻게 됩니다. 메일이 허용될 수 있는 정책에는 개별 사용자의 수신 허용 - 보낸 사람 목록 및 테넌트 수준 정책(예: Exchange 메일 흐름 규칙이라고도 함)이 포함됩니다.

Microsoft에 전자 메일 메시지, URL 및 첨부 파일을 전송하는 다른 방법은 [Microsoft에 보고 메시지 및 파일을 참조하세요.](report-junk-email-messages-to-microsoft.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 준수 센터를 엽니다. 제출 페이지로 직접 **이동하려면** 을 <https://protection.office.com/reportsubmission> 사용합니다.

- 이 항목의 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.

  - 메시지와 파일을 Microsoft에 제출하려면 다음 역할 그룹 중 하나의 구성원이어야 합니다.

    - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리** 및 **예방 조치 관리**

  - 제출 포털에 대한 읽기 전용 액세스를 위해는 다음 역할 그룹 중 하나의 구성원이어야 합니다.

    - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **보안 읽기**
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리**

- 사용자가 Microsoft에 메시지와 파일을 제출하는 방법에 대한 자세한 내용은 Microsoft에 [보고 메시지 및 파일을 참조하세요.](report-junk-email-messages-to-microsoft.md)

## <a name="report-suspicious-content-to-microsoft"></a>Microsoft에 의심스러운 콘텐츠 보고

1. 보안 규정 준수 & 제출로 이동하여 **위협 관리** \> **Submissions**제출로 이동하고 관리자 제출 **탭에 있는지** 확인한 후 새 제출을 **클릭합니다.**

2. 다음 **섹션의** 설명에 따라 메시지, URL 또는 첨부 파일을 전송하는 데 나타나는 새 전송 플라이아웃을 사용합니다.

### <a name="submit-a-questionable-email-to-microsoft"></a>Microsoft에 질문할 수 있는 메일 제출

1. Section in the **Object type** section, select **Email.** 전송 형식 **섹션에서 다음** 옵션 중 하나를 사용합니다.

   - **네트워크 메시지 ID**: 메시지의 **X-MS-Exchange-Organization-Network-Message-Id 헤더에서** 사용할 수 있는 GUID 값입니다.

   - **파일:** 파일 **선택을 클릭합니다.** 대화 상자가 열리면 .eml 또는 .msg 파일을 찾아서 선택한 후 열기를 **클릭합니다.**

2. 받는 **사람** 섹션에서 정책 확인을 실행될 받는 사람을 한 명 이상 지정합니다. 정책 검사에서는 사용자 또는 조직 정책으로 인해 이메일 검사를 무시하는지 여부를 확인합니다.

3. 제출 **이유 섹션에서** 다음 옵션 중 하나를 선택합니다.

   - **차단하지 않아요**

   - **스팸, 피싱**또는 **맬웨어** **선택을 차단해야** **합니다.** 부합하지 않을 경우 최상의 조각을 사용하세요.

4. 전송 시 정책으로 인해 필터가 무시된 경우 해당 정책에 대한 정보가 표시됩니다.

   하나 이상의 정책으로 인해 필터가 무시되지 않은 경우 몇 분 내에 검사가 완료됩니다. 상태 링크를 클릭하여 제출에 대한 추가 정보가 표시됩니다. 여기에는 정책 검사 결과와 재검사 결과가 포함됩니다. 이 작업은 Office 365 ATP 전체 필터링 스택을 통해 다시 실행되지는 않지만 메일, URL 또는 파일의 특정 특성에 따라 부분 재검사가 실행됩니다.

5. 작업을 마치면 제출 단추를 **클릭합니다.**

![URL 제출 예제](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>Microsoft에 의심스러운 URL 보내기

1. Section in the **Object type** section, select **URL.** 나타나는 상자에 전체 URL(예: )을 <https://www.fabrikam.com/marketing.html> 입력합니다.

2. 제출 **이유 섹션에서** 다음 옵션 중 하나를 선택합니다.

   - **차단하지 않아요**

   - **피싱 또는**맬웨어 **선택을 차단한** **Malware**것

3. 작업을 마치면 제출 단추를 **클릭합니다.**

![전자 메일 전송 예제](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a>Microsoft에 의심스러운 파일 제출

1. In the **Object type section,** select **Attachment.**

2. 파일 **선택을 클릭합니다.** 열리는 대화 상자에서 파일을 찾아 서 선택한 다음 열기를 **클릭합니다.**

3. 제출 **이유 섹션에서** 다음 옵션 중 하나를 선택합니다.

   - **차단하지 않아요**

   - **즉, 맬웨어만** **선택할** 수 있는 옵션이며 자동으로 선택됩니다.

4. 작업을 마치면 제출 단추를 **클릭합니다.**

![첨부 파일 전송 예제](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a>관리자 제출 보기

보안 규정 준수 & 제출로 이동하여 **위협 관리** \> **Submissions**제출로 이동하고 관리자 제출 **탭에 있는지** 확인한 후 새 제출을 **클릭합니다.**

페이지 위쪽에 있는 시작 날짜 및 종료 날짜를 입력할 수 있습니다. 기본적으로 제출 **ID(모든** 제출에 할당된 GUID 값)로 상자 상자에 값을 입력하고 새로 고침 단추를 ![ 클릭할 수 ](../../media/scc-quarantine-refresh.png) 있습니다. Update

필터 조건을 변경하려면 제출 **ID 단추를** 클릭하고 다음 값 중 하나를 선택합니다.

- **보낸 사람**
- **제목/URL/파일 이름**
- **제출자**
- **제출 유형**
- **상태**

![관리자 제출 옵션 필터링](../../media/admin-submission-email-filter-options.png)

결과를 내보내려면 **페이지 위쪽에서** 내보내기를 클릭하고 차트 데이터 **또는 테이블을** **선택합니다.** 나타나는 대화 상자에서 .csv 파일을 저장합니다.

그래프 아래에 전자 메일(기본값), **URL,** 첨부 파일 **등** 세 개의 탭이 **있습니다.**

### <a name="view-admin-email-submissions"></a>관리자 전자 메일 제출 보기

Click the **Email** tab.

페이지 **아래쪽에 있는** 열 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.

- **날짜**
- **제출 ID:** 모든 제출에 할당된 GUID 값입니다.
- **제출자**<sup>\*</sup>
- **제목**<sup>\*</sup>
- **보낸 사람**
- **보낸 사람 IP**<sup>\*</sup>
- **제출 유형**
- **배달 이유**
- **상태**<sup>\*</sup>
- **컨트롤 형식**
- **제어 원본**

  <sup>\*</sup> 이 값을 클릭하면 자세한 정보가 플라이아웃에 표시됩니다.

### <a name="view-admin-url-submissions"></a>관리 URL 제출 보기

URL 탭을 **클릭합니다.**

페이지 **아래쪽에 있는** 열 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.

- **날짜**
- **제출 ID**
- **제출자**<sup>\*</sup>
- **URL**<sup>\*</sup>
- **제출 유형**
- **상태**<sup>\*</sup>

  <sup>\*</sup> 이 값을 클릭하면 자세한 정보가 플라이아웃에 표시됩니다.

### <a name="view-admin-attachment-submissions"></a>관리자 첨부 파일 제출 보기

첨부 파일 **탭을 클릭합니다.**

페이지 **아래쪽에 있는** 열 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.

- **날짜**
- **제출 ID**
- **제출자**<sup>\*</sup>
- **파일 이름**<sup>\*</sup>
- **제출 유형**
- **상태**<sup>\*</sup>

  <sup>\*</sup> 이 값을 클릭하면 자세한 정보가 플라이아웃에 표시됩니다.

## <a name="view-user-submissions-to-microsoft"></a>Microsoft에 대한 사용자 제출 보기

보고서 메시지 추가 기능을 [배포하거나](enable-the-report-message-add-in.md)사용자가 웹용 [Outlook의 기본 제공 보고를 사용하는](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)경우 사용자 제출 탭에서 보고 **내용을 확인할 수** 있습니다.

1. 보안 센터에서 & 위협 관리 **제출로** \> **이동합니다.**

2. 사용자 제출 **탭을 선택한** 다음 새 제출을 **클릭합니다.**

페이지 **아래쪽에 있는** 열 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.

- **제출됨**
- **제출자**<sup>\*</sup>
- **제목**<sup>\*</sup>
- **보낸 사람**
- **보낸 사람 IP**<sup>\*</sup>
- **제출 유형**

<sup>\*</sup> 이 값을 클릭하면 자세한 정보가 플라이아웃에 표시됩니다.

페이지 위쪽에 시작 날짜, 종료 날짜 및 기본값으로)을 입력할 수 있습니다. 상자에 값을 **입력하고** 새로 고침 단추를 클릭하여 보낸 사람을 ![ 필터링할 수 ](../../media/scc-quarantine-refresh.png) 있습니다. Update

필터 조건을 변경하려면 보낸 사람 **단추를 클릭하고** 다음 값 중 하나를 선택합니다.

- **보낸 사람 도메인**
- **제목**
- **제출자**
- **제출 유형**
- **보낸 사람 IP**

![사용자 전송을 위한 옵션 필터링](../../media/user-submissions-filter-options.png)

결과를 내보내려면 **페이지 위쪽에서** 내보내기를 클릭하고 차트 데이터 **또는 테이블을** **선택합니다.** 나타나는 대화 상자에서 .csv 파일을 저장합니다.

## <a name="view-user-submissions-to-the-custom-mailbox"></a>사용자 지정 사서함에 대한 사용자 전송 보기

사용자 보고된 [메시지를 받도록 사용자 지정](user-submission.md) 사서함을 구성한 경우에는 보고 사서함에 배달된 메시지를 보고 도용할 수 있습니다.

1. 보안 센터에서 & 위협 관리 **제출로** \> **이동합니다.**

2. 사용자 지정 **사서함 탭을** 선택합니다.

페이지 **아래쪽에 있는** 열 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.

- **제출됨**
- **제출자**<sup>\*</sup>
- **제목**<sup>\*</sup>
- **보낸 사람**
- **보낸 사람 IP**<sup>\*</sup>
- **제출 유형**

페이지 위쪽에 있는 시작 날짜와 종료 날짜를 입력할 수 **Submitted by** ![ ](../../media/scc-quarantine-refresh.png) 있습니다. Update

결과를 내보내려면 **페이지 위쪽에서** 내보내기를 클릭하고 차트 데이터 **또는 테이블을** **선택합니다.** 나타나는 대화 상자에서 .csv 파일을 저장합니다.

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>사용자 지정 사서함에서 Microsoft에 메시지 제출

Microsoft로 메시지를 보내지 않고 사용자가 보고한 메시지를 가로저할 수 있도록 사용자 지정 사서함을 구성한 경우, 분석을 위해 Microsoft에 특정 메시지를 검색하여 보낼 수 있습니다. 사용자 제출을 관리자 제출로 효과적으로 이동합니다.

사용자 **지정 사서함** 탭의 목록에서 메시지를 선택한 후 **동작 단추를** 클릭하고 다음 중 하나를 선택합니다.

- **보고서 정리**
- **보고서 피싱**
- **맬웨어 보고**
- **보고서 스팸 보고서**

![동작 단추의 옵션](../../media/user-submission-custom-mailbox-action-button.png)
