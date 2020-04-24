---
title: 민감도 레이블을 사용하여 SharePoint Online 파일 보호
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: '요약: Azure Information Protection을 적용하여 극비 SharePoint Online 팀 사이트의 파일을 보호합니다.'
ms.openlocfilehash: 7d98ed6813e1c52ef2646cdbe402ab0bb3a50e3c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632183"
---
# <a name="protect-sharepoint-online-files-with-a-sensitivity-label"></a>민감도 레이블을 사용하여 SharePoint Online 파일 보호

이 문서의 단계를 사용하여 파일에 대한 암호화 및 권한을 제공하도록 민감도 레이블을 구성합니다. 이러한 파일은 극비 보호를 위해 구성된 SharePoint 라이브러리에 추가할 수 있습니다. 또는 사이트에서 직접 파일을 열고 레이블을 적용할 수 있습니다. 암호와 및 권한 보호는 사이트에서 다운로드할 때에도 파일과 함께 이동합니다. 

다음 단계는 이러한 사이트 내에서 SharePoint 사이트 및 파일에 대해 극비 보호를 구성하기 위한 보다 큰 솔루션의 일부입니다. 자세한 내용은 [SharePoint Online 사이트 및 파일 보호](../security/office-365-security/secure-sharepoint-online-sites-and-files.md)를 참조하세요. 

SharePoint Online의 파일에 대해 민감도 레이블을 사용하는 것이 모든 고객에게 권장되는 것은 아니지만 일부 파일에 대해 이러한 수준의 보호가 필요한 고객에게는 적절할 수 있습니다.

이 솔루션에 대한 몇 가지 중요 참고 사항은 다음과 같습니다.
- 조직에서 [SharePoint 및 OneDrive의 Office 파일에 대해 민감도 레이블을 사용(공개 미리보기)](/microsoft-365/compliance/sensitivity-labels-sharepoint-onedrive-files)하도록 설정하지 않은 경우: Office 365에 저장된 파일에 암호화가 적용되어 있으면 이 파일의 내용을 처리할 수 없습니다. 즉 공동 작성, eDiscovery, 검색, Delve 및 기타 공동 작업 기능이 작동하지 않습니다. DLP(데이터 손실 방지) 정책은 메타데이터(레이블 포함)에만 작동할 수 있지만, 파일의 내용(예: 파일 내의 신용 카드 번호)에는 작동할 수 없습니다.

- 이 솔루션을 사용하려면 사용자가 보호를 적용할 레이블을 선택해야 합니다. 자동 암호화 및 SharePoint에서 파일을 색인화하고 검사하는 기능이 필요한 경우 SharePoint Online에서 IRM (정보 권한 관리)을 사용하는 것이 좋습니다. IRM에 대해 SharePoint 라이브러리를 구성하면 파일은 편집을 위해 다운로드될 때 자동으로 암호화됩니다.  SharePoint IRM에는 결정에 영향을 줄 수 있는 제한 사항이 포함되어 있습니다. 자세한 내용은 [SharePoint 관리 센터의 IRM (정보 권한 관리) 설정](https://support.office.com/article/Set-up-Information-Rights-Management-IRM-in-SharePoint-admin-center-239CE6EB-4E81-42DB-BF86-A01362FED65C)을 참조합니다.

## <a name="admin-setup"></a>관리자 설정

특정 SharePoint Online 팀 사이트에 저장된 파일에 대한 보안 수준을 추가적으로 설정하려면, 고유의 레이블이나 높은 규제 대상 데이터를 위한 일반 레이블의 하위 레이블인 사용자 지정 민감도 레이블을 구성해야 합니다. SharePoint Online 팀 사이트의 Microsoft 365 그룹 구성원만 레이블 목록에서 사용자 지정된 레이블 또는 하위 레이블을 볼 수 있습니다.

- 전역적인 사용과 개별적 개인 팀에 소수의 레이블이 필요한 경우에는 민감도 레이블을 사용합니다.

- 다수의 레이블을 보유하고 있거나 극비 파일에 일반 레이블로 극비 팀의 레이블을 구성하려는 경우 민감도 하위 레이블을 사용합니다.

[이 지침](encryption-sensitivity-labels.md)을 사용하여 다음의 설정으로 개별 레이블이나 하위 레이블을 구성합니다.

- 레이블 또는 하위 레이블 이름은 팀 사이트 이름을 포함합니다.
- 암호화를 사용하도록 설정됩니다.
- 팀 사이트의 Microsoft 365 그룹은 공동 작성 권한을 가집니다.

작성한 후에는 사용자를 위해 새 레이블이나 하위 레이블을 게시합니다. 사용자는 레이블을 팀에 업로드하기 전에 로컬에서 파일에 적용하거나 파일이 팀에 저장된 후에 파일에 적용할 수 있습니다.
 
사용자가 Microsoft Word, Excel 및 PowerPoint의 **홈** 리본에 있는 **민감도** 옵션에서 민감도 레이블을 선택할 수 있습니다.
  
> [!NOTE]
> 극비 SharePoint Online 팀 사이트가 여러 개인 경우 여러 개의 민감도 레이블을 만들어야 합니다. 
  
## <a name="adding-permissions-for-external-users"></a>외부 사용자에 대한 권한 추가
민감도 레이블로 보호된 파일에 대한 액세스 권한을 외부 사용자에게 부여할 수 있는 두 가지 방법이 있습니다. 두 경우 모두 외부 사용자에게 Azure AD 계정이 있어야 합니다. 외부 사용자가 Azure AD를 사용하는 조직의 구성원이 아닌 경우 [https://aka.ms/aip-signup](https://aka.ms/aip-signup) 등록 페이지를 사용하여 Azure AD 계정을 개별로 가져올 수 있습니다.

 - 팀 사이트의 Microsoft 365 그룹에 외부 사용자를 추가합니다. 먼저 디렉터리에 계정을 B2B 사용자로 추가해야 합니다. [Azure Rights Management에서 그룹 구성원 자격을 캐시](https://docs.microsoft.com/azure/information-protection/plan-design/prepare#group-membership-caching-by-azure-information-protection)하는 데 몇 시간이 걸릴 수 있습니다.  
 - 직접 외부 사용자 계정을 레이블 구성에 추가합니다. 조직의 모든 사용자(예: Fabrikam.com), Microsoft 365 그룹(예: 조직 내의 재무 그룹) 또는 사용자를 추가할 수 있습니다. 예를 들어 민감도 레이블의 권한에 외부 규제자 팀을 추가할 수 있습니다.

## <a name="see-also"></a>참고 항목

[정치적 캠페인, 비영리 조직 및 기타 기밀 조직에 대한 Microsoft 보안 지침](/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[클라우드 도입 및 하이브리드 솔루션](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
