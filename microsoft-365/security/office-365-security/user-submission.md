---
title: 사용자가 보고한 메시지 설정
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 관리자는 사용자가 보고하는 스팸 및 피싱 전자 메일을 수집하도록 사서함을 구성하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d288a9a5821521a68e254aa3ff97182140d66b63
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60203798"
---
# <a name="user-reported-message-settings"></a>사용자가 보고한 메시지 설정

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

사서함이 Microsoft 365 조직에서 Exchange Online 악의적이거나 악의적이지 않은 것으로 보고하는 메시지를 받을 사서함을 지정할 수 있습니다. 사용자가 다양한 보고 옵션을 사용하여 메시지를 보고할 때 이 사서함을 사용하여 메시지를 가로채거나(사용자 지정 사서함으로만 보내기) 메시지 복사본을 받거나(사용자 지정 사서함 및 Microsoft로 보내기) 할 수 있습니다. 이 기능은 다음 메시지 보고 옵션과 함께 작동합니다.

- [보고서 메시지 추가 기능](enable-the-report-message-add-in.md)
- [피싱 보고 추가 기능](enable-the-report-phish-add-in.md)
- [타사 보고 도구](#third-party-reporting-tools)

사용자가 보고한 메시지를 Microsoft에 직접 전달하는 대신 사용자 지정 사서함으로 배달하면 관리자가 관리자 제출을 사용하여 메시지를 선택적으로 수동으로 Microsoft에 보고할 [수 있습니다.](admin-submission.md) 이러한 설정은 이전의 사용자 제출 정책으로 알려졌다.

  > [!NOTE]
  > 웹용 Outlook 보고를 사용하지 않도록 설정한 경우 [여기에서](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)사용자가 보고한 메시지를 사용하도록 설정하면 해당 설정이 다시 웹용 Outlook 합니다.

## <a name="custom-mailbox-prerequisites"></a>사용자 지정 사서함 선행 준비

다음 문서를 사용하여 사용자가 보고한 메시지가 사용자 지정 사서함으로 이동하도록 필수 구성을 구성합니다.

- 스팸 지수 설정 Exchange 메일 흐름 규칙을 만들어 사용자 지정 사서함에서 스팸 필터링을 건너뜁. SCL을 스팸 필터링 무시로 설정하는 [메시지의 SCL을](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) 설정하는 메일 흐름 규칙 만들기를 **참조합니다.**

- [맬웨어에](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) 대한 ZAP(제로 아워 자동 제거)가 꺼져 있는 사용자 지정 사서함을 포함하는 맬웨어 방지 정책을 만들 수 있습니다(**보호** 설정 섹션 맬웨어에 대한 제로 아워 자동 제거 사용이 선택되어 있지 \>  않습니다).

- [스팸에](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) 대한 ZAP 및 피싱용 ZAP가 꺼져 있는 사용자 지정 사서함을 포함하는 스팸 방지 정책을 만들 수 **있습니다(** 제로 아워 자동 제거 섹션 사용 제로 아워 자동 제거(ZAP)를 선택하지 \>  않았습니다.

- 사용자 지정 사서함에서 정크 메일 규칙을 사용하지 않도록 설정 사서함에서 [정크 메일 Exchange Online 구성을 사용하여](configure-junk-email-settings-on-exo-mailboxes.md) 정크 메일 규칙을 사용하지 않도록 설정할 수 있습니다. 이 기능을 사용하지 않도록 설정한 후 EOP는 스팸 필터링 판정 동작에 따라 메시지를  정크 메일 폴더로 이동하거나 사서함의 수신할 수 있는 목록 모음으로 메시지를 이동할 수 없습니다.

Microsoft Defender for Office 365 고급 필터링이 메시지를 보고하는 사용자에게 영향을 끼치지 못하도록 아래를 구성해야 합니다.

- [금고](set-up-safe-links-policies.md) 링크 검색이 꺼져 있는 사용자 지정 사서함을 포함하는 금고 링크 정책을 만드십시오( 메시지에서 알 수 없는 악의적인 URL에 대한 작업 선택 섹션 \> **끄기).**

- [첨부 금고](set-up-safe-attachments-policies.md) 검사가 꺼져 있는 사용자 지정 사서함이 포함된 금고 첨부 파일 정책을 만들 수 있습니다(금고 알 수 없는 맬웨어 응답 섹션 \> 해제).

사서함이 적용 가능한 모든 선행 요구 사항을 충족하는지 확인한 후 이 문서의 절차에 따라 사용자 전송 사서함을 구성할 수 있습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://security.microsoft.com/>에서 Microsoft 365 Defender 포털을 엽니다. 제출 **페이지로** 직접 이동하기 위해 를 <https://security.microsoft.com/reportsubmission> 사용하세요.

- 사용자 제출에 대한 구성을 수정하려면 다음 역할 그룹 중 하나의 구성원이 되어야 합니다.

  - **조직** **포털의** 사용 권한에 있는 [조직 관리 또는 보안 Microsoft 365 Defender.](permissions-microsoft-365-security-center.md)

- PowerShell을 사용하려면 Exchange Online 액세스해야 합니다. 사용하려는 계정에 Exchange Online PowerShell에 액세스할 수 없는 경우 제출 사서함을 지정할 때 다음과 같은 오류가 표시됩니다.

  > 도메인에서 전자 메일 주소 지정

  PowerShell에 대한 액세스를 활성화하거나 Exchange Online 자세한 내용은 다음 항목을 참조하세요.

  - [Exchange Online PowerShell에 대한 액세스 설정 또는 해제](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [클라이언트 액세스 규칙의 Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-microsoft-365-defender-portal-to-configure-the-user-submissions-mailbox"></a>Microsoft 365 Defender 포털을 사용하여 사용자 제출 사서함 구성

1. Microsoft 365 Defender 포털에서 정책 **정책** & 정책 위협 정책 사용자가 기타 사용자 제출에서 메시지 설정을 \>  \>   \> **보고했습니다.**

2. 사용자 **제출 페이지에서는** Microsoft Outlook 메시지 단추 설정이 꺼지거나 으로 설정되어 **있는지** **여부에** 따라 **표시됩니다.**

   - **Microsoft Outlook 메시지 단추** \> **On** ![ 토글합니다. 보고서 메시지 추가 기능, 피싱 보고 추가 기능 또는 기본 제공 보고 기능을 웹용 Outlook 다음 설정을 구성하려면 이 ](../../media/scc-toggle-on.png) 옵션을 선택합니다.
     - **보고된 메시지를** 다음 옵션 중 하나를 선택합니다.
       - **Microsoft:** 사용자 전송 사서함이 사용되지 않습니다(보고된 모든 메시지는 Microsoft로 이동).
       - **Microsoft 및 내** 조직의 사서함: 나타나는 상자에 기존 사서함의 전자 메일 주소를 Exchange Online. 메일 그룹은 허용되지 않습니다. 사용자 제출은 분석을 위해 Microsoft로 이동하고 관리자 또는 보안 운영 팀이 분석할 사용자 지정 사서함으로 이동됩니다.
       - **조직의 사서함:** 나타나는 상자에 기존 사서함의 전자 메일 주소를 Exchange Online. 메일 그룹은 허용되지 않습니다. 메시지를 먼저 분석하기 위해 관리자 또는 보안 운영 팀으로 이동하려는 경우 이 옵션을 사용합니다. 관리자가 메시지를 직접 전달하지 않으면 메시지가 Microsoft로 이동되지 않습니다.

          > [!IMPORTANT]
          > 미국 정부 조직(GCC, GCC High 및 DoD)은 내 조직의 사서함만 **구성할 수 있습니다.** 다른 두 옵션은 사용하지 않도록 설정됩니다.
          >
          > 조직이 사용자 지정 사서함으로만 보내도록 구성된 경우 보고된 메시지는 다시 검색을 위해 전송되지 않습니다. 사용자 보고 메시지 포털의 결과는 항상 비어 있습니다.

       보고된 메시지를 보내기 위해 선택한 값에 관계없이 다음 설정을 사용할 수 있습니다.

       - **사용자가 Microsoft에 메시지를 보고할지 선택할 수 있도록 합니다.**
       - **사용자가 사용할 수 있는** 보고 옵션 선택 섹션: 다음 옵션 중 하나 이상을 선택합니다.
         - **메시지를 보내기 전에 질문하기**
         - **항상 메시지 보고**
         - **메시지를 보고하지 않습니다.**

          > [!CAUTION]
          > 웹용 Outlook 사서함 [](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) 정책을 사용하여 웹용 Outlook 웹용 Outlook 정크 메일 보고를 사용하지 않도록 설정했지만 Microsoft에 메시지를 보고하도록 이전 설정을 구성한 경우 사용자는 보고서 메시지 추가 기능 또는 피싱 보고 추가 기능을 사용하여 웹용 Outlook Microsoft에 메시지를 보고할 수 있습니다.

     최종 **사용자가** Outlook 포털에서 가짓 긍정 메시지를 보고할 수 있도록 Microsoft Outlook 메시지 보고 단추 설정을 설정으로 ![ ](../../media/scc-toggle-on.png)  전환합니다.

     - **사용자 보고 환경 섹션**
       - **보고 탭** 전에:  제목  및 메시지 본문 상자에 보고서 메시지 추가 기능 또는 피싱 보고 추가 기능을 사용하여 메시지를 보고하기 전에 사용자에게 설명 텍스트를 입력합니다. %type% 변수를 사용하여 제출 유형(정크, 피싱 등이 아님)을 포함할 수 있습니다.
       - **보고 탭** 후:  제목  및 확인 메시지 상자에 보고서 메시지 추가 기능 또는 피싱 보고 추가 기능을 사용하여 메시지를 보고한 후 사용자에게 설명 텍스트를 입력합니다. %type% 변수를 사용하여 제출 유형을 포함할 수 있습니다.
       -  **사용자가 피싱을** 보고할 때만 표시: 전자 메일이 피싱으로 보고된 경우만 메시지를 표시하려는 경우 이 옵션을 선택합니다. 그렇지 않은 경우 모든 종류의 보고서에 대해 확인된 메시지가 표시됩니다.

       페이지에 표시된 것 처럼 보고된 메시지를 Microsoft로 보내는 옵션을 선택하면 알림에 다음 텍스트도 추가됩니다.

          > 분석을 위해 전자 메일이 Microsoft에 있는 동안 제출됩니다. 일부 전자 메일에는 개인 또는 중요한 정보가 포함될 수 있습니다.

   - **Microsoft Outlook 메시지 단추** \> **끄기** ![ 토글 해제: 보고서 메시지 추가 기능, 피싱 보고 추가 기능 또는 기본 제공 웹용 Outlook 대신 타사 보고 도구를 사용하는 경우 이 옵션을 선택하고 다음 설정을 ](../../media/scc-toggle-off.png) 구성합니다.
     - 이 **사용자 지정 사서함을 사용하여 사용자가 보고한 제출을 받습니다.를 선택합니다.** 나타나는 상자에 전자 메일을 받을 수 있는 기존 Exchange Online 사서함의 전자 메일 주소를 입력합니다.

   - **Microsoft Outlook 메시지** 보고 단추: 최종 사용자가 메시지를 검지에서 보고할 수 있도록 하려는 경우 이 기능을 사용하도록 설정하세요.

   완료되면 확인 을 **클릭합니다.** 이러한 값을 지우려면 **복원을 클릭합니다.**

## <a name="third-party-reporting-tools"></a>타사 보고 도구

보고된 메시지를 사용자 지정 사서함으로 보내도록 타사 메시지 보고 도구를 구성할 수 있습니다. **Microsoft** Outlook 보고 메시지 단추 설정을 끄기로  설정하고 내  조직의 사서함을 원하는 사서함으로 Office 365 합니다.

유일한 요구 사항은 원본 메시지가 로 포함되는 것입니다. EML 또는 . 사용자 지정 사서함으로 전송된 메시지의 MSG 첨부 파일(압축되지 않습니다.)

메시지 서식 요구 사항은 다음 섹션에 설명되어 있습니다. 서식은 선택 사항이지만 정해진 형식을 따르지 않는 경우 보고서는 항상 피싱으로 제출됩니다.

## <a name="message-submission-format"></a>메시지 전송 형식

원래 첨부된 메시지를 올바르게 식별하려면 사용자 지정 사서함으로 전송되는 메시지에 특정 서식이 필요합니다. 메시지가 이 형식을 사용하지 않는 경우 원래 첨부된 메시지는 항상 피싱 전송으로 식별됩니다.

원래 첨부된 메시지에 대해 보고된 이유를 지정하려면 사용자 지정 사서함으로 전송된 메시지(첨부 파일을 수정하지 않고)는 제목(봉투 제목)의 다음 주소 중 하나에서 시작해야 합니다.

- 1| 또는 정크:
- 2| 또는 정크 아님
- 3| 또는 피싱

예제:

`3|This part is ignored by the system` <br>
`Not Junk:This part of the subject is ignored as well`

- 이러한 메시지는 모두 제목에 따라 정크 메일 아님으로 보고됩니다.
- 나머지는 무시됩니다.


이 형식을 따르지 않는 메시지는 제출 포털에 제대로 표시되지 않습니다.
