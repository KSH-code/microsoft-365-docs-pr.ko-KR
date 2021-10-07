---
title: 사용자 지정 사용자 보기 만들기, 편집 또는 삭제
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 4fe7f6ac-be8e-4b57-9e13-24ff889a4b28
description: 필터를 사용하여 사용자 지정 사용자 보기를 만들거나 편집하거나 삭제하는 방법을 Microsoft 365.
ms.openlocfilehash: e0d809e4f21f8fac798029a403242504b394fb68
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60161837"
---
# <a name="create-edit-or-delete-a-custom-user-view"></a>사용자 지정 사용자 보기 만들기, 편집 또는 삭제

비즈니스용 Microsoft 365 전역 관리자 또는 사용자 관리 관리자인 경우 사용자 지정 사용자 보기를 만들어 특정 사용자 하위 집합을 볼 수 있습니다. 이러한 보기는 표준 보기 집합에 추가됩니다. 사용자 지정 사용자 보기를 만들거나 편집하거나 삭제할 수 있으며, 만든 사용자 지정 보기는 모든 관리자가 사용할 수 있습니다.
  
## <a name="custom-user-views-in-the-admin-center"></a>관리 센터의 사용자 지정 사용자 보기

사용자 지정 사용자 보기를 만들거나 편집하거나 삭제하면 변경  내용이 회사 내 모든 관리자가 사용자 페이지로 이동하면 표시되는 필터 목록에 **표시됩니다.** 최대 50개 사용자 지정 보기를 만들 수 있습니다. 

> [!TIP]
>  표준 사용자 보기는 필터  드롭다운 목록에 기본적으로 표시됩니다. 표준 필터에는 모든 **사용자,** 라이선스가 있는 **사용자,** **게스트** **사용자,** 로그인 **허용,** 로그인 **차단,** 허가되지 않은 **사용자,** 오류가 있는 사용자, **대금** 청구 관리자, 전역 **관리자,** **헬프데스크** **관리자,** 서비스 관리자 및 사용자 관리 관리자가 **포함됩니다.** 표준 보기는 편집하거나 삭제할 수 없습니다. 

표준 보기에 대해 주의해야 할 몇 가지 사항: 

- 목록에 사용자가 2,000명 이상인 경우 일부 표준 보기에는 목록의 목록이 표시되지 않습니다. 이 목록에서 특정 사용자를 찾으면 검색 상자를 사용하세요. 
- Microsoft에서 Microsoft 365 구매하지 않은 경우 청구  관리자는 표준 보기 목록에 나타나지 않습니다. 자세한 내용은 [관리 역할 지정](assign-admin-roles.md)을 참조하세요. 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a>사용자 지정 사용자 보기에 대한 필터 선택

사용자 지정 필터 창에서 사용자 지정 보기를 만들고 **편집할 수** 있습니다. 여러 필터 옵션을 선택하면 선택한 모든 조건과 일치하는 사용자가 포함된 결과가 표시됩니다. 다음 예제에서는 캐나다에 있는 특정 도메인의 모든 사용자를 표시하는 "Canadian users"라는 사용자 지정 보기를 만드는 방법을 보여 주며, 

  
 **A - 도메인** 조직에 여러 도메인이 있는 경우 사용 가능한 도메인의 드롭다운 목록에서 선택할 수 있습니다. 
  
 **B - 로그인 상태** 허용되거나 차단되는 사용자를 선택 합니다. 
  
 **C - 위치** 국가 드롭다운 목록에서 위치를 선택합니다. 
  
 **D - 할당된 제품 라이선스** 조직에서 사용할 수 있는 라이선스의 드롭다운 목록에서 선택합니다. 이 필터를 사용하여 선택한 라이선스가 있는 사용자를 사용자에게 보여 주면 됩니다. 사용자에게 추가 라이선스가 있을 수도 있습니다. 
  
부서, 구 또는 시,도, 국가 또는 지역 또는 직위와 같이 조직에서 사용되는 추가 사용자 프로필 세부 정보를 필터링할 수도 있습니다.
  
 **기타 조건:**
  
