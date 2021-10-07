---
title: 개인 정보 및 개인 데이터
description: 서비스에서 수집, 저장 및 사용되는 데이터 세부 정보
keywords: GDPR, 보존, 삭제, 저장, 보존, 처리, 보안, 감사
ms.service: m365-md
ms.sitesec: library
author: jaimeo
manager: laurawi
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
audience: Admin, ITPro
ms.localizationpriority: medium
ms.openlocfilehash: 23f74d8ddab72b08e2106c1b7d3de0a3264b4444
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60194264"
---
# <a name="overview"></a>개요

Microsoft Managed Desktop 디바이스를 배포하고 업데이트하도록 설계된 엔터프라이즈 클라우드 고객을 위한 ITaaS(IT-as-a-Service) Windows 서비스입니다. 또한 IT 서비스 관리 및 운영을 제공하며, 보안 및 인시던트 대응을 모니터링하고 사용자 지원을 제공합니다. 이 설명서에서는 데이터 플랫폼 및 데이터 플랫폼에 대한 개인 정보 보호 준수에 대한 추가 세부 정보를 Microsoft Managed Desktop.

## <a name="microsoft-managed-desktop-data-sources-and-purpose"></a>Microsoft Managed Desktop 데이터 원본 및 용도

Microsoft Managed Desktop 엔터프라이즈 고객에게 서비스를 제공하며 다양한 원본의 데이터를 사용하여 고객의 등록된 장치를 적절히 관리합니다. Azure Active Directory, Microsoft Intune, Microsoft Windows 10 및 Microsoft Defender for Endpoint를 비롯한 이러한 소스는 사용자가 관리하는 디바이스를 Microsoft Managed Desktop 제공합니다. 또한 이 서비스는 이러한 Microsoft 서비스 사용하여 ITaaS Microsoft Managed Desktop 기능을 제공할 수 있도록 합니다.

- [Microsoft Windows 10 Enterprise](/windows/windows-10/) - 장치 설정 환경을 관리하고, 다른 서비스에 대한 연결을 관리하고, IT 프로를 위한 운영 지원을 제공합니다.
- [Windows 업데이트](/windows/deployment/update/waas-manage-updates-wufb) - Windows 10 Enterprise 진단 데이터를 사용하여 업데이트에 대한 추가 Windows 10 제공합니다. 
- [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) - 장치 관리 및 데이터 보안을 유지하기 위한 것입니다.
  - [Microsoft Azure Active Directory](/azure/active-directory/) - 모든 사용자 계정의 인증 및 식별을 위한 것입니다. 
  - [Microsoft Intune](/mem/intune/) - 장치 구성, 장치 관리 및 응용 프로그램 관리를 배포하기 위한 것입니다.
  - [Endpoint Analytics](/mem/analytics/overview) – 장치 및 앱 사용에 대한 분석 정보를 제공합니다.
  - [Windows 장치 프로비전](/microsoft-365/windows/windows-autopilot) 및 배포를 위해 Autopilot을 사용합니다.
  - [끝점용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) – 장치 보안 모니터링 및 보안 인텔리전스 데이터와 같은 보안 서비스를 제공합니다.
