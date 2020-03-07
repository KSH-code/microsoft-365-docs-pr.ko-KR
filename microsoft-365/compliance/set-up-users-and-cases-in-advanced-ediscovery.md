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
ms.openlocfilehash: 76d5e6ab503cc053e31811cc06ac12545a9eeb7e
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557758"
---
# <a name="set-up-users-and-cases-in-advanced-ediscovery-classic"></a>고급 eDiscovery에서 사용자 및 사례 설정 (클래식)

이 항목에서는 고급 eDiscovery (클래식)에 대 한 사용자 및 사례를 설정 하는 방법에 대해 설명 합니다.
  
> [!IMPORTANT]
> 최신 버전의 Advanced eDiscovery에 계속 투자 하는 경우에는 *고급 ediscovery (클래식)* 또는 *advanced ediscovery v 1.0*이 라고도 하는 Office 365 Advanced ediscovery의 만료를 발표 하 고 있습니다. Advanced eDiscovery v1.0을 계속 사용하고 있는 경우 [Advanced eDiscovery v2.0](overview-ediscovery-20.md)(*Advanced eDiscovery solution in Microsoft 365*라고도 함)으로 전환하세요. Advanced eDiscovery 2.0에는 Advanced eDiscovery v1.0에 있는 유사한 기능이 포함되어 있습니다. 또한 보유자 관리, 통신 관리, 검토 집합 등의 새로운 기능도 제공합니다. Advanced eDiscovery v1.0의 사용 중지에 대한 자세한 내용은 [레거시 eDiscovery 도구의 사용 중지](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)를 참조하세요. 
  
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

[고급 eDiscovery (클래식)](office-365-advanced-ediscovery.md)
  
[데이터 준비](prepare-data-for-advanced-ediscovery.md)
 
