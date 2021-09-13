---
title: 장치 요구 사항
description: 장치와 함께 작동하기 위한 최소 하드웨어 및 소프트웨어 요구 사항에 대한 Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f51208b8376ef160fe83a41e5a2ac74eb843c2f3
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215355"
---
# <a name="device-requirements"></a>장치 요구 사항

Microsoft Managed Desktop 서비스에 포함하기 위한 장치 요구 사항을 정기적으로 평가합니다. 이 문서에서는 장치와 함께 작동하기 위해 장치가 충족해야 하는 하드웨어 및 소프트웨어 요구 사항에 대해 Microsoft Managed Desktop. 이러한 요구 사항에 따라 서비스에서 이미 사용이 승인된 특정 장치 목록을 검토할 수 있습니다. 쇼핑 비즈니스 Microsoft Managed Desktop 사이트에서 Windows 10 Pro [필터링](https://www.microsoft.com/en-us/windowsforbusiness/view-all-devices)

> [!NOTE]
> 이러한 요구 사항은 변경될 수 있지만 하드웨어 요구 사항 변경에 대해 30일 알림이 제공될 것입니다. 가장 최근에 변경된 요구 사항은 로 **\*** 표시됩니다. 

## <a name="check-hardware-requirements"></a>하드웨어 요구 사항 확인

장치 사양 검토 외에도 다운로드 가능한 준비성 [](../get-ready/readiness-assessment-downloadable.md) 평가 검사를 사용하여 특정 장치가 필요한 요구 사항을 충족하는지 확인할 수 있습니다. 또한 이 도구는 서비스 작동에 필요한 네트워크 설정 및 끝점을 확인합니다.

## <a name="minimum-requirements"></a>최소 요구 사항

디바이스에 등록하려면 Microsoft Managed Desktop 이러한 요구 사항을 모두 충족하거나 초과해야 합니다.

### <a name="manufacturer"></a>제조업체

디바이스는 다음 제조업체 중 하나에서 만들어야 합니다.

- Dell
- HP
- Lenovo
- Microsoft


### <a name="installed-software"></a>설치된 소프트웨어

디바이스에 다음 소프트웨어가 사전 설치되어야 합니다.

- Windows 10 Enterprise, Pro 또는 Pro Workstation edition
- 64비트 버전의 엔터프라이즈용 Microsoft 365 앱 
- 적용 가능한 모든 장치 드라이버

> [!NOTE]
> Windows 11은 일반 공급에 도달한 후 사전 설치한 소프트웨어를 위한 추가 옵션입니다.
>
### <a name="physical-features"></a>물리적 기능

디바이스에는 다음 기능이 있어야 합니다.

- UEFI 보안 부팅에 사용 
- 신뢰할 수 있는 플랫폼 모듈 2.0 
- 가상화 기반 보안 지원 
- [BIOS에서](/windows-hardware/drivers/bringup/device-guard-and-credential-guard) 지원하는 하이퍼바이서로 보호된 코드 무결성

이러한 기능 및 서비스에서 사용하는 기술과 관련된 기술에 대한 자세한 내용은 Microsoft Managed Desktop [참조합니다.](../intro/technologies.md)

> [!NOTE]
>- ARM 프로세서가 지원되지 않습니다.
>- Windows 11에는 추가 [하드웨어 요구 사항이 있습니다.](/windows/whats-new/windows-11-requirements)

장치는 저장소 및 메모리에 대한 다음 제한을 충족하거나 초과해야 합니다.

- 부팅 드라이브는 하드 디스크가 될 수 없습니다. 예를 들어 SSD, NVMe 및 eMMC 드라이브는 모두 유효한 선택입니다.
- 부팅 드라이브의 용량은 128GB 이상입니다.
- 내부 장치 메모리(RAM)가 8GB를 초과하거나 같아야 합니다.

디바이스가 2020년 7월 1일 이후에 만들어진 경우 를 지원하려면 IR 카메라, 지문 판독기 또는 둘 [다가 Windows Hello.](/windows-hardware/design/device-experiences/windows-hello-enhanced-sign-in-security)

## <a name="recommended-features"></a>권장 기능

이러한 기능이 있는 장치를 선택하는 경우 사용자는 훨씬 더 나은 환경을 경험할 수 있습니다.

- Intel vPro-platform 프로세서 또는 AMD Ryzen Pro 프로세서
- 용량이 256GB 이상인 SSD 유형의 부팅 드라이브
- 16GB 이상의 내부 장치 메모리(RAM)
- 최신 대기에 대한 지원
- 디바이스가 보안 코어 PC 유형입니다.
- 커널 DMA 보호 지원
