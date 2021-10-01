---
title: 끝점 장치 제어 장치 설치용 Microsoft Defender
description: 이 항목에서는 끝점 장치 제어 장치 설치용 Microsoft Defender에 대한 정보를 제공합니다.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ea7f520fffa7efc7c16a61184f7f5ceb15123978
ms.sourcegitcommit: e5de03d4bd669945fec0d25a3f5eae56f86c9dcc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2021
ms.locfileid: "60043098"
---
# <a name="microsoft-defender-for-endpoint-device-control-device-installation"></a>끝점 장치 제어 장치 설치용 Microsoft Defender 

Microsoft Defender for Endpoint Device Control 이동식 Storage 액세스 제어를 사용하여 다음 작업을 할 수 있습니다.

- 사용자가 특정 장치를 설치하지 못하도록 합니다.
- 사용자가 특정 장치를 설치할 수 있도록 허용하지만 다른 장치는 설치할 수 없습니다.

> [!NOTE]
> 장치 설치와 이동식 저장소 액세스 제어 간의 차이점을 찾으면 [Microsoft Defender for Endpoint Device Control Removable Storage Protection을 참조하세요.](/microsoft-365/security/defender-endpoint/device-control-removable-storage-protection?view=o365-worldwide&preserve-view=true)

|권한|사용 권한|
|---|---|
|Access|장치 설치 |
|작업 모드|허용, 방지 |
|CSP 지원|예|
|GPO 지원|예|
|사용자 기반 지원|아니요|
|컴퓨터 기반 지원|예|

## <a name="prepare-your-endpoints"></a>엔드포인트 준비하기

Server 2022의 Windows 10 장치 Windows 배포합니다.

## <a name="device-properties"></a>장치 속성

다음 장치 속성은 장치 설치 지원에서 지원됩니다.

- 장치 ID 
- 하드웨어 ID 
- 호환되는 ID 
- Device Class 
- '이동식 장치' 장치 유형: 일부 장치는 이동식 장치로 분류될 수 있습니다. 장치가 연결된 디바이스의 드라이버가 이동식으로 표시되면 디바이스는 이동식으로 간주됩니다. 예를 들어 USB 디바이스는 장치가 연결된 USB 허브의 드라이버에 의해 이동식으로 보고됩니다. 자세한 내용은 에서 [장치 설치를 Windows.](/windows/client-management/manage-device-installation-with-group-policy)

## <a name="policies"></a>정책

### <a name="allow-installation-of-devices-that-match-any-of-these-device-ids"></a>이러한 장치 신원과 일치하는 장치 설치 허용

이 정책 설정을 통해 설치가 허용된 장치의 플러그 앤 플레이 하드웨어 WINDOWS 및 호환되는 WINDOWS 수 있습니다. 이 정책 설정은 모든 장치  일치 조건에서 장치 설치 허용 및 금지 정책에 대해 계층적 평가 순서 적용 정책 설정을 사용하도록 설정한 경우만 사용됩니다.

이 정책 설정을 모든 장치  일치 조건 설정에서 장치 설치 허용 및 방지에 대한 계층적 평가 순서 적용 정책 설정과 함께 사용하도록 설정하면 계층 구조에서 같은 계층 또는 상위 계층의 다른 정책 설정으로 인해 해당 설치가 특별히 차단되지 않는 한Windows 플러그 앤 플레이 하드웨어 ID 또는 호환 ID가 생성한 목록에 나타나는 장치를 설치하거나 업데이트할 수 있습니다.  다음과 같은 정책 설정이 있습니다.

- 이러한 장치 신원과 일치하는 디바이스를 설치하지 못하게 합니다.
- 이러한 장치 인스턴스와 일치하는 디바이스를 설치하지 못하게 합니다.

이 **정책** 설정과 함께 모든 장치 일치 조건에서 장치 설치 허용 및 방지 정책에 대해 계층적 평가 순서 적용 정책 설정을 사용하도록 설정하지 않은 경우 특별히 설치를 방지하는 다른 정책 설정이 우선합니다. 

> [!NOTE]
> 다른 **정책 설정에서** 설명하지 않는 장치 설치 방지 정책  설정이 지원되는 대상 버전에 대한 모든 장치 일치 조건 조건 정책 설정에서 장치 설치 허용 및 금지에 대한 계층적 평가 순서 적용 정책 설정으로 Windows 10 변경되었습니다. 가능한 경우 모든 장치  일치 조건 정책 설정에서 장치 설치 허용 및 금지 정책에 대해 계층적 평가 순서 적용을 사용하는 것이 좋습니다.