- [Microsoft Managed Desktop](https://endpoint.microsoft.com/#home) – 고객이 제공하거나 서비스를 실행하는 동안 서비스에서 생성한 데이터입니다.
- [Microsoft 365 앱 -](https://www.microsoft.com/en-us/microsoft-365/enterprise/compare-office-365-plans?rtc=1) 엔터프라이즈용 앱을 Microsoft 365 앱.

## <a name="microsoft-managed-desktop-data-process-and-storage"></a>Microsoft Managed Desktop 프로세스 및 저장소

Microsoft Managed Desktop Microsoft 제품 및 서비스의 데이터를 사용하여 엔터프라이즈 고객에게 서비스를 제공합니다. 등록된 장치를 보호하고 유지 관리하기 위한 목표를 달성하기 위해 이러한 서비스의 데이터를 처리 및 복사하여 Microsoft Managed Desktop.  데이터를 처리하면 온라인 서비스 약관 및 Microsoft 개인 정보 취급 [](https://www.microsoft.com/licensing/product-licensing/products) 방침에서 참조되는 문서화된 지침을 [따르게 됩니다.](https://privacy.microsoft.com/privacystatement) Microsoft Managed Desktop 프로세서 의무에는 적절한 기밀성, 보안 및 탄력성을 보장하는 것이 포함됩니다. Microsoft Managed Desktop 개인 식별 가능 데이터의 적절한 처리를 보장하기 위해 추가 개인 정보 보호 및 보안 조치를 취합니다. 


## <a name="microsoft-managed-desktop-data-storage-and-staff-location"></a>Microsoft Managed Desktop 저장소 및 직원 위치

Microsoft Managed Desktop 데이터는 미국의 Azure 데이터 센터에 저장됩니다. 서비스 운영을 유지하기 위해 Microsoft Managed Desktop 및 기타 서비스에서 획득한 개인 데이터가 필요합니다. 장치에서 제거된 Microsoft Managed Desktop 보안 목적으로 180일 동안 저장되는 끝점용 Microsoft Defender에서 수집한 경고 데이터를 제외하고 최대 30일 동안 개인 데이터를 보관합니다. 데이터 보존에 대한 자세한 내용은 에서 데이터 보존, 삭제 [및 폐기를 Microsoft 365.](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)

Microsoft Managed Desktop 엔지니어링 운영 및 보안 운영 팀은 미국 및 인도에 있습니다. 

### <a name="microsoft-windows-10-diagnostic-data"></a>Microsoft Windows 10 진단 데이터

Microsoft Managed Desktop 데이터를 [Windows 10 향상된](/windows/privacy/windows-diagnostic-data) 진단 데이터를 사용하여 보안 Windows, 문제를 해결하고, 제품을 개선합니다. 향상된 진단 데이터 설정에는 등록된 장치에 대한 자세한 Microsoft Managed Desktop, 설정, 기능 및 장치 상태도 포함됩니다. 향상된 진단 데이터를 선택하면 필수 진단 데이터를 비롯한 데이터가 수집됩니다. 진단 [데이터 Windows](/windows/privacy/changes-to-windows-diagnostic-data-collection) 설정 및 데이터 수집에 대한 자세한 내용은 Windows 10 데이터 수집에 대한 변경 사항을 참조하세요.

진단 데이터 용어는 향후 버전에서 변경될 Windows. Microsoft Managed Desktop 필요한 데이터만 처리하기 위해 최선을 다하고 있습니다. 이 경우 진단 수준이 선택적 으로 변경됩니다Microsoft Managed Desktop 서비스에 필요한 진단 데이터 수집을 세부적으로 조정하기 위해 제한된 진단 정책을 구현합니다.  자세한 내용은 진단 데이터 [수집에 대한 Windows 변경을 참조합니다.](/windows/privacy/changes-to-windows-diagnostic-data-collection)

Microsoft Managed Desktop 응용 프로그램 및 장치 안정성 및 성능 정보와 같은 등록된 장치에서 Windows 10 선택적 진단 데이터의 시스템 수준 데이터만 처리하고 저장합니다. Microsoft Managed Desktop 및 브라우저 기록, 음성, 텍스트 또는 음성 데이터와 같은 고객의 개인 데이터를 처리하고 저장하지 않습니다. 

Microsoft Windows 10 데이터 수집에 대한 자세한 내용은 Microsoft [](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) 개인 정보 취급 방침의 개인 데이터를 저장하고 처리하는 위치 섹션을 참조하세요.

### <a name="microsoft-windows-update-for-business"></a>비즈니스용 Microsoft Windows 업데이트
비즈니스용 Microsoft Windows 업데이트는 Windows 데이터를 사용하여 업데이트 상태 및 실패를 분석합니다. Microsoft Managed Desktop 데이터를 활용하여 문제를 완화하고 해결하여 등록된 모든 장치가 미리 정의된 업데이트 케이던스를 기반으로 최신으로 유지되도록 합니다.

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory
조직에서 사용하는 Microsoft Managed Desktop 식별은 엔터프라이즈 및 Azure용 Microsoft Apps 같은 Microsoft 온라인 서비스에 구독할 때 조직에서 제공한 위치를 기반으로 지리적 위치에 Azure Active Directory(Azure AD)에 의해 저장됩니다. 조직에서 사용하는 Microsoft Managed Desktop 식별은 엔터프라이즈 및 Azure와 같은 Microsoft 온라인 서비스에 구독할 때 조직에서 제공하는 위치에 따라 Azure AD에서 Microsoft Apps 저장합니다. Azure AD 데이터가 있는 장소에 대한 자세한 내용은 Azure Active Directory [- 데이터는 어디에 있나요?를 참조하세요.](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)

### <a name="microsoft-intune"></a>Microsoft Intune
Microsoft Intune 및 서비스를 지원하기 위해 데이터를 Microsoft Managed Desktop, 프로세스 및 공유합니다. Intune에서 수집된 데이터에 대한 자세한 내용은 [Intune의](/mem/intune/protect/privacy-data-collect) 데이터 수집을 참조하세요. 

데이터 위치에 대한 Microsoft Intune 자세한 내용은 고객 데이터가 [Microsoft 365 위치를 참조하세요.](/microsoft-365/enterprise/o365-data-locations) Intune은 고객 데이터에 대해 관리자가 선택한 저장소 위치를 존중합니다.

### <a name="microsoft-defender-for-endpoint"></a>엔드포인트용 Microsoft Defender
끝점용 Microsoft Defender는 관리, 추적 및 보고를 위해 Microsoft Managed Desktop 등록된 장치에 대한 정보를 수집하고 저장합니다. 수집된 정보에는 파일 데이터(예: 파일 이름, 크기 및 해시), 프로세스 데이터(실행 중인 프로세스, 해시), 레지스트리 데이터, 네트워크 연결 데이터 및 장치 세부 정보(예: 장치 식별자, 장치 이름 및 운영 체제 버전)가 포함됩니다. Endpoint의 데이터 수집 및 저장소 위치에 대한 Microsoft Defender에 대한 자세한 내용은 [Endpoint](/microsoft-365/security/defender-endpoint/data-storage-privacy#what-data-does-microsoft-defender-atp-collect) 데이터 저장소 및 개인 정보 보호를 위한 Microsoft Defender를 참조하세요. 

### <a name="microsoft-365-apps-for-enterprise"></a>엔터프라이즈용 Microsoft 365 앱 
엔터프라이즈용 Microsoft 365 앱 데이터를 수집하고 공유하여 Microsoft Managed Desktop 관리되는 미리 정의한 업데이트 채널을 기반으로 최신 버전의 앱을 최신 버전으로 Microsoft Managed Desktop. 데이터 수집 및 저장 위치에 대한 자세한 내용은 Endpoint 데이터 저장소 및 개인 정보 보호를 Microsoft 365 앱 Microsoft [Defender를](/microsoft-365/security/defender-endpoint/data-storage-privacy#what-data-does-microsoft-defender-atp-collect) 참조하세요.

## <a name="major-data-change-notification"></a>주요 데이터 변경 알림
Microsoft Managed Desktop 통신 프레임워크에 설명된 변경 제어 프로세스를 따르는 것입니다. 보안 인시던트와 서비스에 Microsoft 365 주요 변경 사항을 Microsoft Managed Desktop 및 관리자 포털을 통해 고객에게 알릴 수 있습니다. 수집된 데이터 형식 및 데이터가 저장되는 위치에 대한 변경 내용은 변경된 것으로 간주됩니다. 제품 및 서비스에 대한 표준 사례에 따라 이 변경에 대한 최소 30일의 사전 Microsoft 365 제공합니다. 자세한 내용은 서비스 변경 및 [통신을 참조하세요.](/microsoft-365/managed-desktop/service-description/servicechanges)

## <a name="compliance"></a>규정 준수
Microsoft Managed Desktop 감사를 시작하고 포괄적인 규정 준수 제품 집합을 획득했습니다. 자세한 내용은 준수 에서 Microsoft Managed Desktop [있습니다.](/microsoft-365/managed-desktop/intro/compliance) 감사 보고서는 Microsoft Enterprise Online Services의 중앙 리포지토리 역할을 하는 Microsoft Service [Trust Portal에서](https://aka.ms/stp)다운로드할 수 있습니다. 이 Microsoft Managed Desktop "모니터링 및 관리"라는 범주의 문서 내에 나열됩니다.

### <a name="data-subject-requests"></a>데이터 주체 요청
Microsoft Managed Desktop 개인 데이터에 대한 특정 권한을 데이터 주체에 제공 하는 GDPR 및 CCPA 개인 정보 보호 규정을 따릅니다. 이러한 권한에는 개인 데이터의 복사본을 얻거나, 수정을 요청하거나, 데이터의 처리를 제한하거나, 삭제하거나, 다른 컨트롤러로 이동할 수 있도록 전자 형식으로 수신하는 것이 포함됩니다. 일반적으로 DSR(데이터 주체 요청)에 대한 자세한 내용은 데이터 주체 요청 및 [GDPR 및 CCPA를 참조하세요.](/compliance/regulatory/gdpr-data-subject-requests)

Microsoft Managed Desktop 관리 시스템에서 수집한 데이터에 대해 데이터 주체 요청을 이행하기 위해 다음을 참조하세요.

- 끝점 경고에 대한 Microsoft Defender의 데이터: 보안 관리자는 관리 포털에서 보고서 요청을 제출하여 끝점 경고에 대한 Microsoft Defender와 관련된 개인 데이터 삭제 또는 추출을 [요청할 수 있습니다.](https://aka.ms/memadmin) 요청에서 요청 유형 변경 **요청,** 범주 **보안** 및 하위 범주 기타 를 **선택합니다.** 요청 설명에 관련 장치 이름을 제공합니다.
- 지원 Microsoft Managed Desktop 데이터: IT 관리자는 관리 포털에서 보고서 요청을 제출하여 개인 데이터 관련 지원 요청의 삭제 또는 추출을 [요청할 수 있습니다.](https://aka.ms/memadmin) 요청에서 요청 유형 변경 **요청,** 범주 **보안** 및 하위 범주 기타 를 **선택합니다.** 요청 설명에 관련 장치 이름 또는 사용자 이름을 제공합니다.

서비스와 관련된 다른 제품의 DSRS는 다음 문서를 참조하세요.

- Windows [데이터](/compliance/regulatory/gdpr-dsr-windows)
- Microsoft [Intune 데이터](/compliance/regulatory/gdpr-dsr-intune)
- Azure Active [Directory 데이터](/compliance/regulatory/gdpr-dsr-azure)

## <a name="legal"></a>법률 정보
조직 고객이 제공하는 제품의 최종 사용자에게 **Microsoft의** 개인 정보 취급 방침 - [Microsoft](https://privacy.microsoft.com/privacystatement) 개인 정보 취급 방침은 최종 사용자가 작업 계정을 사용하여 Microsoft 제품에 로그인할 때 조직이 자신의 계정을 제어 및 관리할 수 있으며(개인 정보 관련 설정 제어 포함) 해당 데이터에 액세스하고 처리하고, b) Microsoft는 데이터를 수집하고 처리하여 조직 및 최종 사용자에게 서비스를 제공할 수 있습니다.
