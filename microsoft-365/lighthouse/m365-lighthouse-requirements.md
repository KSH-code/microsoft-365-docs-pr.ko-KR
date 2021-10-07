---
title: 요구 사항 Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: MSP(관리 서비스 공급자)의 경우 서비스 공급자를 사용하기 위한 요구 사항 목록을 Microsoft 365 Lighthouse.
ms.openlocfilehash: 70aaefc7e19268a5ad4c33c50b2e165361f2c362
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60188928"
---
# <a name="requirements-for-microsoft-365-lighthouse"></a>요구 사항 Microsoft 365 Lighthouse

> [!NOTE]
> 이 문서에 설명된 기능은 미리 보기에 있으며 변경될 수 있으며 이 문서에 나열된 요구 사항을 충족하는 파트너만 사용할 수 있습니다. 조직에 등록이 Microsoft 365 Lighthouse 에 [등록을 Microsoft 365 Lighthouse.](m365-lighthouse-sign-up.md)

Microsoft 365 Lighthouse SMB(관리 서비스 공급자)가 중소기업 고객을 위해 대규모로 장치, 데이터 및 사용자를 보호하고 관리하는 데 도움이 되는 관리 포털입니다.  

MSP는 Lighthouse를 사용하려면 클라우드 솔루션 공급자(CSP) 프로그램에 간접 대리업체 또는 직접 청구 파트너로 등록해야 합니다.  

또한 각 MSP 고객 테넌트는 다음 요구 사항을 충족하여 Lighthouse 자격을 충족해야 합니다. 
 
- MSP에 대한 DAP(위임된 관리자 권한) 
- 하나 이상의 Microsoft 365 Business Premium 또는 Microsoft 365 E3 라이선스 
- 라이선스가 있는 사용자 500명 미만  

## <a name="requirements-for-enablingdevice-management"></a>장치 관리를 사용하도록 설정하기 위한 요구 사항   

장치 관리 페이지에서 고객 테넌트 장치를 표시하려면 MSP에서 다음을 해야 합니다.    

- MEM(Microsoft Endpoint Manager)에 모든 고객 장치를 등록합니다.자세한 내용은 에서 [장치 등록을 Microsoft Intune.](/mem/intune/enrollment/)
- 모든 고객 장치에 규정 준수 정책을 할당합니다.자세한 내용은 [에서 준수 정책 만들기를 Microsoft Intune.](/mem/intune/protect/create-compliance-policy) 

## <a name="requirements-for-enabling-usermanagement"></a>사용자 관리를 사용하도록 설정하기 위한 요구 사항 

위험한 사용자, 다단계 인증 및 암호 재설정을 비롯한 사용자 관리 페이지에 대한 보고서에 고객 데이터를 표시하려면 고객 테넌트에 Azure Active Directory Premium P1 이상에 대한 라이선스가 있어야 합니다. Azure AD Premium P1 포함된 Microsoft 365 Business Premium Microsoft 365 E3.   

## <a name="requirements-for-enablingthreat-management"></a>위협 관리를 사용하도록 설정하기 위한 요구 사항 

위협 관리 페이지에서 고객 테넌트 장치 및 위협을 표시하려면 모든 고객 테넌트 장치를 MEM(Microsoft Endpoint Manager)에 등록하고 해당 장치를 실행하여 보호해야 Microsoft Defender 바이러스 백신.  

자세한 내용은 에서 [장치 등록을 Microsoft Intune.](/mem/intune/enrollment/)  

Microsoft Defender 바이러스 백신 Windows 운영 체제의 일부로, Windows 실행하는 장치에서 기본적으로 Windows 10.  

> [!NOTE] 
> Microsoft가 아닌 다른 바이러스 백신 솔루션을 사용 중이지 않은 경우 Microsoft Defender 바이러스 백신 Microsoft Defender 바이러스 백신 사용하지 않도록 설정됩니다. Microsoft가 아닌 바이러스 백신 솔루션을 제거하면 Microsoft Defender 바이러스 백신 장치를 위협으로부터 보호하기 위해 Windows 자동으로 활성화됩니다.    

## <a name="related-content"></a>관련 콘텐츠   

[포털 Microsoft 365 Lighthouse](m365-lighthouse-configure-portal-security.md) 구성(문서)\
[Microsoft 365 Lighthouse 준수 페이지](m365-lighthouse-device-compliance-page-overview.md) 개요(문서)\
[Microsoft 365 Lighthouse 페이지](m365-lighthouse-users-page-overview.md) 개요(문서)\
[Microsoft 365 Lighthouse 위협 관리 페이지](m365-lighthouse-threat-management-page-overview.md) 개요(문서)\
[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml)   (문서)

