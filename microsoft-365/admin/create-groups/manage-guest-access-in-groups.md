---
title: Microsoft 365 그룹에서 게스트 액세스 관리
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Microsoft 365 그룹에 게스트를 추가하고, 게스트 사용자를 보고, PowerShell을 사용하여 게스트 액세스를 제어하는 방법을 학습합니다.
ms.openlocfilehash: 9a713684bb9a2401316dbb3289115be19b220cff
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453660"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Microsoft 365 그룹에서 게스트 액세스 관리

기본적으로 Microsoft 365 그룹에 대한 게스트 액세스는 조직에 대해 설정됩니다. 관리자는 전체 조직에 대한 그룹 또는 개별 그룹에 대한 게스트 액세스를 허용할지 여부를 제어할 수 있습니다.

이 설정이 켜져 있는 경우 그룹 구성원은 웹용 Outlook을 통해 게스트 사용자를 Microsoft 365 그룹에 초대할 수 있습니다. 승인을 위해 그룹 소유자에게 초대가 전송됩니다.

승인되면 게스트 사용자가 디렉터리 및 그룹에 추가됩니다.

> [!Note]
> Yammer 모드 또는 [EU 지역인](https://go.microsoft.com/fwlink/?linkid=2107357) 엔터프라이즈 네트워크는 네트워크 게스트를 지원하지 않습니다.
> Microsoft 365 연결된 Yammer 그룹은 현재 게스트 액세스를 지원하지 않지만 연결되지 않은 외부 그룹을 Yammer 있습니다. 자세한 [내용은 2013에서](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) 외부 그룹 만들기 및 Yammer 참조하세요.

그룹의 게스트 액세스는 SharePoint 또는 Teams를 포함하는 더 광범위한 시나리오의 일부로 자주 사용됩니다. 이러한 서비스에는 자체 게스트 공유 설정이 있습니다. 그룹, SharePoint 및 Teams에서 게스트 공유를 설정하기 위한 전체 지침은 다음을 참조하세요.

- [게스트와 현장에서 공동 작업하기](../../solutions/collaborate-in-site.md)
- [게스트와 팀으로 공동 작업하기](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>그룹 게스트 액세스 관리

그룹에서 게스트 액세스를 사용하도록 설정하거나 사용하지 않도록 설정하려면 Microsoft 365 관리 센터에서 설정할 수 있습니다.

1. 관리 센터에서 모든  설정 설정 표시로 이동하고 서비스 탭에서 \>  \>  **Microsoft 365**  그룹을 선택합니다.
  
2. Microsoft **365 그룹** 페이지에서 조직 외부의 사람이 그룹 리소스에 액세스할 수 있도록 할지 아니면 그룹 소유자가 조직 외부의 인원을 그룹에 추가할 수 있도록 할지 선택합니다.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>관리 센터에서 Microsoft 365 그룹에 게스트 추가

게스트가 디렉터리에 이미 있는 경우 Microsoft 365 관리 센터에서 그룹에 게스트를 추가할 수 있습니다. 동적 구성원이 있는 그룹은 [Azure Active Directory에서 관리해야 합니다.](https://docs.microsoft.com/azure/active-directory/enterprise-users/groups-create-rule)
  
1. 관리 센터에서 그룹 그룹   >  **페이지로** 이동합니다.
  
2. 게스트를 추가할 그룹을 클릭하고 구성원 탭에서 모두 보기 및 **구성원** **관리를** 선택합니다. 
  
4. 구성원 **추가를** 선택하고 추가할 게스트의 이름을 선택합니다.
    
5. **저장** 을 선택합니다.

디렉터리에 게스트를 직접 추가하려는 경우 [Azure Portal에서 Azure Active Directory B2B 공동](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)작업 사용자를 추가할 수 있습니다.

게스트의 정보를 편집하려는 경우 Azure Active Directory 를 사용하여 사용자의 프로필 정보를 추가하거나 [업데이트할 수 있습니다.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

## <a name="see-also"></a>참고 항목

[특정 그룹에서 게스트 사용자 차단](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[Microsoft 365 관리 센터에서 그룹 구성원 관리](add-or-remove-members-from-groups.md)
  
[Azure Active Directory 액세스 검토](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
