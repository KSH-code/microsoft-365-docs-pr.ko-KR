---
title: 보안 전자 메일 권장 정책 - Microsoft 365 정책에 대한 | Microsoft Docs
description: 메일 정책과 구성을 적용하는 방법에 관한 Microsoft 권장 정책을 설명합니다.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- remotework
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: de1a66fcf2b057e2f1254d64286b521928d2c560
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59211585"
---
# <a name="policy-recommendations-for-securing-email"></a>메일을 보호하기 위한 정책 권장 사항

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)

이 문서에서는 최신 인증 및 조건부 액세스를 지원하는 조직 전자 메일 및 전자 메일 클라이언트를 보호하기 위해 권장되는 ID 및 장치 액세스 정책을 구현하는 방법을 설명합니다. 이 지침은 공통 [ID](identity-access-policies.md) 및 장치 액세스 정책을 구축하며 몇 가지 추가 권장 사항도 포함합니다.

이러한 권장 사항은 요구의 세분성에 따라 적용할 수 있는 세 가지 보안 및 보호 계층(기준, 중요 및 높은 규제)을 기반으로 **합니다.** [권장되는 보안 정책 및 구성 소개](microsoft-365-policies-configurations.md)에서 이러한 권장 사항을 참조하여 이러한 보안 계층, 권장되는 클라이언트 운영 체제에 대해 더 자세히 알아볼 수 있습니다.

이러한 권장 사항을 사용하려면 사용자가 모바일 장치에서 iOS 및 Android용 앱을 Outlook 최신 전자 메일 클라이언트를 사용해야 합니다. Outlook 및 Android용 버전은 iOS 및 Android용 앱의 최상의 기능을 Office 365. 이러한 모바일 Outlook 앱은 모바일 사용을 지원하고 다른 Microsoft 클라우드 보안 기능과 함께 작동할 수 있는 보안 기능으로 설계됩니다. 자세한 내용은 [iOS 및 Outlook FAQ를 참조하세요.](/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)

## <a name="update-common-policies-to-include-email"></a>전자 메일을 포함 하게 일반적인 정책 업데이트

다음 다이어그램에서는 전자 메일을 보호하기 위해 공통 ID 및 장치 액세스 정책에서 업데이트할 정책을 보여 제공합니다.

