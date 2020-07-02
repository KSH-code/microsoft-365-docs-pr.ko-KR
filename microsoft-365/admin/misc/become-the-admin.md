---
title: 내부 관리 인수 수행
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
description: Microsoft 365에서 관리 되지 않는 테 넌 트를 사용 하도록 전자 메일 및 도메인 소유권을 확인 하는 방법을 알아봅니다.
ms.openlocfilehash: 1eb54a6c34c9700bda09a660c71d2b1222fcdb8c
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45022160"
---
# <a name="perform-an-internal-admin-takeover"></a>내부 관리 인수 수행

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요. 

관리자 인 경우 셀프 서비스 사용자 등록으로 만든 관리 되지 않는 테 넌 트를 사용 하려는 경우에는 내부 관리자 인수을 사용 하 여이 작업을 수행할 수 있습니다.

> [!NOTE]
> Azure AD를 사용 하는 모든 클라우드 서비스에 대 한 셀프 서비스 등록은 관리 되지 않거나 "섀도" Azure AD 디렉터리에 사용자를 추가 하 고 관리 되지 않는 테 넌 트를 만듭니다. 관리 되지 않는 테 넌 트는 전역 관리자가 없는 디렉터리입니다. 테 넌 트가 관리 또는 관리 되지 않는지 여부를 확인 하려면 [테 넌 트 유형 확인](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)을 참조 하십시오. 
  
## <a name="step-1-verify-your-email-address"></a>1 단계: 전자 메일 주소 확인

> [!NOTE]
> 테 넌 트에서 셀프 서비스를 사용 하도록 설정한 경우 사용자는 Power BI와 같은 무료 서비스를 자체에 등록할 수 있습니다. 이 단계에서는 셀프 서비스 사용자 구독이 관리자로 수행 하려는 관리 되지 않는 테 넌 트를 만든 것으로 가정 합니다. 첫 번째 단계에서는 관리자 인수 경로를 보여 주기 위해 Power BI를 사용 하 여 관리 되지 않는 테 넌 트에서 사용자 컨텍스트를 만듭니다.

1. Power bi에 등록 하려면 [power bi 사이트로](https://powerbi.com) 이동한 후 **무료**  >  **시작 무료 평가판** 시작 (power bi Pro를 사용 하 여 공유)을 선택 합니다. 

2. 조직의 도메인 이름을 사용 하는 사용자 계정으로 등록 합니다 (like `powerbiadmin@contoso.com` ). 계정이 이미 사용 중인 경우 현재 암호를 사용 하 여 로그인 합니다.

3. 전자 메일에서 **확인 코드** 를 확인 하 고 코드를 입력 하 여 전자 메일 주소를 확인 합니다.
    
## <a name="step-2-create-a-new-account"></a>2 단계: 새 계정 만들기

1. 확인 코드를 입력 하면 새 계정을 만들 수 있는 페이지로 전환 됩니다. 
    
2. 사용할 계정으로 사용자 이름 및 암호 필드를 입력 한 다음 **시작**을 선택 합니다. 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>3 단계: 도메인 소유권 확인 및 관리자 되기

1. **관리자가 되기** 시작 마법사가 열립니다. 마법사가 시작 되지 않으면 **관리** 타일을 찾아 선택 합니다. 

2. **예, 관리자에 게**싶습니다 .를 선택 합니다.

3. 도메인 등록 기관에 TXT 레코드를 추가 하 여 수행할 도메인을 소유 하 고 있는지 확인 합니다. 마법사가 추가할 TXT 레코드를 제공 하 고, 등록자 웹 사이트에 대 한 링크 및 단계별 지침 링크를 제공 합니다.
    
4. 사용자가 등록자 사이트에 TXT 레코드를 추가 했으면 마법사로 돌아간 다음 확인을 선택 하 **여 레코드를 추가 했다고 가정**합니다.
    
> [!NOTE]
> 섀도 테 넌 트를 이용 해도 기존 정보나 서비스에는 영향을 주지 않습니다. 그러나 도메인의 사용자가 라이선스를 요구 하는 서비스에 등록 된 경우 관리자 역할을 수행 하는 동안 라이선스를 구입 하 라는 메시지가 표시 됩니다. 관리자 설정 프로세스가 완료 되 면 라이선스를 구입 하거나 제거할 수 있습니다.
  
## <a name="related-articles"></a>관련 문서

YouTube: [POWER BI 및 Microsoft 365에 대 한 IT 관리자 인수를 수행 하는 3 단계](https://www.youtube.com/watch?v=xt5EsrQBZZk)

[Azure AD의 관리 인수](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[도메인 도움말 보기](../get-help-with-domains/get-help-with-domains.md)

[조직에서 셀프 서비스 등록 사용](self-service-sign-up.md)
  
[Power BI 서비스 관리자 역할 이해](https://docs.microsoft.com/power-bi/service-admin-role)

