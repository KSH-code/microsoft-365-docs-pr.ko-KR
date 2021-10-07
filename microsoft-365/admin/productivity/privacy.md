---
title: Microsoft 생산성 점수 - 개인 정보
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: 생산성 점수로 개인 정보를 보호하는 방법
ms.openlocfilehash: 1bbc9c7459d29e9aef8dea102d1d98eed9c30550
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60178230"
---
# <a name="privacy-controls-for-productivity-score"></a>생산성 점수에 대한 개인 정보 보호 컨트롤

생산성 점수는 조직의 디지털 변환 여정에 대한 인사이트를 Microsoft 365 지원하는 기술 환경을 제공합니다.  조직의 점수는 사용자 및 기술 환경 측정값을 반영하며 사용자와 비슷한 조직의 벤치마크와 비교할 수 있습니다. 자세한 내용은 생산성 점수 개요 [를 참조하세요.](productivity-score.md)

개인 정보는 Microsoft에 중요합니다. Microsoft가 개인 정보를 보호하는 방법에 대한 자세한 내용은 Microsoft의 개인 정보 [취급 방침을 참조합니다.](https://privacy.microsoft.com/privacystatement) 생산성 점수는 조직의 IT 관리자가 개인 정보 설정에 액세스하여 사용자가 보는 생산성 점수 정보가 실행 가능한지 확인하면서 조직이 Microsoft에 제공하는 신뢰를 해소하지 못하게 합니다.

사용자 환경 영역 내에서 메트릭은 조직 수준에서만 사용할 수 있습니다. 이 영역은 콘텐츠 공동 작업, Microsoft 365, 모임, 팀워크 및 커뮤니케이션의 범주를 보고 사용자가 이러한 작업을 사용하는 방법을 에 대해 간과합니다. 다양한 수준의 컨트롤을 사용하여 내부 개인 정보 취급 방침 요구 사항을 충족할 수 있습니다.
컨트롤은 다음을 제공합니다.

- 생산성 점수에서 정보를 볼 수 있는 사용자 제어를 위한 유연한 관리자 역할
- 사람 환경 영역을 옵트아웃(opt out)하는 기능입니다.

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>생산성 점수에서 정보를 볼 수 있는 사용자 제어를 위한 유연한 관리자 역할

전체 생산성 점수를 보기 위해 다음 관리자 역할 중 하나만 필요합니다.

- 전역 관리자
- Exchange 관리자
- SharePoint 관리자
- 비즈니스용 Skype 관리자
- Teams 관리자
- 전역 읽기 권한자
- 보고서 읽기 권한자
- 사용 현황 요약 보고서 읽기 권한자

보고서 읽기 권한자 또는 사용 현황 요약 보고서 읽기 권한자 역할을 변경 관리 및 채택을 담당하지만 IT 관리자가 아닐 수도 있는 모든 사용자에게 할당합니다. 이 역할은 관리자 센터에서 생산성 점수의 전체 Microsoft 365 액세스할 수 있도록 합니다.

사용 현황 요약 보고서 읽기 프로그램 역할은 2020년 후반에 할당될 때까지 PowerShell cmdlet을 통해 할당해야 Microsoft 365 관리 센터 수 있습니다.

PowerShell을 통해 사용 현황 요약 보고서 읽기 프로그램 역할을 할당합니다.

- 다음 PowerShell을 실행합니다.

```powershell
Connect-AzureAD
Enable-AzureADDirectoryRole -RoleTemplateId '75934031-6c7e-415a-99d7-48dbd49e875e'
$role=Get-AzureADDirectoryRole -Filter "roleTemplateId eq '75934031-6c7e-415a-99d7-48dbd49e875e'"
Get-AzureADDirectoryRoleMember -ObjectId $role.ObjectId
$u=Get-AzureADUser -ObjectId <user upn>
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId $u.ObjectId
```

</br>


## <a name="capability-to-opt-out-of-people-experiences"></a>사람 환경을 옵트아웃(opt out)하는 기능

생산성 점수의 사용자 환경 영역을 옵트아웃(opt out)할 수 있습니다. 옵트아웃하면 조직의 어느 누구도 이러한 메트릭을 볼 수 없습니다. 조직은 커뮤니케이션, 모임, 팀워크, 콘텐츠 공동 작업 및 이동성과 관련된 계산에서 제거됩니다. 사용자 환경 보고서에서 조직을 옵트아웃하려면 전역 관리자 를 선택해야 합니다.

옵트아웃( opt out)

1. 관리 센터에서 생산성 **설정** 또는 설정   >     >  **로 이동하세요.**
2. 사용자 환경 정보를 Microsoft 365 사용 현황 데이터를 사용할 수 있도록 허용 확인란을 **선택하지 않습니다.** Intune 구성 관리자에서 Endpoint Analytics에 대한 데이터 공유 설정을 수정하는 방법을 이해하려면 자세한 **정보를 선택합니다.**
3. 저장을 **선택합니다.**

:::image type="content" source="../../media/orgsettingspageoptout.png" alt-text="사용자 환경을 옵트아웃(opt out)할 수 있는 Org 설정 페이지":::