### <a name="allow-installation-of-devices-that-match-any-of-these-device-instance-ids"></a>이러한 장치 인스턴스와 일치하는 장치 설치 허용 

이 정책 설정을 통해 설치가 허용된 디바이스에 대한 플러그 앤 플레이 장치 Windows 지정할 수 있습니다. 이 정책 설정은 모든 장치  일치 조건에서 장치 설치 허용 및 금지 정책에 대해 계층적 평가 순서 적용 정책 설정을 사용하도록 설정한 경우만 사용됩니다. 

이 정책 설정을 모든 장치  일치 조건 정책 설정에서 허용 및 차단에 대한 계층적 평가 순서 적용 정책 설정과 함께 사용하도록 설정하면 계층 구조에서 같은 계층 또는 상위 계층의 다른 정책 설정으로 인해 해당 설치가 특별히 차단되지 않는 한Windows 플러그 앤 플레이 장치 인스턴스 ID가 생성한 목록에 나타나는 모든 장치를 설치하거나 업데이트할 수 있습니다.  다음과 같은 정책 설정이 있습니다.

- 이러한 장치 인스턴스와 일치하는 장치 설치 방지 

이 **정책** 설정과 함께 모든 장치 일치 조건에서 장치 설치 허용 및 방지 정책에 대해 계층적 평가 순서 적용 정책 설정을 사용하도록 설정하지 않은 경우 특별히 설치를 방지하는 다른 정책 설정이 우선합니다. 

### <a name="allow-installation-of-devices-using-drivers-that-match-these-device-setup-classes"></a>이러한 장치 설정 클래스와 일치하는 드라이버를 사용하여 디바이스 설치 허용 

이 정책 설정을 사용하면 설치가 허용된 드라이버 패키지에 대한 장치 설정 클래스 GUID(globally unique identifiers) Windows 수 있습니다. 이 정책 설정은 모든 장치  일치 조건에서 장치 설치 허용 및 금지 정책에 대해 계층적 평가 순서 적용 정책 설정을 사용하도록 설정한 경우만 사용됩니다.

이 정책 설정을 모든 장치  일치 조건 설정에서 허용 및 방지에 대한 계층적 평가 순서 적용 정책 설정과 함께 사용하도록 설정하면 계층 구조에서 같은 계층 또는 상위 계층의 다른 정책 설정으로 인해 해당 설치가 특별히 차단되지 않는 한 Windows 설치 클래스 GUID가 생성한 목록에 해당 장치 설정 클래스 GUID가 나타나는 드라이버 패키지를 설치하거나 업데이트할 수 있습니다.  다음과 같은 정책 설정이 있습니다. 

- 이러한 장치 클래스에 대한 장치 설치 방지 
- 이러한 장치 ID와 일치하는 장치 설치 방지 
- 이러한 장치 인스턴스와 일치하는 장치 설치 방지 

이 **정책** 설정과 함께 모든 장치 일치 조건에서 장치 설치 허용 및 방지 정책에 대해 계층적 평가 순서 적용 정책 설정을 사용하도록 설정하지 않은 경우 특별히 설치를 방지하는 다른 정책 설정이 우선합니다.

### <a name="apply-layered-order-of-evaluation-for-allow-and-prevent-device-installation-policies-across-all-device-match-criteria"></a>모든 장치 일치 조건에서 장치 설치 허용 및 방지 정책에 대해 계층적 평가 순서 적용 

이 정책 설정은 주어진 장치에 대해 두 개 이상의 설치 정책 설정을 적용할 수 있는 경우 허용 및 금지 정책 설정이 적용되는 평가 순서를 변경합니다. 보다 구체적인 일치 조건이 덜 구체적인 일치 조건을 겹치는 계층 구조에 따라 겹치는 장치 일치 조건이 적용되도록 이 정책 설정을 사용합니다. 장치 일치 조건을 지정하는 정책 설정에 대한 계층적 평가 순서는 다음과 같습니다.

**이동식 > 장치 설정 클래스 > 장치 > 인스턴스 > 수 있습니다.**

#### <a name="device-instance-ids"></a>장치 인스턴스 ID 

