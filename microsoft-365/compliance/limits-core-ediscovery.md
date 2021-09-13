---
title: 핵심 eDiscovery 사례의 제한
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 이 문서에서는 핵심 eDiscovery 사례의 제한에 대해 Microsoft 365.
ms.openlocfilehash: e7b1013abd9fd94748baf3b83dd04efbc3831a1d
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59188099"
---
# <a name="limits-in-core-ediscovery"></a>Core eDiscovery의 제한

다음 표에는 핵심 eDiscovery 사례 및 핵심 eDiscovery 사례와 관련된 보류에 대한 제한이 나열됩니다. Core eDiscovery에 대한 자세한 내용은 [Core eDiscovery 개요를 참조하세요.](./get-started-core-ediscovery.md)
    
  | 제한 설명 | 제한 유형 |
  |:-----|:-----|
  |조직의 최대 사례 수입니다.  <br/> |제한 없음  <br/> |
  |조직의 최대 케이스 보류 수입니다.  <br/> |10,000  <br/> |
  |단일 케이스 보류의 최대 사서함 수입니다. 이 제한에는 사용자 사서함의 총 합계와 Microsoft 365, Microsoft Teams 및 그룹과 연결된 Yammer 포함됩니다.  <br/> |1,000  <br/> |
  |단일 케이스 보류의 최대 사이트 수입니다. 이 제한에는 비즈니스용 OneDrive, SharePoint 사이트, Microsoft 365 그룹, Microsoft Teams 및 Yammer 그룹과 연결된 사이트가 Yammer 포함됩니다.  <br/> |100  <br/> |
  |핵심 eDiscovery 홈 페이지에 표시되는 최대 사례 수와 케이스 내의 보류, 검색 및 내보내기 탭에 표시되는 최대 항목 수입니다. <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup> 1,000개가 넘는 사례, 보류, 검색 또는 내보내기 목록을 표시하기 위해 해당 Office 365 Security & 준수 PowerShell cmdlet을 사용할 수 있습니다.
   > 
   > - [Get-ComplianceCase](/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)

Core eDiscovery 사례와 연결된 검색 및 내보내기와 관련된 제한에 대한 자세한 내용은 [Limits for Content search and Core eDiscovery을 참조하십시오.](limits-for-content-search.md)