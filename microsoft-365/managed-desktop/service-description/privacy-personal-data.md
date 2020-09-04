---
title: 개인 정보 및 개인 데이터
description: 서비스에서 수집, 저장 및 사용 하는 데이터에 대해 자세히 설명 합니다.
keywords: GDPR, 보존, 삭제, 저장, 보존, 처리, 보안, 감사
ms.prod: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: e1b0c856a3bfb886521ee2c1a2115e4c29504862
ms.sourcegitcommit: a6625f76e8f19eebd9353ed70c00d32496ec06eb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47363264"
---
# <a name="privacy-and-personal-data"></a>개인 정보 및 개인 데이터

사용자는 Microsoft Managed Desktop에서 관리 하는 장치에서 데이터를 수신, 전송 및 저장할 수 있습니다. 데이터의 개인 정보 보호를 신뢰 하 고 기대치와 일치 하는 방식 으로만 사용 합니다. 이 문서에서는 Microsoft Managed Desktop이 개인 데이터를 수집, 저장, 보존, 처리, 보안, 공유, 감사 및 내보내는 방법에 대해 설명 합니다. 또한 관리자가 개인 데이터를 보고, 수정 하 고, 삭제 하는 방법에 대해서도 알아봅니다.

Microsoft Managed Desktop은 프로 파일링, 광고 또는 마케팅 목적으로 서비스를 제공 하는 과정에서 수집 된 개인 데이터를 사용 하지 않습니다.

## <a name="data-collection-of-microsoft-managed-desktop"></a>Microsoft Managed Desktop의 데이터 수집

사용자가 회사 장치를 Microsoft Managed Desktop에 등록할 때 기술 계층에서 Windows 및 Microsoft Intune을 사용 하 여 데이터 수집이 처리 됩니다. 이러한 원본은 microsoft managed desktop의 장치 이름과 같은 사용자 장치에 대 한 개인 데이터를 수집 하 여 Microsoft managed Desktop 환경에서 관리할 장치를 식별 하는 데 사용할 수 있습니다.