1. 이러한 장치 인스턴스와 일치하는 드라이버를 사용하여 디바이스를 설치하지 못하게 합니다.
2. 이러한 장치 인스턴스와 일치하는 드라이버를 사용하여 디바이스 설치를 허용합니다.

#### <a name="device-ids"></a>장치 ID 

1. 이러한 장치 ID와 일치하는 드라이버를 사용하여 디바이스를 설치하지 못하게 합니다.
2. 이러한 장치 ID와 일치하는 드라이버를 사용하여 디바이스 설치를 허용합니다.

#### <a name="device-setup-class"></a>디바이스 설정 클래스 

1. 이러한 장치 설정 클래스와 일치하는 드라이버를 사용하여 디바이스를 설치하지 못하게 합니다.
2. 이러한 장치 설정 클래스와 일치하는 드라이버를 사용하여 디바이스 설치를 허용합니다.

#### <a name="removable-devices"></a>이동식 장치 

이동식 장치 설치 방지 

> [!NOTE]
> 이 정책 설정은 다른 정책 설정 정책 설정에 설명되지 않은 장치의 설치 방지 정책 설정보다 더 **세부적인 제어를** 제공합니다. 이러한 충돌하는 정책 설정을 동시에 사용하도록 설정하면 모든 장치 일치 조건에서 장치 설치 허용 및 금지 정책에 대해 계층적 평가 순서 적용 정책 설정이 사용하도록 설정되고 다른 정책 설정은 무시됩니다.  

### <a name="prevent-installation-of-devices-that-match-any-of-these-device-ids"></a>이러한 장치 신원과 일치하는 장치 설치 방지 

이 정책 설정을 통해 설치가 금지된 장치의 플러그 앤 플레이 하드웨어 WINDOWS 및 호환되는 WINDOWS 수 있습니다. 기본적으로 이 정책 설정은 장치 설치를 허용하는 다른 정책 Windows 우선합니다.

> [!NOTE]
> 이러한 장치 인스턴스 **IDs** 정책 설정과 일치하는 디바이스의 설치 허용 정책 설정을 적용 가능한 장치에  대해 이 정책 설정을 겹치지 않도록 설정하려면 모든 장치 일치 조건 정책 설정에서 장치 설치 허용 및 금지에 대해 계층적 평가 순서 적용을 사용하도록 설정하세요. 

이 정책 설정을 사용하면 Windows 목록에 하드웨어 ID 또는 호환 ID가 나타나는 장치를 설치할 수 없습니다. 원격 데스크톱 서버에서 이 정책 설정을 사용하도록 설정하면 정책 설정은 지정한 장치를 원격 데스크톱 클라이언트에서 원격 데스크톱 서버로 리디렉션하는 데 영향을 미치게 됩니다.

이 정책 설정을 사용하지 않도록 설정하거나 구성하지 않는 경우 다른 정책 설정에 의해 허용되거나 금지된 장치로 장치를 설치 및 업데이트할 수 있습니다. 

### <a name="prevent-installation-of-devices-that-match-any-of-these-device-instance-ids"></a>이러한 장치 인스턴스와 일치하는 장치 설치 방지 

이 정책 설정을 사용하면 설치가 금지된 장치의 플러그 앤 플레이 장치 인스턴스 WINDOWS 지정할 수 있습니다. 이 정책 설정은 장치 설치를 허용하는 Windows 설정보다 우선합니다. 

이 정책 설정을 사용하면 Windows 목록에 해당 장치 인스턴스 ID가 나타나는 장치를 설치할 수 없습니다. 원격 데스크톱 서버에서 이 정책 설정을 사용하도록 설정하면 정책 설정은 지정한 장치를 원격 데스크톱 클라이언트에서 원격 데스크톱 서버로 리디렉션하는 데 영향을 미치게 됩니다. 

이 정책 설정을 사용하지 않도록 설정하거나 구성하지 않는 경우 다른 정책 설정에 의해 허용되거나 금지된 장치로 장치를 설치 및 업데이트할 수 있습니다. 

### <a name="prevent-installation-of-devices-using-drivers-that-match-these-device-setup-classes"></a>이러한 장치 설정 클래스와 일치하는 드라이버를 사용하여 디바이스 설치 방지 

