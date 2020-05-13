---
title: 스팸 및 피싱 메시지의 사용자 제출을 위한 사서함 지정
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 관리자는 사용자가 보고 하는 스팸 및 피싱 전자 메일을 수집 하도록 사서함을 구성 하는 방법을 확인할 수 있습니다.
ms.openlocfilehash: 7b4b913a29c3eb16286d5a2874fe48bbc1c121fe
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208504"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a>Exchange Online에서 스팸 및 피싱 메시지의 사용자 제출을 위한 사서함 지정

Exchange Online 사서함이 있는 Microsoft 365 조 직에서는 사용자가 악성 메일로 보고 하는 메시지를 수신 하는 사서함을 지정할 수 있습니다. 사용자가 다양 한 보고 옵션을 사용 하 여 메시지를 전송 하는 경우이 사서함을 사용 하 여 메시지를 가로채 며 (사용자 지정 사서함에만 보냄) 메시지 복사본을 받을 수 있습니다 (사용자 지정 사서함 및 Microsoft로 보내기). 이 기능은 다음과 같은 메시지 보고 옵션에서 작동 합니다.

- [보고서 메시지 추가 기능](enable-the-report-message-add-in.md)

- 웹용 Outlook (이전의 Outlook Web App) [에 기본적으로 제공 되는 보고 기능](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)

또한 타사 메시지 보고 도구를 구성 하 여 지정한 사서함에 메시지를 전달할 수 있습니다.

사용자가 보고 한 메시지를 Microsoft에 직접 배포 하는 대신 사용자 지정 사서함에 전달 하면 관리자가 [관리 제출을](admin-submission.md)사용 하 여 메시지를 선택적으로 수동으로 microsoft에 보고할 수 있습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 규정 준수 센터를 엽니다. **사용자 전송** 페이지로 직접 이동 하려면를 사용 <https://protection.office.com/userSubmissionsReportMessage> 합니다.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결하기](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)를 참조하세요. Exchange Online Protection PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결하기](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)를 참조하세요.

- 이 절차를 수행하려면 먼저 사용 권한을 할당 받아야 합니다. 사용자 제출을 위한 사서함을 구성 하려면 **조직 관리** 또는 **보안 관리자** 역할 그룹의 구성원 이어야 합니다. 보안 및 규정 준수 센터의 역할 그룹에 대한 자세한 내용은 [보안 및 규정 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>보안 & 준수 센터를 사용 하 여 사용자 전송 사서함을 구성 합니다.

1. 보안 & 준수 센터에서 **위협 관리** \> **정책** \> **사용자 전송**으로 이동 합니다.

2. **사용자 제출** 페이지가 나타나면 다음 옵션 중 하나를 선택 합니다.

   - **Outlook에 대 한 보고서 메시지 기능 사용 (권장)**: 웹에서 보고서 메시지 추가 기능 또는 기본 제공 보고를 사용 하는 경우이 옵션을 선택 하 고 다음 설정을 구성 합니다.

     - **최종 사용자에 게 확인 메시지를 사용자 지정**:이 링크를 클릭 합니다. 표시 되는 **확인 메시지 플라이 아웃 사용자 지정** 에서 다음 설정을 구성 합니다.

       - **제출 전**: **제목** 및 **확인 메시지** 상자에 사용자가 보고서 메시지 추가 기능을 사용 하 여 메시지를 보고 하기 전에 표시 되는 설명 텍스트를 입력 합니다. 전송 유형 (정크, 정크 메일 아님, 피싱 등)을 포함 하 여% type% 변수를 사용할 수 있습니다.

         설명 했 듯이 다음과 같은 텍스트도 알림에 추가 됩니다.

         > 전자 메일이 분석을 위해 Microsoft에 게 제출 됩니다. 일부 전자 메일에는 개인 정보나 중요 한 정보가 포함 될 수 있습니다.

       - **제출 후** ![ 확장 아이콘을 클릭 ](../../media/scc-expand-icon.png) 합니다. **제목** 및 **확인 메시지** 상자에 사용자가 보고서 메시지 추가 기능을 사용 하 여 메시지를 보고 한 후에 표시 되는 설명 텍스트를 입력 합니다. 전송 유형을 포함 하기 위해% type% 변수를 사용할 수 있습니다.

      작업을 마쳤으면 **저장**을 클릭합니다. 이러한 값을 지우려면 **사용자 전송** 페이지에서 다시 **복원을** 클릭 합니다.

   - **보고 된 메시지를 보낼**위치: 다음 중 하나를 선택 합니다.

     - **Microsoft (권장)**: 사용자 제출 사서함이 사용 되지 않습니다 (보고 된 모든 메시지는 Microsoft로 이동 됨).

     - **Microsoft 및 사용자 지정 사서함**: 표시 되는 상자에 기존 Exchange Online 사서함의 전자 메일 주소를 입력 합니다. 메일 그룹을 사용할 수 없습니다.

     - **사용자 지정 사서함**: 표시 되는 상자에 기존 Exchange Online 사서함의 전자 메일 주소를 입력 합니다. 메일 그룹을 사용할 수 없습니다.

     작업이 완료 되 면 **확인**을 클릭 합니다.

     ![보고 된 메시지를 Microsoft 및 사용자 지정 사서함으로 보내기](../../media/user-submission-enable-outlook-report-message.png)

   - **Outlook에 대 한 보고서 메시지 기능 사용 안 함**:이 옵션을 선택 하면 보고서 메시지 추가 기능 대신 타사 보고 도구를 사용 하거나, 웹에서 Outlook에서 기본 제공 되는 보고를 사용할 수 있습니다.

     **사용자가 보고 한 제출을 수신 하려면이 사용자 지정 사서함 사용을**선택 합니다. 상자가 나타나면 기존 사서함의 전자 메일 주소 또는 만들려는 사서함의 전자 메일 주소를 입력 합니다.

     작업이 완료 되 면 **확인**을 클릭 합니다.

     ![타사 도구를 사용 하 여 보고 된 메시지를 사용자 지정 사서함으로 보내기](../../media/user-submission-disable-outlook-report-message.png)
