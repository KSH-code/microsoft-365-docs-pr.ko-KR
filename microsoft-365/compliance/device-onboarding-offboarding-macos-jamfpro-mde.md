---
title: 엔드포인트용 Microsoft Defender 고객을 위한 JAMF Pro를 사용하여 macOS 디바이스를 규정 준수 솔루션에 온보딩 및 오프보딩(미리 보기)
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
description: Microsoft Defender for Endpoint 고객을 위한 JAMF Pro 사용하여 macOS 장치를 Microsoft 365 준수 솔루션에 온보딩하고 오프보딩하는 방법(미리 보기)
ms.openlocfilehash: 31ff2803a1180d7a43b462f3a78cc52c894f23a6
ms.sourcegitcommit: 27bf284b3bfe334eb98847798734625bd2ffafb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2021
ms.locfileid: "60792319"
---
# <a name="onboard-and-offboard-macos-devices-into-compliance-solutions-using-jamf-pro-for-microsoft-defender-for-endpoint-customers-preview"></a>엔드포인트용 Microsoft Defender 고객을 위한 JAMF Pro를 사용하여 macOS 디바이스를 규정 준수 솔루션에 온보딩 및 오프보딩(미리 보기)

JAMF 디바이스를 사용하여 Pro 규정 준수 솔루션에 macOS 장치를 Microsoft 365 수 있습니다.

> [!IMPORTANT]
> MacOS  장치에 끝점용 Microsoft Defender(MDE)를 배포한 경우 이 절차를 사용합니다.

## <a name="get-registered"></a>등록하기

이 기능에 액세스하려면 Microsoft에 테넌트를 등록해야 합니다. macOS [지원에 등록을 Microsoft 365 참조.](https://aka.ms/EndpointDLPIgnite21-Previews)

**적용 대상:**

- MDE가 macOS 장치에 배포된 고객.
- [Microsoft 365 끝점 DLP(데이터 손실 방지)](./endpoint-dlp-learn-about.md)
- [내부자 위험 관리](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)


## <a name="before-you-begin"></a>시작하기 전에

- [macOS 장치가 Azure AD에 가입된지 확인](https://docs.jamf.com/10.30.0/jamf-pro/administrator-guide/Azure_AD_Integration.html)
- [MACOS 장치가 JAMF pro를 통해 관리되고 있는지 확인](https://www.jamf.com/resources/product-documentation/jamf-pro-installation-guide-for-mac/) 
- macOS 장치에 v95+ Edge 브라우저 설치 

## <a name="onboard-devices-into-microsoft-365-compliance-solutions-using-jamf-pro"></a>JAMF 2013을 Microsoft 365 규정 준수 솔루션에 장치 온보드 Pro

MacOS 장치를 준수 솔루션에 온보드하는 것은 여러 단계 프로세스입니다.

### <a name="download-the-configuration-files"></a>구성 파일 다운로드

1. 이 절차를 수행하려면 이러한 파일이 필요합니다.

|필요한 파일 |source |
|---------|---------|
|접근성 |[accessibility.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/accessibility.mobileconfig)|
전체 디스크 액세스     |[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)|
|MDE 기본 설정 |[schema.json](https://github.com/microsoft/mdatp-xplat/blob/master/macos/schema/schema.json)

> [!TIP]
> *.mobileconfig* 파일을 개별적으로 또는 다음이 포함된 결합된 [단일 파일로](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig) 다운로드할 수 있습니다.
> - accessibility.mobileconfig
> - fulldisk.mobileconfig
>
>이러한 개별 파일이 업데이트되는 경우 결합된 파일을 다시 다운로드하거나 업데이트된 단일 파일을 개별적으로 다운로드해야 합니다.

### <a name="update-the-existing-mde-preference-domain-profile-using-the-jamf-pro-console"></a>JAMF PRO 콘솔을 사용하여 기존 MDE 기본 설정 도메인 프로필 업데이트

1. 방금 schema.xml **schema.json** 파일로 schema.xml 프로필을 업데이트합니다.

1. **MDE 기본 설정 도메인 속성에서 다음** 설정을 선택합니다.
    - 기능 
        - 시스템 확장 사용: - 카탈로나의 네트워크 확장에 `enabled` 필요
        - 데이터 손실 방지 사용: `enabled`

1. 범위 **탭을** 선택합니다.

1. 이 구성 프로필을 배포할 그룹을 선택하십시오.

1. **저장** 을 선택합니다. 

### <a name="update-the-configuration-profile-for-grant-full-disk-access"></a>전체 디스크 액세스 권한 부여에 대한 구성 프로필 업데이트

1. **fulldisk.mobileconfig** 파일로 기존 전체 디스크 액세스 프로필을 업데이트합니다.

1. 업로드 **fulldisk.mobileconfig** 파일을 JAMF에 저장합니다. [JAMF 를 사용하여](https://docs.jamf.com/technical-articles/Deploying_Custom_Configuration_Profiles_Using_Jamf_Pro.html)사용자 지정 구성 프로필 배포를 Pro.

### <a name="grant-accessibility-access-to-dlp"></a>DLP에 대한 접근성 액세스 권한 부여

1. 이전에 다운로드한 accessibility.mobileconfig 파일을 사용 합니다.

1. 업로드 Jamf 를 사용하여 사용자 지정 구성 프로필 배포에 설명된 바와 같이 [JAMF에 Pro.](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)

### <a name="check-the-macos-device"></a>macOS 장치 확인 

1. macOS 장치를 다시 시작합니다.

1. 시스템 **기본 설정 프로필**  >  **을 열 수 있습니다.**

1. 다음이 표시해야 할 수 있습니다.
    - 접근성
    - 전체 디스크 액세스
    - 커널 확장 프로필
    - MAU
    - MDATP 온보더링
    - MDE 기본 설정
    - 관리 프로필
    - 네트워크 필터
    - 알림
    - 시스템 확장 프로필

## <a name="offboard-macos-devices-using-jamf-pro"></a>JAMF 2013을 사용하여 macOS Pro

> [!IMPORTANT]
> 오프보더링을 통해 디바이스가 포털에 센서 데이터 전송을 중지하지만, 디바이스에서 전송한 모든 경고에 대한 참조를 포함하여 장치의 데이터는 최대 6개월 동안 보존됩니다.

MacOS 디바이스를 오프보드하려면 다음 단계를 따르세요.

 1. **MDE 기본 설정 도메인 속성에서** 이러한 설정의 값을 제거합니다.
    - 기능 
        - 시스템 확장 사용
        - 데이터 손실 방지 사용

1. **저장** 을 선택합니다.
