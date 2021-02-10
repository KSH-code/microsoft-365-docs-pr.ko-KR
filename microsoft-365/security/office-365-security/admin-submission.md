---
title: 관리자 제출
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 관리자는 보안 및 준수 센터의 제출 포털을 사용하여 의심스러운 전자 메일, 의심스러운 피싱 메일, 스팸 및 기타 유해한 메시지, URL 및 파일을 검색을 위해 Microsoft에 제출하는 방법을 배울 수 있습니다. &
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7a822909c318cb336c179b299aa64cd71dcca4d8
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175874"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>관리자 제출을 사용하여 의심스러운 스팸, 피싱, URL 및 파일을 Microsoft에 제출

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 요금제 1 및 계획 2](https://go.microsoft.com/fwlink/?linkid=2148715)


Exchange Online에 사서함이 있는 Microsoft 365 조직에서 관리자는 보안 및 준수 센터의 제출 포털을 & 전자 메일 메시지, URL 및 첨부 파일을 검사하기 위해 Microsoft에 제출할 수 있습니다.

전자 메일 메시지를 제출하면 다음이 표시됩니다.

1. **전자 메일 인증 확인**: 전자 메일 인증이 전달될 때 통과 또는 실패한 경우의 세부 정보입니다.
2. **정책 적중:** 테넌트로 들어오는 전자 메일을 허용하거나 차단할 수 있는 모든 정책에 대한 정보로, 서비스 필터 판정을 의회합니다.
3. **페이로드 신뢰도/확인:** 메시지의 URL 및 첨부 파일을 검사합니다.
4. **등급 분석:** 메시지가 악성인지 여부를 확인하기 위해 휴먼 등급의 검토

> [!IMPORTANT]
> 페이로드 신뢰도/분석 및 등급 분석은 모든 테넌트에서 수행되지 않습니다. 데이터가 규정 준수를 위해 테넌트 경계를 떠날 수 없는 경우 정보가 조직 외부로 나가지 못하도록 차단됩니다.

Microsoft에 전자 메일 메시지, URL 및 첨부 파일을 제출하는 다른 방법은 Microsoft에 메시지 및 [파일 보고를 참조하세요.](report-junk-email-messages-to-microsoft.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 규정 준수 센터를 엽니다. 제출 페이지로 직접 **이동하기** 위해 <https://protection.office.com/reportsubmission> 다음을 사용하세요.

- 메시지와 파일을 Microsoft에 제출하려면 다음 역할 그룹 중 하나의 구성원이 됩니다.

  - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**

  -  [Exchange Online의 조직 관리.](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)

    이 역할 그룹의 구성원 자격은 [](#view-user-submissions-to-the-custom-mailbox) 이 문서의 부분에서 설명하는 사용자 지정 사서함으로의 사용자 제출을 보는 데 필요합니다.

- 사용자가 Microsoft에 메시지와 파일을 제출하는 방법에 대한 자세한 내용은 Microsoft에 메시지 및 [파일 보고를 참조하세요.](report-junk-email-messages-to-microsoft.md)

## <a name="report-suspicious-content-to-microsoft"></a>Microsoft에 의심스러운 콘텐츠 보고

1. 보안 & 준수 센터에서 **위협** 관리 제출으로 이동하여 관리자 제출 탭에 있는지 확인한 다음 새 제출을 \>  **클릭합니다.** 

2. 다음 **섹션에** 설명된 메시지, URL 또는 첨부 파일을 제출하는 것으로 나타나는 새 제출 플라이아웃을 사용합니다.

### <a name="submit-a-questionable-email-to-microsoft"></a>Microsoft에 질문이 있는 전자 메일 제출

1. 개체 유형 **섹션에서** 전자 메일을 **선택합니다.** 제출 형식 **섹션에서** 다음 옵션 중 하나를 사용하세요.

   - 네트워크 메시지 **ID:** 메시지의 **X-MS-Exchange-Organization-Network-Message-Id** 헤더 또는 **X-MS-Office365-Filtering-Correlation-Id** 헤더에서 사용할 수 있는 GUID 값입니다.

   - **파일**: 파일 **선택을 클릭합니다.** 대화 상자가 열리면 .eml 또는 .msg 파일을 찾아 선택한 다음 열기 를 **클릭합니다.**

   > [!NOTE]
   > Office 365 요금제 1 또는 계획 2에 대한 Defender를 가진 관리자는 30일 이전의 메시지를 제출할 수 있습니다. 다른 관리자는 7일만 돌아갈 수 있습니다.

2. 받는 사람 **섹션에서** 정책 검사를 실행할 받는 사람을 하나 이상 지정합니다. 정책 검사는 사용자 또는 조직 정책으로 인해 전자 메일이 검사를 무시한지 여부를 판단합니다.

3. 제출 이유 **섹션에서** 다음 옵션 중 하나를 선택합니다.

   - **차단되지 않은 경우**

   - **차단된 경우**: **스팸,** 피싱 또는 맬웨어를 **선택합니다.**  확실하지 않은 경우 최상의 판단을 사용 합니다.

4. 완료되면 제출 **단추를** 클릭합니다.

   ![URL 제출 예제](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>의심되는 URL을 Microsoft로 보내기

1. 개체 유형 **섹션에서** **URL을 선택합니다.** 상자가 나타나면 전체 URL(예: )을 `https://www.fabrikam.com/marketing.html` 입력합니다.

2. 제출 이유 **섹션에서** 다음 옵션 중 하나를 선택합니다.

   - **차단되지 않은 경우**

   - **차단된 경우**: **피싱** 또는 맬웨어를 **선택합니다.**

3. 완료되면 제출 **단추를** 클릭합니다.

   ![전자 메일 제출 예제](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a>의심되는 파일을 Microsoft에 제출

1. 개체 유형 **섹션에서** 첨부 파일을 **선택합니다.**

2. 파일 **선택을 클릭합니다.** 대화 상자가 열리면 파일을 찾아 선택한 다음 열기 를 **클릭합니다.**

3. 제출 이유 **섹션에서** 다음 옵션 중 하나를 선택합니다.

   - **차단되지 않은 경우**

   - **차단된 경우:**  맬웨어만 선택할 수 있으며 자동으로 선택됩니다.

4. 완료되면 제출 **단추를** 클릭합니다.

   ![첨부 파일 제출 예제](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a>관리자 제출 보기

보안 & 준수 센터에서 **위협** 관리 제출으로 이동하여 관리자 제출 탭에 있는지 확인한 다음 새 제출을 \>  **클릭합니다.** 

페이지 위쪽에서 시작 날짜, 종료 날짜를 입력할 수 있으며(기본적으로) 상자에 값을 입력하고 새로 고침 단추를 클릭하여 제출 **ID(모든** 제출에 할당된 GUID 값)를 필터링할 수 ![ ](../../media/scc-quarantine-refresh.png) 있습니다. Update

필터 조건을 변경하려면 제출 **ID** 단추를 클릭하고 다음 값 중 하나를 선택합니다.

- **보낸 사람**
- **주체/URL/파일 이름**
- **제출자**
- **제출 유형**
- **상태**

![관리자 제출에 대한 필터 옵션](../../media/admin-submission-email-filter-options.png)

결과를 내보내려면 페이지 위쪽에 **있는** 내보내기를 클릭하고 차트 데이터 또는 **표를** **선택합니다.** 나타나는 대화 상자에서 .csv 파일을 저장합니다.

그래프 아래에는 전자 메일(기본값), URL 및 첨부 파일 등 세 개의 **탭이** **있습니다.** 

### <a name="view-admin-email-submissions"></a>관리자 전자 메일 제출 보기

전자 메일 **탭을** 클릭합니다.

페이지 아래쪽의 **열** 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.

- **날짜**
- **제출 ID:** 모든 제출에 할당된 GUID 값입니다.
- **제출자**<sup>\*</sup>
- **제목**<sup>\*</sup>
- **보낸 사람**
- **보낸 사람 IP**<sup>\*</sup>
- **제출 유형**
- **배달 이유**
- **상태**<sup>\*</sup>

  <sup>\*</sup> 이 값을 클릭하면 자세한 정보가 플라이아웃에 표시됩니다.

#### <a name="admin-submission-rescan-details"></a>관리자 제출 세부 정보 다시 검색

관리자 제출에 제출된 메시지는 다시 검색된 후 세부 정보 플라이아웃에 표시됩니다.

- 배달 시 보낸 사람 전자 메일 인증에 오류가 발생했습니다.
- 메시지의 판정에 영향을 주거나 의리가 있을 수 있는 정책 적중에 대한 정보입니다.
- 메시지에 포함된 URL 또는 파일이 악의적이지 않은지의 현재 확인 결과입니다.
- 학년의 피드백.

다시 검색된 재지정은 몇 분 후 완료됩니다. 전자 메일 인증에 문제가 없는 경우 또는 배달에 대한 오버라이드의 영향을 받지 않은 경우 학년들의 피드백이 하루가 걸릴 수 있습니다.

### <a name="view-admin-url-submissions"></a>관리자 URL 제출 보기

URL **탭을** 클릭합니다.

페이지 아래쪽의 **열** 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.

- **날짜**
- **제출 ID**
- **제출자**<sup>\*</sup>
- **URL**<sup>\*</sup>
- **제출 유형**
- **상태**<sup>\*</sup>

  <sup>\*</sup> 이 값을 클릭하면 자세한 정보가 플라이아웃에 표시됩니다.

### <a name="view-admin-attachment-submissions"></a>관리자 첨부 파일 제출 보기

첨부 **파일 탭을** 클릭합니다.

페이지 아래쪽의 **열** 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.

- **날짜**
- **제출 ID**
- **제출자**<sup>\*</sup>
- **파일 이름**<sup>\*</sup>
- **제출 유형**
- **상태**<sup>\*</sup>

  <sup>\*</sup> 이 값을 클릭하면 자세한 정보가 플라이아웃에 표시됩니다.

## <a name="view-user-submissions-to-microsoft"></a>Microsoft에 대한 사용자 제출 보기

보고서 메시지 추가 기능, 피싱 보고 [](enable-the-report-phish-add-in.md)추가 기능을 배포한 경우 또는 사용자가 웹용 [Outlook에서](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)기본 제공 보고를 사용하는 경우 사용자 제출  탭에서 보고하는 사용자를 볼 수 있습니다. [](enable-the-report-message-add-in.md)

1. 보안 및 & 센터에서 **위협** 관리 \> **제출로 이동합니다.**

2. 사용자 제출 **탭을** 선택한 다음 새 **제출을 클릭합니다.**

페이지 아래쪽의 **열** 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.

- **제출 시**
- **제출자**<sup>\*</sup>
- **제목**<sup>\*</sup>
- **보낸 사람**
- **보낸 사람 IP**<sup>\*</sup>
- **제출 유형**

<sup>\*</sup> 이 값을 클릭하면 자세한 정보가 플라이아웃에 표시됩니다.

페이지 위쪽에서 시작 날짜, 종료 날짜를 입력할 수 있으며(기본적으로) 상자에  값을 입력하고 새로 고침 단추를 클릭하여 보낸 사람으로 필터링할 ![ 수 ](../../media/scc-quarantine-refresh.png) 있습니다. Update

필터 조건을 변경하려면 보낸  사람 단추를 클릭하고 다음 값 중 하나를 선택합니다.

- **보낸 사람 도메인**
- **제목**
- **제출자**
- **제출 유형**
- **보낸 사람 IP**

![사용자 제출에 대한 필터 옵션](../../media/user-submissions-filter-options.png)

결과를 내보내려면 페이지 위쪽에 **있는** 내보내기를 클릭하고 차트 데이터 또는 **표를** **선택합니다.** 나타나는 대화 상자에서 .csv 파일을 저장합니다.

## <a name="view-user-submissions-to-the-custom-mailbox"></a>사용자 지정 사서함에 대한 사용자 제출 보기

**사용자가** 보고한 [](user-submission.md) 메시지를 받도록 사용자 지정 사서함을 구성한 경우 보고 사서함으로 배달된 메시지를 보고하고 전송할 수도 있습니다.

1. 보안 및 & 센터에서 **위협** 관리 \> **제출로 이동합니다.**

2. 사용자 **지정 사서함 탭을** 선택합니다.

페이지 아래쪽의 **열** 옵션 단추를 클릭하여 보기에서 열을 추가하거나 제거할 수 있습니다.

- **제출 시**
- **제출자**<sup>\*</sup>
- **제목**<sup>\*</sup>
- **보낸 사람**
- **보낸 사람 IP**<sup>\*</sup>
- **제출 유형**

페이지 위쪽에서 시작 날짜, 종료 날짜를 입력할 수 있으며 상자에 값을 입력하고 새로 고침 단추를 클릭하여 **제출된** 날짜로 필터링할 ![ 수 ](../../media/scc-quarantine-refresh.png) 있습니다. Update

결과를 내보내려면 페이지 위쪽에 **있는** 내보내기를 클릭하고 차트 데이터 또는 **표를** **선택합니다.** 나타나는 대화 상자에서 .csv 파일을 저장합니다.

## <a name="undo-user-submissions"></a>사용자 제출 취소

사용자가 의심스러운 전자 메일을 사용자 지정 사서함에 제출하면 사용자와 관리자는 제출을 취소할 수 있는 옵션이 없습니다. 사용자가 전자 메일을 복구하려면 지우기 항목 또는 정크 메일 폴더에서 복구할 수 있습니다.

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>사용자 지정 사서함에서 Microsoft로 메시지 전송

Microsoft로 메시지를 보내지 않고 사용자가 보고한 메시지를 가로채도록 사용자 지정 사서함을 구성한 경우 분석을 위해 특정 메시지를 찾아 Microsoft로 보낼 수 있습니다. 그러면 사용자 제출이 관리자 제출로 효과적으로 이동됩니다.

사용자 **지정 사서함** 탭의 목록에서 메시지를 선택하고  작업 단추를 클릭한 다음 다음 중 하나를 선택합니다.

- **정리 보고**
- **피싱 보고**
- **맬웨어 보고**
- **스팸 보고**

![작업 단추의 옵션](../../media/user-submission-custom-mailbox-action-button.png)
