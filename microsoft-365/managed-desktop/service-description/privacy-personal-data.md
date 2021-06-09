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
ms.localizationpriority: normal
ms.openlocfilehash: 3f1a251d98be5b3a9fefa5c1f6d5d5562516d5d5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908177"
---
# <a name="privacy-and-personal-data"></a>개인 정보 및 개인 데이터

사용자는 해당 장치에서 데이터를 수신, 전송 및 저장할 수 Microsoft Managed Desktop. 데이터 개인 정보 보호는 예상과 일관된 방식으로만 보호되고 사용된다고 신뢰합니다. 이 문서에서는 개인 Microsoft Managed Desktop 수집, 저장, 보존, 프로세스, 보안, 공유, 감사 및 내보내기 방법에 대해 설명합니다. 관리자는 개인 데이터를 보고 수정하고 삭제하는 방법도 배우게 됩니다.

Microsoft Managed Desktop 프로파일링, 광고 또는 마케팅 목적으로 서비스 제공의 일부로 수집된 개인 데이터는 사용하지 않습니다.

## <a name="data-collection-of-microsoft-managed-desktop"></a>데이터 수집 Microsoft Managed Desktop

사용자가 회사 장치를 Microsoft Managed Desktop 등록하면 데이터 수집이 기술 계층에서 Windows Microsoft Intune. 이러한 원본은 관리되고 서비스 환경과 함께 제공될 장치를 식별하기 위해 Microsoft Managed Desktop 장치 이름과 같은 사용자 장치에 대한 개인 Microsoft Managed Desktop 수집합니다.

