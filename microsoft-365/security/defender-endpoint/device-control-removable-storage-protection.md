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
ms.author: v-smandalika
author: v-smandalika
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ec5cfa78852d65db808c4e853f90f5639df25d6f
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300273"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a>Microsoft Defender for Endpoint Device Control 이동식 Storage 보호

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Microsoft Defender for Endpoint Device Control 이동식 Storage 보호는 사용자 또는 컴퓨터 또는 둘 다 권한이 없는 이동식 저장소 미디어를 사용하지 못하도록 방지합니다.

**끝점 이동식 보호를 위한 Microsoft Defender Storage 보호**


|정책  |기능 |설명  |
|---------|---------|---------|
|장치 설치    |  제외를 포함하거나 제외하지 않고 설치 금지 - 다양한 속성을 기반으로 특정 장치를 허용합니다. 자세한 내용은 아래 [장치 속성 섹션을](#device-properties) 참조하세요.        |    컴퓨터 작업: 동일한 컴퓨터에 로그인하는 여러 사용자가 동일한 정책에 의해 제한됩니다. 자세한 내용은 [Endpoint용 Microsoft Defender를](control-usb-devices-using-intune.md)사용하여 USB 장치 및 기타 이동식 미디어를 제어하는 방법을 참조하세요.     |
|이동식 저장소 액세스 제어      | (1) 예외 또는 예외 없이 다양한 장치 속성을 기반으로 이동식 저장소에 대한 읽기 또는 쓰기 또는 실행 액세스를 감사합니다. 자세한 내용은 아래 [장치 속성 섹션을](#device-properties) 참조하세요. (2) 읽기 또는 쓰기 또는 제외 없이 액세스 실행 금지 - 다양한 장치 속성에 따라 특정 장치를 허용합니다. 장치 속성에 대한 자세한 내용은 아래 [장치 속성 섹션을](#device-properties) 참조하세요.     |     컴퓨터 또는 사용자 또는 둘 다에서 작동합니다. 특정 컴퓨터의 특정 이동식 저장소에 대한 읽기/쓰기/실행 액세스를 수행하는 특정 사용자만 허용합니다. 이동식 저장소 Windows 액세스 제어를 [참조합니다.](device-control-removable-storage-access-control.md) Mac의 기능에 대한 자세한 내용은 [macOS용 장치 제어를 참조하세요.](mac-device-control-overview.md)     |
|끝점 DLP 이동식 저장소      |    사용자가 이동식 미디어 또는 USB 장치에 항목이나 정보를 복사하지 못하도록 감사하거나 경고합니다.     |  자세한 내용은 [Microsoft Endpoint DLP 를 참조하세요.](/compliance/endpoint-dlp-learn-about.md)       |
|BitLocker    |     보호되지 않는 이동식 드라이브에 기록할 데이터를 차단합니다BitLocker: 이동식 드라이브에 대한 액세스 차단(조직이 소유한 컴퓨터에서 암호화되지 않은 경우)    |   자세한 내용은 BitLocker – [이동식](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings#bitlocker---removable-drive-settings.md)드라이브 설정.      |

## <a name="device-properties"></a>장치 속성

Microsoft Defender for Endpoint Device Control 이동식 Storage 보호를 사용하면 아래 표에 설명된 속성에 따라 이동식 저장소 액세스를 제한할 수 있습니다.


|속성 이름  |적용 가능한 정책  |운영 체제에 적용  |설명  |
|---------|---------|---------|---------|
|Device Class    |     [끝점용 Microsoft Defender를 사용하여 USB 장치 및 기타 이동식 미디어를 제어하는 방법](control-usb-devices-using-intune.md)     |   Windows      |  장치 ID 형식에 대한 자세한 내용은 장치 설정 [클래스 를 참조하세요.](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors) **참고:** 이동식 저장소뿐만 아니라 모든 장치에 장치 설치를 적용할 수 있습니다.       |
|기본 ID   |     이동식 저장소 액세스 제어    |   Windows      |      기본 ID에는 이동식 저장소 및 CD/DVD가 포함됩니다.   |
|장치 ID     |  [끝점용 Microsoft Defender를](control-usb-devices-using-intune.md)사용하여 USB 장치 및 기타 이동식 미디어를 제어하는 방법 이동식 저장소 액세스 제어       |      Windows   |    장치 ID 형식에 대한 자세한 내용은 표준 USB 식별자(예: USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07)를 참조하세요. [](/windows-hardware/drivers/install/standard-usb-identifiers)      |
|하드웨어 ID     |     [끝점용 Microsoft Defender를](control-usb-devices-using-intune.md)사용하여 USB 장치 및 기타 이동식 미디어를 제어하는 방법 이동식 저장소 액세스 제어    |     Windows    |    시스템에서 장치를 식별한 문자열(예: USBSTOR\DiskGeneric_Flash_Disk______8.07) **참고:** 하드웨어 ID가 고유하지 않습니다. 다른 디바이스가 동일한 값을 공유할 수 있습니다.|
|인스턴스 ID    | 장치 설치 이동식 저장소 액세스 제어     |     Windows    |   USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0과 같은 문자열은 시스템에서 장치를 고유하게 식별합니다.      |
|이름     |     이동식 저장소 액세스 제어    |   Windows      |    장치에 연결된 문자열(예: 일반 플래시 디스크 USB 장치)     |
|공급업체 ID/제품 ID     |  이동식 저장소 액세스 제어       |   Windows Mac      |     공급업체 ID는 USB 위원회가 공급업체에 할당하는 4자리 공급업체 코드입니다. 제품 ID는 공급업체가 장치에 할당하는 4자리 제품 코드입니다. 와일드카드를 지원합니다.    |
|Serial NumberId     |     이동식 저장소 액세스 제어    |      Windows Mac   |     예: <SerialNumberId>002324B534BCB431B000058A</SerialNumberId>    |

## <a name="related-topic"></a>관련 항목

- [Microsoft Defender for Endpoint Device Control 이동식 Storage 액세스 제어](device-control-removable-storage-access-control.md)
