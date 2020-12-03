---
title: Microsoft 생산성 점수-개인 정보
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: 개인 정보를 생산성 점수가 보호 되는 방식입니다.
ms.openlocfilehash: db123042761b07ed64dd2dd94e783d65205e1460
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561517"
---
# <a name="privacy-controls-for-productivity-score"></a>생산성 점수에 대 한 개인 정보 제어

생산성 점수는 Microsoft 365 및이를 지 원하는 기술 환경을 통해 조직의 디지털 변환에 대 한 정보를 제공 합니다.  조직의 점수가 사용자 및 기술 경험 측정법을 반영 하며,이에 해당 하는 조직에 대 한 벤치 마크와 비교할 수 있습니다. 자세한 내용은 [생산성 점수 개요](productivity-score.md)를 참조 하세요.

개인 정보 보호는 Microsoft에 중요 합니다. 개인 정보를 보호 하는 방법에 대 한 자세한 내용은 [Microsoft의 개인 정보 취급](https://privacy.microsoft.com/privacystatement)방침를 참조 하세요. 생산성 점수가 조직의 IT 관리자가 사용자에 게 제공 하는 개인 정보 설정에 액세스 하 여 확인 하는 생산성 점수 정보를 확인 하 고 Microsoft에서 조직이 갖는 트러스트를 손상 시 키 지는 것을 보장 합니다.

사용자의 경험 분야 내에서 메트릭은 조직 수준 에서만 사용할 수 있습니다. 이 영역에서는 콘텐츠 공동 작업, 모바일, 회의, 팀 작업 및 통신의 범주를 확인 하 여 사용자가 Microsoft 365을 사용 하는 방법을 살펴봅니다. 내부 개인 정보 보호 정책 요구 사항을 충족 하는 데 도움이 되는 다양 한 수준의 컨트롤을 사용할 수 있습니다.
컨트롤에는 다음이 제공 됩니다.

- 유연한 관리자 역할-생산성 성과에서 정보를 볼 수 있는 사용자를 제어 합니다.
- 사용자의 경험 분야를 옵트아웃 하는 기능입니다.

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>생산성 성과에서 정보를 볼 수 있는 사용자를 제어 하기 위한 유연한 관리 역할

전체 생산성 점수를 보려면 다음 관리자 역할 중 하나가 필요 합니다.

- 전역 관리자
- Exchange 관리자
- SharePoint 관리자
- 비즈니스용 Skype 관리자
- Teams 관리자
- 전역 읽기 권한자
- 보고서 구독자
- 사용 현황 요약 보고서 독자

변경 관리 및 채택을 담당 하는 모든 사용자에 게 보고서 판독기 또는 사용 현황 요약 보고서 독자 역할을 할당 합니다 (반드시 IT 관리자 일 필요는 없음). 이 역할을 사용 하면 Microsoft 365 관리 센터의 전체 생산성 점수에 액세스할 수 있습니다.

나중에 2020에서 Microsoft 365 관리 센터에서 할당할 수 있을 때까지 사용 현황 요약 보고서 독자 역할을 PowerShell cmdlet을 통해 할당 해야 합니다.

PowerShell로 사용 현황 요약 보고서 읽기 권한자 역할을 할당 하려면 다음을 수행 합니다.

- 다음 PowerShell을 실행 합니다.

```powershell
Connect-AzureAD
Enable-AzureADDirectoryRole -RoleTemplateId '75934031-6c7e-415a-99d7-48dbd49e875e'
$role=Get-AzureADDirectoryRole -Filter "roleTemplateId eq '75934031-6c7e-415a-99d7-48dbd49e875e'"
Get-AzureADDirectoryRoleMember -ObjectId $role.ObjectId
$u=Get-AzureADUser -ObjectId <user upn>
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId $u.ObjectId
```

</br>


## <a name="capability-to-opt-out-of-people-experiences"></a>사용자 환경에 대 한 경험을 옵트아웃 하는 기능

또한 생산성 점수가 사용자에 게 주는 분야를 거부할 수도 있습니다. 옵트아웃 하는 경우 조직의 아무도 이러한 메트릭을 볼 수 없으며, 조직은 통신, 모임, 팀 작업, 콘텐츠 공동 작업 및 이동성을 포함 하는 모든 계산에서 제거 됩니다.

옵트인 하려면 다음을 수행 합니다.

1. 관리 센터에서 조직 설정 **설정** 으로 이동 하   >   **Org Settings** 고 **서비스** 탭에서 **보고서** 를 선택 합니다.
2. **Microsoft 365 usage data가 사용자에 게 유용한 정보를 사용할 수 있도록** 하는 상자를 선택 취소 합니다. Intune 구성 관리자에서 끝점 분석에 대 한 데이터 공유 설정을 수정 하는 방법을 이해 하려면 **자세히** 를 선택 합니다.
3. **저장** 을 선택 합니다.

:::image type="content" source="../../media/orgsettingspageoptout.png" alt-text="사용자 환경에서 제외할 수 있는 조직 설정 페이지입니다.":::