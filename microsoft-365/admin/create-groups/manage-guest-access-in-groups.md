---
title: 그룹에서 게스트 Microsoft 365 관리
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: 게스트 그룹에 게스트를 추가하고, Microsoft 365 사용자를 보고, PowerShell을 사용하여 게스트 액세스를 제어하는 방법을 학습합니다.
ms.openlocfilehash: 5d4e28234f539a8b4674b2fb3e2d01919fd0afdf
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59774907"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>그룹에서 게스트 Microsoft 365 관리

기본적으로 Microsoft 365 그룹에 대한 게스트 액세스는 조직에 대해 설정됩니다. 관리자는 전체 조직에 대한 그룹 또는 개별 그룹에 대한 게스트 액세스를 허용할지 여부를 제어할 수 있습니다.

이 설정이 켜져 있는 경우 그룹 구성원은 웹에서 사이트를 통해 Microsoft 365 사용자를 Outlook 수 있습니다. 승인을 위해 그룹 소유자에게 초대가 전송됩니다.

승인되면 게스트 사용자가 디렉터리 및 그룹에 추가됩니다.

> [!Note]
> Yammer Enterprise 또는 [EU 지역은](/yammer/manage-security-and-compliance/manage-data-compliance) 네트워크 게스트를 지원하지 않습니다.
> Microsoft 365 연결된 Yammer 그룹은 현재 게스트 액세스를 지원하지 않지만 연결되지 않은 외부 그룹을 Yammer 있습니다. 자세한 [내용은 2013에서](/yammer/work-with-external-users/create-and-manage-external-groups) 외부 그룹 만들기 및 Yammer 참조하세요.

그룹에서 게스트 액세스는 일반적으로 그룹 또는 그룹이 포함된 더 광범위한 시나리오의 일부로 SharePoint Teams. 이러한 서비스에는 자체 게스트 공유 설정이 있습니다. 그룹, 그룹 및 그룹별 게스트 공유를 설정하기 위한 전체 SharePoint Teams 참조하세요.

- [게스트와 현장에서 공동 작업하기](../../solutions/collaborate-in-site.md)
- [게스트와 팀으로 공동 작업하기](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>그룹 게스트 액세스 관리

그룹에서 게스트 액세스를 사용하도록 설정하거나 사용하지 않도록 설정하려면 그룹 에서 설정할 수 <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**있습니다.**</a>

1. 관리 센터에서 모든  설정 설정 표시로 이동하고 서비스 탭에서 그룹 Microsoft 365 \>  \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**선택합니다.**</a> 
  
2. Microsoft 365 **그룹** 페이지에서 조직 외부의 사람이 그룹 리소스에 액세스할 수 있도록 할지 아니면 그룹 소유자가 조직 외부의 사용자 그룹을 그룹에 추가할 수 있도록 할지 선택합니다.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>관리 센터에서 Microsoft 365 그룹에 게스트 추가

게스트가 디렉터리에 이미 있는 경우 에서 그룹에 게스트를 추가할 <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">수 Microsoft 365 관리 센터.</a> 동적 구성원이 있는 그룹은 에서 [관리해야 Azure Active Directory.](/azure/active-directory/enterprise-users/groups-create-rule)
  
1. 관리 센터에서 그룹 **그룹으로**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**이동하세요.**</a>
  
2. 게스트를 추가할 그룹을 클릭하고 구성원 탭에서 모두 보기 및 **구성원** **관리를** 선택합니다. 
  
4. 구성원 **추가를** 선택하고 추가할 게스트의 이름을 선택합니다.
    
5. **저장** 을 선택합니다.

디렉터리에 게스트를 직접 추가하려는 경우 Azure Portal에서 Azure Active Directory [B2B](/azure/active-directory/b2b/add-users-administrator)공동 작업 사용자를 추가할 수 있습니다.

게스트의 정보를 편집하려는 경우 를 사용하여 사용자의 프로필 정보를 추가하거나 업데이트할 [Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

## <a name="related-content"></a>관련 콘텐츠

[특정 그룹에서](../../solutions/per-group-guest-access.md) 게스트 사용자 차단(문서)\
[그룹 구성원 자격 관리](add-or-remove-members-from-groups.md) Microsoft 365 관리 센터(문서)\
[Azure Active Directory 액세스](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) 검토(문서)\
[Set-AzureADUser(문서)](/powershell/module/azuread/set-azureaduser)