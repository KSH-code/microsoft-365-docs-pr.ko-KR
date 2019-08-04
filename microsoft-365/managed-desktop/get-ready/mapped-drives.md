---
title: Microsoft Managed Desktop에 대 한 매핑된 드라이브 준비
description: 확인 해야 하는 중요 한 단계
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: e4c2dbe8f1cae12aa1b10c6cd43f295a9a6062d0
ms.sourcegitcommit: 8102751ae20c93439e19afded396c4e6ee5ea5a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2019
ms.locfileid: "34100714"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Microsoft Managed Desktop에 대 한 매핑된 드라이브 준비

대부분의 엔터프라이즈 환경에서는 사용자 또는 팀이 파일을 공유 및 저장 하거나 온-프레미스 응용 프로그램을 사용할 수 있도록 매핑된 드라이브에 대 한 레거시 요구 사항이 있습니다. Microsoft 관리 데스크톱에서는 매핑된 드라이브를 사용 하지 않는 것이 좋습니다. 대신 다음과 같이 yor 파일 액세스 솔루션을 modernize 것이 좋습니다.
  
- 개별 사용자가 사용 하는 매핑된 드라이브를 비즈니스용 OneDrive로 마이그레이션합니다. 
- 팀에서 SharePoint Online으로 파일을 공유 하는 데 사용 하는 매핑된 드라이브를 마이그레이션합니다. 
- 온-프레미스 파일 공유를 사용 하는 모든 응용 프로그램을 Modernize 하거나 대체 하 여 해당 요구 사항을 제거 합니다.
  
현대화 이러한 서비스를 사용 하면 최상의 최종 사용자 환경을 Microsoft Managed Desktop과 함께 사용할 수 있습니다. Microsoft FastTrack 서비스는 Microsoft 클라우드 서비스를 사용 하 여 환경 현대화를 지원할 수 있습니다. [적합 한 서비스 및 계획](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans) 에서 fasttrack 서비스를 사용할 수 있는지 여부를 확인 한 다음 Microsoft Managed Desktop을 준비 하기 위해 직접 연락 해야 합니다. FastTrack 비즈니스용 OneDrive 또는 SharePoint Online 마이그레이션에 대 한 배경 정보는 [데이터 마이그레이션을](https://docs.microsoft.com/fasttrack/o365-data-migration)참조 하십시오.

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Microsoft Managed Desktop의 매핑된 드라이브
 
일부 사용 사례에서 매핑된 드라이브를 제거 하거나 바꿀 수 없는 경우 Microsoft Managed Desktop administration portal에서 지원 요청을 제출 하 여 Microsoft Managed Desktop users에 배포 해야 합니다.
    
이러한 요청의 경우 지원 요청에 다음과 같은 세부 정보를 제공 해야 합니다. 

- Microsoft Managed Desktop 장치에 대해 매핑되어야 하는 파일 공유 위치의 모든 UNC 경로 
- 이러한 파일 공유 위치에 액세스 해야 하는 사용자 그룹 
- 할당 해야 하는 특정 드라이브 문자 (필요한 경우)

예를 들면 다음과 같습니다.

| 드라이브 문자 | UNC 경로 | 사용자 그룹 |
|--------------|----------|------------|
| 좌표  | \\\server\share\Marketing | ContosoMarketing |

사용자와 그룹이 파일 공유 위치에 액세스 하기 위한 적절 한 권한을 보유 하 고 온-프레미스 파일 서비스에 액세스할 수 있도록 유지 하는 것은 전적으로 책임입니다. 또한 가능한 한 빨리 이러한 파일 공유에 대 한 요구 사항을 제거 해야 합니다.

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>매핑된 드라이브를 Microsoft Managed Desktop에 배포 하려면
 
매핑된 드라이브를 회피 하 고 서비스 요청을 제출 하기 전에 요구 사항을 신중히 검토 했는지 확인 합니다. 그런 후 다음 단계를 수행 합니다.

1. [Microsoft Managed Desktop 포털로](https://aka.ms/mmdportal)이동 합니다.  
2. 지원 **> 지원 요청** 섹션을 통해 "매핑된 드라이브 배포" 라는 지원 요청을 제출 하 고 필요한 파일 공유 정보를 모두 제공 합니다.  
3. Microsoft Managed Desktop IT 작업에서는 요청이 완료 되 면 지원 요청 업데이트를 사용 하 여 권고를 제공 합니다. 이 구성은 처음에 테스트 배포 그룹의 장치에만 배포 됩니다.  
4. Microsoft Managed Desktop IT 작업을 통해 배포 된 구성이 예상 대로 작동 하는지 테스트 하 고 확인 해야 합니다. 테스트를 완료 한 후 지원 요청의 토론 탭을 사용 하 여 Microsoft Managed Desktop IT 작업에 알릴 수 있습니다.  
5. Microsoft Managed Desktop IT 운영 팀에서는 구성을 다른 배포 그룹에 배포 합니다. 
