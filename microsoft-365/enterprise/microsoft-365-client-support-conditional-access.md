---
title: 'Microsoft 365 클라이언트 앱 지원: 조건부 액세스'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
f1.keywords:
- NOCSH
description: 이 문서에서는 Microsoft 365에 대한 조건부 액세스를 지원하는 플랫폼, 클라이언트 및 PowerShell 모듈에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7b0b65ea25091aad01fd8741f9925f2b545e9c4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904969"
---
# <a name="microsoft-365-client-app-support-conditional-access"></a>Microsoft 365 클라이언트 앱 지원: 조건부 액세스

최신 작업 공간에서 사용자는 어디서나 다양한 장치 및 앱을 사용하여 조직의 리소스에 액세스할 수 있습니다. 따라서 리소스에 액세스할 수 있는 사람에 집중하는 것만으로는 더 이상 충분하지 않습니다. 또한 조직은 액세스 제어 인프라에서 리소스에 액세스하는 방법 및 위치를 지원해야 합니다.

Azure Active Directory 장치, 위치 및 다단계 인증 기반 조건부 액세스를 사용하여 이 새로운 요구 사항을 충족할 수 있습니다. 조건부 액세스는 특정 조건에 따라 중앙 위치에서 관리되는 환경의 앱에 대한 액세스에 대한 제어를 적용할 수 있도록 하는 Azure Active Directory의 기능입니다.

[Azure Active Directory 조건부 액세스에 대해 자세히 알아보십시오.](/azure/active-directory/conditional-access/)

## <a name="supported-clients--platforms"></a>지원되는 & 플랫폼

다음 클라이언트 및 플랫폼의 최신 버전은 조건부 액세스를 지원합니다. Microsoft 365의 플랫폼 지원에 대한 자세한 내용은 [Microsoft 365의 시스템 요구 사항을 참조하세요.](/microsoft-365/microsoft-365-and-office-resources)
<br>
<br>

[!INCLUDE [Conditional access services support table](../includes/microsoft-365-client-support-conditional-access-include.md)]

## <a name="supported-powershell-modules"></a>지원되는 PowerShell 모듈

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint 온라인 PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
