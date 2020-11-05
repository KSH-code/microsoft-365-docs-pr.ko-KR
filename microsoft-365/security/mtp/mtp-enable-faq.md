---
title: Microsoft 365 Defender를 켤 때 자주 묻는 질문
description: Microsoft 365 Defender를 사용 하는 것과 관련 된 라이선스, 사용 권한, 초기 설정 및 기타 제품 및 서비스에 대 한 가장 일반적인 질문과 대답을 볼 수 있습니다.
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
ms.openlocfilehash: 3dae9f208f5bb08d694322eb9f7cff35986930da
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920493"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="23db2-104">Microsoft 365 Defender를 켤 때 자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="23db2-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="23db2-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="23db2-105">**Applies to:**</span></span>
- <span data-ttu-id="23db2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="23db2-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="23db2-107">필수 라이선스 및 사용 권한, 지원 서비스 배포 및 초기 설정을 포함 하 여 [Microsoft 365 Defender](microsoft-threat-protection.md)를 켜는 방법에 대해 자주 묻는 질문에 대 한 답변을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="23db2-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-threat-protection.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="23db2-108">서비스를 설정 하는 방법에 대 한 자세한 내용은 [Microsoft 365 Defender On turn을 읽어 보십시오](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="23db2-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="23db2-109">Microsoft 365 E5 라이선스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23db2-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="23db2-110">여전히 Microsoft 365 Defender를 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="23db2-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="23db2-111">다음 E5 이외의 라이선스가 있는 고객은 Microsoft 365 Defender를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23db2-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="23db2-112">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="23db2-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="23db2-113">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="23db2-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="23db2-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="23db2-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="23db2-115">Defender for Office 365 (요금제 2)</span><span class="sxs-lookup"><span data-stu-id="23db2-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="23db2-116">지원 되는 라이선스의 전체 목록을 보려면 [라이선스 요구 사항을 참조](prerequisites.md#licensing-requirements)하세요.</span><span class="sxs-lookup"><span data-stu-id="23db2-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="23db2-117">Microsoft 365 Defender를 사용 하 여 시작 하려면 모든 것을 설치 하거나 배포 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="23db2-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="23db2-118">아니요, Microsoft 365 Defender는 이미 배포한 Microsoft 365 보안 서비스의 데이터를 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="23db2-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="23db2-119">이 기능을 켜면 인시던트, 자동화 및 찾기 환경이 배포 된 제품의 범위 내에서 작동 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23db2-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="23db2-120">이러한 제품이 제대로 배포 되지 않은 경우 Microsoft 365 Defender에는 데이터가 표시 되지 않으며 어떤 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23db2-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="23db2-121">Microsoft 365 Defender 환경을 최적화 하려면 지원 되는 *모든* [Microsoft 365 보안 제품 및 서비스](deploy-supported-services.md)를 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="23db2-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="23db2-122">Microsoft 365 Defender에서 내 데이터를 처리 하 고 저장 하는 위치</span><span class="sxs-lookup"><span data-stu-id="23db2-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="23db2-123">Microsoft 365 Defender는 통합 데이터가 처리 되 고 저장 되는 데이터 센터의 최적의 위치를 자동으로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="23db2-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="23db2-124">Endpoint 용 Microsoft Defender가 있는 경우에는 Defender for Endpoint에서 사용 하는 것과 동일한 위치를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="23db2-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="23db2-125">끝점에 대 한 Microsoft Defender Azure Defender를 통해 켜면 EU (유럽 연합) 데이터 센터를 자동으로 프로 비전 합니다.</span><span class="sxs-lookup"><span data-stu-id="23db2-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="23db2-126">Microsoft 365 Defender는 이러한 방식으로 끝점에 대 한 Microsoft Defender를 프로 비전 한 고객을 위해 동일한 EU 데이터 센터를 자동으로 프로 비전 합니다.</span><span class="sxs-lookup"><span data-stu-id="23db2-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="23db2-127">데이터 센터 위치는 Microsoft 365 Defender ( **settings > microsoft 365 defender** )의 설정 페이지에서 서비스가 프로 비전 되기 전과 후에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23db2-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender ( **Settings > Microsoft 365 Defender** ).</span></span> <span data-ttu-id="23db2-128">다른 데이터 센터 위치를 사용 하려면 microsoft 365 보안 센터에서 Microsoft 지원 서비스에 문의 **하세요** .를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="23db2-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="23db2-129">Microsoft 365 Defender에 액세스할 수 있는 위치</span><span class="sxs-lookup"><span data-stu-id="23db2-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="23db2-130">Microsoft 365 Defender는 Microsoft 365 보안 센터에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23db2-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="23db2-131">보안 센터로 이동 하 여 URL을 찾습니다 [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="23db2-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="23db2-132">Microsoft 365 보안 센터에서 Microsoft 365 Defender에 액세스 하는 데 필요한 사용 권한은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="23db2-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="23db2-133">다음 Azure AD (Active Directory) 역할이 할당 된 계정은 Microsoft 365 Defender 기능 및 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23db2-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="23db2-134">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="23db2-134">Global administrator</span></span>
- <span data-ttu-id="23db2-135">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="23db2-135">Security administrator</span></span>
- <span data-ttu-id="23db2-136">보안 운영자</span><span class="sxs-lookup"><span data-stu-id="23db2-136">Security Operator</span></span>
- <span data-ttu-id="23db2-137">전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="23db2-137">Global Reader</span></span>
- <span data-ttu-id="23db2-138">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="23db2-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="23db2-139">끝점에 대 한 Microsoft Defender의 역할 기반 액세스 제어 설정은 데이터에 대 한 액세스에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="23db2-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="23db2-140">자세한 내용은 [Microsoft 365 Defender에 대 한 액세스 관리](mtp-permissions.md)정보를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="23db2-140">For more information, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="23db2-141">Microsoft 365 Defender 기본값은 어떤 표준 시간대 입니까?</span><span class="sxs-lookup"><span data-stu-id="23db2-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="23db2-142">기본적으로 Microsoft 365 Defender는 시간 정보를 UTC 표준 시간대에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="23db2-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="23db2-143">현지 표준 시간대를 사용 하도록이 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23db2-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="23db2-144">표준 시간대 설정에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="23db2-144">Learn about setting the time zone</span></span>](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="23db2-145">새로운 Microsoft 365 Defender 기능 및 UI 업데이트에 대 한 자세한 내용은 어떻게 확인할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="23db2-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="23db2-146">Microsoft는 다음을 비롯 한 다양 한 채널을 통해 정보를 정기적으로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="23db2-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="23db2-147">Microsoft 365 관리 센터의 [메시지 센터](../../admin/manage/message-center.md)</span><span class="sxs-lookup"><span data-stu-id="23db2-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="23db2-148">[Microsoft 365 보안 & 준수 기술 커뮤니티](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance) 의 blogposts</span><span class="sxs-lookup"><span data-stu-id="23db2-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="23db2-149">[미리 보기 기능](preview.md)을 설정 하 여 공개적으로 사용 가능한 최신 환경을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="23db2-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="23db2-150">Microsoft 365 Defender는 GCC (미국 정부 커뮤니티 클라우드) 또는 높은 gcc (최고)에 게 제공 됩니까?</span><span class="sxs-lookup"><span data-stu-id="23db2-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="23db2-151">현재는 사용불가합니다. </span><span class="sxs-lookup"><span data-stu-id="23db2-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="23db2-152">관련 항목</span><span class="sxs-lookup"><span data-stu-id="23db2-152">Related topics</span></span>

- [<span data-ttu-id="23db2-153">Microsoft 365 Defender 개요</span><span class="sxs-lookup"><span data-stu-id="23db2-153">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- <span data-ttu-id="23db2-154">[Microsoft 365 Defender를 켜십시오](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="23db2-154">[Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>
- [<span data-ttu-id="23db2-155">라이선스 요구 사항 및 기타 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="23db2-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="23db2-156">지원 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="23db2-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="23db2-157">미리 보기 기능 설정</span><span class="sxs-lookup"><span data-stu-id="23db2-157">Turn on preview features</span></span>](preview.md)
