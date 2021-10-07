---
title: 암호화된 메시지에 조직 브랜드 추가
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
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
- seo-marvel-jun2020
- admindeeplinkMAC
description: 전역 Office 365 조직의 브랜드를 암호화 포털의 콘텐츠와 함께 암호화된 전자 메일 메시지에 적용하는 & 방법을 알아보겠습니다.
ms.openlocfilehash: 063a46c94578cbd3cd01184d25086d5246da3fa8
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60195776"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a>비즈니스용 메시지 암호화 암호화 Microsoft 365 조직 브랜드 추가

회사 브랜드를 적용하여 조직의 전자 메일 메시지와 암호화 포털의 모양을 사용자 지정할 수 있습니다. 시작하기 전에 먼저 직장 또는 학교 계정에 전역 관리자 권한을 적용해야 합니다. 이러한 사용 권한이 있는 경우 Get-OMEConfiguration 및 Set-OMEConfiguration Windows PowerShell cmdlet을 사용하여 암호화된 전자 메일 메시지의 이러한 부분을 사용자 지정합니다.
  
- 소개 텍스트

- 고지서 텍스트

- 조직의 개인 정보 취급 방침 URL

- OME 포털의 텍스트

- 전자 메일 메시지 및 OME 포털에 나타나는 로고 또는 로고를 사용할지 여부

- 전자 메일 메시지 및 OME 포털의 배경색

언제든지 기본 모양과 느낌으로 되돌릴 수 있습니다.

더 많은 제어를 원할 경우 조직에서 Office 365 고급 메시지 암호화 암호화된 전자 메일에 대한 여러 템플릿을 만들 수 있습니다. 이러한 템플릿을 사용하여 최종 사용자 환경의 일부를 제어합니다. 예를 들어 받는 사람이 Google, Yahoo 및 Microsoft 계정을 사용하여 암호화 포털에 로그인할 수 있는지 여부를 지정합니다. 서식 파일을 사용하여 다음의 여러 사용 사례를 처리합니다.

- 재무, 영업 등의 개별 부서

- 다른 제품

- 다양한 지리적 지역 또는 국가

- 전자 메일이 해지될 수 있도록 허용할지 여부

- 외부 받는 사람에게 보낸 전자 메일이 지정된 일 수 후에 만료될지 여부를 지정합니다.

템플릿을 만든 후 메일 흐름 규칙을 사용하여 암호화된 전자 메일에 Exchange 있습니다. 이 Office 365 고급 메시지 암호화 경우 이러한 템플릿을 사용하여 브랜드한 모든 전자 메일을 해지할 수 있습니다.

## <a name="work-with-ome-branding-templates"></a>OME 브랜랜드 템플릿 사용

브랜드 템플릿 내에서 여러 기능을 수정할 수 있습니다. 기본 템플릿은 수정할 수 있지만 제거할 수 없습니다. 고급 메시지 암호화가 있는 경우 사용자 지정 서식 파일을 만들고 수정하고 제거할 수도 있습니다. 브랜 Windows PowerShell 한 번씩 작업할 수 있습니다.

- [Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) - 만든 기본 브랜징 템플릿 또는 사용자 지정 브랜징 템플릿을 수정합니다.
- [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) - 새 브랜드 템플릿인 고급 메시지 암호화만 만듭니다.
- [Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) - 사용자 지정 브랜징 템플릿인 고급 메시지 암호화만 제거합니다. 기본 브랜드 템플릿은 삭제할 수 없습니다.
  
## <a name="modify-an-ome-branding-template"></a>OME 브랜랜드 템플릿 수정

이 Windows PowerShell 사용하여 한 번의 브랜드 템플릿을 수정할 수 있습니다. 고급 메시지 암호화가 있는 경우 사용자 지정 서식 파일을 만들고 수정하고 제거할 수도 있습니다.

1. 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Windows PowerShell 세션을 시작하고 조직에 Exchange Online. 지침을 확인하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

