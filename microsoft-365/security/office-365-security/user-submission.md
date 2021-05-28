---
title: 사용자 제출 정책
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
description: 관리자는 사용자가 보고하는 스팸 및 피싱 전자 메일을 수집하도록 사서함을 구성하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 719bd2b86cae1c6a951cb34408ecb9d2b8da699a
ms.sourcegitcommit: a3359982fea01339c7377e3ee89f223788cee0bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/28/2021
ms.locfileid: "52696589"
---
# <a name="user-submissions-policy"></a>사용자 제출 정책

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

사서함이 Microsoft 365 조직에서 Exchange Online 악의적이거나 악의적이지 않은 것으로 보고하는 메시지를 받을 사서함을 지정할 수 있습니다. 사용자가 다양한 보고 옵션을 사용하여 메시지를 전송할 때 이 사서함을 사용하여 메시지를 가로채거나(사용자 지정 사서함으로만 보내기) 메시지 복사본(사용자 지정 사서함 및 Microsoft로 보내기)을 받을 수 있습니다. 이 기능은 다음 메시지 보고 옵션과 함께 작동합니다.

- [보고서 메시지 추가 기능](enable-the-report-message-add-in.md)

- [피싱 보고 추가 기능](enable-the-report-phish-add-in.md)

- [타사 보고 도구](#third-party-reporting-tools)

사용자가 보고한 메시지를 Microsoft에 직접 전달하는 대신 사용자 지정 사서함으로 배달하면 관리자가 관리자 제출을 사용하여 메시지를 선택적으로 수동으로 Microsoft에 보고할 [수 있습니다.](admin-submission.md)

  > [!NOTE]
  > 웹용 웹 Outlook 보고를 사용하지 않도록 설정한 경우 [여기에서](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)사용자 제출을 사용하도록 설정하면 해당 설정이 다시 Outlook 웹에서 메시지를 보고할 수 있습니다.

## <a name="custom-mailbox-prerequisites"></a>사용자 지정 사서함 선행 준비

다음 문서를 사용하여 사용자가 보고한 메시지가 사용자 지정 사서함으로 이동하도록 필수 구성을 구성합니다.

- 스팸 지수 설정 Exchange 메일 흐름 규칙을 만들어 사용자 지정 사서함에서 스팸 필터링을 건너뜁. SCL을 스팸 필터링 무시로 설정하는 [메시지의 SCL을](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) 설정하는 메일 흐름 규칙 만들기를 **참조합니다.**

- 사용자 지정 사서함에서 맬웨어에 대한 첨부 파일 검색을 끄면 됩니다. [Defender에서](set-up-safe-attachments-policies.md) 안전한 첨부 파일 정책 Office 365 설정 을 사용하여 안전한 첨부  파일 알 수 없는 맬웨어 응답에 대해 끄기 설정을 사용하여 안전한 첨부 파일 정책을 **만들 수 있습니다.**

- 사용자 지정 사서함의 메시지에 대해 URL 검색을 끄세요. Defender에서 안전한 링크 정책 Office 365 설정 을 사용하여 메시지의 알  수 없는 악의적인 URL에 대한 작업 선택을 [해제로](set-up-safe-links-policies.md) 설정하여 안전한 링크 정책을 **만들 수 있습니다.**

- 맬웨어 방지 정책을 만들어 맬웨어 제로 아워 자동 제거를 해제합니다. 보안 [및 준수 &](configure-your-spam-filter-policies.md#use-the-security-center-to-create-anti-spam-policies) 사용하여 맬웨어 방지 정책을 만들어 맬웨어 제로 아워 자동 제거를 끄기로 **설정합니다.** 

- 스팸 필터 정책을 만들어 사용자 지정 사서함에서 스팸 및 피싱에 대해 ZAP(제로 아워 자동 제거)를 사용하지 않도록 설정합니다. 보안 및 준수 & 사용하여 스팸 방지 정책 만들기를  참조하고 스팸 ZAP 및 [피싱](configure-your-spam-filter-policies.md#use-the-security-center-to-create-anti-spam-policies) **ZAP에** 대한 On 확인란 선택을 **취소합니다.**

- 사용자 지정 사서함에서 정크 메일 규칙을 사용하지 않도록 설정 사서함에서 [정크 메일 Exchange Online 구성을 사용하여](configure-junk-email-settings-on-exo-mailboxes.md) 정크 메일 규칙을 사용하지 않도록 설정할 수 있습니다. 이 기능을 사용하지 않도록 설정하면 EOP에서 스팸 필터링 판정 동작에 따라  메시지를 정크 메일 폴더로 이동하거나 사서함의 수신할 수 있는 목록 모음으로 메시지를 이동할 수 없습니다.

사서함이 적용 가능한 모든 선행 요구 사항을 충족하는지 확인한 후 보안 & 준수 센터를 사용하여 사용자 제출 사서함을 구성합니다(이 문서). [](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox)

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 준수 센터를 엽니다. 사용자 제출 **페이지로** 직접 이동하기 위해 를 <https://protection.office.com/userSubmissionsReportMessage> 사용하세요.

- 사용자 제출에 대한 구성을 수정하려면 다음 역할 그룹 중 하나의 구성원이 되어야 합니다.

  - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**
  - **에서 조직** [Exchange Online.](/Exchange/permissions-exo/permissions-exo#role-groups)

- PowerShell을 사용하려면 Exchange Online 액세스해야 합니다. 사용하려는 계정에 Exchange Online PowerShell에 액세스할 수 없는 경우 제출 사서함을 지정할 때 다음과 같은 오류가 표시됩니다.

  > 도메인에서 전자 메일 주소 지정

  PowerShell에 대한 액세스를 활성화하거나 Exchange Online 자세한 내용은 다음 항목을 참조하세요.

  - [PowerShell에 대한 액세스 Exchange Online 사용 또는 사용 안 하도록 설정](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [클라이언트 액세스 규칙의 Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>보안 및 & 센터를 사용하여 사용자 제출 사서함 구성

1. 보안 및 & 센터에서 **위협** 관리 정책 \> **사용자** \> **제출으로 이동합니다.**

2. 나타나는 **사용자 제출** 페이지에서 다음 옵션 중 하나를 선택합니다.

      1. **보고서 메시지** 기능에 Outlook 기능 사용(권장) : 보고서 메시지 추가 기능, 피싱 보고 추가 기능 또는 웹용 Outlook 기본 제공 보고를 사용하는 경우 이 옵션을 선택하고 다음 설정을 구성합니다.

    - **최종 사용자 확인 메시지 사용자** 지정: 이 링크를 클릭합니다. 나타나는 **확인 메시지** 사용자 지정 플라이아웃에서 다음 설정을 구성합니다.

        - **제출 전:**  제목  및 확인 메시지 상자에 보고서 메시지 추가 기능 또는 피싱 보고 추가 기능을 사용하여 메시지를 보고하기 전에 사용자에게 설명 텍스트를 입력합니다. %type% 변수를 사용하여 제출 유형(정크, 피싱 등이 아님)을 포함할 수 있습니다.

          앞서 설명한처럼 보고된 메시지를 Microsoft로 보내는 옵션을 선택하면 알림에 다음 텍스트도 추가됩니다.

          > 분석을 위해 전자 메일이 Microsoft에 있는 동안 제출됩니다. 일부 전자 메일에는 개인 또는 중요한 정보가 포함될 수 있습니다.

        - **제출 후**: 확장 ![ 아이콘 ](../../media/scc-expand-icon.png) 을 클릭합니다. 제목 **및**  확인 메시지 상자에 보고서 메시지 추가 기능 또는 피싱 보고 추가 기능을 사용하여 메시지를 보고한 후 사용자에게 표시될 설명 텍스트를 입력합니다. %type% 변수를 사용하여 제출 유형을 포함할 수 있습니다.

      작업을 마쳤으면 **저장** 을 클릭합니다. 이러한 값을 지우려면 사용자 제출 **페이지에서** **복원을** 클릭합니다.
    
    - **최종 사용자 보고 옵션 사용자** 지정: 이 링크를 클릭합니다. 나타나는 **최종 사용자** 보고 옵션 사용자 지정 플라이아웃에서 정크 메일 보고 옵션에 대한 설명 텍스트를 입력합니다. 
    
      메시지가 **보고된 경우를** 표시하는 옵션 아래에서 다음 옵션 중 하나 이상을 선택합니다.
        - **보고서를 보내기 전에 질문하기**
        - **자동으로 보고서 보내기**
        - **보고서를 보내지 않습니다.**
       
      작업을 마쳤으면 **저장** 을 클릭합니다.

        - **보고된 메시지를** 다음 중 하나를 선택합니다.

        - **Microsoft(권장)**: 사용자 제출 사서함이 사용되지 않습니다(보고된 모든 메시지는 Microsoft로 이동).

        - **Microsoft 및** 사용자 지정 사서함 모두: 나타나는 상자에 기존 사서함의 전자 메일 Exchange Online 입력합니다. 메일 그룹은 허용되지 않습니다. 사용자 제출은 분석을 위해 Microsoft로 이동하고 관리자 또는 보안 운영 팀이 분석할 사용자 지정 사서함으로 이동됩니다.

        - **사용자 지정 사서함만:** 나타나는 상자에 기존 사서함의 전자 메일 주소를 Exchange Online. 메일 그룹은 허용되지 않습니다. 메시지를 먼저 분석하기 위해 관리자 또는 보안 운영 팀으로 이동하려는 경우 이 옵션을 사용합니다. 관리자가 메시지를 직접 전달하지 않으면 메시지가 Microsoft로 이동되지 않습니다.

          > [!NOTE]
          > 미국 정부 조직(GCC, GCC-H 및 DoD)은 사용자 지정 사서함만 **구성할 수 있습니다.** 다른 두 옵션은 사용하지 않도록 설정됩니다.

          > [!NOTE]
          > 조직이 사용자 지정 사서함으로만 보내도록 구성된 경우 보고된 메시지는 다시 검색을 위해 전송되지 않습니다. 사용자 보고 메시지 포털의 결과는 항상 비어 있습니다.

      완료되면 확인 을 **클릭합니다.**

      > [!CAUTION]
      > 웹 사서함 [](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) 정책의 Outlook 사용하여 웹의 Outlook에서 정크 메일 보고를 사용하지 않도록 설정했지만 Microsoft에 메시지를 보고하도록 이전 설정을 구성한 경우 사용자는 보고서 메시지 추가 기능 또는 피싱 보고 추가 기능을 사용하여 웹의 Outlook Microsoft에 메시지를 보고할 수 있습니다.


    2. Outlook 보고서 메시지 기능 사용 안 하도록 설정 **:** 보고서 메시지 추가 기능 Outlook, 피싱 보고 추가 기능 또는 웹용 보고서의 기본 제공 보고 대신 타사 보고 도구를 사용하는 경우 이 옵션을 선택하고 다음 설정을 구성합니다.

       이 **사용자 지정 사서함을 사용하여 사용자가 보고한 제출을 받습니다.를 선택합니다.** 상자가 나타나면 이미 사서함에 있는 기존 사서함의 전자 메일 주소를 Office 365. 이 사서함은 전자 메일을 받을 수 Exchange Online 사서함의 기존 사서함이 되어야 합니다.

       완료되면 확인 을 **클릭합니다.**

## <a name="third-party-reporting-tools"></a>타사 보고 도구

보고된 메시지를 사용자 지정 사서함으로 보내도록 타사 메시지 보고 도구를 구성할 수 있습니다. 유일한 요구 사항은 원본 메시지가 사용자 지정 사서함으로 전송되는 메시지에 첨부 파일로 포함되는 것입니다(원본 메시지를 사용자 지정 사서함으로만 전달하는 것이 아니라).

메시지 서식 요구 사항은 다음 섹션에 설명되어 있습니다. 서식은 선택 사항이지만 정해진 형식을 따르지 않는 경우 보고서는 항상 피싱으로 제출됩니다.

## <a name="message-submission-format"></a>메시지 전송 형식

원래 첨부된 메시지를 올바르게 식별하려면 사용자 지정 사서함으로 전송되는 메시지에 특정 서식이 필요합니다. 메시지가 이 형식을 사용하지 않는 경우 원래 첨부된 메시지는 항상 피싱 전송으로 식별됩니다.

원래 첨부된 메시지를 올바르게 식별하려면 사용자 지정 사서함으로 전송되는 메시지는 제목(봉투 제목)에 대해 다음 구문을 사용해야 합니다.

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

여기서 SafetyAPIAction은 다음 정수 값 중 하나입니다.

- 1: 정크
- 2: 정크 아님
- 3: 피싱

이 예제에서는 다음 값을 사용합니다.

- 메시지가 피싱으로 보고되고 있습니다.
- 네트워크 메시지 ID는 49871234-6dc6-43e8-abcd-08d797f20abe입니다.
- 보낸 사람 IP는 167.220.232.101입니다.
- From 주소가 test@contoso.com.
- 메시지의 제목 줄이 "테스트 피싱 제출"입니다.

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

이 형식을 따르지 않는 메시지는 제출 포털에 제대로 표시되지 않습니다.
