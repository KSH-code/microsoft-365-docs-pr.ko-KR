---
title: JAMF에 대한 장치 제어 정책의 예
description: JAMF와 함께 사용할 수 있는 예제를 사용하여 장치 제어 정책을 사용하는 방법을 설명합니다.
keywords: Microsoft, defender, endpoint, Endpoint용 Microsoft Defender, mac, 장치, 제어, usb, 이동식, 미디어, jamf
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b9ce161a472366d11b267824c9bd08ceccf285aa
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933460"
---
# <a name="examples-of-device-control-policies-for-jamf"></a><span data-ttu-id="0cda5-104">JAMF에 대한 장치 제어 정책의 예</span><span class="sxs-lookup"><span data-stu-id="0cda5-104">Examples of device control policies for JAMF</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0cda5-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="0cda5-105">**Applies to:**</span></span>
- [<span data-ttu-id="0cda5-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0cda5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0cda5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0cda5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0cda5-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="0cda5-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0cda5-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="0cda5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="0cda5-110">이 문서에는 조직에 맞게 사용자 지정할 수 있는 장치 제어 정책의 예가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cda5-110">This document contains examples of device control policies that you can customize for your own organization.</span></span> <span data-ttu-id="0cda5-111">이러한 예제는 기업에서 JAMF를 사용하여 장치를 관리하는 경우 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cda5-111">These examples are applicable if you are using JAMF to manage devices in your enterprise.</span></span>

## <a name="restrict-access-to-all-removable-media"></a><span data-ttu-id="0cda5-112">모든 이동식 미디어에 대한 액세스 제한</span><span class="sxs-lookup"><span data-stu-id="0cda5-112">Restrict access to all removable media</span></span>

<span data-ttu-id="0cda5-113">다음 예에서는 모든 이동식 미디어에 대한 액세스를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="0cda5-113">The following example restricts access to all removable media.</span></span> <span data-ttu-id="0cda5-114">정책의 최상위 수준에서 적용되는 사용 권한을 참고하십시오. 즉, 모든 파일 작업이 `none` 금지됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cda5-114">Note the `none` permission that is applied at the top level of the policy, meaning that all file operations will be prohibited.</span></span>

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

## <a name="set-all-removable-media-to-be-read-only"></a><span data-ttu-id="0cda5-115">모든 이동식 미디어를 읽기 전용으로 설정</span><span class="sxs-lookup"><span data-stu-id="0cda5-115">Set all removable media to be read-only</span></span>

<span data-ttu-id="0cda5-116">다음 예제에서는 모든 이동식 미디어를 읽기 전용으로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0cda5-116">The following example configures all removable media to be read-only.</span></span> <span data-ttu-id="0cda5-117">정책의 최상위 수준에서 적용되는 사용 권한을 기록해 두면 모든 쓰기 및 실행 작업이 `read` 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0cda5-117">Note the `read` permission that is applied at the top level of the policy, meaning that all write and execute operations will be disallowed.</span></span>

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

## <a name="disallow-program-execution-from-removable-media"></a><span data-ttu-id="0cda5-118">이동식 미디어에서 프로그램 실행을 안 하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cda5-118">Disallow program execution from removable media</span></span>

<span data-ttu-id="0cda5-119">다음 예제에서는 이동식 미디어에서 프로그램 실행을 금지할 수 있는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="0cda5-119">The following example shows how program execution from removable media can be disallowed.</span></span> <span data-ttu-id="0cda5-120">정책의 최상위 수준에서 적용되는 사용 `read` `write` 권한에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="0cda5-120">Note the `read` and `write` permissions that are applied at the top level of the policy.</span></span>

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

## <a name="restrict-all-devices-from-specific-vendors"></a><span data-ttu-id="0cda5-121">특정 공급업체의 모든 장치 제한</span><span class="sxs-lookup"><span data-stu-id="0cda5-121">Restrict all devices from specific vendors</span></span>

<span data-ttu-id="0cda5-122">다음 예에서는 및 로 식별된 특정 공급업체의 모든 장치를 `fff0` `4525` 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="0cda5-122">The following example restricts all devices from specific vendors (in this case identified by `fff0` and `4525`).</span></span> <span data-ttu-id="0cda5-123">정책의 최상위 수준에 정의된 권한이 모든 사용 권한(읽기, 쓰기 및 실행)을 나열하기 때문에 다른 모든 장치는 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0cda5-123">All other devices will be unrestricted, since the permission defined at the top level of the policy lists all possible permissions (read, write, and execute).</span></span>

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

## <a name="restrict-specific-devices-identified-by-vendor-id-product-id-and-serial-number"></a><span data-ttu-id="0cda5-124">공급업체 ID, 제품 ID 및 일련 번호로 식별되는 특정 장치 제한</span><span class="sxs-lookup"><span data-stu-id="0cda5-124">Restrict specific devices identified by vendor ID, product ID, and serial number</span></span>

<span data-ttu-id="0cda5-125">다음 예에서는 공급업체 ID, 제품 ID 및 일련 번호 및 로 식별되는 두 개의 특정 `fff0` `1000` 장치를 `04ZSSMHI2O7WBVOA` `04ZSSMHI2O7WBVOB` 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="0cda5-125">The following example restricts two specific devices, identified by vendor ID `fff0`, product ID `1000`, and serial numbers `04ZSSMHI2O7WBVOA` and `04ZSSMHI2O7WBVOB`.</span></span> <span data-ttu-id="0cda5-126">정책의 다른 모든 수준에서 사용 권한에는 가능한 모든 값(읽기, 쓰기 및 실행)이 포함됩니다. 즉, 다른 모든 디바이스는 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0cda5-126">At all other levels of the policy the permissions include all possible values (read, write, and execute), meaning that all other devices will be unrestricted.</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="0cda5-127">관련 항목</span><span class="sxs-lookup"><span data-stu-id="0cda5-127">Related topics</span></span>

- [<span data-ttu-id="0cda5-128">macOS용 장치 제어 개요</span><span class="sxs-lookup"><span data-stu-id="0cda5-128">Overview of device control for macOS</span></span>](mac-device-control-overview.md)
