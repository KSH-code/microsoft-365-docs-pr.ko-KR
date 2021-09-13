---
title: Microsoft Defender for Endpoint Device Control 이동식 Storage 보호
description: 사용자 또는 컴퓨터 또는 둘 다 권한이 없는 이동식 저장소 미디어를 사용하지 못하도록 하는 '기능' 이해
keywords: 이동식 저장소 미디어
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 80a3d5bee2f26e708969832c67982f679b95c0b4
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59222836"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a>Microsoft Defender for Endpoint Device Control 이동식 Storage 보호

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Microsoft Defender for Endpoint의 장치 제어 이동식 저장소 보호는 사용자, 끝점 또는 둘 다 권한이 없는 이동식 저장소 미디어를 사용하지 못하게 합니다.

## <a name="protection-policies"></a>보호 정책

### <a name="removable-storage-access-control"></a>이동식 저장소 액세스 제어

**기능**

- *감사* 제외를 포함하거나 제외하지 않고 다양한 장치 속성을 기반으로 이동식 저장소에 대한 액세스를 읽거나 쓰기 또는 실행합니다.
- *방지* 제외를 포함하거나 제외하지 않고 액세스 읽기 또는 쓰기 또는 실행 - 다양한 장치 속성에 따라 특정 장치를 허용합니다.

**Windows 10 지원 세부 정보**:

