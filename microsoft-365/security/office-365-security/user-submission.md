---
title: 사용자 전송 및 피싱 메시지의 사서함 지정
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
description: 관리자는 사용자가 보고한 스팸 및 피싱 전자 메일을 수집하도록 사서함을 구성하는 방법에 대해 알아내세요.
ms.openlocfilehash: 76264801820b6a41ee744a8adcc3b3b48a8e9479
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826744"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a>Exchange Online에서 스팸 및 피싱 메시지의 사용자 전송을 위한 사서함 지정

Exchange Online 사서함이 있는 Microsoft 365 조직에서는 사용자가 악의적인 보안으로 보고하거나 악의적으로 보고하는 메시지를 받을 사서함을 지정할 수 있습니다. 사용자가 다양한 보고 옵션을 사용하여 메시지를 전송하면 이 사서함을 사용하여 사용자 지정 사서함에 메시지를 가로가져오거나(사용자 지정 사서함에 보낸 메시지) 복사본(사용자 지정 사서함에 전송 및 Microsoft)을 받을 수 있습니다. 이 기능은 다음 메시지 보고 옵션에서 사용할 수 있습니다.

- [보고서 메시지 추가 기능](enable-the-report-message-add-in.md)

- [웹용 Outlook(이전의 양식](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) 기능이라고함 Outlook Web App)

- iOS 및 Android용 Outlook에 기본 제공 보고

  > [!NOTE]
  > 웹용 Outlook에서 보고를 [사용하지 않도록](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)설정한 경우 여기에서 사용자 전송을 사용하도록 설정하면 해당 설정이 재정의되고 사용자가 웹용 Outlook에서 메시지를 다시 보고할 수 있습니다.

타사 메시지 보고 도구를 구성하여 지정된 사서함으로 메시지를 전달할 수도 있습니다.