Microsoft Managed Desktop은 [IT 관리자 연락처 정보](#it-admin-contact-information)를 제외 하 고 서비스를 제공 하기 위해 자체적으로 데이터를 수집 하지 않습니다. 대신 Microsoft Managed Desktop은 Windows 및 Microsoft Intune 같은 다른 원본에서 이미 수집한 데이터를 다시 사용할 수 있습니다. Microsoft Managed Desktop은 다음 서비스에서 등록 한 장치를 수집 하는 데이터를 사용 합니다.

- Microsoft Managed Desktop에서 관리 하는 장치의 windows 진단 데이터가 Microsoft의 Windows 진단 데이터 저장소로 전송 됩니다.
- Microsoft Managed Desktop은 [최신 관리](https://docs.microsoft.com/learn/modules/introduction-to-modern-management-in-microsoft-365/) 를 사용 하 여 등록 된 장치를 관리 합니다. 이 경우에는 테 넌 트의 Azure Active Directory에 장치를 등록 해야 합니다.
- 최적화 된 고급 구성 및 보안 구성을 등록 된 장치에 배포 하는 경우 Microsoft Managed Desktop은 Microsoft Intune을 사용 합니다.
- Microsoft Managed Desktop은 해당 서비스를 사용 하는 고객에 대 한 Microsoft Defender Advanced Thread Protection의 보안 인텔리전스 데이터를 사용 합니다.

## <a name="data-storage-and-sources-in-microsoft-managed-desktop"></a>Microsoft Managed Desktop의 데이터 저장소 및 원본

Microsoft Managed Desktop이 데이터를 가져온 후에는 다음과 같이 해당 데이터에 대 한 서비스, 저장 및 처리를 제공 해야 합니다.

### <a name="storing-data-storage-location-and-data-retention"></a>데이터, 저장 위치 및 데이터 보존 저장

Microsoft Managed Desktop은 해당 데이터를 다음 Microsoft 저장소 서비스 중 하나 이상에 저장 합니다.

- Azure SQL
- Azure 저장소

Microsoft Managed Desktop은 해당 데이터를 미국에 저장 합니다. 개인 데이터는 최대 30 일 동안 Microsoft Managed Desktop에 의해 보존 됩니다.

## <a name="data-usage-of-microsoft-managed-desktop"></a>Microsoft Managed Desktop의 데이터 사용

Microsoft Managed Desktop에서는 다음 데이터를 사용 합니다.


| 데이터 원본 |Microsoft Managed Desktop에서 사용  |
|---------|---------|
|Azure Active Directory 데이터     | Microsoft Managed Desktop Admin 포털에서 사용할 수 있는 테 넌 트 관리자 용으로 만든 보고서에서 사용 됩니다.        |
|Intune 데이터     | Microsoft Managed Desktop Admin 포털에서 사용할 수 있는 테 넌 트 관리자 용으로 만든 보고서에서 사용 됩니다.        |
|Microsoft Defender Advanced Threat Protection (ATP)     |  Microsoft 관리 되는 데스크톱의 SOC (보안 작업 센터)에 의해 등록 된 장치에서 검색 된 보안 위험을 해결 하는 데 사용 됩니다.  |
|Windows 진단 데이터     |관리 되는 장치의 업데이트 상태를 확인 하 고, Microsoft Managed Desktop의 IT 서비스 (ITaaS) 제공을 제공 및 개선 하는 데 사용 됩니다.         |
|관리자 연락처 데이터     | Microsoft Managed Desktop이 테 넌 트 관리자와 통신 하는 데 사용 됩니다.        |


### <a name="entities-processed-by-microsoft-managed-desktop"></a>Microsoft Managed Desktop에서 처리 되는 엔터티

Microsoft Managed Desktop은 이러한 엔터티를 처리 하 여 서비스를 제공 합니다.

- 장치 데이터
- 장치 보안 설정
- 장치 운영 체제 및 하드웨어
- 장치 상태에 대 한 집계 된 정보
- 장치 진단 정보
- 테 넌 트 데이터
- Azure Active Directory 리소스
- 정책 및 구성 데이터
- Microsoft Defender ATP 메타 데이터
- Windows 진단 데이터
- 제품 및 서비스 사용 현황 데이터

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Microsoft Managed Desktop에서 사용 되는 id 데이터는 Office 365 또는 Azure와 같은 Microsoft online 서비스를 구독할 때 조직에서 제공한 주소를 기반으로 하 여 지리적 위치에 Azure Active Directory에 저장 됩니다. Azure Active Directory에 대 한 데이터 센터를 보여 주는 맵을 보려면 [Microsoft Azure](http://azuredatacentermap.azurewebsites.net/) 를 참조 하세요.

데이터 저장소에 대 한 Azure 사용 지역에 대 한 자세한 내용은 [Azure Active Directory – 데이터 위치](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)를 참조 하세요.

### <a name="microsoft-intune"></a>Microsoft Intune

Intune 데이터는 유럽 북부 (아일랜드) 및 유럽 서 부 (네덜란드)와 같은 몇 가지 다른 지역에 저장 될 수 있습니다. IT 관리자가 테 넌 트 계정을 만들고 처음 Intune 서비스에 등록할 때 데이터가 저장 될 국가를 선택 합니다. Intune에서 사용 되는 데이터 센터 위치 목록은 [Microsoft Intune-내 고객 데이터의 위치](http://intunedatacentermap.azurewebsites.net/)를 참조 하세요. Intune에서 데이터를 저장 하 고 사용 하는 방법에 대 한 자세한 내용은 [intune에서 데이터 수집](https://docs.microsoft.com/intune/privacy-data-collect)을 참조 하십시오.

### <a name="microsoft-defender-advanced-threat-protection"></a>Microsoft Defender Advanced Threat Protection

Microsoft Defender ATP (Advanced Threat Protection) 데이터는 몇 가지 다른 지역에 저장 될 수 있습니다. 이러한 이유 때문에 microsoft defender ATP는 microsoft [DEFENDER atp](http://intunedatacentermap.azurewebsites.net/)에 설명 된 대로 유럽 연합, 영국 및 미국의 microsoft Azure 데이터 센터에서 작동 합니다. Microsoft Defender ATP에서 데이터를 저장 하 고 사용 하는 방법에 대 한 자세한 내용은 [Microsoft DEFENDER atp에서 수집 하는 데이터](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy#what-data-does-microsoft-defender-atp-collect) 를 참조 하세요.

### <a name="windows-10"></a>Windows 10

[Microsoft 개인 정보 취급](https://privacy.microsoft.com/privacystatement)방침에서 설명한 것 처럼 "microsoft에서 수집한 개인 데이터는 지역에서 저장 및 처리 될 수 있습니다., 미국 및 Microsoft 또는 계열사, 자회사 또는 서비스 공급자가 운영 하는 기타 국가에서 제공 됩니다. [...] 일반적으로 기본 저장소 위치는 고객의 지역 또는 미국에서 다른 지역의 데이터 센터에 대 한 백업을 포함 하는 경우입니다. 저장소 위치는 효율적으로 작동 하 고, 성능을 개선 하 고, 중단 문제나 다른 문제가 발생 한 경우 데이터를 보호 하기 위해 중복성을 만들기 위해 선택 됩니다. 이 개인 정보 취급 방침에서 수집한 데이터는이 문의 프로 비전 및 데이터가 있는 모든 해당 법률의 요구 사항에 따라 처리 되도록 하기 위한 단계를 수행 합니다. "

Windows 10의 진단 데이터 모음에 대 한 자세한 내용은 Microsoft 개인 정보 취급 방침의 ["개인 데이터를 저장 하 고 처리 하는 위치"](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) 섹션을 참조 하십시오.

## <a name="data-access-protection"></a>데이터 액세스 보호

Microsoft Managed Desktop의 내부 데이터 저장소에 대 한 직접 액세스는 다음과 같은 여러 가지 방식으로 제한 됩니다.

- 엔지니어링 팀장 수준 승인이 필요 합니다.
- 감사 되 고 시간도 제한 됩니다.
- 이를 위해서는 높은 보안 및 제한 된 워크스테이션을 사용 해야 합니다.
- 모든 데이터는 저장 되는 동안 암호화 됩니다.
- 한도에 대 한 액세스 권한이 없습니다.
- Microsoft Managed Desktop의 내부 관리 포털에 액세스 하려면 높은 보안 및 제한 된 워크스테이션이 필요 합니다.

## <a name="processing-personal-data-in-a-compliant-manner"></a>호환 되는 방식으로 개인 데이터 처리
Microsoft Managed Desktop은 ISO 인증 시스템을 사용 하 여 개인 데이터를 처리 합니다. 자세한 내용은 [규정 준수](../intro/compliance.md)를 참조 하세요.

## <a name="profiling-and-marketing"></a>프로 파일링 및 마케팅

Microsoft Managed Desktop은 프로 파일링, 광고 또는 마케팅 목적으로 서비스를 제공 하는 과정에서 수집 된 개인 데이터를 사용 하지 않습니다.

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR 및 CCPA에 대한 데이터 주체 요청

[GDPR (유럽 연합 일반 데이터 보호 규정)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) 은 사용자에 게 (규정 데이터 주체 역할에 알려진) 권한을 부여 하 여 고용주 또는 기타 유형의 에이전시/조직이 수집한 개인 데이터 (데이터 컨트롤러나 단순히 컨트롤러)를 관리 합니다. GDPR에서 개인 데이터는 식별되거나 식별 가능한 자연인에 관련된 모든 데이터로 매우 광범위하게 정의됩니다. GDPR은 데이터 주체에게 개인 데이터에 대한 특정 권한을 제공합니다. 이러한 권한에는 개인 데이터의 복사본을 얻거나, 수정을 요청하거나, 처리를 제한하거나, 삭제하거나, 다른 관리자에게 전달할 수 있도록 전자 형식으로 개인 데이터를 수신할 권한이 포함됩니다. 데이터 주체가 개인 데이터에 대한 작업을 수행하도록 관리자에게 공식적으로 요청하는 것을 DSR(Data Subject Request)이라고 합니다.

마찬가지로 캘리포니아 소비자 개인 정보 취급 방침 (CCPA)은 개인 정보를 삭제, 액세스 및 수신 (이식성) 할 수 있는 권한과 같은 GDPR의 데이터 주체 권한 등의 권한을 사용 하 여 캘리포니아 소비자에 게 정보 보호 권리 및 의무를 제공 합니다. 또한 CCPA에서는 특정 공개, electing 운동 시 판별에 대 한 보호, "sales"로 분류 되는 특정 데이터 전송에 대 한 "옵트아웃 (opt out)" 요구 사항에 대해 설명 합니다. 판매는 가치 있는 대가관계를 위하여 데이터 공유를 포함하도록 광범위하게 정의됩니다. CCPA에 대한 자세한 내용은 [캘리포니아 소비자 개인 정보 보호법](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa?view=o365-worldwide) 및 [캘리포니아 소비자 개인 정보 보호법 FAQ](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq?view=o365-worldwide)를 참조하세요.

다음 섹션에서는 Microsoft managed desktop이 사용 하는 개인 데이터 또는 개인 정보에 대해 컨트롤러를 찾고 액세스 하 고 작업 하는 방법에 대해 설명 합니다.

> [!NOTE]
> GDPR에 대 한 일반 정보를 보려면 서비스 보안 포털의 [gdpr 섹션](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) 을 참조 하세요.

### <a name="it-admin-contact-information"></a>IT 관리자 연락처 정보

테 넌 트 관리자는 Microsoft Managed Desktop Portal의 관리자 연락처 섹션에서 자신의 개인 데이터를 직접 보고 수정 하 고 삭제할 수 있습니다.

### <a name="user-related-personal-data"></a>사용자 관련 개인 데이터

이 외에도, Microsoft Managed Desktop은 개인 데이터를 자체적으로 수집 하지 않습니다. 대신 다른 Microsoft Enterprise Online Services가 수집 하는 개인 데이터를 사용 합니다. IT 관리자는 자신의 개인 데이터를 확인, 수정 및 삭제 하기 위해 사용자 요청에 응답 하기 위해 Microsoft Managed Desktop이 종속 된 기본 서비스의 각 기능을 사용할 수 있습니다. 이러한 서비스에서 사용 하는 개인 데이터를 보거나 삭제 하려면 먼저 [GDPR에 대 한 Azure 데이터 주체 요청](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure) 문서를 참조 하세요.

또한 Microsoft Managed Desktop 서비스에 대 한 다음 가이드를 사용 하 여 개인 데이터 모음에 따라 다음 지침을 따르십시오.

- [Azure Active Directory](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure?view=o365-worldwide)
- [Microsoft Intune](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-intune?view=o365-worldwide)
- [Microsoft Defender ATP](https:/docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [Windows 10](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
