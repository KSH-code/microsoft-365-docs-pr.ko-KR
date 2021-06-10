---
title: 끝점용 Microsoft Defender에서 SIEM 통합 사용
description: SIEM(보안 정보 및 이벤트 관리) 솔루션에서 검색을 수신하려면 SIEM 통합을 사용하도록 설정하세요.
keywords: siem 커넥터, siem, 커넥터, 보안 정보 및 이벤트 사용
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 87078bb7bfc6b38788fea2a6a4c3c9108be1d5b4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842965"
---
# <a name="enable-siem-integration-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="c3059-104">끝점용 Microsoft Defender에서 SIEM 통합 사용</span><span class="sxs-lookup"><span data-stu-id="c3059-104">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c3059-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="c3059-105">**Applies to:**</span></span>
- [<span data-ttu-id="c3059-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c3059-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)


><span data-ttu-id="c3059-107">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="c3059-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c3059-108">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="c3059-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink) 

<span data-ttu-id="c3059-109">SIEM(보안 정보 및 이벤트 관리) 통합을 사용하도록 설정하여 보안 정보 및 이벤트 관리에서 검색을 Microsoft Defender 보안 센터.</span><span class="sxs-lookup"><span data-stu-id="c3059-109">Enable security information and event management (SIEM) integration so you can pull detections from Microsoft Defender Security Center.</span></span> <span data-ttu-id="c3059-110">SIEM 솔루션을 사용하여 검색을 끌어오거나 검색 REST API에 직접 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="c3059-110">Pull detections using your SIEM solution or by connecting directly to the detections REST API.</span></span>

>[!NOTE]
>- <span data-ttu-id="c3059-111">[끝점용 Microsoft Defender 경고는](alerts.md) 하나 이상의 검색으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3059-111">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="c3059-112">[끝점 검색을 위한 Microsoft Defender는](api-portal-mapping.md) 장치 및 관련 경고 세부 정보에서 발생한 의심스러운 이벤트로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3059-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
>- <span data-ttu-id="c3059-113">끝점 경고용 Microsoft Defender 경고 API는 경고 소비를 위한 최신 API로, 각 경고에 대한 자세한 관련 증거 목록을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3059-113">The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="c3059-114">자세한 내용은 [Alert 메서드](alerts.md) 및 속성 및 목록 [경고를 참조하세요.](get-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="c3059-114">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c3059-115">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="c3059-115">Prerequisites</span></span>

- <span data-ttu-id="c3059-116">설정을 활성화하는 사용자에게 AAD(응용 프로그램)에서 앱을 만들 수 Azure Active Directory 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3059-116">The user who activates the setting must have permissions to create an app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="c3059-117">이 역할은 다음과 같은 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3059-117">This is someone with the following roles:</span></span> 

  - <span data-ttu-id="c3059-118">보안 관리자 및 전역 관리자</span><span class="sxs-lookup"><span data-stu-id="c3059-118">Security Administrator and either Global Administrator</span></span>
  - <span data-ttu-id="c3059-119">클라우드 응용 프로그램 관리자</span><span class="sxs-lookup"><span data-stu-id="c3059-119">Cloud Application Administrator</span></span>
  - <span data-ttu-id="c3059-120">응용 프로그램 관리자</span><span class="sxs-lookup"><span data-stu-id="c3059-120">Application Administrator</span></span>
  - <span data-ttu-id="c3059-121">서비스 보안 주체의 소유자</span><span class="sxs-lookup"><span data-stu-id="c3059-121">Owner of the service principal</span></span>

- <span data-ttu-id="c3059-122">초기 활성화 중에 자격 증명을 입력할 수 있는 팝업 화면이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3059-122">During the initial activation, a pop-up screen is displayed for credentials to be entered.</span></span> <span data-ttu-id="c3059-123">이 사이트에 대해 팝업을 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3059-123">Make sure that you allow pop-ups for this site.</span></span>

## <a name="enabling-siem-integration"></a><span data-ttu-id="c3059-124">SIEM 통합 사용</span><span class="sxs-lookup"><span data-stu-id="c3059-124">Enabling SIEM integration</span></span> 
1. <span data-ttu-id="c3059-125">탐색 창에서 SIEM **설정**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3059-125">In the navigation pane, select **Settings** > **SIEM**.</span></span>

    ![메뉴의 SIEM 통합 설정1](images/enable_siem.png)

    >[!TIP]
    ><span data-ttu-id="c3059-127">SIEM 커넥터 응용 프로그램을 사용하도록 설정할 때 오류가 발생하는 경우 브라우저의 팝업 차단 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c3059-127">If you encounter an error when trying to enable the SIEM connector application, check the pop-up blocker settings of your browser.</span></span> <span data-ttu-id="c3059-128">이 기능을 사용하도록 설정하면 새 창이 열리게 차단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3059-128">It might be blocking the new window being opened when you enable the capability.</span></span> 

2. <span data-ttu-id="c3059-129">**SIEM 통합 사용 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c3059-129">Select **Enable SIEM integration**.</span></span> <span data-ttu-id="c3059-130">이렇게 하면 미리 채워진 값이 포함된 **SIEM** 커넥터 액세스 세부 정보 섹션이 활성화되어 응용 프로그램이 Azure Active Directory(Azure AD) 테넌트에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c3059-130">This activates the **SIEM connector access details** section with pre-populated values and an application is created under your Azure Active Directory (Azure AD) tenant.</span></span>

    > [!WARNING]
    ><span data-ttu-id="c3059-131">클라이언트 비밀은 한 번만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3059-131">The client secret is only displayed once.</span></span> <span data-ttu-id="c3059-132">복사본을 안전한 장소에 보관해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3059-132">Make sure you keep a copy of it in a safe place.</span></span><br>
     

    ![메뉴의 SIEM 통합 설정2](images/siem_details.png)

3. <span data-ttu-id="c3059-134">조직에서 사용하는 SIEM 유형을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="c3059-134">Choose the SIEM type you use in your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c3059-135">HP ArcSight를 선택하는 경우 다음 두 구성 파일을 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3059-135">If you select HP ArcSight, you'll need to save these two configuration files:</span></span><br>
   > - <span data-ttu-id="c3059-136">WDATP-connector.jsonparser.properties</span><span class="sxs-lookup"><span data-stu-id="c3059-136">WDATP-connector.jsonparser.properties</span></span>
   > - <span data-ttu-id="c3059-137">WDATP-connector.properties</span><span class="sxs-lookup"><span data-stu-id="c3059-137">WDATP-connector.properties</span></span> <br>

   <span data-ttu-id="c3059-138">프로그래밍 액세스를 통해 검색 REST API에 직접 연결하려면 일반 **API 를 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="c3059-138">If you want to connect directly to the detections REST API through programmatic access, choose **Generic API**.</span></span>

4. <span data-ttu-id="c3059-139">개별 값을 복사하거나 **파일에 세부** 정보 저장을 선택하여 모든 값이 포함된 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="c3059-139">Copy the individual values or select **Save details to file** to download a file that contains all the values.</span></span>

5. <span data-ttu-id="c3059-140">토큰 **생성을 선택하여** 액세스 및 새로 고침 토큰을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="c3059-140">Select **Generate tokens** to get an access and refresh token.</span></span>
  
   > [!NOTE]
   > <span data-ttu-id="c3059-141">90일마다 새 Refresh 토큰을 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3059-141">You'll need to generate a new Refresh token every 90 days.</span></span> 

6. <span data-ttu-id="c3059-142">끝점용 [Microsoft Defender에](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp) 대한 Azure AD 앱 등록을 만들기 위한 지침을 따르고 경고를 읽을 수 있는 올바른 권한을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c3059-142">Follow the instructions for [creating an Azure AD app registration for Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp) and assign the correct permissions to it to read alerts.</span></span>

<span data-ttu-id="c3059-143">이제 SIEM 솔루션을 구성하거나 프로그래밍 방법을 통해 검색 REST API에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3059-143">You can now proceed with configuring your SIEM solution or connecting to the detections REST API through programmatic access.</span></span> <span data-ttu-id="c3059-144">SIEM 솔루션을 구성할 때 해당 솔루션에서 검색을 받을 수 있도록 토큰을 Microsoft Defender 보안 센터.</span><span class="sxs-lookup"><span data-stu-id="c3059-144">You'll need to use the tokens when configuring your SIEM solution to allow it to receive detections from Microsoft Defender Security Center.</span></span>

## <a name="integrate-microsoft-defender-for-endpoint-with-ibm-qradar"></a><span data-ttu-id="c3059-145">끝점용 Microsoft Defender와 IBM QRadar 통합</span><span class="sxs-lookup"><span data-stu-id="c3059-145">Integrate Microsoft Defender for Endpoint with IBM QRadar</span></span> 
<span data-ttu-id="c3059-146">끝점용 Microsoft Defender에서 검색을 수집하도록 IBM QRadar를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3059-146">You can configure IBM QRadar to collect detections from Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="c3059-147">자세한 내용은 [IBM 기술 센터를 참조하세요.](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)</span><span class="sxs-lookup"><span data-stu-id="c3059-147">For more information, see [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).</span></span>

## <a name="see-also"></a><span data-ttu-id="c3059-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c3059-148">See also</span></span>
- [<span data-ttu-id="c3059-149">끝점 감지를 위해 Microsoft Defender를 끌어오도록 HP ArcSight 구성</span><span class="sxs-lookup"><span data-stu-id="c3059-149">Configure HP ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="c3059-150">끝점 검색 필드용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c3059-150">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="c3059-151">REST API를 사용하여 끝점 검색을 위한 Microsoft Defender 끌어오기</span><span class="sxs-lookup"><span data-stu-id="c3059-151">Pull Microsoft Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
- [<span data-ttu-id="c3059-152">SIEM 도구 통합 문제 해결</span><span class="sxs-lookup"><span data-stu-id="c3059-152">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