사용자가 직접 Microsoft가 아닌 사용자 지정 사서함에 메시지를 배달하면 관리자가 관리자 전송을 사용하여 메시지를 선택적으로 Microsoft에 선택하여 수동으로 Microsoft에 [보고할 수 있습니다.](admin-submission.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 준수 센터를 엽니다. 사용자 제출 페이지로 **직접 이동하려면** 을 사용합니다. <https://protection.office.com/userSubmissionsReportMessage>

- 이 항목의 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.

  - 사용자 전송의 구성을 수정하려면 다음 역할 그룹 중 하나의 구성원이어야 합니다.

    - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리** 및 **예방 조치 관리**

  - 사용자 전송에 대한 읽기 전용 액세스를 위해는 다음 역할 그룹 중 하나의 구성원이어야 합니다.

    - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **보안 읽기**
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리**

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>보안 센터 & 사용하여 사용자 제출 사서함 구성

1. 보안 센터& 위협 관리 정책 **사용자** \> **Policy** \> **제출로 이동합니다.**

2. 표시되는 **사용자 제출** 페이지에서 다음 옵션 중 하나를 선택합니다.

   a. **Outlook에 대해 보고 메시지 기능 사용(권장):** 웹용 Outlook에서 보고서 메시지 추가 기능 또는 기본 제공 보고기능을 사용하는 경우 이 옵션을 선택하고 다음 설정을 구성합니다.

      - **최종 사용자 확인 메시지를 사용자 지정합니다.** 이 링크를 클릭합니다. 표시되는 사용자 지정 확인 메시지 플라이아웃에서 다음 설정을 구성합니다. **Customize confirmation message**

      - **제출 하기:** **제목 및** **확인 메시지 상자에** 보고서 메시지 추가 기능을 사용하여 메시지를 보고하기 전에 사용자에게 표시되는 설명 텍스트를 입력합니다. %type% 변수를 사용하여 제출 유형(정크, 정크 메일 아님, 피싱 등)을 포함할 수 있습니다.

        앞에서 설명한 것과 같이, 보고된 메시지를 Microsoft로 보내는 옵션을 선택하면 알림에 다음 텍스트도 추가됩니다.

        > 메일은 분석을 위해 Microsoft에 있는 있는 것과 같습니다. 일부 이메일에는 개인 정보나 민감한 정보가 포함될 수 있습니다.

      - **제출 후:** Expand ![ 아이콘을 ](../../media/scc-expand-icon.png) 클릭합니다. 제목 **및** **확인 메시지 상자에는** 사용자가 보고서 메시지 추가 기능을 사용하여 메시지를 보고한 후 표시되는 설명 텍스트를 입력합니다. %type% 변수를 사용하여 제출 유형을 포함할 수 있습니다.

      작업을 마쳤으면 **저장**을 클릭합니다. 이들 값을 **지우려면 사용자** 제출 페이지에서 **복원을 클릭합니다.**

      - **보고된 메시지를 다음**중 하나로 지정합니다.

        - **Microsoft(권장):** 사용자 전송 사서함이 사용되지 않음(보고된 모든 메시지가 Microsoft로 이동).

        - **Microsoft 및 사용자 지정**사서함: 표시되는 상자에 기존 Exchange Online 사서함의 전자 메일 주소를 입력합니다. 메일 그룹은 허용되지 않습니다. 사용자 제출이 분석을 위해, 관리자 또는 보안 작업 팀에서 분석을 위해 Microsoft와 사용자 지정 사서함으로 이동하여 분석합니다.

        - **사용자 지정**사서함: 표시되는 상자에 기존 Exchange Online 사서함의 전자 메일 주소를 입력합니다. 메일 그룹은 허용되지 않습니다. 메시지가 먼저 분석을 위해 관리자 또는 보안 작업 팀으로 이동할 수도 있도록 하려면 이 옵션을 사용합니다. 관리자가 메시지를 전달하지 않으면 메시지는 Microsoft로 전달되지 않습니다.

        > [!NOTE]
        > 미국 정부 조직(GCC, GCC-H, DoD)은 사용자 지정 사서함만 구성할 **수 있습니다.** 다른 두 옵션은 사용하지 않도록 설정됩니다. 

      작업을 마치면 Confirm (확인)을 **클릭합니다.**

      > [!CAUTION]
      > 웹용 Outlook 사서함 정책을 사용하여 [웹용 Outlook에서](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) 정크 메일 보고를 사용하지 않도록 설정하고 이전 설정 중 하나를 구성한 경우 사용자는 보고서 메시지 추가 기능을 사용하여 웹용 Outlook에서 Microsoft에 메시지를 보고할 수 있습니다.

   - **Outlook에 대해 보고 메시지 기능 비활성화**: 웹용 Outlook에서 보고서 메시지 추가 기능 또는 기본 제공 보고 대신 타사 보고 도구를 사용하는 경우 이 옵션을 선택하고 다음 설정을 구성합니다.

      이 **사용자 지정 사서함을 선택하여 사용자가 보고한 제출을 받습니다.** 나타나는 상자에 이미 Office 365에 있는 기존 사서함의 전자 메일 주소를 입력합니다. 이 사서함은 전자 메일을 받을 수 있는 Exchange Online의 기존 사서함입니다.

      작업을 마치면 Confirm (확인)을 **클릭합니다.**

## <a name="message-submission-format"></a>메시지 전송 형식

사용자 지정 사서함에 보내는 메시지는 특정 전송 메일 형식을 따라야 합니다. 제출의 제목(봉투 제목)은 다음 형식이 되어야 합니다.

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

SafetyAPIAction은 다음 정수 값 중 하나입니다.

- 1: 정크
- 2: NotJunk
- 3: 피싱

다음 예에서:

- 메시지가 피싱으로 보고됩니다.
- 네트워크 메시지 ID는 49871234-6dc6-43e8-abcd-08d797f20abe입니다.
- 보낸 사람 IP는 167.220.232.101입니다.
- 시작 주소는 test@contoso.com.
- 메시지의 제목 줄이 "테스트 피싱 제출"입니다.

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

이 형식을 따르지 않는 메시지는 제출 포털에 제대로 표시되지 않습니다.
