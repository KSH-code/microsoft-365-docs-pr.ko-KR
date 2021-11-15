---
title: macOS 디바이스를 Microsoft 365 개요에 온보딩(미리 보기)
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
description: 규정 준수 솔루션에 macOS 장치 온보드에 대해 자세히 알아보십시오.
ms.openlocfilehash: fbf29e0d66bf31d058cede69aba9fe0c7814a3a7
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2021
ms.locfileid: "60963254"
---
# <a name="onboard-macos-devices-into-microsoft-365-overview-preview"></a>macOS 디바이스를 Microsoft 365 개요에 온보딩(미리 보기)

MacOS 장치는 Intune 또는 JAMF 2013을 사용하여 Microsoft 365 준수 솔루션에 온보드할 수 Pro. 온보더링 절차는 사용하는 관리 솔루션에 따라 다릅니다. macOS 장치가 끝점용 Microsoft Defender(MDE)에 이미 온보딩된 경우 단계는 더 적습니다. 적합한 [절차에](#next-steps) 대한 링크는 다음 단계를 참조하세요.

**적용 대상:**

- [Microsoft 365 엔드포인트 DLP(데이터 손실 방지)](./endpoint-dlp-learn-about.md)
- [내부자 위험 관리](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)

## <a name="before-you-begin"></a>시작하기 전에

macOS 디바이스(카탈로니아 10.15 이상)에서 끝점 DLP를 시작하기 전에 다음 문서를 익히세요.

- [Microsoft 365 끝점 데이터 손실 방지에 대한 자세한 정보](endpoint-dlp-learn-about.md#learn-about-microsoft-365-endpoint-data-loss-prevention)
- [끝점 데이터 손실 방지 시작](endpoint-dlp-getting-started.md#get-started-with-endpoint-data-loss-prevention)

DLP에 익숙하지 않은 경우 다음 문서도 익숙해야 합니다.

- [데이터 손실 방지에 대해 알아보기](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
- [DLP(데이터 손실 방지) 계획](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp)
- [데이터 손실 방지 정책 참조](dlp-policy-reference.md#data-loss-prevention-policy-reference)

내부자 위험에 익숙하지 않은 경우 다음 문서에 익숙해야 합니다.

 - [내부자 위험 관리](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)
 - [내부자 위험 관리 계획](insider-risk-management-plan.md#plan-for-insider-risk-management)

MacOS 장치는 Intune 또는 JAMF 2013을 통해 이미 Pro.
 
- Intune에 등록하기 위해 배포 가이드: Microsoft Intune [MacOS](/mem/intune/fundamentals/deployment-guide-platform-macos) 장치 관리 및 mac을 등록을 [Intune 회사 포털.](/mem/intune/user-help/enroll-your-device-in-intune-macos-cp) 
- JAMF 설치에 온보 Pro JAMF Pro 관리자 가이드 및 [JAMF](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/) Pro Mac용 설치 및 구성 [가이드를 참조하세요.](https://www.jamf.com/resources/product-documentation/jamf-pro-installation-guide-for-mac/)
- macOS 장치에 v95+ Edge 브라우저 설치 

## <a name="licensing-guidance"></a>라이선싱 지침

정보 [보호에 Microsoft 365 라이선스 지침을 참조하세요.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business)

## <a name="activities-that-can-be-restricted-on-macos"></a>macOS에서 제한할 수 있는 활동 

macOS 장치가 Microsoft 365 준수 솔루션에 온보드된 후 DLP(데이터 손실 방지) 정책을 사용하여 이러한 작업을 모니터링하고 제한할 수 있습니다.

**USB 이동식** 미디어에 복사 - 적용 시 이 작업은 보호된 파일의 복사 또는 이동을 끝점 장치에서 USB 이동식 미디어로 차단, 경고 또는 감사합니다. 

**네트워크 공유로** 복사 - 이 작업이 적용될 경우 이 작업은 끝점 장치에서 네트워크 공유로 보호된 파일의 복사 또는 이동을 차단, 경고 또는 감사합니다. 

**인쇄** – 적용 시 이 작업은 끝점 장치에서 보호된 파일을 인쇄할 때 차단, 경고 또는 감사를 차단합니다. 

**클립보드에** 복사 - 적용 시 이 작업은 끝점 장치의 클립보드에 복사되는 보호된 파일의 데이터를 차단, 경고 또는 감사합니다. 

**업로드** 클라우드로 설정 - 이 작업은 보호된 파일이 전역 설정의 허용/허용되지 않는 도메인 목록에 따라 클라우드 서비스에 업로드되는 것을 방지하거나 허용할 때 차단, 경고 또는 감사를 차단합니다. 이 작업을 경고 또는 차단으로 설정하면 전역 설정의 허용되지 않은 브라우저 목록에 정의되어 있는 다른 브라우저가 파일에 액세스할 수 없습니다. 

**허용되지** 않는 앱에서 액세스 - 이 작업을 적용하면 전역 설정에 정의된 허용되지 않은 앱 목록에 있는 응용 프로그램이 끝점 장치에서 보호된 파일에 액세스할 수 없습니다. 예제 시나리오 

## <a name="onboarding-devices-into-device-management"></a>장치 관리에 장치 온보딩

장치에서 중요한 항목을 모니터링하고 보호하려면 장치 모니터링을 사용하도록 설정하고 엔드포인트를 온보딩해야 합니다. 이러한 작업은 모두 Microsoft 365 규정 준수 포털에서 수행됩니다.

아직 온보딩되지 않은 장치를 온보딩하려는 경우 적절한 스크립트를 다운로드하여 해당 장치에 배포합니다. <!--Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).-->

<!--If you already have devices onboarded into [Microsoft Defender for Endpoint](/windows/security/threat-protection/), they will already appear in the managed devices list.-->

1. Microsoft 규정 [준수 센터 설정](https://compliance.microsoft.com) **열고** 장치 모니터링 **사용 을 선택합니다.**

   > [!NOTE]
   > 일반적으로 장치 온보딩이 활성화되는 데 60초 정도 소요되지만, Microsoft 지원에 연락하기 전에 30분까지 기다려보세요.

2. 규정 준수 센터 설정 페이지를 열고 **장치 온보딩** 을 선택합니다.

   > [!div class="mx-imgBorder"]
   > ![장치 관리를 사용하도록 설정.](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

## <a name="next-steps"></a>다음 단계

DLP 센서 원격 분석 Microsoft 365 데이터 손실 방지 정책을 적용하려면 장치를 Microsoft 365 준수 솔루션으로 온보드해야 합니다. 

항목 | 설명
:---|:---
|[Intune을 사용하여 macOS 장치를 Microsoft 365 규정 준수 솔루션에 온보딩 및 오프보딩(미리 보기)](device-onboarding-offboarding-macos-intune.md#onboard-and-offboard-macos-devices-into-microsoft-365-compliance-solutions-using-intune-preview)|Intune을 통해 관리되는 macOS 디바이스의 경우
|[엔드포인트용 Microsoft Defender 고객을 위한 Intune을 사용하여 macOS 디바이스를 규정 준수 솔루션에 온보딩 및 오프보딩(미리 보기)](device-onboarding-offboarding-macos-intune-mde.md#onboard-and-offboard-macos-devices-into-compliance-solutions-using-intune-for-microsoft-defender-for-endpoint-customers-preview) |Intune을 통해 관리되고 MDE(엔드포인트용 Microsoft Defender)가 배포된 macOS 장치의 경우
|[JAMF Pro를 사용하여 macOS 장치를 Microsoft 365 규정 준수 솔루션에 온보딩 및 오프보딩(미리 보기)](device-onboarding-offboarding-macos-jamfpro.md#onboard-and-offboard-macos-devices-into-microsoft-365-compliance-solutions-using-jamf-pro-preview) | JAMF Pro를 통해 관리되는 macOS 장치의 경우
|[엔드포인트용 Microsoft Defender 고객을 위한 JAMF Pro를 사용하여 macOS 디바이스를 규정 준수 솔루션에 온보딩 및 오프보딩(미리 보기)](device-onboarding-offboarding-macos-jamfpro-mde.md#onboard-and-offboard-macos-devices-into-compliance-solutions-using-jamf-pro-for-microsoft-defender-for-endpoint-customers-preview)|JAMF Pro를 통해 관리되고 MDE(엔드포인트용 Microsoft Defender)가 배포된 macOS 장치의 경우


## <a name="related-topics"></a>관련 주제

- [엔드포인트 데이터 손실 방지 사용](endpoint-dlp-using.md#using-endpoint-data-loss-prevention)
- [Microsoft 앱의 DLP 정책 팁 지원 매트릭스](dlp-policy-tips-reference.md#support-matrix-for-dlp-policy-tips-across-microsoft-apps)