- 장치 수준 사용자 수준에서 적용됩니다. 또는 둘 다를 사용할 수 있습니다. 특정 컴퓨터의 특정 이동식 저장소에 대한 읽기/쓰기/실행 액세스를 수행하는 특정 사용자만 허용합니다.
- MEM OMA-URI 및 GPO를 지원합니다.
- 나열된['장치 속성'이](#device-properties)지원됩니다.
- 이 기능의 Windows [이동식 저장소 액세스 제어를 참조합니다.](device-control-removable-storage-access-control.md)

**지원되는 플랫폼** - Windows 10

**macOS 지원 세부 정보**:

- 장치 수준에서 적용: 로그온한 모든 사용자에 대해 동일한 정책이 적용됩니다.
- macOS 관련 정보는 [macOS용 장치 제어를 참조하세요.](mac-device-control-overview.md)

**지원되는 플랫폼** - macOS 카탈로니아 10.15.4+(시스템 확장 사용 가능)


### <a name="device-installation"></a>장치 설치

**기능** - 다양한 장치 속성에 따라 제외를 포함하거나 제외하지 않고 설치하지 못하게 합니다.

**Windows 10 지원 세부 정보**:

- 장치 수준에서 적용: 로그온한 모든 사용자에 대해 동일한 정책이 적용됩니다.
- 그룹 Microsoft Endpoint Manager 개체를 지원할 수 있습니다.
- 나열된['장치 속성'이](#device-properties)지원됩니다.
- 자세한 내용은 Windows [Microsoft Defender for Endpoint를](control-usb-devices-using-intune.md)사용하여 USB 장치 및 기타 이동식 미디어를 제어하는 방법을 참조하세요.

**지원되는 플랫폼** - Windows 10

**macOS 지원 세부 정보**:

- 장치 수준에서 적용: 로그온한 사용자에 대해 동일한 정책이 적용됩니다.
- macOS 관련 정보는 [macOS용 장치 제어를 참조하세요.](mac-device-control-overview.md)

**지원되는 플랫폼** - macOS 카탈로니아 10.15.4+(시스템 확장 사용) 이상

### <a name="endpoint-dlp-removable-storage"></a>끝점 DLP 이동식 저장소

**기능** - 사용자가 항목 또는 정보를 이동식 미디어 또는 USB 장치에 복사할 수 있도록 감사, 경고 또는 방지

**설명** - 자세한 내용은 Windows 끝점 데이터 손실 Microsoft 365 [정보를 참조하세요.](../../compliance/endpoint-dlp-learn-about.md)

**지원되는 플랫폼** - Windows 10

### <a name="bitlocker"></a>BitLocker

**기능**:

- BitLocker로 보호되지 않는 이동식 드라이브에 기록할 데이터를 차단합니다.
- 이동식 드라이브에 대한 액세스 차단(조직이 소유한 컴퓨터에서 암호화되지 않은 경우)

**설명** - 에 대한 자세한 Windows [BitLocker - 이동식](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings)드라이브 설정.

**지원되는 플랫폼** - Windows 10

## <a name="device-properties"></a>장치 속성

Microsoft Defender for Endpoint Device Control 이동식 Storage 보호를 사용하면 아래 표에 설명된 속성에 따라 이동식 저장소 액세스를 제한할 수 있습니다.

<br>

****

|속성 이름|적용 가능한 정책|운영 체제에 적용|설명|
|---|---|---|---|
|Device Class|[끝점용 Microsoft Defender를 사용하여 USB 장치 및 기타 이동식 미디어를 제어하는 방법](control-usb-devices-using-intune.md)|Windows|장치 ID 형식에 대한 자세한 내용은 장치 설정 [클래스 를 참조하세요.](/windows-hardware/drivers/install/overview-of-device-setup-classes) 다음 두 링크는 장치 설정 클래스의 전체 목록을 제공합니다. '시스템 사용' 클래스는 주로 출하 시 컴퓨터/컴퓨터와 함께 제공된 장치를 참조하며, '공급업체' 클래스는 대부분 기존 컴퓨터/컴퓨터에 연결할 수 있는 장치를 참조합니다. 공급업체에서 사용할 수 있는 시스템 정의 장치 설정 클래스 [- Windows 드라이버](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors) 및 시스템 사용에 예약된 시스템 정의 장치 설정 클래스 - Windows [드라이버).](/windows-hardware/drivers/install/system-defined-device-setup-classes-reserved-for-system-use) **참고:** 이동식 저장소뿐만 아니라 모든 장치에 장치 설치를 적용할 수 있습니다.|
|기본 ID|[이동식 저장소 액세스 제어](device-control-removable-storage-access-control.md)|Windows|기본 ID에는 이동식 저장소, CD/DVD 및 이동식 Windows/WPD가 포함됩니다.|
|장치 ID|[이동식 저장소 액세스 제어](device-control-removable-storage-access-control.md); <p> [끝점용 Microsoft Defender를 사용하여 USB 장치 및 기타 이동식 미디어를 제어하는 방법](control-usb-devices-using-intune.md)|Windows|장치 ID 형식에 대한 자세한 내용은 표준 USB 식별자(예: USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07)를 참조하세요. [](/windows-hardware/drivers/install/standard-usb-identifiers)|
|하드웨어 ID|[이동식 저장소 액세스 제어](device-control-removable-storage-access-control.md) <p> [끝점용 Microsoft Defender를 사용하여 USB 장치 및 기타 이동식 미디어를 제어하는 방법](control-usb-devices-using-intune.md)|Windows|시스템에서 장치를 식별한 문자열(예: USBSTOR\DiskGeneric_Flash_Disk___8.07) **참고:** 하드웨어 ID가 고유하지 않습니다. 다른 디바이스가 동일한 값을 공유할 수 있습니다.|
|인스턴스 ID|[이동식 저장소 액세스 제어](device-control-removable-storage-access-control.md) <p> 디바이스 설치|Windows|USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0과 같은 문자열은 시스템에서 장치를 고유하게 식별합니다.|
|이름|[이동식 저장소 액세스 제어](device-control-removable-storage-access-control.md)|Windows|장치에 연결된 문자열(예: 일반 플래시 디스크 USB 장치)|
|공급업체 ID/제품 ID|[이동식 저장소 액세스 제어](device-control-removable-storage-access-control.md)|Windows <p> macOS|공급업체 ID는 USB 위원회가 공급업체에 할당하는 4자리 공급업체 코드입니다. 제품 ID는 공급업체가 장치에 할당하는 4자리 제품 코드입니다. 와일드카드를 지원합니다.|
|Serial NumberId|[이동식 저장소 액세스 제어](device-control-removable-storage-access-control.md)|Windows <p> macOS |예: <SerialNumberId>002324B534BCB431B000058A</SerialNumberId>|
|
