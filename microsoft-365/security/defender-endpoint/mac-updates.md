---
title: Mac에서 끝점용 Microsoft Defender 업데이트 배포
description: 엔터프라이즈 환경에서 Mac의 끝점용 Microsoft Defender에 대한 업데이트를 제어합니다.
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, mac, 업데이트, 배포
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b2abd270aeee07e84cf31711494d68ca15885515
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60174678"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-macos"></a>macOS에서 끝점용 Microsoft Defender 업데이트 배포

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [Microsoft Defender for Endpoint(macOS용)](microsoft-defender-endpoint-mac.md)
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft는 성능, 보안을 개선하고 새로운 기능을 제공하기 위해 소프트웨어 업데이트를 정기적으로 게시합니다.

MacOS에서 끝점에 대한 Microsoft Defender를 업데이트하기 위해 MAU(Microsoft 자동 업데이트)라는 프로그램이 사용됩니다. 기본적으로 MAU는 매일 업데이트를 자동으로 확인하지만 매주, 월별 또는 수동으로 변경할 수 있습니다.

![MAU 스크린샷.](images/MDATP-34-MAU.png)

소프트웨어 배포 도구를 사용하여 업데이트를 배포하기로 결정한 경우 소프트웨어 업데이트를 수동으로 확인하도록 MAU를 구성해야 합니다. 기본 설정을 배포하여 MAU가 조직의 Mac에 대한 업데이트를 검사하는 방법과 경우를 구성할 수 있습니다.

## <a name="use-msupdate"></a>Msupdate 사용

MAU에는 업데이트가 적용되는 경우를 보다 정확하게 제어할 수 있도록 IT 관리자를 위해 설계된 *msupdate라는* 명령줄 도구가 포함되어 있습니다. 이 도구를 사용하는 방법에 대한 지침은 [msupdate를](/deployoffice/mac/update-office-for-mac-using-msupdate)사용하여 업데이트 Mac용 Office 있습니다.

MAU에서 macOS의 끝점용 Microsoft Defender에 대한 응용 프로그램 식별자는 *WDAV00입니다.* macOS의 끝점용 Microsoft Defender에 대한 최신 업데이트를 다운로드하고 설치하려면 터미널 창에서 다음 명령을 실행합니다.

```dos
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a>Microsoft 자동 업데이트 기본 설정 설정

이 섹션에서는 MAU를 구성하는 데 사용할 수 있는 가장 일반적인 기본 설정에 대해 설명합니다. 이러한 설정은 엔터프라이즈에서 사용하는 관리 콘솔을 통해 구성 프로필로 배포할 수 있습니다. 구성 프로필의 예는 다음 섹션에 나와 있습니다.

### <a name="set-the-channel-name"></a>채널 이름 설정

채널은 MAU를 통해 제공되는 업데이트의 유형과 빈도를 확인합니다. 의 `Beta` 장치는 및 의 장치 앞에 새로운 기능을 시도할 수 `Preview` `Current` 있습니다.

채널에는 `Current` 제품의 가장 안정적인 버전이 포함되어 있습니다.

> [!IMPORTANT]
> Microsoft 자동 업데이트 버전 4.29 이전의 채널 이름은 서로 다릅니다.
>
> - `Beta` 이름이 `InsiderFast` 지정됩니다(Insider Fast).
> - `Preview` 이름이 `External` 지정(Insider Slow)
> - `Current` 명명 `Production`

> [!TIP]
> 새 기능을 미리 보고 초기 피드백을 제공하기 위해서는 엔터프라이즈의 일부 장치를 또는 로 구성하는 것이 `Beta` `Preview` 좋습니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.autoupdate2`|
|**키**|ChannelName|
|**Data type**|String|
|**사용 가능한 값:**|Beta <p> Preview <p> Current|
|||

