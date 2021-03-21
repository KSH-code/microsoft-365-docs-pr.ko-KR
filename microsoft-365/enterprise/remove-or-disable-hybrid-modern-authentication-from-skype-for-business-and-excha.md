---
title: 비즈니스용 Skype 및 Exchange에서 하이브리드 최신 인증 제거 또는 사용 안 함
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/3/2017
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5a91b9e3-1508-475b-93e0-710fa5d5cd2d
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 비즈니스용 Skype 및 Exchange에서 하이브리드 최신 인증을 제거하거나 사용하지 않도록 설정하는 방법을 설명합니다.
ms.openlocfilehash: 9442ef3e19d0835bfd59f27ec425e36fd7dfcf7a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927291"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a><span data-ttu-id="3d973-103">비즈니스용 Skype 및 Exchange에서 하이브리드 최신 인증 제거 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="3d973-103">Removing or disabling Hybrid Modern Authentication from Skype for Business and Exchange</span></span>

<span data-ttu-id="3d973-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="3d973-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="3d973-105">HMA(하이브리드 최신 인증)를 사용하도록 설정하여 현재 환경에 부적소한 경우 HMA를 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d973-105">If you've enabled Hybrid Modern Authentication (HMA) only to find it's unsuitable for your current environment, you can disable HMA.</span></span> <span data-ttu-id="3d973-106">이 문서에서는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3d973-106">This article explains how.</span></span>
  
## <a name="who-is-this-article-for"></a><span data-ttu-id="3d973-107">이 문서는 누구를 위한 것인가요?</span><span class="sxs-lookup"><span data-stu-id="3d973-107">Who is this article for?</span></span>

<span data-ttu-id="3d973-108">비즈니스용 Skype Online 또는 On-premises 및/또는 Exchange Online 또는 On-premises에서 최신 인증을 사용하도록 설정하고 HMA를 사용하지 않도록 설정해야 하는 경우 이러한 단계가 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d973-108">If you've enabled Modern Authentication in Skype for Business Online or On-premises, and/or Exchange Online or On-premises and found you need to disable HMA, these steps are for you.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3d973-109">비즈니스용[Skype](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)Online 또는 On-premises에 있으며 혼합 토폴로지 HMA가 있으며 시작하기 전에 지원되는 토폴로지가 필요한 경우 ' 최신 인증에서 지원되는 비즈니스용 Skype 토폴로지' 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d973-109">See the '[Skype for Business topologies supported with Modern Authentication](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)' article if you're in Skype for Business Online or On-premises, have a mixed-topology HMA, and need to look at supported topologies before you begin.</span></span>
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a><span data-ttu-id="3d973-110">하이브리드 최신 인증(Exchange)을 사용하지 않도록 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="3d973-110">How to disable Hybrid Modern Authentication (Exchange)</span></span>

1. <span data-ttu-id="3d973-111">**Exchange On-premises:** Exchange 관리 셸을 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3d973-111">**Exchange On-premises**: Open the Exchange Management Shell and run the following commands:</span></span> 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. <span data-ttu-id="3d973-112">**Exchange Online:** 원격 PowerShell을 [사용하여 Exchange Online에](/powershell/exchange/connect-to-exchange-online-powershell) 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3d973-112">**Exchange Online**: [Connect to Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) with Remote PowerShell.</span></span> <span data-ttu-id="3d973-113">다음 명령을 실행하여  *OAuth2ClientProfileEnabled*  플래그를 'false'으로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="3d973-113">Run the following command to turn your  *OAuth2ClientProfileEnabled*  flag to 'false':</span></span>

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a><span data-ttu-id="3d973-114">하이브리드 최신 인증을 사용하지 않도록 설정하는 방법(비즈니스용 Skype)</span><span class="sxs-lookup"><span data-stu-id="3d973-114">How to disable Hybrid Modern Authentication (Skype for Business)</span></span>

1. <span data-ttu-id="3d973-115">**비즈니스용 Skype On-premises:** 비즈니스용 Skype 관리 셸에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3d973-115">**Skype for Business On-premises**: Run the following commands in Skype for Business Management Shell:</span></span>

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. <span data-ttu-id="3d973-116">**비즈니스용 Skype Online:** 원격 PowerShell을 사용하여 [비즈니스용 Skype Online에](manage-skype-for-business-online-with-microsoft-365-powershell.md) 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3d973-116">**Skype for Business Online**: [Connect to Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) with Remote PowerShell.</span></span> <span data-ttu-id="3d973-117">최신 인증을 사용하지 않도록 설정하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3d973-117">Run the following command to disable Modern Authentication:</span></span>

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

<span data-ttu-id="3d973-118">[최신 인증 개요로 다시 연결합니다.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="3d973-118">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md) .</span></span> 
