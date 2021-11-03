---
title: Endpoint 고객용 Microsoft Defender용 Microsoft Intune 사용하여 준수 솔루션에 macOS 장치 온보딩 및 오프보딩(미리 보기)
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
description: MDE 고객을 위한 Microsoft 365(미리 보기)를 사용하여 macOS 장치를 Microsoft Intune 방법에 대해 자세히 알아보십시오.
ms.openlocfilehash: 94664f0d57f1b702484e27c62f9e80339e04e105
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2021
ms.locfileid: "60701376"
---
# <a name="onboard-and-offboard-macos-devices-into-compliance-solutions-using-intune-for-microsoft-defender-for-endpoint-customers-preview"></a>끝점 고객을 위한 Microsoft Defender용 Intune을 사용하여 MacOS 장치를 준수 솔루션에 온보딩 및 오프보드(미리 보기)

> [!IMPORTANT]
> MacOS  장치에 끝점용 Microsoft Defender(MDE)를 배포한 경우 이 절차를 사용합니다.

## <a name="get-registered"></a>등록

이 기능에 액세스하려면 Microsoft에 테넌트를 등록해야 합니다. macOS [지원에 등록을 Microsoft 365 참조.](https://aka.ms/Ignite2021DLP)

**적용 대상:**

- MDE가 macOS 장치에 배포된 고객.
- [Microsoft 365 끝점 DLP(데이터 손실 방지)](./endpoint-dlp-learn-about.md)
- [내부자 위험 관리](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)


## <a name="before-you-begin"></a>시작하기 전에

- macOS 장치가 [Intune에](/mem/intune/fundamentals/deployment-guide-platform-macos) 등록되어 있으며 앱 앱에 [회사 포털 합니다.](/mem/intune/user-help/enroll-your-device-in-intune-macos-cp) 
- 보안 센터에 액세스할 [수 Microsoft Endpoint Manager 있는지 확인](https://endpoint.microsoft.com/#home)
- 이는 macOS 버전 카탈로니아 10.15 이상을 지원
- macOS 장치에 v95+ Edge 브라우저 설치 

## <a name="onboard-macos-devices-into-microsoft-365-compliance-solutions-using-microsoft-intune"></a>macOS 장치를 Microsoft 365 규정 준수 솔루션에 온보드 Microsoft Intune

MDE가 이미 배포된 경우 다음 단계를 사용하여 MacOS 장치를 준수 솔루션에 온보드합니다.

1. 이 절차를 수행하려면 이러한 파일이 필요합니다.

|필요한 파일 |source |
|---------|---------|
|접근성 |[accessibility.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/accessibility.mobileconfig)|
전체 디스크 액세스     |[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)|

> [!TIP]
> *.mobileconfig* 파일을 개별적으로 또는 다음이 포함된 결합된 [단일 파일로](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig) 다운로드할 수 있습니다.
> - accessibility.mobileconfig
> - fulldisk.mobileconfig
> 
>
>이러한 개별 파일이 업데이트되는 경우 결합된 파일을 다시 다운로드하거나 업데이트된 단일 파일을 개별적으로 다운로드해야 합니다.

### <a name="create-system-configuration-profiles"></a>시스템 구성 프로필 만들기

1. 디바이스 **Microsoft Endpoint Manager 프로필**  >    >  **센터 를 열 수 있습니다.**

1. Choose: **Create profile**. 

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

1. 장치 **구성**  >  **프로필을** 열면 생성된 프로필이 표시됩니다.

1. 구성 **프로필 페이지에서** 방금 만든 프로필(이 예의 *접근성formacOS)을* 선택하고 장치 상태를 선택하면 장치 목록과 구성 프로필의 배포 상태를 확인합니다. 

### <a name="update-configuration-profiles"></a>구성 프로필 업데이트

1. **fulldisk.mobileconfig** 파일로 기존 전체 디스크 액세스 프로필을 업데이트합니다.

1. 다음 값으로 MDE 기본 설정 프로필 업데이트
   
```xml
<key>features</key>
<dict>
    <key>systemExtensions</key>
    <string>enabled</string>
    <key>dataLossPrevention</key>
    <string>enabled</string>
</dict>
```

## <a name="offboard-macos-devices-using-intune"></a>Intune을 사용하여 macOS 장치 오프보드

> [!IMPORTANT]
> 오프보더링을 통해 디바이스가 포털에 센서 데이터 전송을 중지하지만, 디바이스에서 전송한 모든 경고에 대한 참조를 포함하여 장치의 데이터는 최대 6개월 동안 보존됩니다.

1. Microsoft Endpoint Manager **센터에서** 장치 구성 프로필을 열면 생성된  >  프로필이 표시됩니다.

2. 구성 **프로필 페이지에서** MDE 기본 설정 프로필을 선택합니다.

1. 다음 설정을 제거합니다.
   
```xml
<key>features</key>
<dict>
    <key>systemExtensions</key>
    <string>enabled</string>
    <key>dataLossPrevention</key>
    <string>enabled</string>
</dict>
```
3. **를 저장합니다.**