이 정책 설정을 사용하면 설치가 금지된 드라이버 패키지의 장치 설정 클래스 GUID(Globally Unique Identifiers) 목록을 Windows 수 있습니다. 기본적으로 이 정책 설정은 장치 설치를 허용하는 다른 정책 Windows 우선합니다.

> [!NOTE]
> 이러한 장치와 일치하는 장치의 설치 허용 및 이러한 장치 인스턴스 **IDs** 정책 설정 중 일치하는 장치의 설치 허용 정책 설정이 해당 장치에  대해 이 정책 설정을 능가하려면 모든 장치 일치 조건 정책 설정에서 장치 설치 허용 및 금지에 대한 평가 계층적 평가 순서 적용을 사용하도록 설정하세요. 

이 정책 설정을 사용하면 Windows 설치 클래스 GUID가 생성한 목록에 나타나는 드라이버 패키지를 설치하거나 업데이트할 수 없습니다. 원격 데스크톱 서버에서 이 정책 설정을 사용하도록 설정하면 정책 설정은 지정한 장치를 원격 데스크톱 클라이언트에서 원격 데스크톱 서버로 리디렉션하는 데 영향을 미치게 됩니다. 

이 정책 설정을 사용하지 않도록 설정하거나 구성하지 않은 경우 다른 정책 Windows 허용 또는 금지된 장치 설치 및 업데이트가 가능합니다. 

### <a name="prevent-installation-of-removable-devices"></a>이동식 장치 설치 방지 

이 정책 설정을 통해 사용자가 이동식 Windows 설치하지 못하도록 할 수 있습니다. 장치가 연결된 디바이스의 드라이버가 이동식으로 표시되면 디바이스는 이동식으로 간주됩니다. 예를 들어 USB(유니버설 직렬 버스) 디바이스는 디바이스가 연결된 USB 허브에 대한 드라이버에 의해 이동식으로 보고됩니다. 기본적으로 이 정책 설정은 장치 설치를 허용하는 다른 정책 Windows 우선합니다. 

> [!NOTE]
> 이러한 장치 설정 클래스와 일치하는 드라이버를 사용하여 디바이스 설치 **허용,** 이러한 장치 신원과 일치하는 장치 설치 허용 및 이러한 장치 인스턴스 **ID** 중 일치하는 장치의 설치 허용 정책  설정이 해당 장치에 대해 이 정책 설정을 능가하도록 허용 정책 설정을 사용하도록 설정하려면 모든 장치 일치 조건 정책 설정에서 장치 설치 허용 및 차단에 대해 계층형 평가 순서 적용 정책 설정을 사용하도록 설정하세요.

이 정책 설정을 사용하면 Windows 장치를 설치할 수 없습니다. 기존 이동식 장치는 드라이버를 업데이트할 수 없습니다. 원격 데스크톱 서버에서 이 정책 설정을 사용하도록 설정하면 정책 설정은 원격 데스크톱 클라이언트에서 원격 데스크톱 서버로 이동식 장치를 리디렉션하는 데 영향을 미치게 됩니다.

이 정책 설정을 사용하지 않도록 설정하거나 구성하지 않는 경우 다른 정책 Windows 허용되거나 금지된 이동식 장치에 대한 드라이버 패키지를 설치하고 업데이트할 수 있습니다.

## <a name="common-removable-storage-access-control-scenarios"></a>일반적인 이동식 Storage 액세스 제어 시나리오

Microsoft Defender for Endpoint 이동식 Storage 액세스 제어에 익숙해지기 위해 따라야 할 몇 가지 일반적인 시나리오를 준비했습니다.

### <a name="scenario-1-prevent-installation-of-all-usb-devices-while-allowing-an-installation-of-only-an-authorized-usb-thumb-drive"></a>시나리오 1: 권한이 부여된 USB 썸 드라이브만 설치할 수 있도록 허용하면서 모든 USB 장치를 설치하지 못하게 합니다. 

이 시나리오에서는 다음과 같은 정책이 사용됩니다.

- 이러한 장치 설정 클래스와 일치하는 드라이버를 사용하여 디바이스를 설치하지 못하게 합니다.
- 모든 장치 일치 조건에서 장치 설치 허용 및 금지 정책에 대해 계층적 평가 순서를 적용합니다.
- 이러한 장치 인스턴스와 일치하는 디바이스를 설치하도록 허용하거나 이러한 장치 ID 중 일치하는 디바이스를 설치 허용합니다.

