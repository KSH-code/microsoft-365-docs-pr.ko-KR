---
title: JAMF 2013을 사용하여 macOS 장치를 Microsoft 365 준수 솔루션에 Pro(미리 보기)
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
description: JAMF 2013(미리 보기)을 사용하여 macOS 장치를 Microsoft 365 규정 준수 솔루션에 Pro 방법 확인
ms.openlocfilehash: 5335ceb47475a633e8f7ba000f8690ca3b9b8b6c
ms.sourcegitcommit: 27bf284b3bfe334eb98847798734625bd2ffafb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2021
ms.locfileid: "60792511"
---
# <a name="onboard-and-offboard-macos-devices-into-microsoft-365-compliance-solutions-using-jamf-pro-preview"></a>JAMF 2013을 사용하여 macOS 장치를 Microsoft 365 준수 솔루션에 Pro(미리 보기)

JAMF 디바이스를 Pro 끝점 데이터 손실 방지와 같은 Microsoft 365 규정 준수 솔루션에 macOS 장치를 온보드할 수 있습니다.

> [!IMPORTANT]
> MacOS 장치에  끝점용 Microsoft Defender(MDE)가 배포되지 않은 경우 이 절차를 사용합니다.

## <a name="get-registered"></a>등록하기

이 기능에 액세스하려면 Microsoft에 테넌트를 등록해야 합니다. macOS [지원에 등록을 Microsoft 365 참조.](https://aka.ms/EndpointDLPIgnite21-Previews)

**적용 대상:**

- [Microsoft 365 끝점 DLP(데이터 손실 방지)](./endpoint-dlp-learn-about.md)
- [내부자 위험 관리](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)

## <a name="before-you-begin"></a>시작하기 전에

- [macOS 장치가 Azure AD에 가입된지 확인](https://docs.jamf.com/10.30.0/jamf-pro/administrator-guide/Azure_AD_Integration.html)
- [MACOS 장치가 JAMF pro를 통해 관리되고 있는지 확인](https://www.jamf.com/resources/product-documentation/jamf-pro-installation-guide-for-mac/)
- macOS 장치에 v95+ Edge 브라우저 설치 

## <a name="onboard-devices-into-microsoft-365-compliance-solutions-using-jamf-pro"></a>JAMF 2013을 Microsoft 365 규정 준수 솔루션에 장치 온보드 Pro

1. 이 절차를 수행하려면 이러한 파일이 필요합니다.

|필요한 파일 |source |
|---------|---------|
|온보더링 패키지    |준수 포털 **온보더링 패키지,** 파일 이름 *DeviceComplianceOnboarding.plist에서 다운로드* |
|접근성 |[accessibility.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/accessibility.mobileconfig)|
전체 디스크 액세스     |[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)|
|네트워크 필터| [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig)
|시스템 확장 |[sysext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/systext.mobileconfig)
|MDE 기본 설정     |[schema.json](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/data_loss_prevention/schema.json)|
|MAU 기본 설정|[com.microsoft.autoupdate2.plist](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/microsoft_auto_update/com.microsoft.autoupdate2.plist)|
|설치 패키지     |준수 포털 설치 **패키지에서** 다운로드한 파일 이름 *\* wdav.pkg*\* |

> [!TIP]
> *.mobileconfig* 파일을 개별적으로 또는 다음이 포함된 결합된 [단일 파일로](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig) 다운로드할 수 있습니다.
> - accessibility.mobileconfig
> - fulldisk.mobileconfig
> - netfilter.mobileconfig
> - sysext.mobileconfig
>
>이러한 개별 파일이 업데이트되는 경우 결합된 파일을 다시 다운로드하거나 업데이트된 단일 파일을 개별적으로 다운로드해야 합니다.

MacOS 장치를 준수 솔루션에 온보드하는 것은 여러 단계 프로세스입니다.

### <a name="get-the-device-onboarding-package"></a>장치 온보더링 패키지를 얻습니다.

1. 준수 **센터에서** 장치 **설정**  >  **열고** **온보더링 을 선택하세요.**
 
1. **온보더링 프로세스를 시작하려면** 운영 체제 선택에서 **macOS 선택**
 
1. 배포 **방법에 대해 모바일** 장치 **관리/모바일** Microsoft Intune
 
1. **온보더링 패키지 다운로드 선택**
 
1. 장치 온보더링 패키지의 콘텐츠를 추출합니다. **JAMF 폴더에** *DeviceComplainceOnboarding.plist 파일이 표시됩니다.*

### <a name="create-a-jamf-pro-configuration-profile-for-the-onboarding-package"></a>온보 Pro 대한 JAMF 구성 프로필 만들기

1. JAMF 2013에서 새 구성 프로필을 Pro. JAMF Pro [관리자 가이드를 참조하세요.](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/) 다음 값을 사용합니다.
    - 이름: `MDATP onboarding for macOS`
    - 설명: `MDATP EDR onboarding for macOS`
    - 범주: `none`
    - 배포 방법: `install automatically`
    - 수준: `computer level`

2. JAMF Pro 콘솔 > **사용자**& 를 선택하고 를  **추가합니다.** 다음 값을 사용 합니다.
    - 기본 설정 도메인: `com.microsoft.wdav.atp`

3. **업로드를** 선택하고 온보더링 파일 **DeviceComplianceOnboarding.plist 를 선택합니다.**

4. 범위 **탭을** 선택합니다.

5. 대상 컴퓨터를 선택 합니다.

6. **저장** 을 선택합니다.

7. **완료** 를 선택합니다.

### <a name="configure-preference-domain-using-the-jamf-pro-console"></a>JAMF PRO 콘솔을 사용하여 기본 설정 도메인 구성

> [!IMPORTANT]
> 기본 설정 도메인 값으로 ***com.microsoft.wdav** _를 사용해야 합니다. Microsoft Defender는 이 이름과 _ *_com.microsoft.wdav.ext_**를 사용하여 관리되는 설정을 로드합니다.

1. JAMF 2013에서 새 구성 프로필을 Pro. JAMF Pro [관리자 가이드를 참조하세요.](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/) 다음 값을 사용합니다.
    - 이름: `MDATP MDAV configuration settings`
    - 설명: 이 비워 두기
    - 범주: `none`
    - 배포 방법: `install automatically`
    - 수준: `computer level`

1. 응용 **프로그램** & 사용자 설정 탭에서 외부 응용 프로그램을  **선택하고** 추가를 선택하고 기본 설정 도메인에 대한 사용자 지정 **Schema를** 선택합니다. 다음 값을 사용 합니다.
    - 기본 설정 도메인: `com.microsoft.wdav`

1. **Schema 추가를** **선택하고** *업로드.json* 파일을 업로드합니다.

1. **저장** 을 선택합니다.

1. 기본 **설정 도메인 속성에서** 다음 설정을 선택합니다.
    - 기능 
        - 시스템 확장 사용: - 카탈로나의 네트워크 확장에 `enabled` 필요
        - 데이터 손실 방지 사용: `enabled`
    - 바이러스 백신 엔진 > 수동 모드: `true|false` . `true`DLP만 배포하는 경우 사용 `false`DLP 및 MDE(Microsoft Defender for Endpoint)를 배포하는 경우 값을 사용하거나 할당하지 않습니다.

1. 범위 **탭을** 선택합니다.

1. 이 구성 프로필을 배포할 그룹을 선택하십시오.

1. **저장** 을 선택합니다. 


### <a name="create-and-deploy-a-configuration-profile-for-microsoft-autoupdate-mau"></a>MAU(Microsoft 자동 업데이트)에 대한 구성 프로필 만들기 및 배포

1. **com.microsoft.autoupdate2.plist를** Pro JAMF 구성 파일을 만들 수 있습니다. JAMF Pro [관리자 가이드를 참조하세요.](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/) 다음 값을 사용합니다.
    - 이름: `MDATP MDAV MAU settings`
    - 설명: `Microsoft AutoUPdate settings for MDATP for macOS`
    - 범주: `none`
    - 배포 방법: `install automatically`
    - 수준: `computer level`

1. 응용 **프로그램 & 사용자 지정 설정** 및 **업로드** **를 선택하십시오.**

1. 기본 **설정 도메인에서** `com.microsoft.autoupdate2` 를 입력한 다음 을 **업로드.**

1. **com.microsoft.autoupdate2.plist 파일을 선택하십시오.**

1. **저장** 을 선택합니다.

1. 범위 **탭을** 선택합니다.

1. 대상 컴퓨터를 선택 합니다.

1. **저장** 을 선택합니다.

1. **완료** 를 선택합니다.


### <a name="create-and-deploy-a-configuration-profile-for-grant-full-disk-access"></a>전체 디스크 액세스 권한 부여를 위한 구성 프로필 만들기 및 배포

1. **fulldisk.mobileconfig 파일을** 사용 합니다.

1. 업로드 **fulldisk.mobileconfig** 파일을 JAMF에 저장합니다. [JAMF 를 사용하여](https://docs.jamf.com/technical-articles/Deploying_Custom_Configuration_Profiles_Using_Jamf_Pro.html)사용자 지정 구성 프로필 배포를 Pro.

### <a name="create-and-deploy-a-configuration-profile-for-system-extensions"></a>시스템 확장에 대한 구성 프로필 만들기 및 배포

1. JAMF Pro 관리자 가이드의 절차를 사용하여 [JAMF Pro 구성 파일을 만드세요.](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/) 다음 값을 사용합니다.
    - 이름: `MDATP MDAV System Extensions`
    - 설명: `MDATP system extensions`
    - 범주: `none`
    - 배포 방법: `install automatically`
    - 수준: `computer level`

1. 시스템 **범위 프로필에서** 다음 값을 입력합니다.
    - 표시 이름: `Microsoft Corp. System Extensions`
    - 시스템 Extenstion Types: `Allowed System Extensions`
    - 팀 식별자: `UBF8T346G9`
    - 허용되는 시스템 확장: `com.microsoft.wdav.epsext` 및 `com.microsoft.wdav.netext`

1. 범위 **탭을** 선택합니다.

1. 대상 컴퓨터를 선택 합니다.

1. **저장** 을 선택합니다.

1. **완료** 를 선택합니다.

### <a name="configure-network-extension"></a>네트워크 확장 구성

1.  Github에서 다운로드한 **netfilter.mobileconfig**  파일을 사용 합니다.

2.  업로드 Jamf 를 사용하여 사용자 지정 구성 프로필 배포에 설명된 바와 같이 [JAMF에 Pro.](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)

### <a name="grant-accessibility-access-to-dlp"></a>DLP에 대한 접근성 액세스 권한 부여

1. Github에서 다운로드한 **accessibility.mobileconfig** 파일을 사용 합니다.

2.  업로드 Jamf 를 사용하여 사용자 지정 구성 프로필 배포에 설명된 바와 같이 [JAMF에 Pro.](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)

### <a name="get-the-installation-package"></a>설치 패키지를 얻습니다.

1. 준수 **센터에서** 장치 **설정**  >  **열고** **온보더링 을 선택하세요.**
 
1. **온보더링 프로세스를 시작하려면** 운영 체제 선택에서 **macOS 선택**
 
1. 배포 **방법에 대해 모바일** 장치 **관리/모바일** Microsoft Intune
 
1. 설치 **패키지 다운로드 를 선택 합니다.** 이렇게 하면 *wdav.pkg 파일이* 표시됩니다.


### <a name="deploy-the-installation-package"></a>설치 패키지 배포

1. 파일을 저장한 위치로 `wdav.pkg` 이동합니다.

1. JAMF 대시보드를 Pro 을 하세요.

1. 컴퓨터를 선택하고 맨 위에 있는 기어를 클릭한 다음 컴퓨터 관리 **를 선택합니다.**

1. **패키지에서** **+새 를 선택 합니다.** 다음 세부 정보를 입력합니다.
    - 표시 이름: .pkg 파일을 선택할 때 다시 설정될 것이기 때문에 비워 두십시오.
    - 범주: 없음(기본값)
    - Filname: 파일(이 경우 파일)을 `wdav.pkg` 선택하십시오.

1. 열기 **를 선택.** 설정:
    - **표시 이름**: `Microsoft Endpoint Technology`
    - **매니페스트 파일:** 필요하지 않습니다.
    - **옵션 탭**: 기본값을 그대로 떠날 수 있습니다.
    - **제한 탭**: 기본값 그대로

1. **저장** 을 선택합니다. 그러면 JAMF 2013에 패키지가 Pro.

1. 정책 **페이지를 열** 수 있습니다.

1. **+새로 만들기를 선택하면** 새 정책을 만들 수 있습니다.

1. 다음 값을 입력합니다.
    - **표시 이름:**`MDATP Onboarding200329 v100.86.92 or later`

1. Choose **Recurring Check-in**.

1. **저장** 을 선택합니다.

1. 패키지 **구성**  >  **을 선택 합니다.**

1. **추가** 를 선택합니다.

1. **저장** 을 선택합니다. 

1. 범위 **탭을** 선택합니다.

1. 대상 컴퓨터를 선택합니다.

1. **추가** 를 선택합니다.

1. 셀프 **서비스 를 선택 합니다.**

1. **완료** 를 선택합니다.

### <a name="check-the-macos-device"></a>macOS 장치 확인 

1. macOS 장치를 다시 시작합니다.

1. 시스템 **기본 설정 프로필**  >  **을 열 수 있습니다.**

1. 다음이 표시해야 할 수 있습니다.
    - 접근성
    - 전체 디스크 액세스
    - MAU
    - MDATP 온보더링
    - MDE 기본 설정
    - 관리 프로필
    - 네트워크 필터
    - 시스템 확장 프로필

## <a name="offboard-macos-devices-using-jamf-pro"></a>JAMF 2013을 사용하여 macOS Pro

1. 응용 프로그램 제거(MDE를 사용하지 않는 경우)
    1. JAMF Pro Docs - 패키지 배포 - [JAMF](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/)Pro 관리자 가이드 Jamf Pro 관리자 가이드를 참조하세요.

1. macOS 장치 다시 시작 - 일부 응용 프로그램이 다시 시작될 때까지 인쇄 기능이 손실될 수 있습니다.

> [!IMPORTANT]
> 오프보더링을 통해 디바이스가 포털에 센서 데이터 전송을 중지하지만, 디바이스에서 전송한 모든 경고에 대한 참조를 포함하여 장치의 데이터는 최대 6개월 동안 보존됩니다.

