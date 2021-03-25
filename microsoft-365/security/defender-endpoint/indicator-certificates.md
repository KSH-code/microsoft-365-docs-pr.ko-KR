---
title: 인증서를 기반으로 표시기 만들기
ms.reviewer: ''
description: 엔터티의 검색, 방지 및 제외를 정의하는 인증서를 기반으로 표시기를 만들 수 있습니다.
keywords: ioc, 인증서, 인증서, 관리, 허용, 차단, 차단, 클린, 악성, 파일 해시, ip 주소, URL, 도메인
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
ms.openlocfilehash: 8cf611e38bc781c2302f70f6491bb827410235b0
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164684"
---
# <a name="create-indicators-based-on-certificates"></a><span data-ttu-id="03e49-104">인증서를 기반으로 표시기 만들기</span><span class="sxs-lookup"><span data-stu-id="03e49-104">Create indicators based on certificates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="03e49-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="03e49-105">**Applies to:**</span></span>
- [<span data-ttu-id="03e49-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="03e49-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="03e49-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="03e49-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="03e49-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="03e49-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="03e49-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="03e49-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="03e49-110">인증서에 대한 표시기를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e49-110">You can create indicators for certificates.</span></span> <span data-ttu-id="03e49-111">몇 가지 일반적인 사용 사례는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="03e49-111">Some common use cases include:</span></span>

- <span data-ttu-id="03e49-112">공격 표면 감소 규칙 및 제어된 [](attack-surface-reduction.md) 폴더 액세스와 [](controlled-folders.md) 같은 차단 기술을 배포해야 하지만 허용 목록에 인증서를 추가하여 서명된 응용 프로그램의 동작을 허용해야 하는 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="03e49-112">Scenarios when you need to deploy blocking technologies, such as [attack surface reduction rules](attack-surface-reduction.md) and [controlled folder access](controlled-folders.md) but need to allow behaviors from signed applications by adding the certificate in the allow list.</span></span>
- <span data-ttu-id="03e49-113">조직 전체에서 서명된 특정 응용 프로그램의 사용을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="03e49-113">Blocking the use of a specific signed application across your organization.</span></span> <span data-ttu-id="03e49-114">응용 프로그램의 인증서를 차단하는 표시기를 만들면 Windows Defender AV에서 파일 실행(차단 및 수정)을 방지하고 자동화된 조사 및 수정이 동일하게 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e49-114">By creating an indicator to block the certificate of the application, Windows Defender AV will prevent file executions (block and remediate) and the Automated Investigation and Remediation behave the same.</span></span>


### <a name="before-you-begin"></a><span data-ttu-id="03e49-115">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="03e49-115">Before you begin</span></span>

<span data-ttu-id="03e49-116">인증서에 대한 표시기를 만들기 전에 다음 요구 사항을 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="03e49-116">It's important to understand the following requirements prior to creating indicators for certificates:</span></span>

- <span data-ttu-id="03e49-117">이 기능은 조직에서 바이러스 백신 및 클라우드 Windows Defender 사용하도록 설정된 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e49-117">This feature is available if your organization uses Windows Defender Antivirus and Cloud-based protection is enabled.</span></span> <span data-ttu-id="03e49-118">자세한 내용은 클라우드 기반 보호 [관리를 참조하세요.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="03e49-118">For more information, see [Manage cloud-based protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>
- <span data-ttu-id="03e49-119">맬웨어 방지 클라이언트 버전은 4.18.1901.x 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="03e49-119">The Antimalware client version must be  4.18.1901.x or later.</span></span>
- <span data-ttu-id="03e49-120">Windows 10 버전 1703 이상, Windows server 2016 및 2019의 컴퓨터에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e49-120">Supported on machines on Windows 10, version 1703 or later, Windows server 2016 and 2019.</span></span>
- <span data-ttu-id="03e49-121">바이러스 및 위협 방지 정의는 최신해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e49-121">The virus and threat protection definitions must be up to date.</span></span>
- <span data-ttu-id="03e49-122">이 기능은 현재 를 입력할 수 있습니다. CER 또는 . PEM 파일 확장명입니다.</span><span class="sxs-lookup"><span data-stu-id="03e49-122">This feature currently supports entering .CER or .PEM file extensions.</span></span>

>[!IMPORTANT]
> - <span data-ttu-id="03e49-123">유효한 리프 인증서는 유효한 인증 경로가 있으며 Microsoft에서 신뢰하는 루트 CA(인증 기관)에 연결되어야 하는 서명 인증서입니다.</span><span class="sxs-lookup"><span data-stu-id="03e49-123">A valid leaf certificate is a signing certificate that has a valid certification path and must be chained to the Root Certificate Authority (CA) trusted by Microsoft.</span></span>  <span data-ttu-id="03e49-124">또는 클라이언트가 신뢰하는 한 사용자 지정(자체 서명된) 인증서를 사용할 수 있습니다(루트 CA 인증서는 로컬 컴퓨터 '신뢰할 수 있는 루트 인증 기관'에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e49-124">Alternatively, a custom (self-signed) certificate can be used as long as it's trusted by the client (Root CA certificate is installed under the Local Machine 'Trusted Root Certification Authorities').</span></span>
>- <span data-ttu-id="03e49-125">허용/차단 인증서 IOC의 자식 또는 부모는 IoC 허용/차단 기능에 포함되지 않습니다. 리프 인증서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e49-125">The children or parent of the allow/block certificate IOCs are not included in the allow/block IoC functionality, only leaf certificates are supported.</span></span>
>- <span data-ttu-id="03e49-126">Microsoft 서명된 인증서는 차단할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03e49-126">Microsoft signed certificates cannot be blocked.</span></span>

#### <a name="create-an-indicator-for-certificates-from-the-settings-page"></a><span data-ttu-id="03e49-127">설정 페이지에서 인증서에 대한 표시기를 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="03e49-127">Create an indicator for certificates from the settings page:</span></span>

>[!IMPORTANT]
> <span data-ttu-id="03e49-128">인증서 IoC를 만들고 제거하는 데 최대 3시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e49-128">It can take up to 3 hours to create and remove a certificate IoC.</span></span>

1. <span data-ttu-id="03e49-129">탐색 창에서 설정   >  **표시기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="03e49-129">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="03e49-130">인증서 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03e49-130">Select the **Certificate** tab.</span></span>

3. <span data-ttu-id="03e49-131">표시기 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="03e49-131">Select **Add indicator**.</span></span>

4. <span data-ttu-id="03e49-132">다음 세부 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03e49-132">Specify the following details:</span></span>
   - <span data-ttu-id="03e49-133">Indicator - 엔터티 세부 정보를 지정하고 표시기 만료를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="03e49-133">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="03e49-134">작업 - 수행될 작업을 지정하고 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="03e49-134">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="03e49-135">범위 - 컴퓨터 그룹의 범위를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="03e49-135">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="03e49-136">요약 탭에서 세부 정보를 검토한 다음 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="03e49-136">Review the details in the Summary tab, then click **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="03e49-137">관련 항목</span><span class="sxs-lookup"><span data-stu-id="03e49-137">Related topics</span></span>
- [<span data-ttu-id="03e49-138">표시기 만들기</span><span class="sxs-lookup"><span data-stu-id="03e49-138">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="03e49-139">파일에 대한 표시기 만들기</span><span class="sxs-lookup"><span data-stu-id="03e49-139">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="03e49-140">IPS 및 URL/도메인에 대한 표시기 만들기</span><span class="sxs-lookup"><span data-stu-id="03e49-140">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="03e49-141">표시기 관리</span><span class="sxs-lookup"><span data-stu-id="03e49-141">Manage indicators</span></span>](indicator-manage.md)