#### <a name="deploying-and-managing-policy-via-intune"></a>Intune을 통해 정책 배포 및 관리 

장치 설치 기능을 사용하면 Intune을 통해 디바이스에 정책을 적용할 수 있습니다.

#### <a name="licensing"></a>라이선싱 

장치 설치를 시작하기 전에 장치 [구독을 Microsoft 365 합니다.](https://www.microsoft.com/en-in/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2) 장치 설치에 액세스하고 사용하려면 설치 권한이 Microsoft 365 E3.

#### <a name="permission"></a>사용 권한 

Intune에서 정책 배포의 경우 계정에 장치 구성 프로필을 생성, 편집, 업데이트 또는 삭제할 수 있는 권한이 있어야 합니다. 다음 사용 권한으로 사용자 지정 역할을 만들거나 기본 제공 역할을 사용할 수 있습니다.  

- 정책 및 프로필 관리자 역할
- 또는 장치 구성 프로필에 대해 보고서 만들기/편집/업데이트/읽기/삭제/보기 권한이 설정되어 있는 사용자 지정 역할
- 또는 전역 관리자

#### <a name="deploying-policy"></a>정책 배포 

In Microsoft Endpoint Manager [https://endpoint.microsoft.com/](https://endpoint.microsoft.com/)  

1. 이러한 장치 설정 클래스와 일치하는 드라이버를 사용하여 디바이스 **설치 방지를 구성합니다.**

    - 끝점 보안 > 공격 표면 감소를 > 정책 > 플랫폼 만들기: Windows 10(이상) &: 장치 제어.
    
      :::image type="content" source="../../media/devicepolicy-editprofile.png" alt-text="프로필 편집":::
    
2. USB, 장치를 연결하면 다음 오류 메시지가 표시됩니다.

      :::image type="content" source="../../media/devicepolicy-errormsg.png" alt-text="오류 메시지":::

3. 모든 장치 일치 조건에서 장치 설치 정책 허용 및 금지에 대해 계층적 평가 순서 **적용을 사용하도록 설정**

    - **지금은 OMA-URI만 지원:** 장치 > 구성 프로필> 프로필 > 플랫폼 만들기: Windows 10(이상) & 프로필: 사용자 지정
    
      :::image type="content" source="../../media/devicepolicy-editrow.png" alt-text="행 편집":::

4. 허용된 USB 인스턴스 ID 사용 및 추가 - 이러한 장치 ID와 일치하는 장치의 설치를 **허용합니다.**

    - 1단계 장치 컨트롤 프로필 업데이트
    
      :::image type="content" source="../../media/devicepolicy-devicecontrol.png" alt-text="devicecontrol":::
       
    Adding PCI\CC_0C03; PCI\CC_0C0330; PCI\VEN_8086; PNP0CA1; PNP0CA1 &HOST; USB\ROOT_HUB30; USB\ROOT_HUB20; USB\USB20_HUB 화면 캡처의 경우 단일 하드웨어 ID만 사용하도록 설정하여 단일 USB 미리 보기 드라이브를 사용하도록 설정하는 것만으로는 충분하지 않습니다. 대상 장치 앞에 있는 모든 USB 장치도 차단(허용)하지 않도록 합니다. 장치 관리자를 열고 보기를 '연결로 장치'로 변경하여 장치가 PnP 트리에 설치되는 방법을 볼 수 있습니다. 이 경우 대상 USB 썸 드라이브도 허용할 수 있도록 다음 장치를 허용해야 합니다. 

    - "Intel(R) USB 3.0 eXtensible Host Controller – 1.0(Microsoft)" -> PCI\CC_0C03 
    - "USB 루트 허브(USB 3.0)" -> USB\ROOT_HUB30 
    - "일반 USB 허브" -> USB\USB20_HUB

    :::image type="content" source="../../media/devicepolicy-devicemgr.png" alt-text="장치 컨트롤":::

    > [!NOTE]
    > 시스템의 일부 디바이스는 시스템에 설치를 정의하기 위한 몇 가지 연결 계층을 습니다. USB 썸 드라이브는 이러한 장치입니다. 따라서 시스템에서 차단하거나 허용할 경우 각 디바이스에 대한 연결 경로를 이해하는 것이 중요합니다. 시스템에서 일반적으로 사용하며 이러한 경우 "허용 목록"을 빌드하기 위한 좋은 시작을 제공할 수 있는 몇 가지 일반 장치 ID가 있습니다. 다음은 한 가지 예입니다(모든 USB에 대해 항상 동일하지는 않습니다. 장치 관리자를 통해 관리하려는 장치의 PnP 트리를 이해해야 합니다.
    >
    > PCI\CC_0C03; PCI\CC_0C0330; PCI\VEN_8086; PNP0CA1; PNP0CA1&HOST(호스트 컨트롤러용)/ USB\ROOT_HUB30; USB\ROOT_HUB20(USB 루트 허브용)/ USB\USB20_HUB(일반 USB 허브용)/ 
    >
    > 특히 데스크톱 컴퓨터의 경우 키보드와 마우스가 위의 목록에서 연결되는 모든 USB 장치를 나열하는 것이 중요합니다. 이렇게 하지 못하면 사용자가 HID 장치를 통해 컴퓨터 액세스가 차단될 수 있습니다. 
    >
    > PC 제조업체마다 PnP 트리에 USB 장치를 중첩하는 다른 방법이 있는 경우도 있지만 일반적으로 이 방법을 사용하는 것이 일반적입니다. 

5. 허용된 USB를 다시 연결합니다. 이제 허용 및 사용 가능으로 표시 됩니다.

    :::image type="content" source="../../media/devicepolicy-removedrive.png" alt-text="드라이브 제거":::

#### <a name="deploying-and-managing-policy-via-group-policy"></a>그룹 정책을 통해 정책 배포 및 관리

장치 설치 기능을 사용하면 그룹 정책을 통해 정책을 적용할 수 있습니다.

#### <a name="licensing"></a>라이선싱

장치 설치에 액세스하고 사용하려면 E3에 Windows 합니다.

#### <a name="deploying-policy"></a>정책 배포

배포 세부 정보는 Manage [Device Installation with Group Policy (Windows 10) - Windows Client에서 찾을 수 있습니다.](/windows/client-management/manage-device-installation-with-group-policy)

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender에서 장치 Storage 이동식 액세스 제어 데이터 보기

보안 [Microsoft 365](https://sip.security.microsoft.com/homepage) 포털에는 장치 제어 장치 설치에 의해 차단된 이동식 저장소가 표시됩니다. Microsoft 365 보안에 액세스하려면 다음 구독이 있어야 합니다.

- Microsoft 365 E5 보고용 보고서

```kusto
//events triggered by Device Installation policies 
DeviceEvents 
| where ActionType == "PnpDeviceBlocked" or ActionType == "PnpDeviceAllowed" 
| extend parsed=parse_json(AdditionalFields) 
| extend MediaClassGuid = tostring(parsed.ClassGuid)  
| extend MediaInstanceId = tostring(parsed.DeviceInstanceId) 
| extend MediaDeviceId = tostring(parsed.MatchingDeviceId) 
| project Timestamp , DeviceId, DeviceName, ActionType, MediaClassGuid, MediaDeviceId, MediaInstanceId, AdditionalFields 
| order by Timestamp desc 
```

:::image type="content" source="../../media/block-removable-storage2.png" alt-text="블록 저장소":::

## <a name="frequently-asked-questions"></a>자주 묻는 질문

### <a name="how-can-i-know-whether-the-target-machine-gets-the-deployed-policy"></a>대상 컴퓨터의 배포된 정책을 받을지 여부를 어떻게 알 수 있나요? 
다음 쿼리를 사용하여 보안 포털에서 맬웨어 방지 클라이언트 버전을 Microsoft 365 있습니다.

```kusto
//check whether the Device installation policy has been deployed to the target machine, event only when modification happens   
DeviceRegistryEvents 
| where RegistryKey contains "HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows\\DeviceInstall\\" 
| order by Timestamp desc
```

## <a name="why-the-allow-policy-doesnt-work"></a>허용 정책이 작동하지 않는 이유는 무엇입니까?
단일 하드웨어 ID만 사용하도록 설정하여 단일 USB 미리 보기 드라이브를 사용하도록 설정하는 것만으로는 충분하지 않습니다. 대상 장치 앞에 있는 모든 USB 장치도 차단되지 않도록 합니다(허용).

:::image type="content" source="../../media/devicemgrscrnshot.png" alt-text="장치 설치 FAQ":::