[![사용자 및 해당 종속 서비스에 대한 액세스를 보호하기 위한 Teams 업데이트 요약입니다.](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

ActiveSync 클라이언트를 차단하는 Exchange Online 새 정책이 추가되었습니다. 따라서 모바일을 강제로 Outlook 합니다.

정책 Exchange Online Outlook 정책 범위에 포함된 경우 ActiveSync 클라이언트를 차단하는 새 정책을 만들어야 합니다. 다음 표에 나열된 정책을 검토하고 권장되는 정책을 추가하거나 이러한 정책이 이미 포함되어 있는지 확인할 수 있습니다. 각 정책은 일반 ID 및 장치 액세스 정책의 관련 구성 [지침에 연결됩니다.](identity-access-policies.md)

|보호 수준|정책|추가 정보|
|---|---|---|
|**기준**|[로그인 위험이 중간 또는 높음인 경우 MFA *필요*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|클라우드 Exchange Online 할당에 사용자 지정 포함|
||[최신 인증을 지원하지 않는 클라이언트 차단](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|클라우드 Exchange Online 할당에 사용자 지정 포함|
||[APP 데이터 보호 정책 적용](identity-access-policies.md#apply-app-data-protection-policies)|앱 Outlook 목록에 포함해야 합니다. 각 플랫폼에 대한 정책을 업데이트해야 합니다(iOS, Android, Windows).|
||[승인된 앱 및 APP 보호 필요](identity-access-policies.md#require-approved-apps-and-app-protection)|클라우드 Exchange Online 목록에 추가|
||[호환 PC 필요](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|클라우드 Exchange Online 목록에 앱 포함|
||[ActiveSync 클라이언트 차단](#block-activesync-clients)|이 새 정책 추가|
|**중요**|[로그인 위험이 낮거나 보통 또는 *높을* 때 MFA *필요*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|클라우드 Exchange Online 할당에 사용자 지정 포함|
||[호환 PC 및 *모바일* 장치 필요](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|클라우드 Exchange Online 목록에 추가|
|**매우 엄격한 규제**|[*항상* MFA 필요](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|클라우드 Exchange Online 할당에 사용자 지정 포함|
|

## <a name="block-activesync-clients"></a>ActiveSync 클라이언트 차단

이 정책은 ActiveSync 클라이언트가 다른 조건부 액세스 정책을 무시하지 못하게 합니다. 정책 구성은 ActiveSync 클라이언트에만 적용됩니다. 앱 보호 정책 **[필요를](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)** 선택하여 이 정책은 ActiveSync 클라이언트를 차단합니다. 이 정책을 만드는 데 대한 자세한 내용은 조건부 액세스를 사용하여 클라우드 앱 액세스에 대한 앱 보호 정책 [필요에서 찾을 수 있습니다.](/azure/active-directory/conditional-access/app-protection-based-conditional-access)

- [Scenario 1: Office 365 apps require approved apps with app](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)protection policies의 "2단계: EAS(ActiveSync)를 사용하는 Exchange Online Azure AD 조건부 액세스 정책 구성"에 따라 기본 인증을 활용하는 Exchange ActiveSync 클라이언트가 EAS에 연결할 수 Exchange Online.

또한 인증 정책을 사용하여 [](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)기본 인증을 사용하지 않도록 설정할 수 있습니다. 이 경우 모든 클라이언트 액세스 요청에서 최신 인증을 강제로 사용할 수 있습니다.

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a>사용자 액세스 Exchange Online 제한 웹용 Outlook

사용자가 umnanaged 장치에서 첨부 파일을 다운로드할 웹용 Outlook 제한할 수 있습니다. 이러한 장치의 사용자는 장치에서 파일을 누출하고 저장하지 않고 Office Online을 사용하여 이러한 파일을 보고 편집할 수 있습니다. 관리되지 않는 장치에서 사용자가 첨부 파일을 볼 수 없는 경우를 차단할 수도 있습니다.

그 단계는 다음과 같습니다.

1. [커넥트 원격 PowerShell Exchange Online 에 연결됩니다.](/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)
2. OWA 사서함 정책이 아직 없는 경우 [New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy) cmdlet을 사용하여 만들 수 있습니다.
3. 첨부 파일을 볼 수 있지만 다운로드할 수 없는 경우 다음 명령을 사용 합니다.

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. 첨부 파일을 차단하려는 경우 다음 명령을 사용 합니다.

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

5. Azure Portal에서 다음 설정을 사용하여 새 조건부 액세스 정책을 생성합니다.

   **배정** \> **사용자 및 그룹:** 포함 및 제외할 적절한 사용자 및 그룹을 선택합니다.

   **배정** \> **클라우드 앱 또는 작업** \> **클라우드 앱** \> **포함** \> **앱 선택:** 선택 **Office 365 Exchange Online**

   **액세스 컨트롤** \> **세션:** 앱 **적용 제한 사용 선택**

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a>iOS 및 Android 장치에서 모바일 장치를 Outlook

iOS 및 Android 장치의 사용자가 iOS 및 Android용 Outlook 사용하여 직장 또는 학교 콘텐츠에만 액세스할 수 있도록 허용하려면 이러한 잠재적 사용자를 대상으로 하는 조건부 액세스 정책이 필요합니다.

이 정책을 구성하는 단계는 Manage messaging collaboration access by using Outlook for iOS and Android 를 [참조하세요.](/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access)

## <a name="set-up-message-encryption"></a>메시지 암호화 설정

Azure Information Protection의 보호 기능을 활용하는 새로운 OME(Office 365 메시지 암호화) 기능을 사용하여 조직은 모든 디바이스의 모든 사용자와 보호된 전자 메일을 쉽게 공유할 수 있습니다. 사용자는 Microsoft 365.com, Gmail 및 기타 전자 메일 서비스를 사용하는 비 고객뿐만 Outlook 아니라 다른 Microsoft 365 메시지를 보내고 받을 수 있습니다.

자세한 내용은 [Set up new Office 365 메시지 암호화 capabilities을 참조하십시오.](../../compliance/set-up-new-message-encryption-capabilities.md)

## <a name="next-steps"></a>다음 단계

![4단계: 클라우드 Microsoft 365 정책.](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

조건부 액세스 정책 구성:

- [Microsoft Teams](teams-access-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
