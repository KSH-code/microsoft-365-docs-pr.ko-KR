---
title: 사용자 제출 정책
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
description: 관리자는 사용자가 보고하는 스팸 및 피싱 전자 메일을 수집하도록 사서함을 구성하는 방법을 배울 수 있습니다.
ms.openlocfilehash: 8f9da620643d46bf21a18eccc2047ad4361832cc
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865068"
---
# <a name="user-submissions-policy"></a>사용자 제출 정책

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online 사서함이 있는 Microsoft 365 조직에서는 사용자가 악성 또는 악의적이지 않은 것으로 보고하는 메시지를 받을 사서함을 지정할 수 있습니다. 사용자가 다양한 보고 옵션을 사용하여 메시지를 전송할 때 이 사서함을 사용하여 메시지를 가로채거나(사용자 지정 사서함으로만 보내기만) 메시지 복사본을 받을 수 있습니다(사용자 지정 사서함 및 Microsoft로 보내기). 이 기능은 다음 메시지 보고 옵션과 함께 작동합니다.

- [보고서 메시지 추가 기능](enable-the-report-message-add-in.md)

- [피싱 보고서 추가 기능](enable-the-report-phish-add-in.md)

- [웹용 Outlook의](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) 기본 제공 보고(이전의 웹 Outlook Web App)

