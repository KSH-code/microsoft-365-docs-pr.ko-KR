---
title: 사용자 전송 정책
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
description: 관리자는 사용자가 보고 하는 스팸 및 피싱 전자 메일을 수집 하도록 사서함을 구성 하는 방법을 확인할 수 있습니다.
ms.openlocfilehash: 31249ab930c44d84f27efac95d8e57bd88d9742f
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130902"
---
# <a name="user-submissions-policy"></a>사용자 전송 정책

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online 사서함이 있는 Microsoft 365 조 직에서는 사용자가 악성 메일로 보고 하는 메시지를 수신 하는 사서함을 지정할 수 있습니다. 사용자가 다양 한 보고 옵션을 사용 하 여 메시지를 전송 하는 경우이 사서함을 사용 하 여 메시지를 가로채 며 (사용자 지정 사서함에만 보냄) 메시지 복사본을 받을 수 있습니다 (사용자 지정 사서함 및 Microsoft로 보내기). 이 기능은 다음과 같은 메시지 보고 옵션에서 작동 합니다.

- [보고서 메시지 추가 기능](enable-the-report-message-add-in.md)

- 웹용 Outlook (이전의 Outlook Web App) [에 기본적으로 제공 되는 보고 기능](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)

- [IOS 및 Android 용 Outlook의 기본 제공 보고](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > [웹에서 outlook에서 보고를 사용 하지 않도록](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)설정한 경우 여기서 사용자 제출을 사용 하도록 설정 하면 해당 설정이 무시 되 고 사용자가 웹에서 Outlook에서 메시지를 다시 보고할 수 있습니다.

또한 타사 메시지 보고 도구를 구성 하 여 지정한 사서함에 메시지를 전달할 수 있습니다.

사용자가 보고 한 메시지를 Microsoft에 직접 배포 하는 대신 사용자 지정 사서함에 전달 하면 관리자가 [관리 제출을](admin-submission.md)사용 하 여 메시지를 선택적으로 수동으로 microsoft에 보고할 수 있습니다.

## <a name="custom-mailbox-prerequisites"></a>사용자 지정 사서함 필수 구성 요소

다음 문서를 사용 하 여 사용자가 보고 한 메시지를 사용자 지정 사서함으로 이동 하는 데 필요한 필수 구성 요소를 구성 합니다.

- Exchange 메일 흐름 규칙을 만들어 scl (스팸 지 수)을 설정 하 여 사용자 지정 사서함에 대 한 스팸 필터링을 건너뜁니다. EAC를 사용 하 여 SCL을 **-1** 로 설정 하 [는 메시지의 SCL을 설정 하는 메일 흐름 규칙 만들기를](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) 참조 하십시오.

- 사용자 지정 사서함에서 맬웨어에 대 한 첨부 파일 검색을 해제 합니다. 안전 **첨부 파일** 에 대 한이 설정을 **해제** 하는 안전 첨부 파일 정책을 만들려면 [Defender for Office 365에서 안전한 첨부 파일 정책 설치](set-up-atp-safe-attachments-policies.md) 를 사용 합니다.

- 사용자 지정 사서함에서 메시지에 대해 URL 검색을 해제 합니다. **메시지에서 알 수 없는 잠재적 악성 url에 대 한 작업을 선택** 하려면 [Defender for Office 365에서](set-up-atp-safe-links-policies.md) 안전한 링크 **정책 설정을 사용** 하 여 안전한 링크 정책을 만듭니다.

- 맬웨어 방지 정책을 만들어 맬웨어 제로 시간 자동 삭제를 해제 합니다. [보안 & 준수 센터를 사용 하 여 맬웨어 방지 정책 만들기](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) 를 참조 하 여 **맬웨어가 있는 맬웨어 자동 삭제** 를 **설정 합니다.**

- 사용자 지정 사서함에서 스팸 및 피싱 사기에 대해 제로 시간 자동 삭제 (ZAP)를 사용 하지 않도록 설정 하는 스팸 필터 정책을 만듭니다. 스팸 방지 정책을 만들고 **스팸 ZAP** 및 **피싱 ZAP** **에 대 한 확인란의** 선택을 취소 [하려면 보안 & 준수 센터 사용을](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) 참조 하십시오.

- 사용자 지정 사서함에서 정크 메일 규칙을 사용 하지 않도록 설정 합니다. 정크 메일 규칙을 사용 하지 않도록 설정 하려면 [Exchange Online 사서함에서 정크 메일 구성 설정을](configure-junk-email-settings-on-exo-mailboxes.md) 사용 합니다. 사용 하지 않도록 설정 되 면 EOP에서 스팸 필터링 결과 동작 **메시지를 정크 메일** 폴더로 이동 하거나 사서함에서 수신 허용 목록 모음으로 이동 하 여 정크 메일 폴더로 메시지를 이동할 수 없습니다.

사서함이 해당 하는 모든 필수 구성 요소를 충족 하는지 확인 한 후에는 [보안 & 준수 센터를 사용 하 여이 문서의 사용자 전송 사서함을 구성](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) 합니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 준수 센터를 엽니다. **사용자 전송** 페이지로 직접 이동 하려면를 사용 <https://protection.office.com/userSubmissionsReportMessage> 합니다.

- 사용자 전송에 대 한 구성을 수정 하려면 다음 역할 그룹 중 하나의 구성원 이어야 합니다.

  - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리**

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>보안 & 준수 센터를 사용 하 여 사용자 전송 사서함을 구성 합니다.

1. 보안 & 준수 센터에서 **위협 관리** \> **정책** \> **사용자 전송** 으로 이동 합니다.

2. **사용자 제출** 페이지가 나타나면 다음 옵션 중 하나를 선택 합니다.

   1. **Outlook에 대 한 보고서 메시지 기능 사용 (권장)**: 웹에서 보고서 메시지 추가 기능 또는 기본 제공 보고를 사용 하는 경우이 옵션을 선택 하 고 다음 설정을 구성 합니다.

      - **최종 사용자에 게 확인 메시지를 사용자 지정**:이 링크를 클릭 합니다. 표시 되는 **확인 메시지 플라이 아웃 사용자 지정** 에서 다음 설정을 구성 합니다.

      - **제출 전**: **제목** 및 **확인 메시지** 상자에 사용자가 보고서 메시지 추가 기능을 사용 하 여 메시지를 보고 하기 전에 표시 되는 설명 텍스트를 입력 합니다. 전송 유형 (정크, 정크 메일 아님, 피싱 등)을 포함 하 여% type% 변수를 사용할 수 있습니다.

        앞에서 설명한 것 처럼, 보고 된 메시지를 Microsoft로 보내는 옵션을 선택 하면 다음과 같은 텍스트도 알림에 추가 됩니다.

        > 전자 메일이 분석을 위해 Microsoft에 게 제출 됩니다. 일부 전자 메일에는 개인 정보나 중요 한 정보가 포함 될 수 있습니다.

      - **제출 후** ![ 확장 아이콘을 클릭 ](../../media/scc-expand-icon.png) 합니다. **제목** 및 **확인 메시지** 상자에 사용자가 보고서 메시지 추가 기능을 사용 하 여 메시지를 보고 한 후에 표시 되는 설명 텍스트를 입력 합니다. 전송 유형을 포함 하기 위해% type% 변수를 사용할 수 있습니다.

      작업을 마친 후 **저장** 을 클릭합니다. 이러한 값을 지우려면 **사용자 전송** 페이지에서 다시 **복원을** 클릭 합니다.

      - **보고 된 메시지를 보낼** 위치: 다음 중 하나를 선택 합니다.

        - **Microsoft (권장)**: 사용자 제출 사서함이 사용 되지 않습니다 (보고 된 모든 메시지는 Microsoft로 이동 됨).

        - **Microsoft 및 사용자 지정 사서함**: 표시 되는 상자에 기존 Exchange Online 사서함의 전자 메일 주소를 입력 합니다. 메일 그룹을 사용할 수 없습니다. 사용자 제출은 Microsoft for analysis와 관리자 또는 보안 운영 팀이 분석 하기 위한 사용자 지정 사서함으로 이동 합니다.

        - **사용자 지정 사서함**: 표시 되는 상자에 기존 Exchange Online 사서함의 전자 메일 주소를 입력 합니다. 메일 그룹을 사용할 수 없습니다. 이 옵션을 사용 하 여 메시지를 먼저 분석을 위해 관리자 또는 보안 운영 팀 으로만 이동 합니다. 관리자가 메시지를 직접 전달 하지 않으면 메시지가 Microsoft로 이동 하지 않습니다.

        > [!NOTE]
        > 미국 정부 기관 (GCC, GCC-H 및 DoD)은 **사용자 지정 사서함** 만 구성할 수 있습니다. 다른 두 옵션은 사용 하지 않도록 설정 됩니다. 

      작업이 완료 되 면 **확인** 을 클릭 합니다.

      > [!CAUTION]
      > 웹 사서함 정책에서 Outlook을 사용 하 여 [웹용 outlook에서 정크 메일 보고를 사용 하지 않도록 설정](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) 했지만 microsoft에 메시지를 보고 하는 이전 설정 중 하나를 구성 하는 경우 사용자는 보고서 메시지 추가 기능을 사용 하 여 웹용 Outlook에서 Microsoft에 메시지를 보고할 수 있습니다.

   - **Outlook에 대 한 보고서 메시지 기능 사용 안 함**:이 옵션을 선택 하면 보고서 메시지 추가 기능 대신 타사 보고 도구를 사용 하거나, 웹에서 Outlook에서 기본 제공 되는 보고를 사용할 수 있습니다.

      **사용자가 보고 한 제출을 수신 하려면이 사용자 지정 사서함 사용을** 선택 합니다. 상자가 나타나면 이미 Office 365에 있는 기존 사서함의 전자 메일 주소를 입력 합니다. 이는 전자 메일을 받을 수 있는 Exchange Online의 기존 사서함 이어야 합니다.

      작업이 완료 되 면 **확인** 을 클릭 합니다.

## <a name="message-submission-format"></a>메시지 전송 형식

사용자 지정 사서함에 전송 된 메시지는 특정 전송 메일 형식을 따라야 합니다. 제출 서류의 제목 (봉투 제목)은 다음과 같은 형식 이어야 합니다.

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

여기에서 기능 \ Etyapiaction은 다음 정수 값 중 하나입니다.

- 1: 정크
- 2: 정크 아님
- 3: 피싱

다음 예제를 실행 합니다.

- 메시지가 피싱 메일로 보고 됩니다.
- 네트워크 메시지 ID는 49871234-6dc6-43e8-abcd-08d797f20abe입니다.
- 보낸 사람 IP는 167.220.232.101입니다.
- 보낸 사람 주소는 test@contoso.com입니다.
- 메시지의 제목 줄은 "피싱 제출 테스트"입니다.

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

이 형식을 따르지 않는 메시지는 제출 포털에서 올바르게 표시 되지 않습니다.
