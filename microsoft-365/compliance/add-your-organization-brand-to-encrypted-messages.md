---
title: 암호화 된 메시지에 조직 브랜드 추가
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/1/2020
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 조직의 암호화 된 전자 메일 메시지와 암호화 포털의 콘텐츠에 조직의 브랜딩을 적용 합니다.
ms.openlocfilehash: fc2767c0b7ad67a53e081d60d18ac583b2b4c686
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034394"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a>암호화된 메시지에 조직의 브랜드 추가

Exchange Online 또는 Exchange Online Protection 관리자는 회사 브랜딩을 적용 하 여 조직의 Microsoft 365에서 비즈니스 메시지 암호화 전자 메일 메시지와 암호화 포털의 내용을 사용자 지정할 수 있습니다. Set-omeconfiguration 및 Set-omeconfiguration Windows PowerShell cmdlet을 사용 하 여 암호화 된 전자 메일 메시지의 받는 사람에 대 한 다음의 보기 환경을 사용자 지정할 수 있습니다.
  
- 암호화된 메시지를 포함하는 전자 메일의 소개 텍스트

- 암호화된 메시지를 포함하는 전자 메일의 고지 사항 텍스트

- 조직에 대 한 개인 정보 취급 방침의 URL

- OME 포털에 표시 되는 텍스트

- 전자 메일 메시지 및 OME 포털에 표시 되는 로고 또는 로고를 사용할지 여부

- 전자 메일 메시지 및 OME 포털의 배경색

언제든지 기본 모양과 느낌으로 되돌릴 수 있습니다.

더 많은 제어권을 원한다 면 Office 365 Advanced Message Encryption을 사용 하 고 조직에서 보내는 암호화 된 전자 메일용으로 여러 템플릿을 만들 수 있습니다. 이러한 서식 파일을 사용 하면 전자 메일 메시지의 모양과 느낌 뿐만 아니라 최종 사용자 환경의 일부를 제어할 수 있습니다. 예를 들어이 서식 파일을 적용 한 메일의 받는 사람 및 Google, Yahoo 및 Microsoft 계정을 사용 하는 사용자가 이러한 계정을 사용 하 여 Office 365 메시지 암호화 포털에 로그인 할 수 있는지 여부를 지정할 수 있습니다. 서식 파일을 사용 하 여 다음과 같은 여러 사용 사례를 충족할 수 있습니다.

- 재무, 판매 등의 각 부서에 대 한 서식 파일입니다.

- 다양 한 제품의 서식 파일

- 다른 지역 또는 국가에 대 한 서식 파일

- 전자 메일을 해지할 수 있도록 할지 여부

- 지정 된 기간 (일) 후에 외부 받는 사람에 게 전송 되는 전자 메일의 만료 여부

템플릿을 만든 후에는 Exchange 메일 흐름 규칙을 사용 하 여이를 암호화 된 전자 메일에 적용할 수 있습니다. Office 365 고급 메시지 암호화가 있는 경우 이러한 서식 파일을 사용 하 여 브랜드는 모든 전자 메일을 해지할 수 있습니다.

## <a name="work-with-ome-branding-templates"></a>OME 브랜딩 서식 파일 사용

브랜딩 서식 파일 내에서 여러 기능을 수정할 수 있습니다. 기본 서식 파일을 수정할 수는 있지만 제거 하지는 못합니다. 고급 메시지 암호화가 있는 경우 사용자 지정 서식 파일을 만들고, 수정 하 고, 제거할 수도 있습니다. Windows PowerShell을 사용 하 여 한 번에 하나의 브랜딩 서식 파일로 작업할 수 있습니다. 이러한 cmdlet을 사용 하려면 조직에서 전역 관리자 권한이 있는 회사 또는 학교 계정이 필요 합니다.

