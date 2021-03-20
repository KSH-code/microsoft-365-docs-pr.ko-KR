---
title: 'Microsoft 365 클라이언트 앱 지원: 단일 Sign-On'
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
description: 이 문서에서는 Microsoft 365에 대한 Single Sign-On을 지원하는 플랫폼, 클라이언트 및 PowerShell 모듈에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 63090e1284bda39fe2d79c80b829891e867d2365
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904909"
---
# <a name="microsoft-365-client-app-support-single-sign-on"></a><span data-ttu-id="2759e-103">Microsoft 365 클라이언트 앱 지원: 단일 Sign-On</span><span class="sxs-lookup"><span data-stu-id="2759e-103">Microsoft 365 Client App Support: Single Sign-On</span></span>

<span data-ttu-id="2759e-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="2759e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="2759e-105">SSO(Single Sign-On)는 사용자가 Azure Active Directory의 응용 프로그램에 로그인할 때 보안과 편의성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2759e-105">Single sign-on (SSO) adds security and convenience when your users sign-on to applications in Azure Active Directory.</span></span> <span data-ttu-id="2759e-106">Single Sign-On을 사용하면 사용자는 한 계정으로 한 번 로그인하여 사내 AD DS(Active Directory 도메인 서비스) 도메인 가입 장치, SaaS(Software as a Service) 응용 프로그램 및 웹 응용 프로그램에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="2759e-106">With single sign-on, users sign in once with one account to access on-premises Active Directory Domain Services (AD DS) domain-joined devices, software as a service (SaaS) applications, and web applications.</span></span>

<span data-ttu-id="2759e-107">Single [Sign-On에 대해 자세히 알아보시고.](/azure/active-directory/manage-apps/what-is-single-sign-on)</span><span class="sxs-lookup"><span data-stu-id="2759e-107">Learn more about [single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="2759e-108">지원되는 & 플랫폼</span><span class="sxs-lookup"><span data-stu-id="2759e-108">Supported clients & platforms</span></span>

<span data-ttu-id="2759e-109">다음 클라이언트 및 플랫폼의 최신 버전은 Single Sign-On을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2759e-109">The latest versions of the following clients and platforms support single sign-on.</span></span> <span data-ttu-id="2759e-110">Microsoft 365의 플랫폼 지원에 대한 자세한 내용은 [Microsoft 365의 시스템 요구 사항을 참조하세요.](/microsoft-365/microsoft-365-and-office-resources)</span><span class="sxs-lookup"><span data-stu-id="2759e-110">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Single sign-on services support table](../includes/microsoft-365-client-support-single-sign-on-include.md)]

## <a name="supported-powershell-modules"></a><span data-ttu-id="2759e-111">지원되는 PowerShell 모듈</span><span class="sxs-lookup"><span data-stu-id="2759e-111">Supported PowerShell modules</span></span>

- [<span data-ttu-id="2759e-112">Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="2759e-112">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [<span data-ttu-id="2759e-113">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="2759e-113">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="2759e-114">SharePoint 온라인 PowerShell</span><span class="sxs-lookup"><span data-stu-id="2759e-114">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
