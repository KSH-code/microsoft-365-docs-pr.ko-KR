---
title: Microsoft Threat Protection을 켤 때 자주 묻는 질문
description: Microsoft Threat Protection을 사용 하도록 설정 하는 것과 관련 된 라이선스, 사용 권한, 초기 설정 및 기타 제품 및 서비스에 대 한 가장 일반적인 질문과 대답을 볼 수 있습니다.
keywords: 자주 묻는 질문, FAQ, GCC, 시작, MTP 사용, Microsoft Threat Protection, M365, 보안, 데이터 위치, 필수 권한, 라이선스 자격, 설정 페이지
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 6b0d8d9be0cc84e61a3228f79fc14f1bfc9f8a83
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198842"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-threat-protection"></a><span data-ttu-id="e9271-104">Microsoft Threat Protection을 켤 때 자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="e9271-104">Frequently asked questions when turning on Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e9271-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="e9271-105">**Applies to:**</span></span>
- <span data-ttu-id="e9271-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="e9271-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="e9271-107">필수 라이선스 및 사용 권한, 지원 서비스 배포 및 초기 설정을 포함 하 여 [Microsoft Threat Protection](microsoft-threat-protection.md)을 설정 하는 방법에 대 한 가장 일반적인 질문에 대 한 답변을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9271-107">Read responses to the most commonly asked questions about turning on [Microsoft Threat Protection](microsoft-threat-protection.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="e9271-108">서비스를 설정 하는 방법에 대 한 자세한 내용은 [Microsoft Threat Protection 사용을 참조](mtp-enable.md)하십시오.</span><span class="sxs-lookup"><span data-stu-id="e9271-108">For instructions on how to turn on the service, [read Turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-threat-protection"></a><span data-ttu-id="e9271-109">Microsoft 365 E5 라이선스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e9271-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="e9271-110">여전히 Microsoft Threat Protection을 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="e9271-110">Can I still use Microsoft Threat Protection?</span></span>

<span data-ttu-id="e9271-111">다음과 같은 E5 이외의 라이선스를 가진 고객은 Microsoft Threat Protection을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9271-111">Customers with the following non-E5 licenses can use Microsoft Threat Protection:</span></span>

- <span data-ttu-id="e9271-112">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e9271-112">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="e9271-113">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e9271-113">Azure Advanced Threat Protection</span></span>
- <span data-ttu-id="e9271-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e9271-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="e9271-115">Office 365 Advanced Threat Protection (계획 2)</span><span class="sxs-lookup"><span data-stu-id="e9271-115">Office 365 Advanced Threat Protection (Plan 2)</span></span>
 
