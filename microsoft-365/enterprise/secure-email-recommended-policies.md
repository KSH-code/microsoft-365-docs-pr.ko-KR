---
title: 보안 메일 권장 정책 - Microsoft 365 Enterprise | Microsoft Docs
description: 메일 정책과 구성을 적용하는 방법에 관한 Microsoft 권장 정책을 설명합니다.
author: brendacarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 101ebbe46b9f49a1a450c4cb22b5d5f67ce1b322
ms.sourcegitcommit: bd487d36b04b8f8caf10900e8c5237f9ccf9e072
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2019
ms.locfileid: "37654027"
---
# <a name="policy-recommendations-for-securing-email"></a>메일을 보호하기 위한 정책 권장 사항

이 문서에서는 최신 인증 및 조건부 액세스를 지 원하는 조직 전자 메일 및 전자 메일 클라이언트를 보호 하기 위해 권장 되는 id 및 장치 액세스 정책을 구현 하는 방법을 설명 합니다. 이 지침은 [일반 id 및 장치 액세스 정책](identity-access-policies.md) 에 대해 구축 되며 몇 가지 추가 권장 사항도 포함 되어 있습니다.

이러한 권장 사항은 **기본**, **중요**및 **높은 규제**의 요구 사항에 따라 적용할 수 있는 세 가지 다른 보안 및 보호 계층을 기반으로 합니다. [권장되는 보안 정책 및 구성 소개](microsoft-365-policies-configurations.md)에서 이러한 권장 사항을 참조하여 이러한 보안 계층, 권장되는 클라이언트 운영 체제에 대해 더 자세히 알아볼 수 있습니다.

이러한 권장 사항을 적용 하려면 사용자가 모바일 장치에서 iOS 및 Android 용 Outlook을 비롯 한 최신 전자 메일 클라이언트를 사용 해야 합니다. IOS 및 Android 용 Outlook에서는 Office 365의 최상의 기능을 지원 합니다. 이러한 모바일 Outlook 앱은 모바일 사용을 지원 하 고 다른 Microsoft 클라우드 보안 기능과 함께 사용할 수 있는 보안 기능으로도 설계 되었습니다. 자세한 내용은 [iOS 및 Android 용 OUTLOOK FAQ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)를 참조 하세요.

## <a name="updating-common-policies-to-include-email"></a>전자 메일을 포함 하도록 일반 정책 업데이트

다음 다이어그램에서는 일반 id 및 장치 액세스 정책을 보여주고 전자 메일을 보호 하기 위해 업데이트 해야 하는 정책을 나타냅니다. Exchange Online에 대 한 새 규칙을 추가 하 여 ActiveSync 클라이언트를 차단 하는 방법에 유의 하세요. 이렇게 하면 Outlook mobile을 사용 하 게 됩니다.

![전자 메일을 보호 하기 위한 정책 업데이트 요약](../images/identity-access-ruleset-mail.png)

정책을 설정할 때 정책 범위에 Exchange Online과 Outlook을 포함 한 경우에는 ActiveSync 클라이언트를 차단 하는 새 정책만 만들면 됩니다. 다음 표에 나와 있는 정책 들을 검토 하 고 권장 되는 추가 내용을 확인 하거나 이미 포함 되어 있는 것을 확인 합니다. 각 규칙은 [일반 id 및 장치 액세스 정책](identity-access-policies.md) 문서의 관련 구성 지침에 연결 됩니다.

|보호 수준|정책도|추가 정보|
|:---------------|:-------|:----------------|
|**기준**|[로그인 위험이 *보통* 또는 *높을* 때 MFA 필요](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|클라우드 앱 할당에 Exchange Online 포함|
|        |[최신 인증을 지원 하지 않는 클라이언트 차단](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|클라우드 앱 할당에 Exchange Online 포함|
|        |[앱 보호 정책 정의](identity-access-policies.md#high-risk-users-must-change-password)|Outlook이 앱 목록에 포함 되어 있어야 합니다. 각 플랫폼의 정책 (iOS, Android, Windows)을 업데이트 해야 합니다.|
|        |[승인 된 앱 필요](identity-access-policies.md#require-approved-apps)|클라우드 앱 목록에 Exchange Online 포함|
|        |[준수 Pc 필요](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|클라우드 앱 목록에 Exchange Online 포함|
|        |[ActiveSync 클라이언트 차단](#block-activesync-clients)|새 정책 추가| 
|**중요**|[로그인 위험이 *낮은* *경우 MFA* 필요 **](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| 클라우드 앱 할당에 Exchange Online 포함|
|         |[준수 Pc *및* 모바일 장치 요구](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|클라우드 앱 목록에 Exchange Online 포함|
|**높은 규제**|[*항상* MFA 필요](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|클라우드 앱 할당에 Exchange Online 포함|

## <a name="block-activesync-clients"></a>ActiveSync 클라이언트 차단

이 정책은 ActiveSync 클라이언트가 다른 조건부 액세스 규칙을 무시할 수 없도록 합니다. 규칙 구성은 ActiveSync 클라이언트에만 적용 됩니다. 승인 된 **클라이언트 앱 필요**를 선택 하면이 정책은 ActiveSync 클라이언트를 차단 합니다. 이 정책을 구성 하려면 다음을 수행 합니다.

1. [Azure Portal](https://portal.azure.com)로 이동한 다음 자격 증명을 사용하여 로그인합니다. 성공적으로 로그인 하면 Azure 대시보드가 표시 됩니다.

2. 왼쪽 메뉴에서 **Azure Active Directory**를 선택합니다.

3. **보안** 섹션 아래에서 **조건부 액세스**를 선택합니다.

4. **새 정책**을 선택합니다.

5. 정책 이름을 입력한 다음 정책을 적용할 **사용자 및 그룹**을 선택합니다.

6. **클라우드 앱**을 선택합니다.

7. **앱 선택을**선택 하 고 **Office 365 Exchange Online**을 선택 합니다. **선택** 및 **완료**를 선택 합니다.

8. **조건을**선택 하 고 **클라이언트 앱**을 선택 합니다.

9. **구성**하려면 **예**를 선택 합니다. **모바일 앱 및 데스크톱 클라이언트** 및 **Exchange ActiveSync 클라이언트만**확인 합니다. **완료**를 선택합니다.

10. **액세스 제어** 섹션에서 **권한 부여**를 선택합니다.

11. **액세스 부여**를 선택 하 고 **승인 된 클라이언트 앱 필요**를 선택 합니다.  여러 컨트롤에 대해 **선택한 컨트롤 필요**를 선택한 다음 **선택을**선택 합니다.

12. **만들기**를 선택합니다.

## <a name="setup-office-365-message-encryption"></a>Office 365 메시지 암호화 설정

Azure Information Protection의 보호 기능을 활용 하는 새로운 Office 365 메시지 암호화 (OME) 기능을 사용 하면 조직에서 모든 장치에 있는 모든 사용자와 보호 된 전자 메일을 쉽게 공유할 수 있습니다. 사용자는 Outlook.com, Gmail 및 기타 전자 메일 서비스를 사용 하는 Office 365 이외의 다른 Office 365 조직과 보호 된 메시지를 주고 받을 수 있습니다.

자세한 내용은 [Set Up Office 365 Message Encryption capabilities](https://support.office.com/article/set-up-new-office-365-message-encryption-capabilities-7ff0c040-b25c-4378-9904-b1b50210d00e)를 참조 하십시오.

## <a name="next-steps"></a>다음 단계

[SharePoint 사이트 및 파일을 보호하기 위한 정책 권장 사항 알아보기](sharepoint-file-access-policies.md)
