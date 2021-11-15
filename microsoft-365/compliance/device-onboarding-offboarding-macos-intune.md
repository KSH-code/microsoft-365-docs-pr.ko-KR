---
title: Microsoft 365(미리 보기)를 사용하여 macOS Microsoft Intune 온보드 및 오프보드
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Microsoft 365(미리 보기)를 사용하여 macOS 장치를 Microsoft Intune 방법에 대해 자세히 알아보십시오.
ms.openlocfilehash: 82aa3909ac7829f07a797673300cc0061bb4feef
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2021
ms.locfileid: "60962714"
---
# <a name="onboard-and-offboard-macos-devices-into-microsoft-365-compliance-solutions-using-intune-preview"></a>Intune을 사용하여 macOS 장치를 Microsoft 365 규정 준수 솔루션에 온보딩 및 오프보딩(미리 보기)

Intune을 사용하여 macOS 장치를 준수 솔루션에 Microsoft 365 수 있습니다.

> [!IMPORTANT]
> MacOS 장치에  끝점용 Microsoft Defender(MDE)가 배포되지 않은 경우 이 절차를 사용합니다.

**적용 대상:**

- [Microsoft 365 엔드포인트 DLP(데이터 손실 방지)](./endpoint-dlp-learn-about.md)
- [내부자 위험 관리](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)

## <a name="before-you-begin"></a>시작하기 전에