Microsoft Managed Desktop 서비스를 제공하기 위해 자체적으로 데이터를 수집하지 [않습니다(IT 관리자](#it-admin-contact-information)연락처 정보 제외). 대신 Microsoft Managed Desktop 원본과 같은 다른 원본이 이미 Windows Microsoft Intune 데이터를 다시 사용합니다. Microsoft Managed Desktop 등록된 장치에서 이러한 서비스가 수집하는 데이터를 사용하는지:

- Windows 관리되는 장치의 Microsoft Managed Desktop 진단 데이터는 Microsoft의 Windows 데이터 저장소로 전송됩니다.
- Microsoft Managed Desktop [관리는](/learn/modules/introduction-to-modern-management-in-microsoft-365/) 최신 관리를 사용하여 등록된 장치를 관리합니다. "최신 관리"의 일부로 디바이스를 테넌트의 디바이스에 등록해야 Azure Active Directory.
- 고도로 최적화된 보안 구성을 등록된 장치에 배포하기 위해 Microsoft Managed Desktop 구성을 Microsoft Intune.
- Microsoft Managed Desktop 서비스를 사용하는 고객을 위해 Microsoft Defender Advanced Thread Protection의 보안 인텔리전스 데이터를 사용하게 됩니다.

## <a name="data-storage-and-sources-in-microsoft-managed-desktop"></a>데이터 저장소 및 원본의 Microsoft Managed Desktop

데이터를 Microsoft Managed Desktop 후 다음과 같이 해당 데이터 처리, 저장 및 처리를 제공해야 합니다.

### <a name="storing-data-storage-location-and-data-retention"></a>데이터 저장, 저장 위치 및 데이터 보존

Microsoft Managed Desktop Microsoft 저장소 서비스 중 하나 이상에 해당 데이터를 저장합니다.

- Azure SQL
- Azure Storage
- Dynamics 365

Microsoft Managed Desktop 미국에 데이터를 저장합니다. 개인 데이터는 Microsoft Managed Desktop Microsoft Defender에서 수집한 Microsoft Managed Desktop 경고 데이터를 제외하고 최대 30일 동안 보존됩니다. 개인 데이터를 포함할 수 있는 실제 경고 데이터는 180일 동안 저장됩니다. 개인 데이터가 제거된 알림 데이터는 최대 2년 동안 저장됩니다. GDPR(일반 데이터 보호 규정) 및 캘리포니아 소비자 개인 정보 보호법(CCPA)을 준수하여 Microsoft Managed Desktop 데이터에 저장된 모든 개인 데이터에 대한 데이터 주체 권리를 준수합니다.

### <a name="staff-location"></a>직원 위치

Microsoft Managed Desktop 운영 및 보안 운영 팀은 미국 및 인도에 있습니다.

## <a name="data-usage-of-microsoft-managed-desktop"></a>데이터 사용 현황 Microsoft Managed Desktop

Microsoft Managed Desktop 데이터를 사용하는지:


| 데이터 원본 |2016에서 Microsoft Managed Desktop  |
|---------|---------|
|Azure Active Directory 데이터     | 테넌트 관리자를 위해 만든 보고서에서 사용됩니다. 이 보고서는 테넌트 관리자 포털에서 Microsoft Managed Desktop 있습니다.        |
|Intune 데이터     | 테넌트 관리자를 위해 만든 보고서에서 사용됩니다. 이 보고서는 테넌트 관리자 포털에서 Microsoft Managed Desktop 있습니다.        |
|끝점용 Microsoft Defender     |  SOC(보안 운영 센터)에서 등록된 장치에서 Microsoft Managed Desktop 위협을 해결하는 데 사용됩니다.  |
|Windows 데이터     |관리되는 장치의 업데이트 상태를 결정하고 ITaaS(IT-as-a-service) Microsoft Managed Desktop 제공 및 개선하는 데 사용됩니다.         |
|관리자 연락처 데이터     | 테넌트 Microsoft Managed Desktop 통신하는 데 사용됩니다.        |


### <a name="entities-processed-by-microsoft-managed-desktop"></a>사용자 지정에서 처리되는 Microsoft Managed Desktop

Microsoft Managed Desktop 서비스를 제공하기 위해 이러한 엔터티를 처리합니다.

- 장치 데이터
- 장치 보안 설정
- 장치 운영 체제 및 하드웨어
- 장치 상태 관련 집계 정보
- 장치 진단 정보
- 테넌트 데이터
- Azure Active Directory 리소스
- 정책 및 구성 데이터
- 끝점 메타데이터 및 경고 데이터용 Microsoft Defender
- Windows 데이터
- 제품 및 서비스 사용 현황 데이터

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Microsoft Managed Desktop 사용하는 ID 데이터는 Azure Active Directory 또는 Azure와 같은 Microsoft 온라인 서비스에 구독할 때 조직에서 제공한 주소에 따라 지리적 위치에 Office 365 저장됩니다. 자세한 Microsoft Azure 데이터 센터를 표시하는 지도는 고객 데이터가 어디에 [있나요?를](http://azuredatacentermap.azurewebsites.net/) Azure Active Directory.

Azure에서 데이터 저장소에 사용하는 지역에 대한 자세한 내용은 Azure Active Directory [–Where is your data located를 참조하세요.](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)

### <a name="microsoft-intune"></a>Microsoft Intune

Intune 데이터는 유럽 북부(아일랜드) 및 유럽 서부(네덜란드)와 같은 몇 가지 다른 지역에 저장할 수 있습니다. IT 관리자가 테넌트 계정을 만들고 Intune 서비스에 처음 등록할 때 데이터가 저장되는 국가를 선택하십시오. Intune에서 사용하는 데이터 센터 위치 목록은 Microsoft Intune -내 고객 데이터는 어디에 [있나요? 를 참조하세요.](http://intunedatacentermap.azurewebsites.net/) Intune에서 데이터 저장소 및 사용에 대한 자세한 내용은 [Intune의 데이터 수집을 참조하세요.](/intune/privacy-data-collect)

### <a name="microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender

끝점용 Microsoft Defender 데이터는 몇 가지 다른 지역에 저장할 수 있습니다. 이러한 이유로 Endpoint용 Defender는 [Microsoft Defender for Endpoint-Data storage locations에](http://intunedatacentermap.azurewebsites.net/)에 Microsoft Azure 유럽 연합, 영국 및 미국의 Microsoft Azure 데이터 센터에서 운영됩니다. 끝점용 Defender의 데이터 저장소 및 사용에 대한 자세한 내용은 [Endpoint용 Microsoft Defender에서](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy#what-data-does-microsoft-defender-atp-collect) 수집하는 데이터를 참조하세요.

### <a name="windows-10"></a>Windows 10

[Microsoft](https://privacy.microsoft.com/privacystatement)개인 정보 취급 방침에 설명된 "Microsoft에서 수집한 개인 데이터는 Microsoft 또는 계열사, 자회사 또는 서비스 공급자가 시설을 운영하는 지역, 미국 및 기타 모든 국가에 저장 및 처리될 수 있습니다. [...] 일반적으로 기본 저장소 위치는 고객의 지역이나 미국에 위치하고 다른 지역의 데이터 센터에 백업하는 경우가 자주 있습니다. 저장소 위치는 효율적으로 작동하고, 성능을 개선하고, 작동이 능동적이거나 다른 문제가 있는 경우 데이터를 보호하기 위해 중복을 만들기 위해 선택됩니다. 이 개인 정보 취급 방침에 따라 수집하는 데이터가 데이터가 어디에 있든 해당 법률의 요구 사항 및 본 조항에 따라 처리되도록 보장하기 위한 조치를 취합니다."

데이터 센터의 진단 데이터 수집에 Windows 10 Microsoft 개인 정보 취급 방침의 "개인 데이터를 저장하고 처리하는 [위치"](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) 섹션을 참조하세요.

## <a name="data-access-protection"></a>데이터 액세스 보호

Microsoft Managed Desktop 데이터 저장소에 대한 직접 액세스는 여러 가지 방법으로 제한됩니다.

- 엔지니어링 리드 수준 승인이 필요합니다.
- 감사 및 시간 제한입니다.
- 보안이 유지되고 제한된 Workstation을 사용해야 합니다.
- 모든 데이터는 저장되는 동안 암호화됩니다.
- 정식 액세스 권한이 없습니다.
- 보안 Microsoft Managed Desktop 포털에 액세스하려면 보안이 강화되고 제한된 Workstation이 필요합니다.

## <a name="processing-personal-data-in-a-compliant-manner"></a>준수 방식으로 개인 데이터 처리
Microsoft Managed Desktop ISO 인증 시스템을 사용하여 개인 데이터를 처리합니다. 자세한 내용은 준수를 [참조하세요.](../intro/compliance.md)

## <a name="profiling-and-marketing"></a>프로파일링 및 마케팅

Microsoft Managed Desktop 프로파일링, 광고 또는 마케팅 목적으로 서비스 제공의 일부로 수집된 개인 데이터는 사용하지 않습니다.

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR 및 CCPA에 대한 데이터 주체 요청

유럽 연합 [GDPR(일반](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) 데이터 보호 규정)은 사용자(규정에서 데이터 주체로 알려진)에게 고용주 또는 다른 유형의 기관이나 조직(데이터 컨트롤러 또는 단지 컨트롤러)에 의해 수집된 개인 데이터를 관리할 수 있는 권한을 제공합니다. GDPR에서 개인 데이터는 식별되거나 식별 가능한 자연인에 관련된 모든 데이터로 매우 광범위하게 정의됩니다. GDPR은 데이터 주체에게 개인 데이터에 대한 특정 권한을 제공합니다. 이러한 권한에는 개인 데이터의 복사본을 얻거나, 수정을 요청하거나, 처리를 제한하거나, 삭제하거나, 다른 관리자에게 전달할 수 있도록 전자 형식으로 개인 데이터를 수신할 권한이 포함됩니다. 데이터 주체가 개인 데이터에 대한 작업을 수행하도록 관리자에게 공식적으로 요청하는 것을 DSR(Data Subject Request)이라고 합니다.

마찬가지로 CCPA는 캘리포니아 소비자에게 GDPR의 데이터 주체 권리와 유사한 권리를 포함하여 개인 정보 삭제, 액세스 및 수신(이식성)과 같은 개인 정보 보호 권리 및 의무를 제공합니다. 또한 CCPA는 특정 공개, 행사 권한을 선택할 때 차별 방지, "판매"로 분류된 특정 데이터 전송에 대한 "옵트아웃/옵트인" 요구 사항을 제공합니다. 판매는 가치 있는 대가관계를 위하여 데이터 공유를 포함하도록 광범위하게 정의됩니다. CCPA에 대한 자세한 내용은 [캘리포니아 소비자 개인 정보 보호법](/compliance/regulatory/offering-ccpa?view=o365-worldwide) 및 [캘리포니아 소비자 개인 정보 보호법 FAQ](/compliance/regulatory/ccpa-faq?view=o365-worldwide)를 참조하세요.

다음 섹션에서는 컨트롤러가 Microsoft Managed Desktop 개인 데이터 또는 조직에서 사용하는 개인 정보를 찾고, 액세스하고, 이에 대해 행동하는 데 도움이 되는 Microsoft Managed Desktop.

> [!NOTE]
> GDPR에 대한 일반적인 정보를 찾고 있는 경우 Service Trust Portal의 [GDPR](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) 섹션을 참조하세요.

### <a name="it-admin-contact-information"></a>IT 관리자 연락처 정보

테넌트 관리자는 Microsoft Managed Desktop 포털의 관리자 연락처 섹션에서 직접 개인 데이터(예: 자신의 연락처 정보)를 보고 수정하고 삭제할 수 있습니다.

## <a name="microsoft-defender-for-endpoint-alert-data"></a>끝점용 Microsoft Defender 경고 데이터

보안 관리자는 해당 환경의 관리되는 디바이스에서 끝점 경고에 대한 Microsoft Defender와 관련된 개인 Microsoft Managed Desktop 추출 또는 Microsoft Managed Desktop 요청할 수 있습니다. 보안 관리자는 Microsoft Managed Desktop 관리 포털에 [로그인하고](https://aka.ms/memadmin) 지원 요청을 제출해야 합니다. 지원 **요청 유형** **변경** **요청,** 보안  범주 및 기타 하위 범주를 선택한 다음 설명에 관련 장치 이름과 함께 데이터 추출 또는 데이터 추출 요청과 함께 제공합니다. 

### <a name="user-related-personal-data"></a>사용자 관련 개인 데이터

이 외에도 Microsoft Managed Desktop 개인 데이터는 자체적으로 수집하지 않습니다. 대신 다른 Microsoft 온라인 서비스에서 수집한 개인 데이터를 Enterprise 사용합니다. 개인 데이터를 보고, 수정하고, 삭제하기 위한 사용자 요청에 응답하기를 원하는 IT 관리자는 해당 서비스에 따라 Microsoft Managed Desktop 서비스를 사용할 수 있습니다. 이러한 서비스에서 사용하는 개인 데이터를 보거나 삭제하는 데 관심이 있는 경우 [먼저 GDPR에](/compliance/regulatory/gdpr-dsr-Azure) 대한 Azure 데이터 주체 요청을 참조하세요.

또한 다음 지침을 사용하여 개인 데이터 수집에 따라 Microsoft Managed Desktop 서비스에 대한 DSRS를 행사할 수 있습니다.

- [Azure Active Directory](/compliance/regulatory/gdpr-dsr-Azure?view=o365-worldwide)
- [Microsoft Intune](/compliance/regulatory/gdpr-dsr-Intune?view=o365-worldwide)
- [끝점용 Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [Windows 10](/windows/privacy/windows-10-and-privacy-compliance)