- **동기화된 사용자만** 사용자가 활성화되어 있는지 여부에 관계없이 로컬 Active Directory와 동기화된 모든 사용자를 표시하려면 이 상자를 선택합니다. 
    
- **오류가 있는 사용자** 프로비전 오류가 있을 수 있는 사용자를 표시하려면 이 상자를 선택합니다. 
    
- **라이선스가 없는 사용자** 라이선스가 할당되지 않은 모든 사용자를 찾으하려면 이 상자를 선택합니다. 이 보기의 결과에는 사서함이 있지만 Exchange 없는 사용자도 포함됩니다. 이러한 사용자를 구체적으로 추적하기 위해 사서함 또는 보관 사서함과 **Exchange 필터를 사용 합니다.** 이 보기의 결과에는 보관함이 있지만 Exchange 없는 사용자도 포함됩니다.
    
- 사서함 또는 보관 **사서함이 Exchange** 라이선스가 없는 사용자 이 상자를 선택하여 Exchange Online 사서함이 있지만 Exchange 라이선스가 할당되지 않은 사용자 계정을 Microsoft 365 선택합니다. 이 필터의 결과에는 보관함이 있는 사용자나 보관함이 할당된 Exchange 포함됩니다. 

> [!NOTE]
> 사서함이 있는 **사용이 Exchange 필터는** 다음 경우 작동합니다.
1. 사서함이 최근에 공유에서  사용자로  변환된 경우 라이선스가 없습니다.
2. 사서함이 최근에 마이그레이션된 Microsoft 365 라이선스가 할당되지 않았습니다.
3. 사서함이 PowerShell을 사용하여 만들어지며 라이선스가 할당되지 않았습니다.
4. 사용자에 대해 cmdlet을 New-RemoteMailbox 새 사서함이 프로비전됩니다.
    
> [!TIP]
> 2,000명 이상의 사용자를 반환하는 사용자 지정 보기를 만드는 경우 결과 사용자 목록이 정렬되지 않습니다. 이 경우 검색 상자를 사용하여 사용자를 찾거나 사용자 지정 보기를 편집하여 검색을 구체화합니다. 
  
## <a name="create-a-custom-user-view"></a>사용자 지정 사용자 보기 만들기

::: moniker range="o365-worldwide"

1. 관리 센터에서 사용자  활성 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">사용자로 이동하세요.</a>
  
::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 사용자  활성 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">사용자로 이동하세요.</a> 

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 사용자  활성 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">사용자로 이동하세요.</a>  

::: moniker-end
    
2. 활성 **사용자 페이지에서** 필터를 **선택하고** 새 필터 **를 선택합니다.**
  
3. 사용자 **지정 필터 페이지에서** 필터의 이름을 입력하고 사용자 지정 필터에 대한 조건을 선택한 다음 추가 를 **선택합니다.** 이제 사용자 지정 보기가 필터 드롭다운 목록에 포함됩니다.

## <a name="edit-or-delete-a-custom-user-view"></a>사용자 지정 사용자 보기 편집 또는 삭제

::: moniker range="o365-worldwide"

1. 관리 센터에서 사용자  활성 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">사용자로 이동하세요.</a>

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 사용자  활성 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">사용자로 이동하세요.</a> 

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 사용자  활성 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">사용자로 이동하세요.</a> 

::: moniker-end 
    
2. 활성 **사용자 페이지에서** **필터를** 선택하고 변경할 필터를 선택한 다음 필터 **편집 을 선택합니다.** 
    
    > [!TIP]
    > 사용자 지정 보기만 편집할 수 있습니다. 
  
3. 사용자 **지정 필터 페이지에서** 필요한 정보를 편집한 다음 저장을 **선택합니다.** 또는 필터를 삭제하려면 페이지 아래쪽에서 삭제를 **선택합니다.** 

## <a name="related-content"></a>관련 콘텐츠

[개요](../../business-video/admin-center-overview.md) Microsoft 365 관리 센터(비디오)\
[관리자 역할(비디오)\](../add-users/about-admin-roles.md)
[조직의 Microsoft 365 테마](../setup/customize-your-organization-theme.md) 사용자 지정(문서)


     