---
title: 그룹 비교하기
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 758759ad-63ee-4ea9-90a3-39f941897b7d
description: Microsoft 365 그룹 구성원은 대화, 파일, 일정 이벤트, Stream 및 플래너에 대한 그룹 전자 메일 및 공유 작업 영역을 가져옵니다.
ms.openlocfilehash: 0b622f791de7615e45e49faec47558b0e67067f2
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59184979"
---
# <a name="compare-groups"></a>그룹 비교

Microsoft 365 관리 센터의 <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**그룹**</a> 섹션에서 다음과 같은 유형의 그룹을 만들고 관리할 수 있습니다. 

- **Microsoft 365 그룹** 은 회사 내부 및 외부의 사용자 간의 공동 작업에 사용됩니다. 여기에는 SharePoint 및 Planner와 같은 공동 작업 서비스가 포함됩니다.
- **메일 그룹** 사용자 그룹에 전자 메일 알림을 보내는 데 사용됩니다.
- **보안 그룹** 은 SharePoint 사이트와 같은 리소스에 대한 액세스 권한을 부여하는 데 사용됩니다.
- **메일 사용이 가능한 보안 그룹** 은 SharePoint와 같은 리소스에 대한 액세스 권한을 부여하고 해당 사용자에게 전자 메일로 알림을 보내는 데 사용됩니다.
- **공유 사서함** 은 여러 사용자가 같은 사서함에 액세스해야 하는 경우(예: 회사 정보 또는 지원 전자 메일 주소)에 사용됩니다.

일부 그룹은 동적 멤버십이나 전자 메일을 허용합니다.

||Microsoft 365 그룹|메일 그룹|보안 그룹|메일 사용 가능 보안 그룹|공유 사서함|
|:----|:----|:----|:----|:----|:----|
|**메일 사용 가능**|예|예|아니요|예|예|
|**Microsoft Azure AD의 동적 멤버십**|예|아니요|예|아니요|아니요|

이러한 모든 그룹 유형은 Power Automate에서 사용할 수 있습니다.

## <a name="microsoft-365-groups"></a>Microsoft 365 그룹

Microsoft 365 그룹은 회사 내부 및 외부의 사용자 간의 공동 작업에 사용됩니다. 각 Microsoft 365 그룹에서 구성원은 대화, 파일, 일정 이벤트, Stream 및 플래너에 대한 그룹 전자 메일 및 공유 작업 영역을 가져옵니다.

[관리자에 의해 사용 가능하도록](manage-guest-access-in-groups.md) 설정한 경우 회사 외부 사용자를 그룹에 추가할 수 있습니다. 외부 보낸 사람이 그룹 전자 메일 주소로 전자 메일을 보낼 수 있도록 허용할 수도 있습니다.

Microsoft 365 그룹은 [Azure Active Directory에서 동적 구성원에 대해 구성](/azure/active-directory/users-groups-roles/groups-change-type)할 수 있습니다. 부서, 위치, 제목 등의 사용자 특성을 기반으로 그룹 구성원을 자동으로 추가하거나 제거할 수 있습니다.

Microsoft 365 그룹은 iOS용 Outlook 및 Android용 Outlook과 같은 모바일 앱을 통해 액세스할 수 있습니다.

[관리자에 의해 사용 가능하도록](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md) 설정한 경우 그룹 구성원은 그룹 전자 메일 주소를 보내기 혹은 대신하여 보낼 수 있습니다.

Microsoft 365 그룹은 다른 Microsoft 365 그룹이나 배포 또는 보안 그룹과의 중첩을 지원하지 않습니다.

## <a name="distribution-groups"></a>메일 그룹

[메일 그룹](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)은 사용자 그룹에 알림을 보내는 데 사용됩니다. 관리자에 의해 사용 가능하도록 설정한 경우 외부 전자메일을 받을 수 있습니다.

메일 그룹은 "A 빌딩의 사용자" 또는 "Contoso의 모든 사용자"와 같은 사용자 그룹 집합에 정보를 브로드캐스팅하는 경우에 가장 적합합니다.

배포 그룹은 [Microsoft 365 groups로 업그레이드](../manage/upgrade-distribution-lists.md) 할 수 있습니다.

메일 그룹은 Microsoft Teams에서 팀에 추가할 수 있습니다.

Microsoft 365 그룹은 배포 그룹의 구성원일 수 없습니다.

## <a name="security-groups"></a>보안 그룹

[보안 그룹](../email/create-edit-or-delete-a-security-group.md)은 SharePoint와 같은 Microsoft 365 리소스에 대한 액세스 권한을 부여하는 데 사용됩니다. 각 리소스에 사용자를 개별적으로 추가하는 것이 아니라 그룹을 관리하기만 하면 되므로 관리를 더 쉽게 수행할 수 있습니다.

보안 그룹에는 사용자 또는 장치가 포함될 수 있습니다. 장치에 대한 보안 그룹 만들기는 Intune과 같은 모바일 장치 관리 서비스와 함께 사용할 수 있습니다.

보안 그룹은 [Azure Active Directory에서 동적 구성원에 대해 구성](/azure/active-directory/users-groups-roles/groups-change-type)할 수 있습니다. 부서, 위치, 제목 등의 사용자 특성이나 운영 체제 버전 등의 장치 속성을 기반으로 그룹 구성원을 자동으로 추가하거나 제거할 수 있습니다.

보안 그룹을 팀에 추가할 수 있습니다.

Microsoft 365 그룹은 보안 그룹의 구성원일 수 없습니다.

## <a name="mail-enabled-security-groups"></a>메일 사용 가능 보안 그룹

메일 사용이 가능한 보안 그룹은 Azure Active Directory를 통해 동적으로 관리할 수 없으며 장치를 포함할 수 없는 경우를 제외하고 일반 보안 그룹과 동일하게 작동합니다.

해당 그룹의 모든 구성원에게 메일을 보낼 수 있는 기능이 포함됩니다.

메일 사용이 가능한 보안 그룹을 팀에 추가할 수 있습니다.

## <a name="shared-mailboxes"></a>공유 사서함

[공유 사서함](../email/create-a-shared-mailbox.md)은 여러 사용자가 같은 사서함에 액세스해야 하는 경우(예: 회사 정보 또는 지원 전자 메일 주소, 리셉션 데스크 또는 여러 사용자에 의해 공유될 수도 있는 기타 기능)에 사용됩니다.

관리자가 이 기능을 사용 가능하도록 설정한 경우 공유 사서함이 외부 전자 메일을 받을 수 있습니다.

공유 사서함에는 공동 작업에 사용할 수 있는 일정이 포함되어 있습니다.

그룹 사서함에 대한 권한이 있는 사용자는 관리자가 해당 사용자에게 권한을 부여한 경우 사서함 전자 메일 주소를 보내기 혹은 대신하여 보낼 수 있습니다. 이 기능은 사용자가 "Contoso 지원" 또는 “A 빌딩 리셉션 데스크"에서 전자 메일을 보낼 수 있기 때문에 도움말 및 지원 사서함에 특히 유용합니다.

Microsoft 365 그룹으로 공유 사서함을 마이그레이션할 수 없습니다. 

## <a name="related-content"></a>관련 콘텐츠

[Microsoft 365 그룹에 대해 자세히 알아보세요.](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Outlook에서 배포 목록을 Microsoft 365 그룹으로 업그레이드](/microsoft-365/admin/manage/upgrade-distribution-lists)

[Outlook에서 배포 목록을 그룹으로 업그레이드해야 하는 이유](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)
