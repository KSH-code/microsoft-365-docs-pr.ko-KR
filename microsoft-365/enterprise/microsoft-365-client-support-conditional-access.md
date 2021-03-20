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
# <a name="microsoft-365-client-app-support-conditional-access"></a><span data-ttu-id="6513b-103">Microsoft 365 클라이언트 앱 지원: 조건부 액세스</span><span class="sxs-lookup"><span data-stu-id="6513b-103">Microsoft 365 Client App Support: Conditional Access</span></span>

<span data-ttu-id="6513b-104">최신 작업 공간에서 사용자는 어디서나 다양한 장치 및 앱을 사용하여 조직의 리소스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6513b-104">In the modern workplace, users can access your organization's resources using various devices and apps from anywhere.</span></span> <span data-ttu-id="6513b-105">따라서 리소스에 액세스할 수 있는 사람에 집중하는 것만으로는 더 이상 충분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6513b-105">As a result, just focusing on who can access a resource is not sufficient anymore.</span></span> <span data-ttu-id="6513b-106">또한 조직은 액세스 제어 인프라에서 리소스에 액세스하는 방법 및 위치를 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6513b-106">Your organization must also support how and where a resource is accessed in your access control infrastructure.</span></span>

<span data-ttu-id="6513b-107">Azure Active Directory 장치, 위치 및 다단계 인증 기반 조건부 액세스를 사용하여 이 새로운 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6513b-107">With Azure Active Directory device, location, and multi-factor authentication-based Conditional Access, you can meet this new requirement.</span></span> <span data-ttu-id="6513b-108">조건부 액세스는 특정 조건에 따라 중앙 위치에서 관리되는 환경의 앱에 대한 액세스에 대한 제어를 적용할 수 있도록 하는 Azure Active Directory의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="6513b-108">Conditional Access is a capability of Azure Active Directory that enables you to enforce controls on the access to apps in your environment, all based on specific conditions and managed from a central location.</span></span>

<span data-ttu-id="6513b-109">[Azure Active Directory 조건부 액세스에 대해 자세히 알아보십시오.](/azure/active-directory/conditional-access/)</span><span class="sxs-lookup"><span data-stu-id="6513b-109">Learn more about [Azure Active Directory Conditional Access](/azure/active-directory/conditional-access/).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="6513b-110">지원되는 & 플랫폼</span><span class="sxs-lookup"><span data-stu-id="6513b-110">Supported clients & platforms</span></span>

<span data-ttu-id="6513b-111">다음 클라이언트 및 플랫폼의 최신 버전은 조건부 액세스를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6513b-111">The latest versions of the following clients and platforms support conditional access.</span></span> <span data-ttu-id="6513b-112">Microsoft 365의 플랫폼 지원에 대한 자세한 내용은 [Microsoft 365의 시스템 요구 사항을 참조하세요.](/microsoft-365/microsoft-365-and-office-resources)</span><span class="sxs-lookup"><span data-stu-id="6513b-112">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Conditional access services support table](../includes/microsoft-365-client-support-conditional-access-include.md)]

## <a name="supported-powershell-modules"></a><span data-ttu-id="6513b-113">지원되는 PowerShell 모듈</span><span class="sxs-lookup"><span data-stu-id="6513b-113">Supported PowerShell modules</span></span>

- [<span data-ttu-id="6513b-114">Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="6513b-114">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [<span data-ttu-id="6513b-115">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="6513b-115">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="6513b-116">SharePoint 온라인 PowerShell</span><span class="sxs-lookup"><span data-stu-id="6513b-116">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