- [iOS 및 Android용 Outlook의 기본 제공 보고](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > 웹용 Outlook에서 보고를 사용하지 않도록 설정한 경우 여기에서 사용자 제출을 사용하도록 설정하면 해당 설정이 다시 설정되고 사용자가 웹용 [Outlook에서](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)메시지를 다시 보고할 수 있습니다.

지정한 사서함으로 메시지를 전달하도록 타사 메시지 보고 도구를 구성할 수도 있습니다.

사용자가 보고한 메시지를 Microsoft에 직접 전달하는 대신 사용자 지정 사서함으로 배달하면 관리자가 관리자 제출을 사용하여 메시지를 선택적으로 수동으로 Microsoft에 보고할 [수 있습니다.](admin-submission.md)

## <a name="custom-mailbox-prerequisites"></a>사용자 지정 사서함의 선행 준비

다음 문서를 사용하여 사용자가 보고한 메시지가 사용자 지정 사서함으로 이동하도록 필수 구성을 구성합니다.

- 스팸 지수 설정에 대한 Exchange 메일 흐름 규칙을 만들어 사용자 지정 사서함에서 스팸 필터링을 건너뜁합니다. SCL을 **-1로** 설정하는 [메시지의 SCL을](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) 설정하는 메일 흐름 규칙을 만들 수 있습니다.

- 사용자 지정 사서함에서 맬웨어에 대한 첨부 파일 검색을 해제합니다. [Office 365용 Defender에서](set-up-atp-safe-attachments-policies.md) 안전 첨부 파일 설정 정책을 사용하여 안전  첨부 파일 알 수 없는 맬웨어 응답에 대해 해제 설정을 사용하여 안전한 첨부 파일 정책을 만들 **수 있습니다.**

- 사용자 지정 사서함의 메시지에 대한 URL 검색을 끄세요. [Office 365용 Defender에서](set-up-atp-safe-links-policies.md) 안전한 링크 설정 정책을 사용하여 메시지의  알 수 없는 악의적인 URL에 대한 작업 선택을 해제로 설정하여 안전한 링크 정책을 만들 **수 있습니다.**

- 맬웨어 방지 정책을 만들어 맬웨어 제로 아워 자동 제거를 해제합니다. 보안 및 준수 [&](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) 사용하여 맬웨어 제로 아워 자동 제거를 해제로 설정하는 맬웨어 방지 정책을 **만들 수 있습니다.** 

- 사용자 지정 사서함에서 스팸 및 피싱에 대해 ZAP(제로 아워 자동 비우기)를 사용하지 않도록 설정하는 스팸 필터 정책을 생성합니다. 보안 및 준수 & 사용하여 스팸 방지 정책을 만들고  스팸 ZAP [및 피싱](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) **ZAP에** 대한 On 확인란의 **선택을 취소합니다.**

- 사용자 지정 사서함에서 정크 메일 규칙을 사용하지 않도록 설정 [Exchange Online 사서함에서](configure-junk-email-settings-on-exo-mailboxes.md) 정크 메일 설정을 구성하여 정크 메일 규칙을 사용하지 않도록 설정할 수 있습니다. 이 기능을 사용하지 않도록 설정하면 EOP는 스팸 필터링 판정 동작에 따라  메시지를 정크 메일 폴더로 이동할 수 없습니다.

사서함이 적용 가능한 모든 선행 요구 사항을 충족하는지 확인한 후 보안 & 준수 센터를 사용하여 사용자 제출 사서함을 구성합니다(이 문서의). [](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox)

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 규정 준수 센터를 엽니다. 사용자 제출 **페이지로** 직접 이동하기 위해 다음을 <https://protection.office.com/userSubmissionsReportMessage> 사용하세요.

- 사용자 제출에 대한 구성을 수정하려면 다음 역할 그룹 중 하나의 구성원이 되어야 합니다.

  - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**
  -  [Exchange Online의 조직 관리.](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>보안 및 & 센터를 사용하여 사용자 제출 사서함 구성

1. 보안 & 준수 센터에서 **위협 관리** 정책 \> **사용자** \> **제출로 이동합니다.**

2. 나타나는 **사용자 제출** 페이지에서 다음 옵션 중 하나를 선택합니다.

   1. Outlook에 보고서 메시지 기능 **사용(권장)**: 보고서 메시지 추가 기능, 피싱 보고서 추가 기능 또는 웹용 Outlook의 기본 제공 보고를 사용하는 경우 이 옵션을 선택하고 다음 설정을 구성합니다.

      - **최종 사용자 확인 메시지** 사용자 지정 : 이 링크를 클릭합니다. 나타나는 **확인 메시지** 플라이아웃 사용자 지정에서 다음 설정을 구성합니다.

      - **제출 전에**:  제목  및 확인 메시지 상자에 보고서 메시지 추가 기능 또는 피싱 보고서 추가 기능을 사용하여 메시지를 보고하기 전에 사용자에게 표시하는 설명 텍스트를 입력합니다. %type 변수를 사용하여 제출 유형(정크, 피싱 아님 등)을 포함할 수 있습니다.

        앞서 설명한 것 처럼 보고된 메시지를 Microsoft로 보내는 옵션을 선택하면 알림에 다음 텍스트도 추가됩니다.

        > 분석을 위해 전자 메일이 Microsoft에 있는 동안 제출됩니다. 일부 전자 메일에는 개인 또는 중요한 정보가 포함될 수 있습니다.

      - **제출 후**: 확장 ![ ](../../media/scc-expand-icon.png) 아이콘을 클릭합니다. 제목 **및**  확인 메시지 상자에 보고서 메시지 추가 기능 또는 피싱 보고서 추가 기능을 사용하여 메시지를 보고한 후 사용자에게 표시하는 설명 텍스트를 입력합니다. %type 변수를 사용하여 제출 형식을 포함할 수 있습니다.

      작업을 마친 후 **저장** 을 클릭합니다. 이러한 값을 지우려면 사용자 제출 **페이지에서** **복원을** 클릭합니다.

      - **보고된 메시지를** 다음 중 하나를 선택합니다.

        - **Microsoft(권장)**: 사용자 제출 사서함이 사용되지 않습니다(보고된 모든 메시지는 Microsoft로 이동).

        - **Microsoft 및 사용자** 지정 사서함: 나타나는 상자에 기존 Exchange Online 사서함의 전자 메일 주소를 입력합니다. 메일 그룹은 허용되지 않습니다. 사용자 제출은 분석을 위해 Microsoft와 관리자 또는 보안 운영 팀이 분석할 사용자 지정 사서함으로 이동됩니다.

        - **사용자 지정 사서함:** 상자가 나타나면 기존 Exchange Online 사서함의 전자 메일 주소를 입력합니다. 메일 그룹은 허용되지 않습니다. 메시지를 먼저 분석하기 위해 관리자 또는 보안 운영 팀으로 이동하려는 경우 이 옵션을 사용합니다. 관리자가 직접 전달하지 않으면 메시지가 Microsoft로 이동되지 않습니다.

        > [!NOTE]
        > 미국 정부 조직(GCC, GCC-H 및 DoD)은 사용자 지정 사서함만 **구성할 수 있습니다.** 다른 두 옵션은 사용하지 않도록 설정됩니다.

      완료되면 확인을 **클릭합니다.**

      > [!CAUTION]
      > 웹용 Outlook 사서함 정책을 사용하여 웹용 [Outlook에서](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) 정크 메일 보고를 사용하지 않도록 설정했지만 Microsoft에 메시지를 보고하도록 이전 설정을 구성한 경우 사용자는 보고서 메시지 추가 기능 또는 피싱 보고서 추가 기능을 사용하여 웹용 Outlook의 Microsoft에 메시지를 보고할 수 있습니다.

   - **Outlook에** 대해 보고서 메시지 기능을 사용하지 않도록 설정 : 보고서 메시지 추가 기능, 피싱 보고서 추가 기능 또는 웹용 Outlook의 기본 제공 보고 대신 타사 보고 도구를 사용하는 경우 이 옵션을 선택하고 다음 설정을 구성합니다.

      이 사용자 지정 사서함을 사용하여 사용자가 **보고한 제출을 받습니다.** 상자가 나타나면 Office 365에 이미 있는 기존 사서함의 전자 메일 주소를 입력합니다. 이 사서함은 전자 메일을 받을 수 있는 Exchange Online의 기존 사서함입니다.

      완료되면 확인을 **클릭합니다.**

## <a name="message-submission-format"></a>메시지 전송 형식

사용자 지정 사서함으로 전송되는 메시지는 특정 전송 메일 형식을 따라야 합니다. 제출의 제목(봉투 제목)은 다음 형식입니다.

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

여기서 SafetyAPIAction은 다음 정수 값 중 하나입니다.

- 1: 정크
- 2: 정크 아님
- 3: 피싱

다음 예제에서는 다음을 들 수 있습니다.

- 메시지가 피싱으로 보고되고 있습니다.
- 네트워크 메시지 ID는 49871234-6dc6-43e8-abcd-08d797f20abe입니다.
- 보낸 사람 IP는 167.220.232.101입니다.
- From 주소가 test@contoso.com.
- 메시지의 제목 줄이 "피싱 제출 테스트"입니다.

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

이 형식을 따르지 않는 메시지는 제출 포털에 제대로 표시되지 않습니다.
