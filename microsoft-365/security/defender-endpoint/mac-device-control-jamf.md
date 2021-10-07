---
title: JAMF에 대한 장치 제어 정책의 예
description: JAMF와 함께 사용할 수 있는 예제를 사용하여 장치 제어 정책을 사용하는 방법을 설명합니다.
keywords: Microsoft, defender, endpoint, Endpoint용 Microsoft Defender, mac, 장치, 제어, usb, 이동식, 미디어, jamf
ms.prod: m365-security
ms.mktglfcycl: security
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
ms.openlocfilehash: c7306782d62f91cea528a70ff0c3754085d0d3c2
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60195248"
---
# <a name="examples-of-device-control-policies-for-jamf"></a>JAMF에 대한 장치 제어 정책의 예

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

이 문서에는 조직에 맞게 사용자 지정할 수 있는 장치 제어 정책의 예가 포함되어 있습니다. 이러한 예제는 기업에서 JAMF를 사용하여 장치를 관리하는 경우 적용할 수 있습니다.

## <a name="restrict-access-to-all-removable-media"></a>모든 이동식 미디어에 대한 액세스 제한

다음 예에서는 모든 이동식 미디어에 대한 액세스를 제한합니다. 정책의 최상위 수준에서 적용되는 사용 권한을 참고하십시오. 즉, 모든 파일 작업이 `none` 금지됩니다.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>deviceControl</key>
    <dict>
        <key>removableMediaPolicy</key>
        <dict>
            <key>enforcementLevel</key>
            <string>block</string>
            <key>permission</key>
            <array>
                <string>none</string>
            </array>
        </dict>
    </dict>
</dict>
</plist>
```

## <a name="set-all-removable-media-to-be-read-only"></a>모든 이동식 미디어를 읽기 전용으로 설정

다음 예제에서는 모든 이동식 미디어를 읽기 전용으로 구성합니다. 정책의 최상위 수준에서 적용되는 사용 권한을 기록해 두면 모든 쓰기 및 실행 작업이 `read` 허용되지 않습니다.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>deviceControl</key>
    <dict>
        <key>removableMediaPolicy</key>
        <dict>
            <key>enforcementLevel</key>
            <string>block</string>
            <key>permission</key>
            <array>
                <string>read</string>
            </array>
        </dict>
    </dict>
</dict>
</plist>
```

## <a name="disallow-program-execution-from-removable-media"></a>이동식 미디어에서 프로그램 실행을 안 하게 합니다.

다음 예제에서는 이동식 미디어에서 프로그램 실행을 금지할 수 있는 방법을 보여줍니다. 정책의 최상위 수준에서 적용되는 사용 `read` `write` 권한에 유의합니다.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>deviceControl</key>
    <dict>
        <key>removableMediaPolicy</key>
        <dict>
            <key>enforcementLevel</key>
            <string>block</string>
            <key>permission</key>
            <array>
                <string>read</string>
                <string>write</string>
            </array>
        </dict>
    </dict>
</dict>
</plist>
```

## <a name="restrict-all-devices-from-specific-vendors"></a>특정 공급업체의 모든 장치 제한

다음 예에서는 및 로 식별된 특정 공급업체의 모든 장치를 `fff0` `4525` 제한합니다. 정책의 최상위 수준에 정의된 권한이 모든 사용 권한(읽기, 쓰기 및 실행)을 나열하기 때문에 다른 모든 장치는 제한되지 않습니다.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>deviceControl</key>
    <dict>
        <key>removableMediaPolicy</key>
        <dict>
            <key>enforcementLevel</key>
            <string>block</string>
            <key>permission</key>
            <array>
                <string>read</string>
                <string>write</string>
                <string>execute</string>
            </array>
            <key>vendors</key>
            <dict>
                <key>fff0</key>
                <dict>
                    <key>permission</key>
                    <array>
                        <string>none</string>
                    </array>
                </dict>
                <key>4525</key>
                <dict>
                    <key>permission</key>
                    <array>
                        <string>none</string>
                    </array>
                </dict>
            </dict>
        </dict>
    </dict>
</dict>
</plist>
```

## <a name="restrict-specific-devices-identified-by-vendor-id-product-id-and-serial-number"></a>공급업체 ID, 제품 ID 및 일련 번호로 식별되는 특정 장치 제한

다음 예에서는 공급업체 ID, 제품 ID 및 일련 번호 및 로 식별되는 두 개의 특정 `fff0` `1000` 장치를 `04ZSSMHI2O7WBVOA` `04ZSSMHI2O7WBVOB` 제한합니다. 정책의 다른 모든 수준에서 사용 권한에는 가능한 모든 값(읽기, 쓰기 및 실행)이 포함됩니다. 즉, 다른 모든 디바이스는 제한되지 않습니다.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>deviceControl</key>
    <dict>
        <key>removableMediaPolicy</key>
        <dict>
            <key>enforcementLevel</key>
            <string>block</string>
            <key>permission</key>
            <array>
                <string>read</string>
                <string>write</string>
                <string>execute</string>
            </array>
            <key>vendors</key>
            <dict>
                <key>fff0</key>
                <dict>
                    <key>permission</key>
                    <array>
                        <string>read</string>
                        <string>write</string>
                        <string>execute</string>
                    </array>
                    <key>products</key>
                    <dict>
                        <key>1000</key>
                        <dict>
                            <key>permission</key>
                            <array>
                                <string>read</string>
                                <string>write</string>
                                <string>execute</string>
                            </array>
                            <key>serialNumbers</key>
                            <dict>
                                <key>04ZSSMHI2O7WBVOA</key>
                                <array>
                                  <string>none</string>
                                </array>
                                <key>04ZSSMHI2O7WBVOB</key>
                                <array>
                                  <string>none</string>
                                </array>
                            </dict>
                        </dict>
                    </dict>
                </dict>
            </dict>
        </dict>
    </dict>
</dict>
</plist>
```

## <a name="related-topics"></a>관련 항목

- [macOS용 장치 제어 개요](mac-device-control-overview.md)
