---
title: DAP Microsoft 365 사용자 Windows PowerShell 관리
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: be497751-596f-431d-b256-0a89d36a47ce
description: Syndication 및 클라우드 솔루션 공급자(CSP) 파트너가 Windows PowerShell 테넌트 관리를 Microsoft 365 방법
ms.openlocfilehash: 2678489d1e281a60d230c65e29b358dff5f1a8ad
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60150561"
---
# <a name="how-to-manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-partners"></a>위임된 액세스 Microsoft 365 파트너용 Windows PowerShell 관리 방법

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

DAP(위임된 액세스 권한) 파트너는 Syndication 및 CSP(클라우드 솔루션 공급자) 파트너입니다. 대부분의 공급자는 네트워크 또는 통신 공급자입니다. 서비스 Microsoft 365 구독을 번들로 묶습니다. Microsoft 365 구독을 판매하는 경우 고객의 테넌트에 대한 AOBO(관리 대신 관리) 권한이 자동으로 부여되어 해당 테넌트에 대해 관리하고 보고할 수 있습니다. 이러한 작업은 작업에서 수행하기 Microsoft 365 관리 센터. PowerShell을 사용하여 PowerShell을 Microsoft 365 수행할 수 있습니다.
- 모든 고객 **TenantIds** 및 해당 도메인 나열 
- 고객 테넌트의 모든 사용자 및 할당된 라이선스 식별
> [!NOTE]
> 일부 관리 작업은 PowerShell에서만 수행할 수 있습니다.

다음 문서에서는 Syndication 및 CSP 파트너가 PowerShell을 사용하여 고객 테넌트 관리 방법을 보여 주며,
  
- [DAP(위임된 액세스 Microsoft 365)에 대한 Windows PowerShell 테넌트 관리](manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissio.md)
    
- [DAP(위임된 액세스 권한) 파트너용 Windows PowerShell을 사용하여 클라이언트 테넌트에 도메인 추가](add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-pe.md)
    
- [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)
    
- [DAP(위임된 액세스 권한) 파트너용 Windows PowerShell을 사용하여 고객 테넌트 보고 데이터 검색](retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-ac.md)