<span data-ttu-id="e9271-116">지원 되는 라이선스의 전체 목록을 보려면 [라이선스 요구 사항을 참조](prerequisites.md#licensing-requirements)하세요.</span><span class="sxs-lookup"><span data-stu-id="e9271-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-threat-protection"></a><span data-ttu-id="e9271-117">Microsoft Threat Protection을 사용 하 여 시작 하려면 모든 것을 설치 하거나 배포 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="e9271-117">Do I need to install or deploy anything to start using Microsoft Threat Protection?</span></span>

<span data-ttu-id="e9271-118">아니요, Microsoft Threat Protection은 이미 배포한 Microsoft 365 보안 서비스의 데이터를 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9271-118">No, Microsoft Threat Protection consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="e9271-119">이 기능을 켜면 인시던트, 자동화 및 찾기 환경이 배포 된 제품의 범위 내에서 작동 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9271-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="e9271-120">이러한 제품이 제대로 배포 되지 않은 경우 Microsoft Threat Protection은 데이터를 표시 하지 않으며 어떤 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e9271-120">If none of these products are properly deployed, Microsoft Threat Protection will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="e9271-121">Microsoft Threat Protection 환경을 최적화 하기 위해 지원 되는 *모든* [Microsoft 365 보안 제품 및 서비스](deploy-supported-services.md)를 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e9271-121">To optimize your Microsoft Threat Protection experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-threat-protection-process-and-store-my-data"></a><span data-ttu-id="e9271-122">Microsoft Threat Protection에서 데이터를 처리 하 고 저장 하는 위치</span><span class="sxs-lookup"><span data-stu-id="e9271-122">Where does Microsoft Threat Protection process and store my data?</span></span>
<span data-ttu-id="e9271-123">Microsoft Threat Protection은 통합 데이터가 처리 되 고 저장 되는 데이터 센터에 대 한 최적의 위치를 자동으로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9271-123">Microsoft Threat Protection automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="e9271-124">Microsoft Defender ATP가 있으면 Microsoft Defender ATP에서 사용 하는 것과 동일한 위치를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9271-124">If you have Microsoft Defender ATP, it selects the same location used by Microsoft Defender ATP.</span></span>

>[!NOTE]
><span data-ttu-id="e9271-125">Azure 보안 센터를 통해 설정 하는 경우 Microsoft Defender ATP는 EU (유럽 연합) 데이터 센터를 자동으로 프로 비전 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9271-125">Microsoft Defender ATP automatically provisions in European Union (EU) data centers when turned on through Azure Security Center.</span></span> <span data-ttu-id="e9271-126">Microsoft Threat Protection은 이러한 방식으로 Microsoft Defender ATP를 프로 비전 한 고객을 위해 동일한 EU 데이터 센터를 자동으로 프로 비전 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9271-126">Microsoft Threat Protection will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender ATP in this manner.</span></span> 

<span data-ttu-id="e9271-127">데이터 센터 위치는 Microsoft Threat Protection (**설정 > Microsoft Threat protection**)에 대 한 설정 페이지에서 서비스가 프로 비전 되기 전과 후에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9271-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft Threat Protection (**Settings > Microsoft Threat Protection**).</span></span> <span data-ttu-id="e9271-128">다른 데이터 센터 위치를 사용 하려면 microsoft 365 보안 센터에서 Microsoft 지원 서비스에 문의 **하세요** .를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9271-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-threat-protection"></a><span data-ttu-id="e9271-129">Microsoft Threat Protection에 액세스할 수 있는 위치</span><span class="sxs-lookup"><span data-stu-id="e9271-129">Where can I access Microsoft Threat Protection?</span></span>

<span data-ttu-id="e9271-130">Microsoft Threat Protection은 Microsoft 365 보안 센터에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9271-130">Microsoft Threat Protection is available in Microsoft 365 security center.</span></span> <span data-ttu-id="e9271-131">보안 센터로 이동 하 여 URL을 찾습니다 [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="e9271-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-threat-protection-in-microsoft-365-security-center"></a><span data-ttu-id="e9271-132">Microsoft 365 보안 센터에서 Microsoft 위협 보호에 액세스 하는 데 필요한 사용 권한은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="e9271-132">What permissions do I need to access Microsoft Threat Protection in Microsoft 365 security center?</span></span>

<span data-ttu-id="e9271-133">다음 Azure AD(Active Directory) 역할이 할당 된 계정은 Microsoft 위협 방지 기능 및 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9271-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft Threat Protection functionality and data:</span></span>

- <span data-ttu-id="e9271-134">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="e9271-134">Global administrator</span></span>
- <span data-ttu-id="e9271-135">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="e9271-135">Security administrator</span></span>
- <span data-ttu-id="e9271-136">보안 운영자</span><span class="sxs-lookup"><span data-stu-id="e9271-136">Security Operator</span></span>
- <span data-ttu-id="e9271-137">전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="e9271-137">Global Reader</span></span>
- <span data-ttu-id="e9271-138">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="e9271-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="e9271-139">Microsoft Defender ATP의 역할 기반 액세스 제어 설정은 데이터에 대 한 액세스에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e9271-139">Role-based access control settings in Microsoft Defender ATP influence access to data.</span></span> <span data-ttu-id="e9271-140">자세한 내용은 [Microsoft Threat Protection에 대 한 액세스 관리](mtp-permissions.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e9271-140">For more information, read about [managing access to Microsoft Threat Protection](mtp-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-threat-protection-default-to"></a><span data-ttu-id="e9271-141">Microsoft Threat Protection이 기본적으로 어떤 표준 시간대에 있습니까?</span><span class="sxs-lookup"><span data-stu-id="e9271-141">What time zone does Microsoft Threat Protection default to?</span></span>
<span data-ttu-id="e9271-142">기본적으로 Microsoft Threat Protection은 시간 정보를 UTC 표준 시간대에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9271-142">By default, Microsoft Threat Protection displays time information in the UTC time zone.</span></span> <span data-ttu-id="e9271-143">현지 표준 시간대를 사용 하도록이 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9271-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="e9271-144">표준 시간대 설정에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="e9271-144">Learn about setting the time zone</span></span>](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-threat-protection-feature-and-ui-updates"></a><span data-ttu-id="e9271-145">새로운 Microsoft 위협 방지 기능 및 UI 업데이트에 대 한 자세한 내용은 어떻게 확인할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="e9271-145">How can I learn about new Microsoft Threat Protection feature and UI updates?</span></span>

<span data-ttu-id="e9271-146">Microsoft는 다음을 비롯 한 다양 한 채널을 통해 정보를 정기적으로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9271-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="e9271-147">Microsoft 365 관리 센터의 [메시지 센터](../../admin/manage/message-center.md)</span><span class="sxs-lookup"><span data-stu-id="e9271-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="e9271-148">[Microsoft 365 보안 & 준수 기술 커뮤니티](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance) 의 blogposts</span><span class="sxs-lookup"><span data-stu-id="e9271-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="e9271-149">[미리 보기 기능](preview.md)을 설정 하 여 공개적으로 사용 가능한 최신 환경을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e9271-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="e9271-150">GCC(미국 정부 커뮤니티 클라우드)나 GCC High에서 Microsoft Threat Protection을 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="e9271-150">Is Microsoft Threat Protection available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="e9271-151">현재는 사용불가합니다. </span><span class="sxs-lookup"><span data-stu-id="e9271-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e9271-152">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e9271-152">Related topics</span></span>

- [<span data-ttu-id="e9271-153">Microsoft 위협 방지 개요</span><span class="sxs-lookup"><span data-stu-id="e9271-153">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- <span data-ttu-id="e9271-154">[Microsoft Threat Protection을 사용 하도록 설정](mtp-enable.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e9271-154">[Turn on Microsoft Threat Protection](mtp-enable.md).</span></span>
- [<span data-ttu-id="e9271-155">라이선스 요구 사항 및 기타 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="e9271-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="e9271-156">지원 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="e9271-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="e9271-157">미리 보기 기능 설정</span><span class="sxs-lookup"><span data-stu-id="e9271-157">Turn on preview features</span></span>](preview.md)
