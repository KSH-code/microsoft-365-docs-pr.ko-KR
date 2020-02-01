---
title: Office 365 Advanced eDiscovery에서 사용자 및 사례 설정
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: 'Office 365 Advanced eDiscovery에서 사용자 역할을 구성 하 고 사례를 만들고 사용자를 사례에 할당 하는 방법에 대해 알아봅니다.  '
ms.openlocfilehash: 754cc7d73fc3325c2525e3101d1378d55afea4de
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601455"
---
# <a name="set-up-users-and-cases-in-office-365-advanced-ediscovery"></a>Office 365 Advanced eDiscovery에서 사용자 및 사례 설정

이 항목에서는 Office 365 Advanced eDiscovery에 대 한 사용자 및 사례를 설정 하는 방법에 대해 설명 합니다.
  
> [!IMPORTANT]
> 최신 버전의 Advanced eDiscovery에 계속 투자 하면 Office 365 Advanced eDiscovery ( *고급 ediscovery v 1.0*이 라고도 함)가 만료 됨을 알리는 것입니다. 여전히 고급 eDiscovery v 1.0을 사용 중인 경우에는 가능한 한 빨리 [Advanced ediscovery v 2.0](overview-ediscovery-20.md) ( *Microsoft 365의 고급 ediscovery 솔루션*이 라고도 함)으로 전환 하세요. Advanced eDiscovery 2.0에는 Advanced eDiscovery v 1.0과 비슷한 기능이 포함 되어 있지만 custodian 관리, 통신 관리 및 검토 집합과 같은 다양 한 새로운 기능도 제공 됩니다. Advanced eDiscovery v 1.0의 만료에 대 한 자세한 내용은 [레거시 ediscovery 도구 만료](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)를 참조 하세요. 
  
## <a name="prerequisites"></a>필수 구성 요소

고급 eDiscovery에서 사례와 사용자를 설정 하기 전에 다음을 수행 해야 합니다.
  
- 고급 eDiscovery를 사용 하 여 사용자 데이터를 분석 하려면 데이터의 custodian 사용자에 게 Office 365 E5 라이선스를 할당 해야 합니다. 또는 Office 365 E1 또는 E3 라이선스를 사용 하는 사용자에 게 고급 eDiscovery 독립 실행형 라이선스를 할당할 수 있습니다. 서비스 케이스에 할당 되 고 고급 eDiscovery를 사용 하 여 데이터를 분석 하는 관리자 및 규정 준수 직원은 E5 라이선스가 필요 하지 않습니다. 
    
- EDiscovery 사례를 만들고 여기에 구성원을 추가 하려면 Office 365 보안 &amp; 및 준수 센터에서 ediscovery 관리자 역할 그룹의 구성원 이어야 합니다. 보안 &amp; 및 준수 센터에서 eDiscovery 관리자 역할 그룹에 자신을 추가 하려면 Office 365 조 직의 전역 관리자 여야 합니다. 전역 관리자가 아닌 경우에는 전역 관리자에 게 사용자를 eDiscovery 관리자 역할 그룹에 추가 해 달라고 요청 해야 합니다. 자세한 내용은 다음을 참조하세요.
    
  - [Microsoft 365 보안 &amp; 및 준수 센터의 사용 권한](~/security/office-365-security/protect-against-threats.md)
    
  - [Microsoft 365 보안 &amp; 및 준수 센터에서 eDiscovery 권한 할당](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a>1 단계: 사용자 eDiscovery 권한 할당

첫 번째 단계는 사용자가 eDiscovery 사례의 구성원으로 추가할 수 있도록 &amp; 보안 및 준수 센터의 요구 사항 사용 권한을 할당 하는 것입니다. 보안 &amp; 및 준수 센터에서 사례 구성원으로 추가 된 사용자는 고급 eDiscovery의 사례에 액세스할 수 있습니다.
  
사용자에 게 eDiscovery 사례의 구성원으로 추가할 수 있는 필수 권한을 할당 하려면 [Microsoft 365 보안 &amp; 및 준수 센터의 eDiscovery 사례](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)에서 1 단계를 참조 하십시오.
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a>2 단계: eDiscovery 사례 만들기 및 구성원 추가

다음 단계에서는 보안 &amp; 및 준수 센터에서 새 eDiscovery 사례를 만들고 구성원을 추가 합니다. 그러면 사례 구성원이 Advanced eDiscovery의 사례에 액세스할 수 있게 됩니다.
  
1. 새 eDiscovery 사례를 만들려면 [Microsoft 365 보안 &amp; 및 준수 센터의 eDiscovery 사례](ediscovery-cases.md#step-2-create-a-new-case)에서 2 단계를 참조 하십시오.
    
2. EDiscovery 사례에 구성원을 추가 하려면 [Microsoft 365 보안 &amp; 및 준수 센터의 eDiscovery 사례](ediscovery-cases.md#step-3-add-members-to-a-case) 에서 3 단계를 참조 하세요.
    
## <a name="step-3-go-a-case-in-advanced-ediscovery"></a>3 단계: Advanced eDiscovery에서 사례 이동

EDiscovery 사례를 만들고 구성원을 추가 하 고 나면 사용자 (또는 사례 구성원)가 Advanced eDiscovery의 해당 사례에 액세스할 수 있습니다. Advanced eDiscovery의 사례에 액세스 하려면 [Microsoft 365 보안 &amp; 및 준수 센터의 eDiscovery 사례](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery)에서 8 단계를 참조 하십시오.
  
## <a name="see-also"></a>참고 항목

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[데이터 준비](prepare-data-for-advanced-ediscovery.md)
 
