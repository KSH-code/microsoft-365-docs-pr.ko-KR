---
title: 내부 관리자 작업 수행
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Microsoft 365에서 관리되지 않는 테넌트를 수행하기 위해 전자 메일 및 도메인 소유권을 확인하는 방법을 알아봅니다.
ms.openlocfilehash: 9c1d98616b10737553060bcbad62df9b3b4c0c9a
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814471"
---
# <a name="perform-an-internal-admin-takeover"></a>내부 관리자 작업 수행

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요. 

관리자이며 셀프 서비스 사용자 등록으로 만들어진 관리되지 않는 테넌트에 대한 수용하려면 내부 관리자 인수를 사용하여 이 작업을 수행할 수 있습니다.

> [!NOTE]
> Azure AD를 사용하는 모든 클라우드 서비스에 대한 셀프 서비스 등록은 관리되지 않는 또는 "섀도" Azure AD 디렉터리에 사용자를 추가하고 관리되지 않는 테넌트를 만듭니다. 관리되지 않는 테넌트는 전역 관리자가 없는 디렉터리입니다. 테넌트가 관리되는지, 관리되지 않는지 확인하려면 [테넌트 유형 확인을 참조하세요.](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type) 
  
## <a name="step-1-verify-your-email-address"></a>1단계: 전자 메일 주소 확인

> [!NOTE]
> 테넌트에서 셀프 서비스를 활성화한 경우 사용자는 자체적으로 Power BI와 같은 무료 서비스를 구독할 수 있습니다. 이 단계에서는 셀프 서비스 사용자 구독에서 관리자로 수행하려는 관리되지 않는 테넌트를 만들었다고 가정합니다. 첫 번째 단계에서는 관리되지 않는 테넌트에서 사용자 컨텍스트를 만들고 Power BI를 사용하여 관리 인수 경로를 설명합니다.

1. Power BI에 등록하려면 Power BI 사이트로 [이동하고 무료](https://powerbi.com) 시작 평가판(Power **Start Free**  >  **Start free trial** BI Pro를 사용하는 Share point)을 선택합니다. 

2. 조직의 도메인 이름(예: )을 사용하는 사용자 계정을 사용하여 `powerbiadmin@contoso.com` 등록합니다. 계정을 이미 사용 중이면 현재 암호를 사용하여 로그인합니다.

3. 확인 코드가 **확인되는지 확인하고 코드를 입력하여 전자** 메일 주소를 확인합니다.
    
## <a name="step-2-create-a-new-account"></a>2단계: 새 계정 만들기

1. 확인 코드를 입력하면 새 계정을 만들 수 있는 페이지로 이동됩니다. 
    
2. 사용할 계정으로 사용자 이름 및 암호 필드를 입력한 다음 시작을 **선택합니다.** 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>3단계: 도메인 소유권 확인 및 관리자 입장

1. 관리 **마법사가 열립니다.** 마법사가 시작되지 않으면 관리 타일을 **검색하여** 선택합니다. 

2. 예, **관리자가 고리입니다.**

3. 도메인 등록 기관에 TXT 레코드를 추가하여 사용자가 수행할 도메인을 소유하고 있는지 확인합니다. 마법사는 추가할 TXT 레코드를 제공하고 등록 기관 웹 사이트에 대한 링크를 제공하고 단계별 지침 링크를 제공합니다.
    
4. 등록 기관 사이트에 TXT 레코드를 추가한 후 마법사로 돌아가 **확인을 선택하세요. 레코드를 추가한 것입니다.**
    
> [!NOTE]
> 섀도 테넌트에 대해 이동을 수행하더라도 기존 정보나 서비스에는 영향을 미치지 않습니다. 그러나 도메인에 라이선스가 필요한 서비스를 등록한 사용자가 있는 경우, 관리자 역할을 수행하라는 일부로 해당 사용자를 위한 라이선스를 구입하라는 메시지가 표시됩니다. 관리 설정 프로세스가 완료되면 라이선스를 구입하거나 제거할 수 있습니다.
  
## <a name="related-articles"></a>관련 문서

YouTube: [Power BI 및 Microsoft 365에 대한 IT 관리자 가리수행을 IT 관리자 조치를 수행하기 위한 3단계](https://www.youtube.com/watch?v=xt5EsrQBZZk)

[Azure AD에서 관리자 관리](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[조직에서 셀프 서비스 등록 사용](self-service-sign-up.md)
  
[Power BI 서비스 관리자 역할 이해](https://docs.microsoft.com/power-bi/service-admin-role)