2. [Set-OMEConfiguration에](/powershell/module/exchange/Set-OMEConfiguration) 설명된 Set-OMEConfiguration cmdlet을 사용하거나 다음 그래픽 및 표를 사용하여 지침을 참조하세요.

![사용자 지정 가능한 전자 메일 파트.](../media/ome-template-breakout.png)

|**암호화 환경에서 사용자 지정하려는 기능**|**다음 명령 사용**|
|:-----|:-----|
|배경색|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> **예제:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> 배경색에 대한 자세한 내용은 이 문서 부분의 [배경색](#background-color-reference) 섹션을 참조하세요.|
|로고|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> **예제:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> 지원되는 파일 형식: .png, .jpg, .bmp 또는 .tiff  <br/> 로고 파일의 최적 크기: 40KB 미만  <br/> 로고 이미지의 최적 크기: 170x70 픽셀 이미지가 이러한 크기를 초과하면 서비스에서 포털에 표시하기 위해 로고 크기를 변경합니다. 서비스는 그래픽 파일 자체를 수정하지 않습니다. 최상의 결과를 얻기 위해 최적의 크기를 사용 합니다.|
|보낸 사람 이름 및 전자 메일 주소 옆의 텍스트|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> **예:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|"메시지 읽기" 단추에 나타나는 텍스트|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> **예:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|"메시지 읽기" 단추 아래에 나타나는 텍스트|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> **예제:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|개인 정보 취급 방침 링크의 URL|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> **예:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|암호화된 메시지를 포함하는 전자 메일의 고지 사항 설명문|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **예:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|암호화된 메일 보기 포털 위쪽에 표시되는 텍스트|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **예:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|이 사용자 지정 서식 파일에서 일회용 암호로 인증을 사용하도록 설정하거나 사용하지 않도록 설정하려면|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> **예제:** <br/>이 사용자 지정 서식 파일에서 일회용 암호를 사용하도록 설정하려면 <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> 이 사용자 지정 서식 파일에서 일회용 암호를 사용하지 않도록 설정 <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|이 사용자 지정 서식 파일에서 Microsoft, Google 또는 Yahoo ID로 인증을 사용하도록 설정하거나 사용하지 않도록 설정하려면|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> **예제:** <br/>이 사용자 지정 서식 파일에서 공유 ID를 사용하도록 설정하려면 <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> 이 사용자 지정 서식 파일에서 공유 ID를 사용하지 않도록 설정 <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a>OME 브랜랜드 템플릿 만들기(고급 메시지 암호화)

이 Office 365 고급 메시지 암호화 [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet을 사용하여 조직에 대한 사용자 지정 브랜징 템플릿을 만들 수 있습니다. 템플릿을 만든 후 Modify an OME branding template 에 설명된 Set-OMEConfiguration cmdlet을 사용하여 [템플릿을 수정합니다.](#modify-an-ome-branding-template) 여러 서식 파일을 만들 수 있습니다.

새 사용자 지정 브랜징 템플릿을 만들 수 있습니다.

1. 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Windows PowerShell 세션을 시작하고 조직에 Exchange Online. 지침을 확인하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

2. [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet을 사용하여 새 템플릿을 만들 수 있습니다.

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   예를 들면 다음과 같습니다.

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a>기본 브랜드 템플릿을 원래 값으로 반환

브랜드 사용자 지정 등을 포함하여 기본 템플릿에서 모든 수정 내용을 제거하려면 다음 단계를 완료합니다.
  
1. 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Windows PowerShell 세션을 시작하고 조직에 Exchange Online. 지침을 확인하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

2. **Set-OMEConfiguration 에** 설명된 바와 같이 [Set-OMEConfiguration cmdlet을 사용 합니다.](/powershell/module/exchange/Set-OMEConfiguration) DisclaimerText, EmailText 및 PortalText 값에서 조직의 브랜드 사용자 지정을 제거하려면 값을 빈 문자열인 로 `""` 설정하십시오. 로고와 같은 모든 이미지 값에 대해 값을 로  `"$null"` 설정합니다.

   다음 표에는 암호화 사용자 지정 옵션 기본값이 설명되어 있습니다.

   |암호화 환경의 이 기능을 기본 텍스트 및 이미지로 되돌리려면|다음 명령 사용|
   |:-----|:-----|
   |암호화된 전자 메일 메시지와 함께 제공된 기본 텍스트입니다.  암호화된 메시지를 보기 위한 지침 위에 표시되는 기본 텍스트|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> **예제:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |암호화된 메시지를 포함하는 전자 메일의 고지 사항 설명문|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> **예:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |암호화된 메일 보기 포털 위쪽에 표시되는 텍스트|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> **기본값으로 되돌리기 예제:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |로고|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> **기본값으로 되돌리기 예제:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |배경색|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> **기본값으로 되돌리기 예제:** <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a>사용자 지정 브랜징 템플릿 제거(고급 메시지 암호화)

만든 브랜디드 템플릿만 제거하거나 삭제할 수 있습니다. 기본 브랜드 템플릿은 제거할 수 없습니다.

사용자 지정 브랜징 서식 파일을 제거하려면
  
1. 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Windows PowerShell 세션을 시작하고 조직에 Exchange Online. 지침을 확인하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

2. **Remove-OMEConfiguration** cmdlet은 다음과 같이 사용할 수 있습니다.

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   예를 들면 다음과 같습니다.

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   자세한 내용은 [Remove-OMEConfiguration을 참조하십시오.](/powershell/module/exchange/remove-omeconfiguration)

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a>암호화된 Exchange 사용자 지정 브랜더를 적용하는 메일 흐름 규칙 만들기

> [!IMPORTANT]
> 메일을 검색하고 수정하는 타사 응용 프로그램을 통해 OME 브랜드가 올바르게 적용되지 않을 수 있습니다.

기본 템플릿을 수정하거나 새 브랜더링 템플릿을 만든 후 특정 조건에 Exchange 사용자 지정 브랜더링을 적용하는 메일 흐름 규칙을 만들 수 있습니다. 이러한 규칙은 다음과 같은 시나리오에서 사용자 지정 브랜드를 적용합니다.

- 전자 메일이 이전의 Outlook 또는 웹용 Outlook 사용자가 수동으로 암호화한 Outlook Web App

- 전자 메일이 Exchange 메일 흐름 규칙 또는 데이터 손실 방지 정책에 의해 자동으로 암호화된 경우

암호화를 적용하는 Exchange 메일 흐름 규칙을 만드는 방법에 대한 자세한 내용은 [Define mail flow rules to encrypt email messages in Office 365.](define-mail-flow-rules-to-encrypt-email.md)

1. 웹 브라우저에서 전역 관리자 권한이 부여된 직장 또는 학교 계정을 사용하여 에 [Office 365.](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)

2. 관리 **타일을** 선택하세요.

3. In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>, choose **Admin centers** \> **Exchange.**

4. EAC에서 메일 흐름 **규칙으로** \> **이동하고** 새 새 **아이콘을** ![ 선택합니다.](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \>**새 규칙을 만드시다.** EAC 사용에 대한 자세한 내용은 에서 Exchange [관리 센터를 Exchange Online.](/exchange/exchange-admin-center)

5. **이름에** 규칙의 이름(예: 영업 부서의 브랜드)을 입력합니다.

6. 다음의 **경우** 이 규칙  적용에서 보낸 사람이 조직 내부에 있는 조건 및 사용 가능한 조건 목록에서 원하는 기타 조건을 선택합니다. 예를 들어 다음에 특정 브랜드 템플릿을 적용할 수 있습니다.

   - 재무 부서의 구성원이 보낸 모든 암호화된 전자 메일
   - "외부" 또는 "파트너"와 같은 특정 키워드를 사용하여 전송된 암호화된 전자 메일
   - 특정 도메인으로 전송된 암호화된 전자 메일

7. 다음 **작업에서** 메시지 보안 수정 **OME** 메시지에 사용자 지정 \> **브랜드 적용 을 선택합니다.** 그런 다음 드롭다운에서 브랜드 템플릿을 선택합니다.

8. (선택 사항) 암호화 및 사용자 지정 브랜드를 적용하도록 메일 흐름 규칙을 구성할 수 있습니다. 다음 **작업에서** **메시지** 보안 수정을 선택한 다음 메시지 보안 및 권한 **Office 365 메시지 암호화 적용을 선택합니다.** 목록에서 RMS 템플릿을 선택하고 **저장을** 선택한 다음 확인 을 **선택합니다.**
  
   템플릿 목록에는 기본 서식 파일 및 옵션과 만든 모든 사용자 지정 템플릿이 포함됩니다. 목록이 비어 있는 경우 새 기능을 Office 365 메시지 암호화 설정해야 합니다. 자세한 내용은 [Set up new Office 365 메시지 암호화 capabilities을 참조하십시오.](set-up-new-message-encryption-capabilities.md) 기본 템플릿에 대한 자세한 내용은 Azure Information Protection용 템플릿 구성 및 [관리를 참조하세요.](/information-protection/deploy-use/configure-policy-templates) 전달 금지 **옵션에** 대한 자세한 내용은 전자 메일에 [대해 전달 금지 옵션을 참조하세요.](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails) 암호화 전용 **옵션에** 대한 자세한 내용은 전자 메일에 대한 [암호화 전용 옵션을 참조하세요.](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)

   다른 **작업을 지정하려는** 경우 작업 추가를 선택 합니다.

## <a name="background-color-reference"></a>배경색 참조

배경색에 사용할 수 있는 색 이름은 제한됩니다. 색 이름 대신 16진수 코드 값(16진수)을 사용할 #RRGGBB. 색 이름에 해당하는 16진수 코드 값을 사용할 수도, 사용자 지정 16진수 코드 값을 사용할 수도 있습니다. 16진수 코드 값을 인용 부호(예: )로 `"#f0f8ff"` 묶습니다.

사용 가능한 배경색 이름과 해당 16진수 코드 값은 다음 표에 설명되어 있습니다.

|**색 이름**|**색 코드**|
|---|---|
|`aliceblue`|#f0f8ff|
|`antiquewhite`|#faebd7|
|`aqua`|#00ffff|
|`aquamarine`|#7fffd4|
|`azure`|#f0ffff|
|`beige`|#f5f5dc|
|`bisque`|#ffe4c4|
|`black`|#000000|
|`blanchedalmond`|#ffebcd|
|`blue`|#0000ff|
|`blueviolet`|#8a2be2|
|`brown`|#a52a2a|
|`burlywood`|#deb887|
|`cadetblue`|#5f9ea0|
|`chartreuse`|#7fff00|
|`chocolate`|#d2691e|
|`coral`|#ff7f50|
|`cornflowerblue`|#6495ed|
|`cornsilk`|#fff8dc|
|`crimson`|#dc143c|
|`cyan`|#00ffff|
|`darkblue`|#00008b|
|`darkcyan`|#008b8b|
|`darkgoldenrod`|#b8860b|
|`darkgray`|#a9a9a9|
|`darkgreen`|#006400|
|`darkkhaki`|#bdb76b|
|`darkmagenta`|#8b008b|
|`darkolivegreen`|#556b2f|
|`darkorange`|#ff8c00|
|`darkorchid`|#9932cc|
|`darkred`|#8b0000|
|`darksalmon`|#e9967a|
|`darkseagreen`|#8fbc8f|
|`darkslateblue`|#483d8b|
|`darkslategray`|#2f4f4f|
|`darkturquoise`|#00ced1|
|`darkviolet`|#9400d3|
|`deeppink`|#ff1493|
|`deepskyblue`|#00bfff|
|`dimgray`|#696969|
|`dodgerblue`|#1e90ff|
|`firebrick`|#b22222|
|`floralwhite`|#fffaf0|
|`forestgreen`|#228b22|
|`fuchsia`|#ff00ff|
|`gainsboro`|#dcdcdc|
|`ghostwhite`|#f8f8ff|
|`gold`|#ffd700|
|`goldenrod`|#daa520|
|`gray`|#808080|
|`green`|#008000|
|`greenyellow`|#adff2f|
|`honeydew`|#f0fff0|
|`hotpink`|#ff69b4|
|`indianred`|#cd5c5c|
|`indigo`|#4b0082|
|`ivory`|#fffff0|
|`khaki`|#f0e68c|
|`lavender`|#e6e6fa|
|`lavenderblush`|#fff0f5|
|`lawngreen`|#7cfc00|
|`lemonchiffon`|#fffacd|
|`lightblue`|#add8e6|
|`lightcoral`|#f08080|
|`lightcyan`|#e0ffff|
|`lightgoldenrodyellow`|#fafad2|
|`lightgray`|#d3d3d3|
|`lightgrey`|#d3d3d3|
|`lightgreen`|#90ee90|
|`lightpink`|#ffb6c1|
|`lightsalmon`|#ffa07a|
|`lightseagreen`|#20b2aa|
|`lightskyblue`|#87cefa|
|`lightslategray`|#778899|
|`lightsteelblue`|#b0c4de|
|`lightyellow`|#ffffe0|
|`lime`|#00ff00|
|`limegreen`|#32cd32|
|`linen`|#faf0e6|
|`magenta`|#ff00ff|
|`maroon`|#800000|
|`mediumaquamarine`|#66cdaa|
|`mediumblue`|#0000cd|
|`mediumorchid`|#ba55d3|
|`mediumpurple`|#9370db|
|`mediumseagreen`|#3cb371|
|`mediumslateblue`|#7b68ee|
|`mediumspringgreen`|#00fa9a|
|`mediumturquoise`|#48d1cc|
|`mediumvioletred`|#c71585|
|`midnightblue`|#191970|
|`mintcream`|#f5fffa|
|`mistyrose`|#ffe4e1|
|`moccasin`|#ffe4b5|
|`navajowhite`|#ffdead|
|`navy`|#000080|
|`oldlace`|#fdf5e6|
|`olive`|#808000|
|`olivedrab`|#6b8e23|
|`orange`|#ffa500|
|`orangered`|#ff4500|
|`orchid`|#da70d6|
|`palegoldenrod`|#eee8aa|
|`palegreen`|#98fb98|
|`paleturquoise`|#afeeee|
|`palevioletred`|#db7093|
|`papayawhip`|#ffefd5|
|`peachpuff`|#ffdab9|
|`peru`|#cd853f|
|`pink`|#ffc0cb|
|`plum`|#dda0dd|
|`powderblue`|#b0e0e6|
|`purple`|#800080|
|`red`|#ff0000|
|`rosybrown`|#bc8f8f|
|`royalblue`|#4169e1|
|`saddlebrown`|#8b4513|
|`salmon`|#fa8072|
|`sandybrown`|#f4a460|
|`seagreen`|#00ff00|
|`seashell`|#fff5ee|
|`sienna`|#a0522d|
|`silver`|#c0c0c0|
|`skyblue`|#87ceeb|
|`slateblue`|#6a5acd|
|`slategray`|#708090|
|`snow`|#fffafa|
|`springgreen`|#00ff7f|
|`steelblue`|#4682b4|
|`tan`|#d2b48c|
|`teal`|#008080|
|`thistle`|#d8bfd8|
|`tomato`|#ff6347|
|`turquoise`|#40e0d0|
|`violet`|#ee82ee|
|`wheat`|#f5deb3|
|`white`|#ffffff|
|`whitesmoke`|#f5f5f5|
|`yellow`|#ffff00|
|`yellowgreen`|#9acd32|