> [!WARNING]
> 이 설정은 Microsoft 자동 업데이트를 통해 업데이트되는 모든 응용 프로그램의 채널을 변경합니다. macOS의 끝점용 Microsoft Defender에 대한 채널만 변경하기 위해 원하는 채널로 바꿔서 다음 명령을 `[channel-name]` 실행합니다.
>
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a>업데이트 확인 빈도 설정

MAU가 업데이트를 검색하는 자주 변경합니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.autoupdate2`|
|**키**|UpdateCheckFrequency|
|**Data type**|정수|
|**기본값**.|720(분)|
|**설명**|이 값은 분으로 설정됩니다.|
|||

### <a name="change-how-mau-interacts-with-updates"></a>MAU가 업데이트와 상호 작용하는 방식 변경

MAU에서 업데이트를 검색하는 방법을 변경합니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.autoupdate2`|
|**키**|HowToCheck|
|**Data type**|String|
|**사용 가능한 값:**|수동 <p> AutomaticCheck <p> AutomaticDownload|
|**설명**|AutomaticDownload는 다운로드를 수행하고 가능한 경우 자동으로 설치합니다.|
|||

### <a name="change-whether-the-check-for-updates-button-is-enabled"></a>"업데이트 확인" 단추를 사용할 수 있는지 여부 변경

로컬 사용자가 Microsoft 자동 업데이트 사용자 인터페이스에서 "업데이트 확인" 옵션을 클릭할 수 있는지 여부를 변경합니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.autoupdate2`|
|**키**|EnableCheckForUpdatesButton|
|**Data type**|부울|
|**사용 가능한 값:**|True(기본값) <p> False|
|||

### <a name="disable-insider-checkbox"></a>내부자 사용 안함 확인란

true로 설정하여 "Office 프로그램 참여..."로 설정 사용자에게 확인란을 사용할 수 없음/회색으로 나타났습니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.autoupdate2`|
|**키**|DisableInsiderCheckbox|
|**Data type**|부울|
|**사용 가능한 값:**|False(기본값) <p> True|
|||

### <a name="limit-the-telemetry-that-is-sent-from-mau"></a>MAU에서 전송된 원격 분석 제한

false로 설정하여 최소 하트비트 데이터, 응용 프로그램 사용 현황 및 환경 세부 정보를 보내지 않습니다.

<br>

****

|섹션|값|
|---|---|
|**도메인**|`com.microsoft.autoupdate2`|
|**키**|SendAllTelemetryEnabled|
|**Data type**|부울|
|**사용 가능한 값:**|True(기본값) <p> False|
|||

## <a name="example-configuration-profile"></a>구성 프로필 예제

다음 구성 프로필은 다음과 같은 데 사용됩니다.

- 프로덕션 채널에 디바이스 추가
- 업데이트를 자동으로 다운로드 및 설치
- 사용자 인터페이스에서 "업데이트 확인" 단추를 사용하도록 설정
- 장치의 사용자가 Insider 채널에 등록할 수 있도록 허용

> [!WARNING]
> 아래 구성은 예제 구성으로, 설정 및 구성 조정을 제대로 검토하지 않으면 프로덕션에서 사용되지 않습니다.

> [!TIP]
> 새 기능을 미리 보고 초기 피드백을 제공하기 위해서는 엔터프라이즈의 일부 장치를 또는 로 구성하는 것이 `Beta` `Preview` 좋습니다.

### <a name="jamf"></a>JAMF

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
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
</plist>
```

### <a name="intune"></a>Intune

```XML
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

MAU를 구성하려면 엔터프라이즈에서 사용하는 관리 도구에서 이 구성 프로필을 배포할 수 있습니다.

- JAMF에서 이 구성 프로필을 업로드하고 기본 설정 도메인을 *com.microsoft.autoupdate2로 설정합니다.*
- Intune에서 이 구성 프로필을 업로드하고 사용자 지정 구성 프로필 이름을 *com.microsoft.autoupdate2로 설정하십시오.*

## <a name="resources"></a>리소스

- [msupdate 참조](/deployoffice/mac/update-office-for-mac-using-msupdate)