- macOS 장치가 [Intune에](/mem/intune/fundamentals/deployment-guide-platform-macos) 등록되어 있으며 앱 앱에 [회사 포털 합니다.](/mem/intune/user-help/enroll-your-device-in-intune-macos-cp) 
- 보안 센터 에 액세스할 [수 Microsoft Endpoint Manager 합니다.](https://endpoint.microsoft.com/#home)
- 이는 macOS 버전 카탈로니아 10.15 이상을 지원합니다.
- 구성 업데이트를 할당할 사용자 그룹을 생성합니다.
- macOS 장치에 v95+ Edge 브라우저 설치 


## <a name="onboard-macos-devices-into-microsoft-365-compliance-solutions-using-microsoft-intune"></a>macOS 장치를 Microsoft 365 규정 준수 솔루션에 온보드 Microsoft Intune

규정 준수 솔루션에 macOS 장치를 온보드하는 것은 6단계 프로세스입니다.

1. [시스템 구성 프로필 만들기](#create-system-configuration-profiles)
1. [장치 온보더링 패키지를 얻습니다.](#get-the-device-onboarding-package)
1. [온보더링 패키지 배포](#deploy-the-onboarding-package)
1. [시스템 확장 사용](#enable-system-extension)
1. [설치 패키지를 얻습니다.](#get-the-installation-package)
1. [설치 패키지 배포](#deploy-the-microsoft-dlp-installation-package)

### <a name="create-system-configuration-profiles"></a>시스템 구성 프로필 만들기

1. 이 절차를 수행하려면 이러한 파일이 필요합니다.

|필요한 파일 |source |
|---------|---------|
|온보더링 패키지    |준수 포털 **온보더링** 패키지에서 다운로드한 후 파일 *이름* DeviceComplianceOnboarding.xml |
|접근성 |[accessibility.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/accessibility.mobileconfig)|
전체 디스크 액세스     |[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)|
|네트워크 파일러| [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig)]
|시스템 확장 |[sysext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/systext.mobileconfig)
|MDE 기본 설정     |[com.microsoft.wdav.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/data_loss_prevention/com.microsoft.wdav.mobileconfig)|
|MAU 기본 설정|[com.microsoft.autoupdate2.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/microsoft_auto_update/com.microsoft.autoupdate2.mobileconfig)|
|설치 패키지     |준수 포털 설치 **패키지에서** 다운로드한 파일 이름 *\* wdav.pkg*\* |

> [!TIP]
> *.mobileconfig* 파일을 개별적으로 또는 다음이 포함된 결합된 [단일 파일로](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig) 다운로드할 수 있습니다.
> - accessibility.mobileconfig
> - fulldisk.mobileconfig
> - netfilter.mobileconfig
> - 시스템 확장
>
>이러한 개별 파일이 업데이트되는 경우 결합된 파일을 다시 다운로드하거나 업데이트된 단일 파일을 개별적으로 다운로드해야 합니다.

<!--2. Copy this code and save it in a file named `com.microsoft.autoupdate2.xml`.

```xml
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>B762FF60-6ACB-4A72-9E72-459D00C936F3</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.autoupdate2</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft AutoUpdate settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft AutoUpdate configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
            <key>PayloadUUID</key>
            <string>5A6F350A-CC2C-440B-A074-68E3F34EBAE9</string>
            <key>PayloadType</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadOrganization</key>
            <string>Microsoft</string>
            <key>PayloadIdentifier</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft AutoUpdate configuration settings</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>ChannelName</key>
            <string>Production</string>
            <key>HowToCheck</key>
            <string>AutomaticDownload</string>
            <key>EnableCheckForUpdatesButton</key>
            <true/>
            <key>DisableInsiderCheckbox</key>
            <false/>
            <key>SendAllTelemetryEnabled</key>
            <true/>
            </dict>
        </array>
    </dict>
</plist>
```
-->

2. 디바이스 **Microsoft Endpoint Manager 프로필**  >    >  **센터 를 열 수 있습니다.**

1. 선택: **프로필 만들기** 

1. 다음을 선택:
    1. **플랫폼 = macOS**
    1. **프로필 유형 = 서식 파일**
    1. **서식 파일 이름 = 사용자 지정**

1. 만들기 **선택**

1. 이 예제의 *접근성formacOS와* 같은 프로필 이름을 선택하십시오. **다음** 을 선택합니다.

1. 1단계에서 다운로드한 **accessibility.mobileconfig** 파일을 구성 프로필 파일로 선택하십시오.

1. 다음 **선택**

1. 할당 **탭에서** 이러한 구성을 배포할 그룹을 추가하고 다음 을 **선택합니다.**

1. 설정을 검토하고 **만들기를 선택해** 구성을 배포합니다.

1. 3-11단계를 반복하여 다음에 대한 프로필을 만들 수 있습니다.
    1. **fulldisk.mobileconfig** 파일
    1. **com.microsoft.autoupdate2.xml** 파일
    1. MDE 기본 **com.microsoft.wdav.xml** 파일
        1. 바이러스 백신 엔진 또는 `passive mode`  =  `true` `false` 를 설정 합니다. `true`DLP만 배포하는 경우 사용 `false`DLP 및 MDE(Microsoft Defender for Endpoint)를 배포하는 경우 값을 사용하거나 할당하지 않습니다.
    1. **netfilter.mobileconfig**
 
1. 장치 **구성**  >  **프로필을** 열면 생성된 프로필이 표시됩니다.

1. 구성 **프로필 페이지에서** 방금 만든 프로필(이 예의 *접근성formacOS)을* 선택하고 장치 상태를 선택하면 장치 목록과 구성 프로필의 배포 상태를 확인합니다. 

### <a name="get-the-device-onboarding-package"></a>장치 온보더링 패키지를 얻습니다.

1. 준수 **센터에서** 장치 **설정**  >  **열고** **온보더링 을 선택하세요.**
 
1. **온보더링 프로세스를 시작하려면** 운영 체제 선택에서 **macOS를 선택합니다.**
 
1. 배포 **방법에 대해** 모바일 장치 **관리/를 Microsoft Intune.**
 
1. **온보더링 패키지 다운로드를 선택하십시오.** 여기에는 온보더링 코드가DeviceComplianceOnboarding.xml *포함되어* 있습니다.

### <a name="deploy-the-onboarding-package"></a>온보더링 패키지 배포

1. 디바이스 **Microsoft Endpoint Manager 프로필**  >    >  **센터 를 열 수 있습니다.**

1. Choose: **Create profile**. 

1. 다음을 선택:
    1. **플랫폼 = macOS**
    1. **프로필 유형 = 서식 파일**
    1. **서식 파일 이름 = 사용자 지정**

1. 만들기 **선택**

1. 이 예제의 *OnboardingPackage와* 같이 프로필의 이름을 선택하십시오. **다음** 을 선택합니다.

1. 구성 *DeviceComplianceOnboarding.xml* 파일로 선택하십시오.

1. 다음 **선택**

1. 할당 **탭에서** 이러한 구성을 배포할 그룹을 추가하고 다음 을 **선택합니다.**

1. 설정을 검토하고 **만들기를 선택해** 구성을 배포합니다.

### <a name="enable-system-extension"></a>시스템 확장 사용

1. In the **Microsoft Endpoint Manager select** **Create Profile** under Configuration **Profiles**

1. 다음을 선택:
    1. **플랫폼 = macOS**
    1. **프로필 유형 = 서식 파일**
    1. **템플릿 이름 = 확장명**

1. 만들기 **선택**

1. 기본 **탭에서** 이 새 프로필에 이름을 지정합니다.

1. 구성 설정 **탭에서** **시스템 확장을 확장합니다.**

1. 번들 **식별자 및** **팀 식별자에서** 다음 값을 설정

|번들 식별자  |팀 식별자  |
|---------|---------|
|**com.microsoft.wdav.epsext**|**UBF8T346G9**|
|**com.microsoft.wdav.netext**|**UBF8T346G9**|


1. 할당 **탭에서** 이러한 구성을 배포할 그룹을 추가하고 다음 을 **선택합니다.**

1. **다음을** 선택하고 구성을 배포합니다.

### <a name="get-the-installation-package"></a>설치 패키지를 얻습니다.

1. 준수 **센터에서** 장치 **설정**  >  **열고** **온보더링 을 선택하세요.**
 
1. **온보더링 프로세스를 시작하려면** 운영 체제 선택에서 **macOS 선택**
 
1. 배포 **방법에 대해 모바일** 장치 **관리/모바일** Microsoft Intune
 
1. 설치 **패키지 다운로드 를 선택 합니다.** 이렇게 하면 *wdav.pkg 파일이* 표시됩니다.

> [!IMPORTANT]
> *wdav.pkg를* 배포하기 전에 Package via Intune, it must be reformatted using the *Intune App Wrapping Tools for Mac into* the *wdav.pkg.intunemac* format.
 

### <a name="deploy-the-microsoft-dlp-installation-package"></a>Microsoft DLP 설치 패키지 배포

1. [macOS LOB(LOB)](/mem/intune/apps/lob-apps-macos) 앱을 추가하는 방법의 절차에 Microsoft Intune *wdav.pkg* 파일을 적절한 형식으로 변환하고 Intune을 통해 배포합니다.

## <a name="offboard-macos-devices-using-intune"></a>Intune을 사용하여 macOS 장치 오프보드

> [!NOTE]
> 오프보링을 통해 디바이스가 포털에 센서 데이터 전송을 중지하지만, 디바이스에서 전송한 모든 경고에 대한 참조를 포함하여 장치의 데이터는 최대 6개월 동안 보존됩니다.

2. Microsoft Endpoint Manager **센터에서** 장치 구성 프로필을 열면 생성된  >  프로필이 표시됩니다.

1. 구성 **프로필 페이지에서** *wdav.pkg.intunemac 프로필을 선택합니다.*

1. 장치 **상태를 선택하여** 장치 목록 및 구성 프로필의 배포 상태를 확인합니다.

1. 속성 **및** **할당 열기**

1. 배정에서 그룹을 제거합니다. 이렇게 하면 *wdav.pkg.intunemac* 패키지가 제거된 다음 준수 솔루션에서 macOS 디바이스를 오프보드합니다.
