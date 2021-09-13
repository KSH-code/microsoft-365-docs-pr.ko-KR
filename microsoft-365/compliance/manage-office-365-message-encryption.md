---
title: Office 365 메시지 암호화 관리
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 5/8/2019
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: OME(Office 365 메시지 암호화 설정)를 완료한 후 여러 가지 방법으로 배포를 사용자 지정하는 방법을 설명합니다.
ms.openlocfilehash: a2b3dde44ea541deb41eeb9d55d5ed745fa6c719
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59188067"
---
# <a name="manage-office-365-message-encryption"></a>Office 365 메시지 암호화 관리

OME(Office 365 메시지 암호화 설정한 후 여러 가지 방법으로 배포 구성을 사용자 지정할 수 있습니다. 예를 들어 일회용 암호를 사용하도록 설정할지, 암호화  단추를 표시할지 여부를 구성할 수 웹용 Outlook 있습니다. 이 문서의 작업에서는 방법을 설명합니다.

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>Google, Yahoo 및 Microsoft 계정 받는 사람이 이러한 계정을 사용하여 앱 포털에 로그인할 Office 365 메시지 암호화 관리

새 Office 365 메시지 암호화 기능을 설정하면 조직의 사용자가 조직 외부의 받는 사람에게 메시지를 보낼 수 있습니다. 받는 사람이 Google 계정, Yahoo 계정 또는 Microsoft 계정과 같은 소셜 *ID를* 사용하는 경우 받는 사람은 소셜 ID를 사용하여 OME 포털에 로그인할 수 있습니다. 원하는 경우 받는 사람이 공유 ID를 사용하여 OME 포털에 로그인하도록 허용하지 않을 수 있습니다.
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a>받는 사람이 소셜 ID를 사용하여 OME 포털에 로그인할 수 있는지 여부를 관리하기 위해
  
1. [커넥트 PowerShell을 Exchange Online 를 사용할 수 있습니다.](/powershell/exchange/connect-to-exchange-online-powershell)

2. 다음과 Set-OMEConfiguration SocialIdSignIn 매개 변수를 사용하여 Set-OMEConfiguration cmdlet을 실행합니다.

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   예를 들어 공유 ID를 사용하지 않도록 설정하는 경우:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   공유 ID를 사용하도록 설정하려면

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a>사이트 포털에 일회용 패스 코드 사용 Office 365 메시지 암호화 관리

OME로 암호화된 메시지의 받는 사람이 받는 사람이 Outlook 사용하는 계정에 관계없이 받는 사람은 메시지를 읽을 수 있는 제한된 시간의 웹 보기 링크를 받게 됩니다. 이 링크에는 일회용 패스 코드가 포함됩니다. 관리자는 받는 사람이 일회용 패스 코드를 사용하여 OME 포털에 로그인할 수 있는지 여부를 결정할 수 있습니다.
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a>OME에서 일회성 통과 코드를 생성하는지 여부를 관리하기 위해
  
1. 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Windows PowerShell 세션을 시작하고 조직에 Exchange Online. 지침을 확인하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

2. OTPEnabled Set-OMEConfiguration cmdlet을 실행합니다.

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -OTPEnabled <$true|$false>
   ```

   예를 들어 일회성 통과 코드를 사용하지 않도록 설정하는 경우:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   일회성 통과 코드를 사용하도록 설정하려면

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a>암호화 단추의 표시를 웹용 Outlook

관리자는 최종 사용자에게 이 단추를 표시할지 여부를 관리할 수 있습니다.
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a>암호화 단추가 암호화 단추에 나타나는지 여부를 웹용 Outlook
  
1. 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Windows PowerShell 세션을 시작하고 조직에 Exchange Online. 지침을 확인하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

2. -Set-IRMConfiguration -SimplifiedClientAccessEnabled 매개 변수를 사용하여 cmdlet을 실행합니다.

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   예를 들어 암호화 단추를 **사용하지 않도록 설정하는 경우:**

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   암호화 **단추를 사용하도록** 설정하려면

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>iOS 메일 앱 사용자에 대해 전자 메일 메시지의 서비스 쪽 암호 해독 사용

iOS 메일 앱은 365로 보호된 메시지의 암호를 해독할 Office 365 메시지 암호화. 관리자로서 Microsoft 365 iOS 메일 앱으로 배달된 메시지에 대해 서비스 쪽 암호 해독을 적용할 수 있습니다. 서비스 쪽 암호 해독을 사용하기로 선택하면 서비스에서 암호 해독된 메시지 복사본을 iOS 장치로 전송합니다. 클라이언트 장치는 암호 해독된 메시지 복사본을 저장합니다. 또한 이 메시지는 iOS 메일 앱이 사용자에게 클라이언트 쪽 사용 권한을 적용하지 않는 경우에도 사용 권한에 대한 정보를 보존합니다. 사용자가 원래 메시지를 복사하거나 인쇄할 수 있는 권한은 없는 경우에도 인쇄할 수 있습니다. 그러나 사용자가 메시지 전달과 같은 Microsoft 365 메일 서버가 필요한 작업을 완료하려고 하면 원래 사용자에게 사용권이 없는 경우 서버에서 해당 작업을 허용하지 않습니다. 그러나 최종 사용자는 iOS 메일 앱 내의 다른 계정에서 메시지를 전달하여 "전달 금지" 사용 제한을 사용할 수 있습니다. 메일의 서비스 쪽 암호 해독을 설정하는지 여부에 관계없이 암호화된 메일 및 권한으로 보호된 메일에 대한 첨부 파일은 iOS 메일 앱에서 볼 수 없습니다.
  
암호 해독된 메시지를 iOS 메일 앱 사용자에게 보낼 수 있도록 허용하지 않는 경우 사용자는 메시지를 볼 수 있는 권한을 받지 못했다는 메시지를 받게 됩니다. 기본적으로 전자 메일 메시지의 서비스 쪽 암호 해독은 사용하도록 설정되어 있지 않습니다.
  
자세한 내용은 클라이언트 환경의 보기를 참조하세요. iPhone 또는 [iPad.](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>iOS 메일 앱 사용자가 iOS 메일 앱으로 보호된 메시지를 볼 수 Office 365 메시지 암호화
  
1. 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Windows PowerShell 세션을 시작하고 조직에 Exchange Online. 지침을 확인하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

2. AllowRMSSupportForUnenlightenedApps 매개 Set-ActiveSyncOrganizations cmdlet을 실행합니다.

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   예를 들어 iOS 메일 앱과 같은 비인식 앱으로 메시지를 보내기 전에 메시지를 암호 해독하도록 서비스를 구성합니다.

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   또는 암호 해독된 메시지를 비인도 앱으로 보내지 못하도록 서비스를 구성합니다.

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> 개별 사서함 정책(OWA/ActiveSync)은 이러한 설정(예: 각 OWA 사서함 정책 또는 ActiveSync 사서함 정책 내에서 -IRMEnabled를 False로 설정한 경우) 이러한 구성이 적용되지 않습니다.

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>웹 브라우저 메일 클라이언트에 대해 전자 메일 첨부 파일 서비스 쪽 암호 해독 사용

일반적으로 메시지 암호화를 Office 365 첨부 파일이 자동으로 암호화됩니다. 관리자는 사용자가 웹 브라우저에서 다운로드하는 전자 메일 첨부 파일에 대해 서비스 쪽 암호 해독을 적용할 수 있습니다.
  
서비스 쪽 암호 해독을 사용하면 서비스에서 암호 해독된 파일의 복사본을 장치로 전송합니다. 메시지가 계속 암호화됩니다. 또한 전자 메일 첨부 파일은 브라우저가 사용자에게 클라이언트 쪽 사용 권한을 적용하지 않는 경우에도 사용 권한에 대한 정보를 보관합니다. 사용자는 원래 전자 메일 첨부 파일을 복사하거나 인쇄할 수 있습니다. 그러나 사용자가 첨부 파일 전달과 같은 Microsoft 365 메일 서버가 필요한 작업을 완료할 경우 원래 사용자에게 사용권이 없는 경우 서버에서 해당 작업을 허용하지 않습니다.
  
첨부 파일에 대한 서비스 쪽 암호 해독을 설정하는지 여부에 관계없이 사용자는 iOS 메일 앱에서 암호화되고 권한으로 보호된 메일에 대한 첨부 파일을 볼 수 없습니다.
  
암호 해독된 전자 메일 첨부 파일(기본값)을 허용하지 않는 경우 사용자는 첨부 파일을 볼 수 있는 권한을 받지 못했다는 메시지를 받게 됩니다.
  
전자 메일 및 전자 Microsoft 365 암호화를 구현하는 방법에 대한 자세한 내용은 Encrypt-Only 전자 메일에 대한 암호화 [전용 옵션을 참조하세요.](/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>웹 브라우저에서 다운로드 시 전자 메일 첨부 파일을 암호 해독할지 여부를 관리하려면
  
1. 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Windows PowerShell 세션을 시작하고 조직에 Exchange Online. 지침을 확인하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

2. DecryptAttachmentForEncryptOnly 매개 Set-IRMConfiguration 사용하여 Set-IRMConfiguration cmdlet을 실행합니다.

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   예를 들어 사용자가 웹 브라우저에서 전자 메일 첨부 파일을 다운로드할 때 암호를 해독하도록 서비스를 구성하려면 다음을 실행합니다.

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   암호화된 전자 메일 첨부 파일을 다운로드 시 그대로 두도록 서비스를 구성하려면

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a>모든 외부 받는 사람이 OME 포털을 사용하여 암호화된 메일을 읽는지 확인

사용자 지정 브랜드 템플릿을 사용하여 받는 사람이 OME 포털에서 암호화된 전자 메일을 읽게 하는 래퍼 메일을 강제로 수신하게 할 수 Outlook 웹용 Outlook. 받는 사람이 받는 메일을 사용하는 방법을 보다 잘 제어하려는 경우 이 작업을 할 수 있습니다. 예를 들어 외부 받는 사람이 웹 포털에서 전자 메일을 보는 경우 전자 메일의 만료 날짜를 설정하고 전자 메일을 해지할 수 있습니다. 이러한 기능은 OME 포털을 통해서만 지원됩니다. 메일 흐름 규칙을 만들 때 암호화 옵션과 전달 금지 옵션을 사용할 수 있습니다.

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a>사용자 지정 템플릿을 사용하여 모든 외부 받는 사람이 OME 포털 및 암호화된 전자 메일을 강제로 사용

1. 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Windows PowerShell 세션을 시작하고 조직에 Exchange Online. 지침을 확인하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

2. 다음 New-TransportRule 실행합니다.

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    여기서 각 부분이 나타내는 의미는 다음과 같습니다.

   - `mail flow rule name` 은 새 메일 흐름 규칙에 사용할 이름입니다.

   - `option name` 는 `Encrypt` 또는 `Do Not Forward` 입니다.

   - `template name` 은 사용자 지정 브랜징 템플릿에 지정한 이름(예: `OME Configuration` )입니다.

   "OME 구성" 템플릿을 사용하여 모든 외부 전자 메일을 암호화하고 다음 Encrypt-Only 적용합니다.

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   "OME 구성" 템플릿을 사용하여 모든 외부 전자 메일을 암호화하고 전달하지 않습니다 옵션을 적용하려면

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a>전자 메일 메시지 및 OME 포털의 모양 사용자 지정

조직에 맞게 OME를 사용자 지정하는 방법에 대한 자세한 내용은 암호화된 메시지에 조직의 브랜드 [추가를 참조하세요.](add-your-organization-brand-to-encrypted-messages.md)
  
## <a name="disable-the-new-capabilities-for-ome"></a>OME에 대한 새 기능을 사용하지 않도록 설정

이 기능이 필요하지는 않지만 필요한 경우 OME에 대한 새 기능을 사용할 수 없는 것은 매우 간단합니다. 먼저 새 OME 기능을 사용하는 메일 흐름 규칙을 제거해야 합니다. 메일 흐름 규칙을 제거하는 데 대한 자세한 내용은 메일 흐름 [규칙 관리를 참조하십시오.](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules) 그런 다음 PowerShell에서 Exchange Online 완료합니다.
  
### <a name="to-disable-the-new-capabilities-for-ome"></a>OME에 대한 새 기능을 사용하지 않도록 설정
  
1. 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Windows PowerShell 세션을 시작하고 조직에 Exchange Online. 지침을 확인하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

2. 사용자 지정에서  암호화 단추를 웹용 Outlook SimplifiedClientAccessEnabled 매개 변수를 사용하여 Set-IRMConfiguration cmdlet을 실행하여 사용하지 않도록 설정합니다. 그렇지 않은 경우 이 단계를 건너뜁.

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. AzureRMSLicensingEnabled 매개 변수를 false로 Set-IRMConfiguration cmdlet을 실행하여 OME에 대한 새 기능을 사용하지 않도록 설정합니다.

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
