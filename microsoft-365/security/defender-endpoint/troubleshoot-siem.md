---
title: 끝점용 Microsoft Defender의 SIEM 도구 통합 문제 해결
description: Microsoft Defender for Endpoint에서 SIEM 도구를 사용할 때 발생할 수 있는 문제를 해결합니다.
keywords: 문제 해결, siem, 클라이언트 비밀, 비밀
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 9c4f3da57796903fc22314574f389bcdd92ca4b3
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311991"
---
# <a name="troubleshoot-siem-tool-integration-issues"></a><span data-ttu-id="732b2-104">SIEM 도구 통합 문제 해결</span><span class="sxs-lookup"><span data-stu-id="732b2-104">Troubleshoot SIEM tool integration issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="732b2-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="732b2-105">**Applies to:**</span></span>
- [<span data-ttu-id="732b2-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="732b2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="732b2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="732b2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="732b2-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="732b2-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="732b2-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="732b2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="732b2-110">SIEM 도구에서 검색을 끌어오는 동안 문제를 해결해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="732b2-110">You might need to troubleshoot issues while pulling detections in your SIEM tools.</span></span>

<span data-ttu-id="732b2-111">이 페이지에서는 발생할 수 있는 문제를 해결하기 위한 자세한 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="732b2-111">This page provides detailed steps to troubleshoot issues you might encounter.</span></span>


## <a name="learn-how-to-get-a-new-client-secret"></a><span data-ttu-id="732b2-112">새 클라이언트 비밀을 얻는 방법 학습</span><span class="sxs-lookup"><span data-stu-id="732b2-112">Learn how to get a new client secret</span></span>
<span data-ttu-id="732b2-113">클라이언트 비밀이 만료되거나 SIEM 도구 응용 프로그램을 사용하도록 설정하는 경우 제공된 복사본을 잘못 저장한 경우 새 비밀을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="732b2-113">If your client secret expires or if you've misplaced the copy provided when you were enabling the SIEM tool application,  you'll need to get a new secret.</span></span>

1. <span data-ttu-id="732b2-114">Azure 관리 [포털에 로그인합니다.](https://portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="732b2-114">Login to the [Azure management portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="732b2-115">**Azure Active Directory** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="732b2-115">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="732b2-116">테넌트 선택</span><span class="sxs-lookup"><span data-stu-id="732b2-116">Select your tenant.</span></span>

4. <span data-ttu-id="732b2-117">앱 **등록 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="732b2-117">Click **App registrations**.</span></span> <span data-ttu-id="732b2-118">그런 다음 응용 프로그램 목록에서 응용 프로그램을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="732b2-118">Then in the applications list, select the application.</span></span>

5. <span data-ttu-id="732b2-119">인증서 **& 섹션을** 선택하고 새 클라이언트 비밀을 클릭한 다음 설명을 제공하고 유효 기간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="732b2-119">Select **Certificates & Secrets** section, Click on New Client Secret, then provide a description and specify the validity duration.</span></span>

6. <span data-ttu-id="732b2-120">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="732b2-120">Click **Save**.</span></span> <span data-ttu-id="732b2-121">키 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="732b2-121">The key value is displayed.</span></span>

7. <span data-ttu-id="732b2-122">값을 복사하여 안전한 장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="732b2-122">Copy the value and save it in a safe place.</span></span>


## <a name="error-when-getting-a-refresh-access-token"></a><span data-ttu-id="732b2-123">새로 고침 액세스 토큰을 사용할 때 오류 발생</span><span class="sxs-lookup"><span data-stu-id="732b2-123">Error when getting a refresh access token</span></span>
<span data-ttu-id="732b2-124">위협 인텔리전스 API 또는 SIEM 도구를 사용할 때 새로 고침 토큰을 얻려고 할 때 오류가 발생하는 경우 해당 응용 프로그램에 대한 회신 URL을 추가해야 Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="732b2-124">If you encounter an error when trying to get a refresh token when using the threat intelligence API or SIEM tools, you'll need to add reply URL for relevant application in Azure Active Directory.</span></span>

1. <span data-ttu-id="732b2-125">Azure 관리 [포털에 로그인합니다.](https://ms.portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="732b2-125">Login to the [Azure management portal](https://ms.portal.azure.com).</span></span>

2. <span data-ttu-id="732b2-126">**Azure Active Directory** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="732b2-126">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="732b2-127">테넌트 선택</span><span class="sxs-lookup"><span data-stu-id="732b2-127">Select your tenant.</span></span>

4. <span data-ttu-id="732b2-128">앱 **등록 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="732b2-128">Click **App Registrations**.</span></span> <span data-ttu-id="732b2-129">그런 다음 응용 프로그램 목록에서 응용 프로그램을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="732b2-129">Then in the applications list, select the application.</span></span>

5. <span data-ttu-id="732b2-130">다음 URL을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="732b2-130">Add the following URL:</span></span>
   - <span data-ttu-id="732b2-131">유럽 연합의 경우: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`</span><span class="sxs-lookup"><span data-stu-id="732b2-131">For the European Union: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`</span></span>
   - <span data-ttu-id="732b2-132">영국의 경우: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`</span><span class="sxs-lookup"><span data-stu-id="732b2-132">For the United Kingdom: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`</span></span>
   - <span data-ttu-id="732b2-133">미국의 경우:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback` .</span><span class="sxs-lookup"><span data-stu-id="732b2-133">For the United States:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback`.</span></span>
 
6. <span data-ttu-id="732b2-134">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="732b2-134">Click **Save**.</span></span>

## <a name="error-while-enabling-the-siem-connector-application"></a><span data-ttu-id="732b2-135">SIEM 커넥터 응용 프로그램을 사용하도록 설정하는 동안 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="732b2-135">Error while enabling the SIEM connector application</span></span>
<span data-ttu-id="732b2-136">SIEM 커넥터 응용 프로그램을 사용하도록 설정할 때 오류가 발생하는 경우 브라우저의 팝업 차단 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="732b2-136">If you encounter an error when trying to enable the SIEM connector application, check the pop-up blocker settings of your browser.</span></span> <span data-ttu-id="732b2-137">이 기능을 사용하도록 설정하면 새 창이 열리게 차단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="732b2-137">It might be blocking the new window being opened when you enable the capability.</span></span>




><span data-ttu-id="732b2-138">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="732b2-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="732b2-139">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="732b2-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshootsiem-belowfoldlink) 

## <a name="related-topics"></a><span data-ttu-id="732b2-140">관련 항목</span><span class="sxs-lookup"><span data-stu-id="732b2-140">Related topics</span></span>
- [<span data-ttu-id="732b2-141">끝점용 Microsoft Defender에서 SIEM 통합 사용</span><span class="sxs-lookup"><span data-stu-id="732b2-141">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="732b2-142">끝점 검색을 위해 Microsoft Defender를 끌어오도록 ArcSight 구성</span><span class="sxs-lookup"><span data-stu-id="732b2-142">Configure ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="732b2-143">SIEM 도구로 검색 끌어오기</span><span class="sxs-lookup"><span data-stu-id="732b2-143">Pull detections to your SIEM tools</span></span>](configure-siem.md)
- [<span data-ttu-id="732b2-144">끝점 검색 필드용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="732b2-144">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="732b2-145">REST API를 사용하여 끝점 검색을 위한 Microsoft Defender 끌어오기</span><span class="sxs-lookup"><span data-stu-id="732b2-145">Pull Microsoft Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
