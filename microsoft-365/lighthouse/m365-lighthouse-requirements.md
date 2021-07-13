---
title: 요구 사항 Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: MSP(관리 서비스 공급자)의 경우 서비스 공급자를 사용하기 위한 요구 사항 목록을 Microsoft 365 Lighthouse.
ms.openlocfilehash: 9c87744053ffe3bace90534287cd2b81697f3554
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395354"
---
# <a name="requirements-for-microsoft-365-lighthouse"></a><span data-ttu-id="e49d7-103">요구 사항 Microsoft 365 Lighthouse</span><span class="sxs-lookup"><span data-stu-id="e49d7-103">Requirements for Microsoft 365 Lighthouse</span></span>

> [!NOTE]
> <span data-ttu-id="e49d7-104">이 문서에 설명된 기능은 미리 보기에 있으며 변경될 수 있으며 이 문서에 나열된 요구 사항을 충족하는 파트너만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e49d7-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the requirements listed in this article.</span></span> <span data-ttu-id="e49d7-105">조직에 등록이 Microsoft 365 Lighthouse 에 [등록을 Microsoft 365 Lighthouse.](m365-lighthouse-sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="e49d7-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="e49d7-106">Microsoft 365 Lighthouse SMB(관리 서비스 공급자)가 중소기업 고객을 위해 대규모로 장치, 데이터 및 사용자를 보호하고 관리하는 데 도움이 되는 관리 포털입니다.</span><span class="sxs-lookup"><span data-stu-id="e49d7-106">Microsoft 365 Lighthouse is an admin portal that helps Managed Service Providers (MSPs) secure and manage devices, data, and users at scale for small- and medium-sized business (SMB) customers.</span></span>  

<span data-ttu-id="e49d7-107">MSP는 CSP(클라우드 솔루션 공급자) 프로그램에 간접 대리업체 또는 직접 청구 파트너로 등록해야 Microsoft 365 Lighthouse.</span><span class="sxs-lookup"><span data-stu-id="e49d7-107">MSPs must be enrolled in the Cloud Solution Provider (CSP) program as an Indirect Reseller or Direct Bill partner to use Microsoft 365 Lighthouse.</span></span>  

<span data-ttu-id="e49d7-108">또한 각 MSP 고객 테넌트는 다음 요구 사항을 Microsoft 365 Lighthouse 자격을 상실해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e49d7-108">In addition, each MSP customer tenant must qualify for Microsoft 365 Lighthouse by meeting the following requirements:</span></span> 
 
- <span data-ttu-id="e49d7-109">MSP에 대한 DAP(위임된 관리자 권한)</span><span class="sxs-lookup"><span data-stu-id="e49d7-109">Delegated Admin Privileges (DAP) for the MSP</span></span> 
- <span data-ttu-id="e49d7-110">하나 이상의 Microsoft 365 Business Premium 라이선스</span><span class="sxs-lookup"><span data-stu-id="e49d7-110">At least one Microsoft 365 Business Premium license</span></span> 
- <span data-ttu-id="e49d7-111">라이선스가 있는 사용자 500명 미만</span><span class="sxs-lookup"><span data-stu-id="e49d7-111">Fewer than 500 licensed users</span></span>  

## <a name="requirements-for-enablingdevice-management"></a><span data-ttu-id="e49d7-112">장치 관리를 사용하도록 설정하기 위한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e49d7-112">Requirements for enabling device management</span></span>   

<span data-ttu-id="e49d7-113">장치 관리 페이지에서 고객 테넌트 장치를 표시하려면 MSP에서 다음을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e49d7-113">To view customer tenant devices on the device management pages, a MSP must:</span></span>    

- <span data-ttu-id="e49d7-114">MEM(Microsoft Endpoint Manager)에 모든 고객 장치를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="e49d7-114">Enroll all customer devices in Microsoft Endpoint Manager (MEM).</span></span><span data-ttu-id="e49d7-115">자세한 내용은 에서 [장치 등록을 Microsoft Intune.](/mem/intune/enrollment/)</span><span class="sxs-lookup"><span data-stu-id="e49d7-115"> For more information, see [Enroll devices in Microsoft Intune](/mem/intune/enrollment/).</span></span>
- <span data-ttu-id="e49d7-116">모든 고객 장치에 규정 준수 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="e49d7-116">Assign compliance policies to all customer devices.</span></span><span data-ttu-id="e49d7-117">자세한 내용은 [에서 준수 정책 만들기를 Microsoft Intune.](/mem/intune/protect/create-compliance-policy)</span><span class="sxs-lookup"><span data-stu-id="e49d7-117"> For more information, see [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).</span></span> 

## <a name="requirements-for-enabling-usermanagement"></a><span data-ttu-id="e49d7-118">사용자 관리를 사용하도록 설정하기 위한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e49d7-118">Requirements for enabling user management</span></span> 

<span data-ttu-id="e49d7-119">위험한 사용자, 다단계 인증 및 암호 재설정을 비롯한 사용자 관리 페이지에 대한 보고서에 고객 데이터를 표시하려면 고객 테넌트에 Azure Active Directory Premium P1 이상에 대한 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e49d7-119">For customer data to show up in reports on user management pages, including Risky users, Multifactor authentication, and Password reset, customer tenants must have licenses for Azure Active Directory Premium P1 or later.</span></span> <span data-ttu-id="e49d7-120">Azure AD Premium P1 포함된 Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="e49d7-120">Azure AD Premium P1 is included with Microsoft 365 Business Premium.</span></span>   

## <a name="requirements-for-enablingthreat-management"></a><span data-ttu-id="e49d7-121">위협 관리를 사용하도록 설정하기 위한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e49d7-121">Requirements for enabling threat management</span></span> 

<span data-ttu-id="e49d7-122">위협 관리 페이지에서 고객 테넌트 장치 및 위협을 표시하려면 모든 고객 테넌트 장치를 MEM(Microsoft Endpoint Manager)에 등록하고 해당 장치를 실행하여 보호해야 Microsoft Defender 바이러스 백신.</span><span class="sxs-lookup"><span data-stu-id="e49d7-122">To view customer tenant devices and threats on the threat management pages, you must enroll all customer tenant devices in Microsoft Endpoint Manager (MEM) and protect them by running Microsoft Defender Antivirus.</span></span>  

<span data-ttu-id="e49d7-123">자세한 내용은 에서 [장치 등록을 Microsoft Intune.](/mem/intune/enrollment/)</span><span class="sxs-lookup"><span data-stu-id="e49d7-123">For more information, see [Enroll devices in Microsoft Intune](/mem/intune/enrollment/).</span></span>  

<span data-ttu-id="e49d7-124">Microsoft Defender 바이러스 백신 Windows 운영 체제의 일부로, Windows 실행하는 장치에서 기본적으로 Windows 10.</span><span class="sxs-lookup"><span data-stu-id="e49d7-124">Microsoft Defender Antivirus is part of the Windows operating system and is enabled by default on devices running Windows 10.</span></span>  

> [!NOTE] 
> <span data-ttu-id="e49d7-125">Microsoft가 아닌 다른 바이러스 백신 솔루션을 사용 중이지 않은 경우 Microsoft Defender 바이러스 백신 Microsoft Defender 바이러스 백신 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e49d7-125">If you're using a non-Microsoft antivirus solution and not Microsoft Defender Antivirus, Microsoft Defender Antivirus is disabled automatically.</span></span> <span data-ttu-id="e49d7-126">Microsoft가 아닌 바이러스 백신 솔루션을 제거하면 Microsoft Defender 바이러스 백신 장치를 위협으로부터 보호하기 위해 Windows 자동으로 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="e49d7-126">When you uninstall the non-Microsoft antivirus solution, Microsoft Defender Antivirus is activated automatically to protect your Windows devices from threats.</span></span>    

## <a name="related-content"></a><span data-ttu-id="e49d7-127">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="e49d7-127">Related content</span></span>   

<span data-ttu-id="e49d7-128">[포털 Microsoft 365 Lighthouse](m365-lighthouse-configure-portal-security.md) 구성(문서)</span><span class="sxs-lookup"><span data-stu-id="e49d7-128">[Configure Microsoft 365 Lighthouse portal security](m365-lighthouse-configure-portal-security.md) (article)</span></span>\
<span data-ttu-id="e49d7-129">[Microsoft 365 Lighthouse 준수 페이지](m365-lighthouse-device-compliance-page-overview.md) 개요(문서)</span><span class="sxs-lookup"><span data-stu-id="e49d7-129">[Microsoft 365 Lighthouse Device compliance page overview](m365-lighthouse-device-compliance-page-overview.md) (article)</span></span>\
<span data-ttu-id="e49d7-130">[Microsoft 365 Lighthouse 페이지](m365-lighthouse-users-page-overview.md) 개요(문서)</span><span class="sxs-lookup"><span data-stu-id="e49d7-130">[Microsoft 365 Lighthouse Users page overview](m365-lighthouse-users-page-overview.md) (article)</span></span>\
<span data-ttu-id="e49d7-131">[Microsoft 365 Lighthouse 위협 관리 페이지](m365-lighthouse-threat-management-page-overview.md) 개요(문서)</span><span class="sxs-lookup"><span data-stu-id="e49d7-131">[Microsoft 365 Lighthouse Threat management page overview](m365-lighthouse-threat-management-page-overview.md) (article)</span></span>\
<span data-ttu-id="e49d7-132">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml)   (문서)</span><span class="sxs-lookup"><span data-stu-id="e49d7-132">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>

