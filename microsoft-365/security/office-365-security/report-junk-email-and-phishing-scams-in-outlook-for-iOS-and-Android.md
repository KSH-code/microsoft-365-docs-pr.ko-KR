---
title: IOS 및 Android 용 Outlook에서 정크 및 피싱 전자 메일 보고
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
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: 관리자는 iOS 및 Android 용 Outlook에서 기본적으로 제공 되는 정크 메일, 정크 메일이 아닌 경우 및 피싱 메일로 보고 옵션에 대해 알아볼 수 있습니다.
ms.openlocfilehash: 23668a762301ee442bc805e62863079ee7ae6076
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350858"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a>Exchange Online에서 iOS 및 Android 용 Outlook에서 정크 및 피싱 전자 메일 보고

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online 또는 온-프레미스 사서함의 사서함을 포함 하는 Microsoft 365 조직에서 [하이브리드 최신 인증](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview)을 사용 하는 경우 Outlook에서 IOS 및 Android 용 기본 제공 보고 옵션을 사용 하 여 가양성 (스팸으로 표시 된 전자 메일), 거짓 네거티브 (잘못 된 전자 메일 허용), EOP (Exchange Online Protection)로의 피싱 메시지를 제출할 수 있습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작 하기 전에 알아야 할 사항

- Exchange Online 사서함을 사용 하는 조직의 관리자 인 경우 보안 & 준수 센터에서 전송 포털을 사용 하는 것이 좋습니다. 자세한 내용은 [관리자 제출을 사용 하 여 의심 스러운 스팸, 피싱, url 및 파일을 Microsoft에 제출](admin-submission.md)합니다 .를 참조 하세요.

- 보고 된 메시지가 사용자가 지정한 사서함으로 복사 되거나 리디렉션되도록 구성할 수 있습니다. 자세한 내용은 [사용자 전송 정책을](user-submission.md)참조 하세요.

- Microsoft에 메시지를 보고 하는 방법에 대 한 자세한 내용은 [microsoft에 메시지 및 파일 보고서](report-junk-email-messages-to-microsoft.md)를 참조 하십시오.

  > [!NOTE]
  > 사용자 전송 정책에서 정크 메일 보고 기능을 Outlook에서 사용 하지 않도록 설정한 경우 정크 또는 피싱 메시지가 정크 폴더로 이동 되 고 관리자 또는 Microsoft에 보고 되지 않습니다.

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a>IOS 및 Android 용 Outlook에서 스팸 및 피싱 메시지 보고

받은 편지함 또는 정크 메일을 제외한 다른 전자 메일 폴더의 메시지에 대해 iOS 및 Android의 스팸 및 피싱 메시지를 보고 하려면 다음 단계를 사용 합니다.

1. 하나 이상의 메시지를 선택 합니다.
2. 오른쪽 위 모서리에 있는 3 개의 세로 점을 누릅니다. 동작 메뉴가 열립니다.

   ![작업 메뉴에서 정크 또는 피싱 전자 메일 보고](../../media/Android-report-as-junk-dialog.png)

3. **정크 메일 보고** 를 누른 다음 **정크** 또는 **피싱**을 선택 합니다.

   ![정크 또는 피싱 전자 메일 보고](../../media/Android-report-junk-or-phishing.png)

4. 대화 상자가 나타나면 **보고서** 를 선택 하거나 **아니요/아니요**를 선택할 수 있습니다. **아니요 아니요**를 선택 하면 **정크** 메일 폴더로 메시지가 이동 하는 경우 **피싱** 메일로 보낸 메시지는 지운 편지함 폴더로 이동 됩니다. **보고서** 를 선택 하 여 메시지의 복사본을 Microsoft로 보냅니다.

   ![정크 또는 피싱 전자 메일 보고 옵션 보고](../../media/Android-junk-email-reporting-options.png)

생각이 변경 되 면 표시 되는 toast 알림에서 **실행 취소** 를 선택 합니다. 메시지가 받은 편지함 폴더에 남아 있습니다.

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a>IOS 및 Android 용 Outlook의 정크 폴더에서 스팸이 아닌 메시지 신고

정크 폴더에서 다음 단계를 사용 하 여 스팸이 가양성을 보고 합니다.

1. 하나 이상의 메시지를 선택 합니다.
2. 오른쪽 위 모서리에 있는 3 개의 세로 점을 누릅니다. 동작 메뉴가 열립니다.

   ![작업 메뉴에서 정크 메일 아님으로 보고](../../media/Android-not-junk-email.png)

3. **정크 메일 아님으로**탭 합니다.

전자 메일이 받은 편지 함으로 이동 되었음을 알리는 알림 메시지가 표시 됩니다. 생각이 변경 되 면 toast 알림에서 **실행 취소** 를 선택 합니다. 전자 메일이 정크 폴더에 남아 있습니다.
