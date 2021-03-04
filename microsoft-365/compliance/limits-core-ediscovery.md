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
description: 이 문서에서는 Microsoft 365의 핵심 eDiscovery 사례의 제한에 대해 설명하고 있습니다.
ms.openlocfilehash: 2699e9b2511c742bb295f69611a976f6a3955980
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423449"
---
# <a name="limits-in-core-ediscovery"></a>Core eDiscovery의 제한

다음 표에는 핵심 eDiscovery 사례 및 핵심 eDiscovery 사례와 관련된 보류에 대한 제한이 나열됩니다. Core eDiscovery에 대한 자세한 내용은 [Core eDiscovery 개요를 참조하세요.](ediscovery-cases.md)
    
  | 제한 설명 | 제한 |
  |:-----|:-----|
  |조직의 최대 사례 수입니다.  <br/> |제한 없음  <br/> |
  |조직의 최대 케이스 보류 수입니다.  <br/> |10,000  <br/> |
  |단일 케이스 보류의 최대 사서함 수입니다. 이 제한에는 총 사용자 사서함과 Microsoft 365 그룹, Microsoft Teams 및 그룹과 연결된 Yammer 포함됩니다.  <br/> |1,000  <br/> |
  |단일 케이스 보류의 최대 사이트 수입니다. 이 제한에는 비즈니스용 OneDrive 사이트, SharePoint 사이트 및 Microsoft 365 그룹, Microsoft Teams 및 Yammer 그룹과 연결된 총 수가 포함됩니다.  <br/> |100  <br/> |
  |핵심 eDiscovery 홈 페이지에 표시되는 최대 사례 수와 케이스 내의 보류, 검색 및 내보내기 탭에 표시되는 최대 항목 수입니다. <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup> 1,000개가 넘는 사례, 보류, 검색 또는 내보내기 목록을 표시하기 위해 해당 Office 365 보안 및 준수 powerShell cmdlet을 & 수 있습니다.
   > 
   > - [Get-ComplianceCase](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)

Core eDiscovery 사례와 연결된 콘텐츠 검색 및 내보내기와 관련된 제한에 대한 자세한 내용은 [Limits for Content Search and Core eDiscovery을 참조하십시오.](limits-for-content-search.md)