- [Set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-omeconfiguration) -기본 브랜딩 템플릿이나 만든 사용자 지정 브랜딩 서식 파일을 수정 합니다.
- [Set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/new-omeconfiguration) -새 브랜딩 서식 파일을 만들고 고급 메시지 암호화만 사용 합니다.
- [Set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/remove-omeconfiguration) -사용자 지정 브랜딩 서식 파일을 제거 하 고 고급 메시지 암호화만 허용 합니다. 기본 브랜딩 서식 파일은 삭제할 수 없습니다.
  
## <a name="modify-an-ome-branding-template"></a>OME 브랜딩 서식 파일 수정

Windows PowerShell을 사용 하 여 한 번에 하나의 브랜딩 서식 파일을 수정 합니다. 고급 메시지 암호화가 있는 경우 사용자 지정 서식 파일을 만들고, 수정 하 고, 제거할 수도 있습니다.

1. 조직에서 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용 하 여 Windows PowerShell 세션을 시작 하 고 Exchange Online에 연결 합니다. 지침을 확인하려면 [Exchange Online PowerShell에 연결](https://aka.ms/exopowershell)을 참조하세요.

2. Set-omeconfiguration에 설명 된 대로 Set-omeconfiguration cmdlet을 사용 하 여 서식 파일을 수정 하거나 다음과 같은 그래픽 및 표를 사용 하 여 지침을 [제공](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration) 합니다.

![사용자 지정 가능한 전자 메일 부분](../media/ome-template-breakout.png)

|**암호화 환경에서 사용자 지정하려는 기능**|**사용할 명령**|
|:-----|:-----|
|배경색|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor "<Hexadecimal color code>"` <br/> **예제:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"`|
|회사|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **예제:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> 지원되는 파일 형식: .png, .jpg, .bmp 또는 .tiff  <br/> 로고 파일의 최적 크기: 40KB 미만  <br/> 로고 이미지의 최적 크기: 170x70 픽셀 이미지가 이러한 차원을 초과 하는 경우에는 서비스에서 포털에 표시 하기 위해 로고 크기를 조정 합니다. 서비스에서 그래픽 파일 자체를 수정 하지 않습니다. 최상의 결과를 얻으려면 최적의 크기를 사용 합니다.|
|보낸 사람 이름 및 전자 메일 주소 옆에 있는 텍스트|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -IntroductionText "<String up to 1024 characters>"` <br/> **예제:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|"메시지 읽기" 단추에 나타나는 텍스트|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -ReadButtonText "<String up to 1024 characters>"` <br/> **예제:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|"메시지 읽기" 단추 아래에 표시 되는 텍스트|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<String up to 1024 characters>"` <br/> **예제:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|개인 정보 취급 방침 링크의 URL입니다.|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PrivacyStatementURL "<URL>"` <br/> **예제:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|암호화된 메시지를 포함하는 전자 메일의 고지 사항 설명문|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **예제:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|암호화된 메일 보기 포털 위쪽에 표시되는 텍스트|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **예제:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|인증을 사용 하거나 사용 하지 않도록 설정 하려면이 사용자 지정 서식 파일의 1 회 통과 코드|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -OTPEnabled <$true|$false>` <br/> **예제:** <br/>이 사용자 지정 서식 파일에 일회용 passcodes을 사용 하도록 설정 하려면 <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> 이 사용자 지정 서식 파일에 대해 일회용 passcodes을 사용 하지 않도록 설정 하려면 <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|이 사용자 지정 서식 파일에 대해 Microsoft, Google 또는 Yahoo id를 사용 하 여 인증을 사용 하거나 사용 하지 않도록 설정 하려면|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -SocialIdSignIn <$true|$false>` <br/> **예제:** <br/>이 사용자 지정 서식 파일에 대해 공유 Id를 사용 하도록 설정 하려면 <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> 이 사용자 지정 서식 파일에 대해 공유 Id를 사용 하지 않도록 설정 하려면 <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a>OME 브랜딩 서식 파일 만들기 (고급 메시지 암호화)

Office 365 고급 메시지 암호화가 있는 경우 [set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/new-omeconfiguration) cmdlet을 사용 하 여 조직에 대 한 사용자 지정 브랜딩 서식 파일을 만들 수 있습니다. 템플릿을 만든 후에 [는 OME 브랜딩 서식 파일 수정](#modify-an-ome-branding-template)에 설명 된 대로 set-omeconfiguration cmdlet을 사용 하 여 서식 파일을 수정 합니다. 템플릿을 여러 개 만들 수 있습니다.

새 사용자 지정 브랜딩 템플릿을 만들려면 다음을 수행 합니다.

1. 조직에서 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용 하 여 Windows PowerShell 세션을 시작 하 고 Exchange Online에 연결 합니다. 지침을 확인하려면 [Exchange Online PowerShell에 연결](https://aka.ms/exopowershell)을 참조하세요.

2. 새 서식 파일을 만들려면 [set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/new-omeconfiguration) cmdlet을 사용 합니다.

   ```powershell
   New-OMEConfiguration -Identity <OMEConfigurationIdParameter>
   ```

   For example,

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a>기본 브랜딩 서식 파일을 원래 값으로 되돌리기

브랜드 사용자 지정 등을 포함 하 여 기본 서식 파일에서 수정 내용을 모두 제거 하려면 다음 단계를 완료 합니다.
  
1. 조직에서 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용 하 여 Windows PowerShell 세션을 시작 하 고 Exchange Online에 연결 합니다. 지침을 확인하려면 [Exchange Online PowerShell에 연결](https://aka.ms/exopowershell)을 참조하세요.

2. [-Set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration)에 설명 된 대로 **set-omeconfiguration** cmdlet을 사용 합니다. DisclaimerText, EmailText 및 PortalText 값에서 조직의 브랜드 사용자 지정을 제거 하려면이 값을 빈 문자열 ( `""`)로 설정 합니다. 로고 등의 모든 이미지 값에 대해 값을로 `"$null"`설정 합니다.

   다음 표에서는 암호화 사용자 지정 옵션 기본값에 대해 설명 합니다.

   **암호화 환경의 이 기능을 기본 텍스트 및 이미지로 되돌리려면**|**사용할 명령**|
   |:-----|:-----|
   |암호화된 전자 메일 메시지에 포함되는 기본 텍스트  <br/> 암호화된 메시지를 보기 위한 지침 위에 표시되는 기본 텍스트|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **예제:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |암호화된 메시지를 포함하는 전자 메일의 고지 사항 설명문|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **예제:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |암호화된 메일 보기 포털 위쪽에 표시되는 텍스트|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **다음은 기본값으로 되돌리는 예제입니다.** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |회사|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **다음은 기본값으로 되돌리는 예제입니다.** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |배경색|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor <"$null">` <br/> **다음은 기본값으로 되돌리는 예제입니다.** <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|
   |

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a>사용자 지정 브랜딩 서식 파일 제거 (고급 메시지 암호화)

지정한 브랜딩 템플릿만 제거 하거나 삭제할 수 있습니다. 기본 브랜딩 서식 파일은 제거할 수 없습니다.

사용자 지정 브랜딩 서식 파일을 제거 하려면:
  
1. 조직에서 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용 하 여 Windows PowerShell 세션을 시작 하 고 Exchange Online에 연결 합니다. 지침을 확인하려면 [Exchange Online PowerShell에 연결](https://aka.ms/exopowershell)을 참조하세요.

2. 다음과 같이 **set-omeconfiguration** cmdlet을 사용 합니다.

   ```powershell
   Remove-OMEConfiguration -Identity "<OMEConfigurationIdParameter>
   ```

   For example,

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   자세한 내용은 [Remove-set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/remove-omeconfiguration)를 참조 하세요.

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a>암호화 된 전자 메일에 사용자 지정 브랜딩을 적용 하는 Exchange 메일 흐름 규칙 만들기

기본 서식 파일을 수정 하거나 새 브랜딩 서식 파일을 만든 후에는 Exchange 메일 흐름 규칙을 만들어 특정 조건에 따라 사용자 지정 브랜딩을 적용할 수 있습니다. 이러한 규칙은 다음과 같은 시나리오에서 사용자 지정 브랜딩을 적용 합니다.

- 최종 사용자가 웹에서 outlook 또는 outlook (이전의 Outlook Web App) 클라이언트를 사용 하 여 전자 메일을 수동으로 암호화 한 경우

- 전자 메일이 Exchange 메일 흐름 규칙 또는 데이터 손실 방지 정책에 의해 자동으로 암호화 된 경우

암호화를 적용 하는 Exchange 메일 흐름 규칙을 만드는 방법에 대 한 자세한 내용은 [Office 365에서 전자 메일 메시지를 암호화 하기 위한 메일 흐름 규칙 정의](define-mail-flow-rules-to-encrypt-email.md)를 참조 하세요.

1. 웹 브라우저에서 전역 관리자 권한이 부여 된 회사 또는 학교 계정을 사용 하 여 [Office 365에 로그인](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)합니다.

2. **관리** 타일을 선택 합니다.

3. Microsoft 365 관리 센터에서 **관리 센터** \> **Exchange**를 선택 합니다.

4. EAC에서 **메일 흐름** \> **규칙** 으로 이동 하 **고 새로** ![만들기 아이콘](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> 을 선택 하 여 **새 규칙을 만듭니다**. EAC를 사용 하는 방법에 대 한 자세한 내용은 exchange [Online의 exchange 관리 센터](https://docs.microsoft.com/exchange/exchange-admin-center)를 참조 하세요.

5. **이름**에 영업 부서에 대 한 브랜딩을 같은 규칙의 이름을 입력 합니다.

6. **다음의 경우이 규칙 적용**에서, **보낸 사람이 조직 내부에 있는** 조건과 사용 가능한 조건 목록에서 원하는 조건을 선택 합니다. 예를 들어 다음과 같은 경우에 특정 브랜딩 서식 파일을 적용할 수 있습니다.

   - 재무 부서의 구성원이 보낸 모든 암호화 된 전자 메일
   - "External" 또는 "Partner" 등의 특정 키워드를 사용 하 여 보낸 암호화 된 전자 메일
   - 특정 도메인으로 전송 되는 암호화 된 전자 메일

7. **다음 작업을 수행**하 고 **메시지 보안** > 수정**사용자 지정 브랜딩을 OME 메시지에 적용**을 선택 합니다. 다음으로, 드롭다운 폴더에서 만들거나 수정한 브랜딩 서식 파일을 선택 합니다.

8. 반드시 메일 흐름 규칙을 통해 사용자 지정 브랜딩 외에도 암호화를 적용 하려면 **다음 작업을 수행**하 고 **메시지 보안 수정을**선택한 다음 **Office 365 메시지 암호화 및 권한 보호 적용**을 선택 합니다. 목록에서 RMS 템플릿을 선택 하 고 **저장**을 선택한 다음 **확인**을 선택 합니다.
  
   서식 파일 목록에는 모든 기본 서식 파일 및 옵션 뿐 아니라 Office 365에서 사용 하기 위해 만든 사용자 지정 서식 파일도 포함 됩니다. 목록이 비어 있으면 [새 office 365 메시지 암호화 기능 설정](set-up-new-message-encryption-capabilities.md)에 설명 된 대로 Office 365 메시지 암호화를 새로운 기능으로 설정 했는지 확인 합니다. 기본 서식 파일에 대 한 자세한 내용은 [Azure Information Protection의 템플릿 구성 및 관리](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)를 참조 하십시오. **전달 하지** 않음 옵션에 대 한 자세한 내용은 [전자 메일에 대 한 전달 옵션 안 함](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)을 참조 하십시오. **암호화 전용** 옵션에 대 한 자세한 내용은 [전자 메일에 대 한 암호화 옵션](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)을 참조 하십시오.

   다른 작업을 지정 하려면 **작업 추가** 를 선택 합니다.
