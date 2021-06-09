---
title: 'Microsoft 365 클라이언트 앱 지원: 다단계 인증'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: 이 문서에서는 사용자에 대해 다단계 인증을 지원하는 플랫폼, 클라이언트 및 PowerShell 모듈에 대해 Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 80ee370526d17d472cd048cd4d89b862e158b631
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927567"
---
# <a name="microsoft-365-client-app-support-multi-factor-authentication"></a><span data-ttu-id="efb63-103">Microsoft 365 클라이언트 앱 지원: 다단계 인증</span><span class="sxs-lookup"><span data-stu-id="efb63-103">Microsoft 365 Client App Support: Multi-factor authentication</span></span>

<span data-ttu-id="efb63-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="efb63-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="efb63-105">로그인에 대한 추가 보안 수준을 제공하기 위해 클라이언트는 사용자 암호와 다음을 기반으로 하는 다른 사용자 확인 방법을 모두 사용하는 MFA(다단계 인증)를 사용하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb63-105">To provide an additional level of security for sign-ins, clients may be configured to use multi-factor authentication (MFA), which uses both a user password and another user verification method based on:</span></span>

- <span data-ttu-id="efb63-106">스마트폰과 같이 쉽게 복제되지 않는 소유의 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="efb63-106">Something  in their possession that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="efb63-107">지문, 얼굴 또는 기타 생체 인식 특성과 같이 사용자가 고유하고 품사적으로 가지고 있는 것</span><span class="sxs-lookup"><span data-stu-id="efb63-107">Something the user has uniquely and biologically, such as their fingerprints, face, or other biometric attribute</span></span>

<span data-ttu-id="efb63-108">다단계 [인증에 대해 자세히 알아보시고 을(를) 자세히 알아보아야 합니다.](/azure/active-directory/authentication/multi-factor-authentication)</span><span class="sxs-lookup"><span data-stu-id="efb63-108">Learn more about [multi-factor authentication](/azure/active-directory/authentication/multi-factor-authentication).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="efb63-109">지원되는 & 플랫폼</span><span class="sxs-lookup"><span data-stu-id="efb63-109">Supported clients & platforms</span></span>

<span data-ttu-id="efb63-110">다음 클라이언트 및 플랫폼의 최신 버전은 다단계 인증을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="efb63-110">The latest versions of the following clients and platforms support multi-factor authentication.</span></span> <span data-ttu-id="efb63-111">Microsoft 365 플랫폼 지원에 대한 자세한 내용은 에 대한 시스템 요구 [Microsoft 365.](/microsoft-365/microsoft-365-and-office-resources)</span><span class="sxs-lookup"><span data-stu-id="efb63-111">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Multi-factor authentication services support table](../includes/microsoft-365-client-support-modern-authentication-include.md)]

## <a name="supported-powershell-modules"></a><span data-ttu-id="efb63-112">지원되는 PowerShell 모듈</span><span class="sxs-lookup"><span data-stu-id="efb63-112">Supported PowerShell modules</span></span>

- [<span data-ttu-id="efb63-113">Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="efb63-113">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [<span data-ttu-id="efb63-114">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="efb63-114">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="efb63-115">SharePoint 온라인 PowerShell</span><span class="sxs-lookup"><span data-stu-id="efb63-115">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)