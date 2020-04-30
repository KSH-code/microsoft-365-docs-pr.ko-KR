---
title: 러시아어 개인 데이터 지역화 요구 사항
description: Microsoft 서비스 및 러시아에 있는 데이터베이스에서 개인 데이터를 수집 하는 방법, 러시아의 개인 데이터 기록, systematization, 누적, 저장, 확인 및 추출이 수행 되는 방식을 알아봅니다.
keywords: Microsoft 365, 규정 준수, 제안
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 989d30a53b767bc8ec757c92e72198e3900bcfeb
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943667"
---
# <a name="russian-personal-data-localization-requirements"></a>러시아어 개인 데이터 지역화 요구 사항

개인 데이터 운영자로 간주 되는 2015 년 9 월 1 일, 조직에서 개인 데이터를 수집할 때에는 러시아어 시민이의 개인 데이터 기록, systematization, 누적, 저장, 확인 (업데이트 중, 변경) 및 추출에 있는 데이터베이스를 통해 러시아 (' 개인 데이터 지역화 요구 사항 ')이 수행 되는지 확인 해야 합니다. <sup>1</sup>

Microsoft Azure, Microsoft 365, Dynamics 365, Power Platform과 같이 개인 데이터 처리를 사용 하도록 설정 하는 경우를 비롯 하 여 조직에서 사용할 수 있는 microsoft Online Services (hereinafter)는 러시아 외부에 있는 데이터 처리 센터 (microsoft [보안 센터](https://www.microsoft.com/trust-center)방문)에서 제공 됩니다.

Microsoft 클라우드 제품을 사용 하는 경우를 비롯 하 여 고객 정보 시스템에서 처리 되는 정보의 유형 및 콘텐츠에 따라 개인 데이터 정보 시스템 (' PDL IS ', ' ISPD ')으로 간주 될 수 있습니다. 고객이 Microsoft Online Services를 사용 하려는 경우 시스템에서 해당 아키텍처와 정보를 처리 하는 정보의 유형을 통해 자격을 갖는 것으로 간주 되며 Microsoft는 아래에 지정 된 다른 사용 가능한 솔루션을 고려 하 여 고객에 게 제공 합니다. 아래에 제공 된 모든 시나리오는 표준 비즈니스 제품에 대 한 추가 옵션으로 고객에 게 제공 됩니다.

예를 들어, 정보 센터의 개인 데이터 운영자는 규정 준수를 담당 하 고 개인 데이터 지역화를 위한 적절 한 법적 요구 사항을 분석 하 고 평가 하며, 자체 판단에 따라 충분 한 조치를 수행 하 여 사용자의 개인 데이터 처리가 러시아어 개인 데이터 법률을 준수 하는 것을 확인할 수 있습니다. <sup>2</sup>

## <a name="subscribing-to-microsoft-online-services"></a>Microsoft Online Services 구독

### <a name="microsoft-id-management"></a>Microsoft ID 관리

Microsoft는 microsoft의 CSP (클라우드 솔루션 공급자) 파트너를 통해 microsoft 온라인 서비스-Microsoft Azure, Microsoft 365, Dynamics 365 및 파워 플랫폼을 구독 하는 것을 고려할 수 있도록 고객에 게 초대 합니다. 자세한 내용은이 [CSP 파트너 목록을](https://pinpoint.microsoft.com/search?type=services&campaign=691) 참조 하세요.

### <a name="managing-user-identity-and-access-for-microsoft-online-services"></a>Microsoft Online Services에 대 한 사용자 Id 및 액세스 관리

Microsoft Azure와 같은 Microsoft Online Services의 경우 Microsoft 365, Dynamics 365 및 Power Platform 사용자 확인 및 액세스 관리는 [AAD (Azure Active Directory](https://azure.microsoft.com/services/active-directory/))를 통해 수행 됩니다. Microsoft 고객이 Microsoft 클라우드 서비스에 대 한 로컬 id 관리 시스템 (예: Windows Server Active Directory (AD) 또는 기타 ID 관리 시스템)을 사용 하는 경우, 고객은 Azure AD Connect를 통해 해당 시스템을 AAD (Azure Active Directory)로 빠르게 통합할 수 있습니다. 자세한 내용은 [AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/cloud-provisioning/) 옵션을 참조 하세요. Microsoft 고객은 타사 공급 업체의 응용 프로그램 및 솔루션을 사용 하 여 사용자를 관리 하 고 자신의 로컬 식별 시스템을 Azure AD와 통합할 수도 있습니다.

## <a name="questions-and-support"></a>질문 및 지원

기술 및 대금 청구 관련 질문은 아래의 Microsoft 지원 리소스를 참조 하세요. 추가 질문이 나 설명은 Microsoft [개인 정보 팀](https://support.microsoft.com/gp/privacy-page)에 문의 하세요.

### <a name="microsoft-azure"></a>Microsoft Azure

- **웹 사이트**: [Microsoft Azure 지원](https://aka.ms/GetAzureSupport)
- **무료**: 8 800 200 8001
- **시내 전화**: 495 916 7171
- **온라인 지원**: [Azure Portal](https://portal.azure.com) 을 통해 쿼리 전송

### <a name="microsoft-365"></a>Microsoft 365

- **무료**: 8 10 800 2548 1044
- **시내 전화**: 499 922 8623
- **온라인 지원**: [관리 센터](https://portal.office.com/) 를 통해 쿼리 전송

### <a name="dynamics-365"></a>Dynamics 365

- **무료**: 8 10 800 2548 1044
- **시내 전화**: 499 922 8623
- **온라인 지원**: [Dynamics 지원 포털](https://dynamics.microsoft.com/support/) 을 통해 쿼리 전송

### <a name="power-platform"></a>전원 플랫폼

- **무료**: 8 10 800 2548 1044
- **시내 전화**: 499 922 8623
- **온라인 지원**: [파워 플랫폼 지원을](https://docs.microsoft.com/power-platform/admin/get-help-support) 통해 쿼리 전송

> [!NOTE]
> <sup>1</sup> 연방 법이 아닙니다. 242-FZ (버전 날짜 12.31.2014) "정보 및 통신 네트워크에서 개인 데이터를 처리 하는 절차를 명확 하 게 설명 하기 위해 러시아어 페더레이션을 사용 하는 특정 기관 작동 amendments <br>
> <sup>2</sup> 연방 법 법칙 152-07.27의 개인 데이터에 대 한 FZ 2006<br>
